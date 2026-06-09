# TelemetryData_pWriteDumpFile

- ea: `0x1400810e8`
- end: `0x14008129e`
- name: `TelemetryData_pWriteDumpFile`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400809b8`

## callees

- `0x140080a44`
- `0x1400810e8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140081286`
- `ntoskrnl!ZwClose` at `0x140081286`
- `ntoskrnl!NtBuildNumber` at `0x140081134`
- `ntoskrnl!ZwWriteFile` at `0x14008119d`
- `ntoskrnl!ZwWriteFile` at `0x1400811ec`
- `ntoskrnl!ZwWriteFile` at `0x14008122e`
- `ntoskrnl!ZwWriteFile` at `0x14008126f`
- `ntoskrnl!ZwWriteFile` at `0x14008119d`
- `ntoskrnl!ZwWriteFile` at `0x1400811ec`
- `ntoskrnl!ZwWriteFile` at `0x14008122e`
- `ntoskrnl!ZwWriteFile` at `0x14008126f`

## pseudocode

```c
__int64 __fastcall TelemetryData_pWriteDumpFile(__int64 a1)
{
  NTSTATUS v2; // edi
  int v3; // eax
  __int128 v4; // xmm0
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp+30h] BYREF

  IoStatusBlock = 0;
  FileHandle = 0;
  v2 = TelemetryData_pCreateDumpFile(a1, &FileHandle);
  if ( v2 >= 0 )
  {
    v3 = *(_DWORD *)(a1 + 24);
    if ( v3 && *(_QWORD *)(a1 + 16) )
    {
      *(_QWORD *)(*(_QWORD *)a1 + 4000LL) = (unsigned int)(v3 + 262192);
      *(_DWORD *)(a1 + 44) = 1886221636;
      *(_DWORD *)(a1 + 48) = 1651469378;
      *(_DWORD *)(a1 + 52) = 16;
      *(_DWORD *)(a1 + 56) = NtBuildNumber;
      *(_DWORD *)(a1 + 60) = 32;
      v4 = *(_OWORD *)(a1 + 28);
      *(_QWORD *)(a1 + 84) = 0;
      *(_OWORD *)(a1 + 64) = v4;
      *(_DWORD *)(a1 + 80) = *(_DWORD *)(a1 + 24);
    }
    v2 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)a1, *(_DWORD *)(a1 + 8), 0, 0);
    if ( v2 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 24) )
      {
        v2 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 44), 0x10u, 0, 0);
        if ( v2 >= 0 )
        {
          v2 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 60), 0x20u, 0, 0);
          if ( v2 >= 0 )
            v2 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 16), *(_DWORD *)(a1 + 24), 0, 0);
        }
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400810e8  push    rbp
0x1400810ea  push    rbx
0x1400810eb  push    rsi
0x1400810ec  push    rdi
0x1400810ed  mov     rbp, rsp
0x1400810f0  sub     rsp, 68h
0x1400810f4  xorps   xmm0, xmm0
0x1400810f7  lea     rdx, [rbp+FileHandle]
0x1400810fb  xor     esi, esi
0x1400810fd  mov     rbx, rcx
0x140081100  movups  xmmword ptr [rbp+var_18.___u0], xmm0
0x140081104  mov     [rbp+FileHandle], rsi
0x140081108  call    TelemetryData_pCreateDumpFile
0x14008110d  mov     edi, eax
0x14008110f  test    eax, eax
0x140081111  js      loc_14008127D
0x140081117  mov     eax, [rbx+18h]
0x14008111a  test    eax, eax
0x14008111c  jz      short loc_14008116F
0x14008111e  cmp     [rbx+10h], rsi
0x140081122  jz      short loc_14008116F
0x140081124  lea     ecx, [rax+40030h]
0x14008112a  mov     rax, [rbx]
0x14008112d  mov     [rax+0FA0h], rcx
0x140081134  mov     rax, cs:NtBuildNumber
0x14008113b  mov     dword ptr [rbx+2Ch], 706D7544h
0x140081142  mov     dword ptr [rbx+30h], 626F6C42h
0x140081149  mov     dword ptr [rbx+34h], 10h
0x140081150  mov     ecx, [rax]
0x140081152  mov     [rbx+38h], ecx
0x140081155  mov     dword ptr [rbx+3Ch], 20h ; ' '
0x14008115c  movups  xmm0, xmmword ptr [rbx+1Ch]
0x140081160  mov     [rbx+54h], rsi
0x140081164  movdqu  xmmword ptr [rbx+40h], xmm0
0x140081169  mov     eax, [rbx+18h]
0x14008116c  mov     [rbx+50h], eax
0x14008116f  mov     eax, [rbx+8]
0x140081172  xor     r9d, r9d; ApcContext
0x140081175  mov     rcx, [rbp+FileHandle]; FileHandle
0x140081179  xor     r8d, r8d; ApcRoutine
0x14008117c  mov     [rsp+68h+Key], rsi; Key
0x140081181  xor     edx, edx; Event
0x140081183  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140081188  mov     [rsp+68h+Length], eax; Length
0x14008118c  mov     rax, [rbx]
0x14008118f  mov     [rsp+68h+Buffer], rax; Buffer
0x140081194  lea     rax, [rbp+var_18]
0x140081198  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14008119d  call    cs:__imp_ZwWriteFile
0x1400811a4  nop     dword ptr [rax+rax+00h]
0x1400811a9  mov     edi, eax
0x1400811ab  test    eax, eax
0x1400811ad  js      loc_14008127D
0x1400811b3  cmp     [rbx+18h], esi
0x1400811b6  jbe     loc_14008127D
0x1400811bc  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400811c0  lea     rax, [rbx+2Ch]
0x1400811c4  mov     [rsp+68h+Key], rsi; Key
0x1400811c9  xor     r9d, r9d; ApcContext
0x1400811cc  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1400811d1  xor     r8d, r8d; ApcRoutine
0x1400811d4  mov     [rsp+68h+Length], 10h; Length
0x1400811dc  xor     edx, edx; Event
0x1400811de  mov     [rsp+68h+Buffer], rax; Buffer
0x1400811e3  lea     rax, [rbp+var_18]
0x1400811e7  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400811ec  call    cs:__imp_ZwWriteFile
0x1400811f3  nop     dword ptr [rax+rax+00h]
0x1400811f8  mov     edi, eax
0x1400811fa  test    eax, eax
0x1400811fc  js      short loc_14008127D
0x1400811fe  mov     rcx, [rbp+FileHandle]; FileHandle
0x140081202  lea     rax, [rbx+3Ch]
0x140081206  mov     [rsp+68h+Key], rsi; Key
0x14008120b  xor     r9d, r9d; ApcContext
0x14008120e  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140081213  xor     r8d, r8d; ApcRoutine
0x140081216  mov     [rsp+68h+Length], 20h ; ' '; Length
0x14008121e  xor     edx, edx; Event
0x140081220  mov     [rsp+68h+Buffer], rax; Buffer
0x140081225  lea     rax, [rbp+var_18]
0x140081229  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14008122e  call    cs:__imp_ZwWriteFile
0x140081235  nop     dword ptr [rax+rax+00h]
0x14008123a  mov     edi, eax
0x14008123c  test    eax, eax
0x14008123e  js      short loc_14008127D
0x140081240  mov     eax, [rbx+18h]
0x140081243  xor     r9d, r9d; ApcContext
0x140081246  mov     rcx, [rbp+FileHandle]; FileHandle
0x14008124a  xor     r8d, r8d; ApcRoutine
0x14008124d  mov     [rsp+68h+Key], rsi; Key
0x140081252  xor     edx, edx; Event
0x140081254  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140081259  mov     [rsp+68h+Length], eax; Length
0x14008125d  mov     rax, [rbx+10h]
0x140081261  mov     [rsp+68h+Buffer], rax; Buffer
0x140081266  lea     rax, [rbp+var_18]
0x14008126a  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14008126f  call    cs:__imp_ZwWriteFile
0x140081276  nop     dword ptr [rax+rax+00h]
0x14008127b  mov     edi, eax
0x14008127d  mov     rcx, [rbp+FileHandle]; Handle
0x140081281  test    rcx, rcx
0x140081284  jz      short loc_140081292
0x140081286  call    cs:__imp_ZwClose
0x14008128d  nop     dword ptr [rax+rax+00h]
0x140081292  mov     eax, edi
0x140081294  add     rsp, 68h
0x140081298  pop     rdi
0x140081299  pop     rsi
0x14008129a  pop     rbx
0x14008129b  pop     rbp
0x14008129c  retn
```

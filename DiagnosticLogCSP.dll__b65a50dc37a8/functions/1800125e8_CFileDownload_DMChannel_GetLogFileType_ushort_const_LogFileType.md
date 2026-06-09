# CFileDownload_DMChannel::GetLogFileType(ushort const *,LogFileType &)

- ea: `0x1800125e8`
- end: `0x180012669`
- name: `?GetLogFileType@CFileDownload_DMChannel@@IEAAJPEBGAEAW4LogFileType@@@Z`
- size: `129`
- prototype: `int(CFileDownload_DMChannel *__hidden this, const unsigned __int16 *, enum LogFileType *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012404`
- `0x180012840`

## callees

- `0x18000e558`
- `0x18000f9fc`
- `0x1800125e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012640`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012640`

## string_xrefs

- `0x180012639`: `MdmConfiguration`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::GetLogFileType(
        CFileDownload_DMChannel *this,
        const unsigned __int16 *a2,
        enum LogFileType *a3)
{
  unsigned int v5; // esi

  *(_DWORD *)a3 = 3;
  if ( a2 )
  {
    v5 = 0;
    if ( (int)CEventLogChannel::IsChannelRegistered(a2) < 0 )
    {
      if ( (int)CEtwLogCollector::IsCollectorRegistered(a2) < 0 )
      {
        if ( !(unsigned int)_o__wcsicmp(L"MdmConfiguration", a2) )
          *(_DWORD *)a3 = 2;
      }
      else
      {
        *(_DWORD *)a3 = 0;
      }
    }
    else
    {
      *(_DWORD *)a3 = 1;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1800125e8  mov     [rsp+arg_0], rbx
0x1800125ed  mov     [rsp+arg_8], rsi
0x1800125f2  push    rdi
0x1800125f3  sub     rsp, 20h
0x1800125f7  mov     dword ptr [r8], 3
0x1800125fe  mov     rbx, r8
0x180012601  mov     rdi, rdx
0x180012604  test    rdx, rdx
0x180012607  jnz     short loc_180012610
0x180012609  mov     esi, 80070057h
0x18001260e  jmp     short loc_180012656
0x180012610  mov     rcx, rdi; unsigned __int16 *
0x180012613  xor     esi, esi
0x180012615  call    ?IsChannelRegistered@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::IsChannelRegistered(ushort const *)
0x18001261a  test    eax, eax
0x18001261c  js      short loc_180012626
0x18001261e  mov     dword ptr [rbx], 1
0x180012624  jmp     short loc_180012656
0x180012626  mov     rcx, rdi; unsigned __int16 *
0x180012629  call    ?IsCollectorRegistered@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::IsCollectorRegistered(ushort const *)
0x18001262e  test    eax, eax
0x180012630  js      short loc_180012636
0x180012632  mov     [rbx], esi
0x180012634  jmp     short loc_180012656
0x180012636  mov     rdx, rdi
0x180012639  lea     rcx, aMdmconfigurati; "MdmConfiguration"
0x180012640  call    cs:__imp__o__wcsicmp
0x180012647  nop     dword ptr [rax+rax+00h]
0x18001264c  test    eax, eax
0x18001264e  jnz     short loc_180012656
0x180012650  mov     dword ptr [rbx], 2
0x180012656  mov     rbx, [rsp+28h+arg_0]
0x18001265b  mov     eax, esi
0x18001265d  mov     rsi, [rsp+28h+arg_8]
0x180012662  add     rsp, 20h
0x180012666  pop     rdi
0x180012667  retn
```

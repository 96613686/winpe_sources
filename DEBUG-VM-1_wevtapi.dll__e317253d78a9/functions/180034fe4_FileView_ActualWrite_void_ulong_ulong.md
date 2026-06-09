# FileView::ActualWrite(void *,ulong,ulong)

- ea: `0x180034fe4`
- end: `0x18003514f`
- name: `?ActualWrite@FileView@@AEAAKPEAXKK@Z`
- size: `363`
- prototype: `unsigned int(FileView *__hidden this, void *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180031754`
- `0x180033b9c`
- `0x180033cec`
- `0x180033fa8`

## callees

- `0x180023548`
- `0x180034fe4`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180035092`
- `ntdll!NtWriteFile` at `0x180035092`
- `ntdll!RtlNtStatusToDosError` at `0x1800350a2`
- `ntdll!RtlNtStatusToDosError` at `0x1800350a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035101`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800350ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035101`

## pseudocode

```c
__int64 __fastcall FileView::ActualWrite(FileView *this, void *a2, unsigned int a3, ULONG Length)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  LastErrInfo *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int v13; // eax
  ULONG v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 1);
  v5 = Length;
  IoStatusBlock = 0;
  if ( v4 == -1 )
  {
    v8 = WPP_GLOBAL_Control;
    v9 = 4317;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 13;
LABEL_6:
    WPP_SF_D(*((_QWORD *)v8 + 2), v10, &WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, v9);
    return v9;
  }
  v12 = *((_QWORD *)this + 2);
  ByteOffset.QuadPart = a3 + v4;
  v13 = NtWriteFile(a2, 0, 0, 0, &IoStatusBlock, (PVOID)(a3 + v12), Length, &ByteOffset, 0);
  if ( v13 < 0 )
  {
    *((_BYTE *)this + 40) = 4;
    v14 = RtlNtStatusToDosError(v13);
    *((_DWORD *)this + 9) = v14;
    SetLastError(v14);
    v9 = *((_DWORD *)this + 9);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 14;
    goto LABEL_6;
  }
  if ( v5 != IoStatusBlock.Information )
  {
    *((_BYTE *)this + 40) = 4;
    *((_DWORD *)this + 9) = 29;
    SetLastError(0x1Du);
    v9 = *((_DWORD *)this + 9);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v9;
    }
    v10 = 15;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180034fe4  mov     [rsp+arg_8], rbx
0x180034fe9  push    rdi
0x180034fea  sub     rsp, 60h
0x180034fee  mov     rax, [rcx+8]
0x180034ff2  xorps   xmm0, xmm0
0x180034ff5  mov     edi, r9d
0x180034ff8  mov     r10, rdx
0x180034ffb  mov     rbx, rcx
0x180034ffe  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x180035003  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035007  jnz     short loc_18003504F
0x180035009  mov     rcx, cs:WPP_GLOBAL_Control
0x180035010  lea     rax, WPP_GLOBAL_Control
0x180035017  mov     ebx, 10DDh
0x18003501c  cmp     rcx, rax
0x18003501f  jz      short loc_180035048
0x180035021  test    dword ptr [rcx+1Ch], 8000h
0x180035028  jz      short loc_180035048
0x18003502a  cmp     byte ptr [rcx+19h], 2
0x18003502e  jb      short loc_180035048
0x180035030  mov     edx, 0Dh
0x180035035  mov     rcx, [rcx+10h]
0x180035039  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x180035040  mov     r9d, ebx
0x180035043  call    WPP_SF_D
0x180035048  mov     eax, ebx
0x18003504a  jmp     loc_180035144
0x18003504f  mov     rdx, [rbx+10h]
0x180035053  xor     r9d, r9d; ApcContext
0x180035056  mov     ecx, r8d
0x180035059  xor     r8d, r8d; ApcRoutine
0x18003505c  add     rax, rcx
0x18003505f  mov     [rsp+68h+Key], 0; Key
0x180035068  add     rdx, rcx
0x18003506b  mov     qword ptr [rsp+68h+arg_0], rax
0x180035070  lea     rax, [rsp+68h+arg_0]
0x180035075  mov     rcx, r10; FileHandle
0x180035078  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x18003507d  lea     rax, [rsp+68h+var_18]
0x180035082  mov     [rsp+68h+Length], edi; Length
0x180035086  mov     [rsp+68h+Buffer], rdx; Buffer
0x18003508b  xor     edx, edx; Event
0x18003508d  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x180035092  call    cs:__imp_NtWriteFile
0x180035098  test    eax, eax
0x18003509a  jns     short loc_1800350EE
0x18003509c  mov     ecx, eax; Status
0x18003509e  mov     byte ptr [rbx+28h], 4
0x1800350a2  call    cs:__imp_RtlNtStatusToDosError
0x1800350a8  mov     ecx, eax; dwErrCode
0x1800350aa  mov     [rbx+24h], eax
0x1800350ad  call    cs:__imp_SetLastError
0x1800350b3  mov     ebx, [rbx+24h]
0x1800350b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350bd  lea     rax, WPP_GLOBAL_Control
0x1800350c4  cmp     rcx, rax
0x1800350c7  jz      loc_180035048
0x1800350cd  test    dword ptr [rcx+1Ch], 8000h
0x1800350d4  jz      loc_180035048
0x1800350da  cmp     byte ptr [rcx+19h], 2
0x1800350de  jb      loc_180035048
0x1800350e4  mov     edx, 0Eh
0x1800350e9  jmp     loc_180035035
0x1800350ee  cmp     rdi, [rsp+68h+var_18.Information]
0x1800350f3  jz      short loc_180035142
0x1800350f5  mov     ecx, 1Dh; dwErrCode
0x1800350fa  mov     byte ptr [rbx+28h], 4
0x1800350fe  mov     [rbx+24h], ecx
0x180035101  call    cs:__imp_SetLastError
0x180035107  mov     ebx, [rbx+24h]
0x18003510a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035111  lea     rax, WPP_GLOBAL_Control
0x180035118  cmp     rcx, rax
0x18003511b  jz      loc_180035048
0x180035121  test    dword ptr [rcx+1Ch], 8000h
0x180035128  jz      loc_180035048
0x18003512e  cmp     byte ptr [rcx+19h], 2
0x180035132  jb      loc_180035048
0x180035138  mov     edx, 0Fh
0x18003513d  jmp     loc_180035035
0x180035142  xor     eax, eax
0x180035144  mov     rbx, [rsp+68h+arg_8]
0x180035149  add     rsp, 60h
0x18003514d  pop     rdi
0x18003514e  retn
```

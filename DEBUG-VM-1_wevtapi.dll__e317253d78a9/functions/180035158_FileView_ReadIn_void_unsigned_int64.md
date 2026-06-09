# FileView::ReadIn(void *,unsigned __int64)

- ea: `0x180035158`
- end: `0x180035272`
- name: `?ReadIn@FileView@@QEAAXPEAX_K@Z`
- size: `282`
- prototype: `void(FileView *__hidden this, void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180031564`
- `0x180031754`
- `0x180032bb8`
- `0x1800330b8`
- `0x180033174`
- `0x180033258`

## callees

- `0x180023548`
- `0x180035158`
- `0x180038fb4`

## import_xrefs

- `ntdll!NtReadFile` at `0x1800351ae`
- `ntdll!NtReadFile` at `0x1800351ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800351ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800351ca`
- `ntdll!RtlSetLastWin32Error` at `0x1800351d5`
- `ntdll!RtlSetLastWin32Error` at `0x1800351d5`

## pseudocode

```c
void __fastcall FileView::ReadIn(union _LARGE_INTEGER *this, void *a2, union _LARGE_INTEGER a3)
{
  int v5; // eax
  ULONG v6; // eax
  unsigned int HighPart; // ebx
  void *QuadPart; // [rsp+28h] [rbp-70h]
  ULONG Length; // [rsp+30h] [rbp-68h]
  struct _IO_STATUS_BLOCK v10; // [rsp+50h] [rbp-48h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp-28h]
  unsigned int v13; // [rsp+78h] [rbp-20h]
  int v14; // [rsp+7Ch] [rbp-1Ch]
  int v15; // [rsp+80h] [rbp-18h]
  union _LARGE_INTEGER v16; // [rsp+A0h] [rbp+8h] BYREF

  Length = this[4].LowPart;
  QuadPart = (void *)this[2].QuadPart;
  v16 = a3;
  v10 = 0;
  v5 = NtReadFile(a2, 0, 0, 0, &v10, QuadPart, Length, &v16, 0);
  if ( v5 < 0 )
  {
    this[1].QuadPart = -1;
    LOBYTE(this[5].LowPart) = 2;
    v6 = RtlNtStatusToDosError(v5);
    this[4].HighPart = v6;
    RtlSetLastWin32Error(v6);
    HighPart = this[4].HighPart;
    if ( !HighPart )
      HighPart = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, HighPart);
    }
    v12 = 0;
    v13 = HighPart;
    v14 = -1;
    pExceptionObject = 0;
    v15 = 112;
    throw (EvtException *)&pExceptionObject;
  }
  this[1] = a3;
}

```

## disassembly

```asm
0x180035158  mov     r11, rsp
0x18003515b  mov     [r11+10h], rbx
0x18003515f  push    rdi
0x180035160  sub     rsp, 90h
0x180035167  mov     qword ptr [r11-58h], 0
0x18003516f  lea     rax, [r11+8]
0x180035173  mov     [r11-60h], rax
0x180035177  mov     r10, rdx
0x18003517a  mov     eax, [rcx+20h]
0x18003517d  mov     rdi, r8
0x180035180  mov     [rsp+98h+Length], eax; Length
0x180035184  mov     rbx, rcx
0x180035187  mov     rax, [rcx+10h]
0x18003518b  xorps   xmm0, xmm0
0x18003518e  mov     [r11-70h], rax
0x180035192  xor     r9d, r9d; ApcContext
0x180035195  lea     rax, [r11-48h]
0x180035199  mov     [r11+8], r8
0x18003519d  xor     r8d, r8d; ApcRoutine
0x1800351a0  mov     [r11-78h], rax
0x1800351a4  xor     edx, edx; Event
0x1800351a6  mov     rcx, r10; FileHandle
0x1800351a9  movups  [rsp+98h+var_48], xmm0
0x1800351ae  call    cs:__imp_NtReadFile
0x1800351b4  test    eax, eax
0x1800351b6  jns     loc_18003525D
0x1800351bc  mov     ecx, eax; Status
0x1800351be  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1800351c6  mov     byte ptr [rbx+28h], 2
0x1800351ca  call    cs:__imp_RtlNtStatusToDosError
0x1800351d0  mov     ecx, eax; LastError
0x1800351d2  mov     [rbx+24h], eax
0x1800351d5  call    cs:__imp_RtlSetLastWin32Error
0x1800351db  mov     ebx, [rbx+24h]
0x1800351de  mov     eax, 507h
0x1800351e3  test    ebx, ebx
0x1800351e5  cmovz   ebx, eax
0x1800351e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351ef  lea     rax, WPP_GLOBAL_Control
0x1800351f6  cmp     rcx, rax
0x1800351f9  jz      short loc_180035222
0x1800351fb  test    dword ptr [rcx+1Ch], 8000h
0x180035202  jz      short loc_180035222
0x180035204  cmp     byte ptr [rcx+19h], 2
0x180035208  jb      short loc_180035222
0x18003520a  mov     rcx, [rcx+10h]
0x18003520e  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x180035215  mov     edx, 0Ch
0x18003521a  mov     r9d, ebx
0x18003521d  call    WPP_SF_D
0x180035222  xorps   xmm0, xmm0
0x180035225  mov     [rsp+98h+var_28], 0
0x18003522e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035235  mov     [rsp+98h+var_20], ebx
0x180035239  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003523e  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x180035246  movdqu  [rsp+98h+pExceptionObject], xmm0
0x18003524c  mov     [rsp+98h+var_18], 70h ; 'p'
0x180035257  call    _CxxThrowException_0
0x18003525d  mov     [rbx+8], rdi
0x180035261  mov     rbx, [rsp+98h+arg_8]
0x180035269  add     rsp, 90h
0x180035270  pop     rdi
0x180035271  retn
```

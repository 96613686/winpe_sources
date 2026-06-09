# CProviderSession::GetDataSource(_GUID const &,IUnknown * *)

- ea: `0x18002dcb0`
- end: `0x18002dd79`
- name: `?GetDataSource@CProviderSession@@UEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(CProviderSession *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d770`
- `0x18002dcb0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002dcdd`
- `KERNEL32!GetCurrentThreadId` at `0x18002dcdd`
- `KERNEL32!LeaveCriticalSection` at `0x18002dd64`
- `KERNEL32!LeaveCriticalSection` at `0x18002dd64`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002dcf8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002dcf8`
- `MSDART!UMSEnterCSWraper` at `0x18002dccd`
- `MSDART!UMSEnterCSWraper` at `0x18002dccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderSession::GetDataSource(
        CProviderSession *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  char *v6; // rbx
  DWORD *v7; // rdi
  unsigned int v8; // r8d
  int v9; // edx
  __int64 (__fastcall ***v10)(_QWORD, const struct _GUID *, struct IUnknown **); // rcx
  unsigned int v11; // esi
  __int64 v13; // rcx

  v6 = (char *)this + 40;
  UMSEnterCSWraper((char *)this + 40);
  v7 = (DWORD *)(v6 + 8);
  if ( !*((_DWORD *)v6 + 3) )
    *v7 = GetCurrentThreadId();
  ++*((_DWORD *)v6 + 3);
  ++*((_DWORD *)v6 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this + 88) = IID_IGetDataSource;
  *((_DWORD *)this + 1051) = 0;
  if ( a3 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, struct IUnknown **))*((_QWORD *)this + 8);
    if ( v10 )
      v9 = (**v10)(v10, a2, a3);
    else
      v9 = -2147467259;
  }
  else
  {
    v9 = -2147024809;
  }
  v11 = CError::PostErrorIfNone((CProviderSession *)((char *)this + 72), v9, v8);
  --*((_DWORD *)v6 + 4);
  if ( (*((_DWORD *)v6 + 3))-- == 1 )
    *v7 = -1;
  v13 = *(_QWORD *)v6;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x18002dcb0  push    rbx
0x18002dcb2  push    rbp
0x18002dcb3  push    rsi
0x18002dcb4  push    rdi
0x18002dcb5  push    r14
0x18002dcb7  push    r15
0x18002dcb9  sub     rsp, 28h
0x18002dcbd  mov     r14, r8
0x18002dcc0  mov     r15, rdx
0x18002dcc3  mov     rbp, rcx
0x18002dcc6  lea     rbx, [rcx+28h]
0x18002dcca  mov     rcx, rbx
0x18002dccd  call    cs:__imp_UMSEnterCSWraper
0x18002dcd3  lea     rdi, [rbx+8]
0x18002dcd7  cmp     dword ptr [rbx+0Ch], 0
0x18002dcdb  jnz     short loc_18002DCE5
0x18002dcdd  call    cs:__imp_GetCurrentThreadId
0x18002dce3  mov     [rdi], eax
0x18002dce5  inc     dword ptr [rbx+0Ch]
0x18002dce8  inc     dword ptr [rbx+10h]
0x18002dceb  mov     [rsp+58h+arg_0], rbx
0x18002dcf0  lea     rsi, [rbp+48h]
0x18002dcf4  xor     edx, edx; perrinfo
0x18002dcf6  xor     ecx, ecx; dwReserved
0x18002dcf8  call    cs:__imp_SetErrorInfo
0x18002dcfe  movups  xmm0, xmmword ptr cs:IID_IGetDataSource.Data1
0x18002dd05  movdqu  xmmword ptr [rsi+10h], xmm0
0x18002dd0a  mov     dword ptr [rsi+1024h], 0
0x18002dd14  test    r14, r14
0x18002dd17  jnz     short loc_18002DD20
0x18002dd19  mov     edx, 80070057h
0x18002dd1e  jmp     short loc_18002DD43
0x18002dd20  mov     rcx, [rbp+40h]
0x18002dd24  test    rcx, rcx
0x18002dd27  jnz     short loc_18002DD30
0x18002dd29  mov     edx, 80004005h
0x18002dd2e  jmp     short loc_18002DD43
0x18002dd30  mov     rax, [rcx]
0x18002dd33  mov     r8, r14
0x18002dd36  mov     rdx, r15
0x18002dd39  mov     rax, [rax]
0x18002dd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd41  mov     edx, eax; int
0x18002dd43  mov     rcx, rsi; this
0x18002dd46  call    ?PostErrorIfNone@CError@@QEAAJJK@Z; CError::PostErrorIfNone(long,ulong)
0x18002dd4b  mov     esi, eax
0x18002dd4d  or      edx, 0FFFFFFFFh
0x18002dd50  add     [rbx+10h], edx
0x18002dd53  add     [rbx+0Ch], edx
0x18002dd56  jnz     short loc_18002DD5A
0x18002dd58  mov     [rdi], edx
0x18002dd5a  mov     rcx, [rbx]
0x18002dd5d  dec     dword ptr [rcx+30h]
0x18002dd60  add     rcx, 8; lpCriticalSection
0x18002dd64  call    cs:__imp_LeaveCriticalSection
0x18002dd6a  mov     eax, esi
0x18002dd6c  add     rsp, 28h
0x18002dd70  pop     r15
0x18002dd72  pop     r14
0x18002dd74  pop     rdi
0x18002dd75  pop     rsi
0x18002dd76  pop     rbp
0x18002dd77  pop     rbx
0x18002dd78  retn
```

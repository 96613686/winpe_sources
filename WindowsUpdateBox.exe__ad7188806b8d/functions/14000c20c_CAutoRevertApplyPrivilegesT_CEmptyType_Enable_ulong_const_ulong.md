# CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)

- ea: `0x14000c20c`
- end: `0x14000c405`
- name: `?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140007b94`
- `0x140009aa8`
- `0x14000a7d0`
- `0x140018ccc`
- `0x14004d240`
- `0x14004eda0`
- `0x14004f8f4`

## callees

- `0x140001c40`
- `0x140001d78`
- `0x140003cf8`
- `0x140006538`
- `0x1400076c8`
- `0x14000c20c`
- `0x1400135b8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c272`
- `KERNEL32!HeapFree` at `0x14000c3c1`
- `KERNEL32!HeapFree` at `0x14000c272`
- `KERNEL32!HeapFree` at `0x14000c3c1`
- `KERNEL32!HeapAlloc` at `0x14000c2b1`
- `KERNEL32!HeapAlloc` at `0x14000c2b1`
- `KERNEL32!GetProcessHeap` at `0x14000c25e`
- `KERNEL32!GetProcessHeap` at `0x14000c29d`
- `KERNEL32!GetProcessHeap` at `0x14000c3ad`
- `KERNEL32!GetProcessHeap` at `0x14000c25e`
- `KERNEL32!GetProcessHeap` at `0x14000c29d`
- `KERNEL32!GetProcessHeap` at `0x14000c3ad`
- `ntdll!RtlAdjustPrivilege` at `0x14000c33f`
- `ntdll!RtlAdjustPrivilege` at `0x14000c33f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(void **a1, ULONG *a2, unsigned int a3)
{
  unsigned __int64 v3; // r12
  unsigned int v6; // edi
  char *v7; // rcx
  char *v8; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v10; // rbx
  bool v11; // cf
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  _QWORD *v14; // rax
  char *v15; // rsi
  __int64 v16; // rbp
  __int64 v17; // rbx
  ULONG v18; // eax
  NTSTATUS v19; // eax
  char *v20; // rcx
  char *v21; // rbx
  HANDLE v22; // rax
  void *v24; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v25; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v26; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v24 = 0;
  v6 = 0;
  v25 = 0;
  v7 = (char *)*a1;
  if ( v7 )
  {
    v8 = v7 - 8;
    `eh vector destructor iterator'(
      v7,
      8u,
      *((_QWORD *)v7 - 1),
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *a1 = 0;
  }
  v10 = 8 * v3;
  if ( !is_mul_ok(v3, 8u) )
    v10 = -1;
  v11 = __CFADD__(v10, 8);
  v12 = v10 + 8;
  if ( v11 )
    v12 = -1;
  v13 = GetProcessHeap();
  v14 = HeapAlloc(v13, 0, v12);
  v26 = v14;
  if ( v14 )
  {
    *v14 = v3;
    v15 = (char *)(v14 + 1);
    `eh vector constructor iterator'(
      v14 + 1,
      8u,
      v3,
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::CPrivilegeState,
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState);
  }
  else
  {
    v15 = 0;
  }
  if ( !v15 )
  {
    v24 = 0;
    v6 = -2147024882;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_23;
  }
  v24 = v15;
  v16 = 0;
  if ( (_DWORD)v3 )
  {
    v17 = 0;
    while ( 1 )
    {
      v18 = *a2;
      *(_DWORD *)&v15[v17] = *a2;
      v19 = RtlAdjustPrivilege(v18, 1u, 0, (PBOOLEAN)&v15[8 * v16 + 5]);
      if ( v19 >= 0 )
        v15[v17 + 4] = 1;
      if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v19, &v25) )
        break;
      v16 = (unsigned int)(v16 + 1);
      ++a2;
      v17 += 8;
      if ( (unsigned int)v16 >= (unsigned int)v3 )
      {
        v6 = v25;
        goto LABEL_20;
      }
    }
    v6 = v25;
    goto LABEL_12;
  }
LABEL_20:
  v24 = 0;
  v20 = (char *)*a1;
  if ( *a1 )
  {
    v21 = v20 - 8;
    `eh vector destructor iterator'(
      v20,
      8u,
      *((_QWORD *)v20 - 1),
      (void (*)(void *))CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState);
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  *a1 = v15;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  SP<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState,SP_CPP_ARRAY<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState>>::~SP<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState,SP_CPP_ARRAY<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState>>(&v24);
  return v6;
}

```

## disassembly

```asm
0x14000c20c  mov     rax, rsp
0x14000c20f  push    rbx
0x14000c210  push    rbp
0x14000c211  push    rsi
0x14000c212  push    rdi
0x14000c213  push    r12
0x14000c215  push    r14
0x14000c217  push    r15
0x14000c219  sub     rsp, 40h
0x14000c21d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x14000c225  mov     r12d, r8d
0x14000c228  mov     r15, rdx
0x14000c22b  mov     r14, rcx
0x14000c22e  mov     qword ptr [rax+8], 0
0x14000c236  xor     edi, edi
0x14000c238  mov     [rax+18h], edi
0x14000c23b  mov     rcx, [rcx]; void *
0x14000c23e  lea     rax, ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x14000c245  lea     esi, [rdi+8]
0x14000c248  test    rcx, rcx
0x14000c24b  jz      short loc_14000C282
0x14000c24d  lea     rbx, [rcx-8]
0x14000c251  mov     r9, rax; void (*)(void *)
0x14000c254  mov     r8, [rbx]; unsigned __int64
0x14000c257  mov     edx, esi; unsigned __int64
0x14000c259  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000c25e  call    cs:__imp_GetProcessHeap
0x14000c265  nop     dword ptr [rax+rax+00h]
0x14000c26a  mov     rcx, rax; hHeap
0x14000c26d  mov     r8, rbx; lpMem
0x14000c270  xor     edx, edx; dwFlags
0x14000c272  call    cs:__imp_HeapFree
0x14000c279  nop     dword ptr [rax+rax+00h]
0x14000c27e  nop
0x14000c27f  mov     [r14], rdi
0x14000c282  mov     rax, rsi
0x14000c285  mul     r12
0x14000c288  mov     rbx, rax
0x14000c28b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000c292  cmovb   rbx, rax
0x14000c296  add     rbx, rsi
0x14000c299  cmovb   rbx, rax
0x14000c29d  call    cs:__imp_GetProcessHeap
0x14000c2a4  nop     dword ptr [rax+rax+00h]
0x14000c2a9  mov     rcx, rax; hHeap
0x14000c2ac  mov     r8, rbx; dwBytes
0x14000c2af  xor     edx, edx; dwFlags
0x14000c2b1  call    cs:__imp_HeapAlloc
0x14000c2b8  nop     dword ptr [rax+rax+00h]
0x14000c2bd  mov     [rsp+78h+arg_18], rax
0x14000c2c5  test    rax, rax
0x14000c2c8  jz      short loc_14000C2F6
0x14000c2ca  mov     [rax], r12
0x14000c2cd  lea     rsi, [rax+8]
0x14000c2d1  lea     rax, ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x14000c2d8  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x14000c2dd  lea     r9, ??0CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; void (*)(void *)
0x14000c2e4  mov     r8, r12; unsigned __int64
0x14000c2e7  mov     edx, 8; unsigned __int64
0x14000c2ec  mov     rcx, rsi; void *
0x14000c2ef  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x14000c2f4  jmp     short loc_14000C2F8
0x14000c2f6  xor     esi, esi
0x14000c2f8  test    rsi, rsi
0x14000c2fb  jnz     short loc_14000C316
0x14000c2fd  mov     [rsp+78h+arg_0], rsi
0x14000c305  mov     edi, 8007000Eh
0x14000c30a  mov     ecx, edi
0x14000c30c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000c311  jmp     loc_14000C3D1
0x14000c316  mov     [rsp+78h+arg_0], rsi
0x14000c31e  xor     ebp, ebp
0x14000c320  test    r12d, r12d
0x14000c323  jz      short loc_14000C381
0x14000c325  xor     ebx, ebx
0x14000c327  mov     eax, [r15]
0x14000c32a  mov     [rbx+rsi], eax
0x14000c32d  lea     r9, ds:5[rbp*8]
0x14000c335  add     r9, rsi; OldValue
0x14000c338  xor     r8d, r8d; ForThread
0x14000c33b  mov     dl, 1; NewValue
0x14000c33d  mov     ecx, eax; Privilege
0x14000c33f  call    cs:__imp_RtlAdjustPrivilege
0x14000c346  nop     dword ptr [rax+rax+00h]
0x14000c34b  test    eax, eax
0x14000c34d  js      short loc_14000C354
0x14000c34f  mov     byte ptr [rbx+rsi+4], 1
0x14000c354  lea     rdx, [rsp+78h+arg_10]
0x14000c35c  mov     ecx, eax
0x14000c35e  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x14000c363  test    eax, eax
0x14000c365  jz      loc_14000C3F8
0x14000c36b  inc     ebp
0x14000c36d  add     r15, 4
0x14000c371  add     rbx, 8
0x14000c375  cmp     ebp, r12d
0x14000c378  jb      short loc_14000C327
0x14000c37a  mov     edi, [rsp+78h+arg_10]
0x14000c381  mov     [rsp+78h+arg_0], 0
0x14000c38d  mov     rcx, [r14]; void *
0x14000c390  test    rcx, rcx
0x14000c393  jz      short loc_14000C3CE
0x14000c395  lea     rbx, [rcx-8]
0x14000c399  lea     r9, ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; void (*)(void *)
0x14000c3a0  mov     r8, [rbx]; unsigned __int64
0x14000c3a3  mov     edx, 8; unsigned __int64
0x14000c3a8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000c3ad  call    cs:__imp_GetProcessHeap
0x14000c3b4  nop     dword ptr [rax+rax+00h]
0x14000c3b9  mov     rcx, rax; hHeap
0x14000c3bc  mov     r8, rbx; lpMem
0x14000c3bf  xor     edx, edx; dwFlags
0x14000c3c1  call    cs:__imp_HeapFree
0x14000c3c8  nop     dword ptr [rax+rax+00h]
0x14000c3cd  nop
0x14000c3ce  mov     [r14], rsi
0x14000c3d1  mov     ecx, edi
0x14000c3d3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c3d8  nop
0x14000c3d9  lea     rcx, [rsp+78h+arg_0]
0x14000c3e1  call    ??1?$SP@UCPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@V?$SP_CPP_ARRAY@UCPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@@@@@QEAA@XZ; SP<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState,SP_CPP_ARRAY<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState>>::~SP<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState,SP_CPP_ARRAY<CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState>>(void)
0x14000c3e6  mov     eax, edi
0x14000c3e8  add     rsp, 40h
0x14000c3ec  pop     r15
0x14000c3ee  pop     r14
0x14000c3f0  pop     r12
0x14000c3f2  pop     rdi
0x14000c3f3  pop     rsi
0x14000c3f4  pop     rbp
0x14000c3f5  pop     rbx
0x14000c3f6  retn
0x14000c3f8  mov     edi, [rsp+78h+arg_10]
0x14000c3ff  jmp     loc_14000C30A
```

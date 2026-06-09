# CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(ulong const *,ulong)

- ea: `0x180027a90`
- end: `0x180027bf6`
- name: `?Enable@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAAJPEBKK@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18002acf8`

## callees

- `0x180002eb8`
- `0x180025ef0`
- `0x180026070`
- `0x180026d68`
- `0x180027008`
- `0x180027a90`
- `0x1800293a4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180027adc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180027b83`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180027be1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180027adc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180027b83`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180027be1`
- `ntdll!RtlAdjustPrivilege` at `0x180027b2e`
- `ntdll!RtlAdjustPrivilege` at `0x180027b2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAutoRevertApplyPrivilegesT<CEmptyType>::Enable(__int64 *a1, __int64 a2, int a3)
{
  __int64 v3; // rax
  void *v6; // rsi
  __int64 v7; // rbx
  __int64 i; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rbx
  ULONG v12; // ecx
  NTSTATUS v13; // eax
  __int64 v14; // rax
  _QWORD *v15; // rbx
  void *v16; // r15
  __int64 v17; // rdi
  __int64 j; // rbp
  unsigned int v19; // edi
  _QWORD *v20; // r14
  __int64 v21; // rsi
  __int64 k; // rbx
  int v24; // [rsp+70h] [rbp+18h] BYREF

  v24 = a3;
  v3 = *a1;
  v24 = 0;
  if ( v3 )
  {
    v6 = (void *)(v3 - 8);
    v7 = *(_QWORD *)(v3 - 8);
    for ( i = v3 + 8 * v7; v7; --v7 )
    {
      i -= 8;
      CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(i);
    }
    operator delete[](v6);
    *a1 = 0;
  }
  v9 = operator new[](0x10u);
  if ( v9
    && (v10 = v9 + 1, *v9 = 1, CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::CPrivilegeState(v9 + 1), v10) )
  {
    v11 = 0;
    do
    {
      v12 = *(_DWORD *)(a2 + 4 * v11);
      LODWORD(v10[v11]) = v12;
      v13 = RtlAdjustPrivilege(v12, 1u, 0, (PBOOLEAN)&v10[v11] + 5);
      if ( v13 >= 0 )
        BYTE4(v10[v11]) = 1;
      if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v13, &v24) )
      {
        v19 = v24;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
        v15 = v10;
        goto LABEL_19;
      }
      v11 = (unsigned int)(v11 + 1);
    }
    while ( !(_DWORD)v11 );
    v14 = *a1;
    v15 = 0;
    if ( *a1 )
    {
      v16 = (void *)(v14 - 8);
      v17 = *(_QWORD *)(v14 - 8);
      for ( j = v14 + 8 * v17; v17; --v17 )
      {
        j -= 8;
        CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(j);
      }
      operator delete[](v16);
    }
    v19 = v24;
    *a1 = (__int64)v10;
  }
  else
  {
    v19 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
    v15 = 0;
  }
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
  if ( v15 )
  {
    v20 = v15 - 1;
    v21 = *(v15 - 1);
    for ( k = (__int64)&v15[v21]; v21; --v21 )
    {
      k -= 8;
      CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(k);
    }
    operator delete[](v20);
  }
  return v19;
}

```

## disassembly

```asm
0x180027a90  mov     [rsp+arg_10], r8d
0x180027a95  push    rbx
0x180027a96  push    rbp
0x180027a97  push    rsi
0x180027a98  push    rdi
0x180027a99  push    r14
0x180027a9b  push    r15
0x180027a9d  sub     rsp, 28h
0x180027aa1  mov     rax, [rcx]
0x180027aa4  mov     r15, rdx
0x180027aa7  mov     [rsp+58h+arg_10], 0
0x180027aaf  mov     r14, rcx
0x180027ab2  test    rax, rax
0x180027ab5  jz      short loc_180027AE9
0x180027ab7  lea     rsi, [rax-8]
0x180027abb  mov     rbx, [rsi]
0x180027abe  lea     rdi, [rax+rbx*8]
0x180027ac2  test    rbx, rbx
0x180027ac5  jz      short loc_180027AD9
0x180027ac7  sub     rdi, 8
0x180027acb  mov     rcx, rdi
0x180027ace  call    ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x180027ad3  sub     rbx, 1
0x180027ad7  jnz     short loc_180027AC7
0x180027ad9  mov     rcx, rsi
0x180027adc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180027ae2  mov     qword ptr [r14], 0
0x180027ae9  mov     ecx, 10h; unsigned __int64
0x180027aee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027af3  test    rax, rax
0x180027af6  jz      loc_180027BA2
0x180027afc  lea     rsi, [rax+8]
0x180027b00  mov     qword ptr [rax], 1
0x180027b07  mov     rcx, rsi
0x180027b0a  call    ??0CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::CPrivilegeState(void)
0x180027b0f  test    rsi, rsi
0x180027b12  jz      loc_180027BA2
0x180027b18  xor     ebx, ebx
0x180027b1a  mov     ecx, [r15+rbx*4]; Privilege
0x180027b1e  lea     r9, [rsi+5]
0x180027b22  lea     r9, [r9+rbx*8]; OldValue
0x180027b26  mov     [rsi+rbx*8], ecx
0x180027b29  xor     r8d, r8d; ForThread
0x180027b2c  mov     dl, 1; NewValue
0x180027b2e  call    cs:__imp_RtlAdjustPrivilege
0x180027b34  test    eax, eax
0x180027b36  js      short loc_180027B3D
0x180027b38  mov     byte ptr [rsi+rbx*8+4], 1
0x180027b3d  lea     rdx, [rsp+58h+arg_10]
0x180027b42  mov     ecx, eax
0x180027b44  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180027b49  test    eax, eax
0x180027b4b  jz      short loc_180027B92
0x180027b4d  inc     ebx
0x180027b4f  cmp     ebx, 1
0x180027b52  jb      short loc_180027B1A
0x180027b54  mov     rax, [r14]
0x180027b57  xor     ebx, ebx
0x180027b59  test    rax, rax
0x180027b5c  jz      short loc_180027B89
0x180027b5e  lea     r15, [rax-8]
0x180027b62  mov     rdi, [r15]
0x180027b65  lea     rbp, [rax+rdi*8]
0x180027b69  test    rdi, rdi
0x180027b6c  jz      short loc_180027B80
0x180027b6e  sub     rbp, 8
0x180027b72  mov     rcx, rbp
0x180027b75  call    ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x180027b7a  sub     rdi, 1
0x180027b7e  jnz     short loc_180027B6E
0x180027b80  mov     rcx, r15
0x180027b83  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180027b89  mov     edi, [rsp+58h+arg_10]
0x180027b8d  mov     [r14], rsi
0x180027b90  jmp     short loc_180027BB0
0x180027b92  mov     edi, [rsp+58h+arg_10]
0x180027b96  mov     ecx, edi
0x180027b98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027b9d  mov     rbx, rsi
0x180027ba0  jmp     short loc_180027BB0
0x180027ba2  mov     edi, 8007000Eh
0x180027ba7  mov     ecx, edi
0x180027ba9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027bae  xor     ebx, ebx
0x180027bb0  mov     ecx, edi
0x180027bb2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027bb7  test    rbx, rbx
0x180027bba  jz      short loc_180027BE7
0x180027bbc  lea     r14, [rbx-8]
0x180027bc0  mov     rsi, [r14]
0x180027bc3  lea     rbx, [rbx+rsi*8]
0x180027bc7  test    rsi, rsi
0x180027bca  jz      short loc_180027BDE
0x180027bcc  sub     rbx, 8
0x180027bd0  mov     rcx, rbx
0x180027bd3  call    ??1CPrivilegeState@?$CAutoRevertApplyPrivilegesT@VCEmptyType@@@@QEAA@XZ; CAutoRevertApplyPrivilegesT<CEmptyType>::CPrivilegeState::~CPrivilegeState(void)
0x180027bd8  sub     rsi, 1
0x180027bdc  jnz     short loc_180027BCC
0x180027bde  mov     rcx, r14
0x180027be1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180027be7  mov     eax, edi
0x180027be9  add     rsp, 28h
0x180027bed  pop     r15
0x180027bef  pop     r14
0x180027bf1  pop     rdi
0x180027bf2  pop     rsi
0x180027bf3  pop     rbp
0x180027bf4  pop     rbx
0x180027bf5  retn
```

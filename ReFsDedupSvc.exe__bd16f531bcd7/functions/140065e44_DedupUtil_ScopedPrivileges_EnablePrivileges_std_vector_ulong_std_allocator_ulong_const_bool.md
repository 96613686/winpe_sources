# DedupUtil::ScopedPrivileges::EnablePrivileges(std::vector<ulong,std::allocator<ulong>> const &,bool)

- ea: `0x140065e44`
- end: `0x140065fcb`
- name: `?EnablePrivileges@ScopedPrivileges@DedupUtil@@QEAAKAEBV?$vector@KV?$allocator@K@std@@@std@@_N@Z`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400668bc`
- `0x1400793e8`
- `0x14007a6fc`

## callees

- `0x140004be0`
- `0x1400635dc`
- `0x1400649f8`
- `0x140064c40`
- `0x140064f14`
- `0x140065e44`
- `0x140067dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065f5a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140065f4a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140065f4a`

## string_xrefs

- `0x140065f6d`: `Failed to adjust token prvileges, error = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DedupUtil::ScopedPrivileges::EnablePrivileges(__int64 a1, int **a2, char a3)
{
  __int64 v6; // rsi
  DWORD v7; // r12d
  PTOKEN_PRIVILEGES v8; // r15
  struct _TOKEN_PRIVILEGES *PreviousState; // r14
  __int64 v10; // r8
  int *v11; // r10
  int *i; // rdx
  __int64 v13; // rcx
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // ebx
  void *v16; // rcx
  DWORD ReturnLength; // [rsp+80h] [rbp+40h] BYREF
  PTOKEN_PRIVILEGES v18; // [rsp+88h] [rbp+48h] BYREF
  DWORD LastError; // [rsp+90h] [rbp+50h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+98h] [rbp+58h] BYREF

  LOBYTE(LastError) = a3;
  v18 = (PTOKEN_PRIVILEGES)a1;
  if ( *a2 == a2[1] )
    return 0;
  if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    DedupUtil::ScopedPrivileges::RestorePrivileges((DedupUtil::ScopedPrivileges *)a1);
  DedupUtil::ScopedPrivileges::EnablePrivileges_::_2_::_lambda_1_::operator()(&v18);
  v6 = a2[1] - *a2;
  v7 = 12 * v6 + 4;
  utl::make_unique<unsigned char [0],0>(&NewState, v7);
  v8 = NewState;
  if ( NewState )
  {
    utl::make_unique<unsigned char [0],0>(&v18, v7);
    PreviousState = v18;
    if ( v18 )
    {
      v10 = 0;
      v11 = a2[1];
      for ( i = *a2; i != v11; ++i )
      {
        v13 = v10;
        v8->Privileges[v13].Luid = (LUID)*i;
        v8->Privileges[v13].Attributes = 2;
        v10 = (unsigned int)(v10 + 1);
      }
      v8->PrivilegeCount = v10;
      *(_DWORD *)(a1 + 16) = v6;
      ReturnLength = 0;
      if ( AdjustTokenPrivileges(*(HANDLE *)a1, 0, v8, v7, PreviousState, &ReturnLength) )
      {
        v16 = *(void **)(a1 + 8);
        if ( v16 )
          operator delete(v16, v14);
        *(_QWORD *)(a1 + 8) = PreviousState;
        v18 = 0;
        v15 = 0;
      }
      else
      {
        LastError = GetLastError();
        DedupUtil::Print<unsigned long &>(6, L"Failed to adjust token prvileges, error = 0x%x\n", &LastError);
        v15 = LastError;
      }
    }
    else
    {
      v15 = 8;
    }
    utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(&v18);
    utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(&NewState);
    return v15;
  }
  else
  {
    utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(&NewState);
    return 8;
  }
}

```

## disassembly

```asm
0x140065e44  mov     byte ptr [rsp-38h+arg_10], r8b
0x140065e49  push    rbp
0x140065e4a  push    rbx
0x140065e4b  push    rsi
0x140065e4c  push    rdi
0x140065e4d  push    r12
0x140065e4f  push    r14
0x140065e51  push    r15
0x140065e53  mov     rbp, rsp
0x140065e56  sub     rsp, 40h
0x140065e5a  mov     rdi, rdx
0x140065e5d  mov     rbx, rcx
0x140065e60  mov     [rbp+arg_8], rcx
0x140065e64  mov     rax, [rdx+8]
0x140065e68  cmp     [rdx], rax
0x140065e6b  jnz     short loc_140065E74
0x140065e6d  xor     eax, eax
0x140065e6f  jmp     loc_140065FBB
0x140065e74  mov     rax, [rcx]
0x140065e77  dec     rax
0x140065e7a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140065e7e  ja      short loc_140065E85
0x140065e80  call    ?RestorePrivileges@ScopedPrivileges@DedupUtil@@QEAAKXZ; DedupUtil::ScopedPrivileges::RestorePrivileges(void)
0x140065e85  lea     rcx, [rbp+arg_8]
0x140065e89  call    _DedupUtil__ScopedPrivileges__EnablePrivileges____2____lambda_1___operator__
0x140065e8e  mov     rsi, [rdi+8]
0x140065e92  sub     rsi, [rdi]
0x140065e95  sar     rsi, 2
0x140065e99  lea     eax, [rsi+rsi*2]
0x140065e9c  lea     r12d, ds:4[rax*4]
0x140065ea4  mov     r14d, r12d
0x140065ea7  mov     edx, r12d
0x140065eaa  lea     rcx, [rbp+NewState]
0x140065eae  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x140065eb3  nop
0x140065eb4  mov     r15, [rbp+NewState]
0x140065eb8  test    r15, r15
0x140065ebb  jnz     short loc_140065ECF
0x140065ebd  lea     rcx, [rbp+NewState]
0x140065ec1  call    ??1?$unique_ptr@$$BY0A@_KU?$default_delete@$$BY0A@_K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(void)
0x140065ec6  lea     eax, [r15+8]
0x140065eca  jmp     loc_140065FBB
0x140065ecf  mov     rdx, r14
0x140065ed2  lea     rcx, [rbp+arg_8]
0x140065ed6  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x140065edb  nop
0x140065edc  mov     r14, [rbp+arg_8]
0x140065ee0  test    r14, r14
0x140065ee3  jz      loc_140065FA1
0x140065ee9  xor     r8d, r8d
0x140065eec  mov     r10, [rdi+8]
0x140065ef0  mov     rdx, [rdi]
0x140065ef3  jmp     short loc_140065F1F
0x140065ef5  movsxd  rax, dword ptr [rdx]
0x140065ef8  mov     dword ptr [rbp+var_10], eax
0x140065efb  shr     rax, 20h
0x140065eff  mov     dword ptr [rbp+var_10+4], eax
0x140065f02  lea     rcx, [r8+r8*2]
0x140065f06  mov     rax, [rbp+var_10]
0x140065f0a  mov     [r15+rcx*4+4], rax
0x140065f0f  mov     dword ptr [r15+rcx*4+0Ch], 2
0x140065f18  inc     r8d
0x140065f1b  add     rdx, 4
0x140065f1f  cmp     rdx, r10
0x140065f22  jnz     short loc_140065EF5
0x140065f24  mov     [r15], r8d
0x140065f27  mov     [rbx+10h], esi
0x140065f2a  mov     [rbp+arg_0], 0
0x140065f31  lea     rax, [rbp+arg_0]
0x140065f35  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140065f3a  mov     [rsp+40h+PreviousState], r14; PreviousState
0x140065f3f  mov     r9d, r12d; BufferLength
0x140065f42  mov     r8, r15; NewState
0x140065f45  xor     edx, edx; DisableAllPrivileges
0x140065f47  mov     rcx, [rbx]; TokenHandle
0x140065f4a  call    cs:__imp_AdjustTokenPrivileges
0x140065f51  nop     dword ptr [rax+rax+00h]
0x140065f56  test    eax, eax
0x140065f58  jnz     short loc_140065F83
0x140065f5a  call    cs:__imp_GetLastError
0x140065f61  nop     dword ptr [rax+rax+00h]
0x140065f66  mov     [rbp+arg_10], eax
0x140065f69  lea     r8, [rbp+arg_10]
0x140065f6d  lea     rdx, aFailedToAdjust; "Failed to adjust token prvileges, error"...
0x140065f74  mov     ecx, 6
0x140065f79  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x140065f7e  mov     ebx, [rbp+arg_10]
0x140065f81  jmp     short loc_140065FA6
0x140065f83  mov     rcx, [rbx+8]; void *
0x140065f87  test    rcx, rcx
0x140065f8a  jz      short loc_140065F91
0x140065f8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140065f91  mov     [rbx+8], r14
0x140065f95  mov     [rbp+arg_8], 0
0x140065f9d  xor     ebx, ebx
0x140065f9f  jmp     short loc_140065FA6
0x140065fa1  mov     ebx, 8
0x140065fa6  lea     rcx, [rbp+arg_8]
0x140065faa  call    ??1?$unique_ptr@$$BY0A@_KU?$default_delete@$$BY0A@_K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(void)
0x140065faf  nop
0x140065fb0  lea     rcx, [rbp+NewState]
0x140065fb4  call    ??1?$unique_ptr@$$BY0A@_KU?$default_delete@$$BY0A@_K@utl@@@utl@@QEAA@XZ; utl::unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>::~unique_ptr<unsigned __int64 [0],utl::default_delete<unsigned __int64 [0]>>(void)
0x140065fb9  mov     eax, ebx
0x140065fbb  add     rsp, 40h
0x140065fbf  pop     r15
0x140065fc1  pop     r14
0x140065fc3  pop     r12
0x140065fc5  pop     rdi
0x140065fc6  pop     rsi
0x140065fc7  pop     rbx
0x140065fc8  pop     rbp
0x140065fc9  retn
```

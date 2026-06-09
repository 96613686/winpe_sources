# CPowerSupport::RemoveReader(ulong)

- ea: `0x18002f334`
- end: `0x18002f4ad`
- name: `?RemoveReader@CPowerSupport@@SAXK@Z`
- size: `377`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002cb40`

## callees

- `0x1800156d4`
- `0x18001974c`
- `0x18002965c`
- `0x18002eb3c`
- `0x18002ebac`
- `0x18002f334`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f3ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002f3ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f458`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f458`

## string_xrefs

- `0x18002f35c`: `CPowerSupport::RemoveReader`

## pseudocode

```c
void __fastcall CPowerSupport::RemoveReader(unsigned int a1)
{
  RTL_SRWLOCK *v1; // rbx
  struct CPowerSupport *v2; // rax
  struct CPowerSupport *v3; // rax
  HANDLE *v4; // rcx
  struct CPowerSupport *v5; // rax
  struct CPowerSupport *v6; // rax
  struct CPowerSupport *v7; // rax
  HANDLE *v8; // rcx
  struct CPowerSupport *v9; // rax
  unsigned int v10; // [rsp+20h] [rbp-60h] BYREF
  int v11; // [rsp+28h] [rbp-58h] BYREF
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-40h] BYREF
  char v15[32]; // [rsp+58h] [rbp-28h] BYREF

  v10 = a1;
  v11 = 0;
  strcpy(v15, "CPowerSupport::RemoveReader");
  v14[0] = v15;
  v14[1] = &v11;
  v14[2] = &v10;
  lambda_18a73fd5e658b1cd187a748ef06eb827_::operator()(v14);
  v11 = 1;
  v13 = v14;
  v1 = (RTL_SRWLOCK *)((char *)CPowerSupport::Instance() + 16);
  AcquireSRWLockExclusive(v1);
  v12 = v1;
  if ( v10 != -1 )
  {
    v2 = CPowerSupport::Instance();
    if ( *((_DWORD *)v2 + 9) > v10 && *(_QWORD *)(*((_QWORD *)v2 + 5) + 8LL * (int)v10) )
    {
      v3 = CPowerSupport::Instance();
      if ( *((_DWORD *)v3 + 9) > v10 )
      {
        _mm_lfence();
        v4 = *(HANDLE **)(*((_QWORD *)v3 + 5) + 8LL * (int)v10);
      }
      else
      {
        v4 = 0;
      }
      if ( !CloseHandle(*v4) )
        GetLastError();
      v5 = CPowerSupport::Instance();
      CDynamicArray<void *>::Set((char *)v5 + 24, v10, 0);
    }
    v6 = CPowerSupport::Instance();
    if ( *((_DWORD *)v6 + 15) > v10 && *(_QWORD *)(*((_QWORD *)v6 + 8) + 8LL * (int)v10) )
    {
      v7 = CPowerSupport::Instance();
      if ( *((_DWORD *)v7 + 15) > v10 )
      {
        _mm_lfence();
        v8 = *(HANDLE **)(*((_QWORD *)v7 + 8) + 8LL * (int)v10);
      }
      else
      {
        v8 = 0;
      }
      if ( !CloseHandle(*v8) )
        GetLastError();
      v9 = CPowerSupport::Instance();
      CDynamicArray<void *>::Set((char *)v9 + 48, v10, 0);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  WppTraceUnwinder__lambda_18a73fd5e658b1cd187a748ef06eb827____::_WppTraceUnwinder__lambda_18a73fd5e658b1cd187a748ef06eb827____(&v13);
}

```

## disassembly

```asm
0x18002f334  mov     [rsp-8+arg_8], rbx
0x18002f339  push    rbp
0x18002f33a  mov     rbp, rsp
0x18002f33d  sub     rsp, 80h
0x18002f344  mov     rax, cs:__security_cookie
0x18002f34b  xor     rax, rsp
0x18002f34e  mov     [rbp+var_8], rax
0x18002f352  mov     [rbp+var_60], ecx
0x18002f355  mov     [rbp+var_58], 0
0x18002f35c  movups  xmm0, xmmword ptr cs:aCpowersupportR; "CPowerSupport::RemoveReader"
0x18002f363  movups  xmmword ptr [rbp+var_28], xmm0
0x18002f367  movups  xmm1, xmmword ptr cs:aCpowersupportR+0Ch; "t::RemoveReader"
0x18002f36e  movups  xmmword ptr [rbp+var_28+0Ch], xmm1
0x18002f372  lea     rax, [rbp+var_28]
0x18002f376  mov     [rbp+var_40], rax
0x18002f37a  lea     rax, [rbp+var_58]
0x18002f37e  mov     [rbp+var_38], rax
0x18002f382  lea     rax, [rbp+var_60]
0x18002f386  mov     [rbp+var_30], rax
0x18002f38a  lea     rcx, [rbp+var_40]
0x18002f38e  call    _lambda_18a73fd5e658b1cd187a748ef06eb827___operator__
0x18002f393  mov     [rbp+var_58], 1
0x18002f39a  lea     rax, [rbp+var_40]
0x18002f39e  mov     [rbp+var_48], rax
0x18002f3a2  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f3a7  lea     rbx, [rax+10h]
0x18002f3ab  mov     rcx, rbx; SRWLock
0x18002f3ae  call    cs:__imp_AcquireSRWLockExclusive
0x18002f3b4  mov     [rbp+var_50], rbx
0x18002f3b8  cmp     [rbp+var_60], 0FFFFFFFFh
0x18002f3bc  jz      loc_18002F47D
0x18002f3c2  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f3c7  movsxd  rcx, [rbp+var_60]
0x18002f3cb  cmp     [rax+24h], ecx
0x18002f3ce  jbe     short loc_18002F41F
0x18002f3d0  mov     rax, [rax+28h]
0x18002f3d4  cmp     qword ptr [rax+rcx*8], 0
0x18002f3d9  jz      short loc_18002F41F
0x18002f3db  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f3e0  movsxd  rcx, [rbp+var_60]
0x18002f3e4  cmp     [rax+24h], ecx
0x18002f3e7  ja      short loc_18002F3ED
0x18002f3e9  xor     ecx, ecx
0x18002f3eb  jmp     short loc_18002F3F8
0x18002f3ed  lfence
0x18002f3f0  mov     rax, [rax+28h]
0x18002f3f4  mov     rcx, [rax+rcx*8]
0x18002f3f8  mov     rcx, [rcx]; hObject
0x18002f3fb  call    cs:__imp_CloseHandle
0x18002f401  test    eax, eax
0x18002f403  jnz     short loc_18002F40B
0x18002f405  call    cs:__imp_GetLastError
0x18002f40b  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f410  lea     rcx, [rax+18h]
0x18002f414  xor     r8d, r8d
0x18002f417  mov     edx, [rbp+var_60]
0x18002f41a  call    ?Set@?$CDynamicArray@PEAX@@QEAAPEAPEAXHPEAPEAX@Z; CDynamicArray<void *>::Set(int,void * *)
0x18002f41f  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f424  movsxd  rcx, [rbp+var_60]
0x18002f428  cmp     [rax+3Ch], ecx
0x18002f42b  jbe     short loc_18002F47D
0x18002f42d  mov     rax, [rax+40h]
0x18002f431  cmp     qword ptr [rax+rcx*8], 0
0x18002f436  jz      short loc_18002F47D
0x18002f438  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f43d  movsxd  rcx, [rbp+var_60]
0x18002f441  cmp     [rax+3Ch], ecx
0x18002f444  ja      short loc_18002F44A
0x18002f446  xor     ecx, ecx
0x18002f448  jmp     short loc_18002F455
0x18002f44a  lfence
0x18002f44d  mov     rax, [rax+40h]
0x18002f451  mov     rcx, [rax+rcx*8]
0x18002f455  mov     rcx, [rcx]; hObject
0x18002f458  call    cs:__imp_CloseHandle
0x18002f45e  test    eax, eax
0x18002f460  jnz     short loc_18002F468
0x18002f462  call    cs:__imp_GetLastError
0x18002f468  call    ?Instance@CPowerSupport@@SAAEAV1@XZ; CPowerSupport::Instance(void)
0x18002f46d  lea     rcx, [rax+30h]
0x18002f471  xor     r8d, r8d
0x18002f474  mov     edx, [rbp+var_60]
0x18002f477  call    ?Set@?$CDynamicArray@PEAX@@QEAAPEAPEAXHPEAPEAX@Z; CDynamicArray<void *>::Set(int,void * *)
0x18002f47c  nop
0x18002f47d  lea     rcx, [rbp+var_50]
0x18002f481  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002f486  nop
0x18002f487  lea     rcx, [rbp+var_48]
0x18002f48b  call    WppTraceUnwinder__lambda_18a73fd5e658b1cd187a748ef06eb827_______WppTraceUnwinder__lambda_18a73fd5e658b1cd187a748ef06eb827____
0x18002f490  mov     rcx, [rbp+var_8]
0x18002f494  xor     rcx, rsp; StackCookie
0x18002f497  call    __security_check_cookie
0x18002f49c  mov     rbx, [rsp+80h+arg_8]
0x18002f4a4  add     rsp, 80h
0x18002f4ab  pop     rbp
0x18002f4ac  retn
```

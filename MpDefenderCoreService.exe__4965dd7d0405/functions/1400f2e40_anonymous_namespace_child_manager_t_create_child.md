# _anonymous_namespace_::child_manager_t::create_child

- ea: `0x1400f2e40`
- end: `0x1400f312a`
- name: `_anonymous_namespace_::child_manager_t::create_child`
- size: `746`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a130`
- `0x14003a5c0`
- `0x14003a66c`
- `0x140084970`
- `0x140084a8c`
- `0x1400f2900`
- `0x1400f2ac8`
- `0x1400f2e40`
- `0x1400f312c`
- `0x140166990`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1400f305a`
- `KERNEL32!SetThreadpoolWait` at `0x1400f305a`
- `KERNEL32!CreateThreadpoolWait` at `0x1400f2f7b`
- `KERNEL32!CreateThreadpoolWait` at `0x1400f2f7b`
- `KERNEL32!CreateJobObjectW` at `0x1400f2ecb`
- `KERNEL32!CreateJobObjectW` at `0x1400f2ecb`
- `KERNEL32!SetInformationJobObject` at `0x1400f2f10`
- `KERNEL32!SetInformationJobObject` at `0x1400f2f10`
- `KERNEL32!CloseHandle` at `0x1400f2fa4`
- `KERNEL32!CloseHandle` at `0x1400f2fb2`
- `KERNEL32!CloseHandle` at `0x1400f3011`
- `KERNEL32!CloseHandle` at `0x1400f2fa4`
- `KERNEL32!CloseHandle` at `0x1400f2fb2`
- `KERNEL32!CloseHandle` at `0x1400f3011`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::child_manager_t::create_child(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 *v3; // r15
  __int64 v4; // r12
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  HANDLE JobObjectW; // rsi
  _QWORD *v10; // rdi
  unsigned int v11; // r14d
  HANDLE v12; // rax
  _DWORD *v14; // rdi
  unsigned int v15; // r14d
  void *v16; // rdi
  __int64 result; // rax
  void *v18; // [rsp+20h] [rbp-148h] BYREF
  _Mtx_t v19; // [rsp+28h] [rbp-140h]
  __int64 v20[3]; // [rsp+30h] [rbp-138h] BYREF
  _OWORD v21[2]; // [rsp+48h] [rbp-120h] BYREF
  __int64 *v22; // [rsp+68h] [rbp-100h]
  __int64 v23; // [rsp+70h] [rbp-F8h]
  HANDLE hObject; // [rsp+78h] [rbp-F0h] BYREF
  PVOID pv; // [rsp+80h] [rbp-E8h]
  char v26; // [rsp+88h] [rbp-E0h]
  _DWORD JobObjectInformation[36]; // [rsp+90h] [rbp-D8h] BYREF

  v3 = a3;
  v4 = a2;
  v23 = a2;
  v22 = a3;
  v6 = a3[2];
  a3[2] = 0;
  v7 = a3[1];
  a3[1] = 0;
  v8 = *a3;
  *a3 = 0;
  v20[0] = v8;
  v20[1] = v7;
  v20[2] = v6;
  v21[0] = *(_OWORD *)v4;
  v21[1] = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 7;
  *(_WORD *)v4 = 0;
  JobObjectW = CreateJobObjectW(0, 0);
  if ( !JobObjectW )
    goto LABEL_12;
  memset(JobObjectInformation, 0, sizeof(JobObjectInformation));
  JobObjectInformation[4] = 0x2000;
  if ( !SetInformationJobObject(JobObjectW, JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u)
    || (anonymous_namespace_::create_process_in_job((__int64)&hObject, JobObjectW, (__int64 *)v21, v20), !v26) )
  {
LABEL_11:
    CloseHandle(JobObjectW);
LABEL_12:
    v10 = 0;
    v18 = 0;
    goto LABEL_13;
  }
  v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
  {
LABEL_7:
    if ( v26 && hObject )
      CloseHandle(hObject);
    if ( !JobObjectW )
      goto LABEL_12;
    goto LABEL_11;
  }
  v11 = (unsigned int)pv;
  v12 = hObject;
  hObject = 0;
  *v10 = JobObjectW;
  v10[1] = v12;
  v10[2] = CreateThreadpoolWait(
             lambda_38c0e11cee8123e6998a03cb73eaee05_::_lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___unsigned_long_,
             (PVOID)v11,
             0);
  *((_DWORD *)v10 + 6) = v11;
  if ( !v10[2] )
  {
    JobObjectW = 0;
    goto LABEL_7;
  }
  v18 = v10;
  if ( v26 && hObject )
    CloseHandle(hObject);
LABEL_13:
  std::wstring::_Tidy_deallocate(v21);
  std::vector<std::wstring>::_Tidy(v20);
  if ( !v10 )
    goto LABEL_26;
  v19 = (_Mtx_t)(a1 + 8);
  if ( Mtx_lock((_Mtx_t)(a1 + 8)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 84) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 84) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  try
  {
    std::_Tree_std::_Tmap_traits_unsigned_long_std::unique_ptr__anonymous_namespace_::child_state_t_std::default_delete__anonymous_namespace_::child_state_t____std::less_unsigned_long__std::allocator_std::pair_unsigned_long_const__std::unique_ptr__anonymous_namespace_::child_state_t_std::default_delete__anonymous_namespace_::child_state_t________0___::emplace_unsigned_long_const___std::unique_ptr__anonymous_namespace_::child_state_t_std::default_delete__anonymous_namespace_::child_state_t_____(
      a1 + 88,
      &hObject,
      v10 + 3,
      &v18);
    v14 = hObject;
    if ( (_BYTE)pv )
      SetThreadpoolWait(*(PTP_WAIT *)(*((_QWORD *)hObject + 5) + 16LL), *(HANDLE *)(*((_QWORD *)hObject + 5) + 8LL), 0);
    v15 = v14[8];
    Mtx_unlock((_Mtx_t)(a1 + 8));
    v16 = v18;
    if ( v18 )
    {
      anonymous_namespace_::child_state_t::_child_state_t(v18);
      operator delete(v16, (const struct std::nothrow_t *)0x20);
    }
    std::wstring::_Tidy_deallocate(v4);
    std::vector<std::wstring>::_Tidy(v3);
    result = v15;
  }
  catch ( ... )
  {
    Mtx_unlock(v19);
    v10 = v18;
    v3 = v22;
    v4 = v23;
LABEL_26:
    if ( v10 )
    {
      anonymous_namespace_::child_state_t::_child_state_t(v10);
      operator delete(v10, (const struct std::nothrow_t *)0x20);
    }
    std::wstring::_Tidy_deallocate(v4);
    std::vector<std::wstring>::_Tidy(v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400f2e40  push    rbx
0x1400f2e42  push    rsi
0x1400f2e43  push    rdi
0x1400f2e44  push    r12
0x1400f2e46  push    r13
0x1400f2e48  push    r14
0x1400f2e4a  push    r15
0x1400f2e4c  sub     rsp, 130h
0x1400f2e53  mov     rax, cs:__security_cookie
0x1400f2e5a  xor     rax, rsp
0x1400f2e5d  mov     [rsp+168h+var_48], rax
0x1400f2e65  mov     r15, r8
0x1400f2e68  mov     r12, rdx
0x1400f2e6b  mov     r13, rcx
0x1400f2e6e  mov     [rsp+168h+var_F8], rdx
0x1400f2e73  mov     [rsp+168h+var_100], r8
0x1400f2e78  mov     rdx, [r8+10h]
0x1400f2e7c  xor     ebx, ebx
0x1400f2e7e  mov     [r8+10h], rbx
0x1400f2e82  mov     rcx, [r8+8]
0x1400f2e86  mov     [r8+8], rbx
0x1400f2e8a  mov     rax, [r8]
0x1400f2e8d  mov     [r8], rbx
0x1400f2e90  mov     [rsp+168h+var_138], rax
0x1400f2e95  mov     [rsp+168h+var_130], rcx
0x1400f2e9a  mov     [rsp+168h+var_128], rdx
0x1400f2e9f  movups  xmm0, xmmword ptr [r12]
0x1400f2ea4  movups  [rsp+168h+var_120], xmm0
0x1400f2ea9  movups  xmm1, xmmword ptr [r12+10h]
0x1400f2eaf  movups  [rsp+168h+var_110], xmm1
0x1400f2eb4  mov     [r12+10h], rbx
0x1400f2eb9  mov     qword ptr [r12+18h], 7
0x1400f2ec2  mov     [r12], bx
0x1400f2ec7  xor     edx, edx; lpName
0x1400f2ec9  xor     ecx, ecx; lpJobAttributes
0x1400f2ecb  call    cs:__imp_CreateJobObjectW
0x1400f2ed1  mov     rsi, rax
0x1400f2ed4  test    rax, rax
0x1400f2ed7  jz      loc_1400F2FB8
0x1400f2edd  mov     edi, 90h
0x1400f2ee2  mov     r8d, edi; Size
0x1400f2ee5  xor     edx, edx; Val
0x1400f2ee7  lea     rcx, [rsp+168h+JobObjectInformation]; void *
0x1400f2eef  call    memset
0x1400f2ef4  mov     [rsp+168h+var_C8], 2000h
0x1400f2eff  mov     r9d, edi; cbJobObjectInformationLength
0x1400f2f02  lea     r8, [rsp+168h+JobObjectInformation]; lpJobObjectInformation
0x1400f2f0a  lea     edx, [rbx+9]; JobObjectInformationClass
0x1400f2f0d  mov     rcx, rsi; hJob
0x1400f2f10  call    cs:__imp_SetInformationJobObject
0x1400f2f16  test    eax, eax
0x1400f2f18  jz      loc_1400F2FAF
0x1400f2f1e  lea     r9, [rsp+168h+var_138]
0x1400f2f23  lea     r8, [rsp+168h+var_120]
0x1400f2f28  mov     rdx, rsi
0x1400f2f2b  lea     rcx, [rsp+168h+hObject]
0x1400f2f30  call    _anonymous_namespace___create_process_in_job
0x1400f2f35  cmp     [rsp+168h+var_E0], bl
0x1400f2f3c  jz      short loc_1400F2FAF
0x1400f2f3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400f2f45  lea     ecx, [rbx+20h]; unsigned __int64
0x1400f2f48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400f2f4d  mov     rdi, rax
0x1400f2f50  test    rax, rax
0x1400f2f53  jz      short loc_1400F2F91
0x1400f2f55  mov     r14d, dword ptr [rsp+168h+pv]
0x1400f2f5d  mov     rax, [rsp+168h+hObject]
0x1400f2f62  mov     [rsp+168h+hObject], rbx
0x1400f2f67  mov     [rdi], rsi
0x1400f2f6a  mov     [rdi+8], rax
0x1400f2f6e  mov     edx, r14d; pv
0x1400f2f71  xor     r8d, r8d; pcbe
0x1400f2f74  lea     rcx, _lambda_38c0e11cee8123e6998a03cb73eaee05____lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___unsigned_long_; pfnwa
0x1400f2f7b  call    cs:__imp_CreateThreadpoolWait
0x1400f2f81  mov     [rdi+10h], rax
0x1400f2f85  mov     [rdi+18h], r14d
0x1400f2f89  cmp     [rdi+10h], rbx
0x1400f2f8d  jnz     short loc_1400F2FF9
0x1400f2f8f  mov     esi, ebx
0x1400f2f91  cmp     [rsp+168h+var_E0], bl
0x1400f2f98  jz      short loc_1400F2FAA
0x1400f2f9a  mov     rcx, [rsp+168h+hObject]; hObject
0x1400f2f9f  test    rcx, rcx
0x1400f2fa2  jz      short loc_1400F2FAA
0x1400f2fa4  call    cs:__imp_CloseHandle
0x1400f2faa  test    rsi, rsi
0x1400f2fad  jz      short loc_1400F2FB8
0x1400f2faf  mov     rcx, rsi; hObject
0x1400f2fb2  call    cs:__imp_CloseHandle
0x1400f2fb8  mov     rdi, rbx
0x1400f2fbb  mov     [rsp+168h+var_148], rbx
0x1400f2fc0  lea     rcx, [rsp+168h+var_120]
0x1400f2fc5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400f2fca  lea     rcx, [rsp+168h+var_138]
0x1400f2fcf  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400f2fd4  nop
0x1400f2fd5  test    rdi, rdi
0x1400f2fd8  jz      loc_1400F30BC
0x1400f2fde  lea     rsi, [r13+8]
0x1400f2fe2  mov     [rsp+168h+var_140], rsi
0x1400f2fe7  mov     rcx, rsi; _Mtx_t
0x1400f2fea  call    _Mtx_lock
0x1400f2fef  test    eax, eax
0x1400f2ff1  jnz     loc_1400F310D
0x1400f2ff7  jmp     short loc_1400F3019
0x1400f2ff9  mov     [rsp+168h+var_148], rdi
0x1400f2ffe  cmp     [rsp+168h+var_E0], bl
0x1400f3005  jz      short loc_1400F2FC0
0x1400f3007  mov     rcx, [rsp+168h+hObject]; hObject
0x1400f300c  test    rcx, rcx
0x1400f300f  jz      short loc_1400F2FC0
0x1400f3011  call    cs:__imp_CloseHandle
0x1400f3017  jmp     short loc_1400F2FC0
0x1400f3019  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x1400f3020  jz      loc_1400F3118
0x1400f3026  lea     r8, [rdi+18h]
0x1400f302a  lea     rcx, [r13+58h]
0x1400f302e  lea     r9, [rsp+168h+var_148]
0x1400f3033  lea     rdx, [rsp+168h+hObject]
0x1400f3038  call    std___Tree_std___Tmap_traits_unsigned_long_std__unique_ptr__anonymous_namespace___child_state_t_std__default_delete__anonymous_namespace___child_state_t____std__less_unsigned_long__std__allocator_std__pair_unsigned_long_const__std__unique_ptr__anonymous_namespace___child_state_t_std__default_delete__anonymous_namespace___child_state_t________0_____emplace_unsigned_long_const___std__unique_ptr__anonymous_namespace___child_state_t_std__default_delete__anonymous_namespace___child_state_t_____
0x1400f303d  mov     rdi, [rsp+168h+hObject]
0x1400f3042  cmp     byte ptr [rsp+168h+pv], bl
0x1400f3049  jz      short loc_1400F3060
0x1400f304b  mov     rcx, [rdi+28h]
0x1400f304f  xor     r8d, r8d; pftTimeout
0x1400f3052  mov     rdx, [rcx+8]; h
0x1400f3056  mov     rcx, [rcx+10h]; pwa
0x1400f305a  call    cs:__imp_SetThreadpoolWait
0x1400f3060  mov     r14d, [rdi+20h]
0x1400f3064  mov     rcx, rsi; _Mtx_t
0x1400f3067  call    _Mtx_unlock
0x1400f306c  nop
0x1400f306d  mov     rdi, [rsp+168h+var_148]
0x1400f3072  test    rdi, rdi
0x1400f3075  jz      short loc_1400F308D
0x1400f3077  mov     rcx, rdi
0x1400f307a  call    _anonymous_namespace___child_state_t___child_state_t
0x1400f307f  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1400f3084  mov     rcx, rdi; void *
0x1400f3087  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f308c  nop
0x1400f308d  mov     rcx, r12
0x1400f3090  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400f3095  nop
0x1400f3096  mov     rcx, r15
0x1400f3099  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400f309e  mov     eax, r14d
0x1400f30a1  jmp     short loc_1400F30EA
0x1400f30a3  mov     rcx, [rsp+168h+var_140]; _Mtx_t
0x1400f30a8  call    _Mtx_unlock
0x1400f30ad  mov     rdi, [rsp+168h+var_148]
0x1400f30b2  mov     r15, [rsp+168h+var_100]
0x1400f30b7  mov     r12, [rsp+168h+var_F8]
0x1400f30bc  test    rdi, rdi
0x1400f30bf  jz      short loc_1400F30D7
0x1400f30c1  mov     rcx, rdi
0x1400f30c4  call    _anonymous_namespace___child_state_t___child_state_t
0x1400f30c9  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1400f30ce  mov     rcx, rdi; void *
0x1400f30d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400f30d6  nop
0x1400f30d7  mov     rcx, r12
0x1400f30da  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400f30df  nop
0x1400f30e0  mov     rcx, r15
0x1400f30e3  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400f30e8  xor     eax, eax
0x1400f30ea  mov     rcx, [rsp+168h+var_48]
0x1400f30f2  xor     rcx, rsp; StackCookie
0x1400f30f5  call    __security_check_cookie
0x1400f30fa  add     rsp, 130h
0x1400f3101  pop     r15
0x1400f3103  pop     r14
0x1400f3105  pop     r13
0x1400f3107  pop     r12
0x1400f3109  pop     rdi
0x1400f310a  pop     rsi
0x1400f310b  pop     rbx
0x1400f310c  retn
0x1400f310d  mov     ecx, 5; int
0x1400f3112  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1400f3118  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x1400f311f  mov     ecx, 6; int
0x1400f3124  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

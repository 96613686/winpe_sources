# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x1800d9d4c`
- end: `0x1800d9e30`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d86c4`
- `0x1800dbee8`

## callees

- `0x180005860`
- `0x180009a64`
- `0x18000acc4`
- `0x1800742c0`
- `0x1800ccf38`
- `0x1800d9d4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9e1d`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,0>::is_running(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  bool v6; // bl
  __int64 v8; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-18h]

  wil::EnterCriticalSection(&v8, a1 + 192);
  v2 = *(_QWORD *)(a1 + 240);
  if ( !v2 || (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    goto LABEL_6;
  if ( *(_DWORD *)(a1 + 232) )
  {
LABEL_12:
    v6 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
    goto LABEL_7;
  }
  v3 = *(unsigned int *)(a1 + 184);
  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  v4 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *, __int64))TestQueryData)(v2, 0, v3, &v9, v8);
  v5 = pv[1];
  if ( v4 )
  {
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
    goto LABEL_12;
  }
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
LABEL_6:
  v6 = 0;
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
  return v6;
}

```

## disassembly

```asm
0x1800d9d4c  mov     [rsp-8+arg_8], rbx
0x1800d9d51  push    rbp
0x1800d9d52  mov     rbp, rsp
0x1800d9d55  sub     rsp, 60h
0x1800d9d59  mov     rax, cs:__security_cookie
0x1800d9d60  xor     rax, rsp
0x1800d9d63  mov     [rbp+var_8], rax
0x1800d9d67  mov     rbx, rcx
0x1800d9d6a  lea     rdx, [rcx+0C0h]
0x1800d9d71  lea     rcx, [rbp+var_40]
0x1800d9d75  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800d9d7a  mov     rcx, [rbx+0F0h]
0x1800d9d81  test    rcx, rcx
0x1800d9d84  jz      short loc_1800D9DD3
0x1800d9d86  test    dword ptr [rbx+40h], 100h
0x1800d9d8d  jnz     short loc_1800D9DD3
0x1800d9d8f  cmp     dword ptr [rbx+0E8h], 0
0x1800d9d96  jnz     loc_1800D9E23
0x1800d9d9c  mov     r8d, [rbx+0B8h]
0x1800d9da3  lea     r9, [rbp+var_38]
0x1800d9da7  xorps   xmm0, xmm0
0x1800d9daa  xor     edx, edx
0x1800d9dac  movups  [rbp+var_38], xmm0
0x1800d9db0  movups  xmmword ptr [rbp+pv], xmm0
0x1800d9db4  movups  [rbp+var_18], xmm0
0x1800d9db8  call    TestQueryData
0x1800d9dbd  mov     rcx, [rbp+pv+8]; pv
0x1800d9dc1  test    eax, eax
0x1800d9dc3  jnz     short loc_1800D9DF7
0x1800d9dc5  call    cs:__imp_CoTaskMemFree
0x1800d9dcb  mov     [rbp+pv+8], 0
0x1800d9dd3  xor     bl, bl
0x1800d9dd5  lea     rcx, [rbp+var_40]
0x1800d9dd9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800d9dde  mov     al, bl
0x1800d9de0  mov     rcx, [rbp+var_8]
0x1800d9de4  xor     rcx, rsp; StackCookie
0x1800d9de7  call    __security_check_cookie
0x1800d9dec  mov     rbx, [rsp+60h+arg_8]
0x1800d9df1  add     rsp, 60h
0x1800d9df5  pop     rbp
0x1800d9df6  retn
0x1800d9df7  mov     eax, dword ptr [rbp+pv+4]
0x1800d9dfa  or      [rbx+40h], eax
0x1800d9dfd  test    rcx, rcx
0x1800d9e00  jz      short loc_1800D9E14
0x1800d9e02  lea     rdx, [rbp+var_38]
0x1800d9e06  mov     rcx, rbx
0x1800d9e09  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1800d9e0e  mov     rcx, [rbp+pv+8]
0x1800d9e12  jmp     short loc_1800D9E1D
0x1800d9e14  mov     eax, dword ptr [rbp+pv]
0x1800d9e17  mov     [rbx+0B8h], eax
0x1800d9e1d  call    cs:__imp_CoTaskMemFree
0x1800d9e23  mov     ebx, [rbx+40h]
0x1800d9e26  shr     ebx, 8
0x1800d9e29  not     bl
0x1800d9e2b  and     bl, 1
0x1800d9e2e  jmp     short loc_1800D9DD5
```

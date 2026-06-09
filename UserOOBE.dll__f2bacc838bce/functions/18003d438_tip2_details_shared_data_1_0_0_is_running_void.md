# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x18003d438`
- end: `0x18003d51c`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037be4`

## callees

- `0x1800032b0`
- `0x18000a644`
- `0x18000b97c`
- `0x18003c738`
- `0x18003d438`
- `0x18003fab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d509`

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
0x18003d438  mov     [rsp-8+arg_8], rbx
0x18003d43d  push    rbp
0x18003d43e  mov     rbp, rsp
0x18003d441  sub     rsp, 60h
0x18003d445  mov     rax, cs:__security_cookie
0x18003d44c  xor     rax, rsp
0x18003d44f  mov     [rbp+var_8], rax
0x18003d453  mov     rbx, rcx
0x18003d456  lea     rdx, [rcx+0C0h]
0x18003d45d  lea     rcx, [rbp+var_40]
0x18003d461  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18003d466  mov     rcx, [rbx+0F0h]
0x18003d46d  test    rcx, rcx
0x18003d470  jz      short loc_18003D4BF
0x18003d472  test    dword ptr [rbx+40h], 100h
0x18003d479  jnz     short loc_18003D4BF
0x18003d47b  cmp     dword ptr [rbx+0E8h], 0
0x18003d482  jnz     loc_18003D50F
0x18003d488  mov     r8d, [rbx+0B8h]
0x18003d48f  lea     r9, [rbp+var_38]
0x18003d493  xorps   xmm0, xmm0
0x18003d496  xor     edx, edx
0x18003d498  movups  [rbp+var_38], xmm0
0x18003d49c  movups  xmmword ptr [rbp+pv], xmm0
0x18003d4a0  movups  [rbp+var_18], xmm0
0x18003d4a4  call    TestQueryData
0x18003d4a9  mov     rcx, [rbp+pv+8]; pv
0x18003d4ad  test    eax, eax
0x18003d4af  jnz     short loc_18003D4E3
0x18003d4b1  call    cs:__imp_CoTaskMemFree
0x18003d4b7  mov     [rbp+pv+8], 0
0x18003d4bf  xor     bl, bl
0x18003d4c1  lea     rcx, [rbp+var_40]
0x18003d4c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003d4ca  mov     al, bl
0x18003d4cc  mov     rcx, [rbp+var_8]
0x18003d4d0  xor     rcx, rsp; StackCookie
0x18003d4d3  call    __security_check_cookie
0x18003d4d8  mov     rbx, [rsp+60h+arg_8]
0x18003d4dd  add     rsp, 60h
0x18003d4e1  pop     rbp
0x18003d4e2  retn
0x18003d4e3  mov     eax, dword ptr [rbp+pv+4]
0x18003d4e6  or      [rbx+40h], eax
0x18003d4e9  test    rcx, rcx
0x18003d4ec  jz      short loc_18003D500
0x18003d4ee  lea     rdx, [rbp+var_38]
0x18003d4f2  mov     rcx, rbx
0x18003d4f5  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003d4fa  mov     rcx, [rbp+pv+8]
0x18003d4fe  jmp     short loc_18003D509
0x18003d500  mov     eax, dword ptr [rbp+pv]
0x18003d503  mov     [rbx+0B8h], eax
0x18003d509  call    cs:__imp_CoTaskMemFree
0x18003d50f  mov     ebx, [rbx+40h]
0x18003d512  shr     ebx, 8
0x18003d515  not     bl
0x18003d517  and     bl, 1
0x18003d51a  jmp     short loc_18003D4C1
```

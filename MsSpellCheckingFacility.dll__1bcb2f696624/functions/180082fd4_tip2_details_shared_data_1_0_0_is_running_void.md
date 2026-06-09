# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x180082fd4`
- end: `0x1800830b8`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041524`
- `0x180046b88`
- `0x1800510bc`
- `0x18007ded0`
- `0x180082050`

## callees

- `0x18003b2d4`
- `0x180054d08`
- `0x180057ac4`
- `0x180061320`
- `0x1800785e0`
- `0x180082fd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008304d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800830a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008304d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800830a5`

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
0x180082fd4  mov     [rsp-8+arg_8], rbx
0x180082fd9  push    rbp
0x180082fda  mov     rbp, rsp
0x180082fdd  sub     rsp, 60h
0x180082fe1  mov     rax, cs:__security_cookie
0x180082fe8  xor     rax, rsp
0x180082feb  mov     [rbp+var_8], rax
0x180082fef  mov     rbx, rcx
0x180082ff2  lea     rdx, [rcx+0C0h]
0x180082ff9  lea     rcx, [rbp+var_40]
0x180082ffd  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180083002  mov     rcx, [rbx+0F0h]
0x180083009  test    rcx, rcx
0x18008300c  jz      short loc_18008305B
0x18008300e  test    dword ptr [rbx+40h], 100h
0x180083015  jnz     short loc_18008305B
0x180083017  cmp     dword ptr [rbx+0E8h], 0
0x18008301e  jnz     loc_1800830AB
0x180083024  mov     r8d, [rbx+0B8h]
0x18008302b  lea     r9, [rbp+var_38]
0x18008302f  xorps   xmm0, xmm0
0x180083032  xor     edx, edx
0x180083034  movups  [rbp+var_38], xmm0
0x180083038  movups  xmmword ptr [rbp+pv], xmm0
0x18008303c  movups  [rbp+var_18], xmm0
0x180083040  call    TestQueryData
0x180083045  mov     rcx, [rbp+pv+8]; pv
0x180083049  test    eax, eax
0x18008304b  jnz     short loc_18008307F
0x18008304d  call    cs:__imp_CoTaskMemFree
0x180083053  mov     [rbp+pv+8], 0
0x18008305b  xor     bl, bl
0x18008305d  lea     rcx, [rbp+var_40]
0x180083061  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180083066  mov     al, bl
0x180083068  mov     rcx, [rbp+var_8]
0x18008306c  xor     rcx, rsp; StackCookie
0x18008306f  call    __security_check_cookie
0x180083074  mov     rbx, [rsp+60h+arg_8]
0x180083079  add     rsp, 60h
0x18008307d  pop     rbp
0x18008307e  retn
0x18008307f  mov     eax, dword ptr [rbp+pv+4]
0x180083082  or      [rbx+40h], eax
0x180083085  test    rcx, rcx
0x180083088  jz      short loc_18008309C
0x18008308a  lea     rdx, [rbp+var_38]
0x18008308e  mov     rcx, rbx
0x180083091  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180083096  mov     rcx, [rbp+pv+8]
0x18008309a  jmp     short loc_1800830A5
0x18008309c  mov     eax, dword ptr [rbp+pv]
0x18008309f  mov     [rbx+0B8h], eax
0x1800830a5  call    cs:__imp_CoTaskMemFree
0x1800830ab  mov     ebx, [rbx+40h]
0x1800830ae  shr     ebx, 8
0x1800830b1  not     bl
0x1800830b3  and     bl, 1
0x1800830b6  jmp     short loc_18008305D
```

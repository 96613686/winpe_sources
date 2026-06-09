# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x18006ac7c`
- end: `0x18006ad60`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180069324`

## callees

- `0x18000c6e0`
- `0x1800134d4`
- `0x1800166c8`
- `0x180017a80`
- `0x1800444e8`
- `0x18006ac7c`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18006acf5`
- `OLE32!CoTaskMemFree` at `0x18006ad4d`
- `OLE32!CoTaskMemFree` at `0x18006acf5`
- `OLE32!CoTaskMemFree` at `0x18006ad4d`

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
0x18006ac7c  mov     [rsp-8+arg_8], rbx
0x18006ac81  push    rbp
0x18006ac82  mov     rbp, rsp
0x18006ac85  sub     rsp, 60h
0x18006ac89  mov     rax, cs:__security_cookie
0x18006ac90  xor     rax, rsp
0x18006ac93  mov     [rbp+var_8], rax
0x18006ac97  mov     rbx, rcx
0x18006ac9a  lea     rdx, [rcx+0C0h]
0x18006aca1  lea     rcx, [rbp+var_40]
0x18006aca5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006acaa  mov     rcx, [rbx+0F0h]
0x18006acb1  test    rcx, rcx
0x18006acb4  jz      short loc_18006AD03
0x18006acb6  test    dword ptr [rbx+40h], 100h
0x18006acbd  jnz     short loc_18006AD03
0x18006acbf  cmp     dword ptr [rbx+0E8h], 0
0x18006acc6  jnz     loc_18006AD53
0x18006accc  mov     r8d, [rbx+0B8h]
0x18006acd3  lea     r9, [rbp+var_38]
0x18006acd7  xorps   xmm0, xmm0
0x18006acda  xor     edx, edx
0x18006acdc  movups  [rbp+var_38], xmm0
0x18006ace0  movups  xmmword ptr [rbp+pv], xmm0
0x18006ace4  movups  [rbp+var_18], xmm0
0x18006ace8  call    TestQueryData
0x18006aced  mov     rcx, [rbp+pv+8]; pv
0x18006acf1  test    eax, eax
0x18006acf3  jnz     short loc_18006AD27
0x18006acf5  call    cs:__imp_CoTaskMemFree
0x18006acfb  mov     [rbp+pv+8], 0
0x18006ad03  xor     bl, bl
0x18006ad05  lea     rcx, [rbp+var_40]
0x18006ad09  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18006ad0e  mov     al, bl
0x18006ad10  mov     rcx, [rbp+var_8]
0x18006ad14  xor     rcx, rsp; StackCookie
0x18006ad17  call    __security_check_cookie
0x18006ad1c  mov     rbx, [rsp+60h+arg_8]
0x18006ad21  add     rsp, 60h
0x18006ad25  pop     rbp
0x18006ad26  retn
0x18006ad27  mov     eax, dword ptr [rbp+pv+4]
0x18006ad2a  or      [rbx+40h], eax
0x18006ad2d  test    rcx, rcx
0x18006ad30  jz      short loc_18006AD44
0x18006ad32  lea     rdx, [rbp+var_38]
0x18006ad36  mov     rcx, rbx
0x18006ad39  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18006ad3e  mov     rcx, [rbp+pv+8]
0x18006ad42  jmp     short loc_18006AD4D
0x18006ad44  mov     eax, dword ptr [rbp+pv]
0x18006ad47  mov     [rbx+0B8h], eax
0x18006ad4d  call    cs:__imp_CoTaskMemFree
0x18006ad53  mov     ebx, [rbx+40h]
0x18006ad56  shr     ebx, 8
0x18006ad59  not     bl
0x18006ad5b  and     bl, 1
0x18006ad5e  jmp     short loc_18006AD05
```

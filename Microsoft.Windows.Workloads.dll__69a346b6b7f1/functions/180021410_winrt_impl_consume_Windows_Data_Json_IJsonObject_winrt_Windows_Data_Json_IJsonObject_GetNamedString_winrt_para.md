# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)

- ea: `0x180021410`
- end: `0x18002147c`
- name: `?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `108`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x180004810`
- `0x180021410`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  int v5; // eax
  _QWORD *result; // rax
  _QWORD *v7; // [rsp+28h] [rbp-20h] BYREF

  v7 = a2;
  v3 = *a1;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v3 + 80LL))(v3, *a3, &v7);
  if ( v5 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v5);
  }
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x180021410  push    rbx
0x180021412  sub     rsp, 40h
0x180021416  mov     rax, cs:__security_cookie
0x18002141d  xor     rax, rsp
0x180021420  mov     [rsp+48h+var_18], rax
0x180021425  mov     [rsp+48h+var_20], rdx
0x18002142a  xor     eax, eax
0x18002142c  mov     rcx, [rcx]
0x18002142f  mov     r9, r8
0x180021432  mov     [rsp+48h+var_20], rax
0x180021437  lea     r8, [rsp+48h+var_20]
0x18002143c  mov     rbx, rdx
0x18002143f  mov     rax, [rcx]
0x180021442  mov     rdx, [r9]
0x180021445  mov     rax, [rax+50h]
0x180021449  call    cs:__guard_dispatch_icall_fptr
0x18002144f  test    eax, eax
0x180021451  js      short loc_180021471
0x180021453  mov     rcx, [rsp+48h+var_20]
0x180021458  mov     rax, rbx
0x18002145b  mov     [rbx], rcx
0x18002145e  mov     rcx, [rsp+48h+var_18]
0x180021463  xor     rcx, rsp; StackCookie
0x180021466  call    __security_check_cookie
0x18002146b  add     rsp, 40h
0x18002146f  pop     rbx
0x180021470  retn
0x180021471  lfence
0x180021474  mov     ecx, eax
0x180021476  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

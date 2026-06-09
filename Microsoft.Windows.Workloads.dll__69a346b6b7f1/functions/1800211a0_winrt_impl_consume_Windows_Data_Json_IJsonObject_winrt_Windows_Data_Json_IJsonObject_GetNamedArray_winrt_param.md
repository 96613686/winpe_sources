# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)

- ea: `0x1800211a0`
- end: `0x18002120c`
- name: `?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `108`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x180004810`
- `0x1800211a0`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
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
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v3 + 72LL))(v3, *a3, &v7);
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
0x1800211a0  push    rbx
0x1800211a2  sub     rsp, 40h
0x1800211a6  mov     rax, cs:__security_cookie
0x1800211ad  xor     rax, rsp
0x1800211b0  mov     [rsp+48h+var_18], rax
0x1800211b5  mov     [rsp+48h+var_20], rdx
0x1800211ba  xor     eax, eax
0x1800211bc  mov     rcx, [rcx]
0x1800211bf  mov     r9, r8
0x1800211c2  mov     [rsp+48h+var_20], rax
0x1800211c7  lea     r8, [rsp+48h+var_20]
0x1800211cc  mov     rbx, rdx
0x1800211cf  mov     rax, [rcx]
0x1800211d2  mov     rdx, [r9]
0x1800211d5  mov     rax, [rax+48h]
0x1800211d9  call    cs:__guard_dispatch_icall_fptr
0x1800211df  test    eax, eax
0x1800211e1  js      short loc_180021201
0x1800211e3  mov     rcx, [rsp+48h+var_20]
0x1800211e8  mov     rax, rbx
0x1800211eb  mov     [rbx], rcx
0x1800211ee  mov     rcx, [rsp+48h+var_18]
0x1800211f3  xor     rcx, rsp; StackCookie
0x1800211f6  call    __security_check_cookie
0x1800211fb  add     rsp, 40h
0x1800211ff  pop     rbx
0x180021200  retn
0x180021201  lfence
0x180021204  mov     ecx, eax
0x180021206  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

# winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)

- ea: `0x1800215e0`
- end: `0x180021636`
- name: `?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `86`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x180004810`
- `0x1800215e0`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  int v4; // eax
  _BYTE v6[8]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  v3 = *a2;
  v6[0] = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v2 + 96LL))(v2, v3, v6);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v4);
  }
  return v6[0];
}

```

## disassembly

```asm
0x1800215e0  sub     rsp, 38h
0x1800215e4  mov     rax, cs:__security_cookie
0x1800215eb  xor     rax, rsp
0x1800215ee  mov     [rsp+38h+var_10], rax
0x1800215f3  mov     rcx, [rcx]
0x1800215f6  lea     r8, [rsp+38h+var_18]
0x1800215fb  mov     rdx, [rdx]
0x1800215fe  mov     [rsp+38h+var_18], 0
0x180021603  mov     rax, [rcx]
0x180021606  mov     rax, [rax+60h]
0x18002160a  call    cs:__guard_dispatch_icall_fptr
0x180021610  test    eax, eax
0x180021612  js      short loc_18002162B
0x180021614  movzx   eax, [rsp+38h+var_18]
0x180021619  mov     rcx, [rsp+38h+var_10]
0x18002161e  xor     rcx, rsp; StackCookie
0x180021621  call    __security_check_cookie
0x180021626  add     rsp, 38h
0x18002162a  retn
0x18002162b  lfence
0x18002162e  mov     ecx, eax
0x180021630  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

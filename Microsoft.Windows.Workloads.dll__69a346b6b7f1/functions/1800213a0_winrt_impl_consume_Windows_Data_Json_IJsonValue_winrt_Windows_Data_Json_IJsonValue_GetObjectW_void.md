# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)

- ea: `0x1800213a0`
- end: `0x180021406`
- name: `?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `102`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001eb00`

## callees

- `0x180004810`
- `0x1800213a0`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v2; // rcx
  int v4; // eax
  _QWORD *result; // rax
  _QWORD *v6; // [rsp+28h] [rbp-20h] BYREF

  v6 = a2;
  v2 = *a1;
  v6 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v2 + 96LL))(v2, &v6);
  if ( v4 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v4);
  }
  result = a2;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1800213a0  push    rbx
0x1800213a2  sub     rsp, 40h
0x1800213a6  mov     rax, cs:__security_cookie
0x1800213ad  xor     rax, rsp
0x1800213b0  mov     [rsp+48h+var_18], rax
0x1800213b5  mov     [rsp+48h+var_20], rdx
0x1800213ba  xor     eax, eax
0x1800213bc  mov     rcx, [rcx]
0x1800213bf  mov     rbx, rdx
0x1800213c2  mov     [rsp+48h+var_20], rax
0x1800213c7  lea     rdx, [rsp+48h+var_20]
0x1800213cc  mov     rax, [rcx]
0x1800213cf  mov     rax, [rax+60h]
0x1800213d3  call    cs:__guard_dispatch_icall_fptr
0x1800213d9  test    eax, eax
0x1800213db  js      short loc_1800213FB
0x1800213dd  mov     rcx, [rsp+48h+var_20]
0x1800213e2  mov     rax, rbx
0x1800213e5  mov     [rbx], rcx
0x1800213e8  mov     rcx, [rsp+48h+var_18]
0x1800213ed  xor     rcx, rsp; StackCookie
0x1800213f0  call    __security_check_cookie
0x1800213f5  add     rsp, 40h
0x1800213f9  pop     rbx
0x1800213fa  retn
0x1800213fb  lfence
0x1800213fe  mov     ecx, eax
0x180021400  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```

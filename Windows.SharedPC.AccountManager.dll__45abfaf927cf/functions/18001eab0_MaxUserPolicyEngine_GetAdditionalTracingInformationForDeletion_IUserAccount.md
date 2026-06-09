# MaxUserPolicyEngine::GetAdditionalTracingInformationForDeletion(IUserAccount *)

- ea: `0x18001eab0`
- end: `0x18001eb33`
- name: `?GetAdditionalTracingInformationForDeletion@MaxUserPolicyEngine@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUserAccount@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x18000a1bc`
- `0x180017214`
- `0x180019874`
- `0x18001eab0`
- `0x180026010`

## string_xrefs

- `0x18001eaf6`: `LastAccessedTimeUTC: 0x%I64x`

## pseudocode

```c
__int64 __fastcall MaxUserPolicyEngine::GetAdditionalTracingInformationForDeletion(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  const WCHAR *v5; // rdx
  _QWORD v7[4]; // [rsp+28h] [rbp-20h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v8);
  memset(v7, 0, 24);
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         v7,
         L"LastAccessedTimeUTC: 0x%I64x",
         v8);
  v5 = (const WCHAR *)v7[0];
  if ( v4 < 0 )
    v5 = &String2;
  std::wstring::wstring(a2, (__int64)v5);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v7);
  return a2;
}

```

## disassembly

```asm
0x18001eab0  push    rbx
0x18001eab2  sub     rsp, 40h
0x18001eab6  mov     rbx, rdx
0x18001eab9  mov     [rsp+48h+arg_10], 0
0x18001eac2  mov     rax, [r8]
0x18001eac5  lea     rdx, [rsp+48h+arg_10]
0x18001eaca  mov     rcx, r8
0x18001eacd  mov     rax, [rax+30h]
0x18001ead1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ead6  mov     [rsp+48h+var_20], 0
0x18001eadf  mov     [rsp+48h+var_18], 0
0x18001eae8  mov     [rsp+48h+var_10], 0
0x18001eaf1  mov     r8, [rsp+48h+arg_10]
0x18001eaf6  lea     rdx, aLastaccessedti; "LastAccessedTimeUTC: 0x%I64x"
0x18001eafd  lea     rcx, [rsp+48h+var_20]
0x18001eb02  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001eb07  mov     rcx, rbx
0x18001eb0a  test    eax, eax
0x18001eb0c  mov     rdx, [rsp+48h+var_20]
0x18001eb11  jns     short loc_18001EB1A
0x18001eb13  lea     rdx, String2
0x18001eb1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001eb1f  nop
0x18001eb20  lea     rcx, [rsp+48h+var_20]
0x18001eb25  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001eb2a  mov     rax, rbx
0x18001eb2d  add     rsp, 40h
0x18001eb31  pop     rbx
0x18001eb32  retn
```

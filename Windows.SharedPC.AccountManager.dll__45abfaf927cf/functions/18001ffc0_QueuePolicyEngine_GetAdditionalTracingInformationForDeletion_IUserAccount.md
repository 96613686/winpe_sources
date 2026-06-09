# QueuePolicyEngine::GetAdditionalTracingInformationForDeletion(IUserAccount *)

- ea: `0x18001ffc0`
- end: `0x180020043`
- name: `?GetAdditionalTracingInformationForDeletion@QueuePolicyEngine@@MEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUserAccount@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x18000a1bc`
- `0x180017214`
- `0x180019874`
- `0x18001ffc0`
- `0x180026010`

## string_xrefs

- `0x180020006`: `LastAccessedTime: 0x%I64x`

## pseudocode

```c
__int64 __fastcall QueuePolicyEngine::GetAdditionalTracingInformationForDeletion(__int64 a1, __int64 a2, __int64 a3)
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
         L"LastAccessedTime: 0x%I64x",
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
0x18001ffc0  push    rbx
0x18001ffc2  sub     rsp, 40h
0x18001ffc6  mov     rbx, rdx
0x18001ffc9  mov     [rsp+48h+arg_10], 0
0x18001ffd2  mov     rax, [r8]
0x18001ffd5  lea     rdx, [rsp+48h+arg_10]
0x18001ffda  mov     rcx, r8
0x18001ffdd  mov     rax, [rax+30h]
0x18001ffe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffe6  mov     [rsp+48h+var_20], 0
0x18001ffef  mov     [rsp+48h+var_18], 0
0x18001fff8  mov     [rsp+48h+var_10], 0
0x180020001  mov     r8, [rsp+48h+arg_10]
0x180020006  lea     rdx, aLastaccessedti_0; "LastAccessedTime: 0x%I64x"
0x18002000d  lea     rcx, [rsp+48h+var_20]
0x180020012  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180020017  mov     rcx, rbx
0x18002001a  test    eax, eax
0x18002001c  mov     rdx, [rsp+48h+var_20]
0x180020021  jns     short loc_18002002A
0x180020023  lea     rdx, String2
0x18002002a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002002f  nop
0x180020030  lea     rcx, [rsp+48h+var_20]
0x180020035  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002003a  mov     rax, rbx
0x18002003d  add     rsp, 40h
0x180020041  pop     rbx
0x180020042  retn
```

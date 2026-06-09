# Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(long)

- ea: `0x180005034`
- end: `0x18000508e`
- name: `?EnsureStackSnapshot@?$DelegateTraits@$0?0@WRL@Microsoft@@SAXJ@Z`
- size: `90`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005dc0`
- `0x180005e00`
- `0x180005e30`
- `0x180005e60`
- `0x180005e90`

## callees

- `0x180005034`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x180005046`
- `api-ms-win-core-winrt-error-l1-1-1!RoGetMatchingRestrictedErrorInfo` at `0x180005046`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000505b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000505b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rcx
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  result = RoGetMatchingRestrictedErrorInfo(a1, &v3);
  if ( (int)result >= 0 )
    result = SetRestrictedErrorInfo(v3);
  v2 = v3;
  if ( v3 )
  {
    v3 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180005034  sub     rsp, 28h
0x180005038  mov     [rsp+28h+arg_8], 0
0x180005041  lea     rdx, [rsp+28h+arg_8]
0x180005046  call    cs:__imp_RoGetMatchingRestrictedErrorInfo
0x18000504d  nop     dword ptr [rax+rax+00h]
0x180005052  test    eax, eax
0x180005054  js      short loc_180005068
0x180005056  mov     rcx, [rsp+28h+arg_8]
0x18000505b  call    cs:__imp_SetRestrictedErrorInfo
0x180005062  nop     dword ptr [rax+rax+00h]
0x180005067  nop
0x180005068  mov     rcx, [rsp+28h+arg_8]
0x18000506d  test    rcx, rcx
0x180005070  jz      short loc_180005088
0x180005072  mov     [rsp+28h+arg_8], 0
0x18000507b  mov     rax, [rcx]
0x18000507e  mov     rax, [rax+10h]
0x180005082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005087  nop
0x180005088  add     rsp, 28h
0x18000508c  retn
```

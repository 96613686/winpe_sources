# GetApplicablePackages

- ea: `0x18000ce90`
- end: `0x18000cedd`
- name: `GetApplicablePackages`
- size: `77`
- prototype: `__int64 __fastcall(struct IAppxBundleManifestReader *, struct ApplicabilityContext *, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000ce90`
- `0x18000cef0`
- `0x18000d6f4`

## pseudocode

```c
__int64 __fastcall GetApplicablePackages(
        struct IAppxBundleManifestReader *a1,
        struct ApplicabilityContext *a2,
        _DWORD *a3,
        _QWORD *a4)
{
  int ApplicablePackagesWithAppChosenResources; // eax
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ApplicablePackagesWithAppChosenResources = GetApplicablePackagesWithAppChosenResources(a1, a2, 0, 0, a3, a4);
  try
  {
    if ( ApplicablePackagesWithAppChosenResources < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)ApplicablePackagesWithAppChosenResources,
        v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B2,
                           (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000ce90  sub     rsp, 48h
0x18000ce94  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFEh
0x18000ce9d  mov     [rsp+48h+var_20], r9; __int64
0x18000cea2  mov     [rsp+48h+var_28], r8; int
0x18000cea7  xor     r9d, r9d; unsigned __int16 **
0x18000ceaa  xor     r8d, r8d; unsigned int
0x18000cead  call    GetApplicablePackagesWithAppChosenResources
0x18000ceb2  mov     rcx, [rsp+48h]; this
0x18000ceb7  test    eax, eax
0x18000ceb9  jns     short loc_18000CECF
0x18000cebb  mov     r9d, eax; char *
0x18000cebe  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000cec5  mov     edx, 1AFh; void *
0x18000ceca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cecf  xor     eax, eax
0x18000ced1  jmp     short loc_18000CED7
0x18000ced3  mov     eax, [rsp+48h+var_18]
0x18000ced7  add     rsp, 48h
0x18000cedb  retn
```

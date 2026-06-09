# GetApplicablePackagesForUser

- ea: `0x18000d290`
- end: `0x18000d2dd`
- name: `GetApplicablePackagesForUser`
- size: `77`
- prototype: `__int64 __fastcall(struct IAppxBundleManifestReader *, void *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000d290`
- `0x18000d510`
- `0x18000d6f4`

## pseudocode

```c
__int64 __fastcall GetApplicablePackagesForUser(struct IAppxBundleManifestReader *a1, void *a2, __int64 a3, __int64 a4)
{
  int ApplicablePackagesForUserWithAppChosenResources; // eax
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  ApplicablePackagesForUserWithAppChosenResources = GetApplicablePackagesForUserWithAppChosenResources(
                                                      a1,
                                                      a2,
                                                      0,
                                                      0,
                                                      a3,
                                                      a4);
  try
  {
    if ( ApplicablePackagesForUserWithAppChosenResources < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
        (const char *)(unsigned int)ApplicablePackagesForUserWithAppChosenResources,
        v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C0,
                           (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\resolver.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000d290  sub     rsp, 48h
0x18000d294  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFEh
0x18000d29d  mov     [rsp+48h+var_20], r9; __int64
0x18000d2a2  mov     [rsp+48h+var_28], r8; int
0x18000d2a7  xor     r9d, r9d; unsigned __int16 **
0x18000d2aa  xor     r8d, r8d; unsigned int
0x18000d2ad  call    GetApplicablePackagesForUserWithAppChosenResources
0x18000d2b2  mov     rcx, [rsp+48h]; this
0x18000d2b7  test    eax, eax
0x18000d2b9  jns     short loc_18000D2CF
0x18000d2bb  mov     r9d, eax; char *
0x18000d2be  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\mrt\\applicability\\s"...
0x18000d2c5  mov     edx, 1BDh; void *
0x18000d2ca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d2cf  xor     eax, eax
0x18000d2d1  jmp     short loc_18000D2D7
0x18000d2d3  mov     eax, [rsp+48h+var_18]
0x18000d2d7  add     rsp, 48h
0x18000d2db  retn
```

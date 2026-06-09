# ShouldIncludeRegionNameBasedOnUILanguageInfo(ushort const *)

- ea: `0x180019554`
- end: `0x1800195a8`
- name: `?ShouldIncludeRegionNameBasedOnUILanguageInfo@@YA_NPEBG@Z`
- size: `84`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015030`

## callees

- `0x18001334c`
- `0x18001b504`

## string_xrefs

- `0x180019574`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
bool __fastcall ShouldIncludeRegionNameBasedOnUILanguageInfo(const unsigned __int16 *a1)
{
  unsigned int v2; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v2 = CallRtlGetUILanguageInfo(a1, &v5);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x93,
    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
    (const char *)v2,
    (int)"lang: %ws",
    (const char *)a1);
  return BYTE1(v5) & 1;
}

```

## disassembly

```asm
0x180019554  push    rbx
0x180019556  sub     rsp, 30h
0x18001955a  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x18001955f  mov     [rsp+38h+arg_0], 0
0x180019567  mov     rbx, rcx
0x18001956a  call    ?CallRtlGetUILanguageInfo@@YAJPEBGPEAK@Z; CallRtlGetUILanguageInfo(ushort const *,ulong *)
0x18001956f  mov     rcx, [rsp+38h]; this
0x180019574  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001957b  mov     r9d, eax; char *
0x18001957e  mov     [rsp+38h+var_10], rbx; char *
0x180019583  lea     rax, aLangWs; "lang: %ws"
0x18001958a  mov     edx, 93h; void *
0x18001958f  mov     qword ptr [rsp+38h+var_18], rax; int
0x180019594  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180019599  mov     eax, [rsp+38h+arg_0]
0x18001959d  shr     eax, 8
0x1800195a0  and     al, 1
0x1800195a2  add     rsp, 30h
0x1800195a6  pop     rbx
0x1800195a7  retn
```

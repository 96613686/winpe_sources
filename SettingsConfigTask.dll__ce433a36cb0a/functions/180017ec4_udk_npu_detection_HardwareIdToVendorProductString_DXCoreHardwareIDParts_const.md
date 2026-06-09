# udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)

- ea: `0x180017ec4`
- end: `0x180017fb2`
- name: `?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019898`

## callees

- `0x1800021d0`
- `0x180009f8c`
- `0x180011918`
- `0x180017ec4`
- `0x18001c9e4`

## string_xrefs

- `0x180017f29`: `VEN_QCOM&DEV_%c%c%c%c`

## pseudocode

```c
__int64 __fastcall udk::npu_detection::HardwareIdToVendorProductString(__int64 a1, unsigned int *a2)
{
  int v3; // eax
  int v4; // eax
  int v6; // [rsp+20h] [rbp-B8h]
  int v7; // [rsp+20h] [rbp-B8h]
  unsigned __int16 v8[56]; // [rsp+50h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( *a2 == 1297040209 )
  {
    v7 = *((unsigned __int8 *)a2 + 5);
    v4 = StringCchPrintfW(v8, 0x38u, L"VEN_QCOM&DEV_%c%c%c%c", *((unsigned __int8 *)a2 + 4));
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
        (const char *)(unsigned int)v4,
        v7);
  }
  else
  {
    v6 = a2[1];
    v3 = StringCchPrintfW(v8, 0x38u, L"VEN_%X&DEV_%X", *a2);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
        (const char *)(unsigned int)v3,
        v6);
  }
  std::wstring::wstring(a1, v8);
  return a1;
}

```

## disassembly

```asm
0x180017ec4  push    rbx
0x180017ec6  sub     rsp, 0D0h
0x180017ecd  mov     rax, cs:__security_cookie
0x180017ed4  xor     rax, rsp
0x180017ed7  mov     [rsp+0D8h+var_18], rax
0x180017edf  cmp     dword ptr [rdx], 4D4F4351h
0x180017ee5  mov     r8, rdx
0x180017ee8  mov     rbx, rcx
0x180017eeb  mov     [rsp+0D8h+var_90], rcx
0x180017ef0  jz      short loc_180017F18
0x180017ef2  mov     eax, [rdx+4]
0x180017ef5  lea     r8, aVenXDevX; "VEN_%X&DEV_%X"
0x180017efc  mov     r9d, [rdx]
0x180017eff  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x180017f04  mov     edx, 38h ; '8'; unsigned __int64
0x180017f09  mov     [rsp+0D8h+var_B8], eax; int
0x180017f0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017f12  test    eax, eax
0x180017f14  js      short loc_180017F95
0x180017f16  jmp     short loc_180017F4F
0x180017f18  movzx   ecx, byte ptr [rdx+6]
0x180017f1c  movzx   eax, byte ptr [rdx+7]
0x180017f20  movzx   edx, byte ptr [rdx+5]
0x180017f24  movzx   r9d, byte ptr [r8+4]
0x180017f29  lea     r8, aVenQcomDevCCCC; "VEN_QCOM&DEV_%c%c%c%c"
0x180017f30  mov     [rsp+0D8h+var_A8], eax
0x180017f34  mov     [rsp+0D8h+var_B0], ecx
0x180017f38  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x180017f3d  mov     [rsp+0D8h+var_B8], edx; int
0x180017f41  mov     edx, 38h ; '8'; unsigned __int64
0x180017f46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017f4b  test    eax, eax
0x180017f4d  js      short loc_180017F78
0x180017f4f  lea     rdx, [rsp+0D8h+var_88]
0x180017f54  mov     rcx, rbx
0x180017f57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180017f5c  mov     rax, rbx
0x180017f5f  mov     rcx, [rsp+0D8h+var_18]
0x180017f67  xor     rcx, rsp; StackCookie
0x180017f6a  call    __security_check_cookie
0x180017f6f  add     rsp, 0D0h
0x180017f76  pop     rbx
0x180017f77  retn
0x180017f78  mov     rcx, [rsp+0D8h]; this
0x180017f80  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x180017f87  mov     r9d, eax; char *
0x180017f8a  mov     edx, 103h; void *
0x180017f8f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017f95  mov     rcx, [rsp+0D8h]; this
0x180017f9d  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x180017fa4  mov     r9d, eax; char *
0x180017fa7  mov     edx, 10Ch; void *
0x180017fac  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

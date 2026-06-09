# Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(void)

- ea: `0x18001cafc`
- end: `0x18001cb63`
- name: `?FinalizeAndRelease@?$RegValueReadTraits@VHString@Wrappers@WRL@Microsoft@@@Registry@@QEAA?AVHString@Wrappers@WRL@Microsoft@@XZ`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019d84`
- `0x18001f5c0`

## callees

- `0x180010150`
- `0x180014990`
- `0x18001cafc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cb54`

## string_xrefs

- `0x18001cb2f`: `onecoreuap\enduser\winstore\installservice\lib\RegHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Registry::RegValueReadTraits<Microsoft::WRL::Wrappers::HString>::FinalizeAndRelease(
        __int64 *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v8 = *a1;
  v3 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v7, &v8);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\RegHelpers.h",
      (const char *)(unsigned int)v3,
      v5);
  *a2 = v7;
  v7 = 0;
  WindowsDeleteString(0);
  return a2;
}

```

## disassembly

```asm
0x18001cafc  mov     r11, rsp
0x18001caff  push    rbx
0x18001cb00  sub     rsp, 30h
0x18001cb04  mov     rbx, rdx
0x18001cb07  mov     qword ptr [r11+8], 0
0x18001cb0f  mov     rax, [rcx]
0x18001cb12  mov     [r11+18h], rax
0x18001cb16  lea     rdx, [r11+18h]
0x18001cb1a  lea     rcx, [r11+8]
0x18001cb1e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18001cb23  mov     rcx, [rsp+38h]; this
0x18001cb28  test    eax, eax
0x18001cb2a  jns     short loc_18001CB41
0x18001cb2c  mov     r9d, eax; char *
0x18001cb2f  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\installs"...
0x18001cb36  mov     edx, 6Ah ; 'j'; void *
0x18001cb3b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001cb41  mov     rax, [rsp+38h+arg_0]
0x18001cb46  mov     [rbx], rax
0x18001cb49  mov     [rsp+38h+arg_0], 0
0x18001cb52  xor     ecx, ecx; string
0x18001cb54  call    cs:__imp_WindowsDeleteString
0x18001cb5a  mov     rax, rbx
0x18001cb5d  add     rsp, 30h
0x18001cb61  pop     rbx
0x18001cb62  retn
```

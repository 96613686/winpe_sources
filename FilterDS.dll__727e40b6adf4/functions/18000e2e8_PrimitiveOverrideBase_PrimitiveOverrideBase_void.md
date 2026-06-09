# PrimitiveOverrideBase::~PrimitiveOverrideBase(void)

- ea: `0x18000e2e8`
- end: `0x18000e34f`
- name: `??1PrimitiveOverrideBase@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(PrimitiveOverrideBase *this, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e2a8`
- `0x18000e3c0`

## callees

- `0x180006bd0`
- `0x18000e2e8`
- `0x180024010`

## string_xrefs

- `0x18000e33d`: `mincore\textinput\dev\mtf\datasources\filterds\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrimitiveOverrideBase::~PrimitiveOverrideBase(
        PrimitiveOverrideBase *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &PrimitiveOverrideBase::`vftable'{for `IMtfSuggestionCandidatePrimitive'};
  *((_QWORD *)this + 1) = &PrimitiveDisplayOverride::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMtfSuggestionListElement>'};
  if ( _InterlockedAdd(&g_cRefDll, 0xFFFFFFFF) < 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2E,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\dll\\dllmain.cpp",
      a4);
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18000e2e8  push    rbx
0x18000e2ea  sub     rsp, 20h
0x18000e2ee  mov     rbx, rcx
0x18000e2f1  lea     rax, ??_7PrimitiveOverrideBase@@6BIMtfSuggestionCandidatePrimitive@@@; const PrimitiveOverrideBase::`vftable'{for `IMtfSuggestionCandidatePrimitive'}
0x18000e2f8  mov     [rcx], rax
0x18000e2fb  lea     rax, ??_7PrimitiveDisplayOverride@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMtfSuggestionListElement@@@Details@WRL@Microsoft@@@; const PrimitiveDisplayOverride::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMtfSuggestionListElement>'}
0x18000e302  mov     [rcx+8], rax
0x18000e306  lock add cs:?g_cRefDll@@3JA, 0FFFFFFFFh; long g_cRefDll
0x18000e30e  sets    dl
0x18000e311  mov     rcx, [rsp+28h]; this
0x18000e316  test    dl, dl
0x18000e318  jnz     short loc_18000E33D
0x18000e31a  mov     rcx, [rbx+18h]
0x18000e31e  test    rcx, rcx
0x18000e321  jz      short loc_18000E330
0x18000e323  mov     rax, [rcx]
0x18000e326  mov     rax, [rax+10h]
0x18000e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e32f  nop
0x18000e330  mov     dword ptr [rbx+14h], 0C0000001h
0x18000e337  add     rsp, 20h
0x18000e33b  pop     rbx
0x18000e33c  retn
0x18000e33d  lea     r8, aMincoreTextinp_24; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18000e344  mov     edx, 2Eh ; '.'; void *
0x18000e349  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

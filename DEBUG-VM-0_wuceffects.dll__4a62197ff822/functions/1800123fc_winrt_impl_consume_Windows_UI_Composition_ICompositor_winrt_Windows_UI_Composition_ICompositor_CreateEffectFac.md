# winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(winrt::Windows::Graphics::Effects::IGraphicsEffect const &)

- ea: `0x1800123fc`
- end: `0x180012465`
- name: `?CreateEffectFactory@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUIGraphicsEffect@Effects@Graphics@Windows@3@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010aac`
- `0x180010c58`

## callees

- `0x1800123fc`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180012407`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  const char *v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v9 = 7613;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v12 = 0;
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 88))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x1800123fc  mov     r11, rsp
0x1800123ff  push    rbx
0x180012400  sub     rsp, 40h
0x180012404  mov     rcx, [rcx]
0x180012407  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001240e  mov     r9, r8
0x180012411  mov     [rsp+48h+var_20], 1DBDh
0x180012419  mov     [r11-18h], rax
0x18001241d  lea     r8, [r11+8]
0x180012421  mov     qword ptr [r11+8], 0
0x180012429  mov     rbx, rdx
0x18001242c  mov     rax, [rcx]
0x18001242f  mov     rdx, [r9]
0x180012432  mov     qword ptr [r11-10h], 0
0x18001243a  mov     rax, [rax+58h]
0x18001243e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012443  test    eax, eax
0x180012445  js      short loc_180012458
0x180012447  mov     rax, [rsp+48h+arg_0]
0x18001244c  mov     [rbx], rax
0x18001244f  mov     rax, rbx
0x180012452  add     rsp, 40h
0x180012456  pop     rbx
0x180012457  retn
0x180012458  lea     rdx, [rsp+48h+var_20]
0x18001245d  mov     ecx, eax
0x18001245f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

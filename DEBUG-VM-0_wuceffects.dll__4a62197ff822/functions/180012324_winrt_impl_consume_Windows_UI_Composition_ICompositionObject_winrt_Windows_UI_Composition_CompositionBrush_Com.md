# winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::CompositionBrush>::Compositor(void)

- ea: `0x180012324`
- end: `0x1800123f3`
- name: `?Compositor@?$consume_Windows_UI_Composition_ICompositionObject@UCompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x180012040`
- `0x180012324`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180012375`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::CompositionBrush>::Compositor(
        __int64 (__fastcall ****a1)(_QWORD, void *, __int64 *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, void *, __int64 *); // rcx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  int v8; // [rsp+28h] [rbp-18h] BYREF
  const char *v9; // [rsp+30h] [rbp-10h]
  __int64 v10; // [rsp+38h] [rbp-8h]
  __int64 v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v12 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v11 = 0;
    v4 = (**v3)(v3, &winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>, &v11);
    v5 = v11;
  }
  else
  {
    v4 = 0;
    v11 = 0;
    v5 = 0;
  }
  v8 = 4372;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v10 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v8);
  v8 = 4374;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 48LL))(v5, &v12);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v8);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x180012324  mov     [rsp-8+arg_8], rbx
0x180012329  push    rbp
0x18001232a  mov     rbp, rsp
0x18001232d  sub     rsp, 40h
0x180012331  mov     rbx, rdx
0x180012334  mov     [rbp+arg_10], 0
0x18001233c  mov     rcx, [rcx]
0x18001233f  test    rcx, rcx
0x180012342  jz      loc_1800123D1
0x180012348  mov     [rbp+arg_0], 0
0x180012350  mov     rax, [rcx]
0x180012353  lea     r8, [rbp+arg_0]
0x180012357  lea     rdx, ??$guid_v@UICompositionObject@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>
0x18001235e  mov     rax, [rax]
0x180012361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012366  mov     rcx, [rbp+arg_0]
0x18001236a  mov     [rbp+arg_0], rcx
0x18001236e  mov     [rbp+var_18], 1114h
0x180012375  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001237c  mov     [rbp+var_10], rdx
0x180012380  mov     [rbp+var_8], 0
0x180012388  test    eax, eax
0x18001238a  js      short loc_1800123DB
0x18001238c  mov     [rbp+var_18], 1116h
0x180012393  mov     [rbp+var_10], rdx
0x180012397  mov     [rbp+var_8], 0
0x18001239f  mov     rax, [rcx]
0x1800123a2  lea     rdx, [rbp+arg_10]
0x1800123a6  mov     rax, [rax+30h]
0x1800123aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123af  test    eax, eax
0x1800123b1  js      short loc_1800123E7
0x1800123b3  lea     rcx, [rbp+arg_0]
0x1800123b7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800123bc  mov     rax, [rbp+arg_10]
0x1800123c0  mov     [rbx], rax
0x1800123c3  mov     rax, rbx
0x1800123c6  mov     rbx, [rsp+40h+arg_8]
0x1800123cb  add     rsp, 40h
0x1800123cf  pop     rbp
0x1800123d0  retn
0x1800123d1  xor     eax, eax
0x1800123d3  mov     [rbp+arg_0], rax
0x1800123d7  xor     ecx, ecx
0x1800123d9  jmp     short loc_18001236E
0x1800123db  lea     rdx, [rbp+var_18]
0x1800123df  mov     ecx, eax
0x1800123e1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800123e7  lea     rdx, [rbp+var_18]
0x1800123eb  mov     ecx, eax
0x1800123ed  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

# Windows::UI::Composition::CompositionEffectBrush::InitializePropertySet(void)

- ea: `0x180044540`
- end: `0x180044790`
- name: `?InitializePropertySet@CompositionEffectBrush@Composition@UI@Windows@@AEAAJXZ`
- size: `592`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionEffectBrush *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180045d68`

## callees

- `0x18000dff0`
- `0x18001358c`
- `0x1800314dc`
- `0x180033c2c`
- `0x180044540`
- `0x18004cfec`
- `0x18004d2d4`
- `0x18004d7ac`
- `0x18004db80`
- `0x18004dcfc`
- `0x18004eb6c`
- `0x1800f6f10`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800446ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800446ba`

## string_xrefs

- `0x1800446aa`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioneffectbrush.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionEffectBrush::InitializePropertySet(
        Windows::UI::Composition::CompositionEffectBrush *this)
{
  __int64 *v2; // r14
  unsigned int *Properties; // rdi
  unsigned int v4; // r15d
  unsigned int i; // esi
  __int64 v7; // rcx
  void (__fastcall *v8)(__int64 *, _QWORD, HSTRING *, int *); // rbx
  __int64 v9; // r8
  __int64 v10; // r9
  int inserted; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r9
  int *v15; // [rsp+20h] [rbp-59h]
  HSTRING string; // [rsp+30h] [rbp-49h] BYREF
  int v17; // [rsp+38h] [rbp-41h] BYREF
  int v18; // [rsp+40h] [rbp-39h] BYREF
  int v19[16]; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *(__int64 **)(*((_QWORD *)this + 23) + 168LL);
  Properties = (unsigned int *)Windows::UI::Composition::CompositionObject::GetProperties(this, 1);
  Windows::UI::Composition::ProxyObject::SetReferenceProperty(this, 2, Properties[36]);
  memset_0(v19, 0, sizeof(v19));
  v4 = (*(__int64 (__fastcall **)(__int64 *))(*v2 + 16))(v2);
  for ( i = 0; ; ++i )
  {
    if ( i >= v4 )
      return 0;
    v7 = *v2;
    string = 0;
    v17 = 0;
    v8 = *(void (__fastcall **)(__int64 *, _QWORD, HSTRING *, int *))(v7 + 136);
    WindowsDeleteString(0);
    string = 0;
    v15 = v19;
    v8(v2, i, &string, &v17);
    switch ( v17 )
    {
      case 18:
        LOBYTE(v10) = 1;
        v18 = v19[0];
        v15 = &v18;
        inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetScalarValue,float>(
                     Properties,
                     string,
                     v9,
                     v10);
        v12 = inserted;
        if ( inserted >= 0 )
          goto LABEL_6;
        v13 = 402;
LABEL_13:
        v14 = (unsigned int)inserted;
        goto LABEL_14;
      case 35:
        inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector2Value,D2DVector2>(
                     (Windows::UI::Composition::CompositionObject *)Properties,
                     string,
                     (__int64)v19);
        v12 = inserted;
        if ( inserted < 0 )
        {
          v13 = 410;
          goto LABEL_13;
        }
        goto LABEL_6;
      case 52:
        inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector3Value,D2DVector3>(
                     (Windows::UI::Composition::CompositionObject *)Properties,
                     string,
                     (__int64)v19);
        v12 = inserted;
        if ( inserted < 0 )
        {
          v13 = 418;
          goto LABEL_13;
        }
        goto LABEL_6;
      case 69:
        inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector4Value,D2DVector4>(
                     (Windows::UI::Composition::CompositionObject *)Properties,
                     string,
                     (__int64)v19);
        v12 = inserted;
        if ( inserted < 0 )
        {
          v13 = 426;
          goto LABEL_13;
        }
        goto LABEL_6;
    }
    if ( v17 != 70 )
      break;
    inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetColorValue,_D3DCOLORVALUE>(
                 (Windows::UI::Composition::CompositionObject *)Properties,
                 string,
                 (__int64)v19);
    v12 = inserted;
    if ( inserted < 0 )
    {
      v13 = 434;
      goto LABEL_13;
    }
LABEL_6:
    WindowsDeleteString(string);
  }
  if ( v17 == 104 )
  {
    inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetMatrix3x2Value,D2D_MATRIX_3X2_F>(
                 (Windows::UI::Composition::CompositionObject *)Properties,
                 string,
                 (__int64)v19);
    v12 = inserted;
    if ( inserted < 0 )
    {
      v13 = 442;
      goto LABEL_13;
    }
    goto LABEL_6;
  }
  if ( v17 == 265 )
  {
    inserted = Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetMatrix4x4Value,D2DMatrix>(
                 (Windows::UI::Composition::CompositionObject *)Properties,
                 string,
                 (__int64)v19);
    v12 = inserted;
    if ( inserted < 0 )
    {
      v13 = 450;
      goto LABEL_13;
    }
    goto LABEL_6;
  }
  v12 = -2147467263;
  v13 = 456;
  v14 = 2147500033LL;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioneffectbrush.cpp",
    (const char *)v14,
    (int)v15);
  WindowsDeleteString(string);
  return v12;
}

```

## disassembly

```asm
0x180044540  push    rbp
0x180044542  push    rbx
0x180044543  push    rsi
0x180044544  push    rdi
0x180044545  push    r14
0x180044547  push    r15
0x180044549  lea     rbp, [rsp-2Fh]
0x18004454e  sub     rsp, 0A8h
0x180044555  mov     rax, cs:__security_cookie
0x18004455c  xor     rax, rsp
0x18004455f  mov     [rbp+57h+var_40], rax
0x180044563  mov     rax, [rcx+0B8h]
0x18004456a  mov     dl, 1; bool
0x18004456c  mov     rbx, rcx
0x18004456f  mov     r14, [rax+0A8h]
0x180044576  call    ?GetProperties@CompositionObject@Composition@UI@Windows@@UEAAPEAVCompositionPropertySet@234@_N@Z; Windows::UI::Composition::CompositionObject::GetProperties(bool)
0x18004457b  mov     edx, 2
0x180044580  mov     rcx, rbx
0x180044583  mov     rdi, rax
0x180044586  mov     r8d, [rax+90h]
0x18004458d  call    ?SetReferenceProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@I@Z; Windows::UI::Composition::ProxyObject::SetReferenceProperty(DCOMPOSITION_PROPERTY_ID,uint)
0x180044592  xor     edx, edx; Val
0x180044594  lea     rcx, [rbp+57h+var_80]; void *
0x180044598  lea     r8d, [rdx+40h]; Size
0x18004459c  call    memset_0
0x1800445a1  mov     rcx, [r14]
0x1800445a4  mov     rax, [rcx+10h]
0x1800445a8  mov     rcx, r14
0x1800445ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445b0  mov     r15d, eax
0x1800445b3  xor     esi, esi
0x1800445b5  cmp     esi, r15d
0x1800445b8  jb      short loc_1800445D8
0x1800445ba  xor     eax, eax
0x1800445bc  mov     rcx, [rbp+57h+var_40]
0x1800445c0  xor     rcx, rsp; StackCookie
0x1800445c3  call    __security_check_cookie
0x1800445c8  add     rsp, 0A8h
0x1800445cf  pop     r15
0x1800445d1  pop     r14
0x1800445d3  pop     rdi
0x1800445d4  pop     rsi
0x1800445d5  pop     rbx
0x1800445d6  pop     rbp
0x1800445d7  retn
0x1800445d8  mov     rcx, [r14]
0x1800445db  mov     [rbp+57h+string], 0
0x1800445e3  mov     [rbp+57h+var_98], 0
0x1800445ea  mov     rbx, [rcx+88h]
0x1800445f1  xor     ecx, ecx; string
0x1800445f3  call    cs:__imp_WindowsDeleteString
0x1800445f9  lea     rax, [rbp+57h+var_80]
0x1800445fd  mov     [rbp+57h+string], 0
0x180044605  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18004460a  lea     r9, [rbp+57h+var_98]
0x18004460e  mov     rax, rbx
0x180044611  lea     r8, [rbp+57h+string]
0x180044615  mov     edx, esi
0x180044617  mov     rcx, r14
0x18004461a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004461f  mov     ecx, [rbp+57h+var_98]
0x180044622  sub     ecx, 12h
0x180044625  jnz     short loc_180044660
0x180044627  movss   xmm0, [rbp+57h+var_80]
0x18004462c  lea     rax, [rbp+57h+var_90]
0x180044630  mov     rdx, [rbp+57h+string]
0x180044634  mov     r9b, 1
0x180044637  mov     rcx, rdi
0x18004463a  movss   [rbp+57h+var_90], xmm0
0x18004463f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180044644  call    ??$InsertProperty@UPropertySetScalarValue@@M@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBM@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetScalarValue,float>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,float const *)
0x180044649  mov     ebx, eax
0x18004464b  test    eax, eax
0x18004464d  js      short loc_1800446C7
0x18004464f  mov     rcx, [rbp+57h+string]; string
0x180044653  call    cs:__imp_WindowsDeleteString
0x180044659  inc     esi
0x18004465b  jmp     loc_1800445B5
0x180044660  sub     ecx, 11h
0x180044663  jz      loc_180044764
0x180044669  sub     ecx, 11h
0x18004466c  jz      loc_180044738
0x180044672  sub     ecx, 11h
0x180044675  jz      loc_18004470C
0x18004467b  sub     ecx, 1
0x18004467e  jnz     short loc_1800446CE
0x180044680  mov     rdx, [rbp+57h+string]
0x180044684  lea     rax, [rbp+57h+var_80]
0x180044688  mov     r9b, 1
0x18004468b  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180044690  mov     rcx, rdi
0x180044693  call    ??$InsertProperty@UPropertySetColorValue@@U_D3DCOLORVALUE@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBU_D3DCOLORVALUE@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetColorValue,_D3DCOLORVALUE>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,_D3DCOLORVALUE const *)
0x180044698  mov     ebx, eax
0x18004469a  test    eax, eax
0x18004469c  jns     short loc_18004464F
0x18004469e  mov     edx, 1B2h; void *
0x1800446a3  mov     r9d, eax; char *
0x1800446a6  mov     rcx, [rbp+5Fh]; this
0x1800446aa  lea     r8, aOnecoreuapWind_25; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800446b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800446b6  mov     rcx, [rbp+57h+string]; string
0x1800446ba  call    cs:__imp_WindowsDeleteString
0x1800446c0  mov     eax, ebx
0x1800446c2  jmp     loc_1800445BC
0x1800446c7  mov     edx, 192h
0x1800446cc  jmp     short loc_1800446A3
0x1800446ce  sub     ecx, 22h ; '"'
0x1800446d1  jz      loc_18017DC16
0x1800446d7  cmp     ecx, 0A1h
0x1800446dd  jnz     loc_18017DC42
0x1800446e3  mov     rdx, [rbp+57h+string]
0x1800446e7  lea     rax, [rbp+57h+var_80]
0x1800446eb  mov     r9b, 1
0x1800446ee  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800446f3  mov     rcx, rdi
0x1800446f6  call    ??$InsertProperty@UPropertySetMatrix4x4Value@@UD2DMatrix@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBUD2DMatrix@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetMatrix4x4Value,D2DMatrix>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,D2DMatrix const *)
0x1800446fb  mov     ebx, eax
0x1800446fd  test    eax, eax
0x1800446ff  jns     loc_18004464F
0x180044705  mov     edx, 1C2h
0x18004470a  jmp     short loc_1800446A3
0x18004470c  mov     rdx, [rbp+57h+string]
0x180044710  lea     rax, [rbp+57h+var_80]
0x180044714  mov     r9b, 1
0x180044717  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18004471c  mov     rcx, rdi
0x18004471f  call    ??$InsertProperty@UPropertySetVector4Value@@UD2DVector4@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBUD2DVector4@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector4Value,D2DVector4>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,D2DVector4 const *)
0x180044724  mov     ebx, eax
0x180044726  test    eax, eax
0x180044728  jns     loc_18004464F
0x18004472e  mov     edx, 1AAh
0x180044733  jmp     loc_1800446A3
0x180044738  mov     rdx, [rbp+57h+string]
0x18004473c  lea     rax, [rbp+57h+var_80]
0x180044740  mov     r9b, 1
0x180044743  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180044748  mov     rcx, rdi
0x18004474b  call    ??$InsertProperty@UPropertySetVector3Value@@UD2DVector3@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBUD2DVector3@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector3Value,D2DVector3>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,D2DVector3 const *)
0x180044750  mov     ebx, eax
0x180044752  test    eax, eax
0x180044754  jns     loc_18004464F
0x18004475a  mov     edx, 1A2h
0x18004475f  jmp     loc_1800446A3
0x180044764  mov     rdx, [rbp+57h+string]
0x180044768  lea     rax, [rbp+57h+var_80]
0x18004476c  mov     r9b, 1
0x18004476f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180044774  mov     rcx, rdi
0x180044777  call    ??$InsertProperty@UPropertySetVector2Value@@UD2DVector2@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBUD2DVector2@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetVector2Value,D2DVector2>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,D2DVector2 const *)
0x18004477c  mov     ebx, eax
0x18004477e  test    eax, eax
0x180044780  jns     loc_18004464F
0x180044786  mov     edx, 19Ah
0x18004478b  jmp     loc_1800446A3
0x18017dc16  mov     rdx, [rbp+57h+string]
0x18017dc1a  lea     rax, [rbp+57h+var_80]
0x18017dc1e  mov     r9b, 1
0x18017dc21  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18017dc26  mov     rcx, rdi
0x18017dc29  call    ??$InsertProperty@UPropertySetMatrix3x2Value@@UD2D_MATRIX_3X2_F@@@CompositionPropertySet@Composition@UI@Windows@@AEAAJPEAUHSTRING__@@W4DCOMPOSITION_EXPRESSION_TYPE@@_NPEBUD2D_MATRIX_3X2_F@@@Z; Windows::UI::Composition::CompositionPropertySet::InsertProperty<PropertySetMatrix3x2Value,D2D_MATRIX_3X2_F>(HSTRING__ *,DCOMPOSITION_EXPRESSION_TYPE,bool,D2D_MATRIX_3X2_F const *)
0x18017dc2e  mov     ebx, eax
0x18017dc30  test    eax, eax
0x18017dc32  jns     loc_18004464F
0x18017dc38  mov     edx, 1BAh
0x18017dc3d  jmp     loc_1800446A3
0x18017dc42  mov     ebx, 80004001h
0x18017dc47  mov     edx, 1C8h
0x18017dc4c  mov     r9d, ebx
0x18017dc4f  jmp     loc_1800446A6
```

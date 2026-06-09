# Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(HSTRING__ *,Windows::UI::Composition::CompositionObject *,Windows::UI::Composition::CompositionAnimation *,Windows::UI::Composition::AnimationValueData const *,bool *)

- ea: `0x1800755d8`
- end: `0x1800758bb`
- name: `?SetFinalValueParameter@AnimationHelper@Composition@UI@Windows@@YAJPEAUHSTRING__@@PEAVCompositionObject@234@PEAVCompositionAnimation@234@PEBUAnimationValueData@234@PEA_N@Z`
- size: `739`
- prototype: `__int64 __fastcall(Windows::UI::Composition::AnimationHelper *__hidden this, HSTRING, struct Windows::UI::Composition::CompositionObject *, struct Windows::UI::Composition::CompositionAnimation *, const struct Windows::UI::Composition::AnimationValueData *, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180072668`
- `0x180074ab8`

## callees

- `0x18001358c`
- `0x1800755d8`
- `0x1800758c4`
- `0x180076060`
- `0x180079448`
- `0x18009a3e0`
- `0x1800c7290`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x18013eda4`
- `0x18013f040`
- `0x18013f170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075679`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800756d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075679`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800756d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800756ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800756ba`

## string_xrefs

- `0x180075723`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtanimationhelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::AnimationHelper::SetFinalValueParameter(
        Windows::UI::Composition::AnimationHelper *this,
        HSTRING a2,
        struct Windows::UI::Composition::CompositionObject *a3,
        const __m128i *a4,
        const struct Windows::UI::Composition::AnimationValueData *a5)
{
  int v7; // ecx
  HRESULT v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  float v12; // xmm6_4
  HRESULT v13; // eax
  int v14; // ebx
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // ecx
  __m128i v19; // xmm6
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  HSTRING_HEADER v22; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_BYTE *)a5 = 0;
  if ( !a2 )
  {
    v16 = 32;
LABEL_29:
    v14 = -2147024809;
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v16 = 33;
    goto LABEL_29;
  }
  if ( !a4 )
  {
    v16 = 34;
    goto LABEL_29;
  }
  if ( !(unsigned __int8)AreAnimationNamesEqual<HSTRING__ *,HSTRING__ *>(a4[1].m128i_i64[1], this) )
    return 0;
  v7 = a4[6].m128i_i32[0];
  if ( v7 > 52 )
  {
    v17 = v7 - 69;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 1 )
          goto LABEL_20;
        string = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"this.FinalValue", 0x10u, 0xFu);
        v14 = Windows::UI::Composition::CompositionAnimation::SetQuaternionParameter(
                a3,
                string,
                (const struct Windows::Foundation::Numerics::Quaternion *)&a4[2]);
        if ( v14 < 0 )
        {
          v16 = 80;
          goto LABEL_18;
        }
      }
      else
      {
        v19 = _mm_loadu_si128(a4 + 2);
        v23 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v22, L"this.FinalValue", 0x10u, 0xFu);
        *(__m128i *)&hstringHeader.Reserved.Reserved1 = v19;
        v14 = Windows::UI::Composition::CompositionAnimation::SetColorParameter(
                a3,
                v23,
                (struct _D3DCOLORVALUE *)&hstringHeader);
        if ( v14 < 0 )
        {
          v16 = 74;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v23 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v22, L"this.FinalValue", 0x10u, 0xFu);
      v14 = Windows::UI::Composition::CompositionAnimation::SetVector4Parameter(
              a3,
              v23,
              (const struct Windows::Foundation::Numerics::Vector4 *)&a4[2]);
      if ( v14 < 0 )
      {
        v16 = 68;
        goto LABEL_18;
      }
    }
    goto LABEL_15;
  }
  if ( v7 != 52 )
  {
    v9 = v7 - 11;
    if ( !v9 )
      goto LABEL_20;
    v10 = v9 - 6;
    if ( !v10 )
      goto LABEL_20;
    v11 = v10 - 1;
    if ( !v11 )
    {
      v12 = *(float *)a4[2].m128i_i32;
      string = 0;
      v13 = WindowsCreateStringReference(L"this.FinalValue", 0xFu, &hstringHeader, &string);
      if ( v13 < 0 )
      {
        RaiseException(v13, 1u, 0, 0);
        __debugbreak();
      }
      v14 = Windows::UI::Composition::CompositionAnimation::SetScalarParameter(a3, string, v12);
      if ( v14 >= 0 )
        goto LABEL_15;
      v16 = 50;
      goto LABEL_18;
    }
    if ( v11 != 17 )
LABEL_20:
      Microsoft::WRL2::FailFast::Unexpected(0);
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"this.FinalValue", 0x10u, 0xFu);
    v14 = Windows::UI::Composition::CompositionAnimation::SetVector2Parameter(
            a3,
            string,
            (const struct Windows::Foundation::Numerics::Vector2 *)&a4[2]);
    if ( v14 < 0 )
    {
      v16 = 56;
      goto LABEL_18;
    }
LABEL_15:
    *(_BYTE *)a5 = 1;
    return 0;
  }
  string = 0;
  v8 = WindowsCreateStringReference(L"this.FinalValue", 0xFu, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v14 = Windows::UI::Composition::CompositionAnimation::SetVector3Parameter(
          a3,
          string,
          (const struct Windows::Foundation::Numerics::Vector3 *)&a4[2]);
  if ( v14 >= 0 )
    goto LABEL_15;
  v16 = 62;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtanimationhelper.cpp",
    (const char *)(unsigned int)v14,
    (int)hstringHeader.Reserved.Reserved1);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800755d8  mov     [rsp-18h+arg_8], rbx
0x1800755dd  push    rbp
0x1800755de  push    rsi
0x1800755df  push    rdi
0x1800755e0  mov     rbp, rsp
0x1800755e3  sub     rsp, 80h
0x1800755ea  movaps  [rsp+80h+var_10], xmm6
0x1800755ef  mov     rax, cs:__security_cookie
0x1800755f6  xor     rax, rsp
0x1800755f9  mov     [rbp+var_20], rax
0x1800755fd  mov     rsi, [rbp+arg_20]
0x180075601  mov     rbx, r9
0x180075604  mov     rdi, r8
0x180075607  mov     byte ptr [rsi], 0
0x18007560a  test    rdx, rdx
0x18007560d  jz      loc_1800757C2
0x180075613  test    r8, r8
0x180075616  jz      loc_1800757D1
0x18007561c  test    rbx, rbx
0x18007561f  jz      loc_1800757D8
0x180075625  mov     rdx, rcx
0x180075628  mov     rcx, [r9+18h]
0x18007562c  call    ??$AreAnimationNamesEqual@PEAUHSTRING__@@PEAU1@@@YA_NPEAUHSTRING__@@0@Z; AreAnimationNamesEqual<HSTRING__ *,HSTRING__ *>(HSTRING__ *,HSTRING__ *)
0x180075631  test    al, al
0x180075633  jz      loc_1800756F4
0x180075639  mov     ecx, [rbx+60h]
0x18007563c  cmp     ecx, 34h ; '4'
0x18007563f  jg      loc_180075747
0x180075645  jnz     short loc_180075680
0x180075647  lea     r9, [rbp+string]; string
0x18007564b  mov     [rbp+string], 0
0x180075653  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180075657  mov     edx, 0Fh; length
0x18007565c  lea     rcx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x180075663  call    cs:__imp_WindowsCreateStringReference
0x180075669  test    eax, eax
0x18007566b  jns     short loc_1800756DB
0x18007566d  xor     r9d, r9d; lpArguments
0x180075670  xor     r8d, r8d; nNumberOfArguments
0x180075673  mov     ecx, eax; dwExceptionCode
0x180075675  lea     edx, [r9+1]; dwExceptionFlags
0x180075679  call    cs:__imp_RaiseException
0x18007567f  int     3; Trap to Debugger
0x180075680  sub     ecx, 0Bh
0x180075683  jz      loc_18007573F
0x180075689  sub     ecx, 6
0x18007568c  jz      loc_18007573F
0x180075692  sub     ecx, 1
0x180075695  jnz     loc_180075736
0x18007569b  movss   xmm6, dword ptr [rbx+20h]
0x1800756a0  lea     edx, [rcx+0Fh]; length
0x1800756a3  lea     rcx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x1800756aa  mov     [rbp+string], 0
0x1800756b2  lea     r9, [rbp+string]; string
0x1800756b6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800756ba  call    cs:__imp_WindowsCreateStringReference
0x1800756c0  test    eax, eax
0x1800756c2  jns     loc_18007579F
0x1800756c8  xor     r9d, r9d; lpArguments
0x1800756cb  xor     r8d, r8d; nNumberOfArguments
0x1800756ce  mov     ecx, eax; dwExceptionCode
0x1800756d0  lea     edx, [r9+1]; dwExceptionFlags
0x1800756d4  call    cs:__imp_RaiseException
0x1800756da  int     3; Trap to Debugger
0x1800756db  mov     rdx, [rbp+string]; HSTRING
0x1800756df  lea     r8, [rbx+20h]; struct Windows::Foundation::Numerics::Vector3 *
0x1800756e3  mov     rcx, rdi; this
0x1800756e6  call    ?SetVector3Parameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@AEBUVector3@Numerics@Foundation@4@@Z; Windows::UI::Composition::CompositionAnimation::SetVector3Parameter(HSTRING__ *,Windows::Foundation::Numerics::Vector3 const &)
0x1800756eb  mov     ebx, eax
0x1800756ed  test    eax, eax
0x1800756ef  js      short loc_18007571A
0x1800756f1  mov     byte ptr [rsi], 1
0x1800756f4  xor     eax, eax
0x1800756f6  mov     rcx, [rbp+var_20]
0x1800756fa  xor     rcx, rsp; StackCookie
0x1800756fd  call    __security_check_cookie
0x180075702  mov     rbx, [rsp+80h+arg_8]
0x18007570a  movaps  xmm6, [rsp+80h+var_10]
0x18007570f  add     rsp, 80h
0x180075716  pop     rdi
0x180075717  pop     rsi
0x180075718  pop     rbp
0x180075719  retn
0x18007571a  mov     edx, 3Eh ; '>'; void *
0x18007571f  mov     rcx, [rbp+18h]; this
0x180075723  lea     r8, aOnecoreuapWind_275; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18007572a  mov     r9d, ebx; char *
0x18007572d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075732  mov     eax, ebx
0x180075734  jmp     short loc_1800756F6
0x180075736  cmp     ecx, 11h
0x180075739  jz      loc_1800757DF
0x18007573f  xor     ecx, ecx; char *
0x180075741  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180075747  sub     ecx, 45h ; 'E'
0x18007574a  jz      loc_180075875
0x180075750  sub     ecx, 1
0x180075753  jz      loc_180075825
0x180075759  sub     ecx, 1
0x18007575c  jnz     short loc_18007573F
0x18007575e  lea     r9d, [rcx+0Fh]; unsigned int
0x180075762  mov     [rbp+string], 0
0x18007576a  lea     r8d, [rcx+10h]; unsigned int
0x18007576e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180075772  lea     rdx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x180075779  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007577e  mov     rdx, [rbp+string]; HSTRING
0x180075782  lea     r8, [rbx+20h]; struct Windows::Foundation::Numerics::Quaternion *
0x180075786  mov     rcx, rdi; this
0x180075789  call    ?SetQuaternionParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@AEBUQuaternion@Numerics@Foundation@4@@Z; Windows::UI::Composition::CompositionAnimation::SetQuaternionParameter(HSTRING__ *,Windows::Foundation::Numerics::Quaternion const &)
0x18007578e  mov     ebx, eax
0x180075790  test    eax, eax
0x180075792  jns     loc_1800756F1
0x180075798  mov     edx, 50h ; 'P'
0x18007579d  jmp     short loc_18007571F
0x18007579f  mov     rdx, [rbp+string]; HSTRING
0x1800757a3  movaps  xmm2, xmm6; float
0x1800757a6  mov     rcx, rdi; this
0x1800757a9  call    ?SetScalarParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@M@Z; Windows::UI::Composition::CompositionAnimation::SetScalarParameter(HSTRING__ *,float)
0x1800757ae  mov     ebx, eax
0x1800757b0  test    eax, eax
0x1800757b2  jns     loc_1800756F1
0x1800757b8  mov     edx, 32h ; '2'
0x1800757bd  jmp     loc_18007571F
0x1800757c2  mov     edx, 20h ; ' '
0x1800757c7  mov     ebx, 80070057h
0x1800757cc  jmp     loc_18007571F
0x1800757d1  mov     edx, 21h ; '!'
0x1800757d6  jmp     short loc_1800757C7
0x1800757d8  mov     edx, 22h ; '"'
0x1800757dd  jmp     short loc_1800757C7
0x1800757df  mov     r9d, 0Fh; unsigned int
0x1800757e5  mov     [rbp+string], 0
0x1800757ed  lea     rdx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x1800757f4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800757f8  lea     r8d, [r9+1]; unsigned int
0x1800757fc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180075801  mov     rdx, [rbp+string]; HSTRING
0x180075805  lea     r8, [rbx+20h]; struct Windows::Foundation::Numerics::Vector2 *
0x180075809  mov     rcx, rdi; this
0x18007580c  call    ?SetVector2Parameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@AEBUVector2@Numerics@Foundation@4@@Z; Windows::UI::Composition::CompositionAnimation::SetVector2Parameter(HSTRING__ *,Windows::Foundation::Numerics::Vector2 const &)
0x180075811  mov     ebx, eax
0x180075813  test    eax, eax
0x180075815  jns     loc_1800756F1
0x18007581b  mov     edx, 38h ; '8'
0x180075820  jmp     loc_18007571F
0x180075825  movdqu  xmm6, xmmword ptr [rbx+20h]
0x18007582a  mov     r9d, 0Fh; unsigned int
0x180075830  mov     [rbp+var_28], 0
0x180075838  lea     rdx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x18007583f  lea     rcx, [rbp+var_40]; hstringHeader
0x180075843  lea     r8d, [r9+1]; unsigned int
0x180075847  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007584c  mov     rdx, [rbp+var_28]; HSTRING
0x180075850  lea     r8, [rbp+hstringHeader]; struct _D3DCOLORVALUE
0x180075854  mov     rcx, rdi; this
0x180075857  movdqa  xmmword ptr [rbp+hstringHeader.Reserved], xmm6
0x18007585c  call    ?SetColorParameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@U_D3DCOLORVALUE@@@Z; Windows::UI::Composition::CompositionAnimation::SetColorParameter(HSTRING__ *,_D3DCOLORVALUE)
0x180075861  mov     ebx, eax
0x180075863  test    eax, eax
0x180075865  jns     loc_1800756F1
0x18007586b  mov     edx, 4Ah ; 'J'
0x180075870  jmp     loc_18007571F
0x180075875  mov     r9d, 0Fh; unsigned int
0x18007587b  mov     [rbp+var_28], 0
0x180075883  lea     rdx, ?c_relativeToFinal@Composition@UI@Windows@@3QBGB; "this.FinalValue"
0x18007588a  lea     rcx, [rbp+var_40]; hstringHeader
0x18007588e  lea     r8d, [r9+1]; unsigned int
0x180075892  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180075897  mov     rdx, [rbp+var_28]; HSTRING
0x18007589b  lea     r8, [rbx+20h]; struct Windows::Foundation::Numerics::Vector4 *
0x18007589f  mov     rcx, rdi; this
0x1800758a2  call    ?SetVector4Parameter@CompositionAnimation@Composition@UI@Windows@@QEAAJPEAUHSTRING__@@AEBUVector4@Numerics@Foundation@4@@Z; Windows::UI::Composition::CompositionAnimation::SetVector4Parameter(HSTRING__ *,Windows::Foundation::Numerics::Vector4 const &)
0x1800758a7  mov     ebx, eax
0x1800758a9  test    eax, eax
0x1800758ab  jns     loc_1800756F1
0x1800758b1  mov     edx, 44h ; 'D'
0x1800758b6  jmp     loc_18007571F
```

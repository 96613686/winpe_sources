# ColorTemperatureEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801ea2f0`
- end: `0x1801ea7af`
- name: `?OnPropertyChanged@ColorTemperatureEffect@@UEAAJPEB_W@Z`
- size: `1215`
- prototype: `__int64 __fastcall(ColorTemperatureEffect *__hidden this, PCNZWCH lpString1)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1801e9f74`
- `0x1801ea2f0`
- `0x1804444f0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801ea35d`
- `KERNEL32!CompareStringW` at `0x1801ea388`
- `KERNEL32!CompareStringW` at `0x1801ea3b3`
- `KERNEL32!CompareStringW` at `0x1801ea3de`
- `KERNEL32!CompareStringW` at `0x1801ea409`
- `KERNEL32!CompareStringW` at `0x1801ea504`
- `KERNEL32!CompareStringW` at `0x1801ea35d`
- `KERNEL32!CompareStringW` at `0x1801ea388`
- `KERNEL32!CompareStringW` at `0x1801ea3b3`
- `KERNEL32!CompareStringW` at `0x1801ea3de`
- `KERNEL32!CompareStringW` at `0x1801ea409`
- `KERNEL32!CompareStringW` at `0x1801ea504`
- `OLEAUT32!__imp_VariantInit` at `0x1801ea42c`
- `OLEAUT32!__imp_VariantInit` at `0x1801ea42c`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea4b3`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea617`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea70b`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea4b3`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea617`
- `OLEAUT32!__imp_VariantClear` at `0x1801ea70b`

## string_xrefs

- `0x1801ea33c`: `SceneTemperature`
- `0x1801ea370`: `CameraSettingsTemperature`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ColorTemperatureEffect::OnPropertyChanged(ColorTemperatureEffect *this, PCNZWCH lpString1)
{
  int v4; // r13d
  int v5; // eax
  int v6; // eax
  __int64 result; // rax
  struct IAutoEffect *v8; // rdx
  int v9; // eax
  __int64 (__fastcall *v10)(__int64 *, wchar_t *, VARIANTARG *); // r9
  LONGLONG v11; // xmm0_8
  int v12; // edi
  int v13; // eax
  __int64 v14; // rax
  LONGLONG v15; // xmm0_8
  int v16; // edi
  int v17; // [rsp+30h] [rbp-78h] BYREF
  _DWORD v18[4]; // [rsp+38h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-60h] BYREF
  VARIANTARG v20[3]; // [rsp+60h] [rbp-48h] BYREF
  __int64 *v21; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+18h]
  unsigned __int64 v23; // [rsp+C8h] [rbp+20h]

  try
  {
    v4 = 0;
    if ( !lpString1 )
      ATL::BaseAtlThrow(-2147467261);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
    if ( v5 < 0 )
      ATL::BaseAtlThrow(v5);
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"SceneTemperature", -1) == 2
      || CompareStringW(0x7Fu, 1u, lpString1, -1, L"CameraSettingsTemperature", -1) == 2
      || CompareStringW(0x7Fu, 1u, lpString1, -1, L"SceneTint", -1) == 2
      || CompareStringW(0x7Fu, 1u, lpString1, -1, L"CameraSettingsTint", -1) == 2 )
    {
      ColorTemperatureEffect::CalculateWhitePoints(this);
      while ( v4 < 3 )
      {
        v21 = 0;
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 19) + 56LL))(
               *((_QWORD *)this + 19),
               &v21);
        if ( v9 < 0 )
          ATL::BaseAtlThrow(v9);
        if ( !v21 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
        v10 = *(__int64 (__fastcall **)(__int64 *, wchar_t *, VARIANTARG *))(*v21 + 104);
        v22 = v4;
        v11 = *((_QWORD *)this + 2 * v4 + 22);
        pvarg.vt = 5;
        pvarg.llVal = v11;
        v23 = 8LL * v4;
        v20[0] = pvarg;
        v12 = v10(v21, off_1805FCC70[v23 / 8], v20);
        VariantClear(&pvarg);
        if ( v12 == -2147024882 || v12 == -2045378032 || v12 == -2045312765 || v12 == -2045247216 )
          ATL::BaseAtlThrow(v12);
        if ( v12 < 0 )
          ATL::BaseAtlThrow(v12);
        v21 = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 19) + 56LL))(
                *((_QWORD *)this + 19),
                &v21);
        if ( v13 < 0 )
          ATL::BaseAtlThrow(v13);
        if ( !v21 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
        v14 = *v21;
        v15 = *((_QWORD *)this + 2 * v22 + 23);
        pvarg.vt = 5;
        pvarg.llVal = v15;
        v20[0] = pvarg;
        v16 = (*(__int64 (__fastcall **)(__int64 *, wchar_t *, VARIANTARG *))(v14 + 104))(
                v21,
                off_1805FCC50[v23 / 8],
                v20);
        VariantClear(&pvarg);
        if ( v16 == -2147024882 || v16 == -2045378032 || v16 == -2045312765 || v16 == -2045247216 )
          ATL::BaseAtlThrow(v16);
        if ( v16 < 0 )
          ATL::BaseAtlThrow(v16);
        ++v4;
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"WorkingColorSpaceProfile", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v6 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             L"WorkingColorSpaceProfile",
             &pvarg);
      if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
        ATL::BaseAtlThrow(v6);
      if ( v6 < 0 )
        ATL::BaseAtlThrow(v6);
      if ( pvarg.vt && pvarg.vt != 8 && pvarg.vt != 8209 )
        ATL::BaseAtlThrow(-2045181696);
      VariantClear(&pvarg);
    }
    else if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"_AutoFix", -1) == 2 )
    {
      EffectUtils::AutoFix((EffectUtils *)(((unsigned __int64)this + 160) & -(__int64)(this != 0)), v8);
    }
    result = 0;
  }
  catch ( Base::Exception v18 )
  {
    LODWORD(v21) = v18[2];
    goto LABEL_19;
  }
  catch ( long v17 )
  {
    LODWORD(v21) = v17;
LABEL_19:
    result = (unsigned int)v21;
    if ( (_WORD)v21 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801ea2f0  mov     [rsp+arg_0], rbx
0x1801ea2f5  push    rsi
0x1801ea2f6  push    rdi
0x1801ea2f7  push    r12
0x1801ea2f9  push    r13
0x1801ea2fb  push    r14
0x1801ea2fd  sub     rsp, 80h
0x1801ea304  mov     rdi, rdx
0x1801ea307  mov     rbx, rcx
0x1801ea30a  xor     r13d, r13d
0x1801ea30d  test    rdx, rdx
0x1801ea310  jz      loc_1801EA742
0x1801ea316  mov     rcx, [rcx+80h]
0x1801ea31d  mov     rax, [rcx]
0x1801ea320  mov     rax, [rax+110h]
0x1801ea327  call    cs:__guard_dispatch_icall_fptr
0x1801ea32d  test    eax, eax
0x1801ea32f  js      loc_1801EA74C
0x1801ea335  or      esi, 0FFFFFFFFh
0x1801ea338  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea33c  lea     rax, aScenetemperatu; "SceneTemperature"
0x1801ea343  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea348  mov     r9d, esi; cchCount1
0x1801ea34b  mov     r8, rdi; lpString1
0x1801ea34e  lea     r12d, [rsi+2]
0x1801ea352  mov     edx, r12d; dwCmpFlags
0x1801ea355  lea     r14d, [r12+7Eh]
0x1801ea35a  mov     ecx, r14d; Locale
0x1801ea35d  call    cs:__imp_CompareStringW
0x1801ea363  cmp     eax, 2
0x1801ea366  jz      loc_1801EA526
0x1801ea36c  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea370  lea     rax, aCamerasettings_0; "CameraSettingsTemperature"
0x1801ea377  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea37c  mov     r9d, esi; cchCount1
0x1801ea37f  mov     r8, rdi; lpString1
0x1801ea382  mov     edx, r12d; dwCmpFlags
0x1801ea385  mov     ecx, r14d; Locale
0x1801ea388  call    cs:__imp_CompareStringW
0x1801ea38e  cmp     eax, 2
0x1801ea391  jz      loc_1801EA526
0x1801ea397  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea39b  lea     rax, aScenetint; "SceneTint"
0x1801ea3a2  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea3a7  mov     r9d, esi; cchCount1
0x1801ea3aa  mov     r8, rdi; lpString1
0x1801ea3ad  mov     edx, r12d; dwCmpFlags
0x1801ea3b0  mov     ecx, r14d; Locale
0x1801ea3b3  call    cs:__imp_CompareStringW
0x1801ea3b9  cmp     eax, 2
0x1801ea3bc  jz      loc_1801EA526
0x1801ea3c2  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea3c6  lea     rax, aCamerasettings; "CameraSettingsTint"
0x1801ea3cd  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea3d2  mov     r9d, esi; cchCount1
0x1801ea3d5  mov     r8, rdi; lpString1
0x1801ea3d8  mov     edx, r12d; dwCmpFlags
0x1801ea3db  mov     ecx, r14d; Locale
0x1801ea3de  call    cs:__imp_CompareStringW
0x1801ea3e4  cmp     eax, 2
0x1801ea3e7  jz      loc_1801EA526
0x1801ea3ed  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea3f1  lea     rax, aWorkingcolorsp; "WorkingColorSpaceProfile"
0x1801ea3f8  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea3fd  mov     r9d, esi; cchCount1
0x1801ea400  mov     r8, rdi; lpString1
0x1801ea403  mov     edx, r12d; dwCmpFlags
0x1801ea406  mov     ecx, r14d; Locale
0x1801ea409  call    cs:__imp_CompareStringW
0x1801ea40f  cmp     eax, 2
0x1801ea412  jnz     loc_1801EA4E8
0x1801ea418  xorps   xmm0, xmm0
0x1801ea41b  xor     eax, eax
0x1801ea41d  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1801ea422  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1801ea427  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801ea42c  call    cs:__imp_VariantInit
0x1801ea432  mov     rcx, [rbx+80h]
0x1801ea439  mov     rax, [rcx]
0x1801ea43c  lea     r8, [rsp+0A8h+pvarg]
0x1801ea441  lea     rdx, aWorkingcolorsp; "WorkingColorSpaceProfile"
0x1801ea448  mov     rax, [rax+60h]
0x1801ea44c  call    cs:__guard_dispatch_icall_fptr
0x1801ea452  mov     r12d, 8007000Eh
0x1801ea458  cmp     eax, r12d
0x1801ea45b  jz      loc_1801EA76A
0x1801ea461  mov     esi, 86160210h
0x1801ea466  cmp     eax, esi
0x1801ea468  jz      loc_1801EA76A
0x1801ea46e  mov     r14d, 86170103h
0x1801ea474  cmp     eax, r14d
0x1801ea477  jz      loc_1801EA76A
0x1801ea47d  cmp     eax, 86180110h
0x1801ea482  jz      loc_1801EA76A
0x1801ea488  test    eax, eax
0x1801ea48a  js      loc_1801EA759
0x1801ea490  movzx   eax, word ptr [rsp+0A8h+pvarg]
0x1801ea495  test    ax, ax
0x1801ea498  jz      short loc_1801EA4AE
0x1801ea49a  cmp     ax, 8
0x1801ea49e  jz      short loc_1801EA4AE
0x1801ea4a0  mov     ecx, 2011h
0x1801ea4a5  cmp     ax, cx
0x1801ea4a8  jnz     loc_1801EA760
0x1801ea4ae  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801ea4b3  call    cs:__imp_VariantClear
0x1801ea4b9  xor     eax, eax
0x1801ea4bb  jmp     short loc_1801EA4D0
0x1801ea4bd  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x1801ea4c4  mov     edx, 86160101h
0x1801ea4c9  cmp     ax, 216h
0x1801ea4cd  cmovz   eax, edx
0x1801ea4d0  mov     rbx, [rsp+0A8h+arg_0]
0x1801ea4d8  add     rsp, 80h
0x1801ea4df  pop     r14
0x1801ea4e1  pop     r13
0x1801ea4e3  pop     r12
0x1801ea4e5  pop     rdi
0x1801ea4e6  pop     rsi
0x1801ea4e7  retn
0x1801ea4e8  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801ea4ec  lea     rax, aAutofix; "_AutoFix"
0x1801ea4f3  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801ea4f8  mov     r9d, esi; cchCount1
0x1801ea4fb  mov     r8, rdi; lpString1
0x1801ea4fe  mov     edx, r12d; dwCmpFlags
0x1801ea501  mov     ecx, r14d; Locale
0x1801ea504  call    cs:__imp_CompareStringW
0x1801ea50a  cmp     eax, 2
0x1801ea50d  jnz     short loc_1801EA4B9
0x1801ea50f  lea     rax, [rbx+0A0h]
0x1801ea516  neg     rbx
0x1801ea519  sbb     rcx, rcx
0x1801ea51c  and     rcx, rax; this
0x1801ea51f  call    ?AutoFix@EffectUtils@@YAXPEAUIAutoEffect@@@Z; EffectUtils::AutoFix(IAutoEffect *)
0x1801ea524  jmp     short loc_1801EA4B9
0x1801ea526  mov     rcx, rbx; this
0x1801ea529  call    ?CalculateWhitePoints@ColorTemperatureEffect@@AEAAXXZ; ColorTemperatureEffect::CalculateWhitePoints(void)
0x1801ea52e  mov     esi, 86160210h
0x1801ea533  mov     r12d, 8007000Eh
0x1801ea539  mov     r14d, 86170103h
0x1801ea53f  mov     edi, 5
0x1801ea544  cmp     r13d, 3
0x1801ea548  jge     loc_1801EA4B9
0x1801ea54e  mov     [rsp+0A8h+arg_8], 0
0x1801ea55a  mov     rcx, [rbx+98h]
0x1801ea561  mov     rax, [rcx]
0x1801ea564  lea     rdx, [rsp+0A8h+arg_8]
0x1801ea56c  mov     rax, [rax+38h]
0x1801ea570  call    cs:__guard_dispatch_icall_fptr
0x1801ea576  test    eax, eax
0x1801ea578  js      loc_1801EA775
0x1801ea57e  mov     rcx, [rsp+0A8h+arg_8]
0x1801ea586  test    rcx, rcx
0x1801ea589  jz      loc_1801EA77C
0x1801ea58f  mov     rax, [rcx]
0x1801ea592  mov     rax, [rax+10h]
0x1801ea596  call    cs:__guard_dispatch_icall_fptr
0x1801ea59c  mov     rcx, [rsp+0A8h+arg_8]
0x1801ea5a4  mov     rax, [rcx]
0x1801ea5a7  mov     r9, [rax+68h]
0x1801ea5ab  movsxd  rdx, r13d
0x1801ea5ae  mov     [rsp+0A8h+arg_10], rdx
0x1801ea5b6  lea     rax, [rdx+0Bh]
0x1801ea5ba  add     rax, rax
0x1801ea5bd  movsd   xmm0, qword ptr [rbx+rax*8]
0x1801ea5c2  mov     word ptr [rsp+0A8h+pvarg], di
0x1801ea5c7  movsd   qword ptr [rsp+0A8h+pvarg+8], xmm0
0x1801ea5cd  lea     rax, ds:0[rdx*8]
0x1801ea5d5  mov     [rsp+0A8h+arg_18], rax
0x1801ea5dd  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x1801ea5e2  movaps  [rsp+0A8h+var_48], xmm0
0x1801ea5e7  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x1801ea5ed  movsd   [rsp+0A8h+var_38], xmm1
0x1801ea5f3  lea     r8, [rsp+0A8h+var_48]
0x1801ea5f8  lea     rdx, __NULL_IMPORT_DESCRIPTOR
0x1801ea5ff  mov     rdx, [rax+rdx+5FCC70h]
0x1801ea607  mov     rax, r9
0x1801ea60a  call    cs:__guard_dispatch_icall_fptr
0x1801ea610  mov     edi, eax
0x1801ea612  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801ea617  call    cs:__imp_VariantClear
0x1801ea61d  cmp     edi, r12d
0x1801ea620  jz      loc_1801EA73B
0x1801ea626  cmp     edi, esi
0x1801ea628  jz      loc_1801EA73B
0x1801ea62e  cmp     edi, r14d
0x1801ea631  jz      loc_1801EA73B
0x1801ea637  cmp     edi, 86180110h
0x1801ea63d  jz      loc_1801EA73B
0x1801ea643  test    edi, edi
0x1801ea645  js      loc_1801EA786
0x1801ea64b  mov     [rsp+0A8h+arg_8], 0
0x1801ea657  mov     rcx, [rbx+98h]
0x1801ea65e  mov     rax, [rcx]
0x1801ea661  lea     rdx, [rsp+0A8h+arg_8]
0x1801ea669  mov     rax, [rax+38h]
0x1801ea66d  call    cs:__guard_dispatch_icall_fptr
0x1801ea673  test    eax, eax
0x1801ea675  js      loc_1801EA78D
0x1801ea67b  mov     rcx, [rsp+0A8h+arg_8]
0x1801ea683  test    rcx, rcx
0x1801ea686  jz      loc_1801EA794
0x1801ea68c  mov     rax, [rcx]
0x1801ea68f  mov     rax, [rax+10h]
0x1801ea693  call    cs:__guard_dispatch_icall_fptr
0x1801ea699  mov     rcx, [rsp+0A8h+arg_8]
0x1801ea6a1  mov     rax, [rcx]
0x1801ea6a4  mov     rdx, [rsp+0A8h+arg_10]
0x1801ea6ac  add     rdx, rdx
0x1801ea6af  movsd   xmm0, qword ptr [rbx+rdx*8+0B8h]
0x1801ea6b8  mov     edx, 5
0x1801ea6bd  mov     word ptr [rsp+0A8h+pvarg], dx
0x1801ea6c2  movsd   qword ptr [rsp+0A8h+pvarg+8], xmm0
0x1801ea6c8  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x1801ea6cd  movaps  [rsp+0A8h+var_48], xmm0
0x1801ea6d2  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x1801ea6d8  movsd   [rsp+0A8h+var_38], xmm1
0x1801ea6de  lea     r8, [rsp+0A8h+var_48]
0x1801ea6e3  mov     rdx, [rsp+0A8h+arg_18]
0x1801ea6eb  lea     r9, __NULL_IMPORT_DESCRIPTOR
0x1801ea6f2  mov     rdx, [rdx+r9+5FCC50h]
0x1801ea6fa  mov     rax, [rax+68h]
0x1801ea6fe  call    cs:__guard_dispatch_icall_fptr
0x1801ea704  mov     edi, eax
0x1801ea706  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801ea70b  call    cs:__imp_VariantClear
0x1801ea711  cmp     edi, r12d
0x1801ea714  jz      loc_1801EA7A5
0x1801ea71a  cmp     edi, esi
0x1801ea71c  jz      loc_1801EA7A5
0x1801ea722  cmp     edi, r14d
0x1801ea725  jz      short loc_1801EA7A5
0x1801ea727  cmp     edi, 86180110h
0x1801ea72d  jz      short loc_1801EA7A5
0x1801ea72f  test    edi, edi
0x1801ea731  js      short loc_1801EA79E
0x1801ea733  inc     r13d
0x1801ea736  jmp     loc_1801EA53F
0x1801ea73b  mov     ecx, edi; int
0x1801ea73d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea742  mov     ecx, 80004003h; int
0x1801ea747  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea74c  mov     ecx, eax; int
0x1801ea74e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea754  jmp     short loc_1801EA758
0x1801ea758  nop
0x1801ea759  mov     ecx, eax; int
0x1801ea75b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea760  mov     ecx, 86190100h; int
0x1801ea765  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea76a  mov     ecx, eax; int
0x1801ea76c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea772  jmp     short $+2
0x1801ea774  nop
0x1801ea775  mov     ecx, eax; int
0x1801ea777  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea77c  mov     ecx, 8618010Ah; int
0x1801ea781  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea786  mov     ecx, edi; int
0x1801ea788  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea78d  mov     ecx, eax; int
0x1801ea78f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea794  mov     ecx, 8618010Ah; int
0x1801ea799  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea79e  mov     ecx, edi; int
0x1801ea7a0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801ea7a5  mov     ecx, edi; int
0x1801ea7a7  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```

# CThemeAnimationScheduleHelper::CreateAndAddChoppedCubicBezierTransition(IUIAnimationStoryboard2 *,IUIAnimationVariable2 *,IUIAnimationTransitionLibrary2 *,double,double *,double *,uint,double *,double *,uint,float,float,float,float,__MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *)

- ea: `0x18009e834`
- end: `0x18009eb8e`
- name: `?CreateAndAddChoppedCubicBezierTransition@CThemeAnimationScheduleHelper@@QEAAJPEAUIUIAnimationStoryboard2@@PEAUIUIAnimationVariable2@@PEAUIUIAnimationTransitionLibrary2@@NPEAN3I33IMMMMPEAU__MIDL___MIDL_itf_UIAnimation_0000_0002_0003@@@Z`
- size: `858`
- prototype: `int(CThemeAnimationScheduleHelper *__hidden this, struct IUIAnimationStoryboard2 *, struct IUIAnimationVariable2 *, struct IUIAnimationTransitionLibrary2 *, double, double *, double *, unsigned int, double *, double *, unsigned int, float, float, float, float, struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003206c`

## callees

- `0x1800029dc`
- `0x18009e130`
- `0x18009e228`
- `0x18009e834`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009e9bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009e9bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeAnimationScheduleHelper::CreateAndAddChoppedCubicBezierTransition(
        CThemeAnimationScheduleHelper *this,
        struct IUIAnimationStoryboard2 *a2,
        struct IUIAnimationVariable2 *a3,
        struct IUIAnimationTransitionLibrary2 *a4,
        double a5,
        double *a6,
        double *a7,
        unsigned int a8,
        double *a9,
        double *a10,
        unsigned int a11,
        float a12,
        float a13,
        float a14,
        float a15,
        struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *a16)
{
  double v18; // xmm7_8
  double v19; // xmm6_8
  double v20; // xmm1_8
  double v21; // xmm0_8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  LPVOID *ppv; // rax
  __int64 v26; // rdx
  HRESULT Instance; // ebx
  __int64 v28; // rdx
  __int64 v29; // rdx
  struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *v30; // [rsp+40h] [rbp-C8h]
  __int64 v31; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-98h]
  _BYTE v33[192]; // [rsp+78h] [rbp-90h] BYREF
  CThemeAnimationScheduleHelper *v34; // [rsp+148h] [rbp+40h] BYREF

  v34 = this;
  if ( a8 > 4 )
    return 2147942450LL;
  if ( a5 <= 0.0 )
    return 2147942487LL;
  if ( a11 >= a8 )
    return 2147942487LL;
  v18 = a7[a11];
  v19 = a6[a11];
  if ( v18 == v19 )
    return 2147942487LL;
  v20 = a9 ? *a9 : a6[a11];
  v21 = a10 ? *a10 : a7[a11];
  if ( v20 != v21 && v18 > v19 == v20 > v21 )
    return 2147942487LL;
  if ( v18 > v19 == v19 > v20 && v18 > v19 == v21 > v19 )
    v20 = a6[a11];
  if ( v18 > v19 == v18 > v20 && v18 > v19 == v21 > v18 )
    v21 = a7[a11];
  CThemeAnimationScheduleHelper::CCubicBezierChopper::CCubicBezierChopper(
    (CThemeAnimationScheduleHelper::CCubicBezierChopper *)v33,
    a2,
    a3,
    a4,
    a6,
    a7,
    a8,
    v30,
    v20,
    v21,
    a11);
  v34 = 0;
  ppv = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                    &v34,
                    v22,
                    v23,
                    v24);
  Instance = CoCreateInstance(&CLSID_UIAnimationManager2, 0, 3u, &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(CThemeAnimationScheduleHelper *, __int64, _QWORD))(*(_QWORD *)v34 + 72LL))(
                 v34,
                 v26,
                 0);
    if ( Instance >= 0 )
    {
      v31 = 0;
      Instance = (*(__int64 (__fastcall **)(CThemeAnimationScheduleHelper *, __int64, __int64 *))(*(_QWORD *)v34 + 32LL))(
                   v34,
                   v28,
                   &v31);
      if ( Instance >= 0 )
      {
        a16 = 0;
        Instance = (*(__int64 (__fastcall **)(CThemeAnimationScheduleHelper *, struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 **))(*(_QWORD *)v34 + 48LL))(
                     v34,
                     &a16);
        if ( Instance >= 0 )
        {
          v32 = 0;
          Instance = ((__int64 (__fastcall *)(struct IUIAnimationTransitionLibrary2 *))a4->lpVtbl->CreateCubicBezierLinearTransition)(a4);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *, __int64, __int64))(*(_QWORD *)&a16->_ + 24LL))(
                         a16,
                         v31,
                         v32);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            if ( Instance >= 0 )
              Instance = (*(__int64 (__fastcall **)(struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *, __int64, _QWORD))(*(_QWORD *)&a16->_ + 96LL))(
                           a16,
                           v29,
                           0);
          }
          (*(void (__fastcall **)(struct __MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *))(*(_QWORD *)&a16->_ + 16LL))(a16);
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 48LL))(v31, v33);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    (*(void (__fastcall **)(CThemeAnimationScheduleHelper *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  CThemeAnimationScheduleHelper::CCubicBezierChopper::~CCubicBezierChopper((CThemeAnimationScheduleHelper::CCubicBezierChopper *)v33);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18009e834  mov     rax, rsp
0x18009e837  mov     [rax+10h], rbx
0x18009e83b  mov     [rax+18h], rdi
0x18009e83f  mov     [rax+8], rcx
0x18009e843  push    rbp
0x18009e844  lea     rbp, [rax-38h]
0x18009e848  sub     rsp, 130h
0x18009e84f  movaps  xmmword ptr [rax-18h], xmm6
0x18009e853  movaps  xmmword ptr [rax-28h], xmm7
0x18009e857  movaps  xmmword ptr [rax-38h], xmm8
0x18009e85c  mov     rdi, r9
0x18009e85f  mov     r11, r8
0x18009e862  mov     rbx, rdx
0x18009e865  mov     r10d, [rbp+30h+arg_38]
0x18009e869  cmp     r10d, 4
0x18009e86d  jbe     short loc_18009E879
0x18009e86f  mov     eax, 80070032h
0x18009e874  jmp     loc_18009EB6A
0x18009e879  xorps   xmm8, xmm8
0x18009e87d  comisd  xmm8, [rbp+30h+arg_20]
0x18009e883  jnb     loc_18009EB65
0x18009e889  mov     edx, [rbp+30h+arg_50]
0x18009e88f  cmp     edx, r10d
0x18009e892  jnb     loc_18009EB65
0x18009e898  mov     r8, [rbp+30h+arg_30]
0x18009e89c  movsd   xmm7, qword ptr [r8+rdx*8]
0x18009e8a2  mov     r9, [rbp+30h+arg_28]
0x18009e8a6  movsd   xmm6, qword ptr [r9+rdx*8]
0x18009e8ac  ucomisd xmm7, xmm6
0x18009e8b0  jp      short loc_18009E8B8
0x18009e8b2  jz      loc_18009EB65
0x18009e8b8  mov     rax, [rbp+30h+arg_40]
0x18009e8bf  test    rax, rax
0x18009e8c2  jnz     short loc_18009E8C9
0x18009e8c4  movaps  xmm1, xmm6
0x18009e8c7  jmp     short loc_18009E8CD
0x18009e8c9  movsd   xmm1, qword ptr [rax]
0x18009e8cd  mov     rax, [rbp+30h+arg_48]
0x18009e8d4  test    rax, rax
0x18009e8d7  jnz     short loc_18009E8DE
0x18009e8d9  movaps  xmm0, xmm7
0x18009e8dc  jmp     short loc_18009E8E2
0x18009e8de  movsd   xmm0, qword ptr [rax]
0x18009e8e2  ucomisd xmm1, xmm0
0x18009e8e6  jp      short loc_18009E8EA
0x18009e8e8  jz      short loc_18009E904
0x18009e8ea  xor     ecx, ecx
0x18009e8ec  comisd  xmm7, xmm6
0x18009e8f0  setnbe  cl
0x18009e8f3  xor     eax, eax
0x18009e8f5  comisd  xmm1, xmm0
0x18009e8f9  setnbe  al
0x18009e8fc  cmp     ecx, eax
0x18009e8fe  jz      loc_18009EB65
0x18009e904  xor     ecx, ecx
0x18009e906  comisd  xmm7, xmm6
0x18009e90a  setnbe  cl
0x18009e90d  xor     eax, eax
0x18009e90f  comisd  xmm6, xmm1
0x18009e913  setnbe  al
0x18009e916  cmp     ecx, eax
0x18009e918  jnz     short loc_18009E933
0x18009e91a  xor     ecx, ecx
0x18009e91c  comisd  xmm7, xmm6
0x18009e920  setnbe  cl
0x18009e923  xor     eax, eax
0x18009e925  comisd  xmm0, xmm6
0x18009e929  setnbe  al
0x18009e92c  cmp     ecx, eax
0x18009e92e  jnz     short loc_18009E933
0x18009e930  movaps  xmm1, xmm6
0x18009e933  xor     ecx, ecx
0x18009e935  comisd  xmm7, xmm6
0x18009e939  setnbe  cl
0x18009e93c  xor     eax, eax
0x18009e93e  comisd  xmm7, xmm1
0x18009e942  setnbe  al
0x18009e945  cmp     ecx, eax
0x18009e947  jnz     short loc_18009E962
0x18009e949  xor     ecx, ecx
0x18009e94b  comisd  xmm7, xmm6
0x18009e94f  setnbe  cl
0x18009e952  xor     eax, eax
0x18009e954  comisd  xmm0, xmm7
0x18009e958  setnbe  al
0x18009e95b  cmp     ecx, eax
0x18009e95d  jnz     short loc_18009E962
0x18009e95f  movaps  xmm0, xmm7
0x18009e962  mov     [rsp+130h+var_E0], edx; unsigned int
0x18009e966  movsd   [rsp+130h+var_E8], xmm0; double
0x18009e96c  movsd   [rsp+130h+var_F0], xmm1; double
0x18009e972  mov     [rsp+130h+var_100], r10d; unsigned int
0x18009e977  mov     [rsp+130h+var_108], r8; double *
0x18009e97c  mov     [rsp+130h+ppv], r9; double *
0x18009e981  mov     r9, rdi; struct IUIAnimationTransitionLibrary2 *
0x18009e984  mov     r8, r11; struct IUIAnimationVariable2 *
0x18009e987  mov     rdx, rbx; struct IUIAnimationStoryboard2 *
0x18009e98a  lea     rcx, [rsp+130h+var_C0]; this
0x18009e98f  call    ??0CCubicBezierChopper@CThemeAnimationScheduleHelper@@QEAA@PEAUIUIAnimationStoryboard2@@PEAUIUIAnimationVariable2@@PEAUIUIAnimationTransitionLibrary2@@PEAN3IPEAU__MIDL___MIDL_itf_UIAnimation_0000_0002_0003@@NNI@Z; CThemeAnimationScheduleHelper::CCubicBezierChopper::CCubicBezierChopper(IUIAnimationStoryboard2 *,IUIAnimationVariable2 *,IUIAnimationTransitionLibrary2 *,double *,double *,uint,__MIDL___MIDL_itf_UIAnimation_0000_0002_0003 *,double,double,uint)
0x18009e994  nop
0x18009e995  mov     [rbp+30h+arg_0], 0
0x18009e99d  lea     rcx, [rbp+30h+arg_0]
0x18009e9a1  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18009e9a6  mov     [rsp+130h+ppv], rax; ppv
0x18009e9ab  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x18009e9b2  xor     edx, edx; pUnkOuter
0x18009e9b4  lea     r8d, [rdx+3]; dwClsContext
0x18009e9b8  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x18009e9bf  call    cs:__imp_CoCreateInstance
0x18009e9c5  mov     ebx, eax
0x18009e9c7  test    eax, eax
0x18009e9c9  js      loc_18009EB57
0x18009e9cf  mov     rcx, [rbp+30h+arg_0]
0x18009e9d3  mov     rax, [rcx]
0x18009e9d6  xor     r8d, r8d
0x18009e9d9  xorps   xmm1, xmm1
0x18009e9dc  mov     rax, [rax+48h]
0x18009e9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e9e5  mov     ebx, eax
0x18009e9e7  test    eax, eax
0x18009e9e9  js      loc_18009EB46
0x18009e9ef  mov     [rsp+130h+var_D0], 0
0x18009e9f8  mov     rcx, [rbp+30h+arg_0]
0x18009e9fc  mov     rax, [rcx]
0x18009e9ff  lea     r8, [rsp+130h+var_D0]
0x18009ea04  movaps  xmm1, xmm6
0x18009ea07  mov     rax, [rax+20h]
0x18009ea0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea10  mov     ebx, eax
0x18009ea12  test    eax, eax
0x18009ea14  js      loc_18009EB46
0x18009ea1a  mov     [rbp+30h+arg_78], 0
0x18009ea25  mov     rcx, [rbp+30h+arg_0]
0x18009ea29  mov     rax, [rcx]
0x18009ea2c  lea     rdx, [rbp+30h+arg_78]
0x18009ea33  mov     rax, [rax+30h]
0x18009ea37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea3c  mov     ebx, eax
0x18009ea3e  test    eax, eax
0x18009ea40  js      loc_18009EB35
0x18009ea46  mov     [rsp+130h+var_C8], 0
0x18009ea4f  mov     rax, [rdi]
0x18009ea52  movss   xmm0, [rbp+30h+arg_70]
0x18009ea5a  cvtps2pd xmm0, xmm0
0x18009ea5d  movss   xmm1, [rbp+30h+arg_68]
0x18009ea65  cvtps2pd xmm1, xmm1
0x18009ea68  movss   xmm4, [rbp+30h+arg_60]
0x18009ea70  cvtps2pd xmm4, xmm4
0x18009ea73  movss   xmm3, [rbp+30h+arg_58]
0x18009ea7b  cvtps2pd xmm3, xmm3
0x18009ea7e  lea     rcx, [rsp+130h+var_C8]
0x18009ea83  mov     [rsp+130h+var_F8], rcx
0x18009ea88  movsd   qword ptr [rsp+130h+var_100], xmm0
0x18009ea8e  movsd   [rsp+130h+var_108], xmm1
0x18009ea94  movsd   [rsp+130h+ppv], xmm4
0x18009ea9a  movaps  xmm2, xmm7
0x18009ea9d  movsd   xmm1, [rbp+30h+arg_20]
0x18009eaa2  mov     rcx, rdi
0x18009eaa5  mov     rax, [rax+0A0h]
0x18009eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eab1  mov     ebx, eax
0x18009eab3  test    eax, eax
0x18009eab5  js      short loc_18009EB06
0x18009eab7  mov     rcx, [rbp+30h+arg_78]
0x18009eabe  mov     rax, [rcx]
0x18009eac1  mov     r8, [rsp+130h+var_C8]
0x18009eac6  mov     rdx, [rsp+130h+var_D0]
0x18009eacb  mov     rax, [rax+18h]
0x18009eacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ead4  mov     ebx, eax
0x18009ead6  mov     rcx, [rsp+130h+var_C8]
0x18009eadb  mov     rax, [rcx]
0x18009eade  mov     rax, [rax+10h]
0x18009eae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eae7  test    ebx, ebx
0x18009eae9  js      short loc_18009EB06
0x18009eaeb  mov     rcx, [rbp+30h+arg_78]
0x18009eaf2  mov     rax, [rcx]
0x18009eaf5  xor     r8d, r8d
0x18009eaf8  xorps   xmm1, xmm1
0x18009eafb  mov     rax, [rax+60h]
0x18009eaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb04  mov     ebx, eax
0x18009eb06  mov     rcx, [rbp+30h+arg_78]
0x18009eb0d  mov     rax, [rcx]
0x18009eb10  mov     rax, [rax+10h]
0x18009eb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb19  test    ebx, ebx
0x18009eb1b  js      short loc_18009EB35
0x18009eb1d  mov     rcx, [rsp+130h+var_D0]
0x18009eb22  mov     rax, [rcx]
0x18009eb25  lea     rdx, [rsp+130h+var_C0]
0x18009eb2a  mov     rax, [rax+30h]
0x18009eb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb33  mov     ebx, eax
0x18009eb35  mov     rcx, [rsp+130h+var_D0]
0x18009eb3a  mov     rax, [rcx]
0x18009eb3d  mov     rax, [rax+10h]
0x18009eb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb46  mov     rcx, [rbp+30h+arg_0]
0x18009eb4a  mov     rax, [rcx]
0x18009eb4d  mov     rax, [rax+10h]
0x18009eb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb56  nop
0x18009eb57  lea     rcx, [rsp+130h+var_C0]; this
0x18009eb5c  call    ??1CCubicBezierChopper@CThemeAnimationScheduleHelper@@QEAA@XZ; CThemeAnimationScheduleHelper::CCubicBezierChopper::~CCubicBezierChopper(void)
0x18009eb61  mov     eax, ebx
0x18009eb63  jmp     short loc_18009EB6A
0x18009eb65  mov     eax, 80070057h
0x18009eb6a  lea     r11, [rsp+130h+var_s0]
0x18009eb72  mov     rbx, [r11+18h]
0x18009eb76  mov     rdi, [r11+20h]
0x18009eb7a  movaps  xmm6, xmmword ptr [r11-10h]
0x18009eb7f  movaps  xmm7, xmmword ptr [r11-20h]
0x18009eb84  movaps  xmm8, xmmword ptr [r11-30h]
0x18009eb89  mov     rsp, r11
0x18009eb8c  pop     rbp
0x18009eb8d  retn
```

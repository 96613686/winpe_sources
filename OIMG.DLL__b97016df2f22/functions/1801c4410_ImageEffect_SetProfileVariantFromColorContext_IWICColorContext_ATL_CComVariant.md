# ImageEffect::SetProfileVariantFromColorContext(IWICColorContext *,ATL::CComVariant *)

- ea: `0x1801c4410`
- end: `0x1801c4896`
- name: `?SetProfileVariantFromColorContext@ImageEffect@@CAXPEAUIWICColorContext@@PEAVCComVariant@ATL@@@Z`
- size: `1158`
- prototype: `void __fastcall(struct IWICColorContext *, VARIANTARG *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801c48a0`
- `0x1801c4ae0`

## callees

- `0x18001397c`
- `0x1801c2978`
- `0x1801c4410`
- `0x1801c5988`
- `0x1801c59a4`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056d170`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801c4450`
- `OLEAUT32!__imp_VariantClear` at `0x1801c4743`
- `OLEAUT32!__imp_VariantClear` at `0x1801c4450`
- `OLEAUT32!__imp_VariantClear` at `0x1801c4743`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801c46ea`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801c46ea`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801c47b9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801c47b9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801c4707`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801c4707`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801c47ac`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801c47ac`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801c4762`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801c4762`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801c4776`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801c4776`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801c468a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801c468a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801c47fd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801c47fd`

## pseudocode

```c
void __fastcall ImageEffect::SetProfileVariantFromColorContext(struct IWICColorContext *a1, VARIANTARG *a2)
{
  int v4; // eax
  int v5; // eax
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax
  void *v10; // rsi
  int v11; // eax
  size_t v12; // r14
  SAFEARRAY *v13; // rbx
  SAFEARRAY *v14; // rax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  __int64 v18; // rcx
  bool v19; // al
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Size; // [rsp+38h] [rbp-C8h] BYREF
  int Size_4; // [rsp+3Ch] [rbp-C4h] BYREF
  size_t v23; // [rsp+40h] [rbp-C0h] BYREF
  void *v24; // [rsp+48h] [rbp-B8h]
  SAFEARRAY *v25; // [rsp+50h] [rbp-B0h]
  _BYTE v26[268]; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+16Ch] [rbp+6Ch]
  __int16 v28; // [rsp+170h] [rbp+70h]
  int v29; // [rsp+17Ch] [rbp+7Ch]
  __int16 v30; // [rsp+180h] [rbp+80h]
  int v31; // [rsp+18Ch] [rbp+8Ch]
  __int16 v32; // [rsp+190h] [rbp+90h]
  int v33; // [rsp+19Ch] [rbp+9Ch]
  int v34; // [rsp+1A0h] [rbp+A0h]
  int v35; // [rsp+1A4h] [rbp+A4h]
  int v36; // [rsp+1B0h] [rbp+B0h]
  int v37; // [rsp+1B4h] [rbp+B4h]
  int v38; // [rsp+1B8h] [rbp+B8h]
  int v39; // [rsp+1C4h] [rbp+C4h]
  int v40; // [rsp+1C8h] [rbp+C8h]
  int v41; // [rsp+1CCh] [rbp+CCh]
  char v42[88]; // [rsp+1E8h] [rbp+E8h] BYREF

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  VariantClear(a2);
  if ( a1 )
  {
    Size_4 = 0;
    v4 = ((__int64 (__fastcall *)(struct IWICColorContext *, int *))a1->lpVtbl->GetType)(a1, &Size_4);
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    if ( Size_4 )
    {
      if ( Size_4 != 2 )
        goto LABEL_14;
      rgsabound.cElements = 0;
      v5 = ((__int64 (__fastcall *)(struct IWICColorContext *, SAFEARRAYBOUND *))a1->lpVtbl->GetExifColorSpace)(
             a1,
             &rgsabound);
      if ( v5 < 0 )
        ATL::BaseAtlThrow(v5);
      if ( rgsabound.cElements == 1 )
      {
        ATL::CComVariant::operator=(a2, L"sRGB Color Space Profile.ICM");
        return;
      }
      if ( rgsabound.cElements == 2 )
      {
        v6 = v26;
        v7 = &Icc::kMatrixGammaColorProfile;
        v8 = 3;
        do
        {
          *v6 = *v7;
          v6[1] = v7[1];
          v6[2] = v7[2];
          v6[3] = v7[3];
          v6[4] = v7[4];
          v6[5] = v7[5];
          v6[6] = v7[6];
          v6 += 8;
          *(v6 - 1) = v7[7];
          v7 += 8;
          --v8;
        }
        while ( v8 );
        *v6 = *v7;
        v6[1] = v7[1];
        v6[2] = v7[2];
        v6[3] = v7[3];
        v6[4] = v7[4];
        v6[5] = v7[5];
        v33 = 412876800;
        v34 = -1521549312;
        v35 = -66846720;
        v36 = -1925971968;
        v37 = 748683264;
        v38 = -1794179072;
        v39 = 824573952;
        v40 = 789577728;
        v41 = -1665269760;
        v28 = 13058;
        v27 = 0x1000000;
        v30 = 13058;
        v29 = 0x1000000;
        v32 = 13058;
        v31 = 0x1000000;
        strcpy(v42, "opRGB");
        MatrixGammaColorProfile::GetVariantProfile((MatrixGammaColorProfile *)v26, a2);
      }
      else
      {
LABEL_14:
        Size = 0;
        if ( !((unsigned int (__fastcall *)(struct IWICColorContext *, _QWORD, _QWORD, unsigned int *))a1->lpVtbl->GetProfileBytes)(
                a1,
                0,
                0,
                &Size)
          && Size )
        {
          LODWORD(v23) = 0;
          v24 = 0;
          v9 = malloc(Size);
          v10 = v9;
          if ( !v9 )
            ThrowOOM();
          v24 = v9;
          v11 = ((__int64 (__fastcall *)(struct IWICColorContext *, _QWORD, void *, size_t *))a1->lpVtbl->GetProfileBytes)(
                  a1,
                  Size,
                  v9,
                  &v23);
          if ( v11 < 0 )
            ATL::BaseAtlThrow(v11);
          v12 = (unsigned int)v23;
          v13 = 0;
          v25 = 0;
          if ( (_DWORD)v23 )
          {
            rgsabound.cElements = v23;
            rgsabound.lLbound = 0;
            v14 = SafeArrayCreate(0x11u, 1u, &rgsabound);
            v13 = v14;
            v25 = v14;
            if ( v14 )
              v15 = SafeArrayLock(v14);
            else
              v15 = -2147024882;
            if ( v15 < 0 )
              ATL::BaseAtlThrow(v15);
            memcpy_0(v13->pvData, v10, v12);
          }
          if ( !v13 )
          {
            ATL::CComVariant::ClearThrow((ATL::CComVariant *)a2);
            a2->vt = 10;
            a2->lVal = -2147024809;
            ATL::BaseAtlThrow(-2147024809);
          }
          if ( (a2->vt & 0x2000) == 0 || v13 != a2->parray )
          {
            v16 = VariantClear(a2);
            if ( v16 < 0 )
              ATL::BaseAtlThrow(v16);
            rgsabound = 0;
            v17 = SafeArrayCopy(v13, (SAFEARRAY **)&rgsabound);
            if ( v17 < 0 )
            {
              a2->vt = 10;
              a2->lVal = v17;
              if ( v17 == -2147024882 )
                ATL::BaseAtlThrow(-2147024882);
              ATL::BaseAtlThrow(v17);
            }
            if ( SafeArrayGetVartype(v13, &a2->vt) >= 0 && a2->vt == 13 && (v13->fFeatures & 0x440) == 0x440 )
              a2->vt = 9;
            a2->vt |= 0x2000u;
            a2->decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
          }
          if ( SafeArrayUnlock(v13) >= 0 )
            SafeArrayDestroy(v13);
          if ( ImagingEngine::s_singleton )
            v18 = *((_QWORD *)ImagingEngine::s_singleton + 10);
          else
            v18 = 0;
          if ( v18 )
            v19 = (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v18 + 88LL))(v18, v10) == 0;
          else
            v19 = 0;
          if ( !v19 )
            free(v10);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801c4410  mov     [rsp-8+arg_10], rbx
0x1801c4415  mov     [rsp-8+arg_18], rsi
0x1801c441a  push    rbp
0x1801c441b  push    rdi
0x1801c441c  push    r14
0x1801c441e  lea     rbp, [rsp-150h]
0x1801c4426  sub     rsp, 250h
0x1801c442d  mov     rax, cs:__security_cookie
0x1801c4434  xor     rax, rsp
0x1801c4437  mov     [rbp+160h+var_20], rax
0x1801c443e  mov     rdi, rdx
0x1801c4441  mov     rbx, rcx
0x1801c4444  test    rdx, rdx
0x1801c4447  jz      loc_1801C483B
0x1801c444d  mov     rcx, rdx; pvarg
0x1801c4450  call    cs:__imp_VariantClear
0x1801c4456  test    rbx, rbx
0x1801c4459  jz      short loc_1801C44CC
0x1801c445b  mov     dword ptr [rsp+260h+Size+4], 0
0x1801c4463  mov     rax, [rbx]
0x1801c4466  lea     rdx, [rsp+260h+Size+4]
0x1801c446b  mov     rcx, rbx
0x1801c446e  mov     rax, [rax+30h]
0x1801c4472  call    cs:__guard_dispatch_icall_fptr
0x1801c4478  test    eax, eax
0x1801c447a  js      loc_1801C4833
0x1801c4480  mov     eax, dword ptr [rsp+260h+Size+4]
0x1801c4484  test    eax, eax
0x1801c4486  jz      short loc_1801C44CC
0x1801c4488  cmp     eax, 2
0x1801c448b  jnz     loc_1801C4641
0x1801c4491  mov     [rsp+260h+rgsabound.cElements], 0
0x1801c4499  mov     rax, [rbx]
0x1801c449c  lea     rdx, [rsp+260h+rgsabound]
0x1801c44a1  mov     rcx, rbx
0x1801c44a4  mov     rax, [rax+40h]
0x1801c44a8  call    cs:__guard_dispatch_icall_fptr
0x1801c44ae  test    eax, eax
0x1801c44b0  js      loc_1801C4846
0x1801c44b6  cmp     [rsp+260h+rgsabound.cElements], 1
0x1801c44bb  jnz     short loc_1801C44F3
0x1801c44bd  lea     rdx, aSrgbColorSpace; "sRGB Color Space Profile.ICM"
0x1801c44c4  mov     rcx, rdi
0x1801c44c7  call    ??4CComVariant@ATL@@QEAAAEAV01@PEB_W@Z; ATL::CComVariant::operator=(wchar_t const *)
0x1801c44cc  mov     rcx, [rbp+160h+var_20]
0x1801c44d3  xor     rcx, rsp; StackCookie
0x1801c44d6  call    __security_check_cookie
0x1801c44db  lea     r11, [rsp+260h+var_10]
0x1801c44e3  mov     rbx, [r11+30h]
0x1801c44e7  mov     rsi, [r11+38h]
0x1801c44eb  mov     rsp, r11
0x1801c44ee  pop     r14
0x1801c44f0  pop     rdi
0x1801c44f1  pop     rbp
0x1801c44f2  retn
0x1801c44f3  cmp     [rsp+260h+rgsabound.cElements], 2
0x1801c44f8  jnz     loc_1801C4641
0x1801c44fe  lea     rax, [rsp+260h+var_200]
0x1801c4503  lea     rcx, ?kMatrixGammaColorProfile@Icc@@3U_MatrixGammaColorProfile@1@A; Icc::_MatrixGammaColorProfile Icc::kMatrixGammaColorProfile
0x1801c450a  mov     edx, 3
0x1801c450f  lea     r8d, [rdx+7Dh]
0x1801c4513  movups  xmm0, xmmword ptr [rcx]
0x1801c4516  movups  xmmword ptr [rax], xmm0
0x1801c4519  movups  xmm1, xmmword ptr [rcx+10h]
0x1801c451d  movups  xmmword ptr [rax+10h], xmm1
0x1801c4521  movups  xmm0, xmmword ptr [rcx+20h]
0x1801c4525  movups  xmmword ptr [rax+20h], xmm0
0x1801c4529  movups  xmm1, xmmword ptr [rcx+30h]
0x1801c452d  movups  xmmword ptr [rax+30h], xmm1
0x1801c4531  movups  xmm0, xmmword ptr [rcx+40h]
0x1801c4535  movups  xmmword ptr [rax+40h], xmm0
0x1801c4539  movups  xmm1, xmmword ptr [rcx+50h]
0x1801c453d  movups  xmmword ptr [rax+50h], xmm1
0x1801c4541  movups  xmm0, xmmword ptr [rcx+60h]
0x1801c4545  movups  xmmword ptr [rax+60h], xmm0
0x1801c4549  add     rax, r8
0x1801c454c  movups  xmm1, xmmword ptr [rcx+70h]
0x1801c4550  movups  xmmword ptr [rax-10h], xmm1
0x1801c4554  add     rcx, r8
0x1801c4557  sub     rdx, 1
0x1801c455b  jnz     short loc_1801C4513
0x1801c455d  movups  xmm0, xmmword ptr [rcx]
0x1801c4560  movups  xmmword ptr [rax], xmm0
0x1801c4563  movups  xmm1, xmmword ptr [rcx+10h]
0x1801c4567  movups  xmmword ptr [rax+10h], xmm1
0x1801c456b  movups  xmm0, xmmword ptr [rcx+20h]
0x1801c456f  movups  xmmword ptr [rax+20h], xmm0
0x1801c4573  movups  xmm1, xmmword ptr [rcx+30h]
0x1801c4577  movups  xmmword ptr [rax+30h], xmm1
0x1801c457b  movups  xmm0, xmmword ptr [rcx+40h]
0x1801c457f  movups  xmmword ptr [rax+40h], xmm0
0x1801c4583  movups  xmm1, xmmword ptr [rcx+50h]
0x1801c4587  movups  xmmword ptr [rax+50h], xmm1
0x1801c458b  mov     [rbp+160h+var_C4], 189C0000h
0x1801c4595  mov     [rbp+160h+var_C0], 0A54F0000h
0x1801c459f  mov     [rbp+160h+var_BC], 0FC040000h
0x1801c45a9  mov     [rbp+160h+var_B0], 8D340000h
0x1801c45b3  mov     [rbp+160h+var_AC], 2CA00000h
0x1801c45bd  mov     [rbp+160h+var_A8], 950F0000h
0x1801c45c7  mov     [rbp+160h+var_9C], 31260000h
0x1801c45d1  mov     [rbp+160h+var_98], 2F100000h
0x1801c45db  mov     [rbp+160h+var_94], 9CBE0000h
0x1801c45e5  mov     ecx, 3302h
0x1801c45ea  mov     [rbp+160h+var_F0], cx
0x1801c45ee  mov     eax, 1000000h
0x1801c45f3  mov     [rbp+160h+var_F4], eax
0x1801c45f6  mov     [rbp+160h+var_E0], cx
0x1801c45fd  mov     [rbp+160h+var_E4], eax
0x1801c4600  mov     [rbp+160h+var_D0], cx
0x1801c4607  mov     [rbp+160h+var_D4], eax
0x1801c460d  mov     eax, dword ptr cs:aOprgb; "opRGB"
0x1801c4613  mov     dword ptr [rbp+160h+var_78], eax
0x1801c4619  mov     al, byte ptr cs:aOprgb+4; "B"
0x1801c461f  mov     [rbp+160h+var_78+4], al
0x1801c4625  lea     eax, [rdx+5]
0x1801c4628  mov     [rbp+rax+160h+var_78], dl
0x1801c462f  mov     rdx, rdi; struct tagVARIANT *
0x1801c4632  lea     rcx, [rsp+260h+var_200]; this
0x1801c4637  call    ?GetVariantProfile@MatrixGammaColorProfile@@QEAAXPEAUtagVARIANT@@@Z; MatrixGammaColorProfile::GetVariantProfile(tagVARIANT *)
0x1801c463c  jmp     loc_1801C44CC
0x1801c4641  mov     dword ptr [rsp+260h+Size], 0
0x1801c4649  mov     rax, [rbx]
0x1801c464c  lea     r9, [rsp+260h+Size]
0x1801c4651  xor     r8d, r8d
0x1801c4654  xor     edx, edx
0x1801c4656  mov     rcx, rbx
0x1801c4659  mov     rax, [rax+38h]
0x1801c465d  call    cs:__guard_dispatch_icall_fptr
0x1801c4663  test    eax, eax
0x1801c4665  jnz     loc_1801C44CC
0x1801c466b  mov     eax, dword ptr [rsp+260h+Size]
0x1801c466f  test    eax, eax
0x1801c4671  jz      loc_1801C44CC
0x1801c4677  mov     dword ptr [rsp+260h+var_220], 0
0x1801c467f  mov     [rsp+260h+var_218], 0
0x1801c4688  mov     ecx, eax; Size
0x1801c468a  call    cs:__imp_malloc
0x1801c4690  mov     rsi, rax
0x1801c4693  test    rax, rax
0x1801c4696  jz      loc_1801C4851
0x1801c469c  mov     [rsp+260h+var_218], rax
0x1801c46a1  mov     rax, [rbx]
0x1801c46a4  lea     r9, [rsp+260h+var_220]
0x1801c46a9  mov     r8, rsi
0x1801c46ac  mov     edx, dword ptr [rsp+260h+Size]
0x1801c46b0  mov     rcx, rbx
0x1801c46b3  mov     rax, [rax+38h]
0x1801c46b7  call    cs:__guard_dispatch_icall_fptr
0x1801c46bd  test    eax, eax
0x1801c46bf  js      loc_1801C4819
0x1801c46c5  mov     r14d, dword ptr [rsp+260h+var_220]
0x1801c46ca  xor     ebx, ebx
0x1801c46cc  mov     [rsp+260h+var_210], rbx
0x1801c46d1  test    r14d, r14d
0x1801c46d4  jz      short loc_1801C4725
0x1801c46d6  mov     [rsp+260h+rgsabound.cElements], r14d
0x1801c46db  mov     [rsp+260h+rgsabound.lLbound], ebx
0x1801c46df  lea     ecx, [rbx+11h]; vt
0x1801c46e2  lea     r8, [rsp+260h+rgsabound]; rgsabound
0x1801c46e7  lea     edx, [rbx+1]; cDims
0x1801c46ea  call    cs:__imp_SafeArrayCreate
0x1801c46f0  mov     rbx, rax
0x1801c46f3  mov     [rsp+260h+var_210], rax
0x1801c46f8  test    rax, rax
0x1801c46fb  jnz     short loc_1801C4704
0x1801c46fd  mov     eax, 8007000Eh
0x1801c4702  jmp     short loc_1801C470D
0x1801c4704  mov     rcx, rbx; psa
0x1801c4707  call    cs:__imp_SafeArrayLock
0x1801c470d  test    eax, eax
0x1801c470f  js      loc_1801C487B
0x1801c4715  mov     r8, r14; Size
0x1801c4718  mov     rdx, rsi; Src
0x1801c471b  mov     rcx, [rbx+10h]; void *
0x1801c471f  call    memcpy_0
0x1801c4724  nop
0x1801c4725  test    rbx, rbx
0x1801c4728  jz      loc_1801C485D
0x1801c472e  mov     r14d, 2000h
0x1801c4734  test    [rdi], r14w
0x1801c4738  jz      short loc_1801C4740
0x1801c473a  cmp     rbx, [rdi+8]
0x1801c473e  jz      short loc_1801C47A9
0x1801c4740  mov     rcx, rdi; pvarg
0x1801c4743  call    cs:__imp_VariantClear
0x1801c4749  test    eax, eax
0x1801c474b  js      loc_1801C4886
0x1801c4751  mov     qword ptr [rsp+260h+rgsabound.cElements], 0
0x1801c475a  lea     rdx, [rsp+260h+rgsabound]; ppsaOut
0x1801c475f  mov     rcx, rbx; psa
0x1801c4762  call    cs:__imp_SafeArrayCopy
0x1801c4768  test    eax, eax
0x1801c476a  js      loc_1801C4808
0x1801c4770  mov     rdx, rdi; pvt
0x1801c4773  mov     rcx, rbx; psa
0x1801c4776  call    cs:__imp_SafeArrayGetVartype
0x1801c477c  test    eax, eax
0x1801c477e  js      short loc_1801C479C
0x1801c4780  cmp     word ptr [rdi], 0Dh
0x1801c4784  jnz     short loc_1801C479C
0x1801c4786  movzx   eax, word ptr [rbx+2]
0x1801c478a  mov     ecx, 440h
0x1801c478f  and     ax, cx
0x1801c4792  cmp     ax, cx
0x1801c4795  jnz     short loc_1801C479C
0x1801c4797  mov     word ptr [rdi], 9
0x1801c479c  or      [rdi], r14w
0x1801c47a0  mov     rax, qword ptr [rsp+260h+rgsabound.cElements]
0x1801c47a5  mov     [rdi+8], rax
0x1801c47a9  mov     rcx, rbx; psa
0x1801c47ac  call    cs:__imp_SafeArrayUnlock
0x1801c47b2  test    eax, eax
0x1801c47b4  js      short loc_1801C47C0
0x1801c47b6  mov     rcx, rbx; psa
0x1801c47b9  call    cs:__imp_SafeArrayDestroy
0x1801c47bf  nop
0x1801c47c0  mov     rax, cs:?s_singleton@ImagingEngine@@2USingleton@1@A; ImagingEngine::Singleton ImagingEngine::s_singleton
0x1801c47c7  test    rax, rax
0x1801c47ca  jz      short loc_1801C47D2
0x1801c47cc  mov     rcx, [rax+50h]
0x1801c47d0  jmp     short loc_1801C47D4
0x1801c47d2  xor     ecx, ecx
0x1801c47d4  test    rcx, rcx
0x1801c47d7  jz      short loc_1801C47F0
0x1801c47d9  mov     rax, [rcx]
0x1801c47dc  mov     rdx, rsi
0x1801c47df  mov     rax, [rax+58h]
0x1801c47e3  call    cs:__guard_dispatch_icall_fptr
0x1801c47e9  test    eax, eax
0x1801c47eb  setz    al
0x1801c47ee  jmp     short loc_1801C47F2
0x1801c47f0  xor     al, al
0x1801c47f2  test    al, al
0x1801c47f4  jnz     loc_1801C44CC
0x1801c47fa  mov     rcx, rsi; Block
0x1801c47fd  call    cs:__imp_free
0x1801c4803  jmp     loc_1801C44CC
0x1801c4808  mov     word ptr [rdi], 0Ah
0x1801c480d  mov     [rdi+8], eax
0x1801c4810  cmp     eax, 8007000Eh
0x1801c4815  jnz     short loc_1801C488E
0x1801c4817  jmp     short loc_1801C4825
0x1801c4819  mov     ecx, eax; int
0x1801c481b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c4821  jmp     short loc_1801C4824
0x1801c4824  nop
0x1801c4825  mov     ecx, 8007000Eh; int
0x1801c482a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c4830  jmp     short $+2
0x1801c4832  nop
0x1801c4833  mov     ecx, eax; int
0x1801c4835  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c483b  mov     ecx, 80004003h; int
0x1801c4840  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c4846  mov     ecx, eax; int
0x1801c4848  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c484e  jmp     short $+2
0x1801c4850  nop
0x1801c4851  call    ?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1801c4857  jmp     short loc_1801C485C
0x1801c485c  nop
0x1801c485d  mov     rcx, rdi; this
0x1801c4860  call    ?ClearThrow@CComVariant@ATL@@AEAAXXZ; ATL::CComVariant::ClearThrow(void)
0x1801c4865  mov     word ptr [rdi], 0Ah
0x1801c486a  mov     ecx, 80070057h; int
0x1801c486f  mov     [rdi+8], ecx
0x1801c4872  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c4878  jmp     short $+2
0x1801c487a  nop
0x1801c487b  mov     ecx, eax; int
0x1801c487d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c4883  jmp     short $+2
0x1801c4885  nop
0x1801c4886  mov     ecx, eax; int
0x1801c4888  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801c488e  mov     ecx, eax; int
0x1801c4890  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```

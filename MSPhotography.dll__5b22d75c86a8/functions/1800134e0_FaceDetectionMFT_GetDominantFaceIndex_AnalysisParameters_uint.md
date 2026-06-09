# FaceDetectionMFT::GetDominantFaceIndex(AnalysisParameters *,uint *)

- ea: `0x1800134e0`
- end: `0x180013875`
- name: `?GetDominantFaceIndex@FaceDetectionMFT@@AEAAJPEAUAnalysisParameters@@PEAI@Z`
- size: `917`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct AnalysisParameters *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800197e0`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b480`
- `0x18000b490`
- `0x18000c0f8`
- `0x1800134e0`
- `0x18001d860`
- `0x18001d8a0`
- `0x18001d948`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001383f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001383f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800135c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800135c8`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::GetDominantFaceIndex(
        FaceDetectionMFT *this,
        struct AnalysisParameters *a2,
        unsigned int *a3)
{
  unsigned int v6; // edi
  unsigned int v7; // r15d
  int v8; // ebx
  __int64 v9; // rdx
  _DWORD *v10; // rsi
  __int64 i; // r15
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // r14d
  __int64 v20; // rdi
  __int64 v21; // rdx
  unsigned int v22; // ecx
  __int64 v23; // r8
  unsigned int v25; // [rsp+30h] [rbp-40h] BYREF
  int v26; // [rsp+34h] [rbp-3Ch]
  int v27; // [rsp+38h] [rbp-38h]
  int v28; // [rsp+3Ch] [rbp-34h]
  int v29; // [rsp+40h] [rbp-30h]
  int v30; // [rsp+44h] [rbp-2Ch]
  int v31; // [rsp+48h] [rbp-28h]
  __int64 v32; // [rsp+50h] [rbp-20h] BYREF
  __int128 v33; // [rsp+58h] [rbp-18h] BYREF

  v32 = 0;
  v33 = 0;
  v25 = 0;
  v6 = *((_DWORD *)a2 + 16);
  v26 = *((_DWORD *)a2 + 14);
  v7 = *((_DWORD *)a2 + 17);
  v27 = *((_DWORD *)a2 + 15);
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)a2 + 56LL))(*(_QWORD *)a2, &v25);
  if ( v8 >= 0 )
  {
    if ( !a3 )
    {
      v8 = -2147467261;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_42;
      v9 = 260;
      goto LABEL_4;
    }
    *a3 = 0;
    if ( !v25 )
    {
      v8 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_42;
      v9 = 261;
      goto LABEL_4;
    }
    v10 = CoTaskMemAlloc(4LL * v25);
    if ( !v10 )
    {
      v8 = -2147024882;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_42;
      v9 = 262;
      goto LABEL_4;
    }
    v8 = 0;
    v28 = 0x7FFFFFFF;
    v30 = 0;
    v29 = 0x7FFFFFFF;
    v31 = 0;
    v26 += v6 >> 1;
    v27 += v7 >> 1;
    for ( i = 0; (unsigned int)i < v25; i = (unsigned int)(i + 1) )
    {
      v12 = *(_QWORD *)a2;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)a2 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      v8 = v13(v12, (unsigned int)i, &v32);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_41;
        v18 = 263;
        goto LABEL_30;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v32 + 48LL))(v32, &v33);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_41;
        v18 = 264;
LABEL_30:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
        goto LABEL_41;
      }
      v10[i] = DWORD2(v33) * HIDWORD(v33);
      if ( *((_BYTE *)a2 + 129)
        && (signed int)((v27 - (HIDWORD(v33) >> 1) - DWORD1(v33)) * (v27 - (HIDWORD(v33) >> 1) - DWORD1(v33))
                      + (v26 - (DWORD2(v33) >> 1) - v33) * (v26 - (DWORD2(v33) >> 1) - v33)) < v28 )
      {
        v28 = (v27 - (HIDWORD(v33) >> 1) - DWORD1(v33)) * (v27 - (HIDWORD(v33) >> 1) - DWORD1(v33))
            + (v26 - (DWORD2(v33) >> 1) - v33) * (v26 - (DWORD2(v33) >> 1) - v33);
        v30 = i;
      }
      v14 = (*((_DWORD *)a2 + 12) >> 1) - (DWORD2(v33) >> 1) - v33;
      v15 = (*((_DWORD *)a2 + 13) >> 1) - (HIDWORD(v33) >> 1) - DWORD1(v33);
      if ( v14 * v14 + v15 * v15 < v29 )
      {
        v29 = v14 * v14 + v15 * v15;
        v31 = i;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v16,
          v17,
          (unsigned int)i,
          v33 + (DWORD2(v33) >> 1),
          DWORD1(v33) + (HIDWORD(v33) >> 1));
    }
    if ( *((_BYTE *)a2 + 129) )
      v10[v30] = (int)((double)(int)v10[v30] * 1.5);
    v10[v31] = (int)((double)(int)v10[v31] * 2.5);
    v19 = 0;
    v20 = 0;
    if ( v25 )
    {
      do
      {
        if ( v10[v20] > v19 )
        {
          v19 = v10[v20];
          *a3 = v20;
        }
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
        {
          WPP_SF_dL(*((_QWORD *)WPP_GLOBAL_Control + 27), v21, v23, (unsigned int)v20, v10[v20]);
          v22 = v25;
        }
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < v22 );
    }
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 267, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, *a3);
LABEL_41:
    CoTaskMemFree(v10);
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 259;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
  }
LABEL_42:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800134e0  mov     [rsp-38h+arg_18], rbx
0x1800134e5  push    rbp
0x1800134e6  push    rsi
0x1800134e7  push    rdi
0x1800134e8  push    r12
0x1800134ea  push    r13
0x1800134ec  push    r14
0x1800134ee  push    r15
0x1800134f0  mov     rbp, rsp
0x1800134f3  sub     rsp, 70h
0x1800134f7  mov     rax, cs:__security_cookie
0x1800134fe  xor     rax, rsp
0x180013501  mov     [rbp+var_8], rax
0x180013505  mov     r13, r8
0x180013508  mov     r12, rdx
0x18001350b  mov     r14, rcx
0x18001350e  xor     esi, esi
0x180013510  mov     [rbp+var_20], rsi
0x180013514  xorps   xmm0, xmm0
0x180013517  movups  [rbp+var_18], xmm0
0x18001351b  mov     [rbp+var_40], esi
0x18001351e  mov     edi, [rdx+40h]
0x180013521  mov     eax, [rdx+38h]
0x180013524  mov     [rbp+var_3C], eax
0x180013527  mov     r15d, [rdx+44h]
0x18001352b  mov     eax, [rdx+3Ch]
0x18001352e  mov     [rbp+var_38], eax
0x180013531  mov     rcx, [rdx]
0x180013534  mov     rax, [rcx]
0x180013537  lea     rdx, [rbp+var_40]
0x18001353b  mov     rax, [rax+38h]
0x18001353f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013544  mov     ebx, eax
0x180013546  test    eax, eax
0x180013548  jns     short loc_18001357F
0x18001354a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001354f  cmp     al, 1
0x180013551  jb      loc_180013846
0x180013557  mov     edx, 103h
0x18001355c  mov     [rsp+70h+var_50], ebx
0x180013560  mov     r9, r14
0x180013563  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001356a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013571  mov     rcx, [rcx+10h]
0x180013575  call    WPP_SF_qD
0x18001357a  jmp     loc_180013846
0x18001357f  test    r13, r13
0x180013582  jnz     short loc_18001359D
0x180013584  mov     ebx, 80004003h
0x180013589  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001358e  cmp     al, 1
0x180013590  jb      loc_180013846
0x180013596  mov     edx, 104h
0x18001359b  jmp     short loc_18001355C
0x18001359d  mov     [r13+0], esi
0x1800135a1  mov     eax, [rbp+var_40]
0x1800135a4  test    eax, eax
0x1800135a6  jnz     short loc_1800135C1
0x1800135a8  mov     ebx, 80070057h
0x1800135ad  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800135b2  cmp     al, 1
0x1800135b4  jb      loc_180013846
0x1800135ba  mov     edx, 105h
0x1800135bf  jmp     short loc_18001355C
0x1800135c1  mov     rcx, rax
0x1800135c4  shl     rcx, 2; cb
0x1800135c8  call    cs:__imp_CoTaskMemAlloc
0x1800135ce  mov     rsi, rax
0x1800135d1  test    rax, rax
0x1800135d4  jnz     short loc_1800135F2
0x1800135d6  mov     ebx, 8007000Eh
0x1800135db  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800135e0  cmp     al, 1
0x1800135e2  jb      loc_180013846
0x1800135e8  mov     edx, 106h
0x1800135ed  jmp     loc_18001355C
0x1800135f2  xor     ebx, ebx
0x1800135f4  mov     eax, 7FFFFFFFh
0x1800135f9  mov     [rbp+var_34], eax
0x1800135fc  mov     [rbp+var_2C], ebx
0x1800135ff  mov     [rbp+var_30], eax
0x180013602  mov     [rbp+var_28], ebx
0x180013605  shr     edi, 1
0x180013607  add     edi, [rbp+var_3C]
0x18001360a  mov     [rbp+var_3C], edi
0x18001360d  shr     r15d, 1
0x180013610  add     r15d, [rbp+var_38]
0x180013614  mov     [rbp+var_38], r15d
0x180013618  xor     r15d, r15d
0x18001361b  cmp     r15d, [rbp+var_40]
0x18001361f  jnb     loc_180013786
0x180013625  mov     rdi, [r12]
0x180013629  mov     rax, [rdi]
0x18001362c  mov     rbx, [rax+30h]
0x180013630  lea     rcx, [rbp+var_20]
0x180013634  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013639  lea     r8, [rbp+var_20]
0x18001363d  mov     edx, r15d
0x180013640  mov     rcx, rdi
0x180013643  mov     rax, rbx
0x180013646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001364b  mov     ebx, eax
0x18001364d  test    eax, eax
0x18001364f  js      loc_180013751
0x180013655  mov     rcx, [rbp+var_20]
0x180013659  mov     rax, [rcx]
0x18001365c  lea     rdx, [rbp+var_18]
0x180013660  mov     rax, [rax+30h]
0x180013664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013669  mov     ebx, eax
0x18001366b  test    eax, eax
0x18001366d  js      loc_18001373D
0x180013673  mov     ecx, dword ptr [rbp+var_18+0Ch]
0x180013676  imul    ecx, dword ptr [rbp+var_18+8]
0x18001367a  mov     [rsi+r15*4], ecx
0x18001367e  mov     r8d, dword ptr [rbp+var_18+0Ch]
0x180013682  mov     r9d, dword ptr [rbp+var_18+8]
0x180013686  cmp     byte ptr [r12+81h], 0
0x18001368f  jz      short loc_1800136C0
0x180013691  mov     eax, r9d
0x180013694  shr     eax, 1
0x180013696  mov     edx, [rbp+var_3C]
0x180013699  sub     edx, eax
0x18001369b  sub     edx, dword ptr [rbp+var_18]
0x18001369e  mov     eax, r8d
0x1800136a1  shr     eax, 1
0x1800136a3  mov     ecx, [rbp+var_38]
0x1800136a6  sub     ecx, eax
0x1800136a8  sub     ecx, dword ptr [rbp+var_18+4]
0x1800136ab  imul    ecx, ecx
0x1800136ae  imul    edx, edx
0x1800136b1  lea     eax, [rcx+rdx]
0x1800136b4  cmp     eax, [rbp+var_34]
0x1800136b7  jge     short loc_1800136C0
0x1800136b9  mov     [rbp+var_34], eax
0x1800136bc  mov     [rbp+var_2C], r15d
0x1800136c0  mov     ecx, [r12+30h]
0x1800136c5  shr     ecx, 1
0x1800136c7  shr     r9d, 1
0x1800136ca  sub     ecx, r9d
0x1800136cd  sub     ecx, dword ptr [rbp+var_18]
0x1800136d0  mov     eax, [r12+34h]
0x1800136d5  shr     eax, 1
0x1800136d7  shr     r8d, 1
0x1800136da  sub     eax, r8d
0x1800136dd  sub     eax, dword ptr [rbp+var_18+4]
0x1800136e0  imul    ecx, ecx
0x1800136e3  imul    eax, eax
0x1800136e6  lea     edx, [rcx+rax]
0x1800136e9  cmp     edx, [rbp+var_30]
0x1800136ec  jge     short loc_1800136F5
0x1800136ee  mov     [rbp+var_30], edx
0x1800136f1  mov     [rbp+var_28], r15d
0x1800136f5  lea     rcx, [rbp+var_20]
0x1800136f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800136fe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180013703  cmp     al, 20h ; ' '
0x180013705  jb      short loc_180013735
0x180013707  mov     ecx, dword ptr [rbp+var_18+0Ch]
0x18001370a  shr     ecx, 1
0x18001370c  add     ecx, dword ptr [rbp+var_18+4]
0x18001370f  mov     eax, dword ptr [rbp+var_18+8]
0x180013712  shr     eax, 1
0x180013714  add     eax, dword ptr [rbp+var_18]
0x180013717  mov     [rsp+70h+var_48], ecx
0x18001371b  mov     [rsp+70h+var_50], eax
0x18001371f  mov     r9d, r15d
0x180013722  mov     rcx, cs:WPP_GLOBAL_Control
0x180013729  mov     rcx, [rcx+0D8h]
0x180013730  call    WPP_SF_ddd
0x180013735  inc     r15d
0x180013738  jmp     loc_18001361B
0x18001373d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013742  cmp     al, 1
0x180013744  jb      loc_18001383C
0x18001374a  mov     edx, 108h
0x18001374f  jmp     short loc_180013763
0x180013751  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180013756  cmp     al, 1
0x180013758  jb      loc_18001383C
0x18001375e  mov     edx, 107h
0x180013763  mov     [rsp+70h+var_50], ebx
0x180013767  mov     r9, r14
0x18001376a  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180013771  mov     rcx, cs:WPP_GLOBAL_Control
0x180013778  mov     rcx, [rcx+10h]
0x18001377c  call    WPP_SF_qD
0x180013781  jmp     loc_18001383C
0x180013786  cmp     byte ptr [r12+81h], 0
0x18001378f  jz      short loc_1800137AC
0x180013791  mov     ecx, [rbp+var_2C]
0x180013794  movd    xmm0, dword ptr [rsi+rcx*4]
0x180013799  cvtdq2pd xmm0, xmm0
0x18001379d  mulsd   xmm0, cs:__real@3ff8000000000000
0x1800137a5  cvttsd2si eax, xmm0
0x1800137a9  mov     [rsi+rcx*4], eax
0x1800137ac  mov     ecx, [rbp+var_28]
0x1800137af  movd    xmm0, dword ptr [rsi+rcx*4]
0x1800137b4  cvtdq2pd xmm0, xmm0
0x1800137b8  mulsd   xmm0, cs:__real@4004000000000000
0x1800137c0  cvttsd2si eax, xmm0
0x1800137c4  mov     [rsi+rcx*4], eax
0x1800137c7  xor     r14d, r14d
0x1800137ca  xor     edi, edi
0x1800137cc  mov     ecx, [rbp+var_40]
0x1800137cf  test    ecx, ecx
0x1800137d1  jz      short loc_180013810
0x1800137d3  cmp     [rsi+rdi*4], r14d
0x1800137d7  jle     short loc_1800137E1
0x1800137d9  mov     r14d, [rsi+rdi*4]
0x1800137dd  mov     [r13+0], edi
0x1800137e1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800137e6  cmp     al, 20h ; ' '
0x1800137e8  jb      short loc_18001380A
0x1800137ea  mov     eax, [rsi+rdi*4]
0x1800137ed  mov     [rsp+70h+var_50], eax
0x1800137f1  mov     r9d, edi
0x1800137f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137fb  mov     rcx, [rcx+0D8h]
0x180013802  call    WPP_SF_dL
0x180013807  mov     ecx, [rbp+var_40]
0x18001380a  inc     edi
0x18001380c  cmp     edi, ecx
0x18001380e  jb      short loc_1800137D3
0x180013810  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180013815  cmp     al, 20h ; ' '
0x180013817  jb      short loc_18001383C
0x180013819  mov     edx, 10Bh
0x18001381e  mov     r9d, [r13+0]
0x180013822  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180013829  mov     rcx, cs:WPP_GLOBAL_Control
0x180013830  mov     rcx, [rcx+0D8h]
0x180013837  call    WPP_SF_d
0x18001383c  mov     rcx, rsi; pv
0x18001383f  call    cs:__imp_CoTaskMemFree
0x180013845  nop
0x180013846  lea     rcx, [rbp+var_20]
0x18001384a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001384f  mov     eax, ebx
0x180013851  mov     rcx, [rbp+var_8]
0x180013855  xor     rcx, rsp; StackCookie
0x180013858  call    __security_check_cookie
0x18001385d  mov     rbx, [rsp+70h+arg_18]
0x180013865  add     rsp, 70h
0x180013869  pop     r15
0x18001386b  pop     r14
0x18001386d  pop     r13
0x18001386f  pop     r12
0x180013871  pop     rdi
0x180013872  pop     rsi
0x180013873  pop     rbp
0x180013874  retn
```

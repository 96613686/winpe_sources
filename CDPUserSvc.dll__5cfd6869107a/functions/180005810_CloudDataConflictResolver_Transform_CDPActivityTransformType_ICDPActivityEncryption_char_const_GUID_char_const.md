# CloudDataConflictResolver::Transform(CDPActivityTransformType,ICDPActivityEncryption *,char const *,_GUID,char const *,ICDPCrossPlatformAppId *,char const *,ICDPActivityTransformResult * *)

- ea: `0x180005810`
- end: `0x180005b78`
- name: `?Transform@CloudDataConflictResolver@@UEAAJW4CDPActivityTransformType@@PEAVICDPActivityEncryption@@PEBDU_GUID@@2PEAVICDPCrossPlatformAppId@@2PEAPEAVICDPActivityTransformResult@@@Z`
- size: `872`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003678`
- `0x180005810`
- `0x180005b80`
- `0x180005c64`
- `0x18002c5e4`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005b58`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CloudDataConflictResolver::Transform(
        CloudDataConflictResolver *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v13; // rbx
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64, __int64, _OWORD *, __int64, __int64, __int64, __int64 **); // r10
  int v19; // eax
  int v20; // edx
  int v21; // ecx
  __int64 *v22; // r14
  _QWORD *v23; // rax
  int v24; // edx
  int v25; // ecx
  _QWORD *v26; // rsi
  __int64 v27; // rax
  int v28; // eax
  int v29; // edx
  int v30; // ecx
  __int64 (__fastcall *v31)(__int64 *, _QWORD *); // r13
  void *v32; // r12
  int v33; // edi
  __int64 v34; // rax
  __int64 *v35; // rcx
  __int64 *v37; // rcx
  DWORD LastError; // edi
  int v39; // [rsp+50h] [rbp-31h] BYREF
  __int64 *v40; // [rsp+58h] [rbp-29h] BYREF
  __int64 v41; // [rsp+60h] [rbp-21h] BYREF
  _QWORD *v42; // [rsp+68h] [rbp-19h]
  _OWORD v43[5]; // [rsp+70h] [rbp-11h] BYREF

  v13 = a9;
  if ( !a9 )
  {
    LODWORD(a9) = -2147467261;
    v39 = 106;
    Log<long &,char const (&)[36],int>(
      (_DWORD)a1,
      a2,
      (unsigned int)&a9,
      (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
      (__int64)&v39);
    return (unsigned int)a9;
  }
  *a9 = 0;
  v14 = CloudDataConflictResolver::EnsureConflictResolverImpl(a1);
  if ( v14 < 0 )
  {
    LODWORD(a9) = v14;
    v39 = 109;
    Log<long &,char const (&)[36],int>(
      v16,
      v15,
      (unsigned int)&a9,
      (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
      (__int64)&v39);
    return (unsigned int)a9;
  }
  v40 = 0;
  v17 = *((_QWORD *)a1 + 12);
  v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _OWORD *, __int64, __int64, __int64, __int64 **))(*(_QWORD *)v17 + 48LL);
  v43[0] = *a5;
  v19 = v18(v17, a2, a3, a4, v43, a6, a7, a8, &v40);
  if ( v19 >= 0 )
  {
    v41 = 0;
    v22 = v40;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v41 = 0;
    v23 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v26 = v23;
    v42 = v23;
    if ( !v23 )
    {
      v33 = -2147024882;
      goto LABEL_19;
    }
    *v23 = &ICDPActivityTransformResult::`vftable';
    *((_DWORD *)v23 + 3) = 1;
    *v23 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPActivityTransformResult>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v26 = &CloudDataTransformResult::`vftable';
    v26[3] = 0;
    v26[4] = 0;
    *(_QWORD *)&v43[0] = v26;
    v42 = 0;
    v27 = *v22;
    v26[3] = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 *))(v27 + 24))(v22);
    if ( v28 < 0 )
    {
      v39 = 183;
    }
    else
    {
      v31 = *(__int64 (__fastcall **)(__int64 *, _QWORD *))(*v22 + 40);
      v32 = (void *)v26[4];
      if ( v32 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v32);
        SetLastError(LastError);
      }
      v26[4] = 0;
      v28 = v31(v22, v26 + 4);
      if ( v28 >= 0 )
      {
LABEL_11:
        v33 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v26)(
                v26,
                &GUID_0bf16d05_5d24_4e0f_8fa1_88908a290a55,
                &v41);
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
        if ( v33 >= 0 )
        {
          v34 = v41;
          v41 = 0;
          *v13 = v34;
          v35 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
          }
          return 0;
        }
LABEL_19:
        LODWORD(a9) = v33;
        v39 = 116;
        Log<long &,char const (&)[36],int>(
          v25,
          v24,
          (unsigned int)&a9,
          (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
          (__int64)&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        return (unsigned int)a9;
      }
      v39 = 184;
    }
    LODWORD(a9) = v28;
    Log<long &,char const (&)[36],int>(
      v30,
      v29,
      (unsigned int)&a9,
      (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
      (__int64)&v39);
    v33 = (int)a9;
    if ( (int)a9 < 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      goto LABEL_19;
    }
    goto LABEL_11;
  }
  LODWORD(a9) = v19;
  v39 = 113;
  Log<long &,char const (&)[36],int>(
    v21,
    v20,
    (unsigned int)&a9,
    (unsigned int)"..\\cdpclouddataconflictresolver.cpp",
    (__int64)&v39);
  v37 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  }
  return (unsigned int)a9;
}

```

## disassembly

```asm
0x180005810  push    rbp
0x180005812  push    rbx
0x180005813  push    rsi
0x180005814  push    rdi
0x180005815  push    r12
0x180005817  push    r13
0x180005819  push    r14
0x18000581b  push    r15
0x18000581d  lea     rbp, [rsp-7]
0x180005822  sub     rsp, 88h
0x180005829  mov     rsi, r9
0x18000582c  mov     r14, r8
0x18000582f  mov     r15d, edx
0x180005832  mov     rdi, rcx
0x180005835  mov     rbx, [rbp+3Fh+arg_40]
0x18000583c  test    rbx, rbx
0x18000583f  jz      loc_180005A95
0x180005845  xor     r12d, r12d
0x180005848  mov     [rbx], r12
0x18000584b  call    ?EnsureConflictResolverImpl@CloudDataConflictResolver@@AEAAJXZ; CloudDataConflictResolver::EnsureConflictResolverImpl(void)
0x180005850  test    eax, eax
0x180005852  js      loc_180005B19
0x180005858  mov     [rbp+3Fh+var_68], r12
0x18000585c  mov     rcx, [rdi+60h]
0x180005860  mov     rax, [rcx]
0x180005863  mov     r10, [rax+30h]
0x180005867  mov     rax, [rbp+3Fh+arg_20]
0x18000586b  movups  xmm0, xmmword ptr [rax]
0x18000586e  movaps  [rbp+3Fh+var_50], xmm0
0x180005872  lea     rax, [rbp+3Fh+var_68]
0x180005876  mov     [rsp+0C0h+var_80], rax
0x18000587b  mov     rdx, [rbp+3Fh+arg_38]
0x180005882  mov     [rsp+0C0h+var_88], rdx
0x180005887  mov     rdx, [rbp+3Fh+arg_30]
0x18000588b  mov     [rsp+0C0h+var_90], rdx
0x180005890  mov     rdx, [rbp+3Fh+arg_28]
0x180005894  mov     [rsp+0C0h+var_98], rdx
0x180005899  lea     rax, [rbp+3Fh+var_50]
0x18000589d  mov     [rsp+0C0h+var_A0], rax
0x1800058a2  mov     r9, rsi
0x1800058a5  mov     r8, r14
0x1800058a8  mov     edx, r15d
0x1800058ab  mov     rax, r10
0x1800058ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b3  test    eax, eax
0x1800058b5  js      loc_1800059FC
0x1800058bb  mov     [rbp+3Fh+var_60], r12
0x1800058bf  mov     r14, [rbp+3Fh+var_68]
0x1800058c3  lea     rcx, [rbp+3Fh+var_60]
0x1800058c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800058cc  mov     [rbp+3Fh+var_60], r12
0x1800058d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800058d7  mov     ecx, 28h ; '('; unsigned __int64
0x1800058dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800058e1  mov     rsi, rax
0x1800058e4  mov     [rbp+3Fh+var_58], rax
0x1800058e8  test    rax, rax
0x1800058eb  jz      loc_180005A48
0x1800058f1  lea     rax, ??_7ICDPActivityTransformResult@@6B@; const ICDPActivityTransformResult::`vftable'
0x1800058f8  mov     [rsi], rax
0x1800058fb  mov     dword ptr [rsi+0Ch], 1
0x180005902  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VICDPActivityTransformResult@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICDPActivityTransformResult>::`vftable'
0x180005909  mov     [rsi], rax
0x18000590c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005913  test    rcx, rcx
0x180005916  jz      short loc_180005925
0x180005918  mov     rax, [rcx]
0x18000591b  mov     rax, [rax+8]
0x18000591f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005924  nop
0x180005925  lea     rax, ??_7CloudDataTransformResult@@6B@; const CloudDataTransformResult::`vftable'
0x18000592c  mov     [rsi], rax
0x18000592f  lea     rdx, [rsi+18h]
0x180005933  mov     [rdx], r12
0x180005936  mov     [rsi+20h], r12
0x18000593a  mov     qword ptr [rbp+3Fh+var_50], rsi
0x18000593e  mov     [rbp+3Fh+var_58], r12
0x180005942  mov     rax, [r14]
0x180005945  mov     [rdx], r12
0x180005948  mov     rcx, r14
0x18000594b  mov     rax, [rax+18h]
0x18000594f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005954  test    eax, eax
0x180005956  js      loc_180005ACD
0x18000595c  mov     rax, [r14]
0x18000595f  mov     r13, [rax+28h]
0x180005963  mov     r12, [rsi+20h]
0x180005967  test    r12, r12
0x18000596a  jnz     loc_180005B4D
0x180005970  xor     r12d, r12d
0x180005973  mov     [rsi+20h], r12
0x180005977  lea     rdx, [rsi+20h]
0x18000597b  mov     rcx, r14
0x18000597e  mov     rax, r13
0x180005981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005986  test    eax, eax
0x180005988  js      loc_180005B6B
0x18000598e  mov     rax, [rsi]
0x180005991  lea     r8, [rbp+3Fh+var_60]
0x180005995  lea     rdx, _GUID_0bf16d05_5d24_4e0f_8fa1_88908a290a55
0x18000599c  mov     rcx, rsi
0x18000599f  mov     rax, [rax]
0x1800059a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a7  mov     edi, eax
0x1800059a9  mov     rcx, [rsi]
0x1800059ac  mov     rax, [rcx+10h]
0x1800059b0  mov     rcx, rsi
0x1800059b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b8  nop
0x1800059b9  test    edi, edi
0x1800059bb  js      loc_180005A4D
0x1800059c1  mov     rax, [rbp+3Fh+var_60]
0x1800059c5  mov     [rbp+3Fh+var_60], r12
0x1800059c9  mov     [rbx], rax
0x1800059cc  mov     rcx, [rbp+3Fh+var_68]
0x1800059d0  test    rcx, rcx
0x1800059d3  jz      short loc_1800059E6
0x1800059d5  mov     [rbp+3Fh+var_68], r12
0x1800059d9  mov     rax, [rcx]
0x1800059dc  mov     rax, [rax+10h]
0x1800059e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e5  nop
0x1800059e6  xor     eax, eax
0x1800059e8  add     rsp, 88h
0x1800059ef  pop     r15
0x1800059f1  pop     r14
0x1800059f3  pop     r13
0x1800059f5  pop     r12
0x1800059f7  pop     rdi
0x1800059f8  pop     rsi
0x1800059f9  pop     rbx
0x1800059fa  pop     rbp
0x1800059fb  retn
0x1800059fc  mov     dword ptr [rbp+3Fh+arg_40], eax
0x180005a02  mov     [rbp+3Fh+var_70], 71h ; 'q'
0x180005a09  lea     rax, [rbp+3Fh+var_70]
0x180005a0d  mov     [rsp+0C0h+var_A0], rax
0x180005a12  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005a19  lea     r8, [rbp+3Fh+arg_40]
0x180005a20  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005a25  nop
0x180005a26  mov     rcx, [rbp+3Fh+var_68]
0x180005a2a  test    rcx, rcx
0x180005a2d  jz      short loc_180005A40
0x180005a2f  mov     [rbp+3Fh+var_68], r12
0x180005a33  mov     rdx, [rcx]
0x180005a36  mov     rax, [rdx+10h]
0x180005a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3f  nop
0x180005a40  mov     eax, dword ptr [rbp+3Fh+arg_40]
0x180005a46  jmp     short loc_1800059E8
0x180005a48  mov     edi, 8007000Eh
0x180005a4d  mov     dword ptr [rbp+3Fh+arg_40], edi
0x180005a53  mov     [rbp+3Fh+var_70], 74h ; 't'
0x180005a5a  lea     rax, [rbp+3Fh+var_70]
0x180005a5e  mov     [rsp+0C0h+var_A0], rax
0x180005a63  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005a6a  lea     r8, [rbp+3Fh+arg_40]
0x180005a71  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005a76  nop
0x180005a77  lea     rcx, [rbp+3Fh+var_60]
0x180005a7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005a80  nop
0x180005a81  lea     rcx, [rbp+3Fh+var_68]
0x180005a85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005a8a  mov     eax, dword ptr [rbp+3Fh+arg_40]
0x180005a90  jmp     loc_1800059E8
0x180005a95  mov     dword ptr [rbp+3Fh+arg_40], 80004003h
0x180005a9f  mov     [rbp+3Fh+var_70], 6Ah ; 'j'
0x180005aa6  lea     rax, [rbp+3Fh+var_70]
0x180005aaa  mov     [rsp+0C0h+var_A0], rax
0x180005aaf  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005ab6  lea     r8, [rbp+3Fh+arg_40]
0x180005abd  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005ac2  mov     eax, dword ptr [rbp+3Fh+arg_40]
0x180005ac8  jmp     loc_1800059E8
0x180005acd  mov     [rbp+3Fh+var_70], 0B7h
0x180005ad4  mov     dword ptr [rbp+3Fh+arg_40], eax
0x180005ada  lea     rax, [rbp+3Fh+var_70]
0x180005ade  mov     [rsp+0C0h+var_A0], rax
0x180005ae3  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005aea  lea     r8, [rbp+3Fh+arg_40]
0x180005af1  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005af6  mov     edi, dword ptr [rbp+3Fh+arg_40]
0x180005afc  test    edi, edi
0x180005afe  jns     loc_18000598E
0x180005b04  mov     rax, [rsi]
0x180005b07  mov     rcx, rsi
0x180005b0a  mov     rax, [rax+10h]
0x180005b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b13  nop
0x180005b14  jmp     loc_180005A4D
0x180005b19  mov     dword ptr [rbp+3Fh+arg_40], eax
0x180005b1f  mov     [rbp+3Fh+var_70], 6Dh ; 'm'
0x180005b26  lea     rax, [rbp+3Fh+var_70]
0x180005b2a  mov     [rsp+0C0h+var_A0], rax
0x180005b2f  lea     r9, aCdpclouddataco; "..\\cdpclouddataconflictresolver.cpp"
0x180005b36  lea     r8, [rbp+3Fh+arg_40]
0x180005b3d  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180005b42  mov     eax, dword ptr [rbp+3Fh+arg_40]
0x180005b48  jmp     loc_1800059E8
0x180005b4d  call    cs:__imp_GetLastError
0x180005b53  mov     edi, eax
0x180005b55  mov     rcx, r12; pv
0x180005b58  call    cs:__imp_CoTaskMemFree
0x180005b5e  mov     ecx, edi; dwErrCode
0x180005b60  call    cs:__imp_SetLastError
0x180005b66  jmp     loc_180005970
0x180005b6b  mov     [rbp+3Fh+var_70], 0B8h
0x180005b72  jmp     loc_180005AD4
```

# Broker::BackgroundAccessApplicationsWrapper::GetBackgroundAccessAppsForUser(void *)

- ea: `0x180006540`
- end: `0x180006a53`
- name: `?GetBackgroundAccessAppsForUser@BackgroundAccessApplicationsWrapper@Broker@@QEAA?AV?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@PEAX@Z`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c970`

## callees

- `0x180004e38`
- `0x180006540`
- `0x180006aa0`
- `0x180006cec`
- `0x180008430`
- `0x1800084a8`
- `0x180009e94`
- `0x18000ab10`
- `0x18000fe88`
- `0x18000ff94`
- `0x180012cd0`
- `0x180014898`
- `0x180015af0`
- `0x180015b58`
- `0x1800165b6`
- `0x1800165da`
- `0x180019d48`
- `0x18001e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800066fc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800066fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006627`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000686f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000686f`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000677e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000677e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Broker::BackgroundAccessApplicationsWrapper::GetBackgroundAccessAppsForUser(
        __int64 a1,
        _QWORD *a2,
        void *a3)
{
  HRESULT v5; // eax
  unsigned __int16 v6; // bx
  int v7; // eax
  unsigned __int16 v8; // bx
  int v9; // eax
  __int64 v10; // r8
  unsigned __int16 v11; // bx
  unsigned int i; // r15d
  _WORD *v13; // rsi
  unsigned __int64 v14; // rcx
  DWORD LengthSid; // eax
  unsigned __int64 v16; // rdx
  void **v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  void **v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rcx
  void *v24; // rcx
  unsigned __int64 v25; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h]
  LPVOID v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  void *v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  void **pExceptionObject; // [rsp+78h] [rbp-88h] BYREF
  __int128 v39; // [rsp+80h] [rbp-80h]
  int v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+98h] [rbp-68h]
  _QWORD *v42; // [rsp+A0h] [rbp-60h]
  void *v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  char *v44; // [rsp+C0h] [rbp-40h]
  void *v45[2]; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID *v46; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v47; // [rsp+E0h] [rbp-20h]
  void *v48[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v49; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v50; // [rsp+100h] [rbp+0h]
  _BYTE v51[64]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR packageFamilyName[128]; // [rsp+150h] [rbp+50h] BYREF

  v42 = a2;
  v31 = 0;
  Broker::BinarySid::BinarySid((LPWSTR *)&hMem, a3);
  v34 = 0;
  v37 = 0;
  v29 = 0;
  v33 = 0;
  v32 = 0;
  v43[0] = off_18001F030;
  v43[1] = &v34;
  v44 = (char *)&v37;
  v45[0] = &v29;
  v45[1] = &v33;
  v46 = &v32;
  v48[0] = v43;
  Broker::UnwindHelper::UnwindHelper(v51, v43);
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v31 = 1;
  v5 = CoCreateInstance(&GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23, 0, 1u, &IID_IUserServiceProvider, &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids,
        (unsigned int)v5);
    v39 = 0;
    v40 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v41 = v6;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, HLOCAL, SID *, GUID *, __int64 *))(*(_QWORD *)v32 + 24LL))(
         v32,
         hMem,
         &SID_BackgroundAccessManagerService,
         &GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b,
         &v33);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(ppv) = v7;
      WPP_SF__sid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x13u,
        &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids,
        (char *)a3,
        ppv);
    }
    v39 = 0;
    v40 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v41 = v8;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  ppva = (LPVOID *)&v34;
  v9 = (*(__int64 (__fastcall **)(__int64, HLOCAL, unsigned int *, __int64 *))(*(_QWORD *)v33 + 144LL))(
         v33,
         hMem,
         &v29,
         &v37);
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LODWORD(ppva) = v9;
      WPP_SF__sid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x14u,
        &WPP_a9458e0debc7300a47110d600cc51ede_Traceguids,
        (char *)a3,
        ppva);
    }
    v39 = 0;
    v40 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v41 = v11;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  for ( i = 0; i < v29; ++i )
  {
    v13 = *(_WORD **)(v34 + 8LL * i);
    *(_OWORD *)v43 = 0;
    v44 = 0;
    *(_OWORD *)v45 = 0;
    v46 = 0;
    v47 = 7;
    LOWORD(v45[0]) = 0;
    *(_OWORD *)v48 = 0;
    v49 = 0;
    v14 = 7;
    v50 = 7;
    LOWORD(v48[0]) = 0;
    if ( a3 )
    {
      LengthSid = GetLengthSid(a3);
      std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(v43, v43[0], a3, LengthSid);
      v14 = v50;
    }
    if ( v13 )
    {
      packageFamilyNameLength[0] = 0;
      v16 = -1;
      do
        ++v16;
      while ( v13[v16] );
      if ( v16 > v14 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v48,
          v16,
          v10,
          v13,
          (_DWORD)ppva);
      }
      else
      {
        v17 = v48;
        if ( v14 > 7 )
          v17 = (void **)v48[0];
        v49 = v16;
        v18 = 2 * v16;
        memmove_0(v17, v13, 2 * v16);
        *(_WORD *)((char *)v17 + v18) = 0;
      }
      packageFamilyNameLength[0] = 128;
      if ( PackageFamilyNameFromFullName(v13, packageFamilyNameLength, packageFamilyName) )
      {
        std::wstring::assign(v45, v13);
      }
      else
      {
        v20 = -1;
        do
          ++v20;
        while ( packageFamilyName[v20] );
        if ( v20 > v47 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v45,
            v20,
            v19,
            packageFamilyName,
            (_DWORD)ppva);
        }
        else
        {
          v21 = v45;
          if ( v47 > 7 )
            v21 = (void **)v45[0];
          v46 = (LPVOID *)v20;
          v22 = 2 * v20;
          memmove_0(v21, packageFamilyName, 2 * v20);
          *(_WORD *)((char *)v21 + v22) = 0;
        }
      }
    }
    v23 = a2[1];
    if ( v23 == a2[2] )
    {
      std::vector<Broker::ApplicationIdentity>::_Emplace_reallocate<Broker::ApplicationIdentity>(a2, a2[1], v43);
    }
    else
    {
      Broker::ApplicationIdentity::ApplicationIdentity(v23, v43);
      a2[1] += 88LL;
    }
    if ( v50 > 7 )
      std::_Deallocate<16>(v48[0], 2 * v50 + 2);
    v49 = 0;
    v50 = 7;
    LOWORD(v48[0]) = 0;
    if ( v47 > 7 )
      std::_Deallocate<16>(v45[0], 2 * v47 + 2);
    v46 = 0;
    v47 = 7;
    LOWORD(v45[0]) = 0;
    v24 = v43[0];
    if ( v43[0] )
    {
      v25 = v44 - (char *)v43[0];
      *(_QWORD *)packageFamilyNameLength = v44 - (char *)v43[0];
      v36 = v43[0];
      if ( (unsigned __int64)(v44 - (char *)v43[0]) >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v36, (unsigned __int64 *)packageFamilyNameLength);
        v25 = *(_QWORD *)packageFamilyNameLength;
        v24 = v36;
      }
      operator delete(v24, v25);
    }
  }
  Broker::UnwindHelper::~UnwindHelper((Broker::UnwindHelper *)v51);
  LocalFree(hMem);
  return a2;
}

```

## disassembly

```asm
0x180006540  mov     [rsp-8+arg_0], rbx
0x180006545  push    rbp
0x180006546  push    rsi
0x180006547  push    rdi
0x180006548  push    r12
0x18000654a  push    r13
0x18000654c  push    r14
0x18000654e  push    r15
0x180006550  lea     rbp, [rsp-160h]
0x180006558  sub     rsp, 260h
0x18000655f  mov     rax, cs:__security_cookie
0x180006566  xor     rax, rsp
0x180006569  mov     [rbp+190h+var_40], rax
0x180006570  mov     r12, r8
0x180006573  mov     r14, rdx
0x180006576  mov     [rbp+190h+var_1F0], rdx
0x18000657a  xor     r13d, r13d
0x18000657d  mov     [rsp+290h+var_250], r13d
0x180006582  mov     rdx, r8; Sid
0x180006585  lea     rcx, [rsp+290h+hMem]; StringSid
0x18000658a  call    ??0BinarySid@Broker@@QEAA@PEAX@Z; Broker::BinarySid::BinarySid(void *)
0x18000658f  nop
0x180006590  mov     [rsp+290h+var_238], r13
0x180006595  mov     [rsp+290h+var_220], r13
0x18000659a  mov     [rsp+290h+var_260], r13d
0x18000659f  mov     [rsp+290h+var_240], r13
0x1800065a4  mov     [rsp+290h+var_248], r13
0x1800065a9  lea     rax, off_18001F030
0x1800065b0  mov     [rbp+190h+var_1E0], rax
0x1800065b4  lea     rax, [rsp+290h+var_238]
0x1800065b9  mov     [rbp+190h+var_1E0+8], rax
0x1800065bd  lea     rax, [rsp+290h+var_220]
0x1800065c2  mov     [rbp+190h+var_1D0], rax
0x1800065c6  lea     rax, [rsp+290h+var_260]
0x1800065cb  mov     [rbp+190h+var_1C8], rax
0x1800065cf  lea     rax, [rsp+290h+var_240]
0x1800065d4  mov     [rbp+190h+var_1C8+8], rax
0x1800065d8  lea     rax, [rsp+290h+var_248]
0x1800065dd  mov     [rbp+190h+var_1B8], rax
0x1800065e1  lea     rax, [rbp+190h+var_1E0]
0x1800065e5  mov     [rbp+190h+var_1A8], rax
0x1800065e9  lea     rdx, [rbp+190h+var_1E0]
0x1800065ed  lea     rcx, [rbp+190h+var_180]
0x1800065f1  call    ??0UnwindHelper@Broker@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Broker::UnwindHelper::UnwindHelper(std::function<void (void)>)
0x1800065f6  nop
0x1800065f7  mov     [r14], r13
0x1800065fa  mov     [r14+8], r13
0x1800065fe  mov     [r14+10h], r13
0x180006602  lea     edi, [r13+1]
0x180006606  mov     [rsp+290h+var_250], edi
0x18000660a  lea     rax, [rsp+290h+var_248]
0x18000660f  mov     [rsp+290h+ppv], rax; ppv
0x180006614  lea     r9, IID_IUserServiceProvider; riid
0x18000661b  mov     r8d, edi; dwClsContext
0x18000661e  xor     edx, edx; pUnkOuter
0x180006620  lea     rcx, _GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23; rclsid
0x180006627  call    cs:__imp_CoCreateInstance
0x18000662d  mov     ebx, eax
0x18000662f  test    eax, eax
0x180006631  js      loc_180006941
0x180006637  mov     rcx, [rsp+290h+var_248]
0x18000663c  mov     rax, [rcx]
0x18000663f  lea     rdx, [rsp+290h+var_240]
0x180006644  mov     [rsp+290h+ppv], rdx
0x180006649  lea     r9, _GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b
0x180006650  lea     r8, SID_BackgroundAccessManagerService
0x180006657  mov     rdx, [rsp+290h+hMem]
0x18000665c  mov     rax, [rax+18h]
0x180006660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006665  mov     ebx, eax
0x180006667  test    eax, eax
0x180006669  js      loc_1800068CE
0x18000666f  mov     rcx, [rsp+290h+var_240]
0x180006674  mov     rax, [rcx]
0x180006677  lea     rdx, [rsp+290h+var_238]
0x18000667c  mov     [rsp+290h+ppv], rdx
0x180006681  lea     r9, [rsp+290h+var_220]
0x180006686  lea     r8, [rsp+290h+var_260]
0x18000668b  mov     rdx, [rsp+290h+hMem]
0x180006690  mov     rax, [rax+90h]
0x180006697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669c  mov     ebx, eax
0x18000669e  test    eax, eax
0x1800066a0  js      loc_18000699D
0x1800066a6  mov     r15d, r13d
0x1800066a9  cmp     [rsp+290h+var_260], r13d
0x1800066ae  jbe     loc_180006860
0x1800066b4  lea     ebx, [rdi+6]
0x1800066b7  mov     ecx, r15d
0x1800066ba  mov     rax, [rsp+290h+var_238]
0x1800066bf  mov     rsi, [rax+rcx*8]
0x1800066c3  xorps   xmm0, xmm0
0x1800066c6  movdqa  xmmword ptr [rbp+190h+var_1E0], xmm0
0x1800066cb  mov     [rbp+190h+var_1D0], r13
0x1800066cf  movups  xmmword ptr [rbp+190h+var_1C8], xmm0
0x1800066d3  mov     [rbp+190h+var_1B8], r13
0x1800066d7  mov     [rbp+190h+var_1B0], rbx
0x1800066db  mov     word ptr [rbp+190h+var_1C8], r13w
0x1800066e0  movups  xmmword ptr [rbp+190h+var_1A8], xmm0
0x1800066e4  mov     [rbp+190h+var_198], r13
0x1800066e8  mov     rcx, rbx
0x1800066eb  mov     [rbp+190h+var_190], rbx
0x1800066ef  mov     word ptr [rbp+190h+var_1A8], r13w
0x1800066f4  test    r12, r12
0x1800066f7  jz      short loc_180006719
0x1800066f9  mov     rcx, r12; pSid
0x1800066fc  call    cs:__imp_GetLengthSid
0x180006702  mov     r9d, eax
0x180006705  mov     r8, r12
0x180006708  mov     rdx, [rbp+190h+var_1E0]
0x18000670c  lea     rcx, [rbp+190h+var_1E0]
0x180006710  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x180006715  mov     rcx, [rbp+190h+var_190]
0x180006719  test    rsi, rsi
0x18000671c  jz      loc_1800067D1
0x180006722  mov     [rsp+290h+packageFamilyNameLength], r13d
0x180006727  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000672b  inc     rdx
0x18000672e  cmp     [rsi+rdx*2], r13w
0x180006733  jnz     short loc_18000672B
0x180006735  cmp     rdx, rcx
0x180006738  ja      loc_1800069FD
0x18000673e  lea     rdi, [rbp+190h+var_1A8]
0x180006742  cmp     rcx, rbx
0x180006745  cmova   rdi, [rbp+190h+var_1A8]
0x18000674a  mov     [rbp+190h+var_198], rdx
0x18000674e  lea     rbx, [rdx+rdx]
0x180006752  mov     r8, rbx; Size
0x180006755  mov     rdx, rsi; Src
0x180006758  mov     rcx, rdi; void *
0x18000675b  call    memmove_0
0x180006760  mov     [rdi+rbx], r13w
0x180006765  mov     ebx, 7
0x18000676a  mov     [rsp+290h+packageFamilyNameLength], 80h
0x180006772  lea     r8, [rbp+190h+packageFamilyName]; packageFamilyName
0x180006776  lea     rdx, [rsp+290h+packageFamilyNameLength]; packageFamilyNameLength
0x18000677b  mov     rcx, rsi; packageFullName
0x18000677e  call    cs:__imp_PackageFamilyNameFromFullName
0x180006784  test    eax, eax
0x180006786  jnz     loc_18000690C
0x18000678c  lea     rax, [rbp+190h+packageFamilyName]
0x180006790  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006794  inc     rdx
0x180006797  cmp     [rax+rdx*2], r13w
0x18000679c  jnz     short loc_180006794
0x18000679e  cmp     rdx, [rbp+190h+var_1B0]
0x1800067a2  ja      loc_180006A0E
0x1800067a8  lea     rdi, [rbp+190h+var_1C8]
0x1800067ac  cmp     [rbp+190h+var_1B0], rbx
0x1800067b0  cmova   rdi, [rbp+190h+var_1C8]
0x1800067b5  mov     [rbp+190h+var_1B8], rdx
0x1800067b9  lea     rbx, [rdx+rdx]
0x1800067bd  mov     r8, rbx; Size
0x1800067c0  lea     rdx, [rbp+190h+packageFamilyName]; Src
0x1800067c4  mov     rcx, rdi; void *
0x1800067c7  call    memmove_0
0x1800067cc  mov     [rdi+rbx], r13w
0x1800067d1  mov     rcx, [r14+8]
0x1800067d5  cmp     rcx, [r14+10h]
0x1800067d9  jz      loc_180006A20
0x1800067df  lea     rdx, [rbp+190h+var_1E0]
0x1800067e3  call    ??0ApplicationIdentity@Broker@@QEAA@$$QEAU01@@Z; Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity &&)
0x1800067e8  add     qword ptr [r14+8], 58h ; 'X'
0x1800067ed  mov     rdx, [rbp+190h+var_190]
0x1800067f1  mov     ebx, 7
0x1800067f6  cmp     rdx, rbx
0x1800067f9  ja      loc_1800068A2
0x1800067ff  mov     [rbp+190h+var_198], r13
0x180006803  mov     [rbp+190h+var_190], rbx
0x180006807  mov     word ptr [rbp+190h+var_1A8], r13w
0x18000680c  mov     rdx, [rbp+190h+var_1B0]
0x180006810  cmp     rdx, rbx
0x180006813  ja      loc_1800068B8
0x180006819  mov     [rbp+190h+var_1B8], r13
0x18000681d  mov     [rbp+190h+var_1B0], rbx
0x180006821  mov     word ptr [rbp+190h+var_1C8], r13w
0x180006826  mov     rcx, [rbp+190h+var_1E0]; void *
0x18000682a  test    rcx, rcx
0x18000682d  jz      short loc_180006852
0x18000682f  mov     rdx, [rbp+190h+var_1D0]
0x180006833  sub     rdx, rcx; unsigned __int64
0x180006836  mov     qword ptr [rsp+290h+packageFamilyNameLength], rdx
0x18000683b  mov     [rsp+290h+var_228], rcx
0x180006840  cmp     rdx, 1000h
0x180006847  jnb     loc_180006A34
0x18000684d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006852  inc     r15d
0x180006855  cmp     r15d, [rsp+290h+var_260]
0x18000685a  jb      loc_1800066B7
0x180006860  lea     rcx, [rbp+190h+var_180]; this
0x180006864  call    ??1UnwindHelper@Broker@@QEAA@XZ; Broker::UnwindHelper::~UnwindHelper(void)
0x180006869  nop
0x18000686a  mov     rcx, [rsp+290h+hMem]; hMem
0x18000686f  call    cs:__imp_LocalFree
0x180006875  mov     rax, r14
0x180006878  mov     rcx, [rbp+190h+var_40]
0x18000687f  xor     rcx, rsp; StackCookie
0x180006882  call    __security_check_cookie
0x180006887  mov     rbx, [rsp+290h+arg_0]
0x18000688f  add     rsp, 260h
0x180006896  pop     r15
0x180006898  pop     r14
0x18000689a  pop     r13
0x18000689c  pop     r12
0x18000689e  pop     rdi
0x18000689f  pop     rsi
0x1800068a0  pop     rbp
0x1800068a1  retn
0x1800068a2  lea     rdx, ds:2[rdx*2]
0x1800068aa  mov     rcx, [rbp+190h+var_1A8]
0x1800068ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800068b3  jmp     loc_1800067FF
0x1800068b8  lea     rdx, ds:2[rdx*2]
0x1800068c0  mov     rcx, [rbp+190h+var_1C8]
0x1800068c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800068c9  jmp     loc_180006819
0x1800068ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068d5  test    dword ptr [rcx+1Ch], 400h
0x1800068dc  jnz     short loc_18000691D
0x1800068de  xorps   xmm0, xmm0
0x1800068e1  movups  [rbp+190h+var_210], xmm0
0x1800068e5  mov     [rbp+190h+var_200], edi
0x1800068e8  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800068ef  mov     [rsp+290h+pExceptionObject], rax
0x1800068f4  movzx   eax, bx
0x1800068f7  mov     [rbp+190h+var_1F8], eax
0x1800068fa  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180006901  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x180006906  call    _CxxThrowException_0
0x18000690c  mov     rdx, rsi
0x18000690f  lea     rcx, [rbp+190h+var_1C8]
0x180006913  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180006918  jmp     loc_1800067D1
0x18000691d  cmp     byte ptr [rcx+19h], 2
0x180006921  jb      short loc_1800068DE
0x180006923  mov     edx, 13h
0x180006928  mov     dword ptr [rsp+290h+ppv], ebx; char
0x18000692c  mov     r9, r12
0x18000692f  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180006936  mov     rcx, [rcx+10h]; LoggerHandle
0x18000693a  call    WPP_SF__sid_d
0x18000693f  jmp     short loc_1800068DE
0x180006941  mov     rcx, cs:WPP_GLOBAL_Control
0x180006948  test    dword ptr [rcx+1Ch], 400h
0x18000694f  jz      short loc_18000696F
0x180006951  cmp     byte ptr [rcx+19h], 2
0x180006955  jb      short loc_18000696F
0x180006957  mov     edx, 12h
0x18000695c  mov     r9d, ebx
0x18000695f  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x180006966  mov     rcx, [rcx+10h]
0x18000696a  call    WPP_SF_d
0x18000696f  xorps   xmm0, xmm0
0x180006972  movups  [rbp+190h+var_210], xmm0
0x180006976  mov     [rbp+190h+var_200], edi
0x180006979  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180006980  mov     [rsp+290h+pExceptionObject], rax
0x180006985  movzx   eax, bx
0x180006988  mov     [rbp+190h+var_1F8], eax
0x18000698b  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180006992  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x180006997  call    _CxxThrowException_0
0x18000699d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069a4  test    dword ptr [rcx+1Ch], 400h
0x1800069ab  jz      short loc_1800069CF
0x1800069ad  cmp     byte ptr [rcx+19h], 2
0x1800069b1  jb      short loc_1800069CF
0x1800069b3  mov     edx, 14h
0x1800069b8  mov     dword ptr [rsp+290h+ppv], ebx; char
0x1800069bc  mov     r9, r12
0x1800069bf  lea     r8, WPP_a9458e0debc7300a47110d600cc51ede_Traceguids
0x1800069c6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800069ca  call    WPP_SF__sid_d
0x1800069cf  xorps   xmm0, xmm0
0x1800069d2  movups  [rbp+190h+var_210], xmm0
0x1800069d6  mov     [rbp+190h+var_200], edi
0x1800069d9  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800069e0  mov     [rsp+290h+pExceptionObject], rax
0x1800069e5  movzx   eax, bx
0x1800069e8  mov     [rbp+190h+var_1F8], eax
0x1800069eb  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800069f2  lea     rcx, [rsp+290h+pExceptionObject]; pExceptionObject
0x1800069f7  call    _CxxThrowException_0
0x1800069fd  mov     r9, rsi
0x180006a00  lea     rcx, [rbp+190h+var_1A8]
0x180006a04  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180006a09  jmp     loc_18000676A
0x180006a0e  lea     r9, [rbp+190h+packageFamilyName]
0x180006a12  lea     rcx, [rbp+190h+var_1C8]
0x180006a16  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180006a1b  jmp     loc_1800067D1
0x180006a20  lea     r8, [rbp+190h+var_1E0]
0x180006a24  mov     rdx, rcx
0x180006a27  mov     rcx, r14
0x180006a2a  call    ??$_Emplace_reallocate@UApplicationIdentity@Broker@@@?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@AEAAPEAUApplicationIdentity@Broker@@QEAU23@$$QEAU23@@Z; std::vector<Broker::ApplicationIdentity>::_Emplace_reallocate<Broker::ApplicationIdentity>(Broker::ApplicationIdentity * const,Broker::ApplicationIdentity &&)
0x180006a2f  jmp     loc_1800067ED
0x180006a34  lea     rdx, [rsp+290h+packageFamilyNameLength]; unsigned __int64 *
0x180006a39  lea     rcx, [rsp+290h+var_228]; void **
0x180006a3e  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180006a43  mov     rdx, qword ptr [rsp+290h+packageFamilyNameLength]
  ... truncated ...
```

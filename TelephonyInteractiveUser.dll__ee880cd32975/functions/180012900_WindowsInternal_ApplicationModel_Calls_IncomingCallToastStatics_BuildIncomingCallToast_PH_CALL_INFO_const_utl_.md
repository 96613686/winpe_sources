# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToast(PH_CALL_INFO const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,IBrandingInfo *)

- ea: `0x180012900`
- end: `0x180012ea6`
- name: `?_BuildIncomingCallToast@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJAEBUPH_CALL_INFO@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAUIBrandingInfo@@@Z`
- size: `1446`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, struct IBrandingInfo *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x1800027c0`
- `0x180004a0c`
- `0x180004b4c`
- `0x180005a90`
- `0x180011e68`
- `0x180012900`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012c1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012c8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012c1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180012c8f`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180012b4e`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180012b4e`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x180012aec`
- `PhoneOm!PhoneGetProviderLineInfo` at `0x180012aec`
- `PhoneUtil!CreateBrandingInfo` at `0x180012b05`
- `PhoneUtil!CreateBrandingInfo` at `0x180012b05`
- `dmxmlhelputils!XMLHEscapeString` at `0x180012bf9`
- `dmxmlhelputils!XMLHEscapeString` at `0x180012bf9`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToast(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        struct IBrandingInfo *a4)
{
  __int64 v4; // rax
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 (__fastcall *v12)(__int64 *, __int64, __int64, void **); // rax
  int v13; // eax
  __int64 v14; // r8
  int ProviderLineInfo; // esi
  void *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r9
  struct IBrandingInfo *v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 **v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  void *v28; // rdi
  void *v29; // rsi
  __int64 (__fastcall *v30)(__int64 *, __int64, void *, __int64, __int64, __int64, __int64, void *, void *, __int64); // r14
  __int64 v31; // rbx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // r8
  unsigned int v35; // edi
  struct IBrandingInfo *v36; // rcx
  void *v37; // rcx
  bool v38; // zf
  __int64 v39; // r8
  struct IBrandingInfo *v40; // rcx
  struct IBrandingInfo *v41; // rcx
  struct IBrandingInfo *v44; // [rsp+70h] [rbp-90h] BYREF
  void *Block[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 v47; // [rsp+8Ah] [rbp-76h]
  int v48; // [rsp+92h] [rbp-6Eh]
  __int16 v49; // [rsp+96h] [rbp-6Ah]
  void *v50[2]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v51; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+AAh] [rbp-56h]
  int v53; // [rsp+B2h] [rbp-4Eh]
  __int16 v54; // [rsp+B6h] [rbp-4Ah]
  HLOCAL hMem; // [rsp+B8h] [rbp-48h] BYREF
  void *v56[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v57; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+D2h] [rbp-2Eh]
  int v59; // [rsp+DAh] [rbp-26h]
  __int16 v60; // [rsp+DEh] [rbp-22h]
  unsigned int v61[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v62[320]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v63[1616]; // [rsp+230h] [rbp+130h] BYREF

  v4 = *a1;
  if ( *(_DWORD *)(a2 + 3040) == 4 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v4 + 72))(a1, a2);
    v10 = v8;
    if ( v8 < 0 )
    {
      Log_HREvent_1((unsigned int)v8, 1, v9, 309);
      return v10;
    }
    return 0;
  }
  v12 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64, void **))(v4 + 176);
  Block[0] = &v46;
  v47 = 0;
  Block[1] = &v46;
  v48 = 0;
  v49 = 0;
  v46 = 0;
  v13 = v12(a1, 4, a2 + 3044, Block);
  ProviderLineInfo = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_1((unsigned int)v13, 1, v14, 315);
    v16 = Block[0];
    if ( Block[0] == &v46 )
      return (unsigned int)ProviderLineInfo;
LABEL_6:
    operator delete(v16);
    return (unsigned int)ProviderLineInfo;
  }
  v52 = 0;
  v50[0] = &v51;
  v53 = 0;
  v50[1] = &v51;
  v17 = *a1;
  v54 = 0;
  v51 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, void **))(v17 + 96))(a1, a2, v50);
  ProviderLineInfo = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_1((unsigned int)v18, 1, v19, 319);
    goto LABEL_10;
  }
  v44 = 0;
  memset_0(v63, 0, sizeof(v63));
  memset_0(v62, 0, 0x13Cu);
  if ( a4 )
  {
    (*(void (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)a4 + 8LL))(a4);
    v44 = a4;
  }
  else
  {
    ProviderLineInfo = CreateBrandingInfo(&v44);
    if ( ProviderLineInfo < 0 )
    {
      v21 = 331;
      goto LABEL_20;
    }
  }
  ProviderLineInfo = PhoneGetProviderLineInfo(a2 + 3060, v63);
  if ( ProviderLineInfo < 0 )
  {
    v21 = 334;
    goto LABEL_20;
  }
  ProviderLineInfo = PhoneGetProviderLineServiceInfo(a2 + 3060, v62);
  if ( ProviderLineInfo < 0 )
  {
    v21 = 335;
    goto LABEL_20;
  }
  v23 = 3;
  if ( *(_DWORD *)(a2 + 3016) != 1 )
    v23 = 1;
  ProviderLineInfo = (*(__int64 (__fastcall **)(struct IBrandingInfo *, __int64, _BYTE *, _BYTE *, _DWORD))(*(_QWORD *)v44 + 56LL))(
                       v44,
                       v23,
                       v63,
                       v62,
                       0);
  if ( ProviderLineInfo < 0 )
  {
    v21 = 340;
LABEL_20:
    Log_HREvent_1((unsigned int)ProviderLineInfo, 1, v20, v21);
    v22 = v44;
    if ( !v44 )
      goto LABEL_10;
    goto LABEL_36;
  }
  v58 = 0;
  v56[0] = &v57;
  v59 = 0;
  v56[1] = &v57;
  v60 = 0;
  v57 = 0;
  if ( *(_WORD *)(a2 + 1912) )
  {
    hMem = 0;
    v61[0] = 0;
    v24 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&hMem);
    ProviderLineInfo = XMLHEscapeString((const unsigned __int16 *)(a2 + 1912), v24, v61);
    if ( ProviderLineInfo < 0 )
    {
      v26 = 347;
      goto LABEL_31;
    }
    ProviderLineInfo = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                         v56,
                         L"file:///%s",
                         hMem);
    if ( ProviderLineInfo < 0 )
    {
      v26 = 349;
LABEL_31:
      Log_HREvent_1((unsigned int)ProviderLineInfo, 1, v25, v26);
      if ( hMem )
        LocalFree(hMem);
      if ( v56[0] != &v57 )
        operator delete(v56[0]);
      v22 = v44;
      if ( !v44 )
      {
LABEL_10:
        if ( v50[0] != &v51 )
          operator delete(v50[0]);
        v16 = Block[0];
        if ( Block[0] == &v46 )
          return (unsigned int)ProviderLineInfo;
        goto LABEL_6;
      }
LABEL_36:
      v44 = 0;
      (*(void (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_10;
    }
    if ( hMem )
      LocalFree(hMem);
  }
  else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                v56,
                                L"ms-winsoundevent:notification.looping.call") )
  {
    v35 = -2147024882;
    Log_HREvent_1(2147942414LL, 0, v39, 353);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    v40 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    if ( v50[0] != &v51 )
      operator delete(v50[0]);
    v37 = Block[0];
    v38 = Block[0] == &v46;
    goto LABEL_57;
  }
  v27 = *a1;
  v28 = v50[0];
  v29 = v56[0];
  v30 = *(__int64 (__fastcall **)(__int64 *, __int64, void *, __int64, __int64, __int64, __int64, void *, void *, __int64))(v27 + 88);
  v31 = (*(__int64 (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v44 + 24LL))(v44);
  v32 = (*(__int64 (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v44 + 32LL))(v44);
  v33 = v30(a1, a2 + 5784, Block[0], v32, v31, a2, a2 + 1392, v29, v28, a3);
  v35 = v33;
  if ( v33 >= 0 )
  {
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    v41 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( v50[0] != &v51 )
      operator delete(v50[0]);
    if ( Block[0] != &v46 )
      operator delete(Block[0]);
    return 0;
  }
  Log_HREvent_1((unsigned int)v33, 1, v34, 365);
  if ( v56[0] != &v57 )
    operator delete(v56[0]);
  v36 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct IBrandingInfo *))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( v50[0] != &v51 )
    operator delete(v50[0]);
  v37 = Block[0];
  v38 = Block[0] == &v46;
LABEL_57:
  if ( !v38 )
    operator delete(v37);
  return v35;
}

```

## disassembly

```asm
0x180012900  mov     [rsp-8+arg_18], rbx
0x180012905  push    rbp
0x180012906  push    rsi
0x180012907  push    rdi
0x180012908  push    r12
0x18001290a  push    r13
0x18001290c  push    r14
0x18001290e  push    r15
0x180012910  lea     rbp, [rsp-790h]
0x180012918  sub     rsp, 890h
0x18001291f  mov     rax, cs:__security_cookie
0x180012926  xor     rax, rsp
0x180012929  mov     [rbp+7C0h+var_40], rax
0x180012930  mov     rax, [rcx]
0x180012933  mov     r13, rdx
0x180012936  mov     edx, 4
0x18001293b  mov     [rsp+8C0h+var_860], r8
0x180012940  mov     rbx, r9
0x180012943  mov     [rsp+8C0h+var_858], rcx
0x180012948  mov     rdi, rcx
0x18001294b  cmp     [r13+0BE0h], edx
0x180012952  jnz     short loc_180012983
0x180012954  mov     rax, [rax+48h]
0x180012958  mov     rdx, r13
0x18001295b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012960  mov     ebx, eax
0x180012962  test    eax, eax
0x180012964  jns     loc_180012E7A
0x18001296a  mov     edx, 1
0x18001296f  mov     r9d, 135h
0x180012975  mov     ecx, eax
0x180012977  call    Log_HREvent_1
0x18001297c  mov     eax, ebx
0x18001297e  jmp     loc_180012E7C
0x180012983  mov     rax, [rax+0B0h]
0x18001298a  lea     rcx, [rbp+7C0h+var_838]
0x18001298e  xor     r15d, r15d
0x180012991  mov     [rsp+8C0h+Block], rcx
0x180012996  lea     rcx, [rbp+7C0h+var_838]
0x18001299a  mov     [rbp+7C0h+var_836], r15
0x18001299e  mov     [rbp+7C0h+var_840], rcx
0x1800129a2  lea     r8, [r13+0BE4h]
0x1800129a9  mov     rcx, rdi
0x1800129ac  mov     [rbp+7C0h+var_82E], r15d
0x1800129b0  lea     r9, [rsp+8C0h+Block]
0x1800129b5  mov     [rbp+7C0h+var_82A], r15w
0x1800129ba  mov     [rbp+7C0h+var_838], r15w
0x1800129bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129c4  mov     esi, eax
0x1800129c6  test    eax, eax
0x1800129c8  jns     short loc_1800129FC
0x1800129ca  lea     edx, [r15+1]
0x1800129ce  mov     r9d, 13Bh
0x1800129d4  mov     ecx, eax
0x1800129d6  call    Log_HREvent_1
0x1800129db  mov     rcx, [rsp+8C0h+Block]; Block
0x1800129e0  lea     rax, [rbp+7C0h+var_838]
0x1800129e4  cmp     rcx, rax
0x1800129e7  jz      short loc_1800129F5
0x1800129e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800129f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800129f5  mov     eax, esi
0x1800129f7  jmp     loc_180012E7C
0x1800129fc  lea     rax, [rbp+7C0h+var_818]
0x180012a00  mov     [rbp+7C0h+var_816], r15
0x180012a04  mov     [rbp+7C0h+var_828], rax
0x180012a08  lea     r8, [rbp+7C0h+var_828]
0x180012a0c  lea     rax, [rbp+7C0h+var_818]
0x180012a10  mov     [rbp+7C0h+var_80E], r15d
0x180012a14  mov     [rbp+7C0h+var_820], rax
0x180012a18  mov     rdx, r13
0x180012a1b  mov     rax, [rdi]
0x180012a1e  mov     rcx, rdi
0x180012a21  mov     [rbp+7C0h+var_80A], r15w
0x180012a26  mov     [rbp+7C0h+var_818], r15w
0x180012a2b  mov     rax, [rax+60h]
0x180012a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a34  mov     esi, eax
0x180012a36  test    eax, eax
0x180012a38  jns     short loc_180012A82
0x180012a3a  mov     edx, 1
0x180012a3f  mov     r9d, 13Fh
0x180012a45  mov     ecx, eax
0x180012a47  call    Log_HREvent_1
0x180012a4c  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012a53  mov     rcx, [rbp+7C0h+var_828]; Block
0x180012a57  lea     rax, [rbp+7C0h+var_818]
0x180012a5b  cmp     rcx, rax
0x180012a5e  jz      short loc_180012A68
0x180012a60  mov     rdx, rbx
0x180012a63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012a68  mov     rcx, [rsp+8C0h+Block]
0x180012a6d  lea     rax, [rbp+7C0h+var_838]
0x180012a71  cmp     rcx, rax
0x180012a74  jz      loc_1800129F5
0x180012a7a  mov     rdx, rbx
0x180012a7d  jmp     loc_1800129F0
0x180012a82  xor     edx, edx; Val
0x180012a84  mov     [rsp+8C0h+var_850], r15
0x180012a89  mov     r8d, 650h; Size
0x180012a8f  lea     rcx, [rbp+7C0h+var_690]; void *
0x180012a96  call    memset_0
0x180012a9b  xor     edx, edx; Val
0x180012a9d  lea     rcx, [rbp+7C0h+var_7D0]; void *
0x180012aa1  mov     r8d, 13Ch; Size
0x180012aa7  call    memset_0
0x180012aac  test    rbx, rbx
0x180012aaf  jz      short loc_180012B00
0x180012ab1  mov     rax, [rbx]
0x180012ab4  mov     rcx, rbx
0x180012ab7  mov     rax, [rax+8]
0x180012abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ac0  mov     rcx, [rsp+8C0h+var_850]
0x180012ac5  mov     [rsp+8C0h+var_850], rbx
0x180012aca  test    rcx, rcx
0x180012acd  jz      short loc_180012ADB
0x180012acf  mov     rax, [rcx]
0x180012ad2  mov     rax, [rax+10h]
0x180012ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012adb  lea     rbx, [r13+0BF4h]
0x180012ae2  mov     rcx, rbx
0x180012ae5  lea     rdx, [rbp+7C0h+var_690]
0x180012aec  call    cs:__imp_PhoneGetProviderLineInfo
0x180012af2  mov     esi, eax
0x180012af4  test    eax, eax
0x180012af6  jns     short loc_180012B47
0x180012af8  mov     r9d, 14Eh
0x180012afe  jmp     short loc_180012B17
0x180012b00  lea     rcx, [rsp+8C0h+var_850]
0x180012b05  call    cs:__imp_?CreateBrandingInfo@@YAJPEAPEAUIBrandingInfo@@@Z; CreateBrandingInfo(IBrandingInfo * *)
0x180012b0b  mov     esi, eax
0x180012b0d  test    eax, eax
0x180012b0f  jns     short loc_180012ADB
0x180012b11  mov     r9d, 14Bh
0x180012b17  mov     edx, 1
0x180012b1c  mov     ecx, esi
0x180012b1e  call    Log_HREvent_1
0x180012b23  mov     rcx, [rsp+8C0h+var_850]
0x180012b28  test    rcx, rcx
0x180012b2b  jz      loc_180012A4C
0x180012b31  mov     [rsp+8C0h+var_850], r15
0x180012b36  mov     rdx, [rcx]
0x180012b39  mov     rax, [rdx+10h]
0x180012b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b42  jmp     loc_180012A4C
0x180012b47  lea     rdx, [rbp+7C0h+var_7D0]
0x180012b4b  mov     rcx, rbx
0x180012b4e  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x180012b54  mov     esi, eax
0x180012b56  test    eax, eax
0x180012b58  jns     short loc_180012B62
0x180012b5a  mov     r9d, 14Fh
0x180012b60  jmp     short loc_180012B17
0x180012b62  mov     rcx, [rsp+8C0h+var_850]
0x180012b67  lea     r9, [rbp+7C0h+var_7D0]
0x180012b6b  mov     edx, 3
0x180012b70  mov     dword ptr [rsp+8C0h+var_8A0], r15d
0x180012b75  lea     r8, [rbp+7C0h+var_690]
0x180012b7c  mov     rax, [rcx]
0x180012b7f  lea     r12d, [rdx-2]
0x180012b83  cmp     [r13+0BC8h], r12d
0x180012b8a  mov     rax, [rax+38h]
0x180012b8e  cmovnz  edx, r12d
0x180012b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b97  mov     esi, eax
0x180012b99  test    eax, eax
0x180012b9b  jns     short loc_180012BAB
0x180012b9d  mov     r9d, 154h
0x180012ba3  mov     edx, r12d
0x180012ba6  jmp     loc_180012B1C
0x180012bab  lea     rax, [rbp+7C0h+var_7F0]
0x180012baf  mov     [rbp+7C0h+var_7EE], r15
0x180012bb3  mov     [rbp+7C0h+var_800], rax
0x180012bb7  lea     rbx, [r13+778h]
0x180012bbe  lea     rax, [rbp+7C0h+var_7F0]
0x180012bc2  mov     [rbp+7C0h+var_7E6], r15d
0x180012bc6  mov     [rbp+7C0h+var_7F8], rax
0x180012bca  mov     [rbp+7C0h+var_7E2], r15w
0x180012bcf  mov     [rbp+7C0h+var_7F0], r15w
0x180012bd4  cmp     [rbx], r15w
0x180012bd8  jz      loc_180012D86
0x180012bde  lea     rcx, [rbp+7C0h+hMem]
0x180012be2  mov     [rbp+7C0h+hMem], r15
0x180012be6  mov     [rbp+7C0h+var_7E0], r15d
0x180012bea  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012bef  mov     rdx, rax
0x180012bf2  lea     r8, [rbp+7C0h+var_7E0]
0x180012bf6  mov     rcx, rbx
0x180012bf9  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180012bff  mov     esi, eax
0x180012c01  test    eax, eax
0x180012c03  jns     short loc_180012C64
0x180012c05  mov     r9d, 15Bh
0x180012c0b  mov     edx, r12d
0x180012c0e  mov     ecx, esi
0x180012c10  call    Log_HREvent_1
0x180012c15  mov     rcx, [rbp+7C0h+hMem]; hMem
0x180012c19  test    rcx, rcx
0x180012c1c  jz      short loc_180012C24
0x180012c1e  call    cs:__imp_LocalFree
0x180012c24  mov     rcx, [rbp+7C0h+var_800]; Block
0x180012c28  lea     rax, [rbp+7C0h+var_7F0]
0x180012c2c  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012c33  cmp     rcx, rax
0x180012c36  jz      short loc_180012C40
0x180012c38  mov     rdx, rbx
0x180012c3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012c40  mov     rcx, [rsp+8C0h+var_850]
0x180012c45  test    rcx, rcx
0x180012c48  jz      loc_180012A53
0x180012c4e  mov     [rsp+8C0h+var_850], r15
0x180012c53  mov     rax, [rcx]
0x180012c56  mov     rax, [rax+10h]
0x180012c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5f  jmp     loc_180012A53
0x180012c64  mov     r8, [rbp+7C0h+hMem]
0x180012c68  lea     rdx, aFileS; "file:///%s"
0x180012c6f  lea     rcx, [rbp+7C0h+var_800]
0x180012c73  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180012c78  mov     esi, eax
0x180012c7a  test    eax, eax
0x180012c7c  jns     short loc_180012C86
0x180012c7e  mov     r9d, 15Dh
0x180012c84  jmp     short loc_180012C0B
0x180012c86  mov     rcx, [rbp+7C0h+hMem]; hMem
0x180012c8a  test    rcx, rcx
0x180012c8d  jz      short loc_180012C95
0x180012c8f  call    cs:__imp_LocalFree
0x180012c95  mov     rax, [rdi]
0x180012c98  mov     rcx, [rsp+8C0h+var_850]
0x180012c9d  mov     rdi, [rbp+7C0h+var_828]
0x180012ca1  mov     rsi, [rbp+7C0h+var_800]
0x180012ca5  mov     r14, [rax+58h]
0x180012ca9  mov     rax, [rcx]
0x180012cac  mov     rax, [rax+18h]
0x180012cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb5  mov     rcx, [rsp+8C0h+var_850]
0x180012cba  mov     rbx, rax
0x180012cbd  mov     rdx, [rcx]
0x180012cc0  mov     rax, [rdx+20h]
0x180012cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cc9  mov     r8, [rsp+8C0h+var_860]
0x180012cce  lea     rcx, [r13+570h]
0x180012cd5  mov     [rsp+8C0h+var_878], r8
0x180012cda  lea     rdx, [r13+1698h]
0x180012ce1  mov     r8, [rsp+8C0h+Block]
0x180012ce6  mov     r9, rax
0x180012ce9  mov     [rsp+8C0h+var_880], rdi
0x180012cee  mov     rax, r14
0x180012cf1  mov     [rsp+8C0h+var_888], rsi
0x180012cf6  mov     [rsp+8C0h+var_890], rcx
0x180012cfb  mov     rcx, [rsp+8C0h+var_858]
0x180012d00  mov     [rsp+8C0h+var_898], r13
0x180012d05  mov     [rsp+8C0h+var_8A0], rbx
0x180012d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d0f  mov     edi, eax
0x180012d11  test    eax, eax
0x180012d13  jns     loc_180012E18
0x180012d19  mov     r9d, 16Dh
0x180012d1f  mov     edx, r12d
0x180012d22  mov     ecx, eax
0x180012d24  call    Log_HREvent_1
0x180012d29  mov     rcx, [rbp+7C0h+var_800]; Block
0x180012d2d  lea     rax, [rbp+7C0h+var_7F0]
0x180012d31  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012d38  cmp     rcx, rax
0x180012d3b  jz      short loc_180012D45
0x180012d3d  mov     rdx, rbx
0x180012d40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d45  mov     rcx, [rsp+8C0h+var_850]
0x180012d4a  test    rcx, rcx
0x180012d4d  jz      short loc_180012D60
0x180012d4f  mov     [rsp+8C0h+var_850], r15
0x180012d54  mov     rax, [rcx]
0x180012d57  mov     rax, [rax+10h]
0x180012d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d60  mov     rcx, [rbp+7C0h+var_828]; Block
0x180012d64  lea     rax, [rbp+7C0h+var_818]
0x180012d68  cmp     rcx, rax
0x180012d6b  jz      short loc_180012D75
0x180012d6d  mov     rdx, rbx
0x180012d70  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d75  mov     rcx, [rsp+8C0h+Block]
0x180012d7a  lea     rax, [rbp+7C0h+var_838]
0x180012d7e  cmp     rcx, rax
0x180012d81  jmp     loc_180012E0A
0x180012d86  lea     rdx, aMsWinsoundeven; "ms-winsoundevent:notification.looping.c"...
0x180012d8d  lea     rcx, [rbp+7C0h+var_800]
0x180012d91  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180012d96  test    al, al
0x180012d98  jnz     loc_180012C95
0x180012d9e  mov     edi, 8007000Eh
0x180012da3  xor     edx, edx
0x180012da5  mov     ecx, edi
0x180012da7  mov     r9d, 161h
0x180012dad  call    Log_HREvent_1
0x180012db2  mov     rcx, [rbp+7C0h+var_800]; Block
0x180012db6  lea     rax, [rbp+7C0h+var_7F0]
0x180012dba  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180012dc1  cmp     rcx, rax
  ... truncated ...
```

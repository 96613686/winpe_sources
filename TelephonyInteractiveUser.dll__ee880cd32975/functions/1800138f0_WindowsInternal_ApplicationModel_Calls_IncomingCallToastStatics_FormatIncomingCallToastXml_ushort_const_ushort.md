# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_FormatIncomingCallToastXml(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800138f0`
- end: `0x180013e5d`
- name: `?_FormatIncomingCallToastXml@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG0000000PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, _WORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180004a0c`
- `0x180004b4c`
- `0x180011e68`
- `0x1800138f0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001399f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800139fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013a7f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013aa8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013ab8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013af2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013b74`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013bdc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013c5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013cb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013e1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013e2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001399f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800139fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013a7f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013aa8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013ab8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013af2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013b74`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013bdc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013c5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013cb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013e1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180013e2e`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013977`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800139d0`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013a57`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013b4c`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013c36`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013977`
- `dmxmlhelputils!XMLHEscapeString` at `0x1800139d0`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013a57`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013b4c`
- `dmxmlhelputils!XMLHEscapeString` at `0x180013c36`

## string_xrefs

- `0x180013d8d`: `<toast scenario="incomingCall" %s activationType="background" launch="%s"><visual><binding template="ToastGeneric">%s<text id="1">%s</text><text id="2">%s</text>%s</binding></visual><actions>%s</actions>%s</toast>`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_FormatIncomingCallToastXml(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        _WORD *a8,
        __int64 a9,
        __int64 a10)
{
  _WORD *v12; // rcx
  unsigned __int16 **v13; // rax
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // ebx
  unsigned __int16 **v18; // rax
  int v19; // eax
  __int64 v20; // r8
  unsigned __int16 **v21; // rax
  int v22; // edi
  __int64 v23; // r8
  __int64 v24; // r9
  void *v25; // rcx
  unsigned __int16 **v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int16 **v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // r9
  HLOCAL v35; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v37; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+78h] [rbp-88h] BYREF
  void *Block[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+92h] [rbp-6Eh]
  int v42; // [rsp+9Ah] [rbp-66h]
  __int16 v43; // [rsp+9Eh] [rbp-62h]
  void *v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B2h] [rbp-4Eh]
  int v47; // [rsp+BAh] [rbp-46h]
  __int16 v48; // [rsp+BEh] [rbp-42h]
  void *v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+D2h] [rbp-2Eh]
  int v52; // [rsp+DAh] [rbp-26h]
  __int16 v53; // [rsp+DEh] [rbp-22h]
  void *v54[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v55; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+F2h] [rbp-Eh]
  int v57; // [rsp+FAh] [rbp-6h]
  __int16 v58; // [rsp+FEh] [rbp-2h]
  unsigned int v59; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v60; // [rsp+104h] [rbp+4h] BYREF

  v12 = *(_WORD **)a10;
  *(_QWORD *)(a10 + 8) = *(_QWORD *)a10;
  *v12 = 0;
  hMem = 0;
  v59 = 0;
  v13 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&hMem);
  v14 = XMLHEscapeString(a6, v13, &v59);
  v16 = v14;
  if ( v14 < 0 )
  {
    Log_HREvent_1((unsigned int)v14, 1, v15, 386);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return v16;
  }
  v37 = 0;
  v60 = 0;
  v18 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&v37);
  v19 = XMLHEscapeString(a5, v18, &v60);
  v16 = v19;
  if ( v19 < 0 )
  {
    Log_HREvent_1((unsigned int)v19, 1, v20, 391);
    if ( v37 )
      LocalFree(v37);
    goto LABEL_3;
  }
  v41 = 0;
  Block[0] = &v40;
  Block[1] = &v40;
  v42 = 0;
  v43 = 0;
  v40 = 0;
  if ( a4 && *a4 )
  {
    v35 = 0;
    v38 = 0;
    v21 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&v35);
    v22 = XMLHEscapeString(a4, v21, &v38);
    if ( v22 < 0 )
    {
      v24 = 399;
      goto LABEL_13;
    }
    v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            Block,
            L"<image placement=\"appLogoOverride\" src=\"%s\"/>",
            v35);
    if ( v22 < 0 )
    {
      v24 = 401;
LABEL_13:
      Log_HREvent_1((unsigned int)v22, 1, v23, v24);
      if ( v35 )
        LocalFree(v35);
      v25 = Block[0];
      if ( Block[0] == &v40 )
        goto LABEL_17;
      goto LABEL_16;
    }
    if ( v35 )
      LocalFree(v35);
  }
  v46 = 0;
  v44[0] = &v45;
  v44[1] = &v45;
  v47 = 0;
  v48 = 0;
  v45 = 0;
  if ( a2 && *a2 )
  {
    v35 = 0;
    v38 = 0;
    v26 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&v35);
    v22 = XMLHEscapeString(a2, v26, &v38);
    if ( v22 < 0 )
    {
      v28 = 410;
      goto LABEL_30;
    }
    v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v44,
            L"hint-people=\"remoteid:%s\"",
            v35);
    if ( v22 < 0 )
    {
      v28 = 412;
LABEL_30:
      Log_HREvent_1((unsigned int)v22, 1, v27, v28);
      if ( v35 )
        LocalFree(v35);
      goto LABEL_32;
    }
    if ( v35 )
      LocalFree(v35);
  }
  v51 = 0;
  v49[0] = &v50;
  v49[1] = &v50;
  v52 = 0;
  v53 = 0;
  v50 = 0;
  if ( a7 && *a7 )
  {
    v35 = 0;
    v38 = 0;
    v29 = (unsigned __int16 **)tlx::replace<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>(&v35);
    v22 = XMLHEscapeString(a7, v29, &v38);
    if ( v22 < 0 )
    {
      v31 = 420;
      goto LABEL_44;
    }
    v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v49,
            L"<image placement=\"inline\" src=\"%s\" hint-crop=\"circle\"/>",
            v35);
    if ( v22 < 0 )
    {
      v31 = 422;
LABEL_44:
      Log_HREvent_1((unsigned int)v22, 1, v30, v31);
      if ( v35 )
        LocalFree(v35);
LABEL_46:
      if ( v49[0] != &v50 )
        operator delete(v49[0]);
LABEL_32:
      if ( v44[0] != &v45 )
        operator delete(v44[0]);
      v25 = Block[0];
      if ( Block[0] == &v40 )
        goto LABEL_17;
LABEL_16:
      operator delete(v25);
LABEL_17:
      if ( v37 )
        LocalFree(v37);
      if ( hMem )
        LocalFree(hMem);
      return (unsigned int)v22;
    }
    if ( v35 )
      LocalFree(v35);
  }
  v56 = 0;
  v54[0] = &v55;
  v54[1] = &v55;
  v57 = 0;
  v58 = 0;
  v55 = 0;
  if ( a8 && *a8 )
  {
    v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v54,
            L"<audio src = \"%s\" loop=\"true\"/>",
            a8);
    if ( v22 < 0 )
    {
      v33 = 428;
      goto LABEL_56;
    }
  }
  else
  {
    v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
            v54,
            L"<audio silent=\"true\"/>");
    if ( v22 < 0 )
    {
      v33 = 432;
      goto LABEL_56;
    }
  }
  v22 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          a10,
          L"<toast scenario=\"incomingCall\" %s activationType=\"background\" launch=\"%s\"><visual><binding template=\"To"
           "astGeneric\">%s<text id=\"1\">%s</text><text id=\"2\">%s</text>%s</binding></visual><actions>%s</actions>%s</toast>",
          v44[0],
          a3,
          Block[0],
          v37,
          hMem,
          v49[0],
          a9,
          v54[0]);
  if ( v22 < 0 )
  {
    v33 = 445;
LABEL_56:
    Log_HREvent_1((unsigned int)v22, 1, v32, v33);
    if ( v54[0] != &v55 )
      operator delete(v54[0]);
    goto LABEL_46;
  }
  if ( v54[0] != &v55 )
    operator delete(v54[0]);
  if ( v49[0] != &v50 )
    operator delete(v49[0]);
  if ( v44[0] != &v45 )
    operator delete(v44[0]);
  if ( Block[0] != &v40 )
    operator delete(Block[0]);
  if ( v37 )
    LocalFree(v37);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x1800138f0  mov     [rsp-8+arg_0], rbx
0x1800138f5  push    rbp
0x1800138f6  push    rsi
0x1800138f7  push    rdi
0x1800138f8  push    r12
0x1800138fa  push    r13
0x1800138fc  push    r14
0x1800138fe  push    r15
0x180013900  lea     rbp, [rsp-10h]
0x180013905  sub     rsp, 110h
0x18001390c  mov     rax, cs:__security_cookie
0x180013913  xor     rax, rsp
0x180013916  mov     [rbp+40h+var_38], rax
0x18001391a  mov     rax, [rbp+40h+arg_40]
0x180013921  mov     rdi, r9
0x180013924  mov     r13, [rbp+40h+arg_48]
0x18001392b  mov     rsi, rdx
0x18001392e  mov     r12, [rbp+40h+arg_20]
0x180013932  mov     rbx, [rbp+40h+arg_28]
0x180013936  mov     r14, [rbp+40h+arg_30]
0x18001393d  mov     rcx, [r13+0]
0x180013941  mov     r15, [rbp+40h+arg_38]
0x180013948  mov     [r13+8], rcx
0x18001394c  mov     [rsp+140h+var_F0], rax
0x180013951  xor     eax, eax
0x180013953  mov     [rcx], ax
0x180013956  lea     rcx, [rsp+140h+hMem]
0x18001395b  mov     [rsp+140h+var_E8], r8
0x180013960  mov     [rsp+140h+hMem], rax
0x180013965  mov     [rbp+40h+var_40], eax
0x180013968  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x18001396d  mov     rdx, rax
0x180013970  lea     r8, [rbp+40h+var_40]
0x180013974  mov     rcx, rbx
0x180013977  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x18001397d  mov     ebx, eax
0x18001397f  test    eax, eax
0x180013981  jns     short loc_1800139AC
0x180013983  mov     edx, 1
0x180013988  mov     r9d, 182h
0x18001398e  mov     ecx, eax
0x180013990  call    Log_HREvent_1
0x180013995  mov     rcx, [rsp+140h+hMem]; hMem
0x18001399a  test    rcx, rcx
0x18001399d  jz      short loc_1800139A5
0x18001399f  call    cs:__imp_LocalFree
0x1800139a5  mov     eax, ebx
0x1800139a7  jmp     loc_180013E36
0x1800139ac  lea     rcx, [rsp+140h+var_D0]
0x1800139b1  mov     [rsp+140h+var_D0], 0
0x1800139ba  mov     [rbp+40h+var_3C], 0
0x1800139c1  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x1800139c6  mov     rdx, rax
0x1800139c9  lea     r8, [rbp+40h+var_3C]
0x1800139cd  mov     rcx, r12
0x1800139d0  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x1800139d6  xor     r12d, r12d
0x1800139d9  mov     ebx, eax
0x1800139db  test    eax, eax
0x1800139dd  jns     short loc_180013A03
0x1800139df  lea     edx, [r12+1]
0x1800139e4  mov     r9d, 187h
0x1800139ea  mov     ecx, eax
0x1800139ec  call    Log_HREvent_1
0x1800139f1  mov     rcx, [rsp+140h+var_D0]; hMem
0x1800139f6  test    rcx, rcx
0x1800139f9  jz      short loc_180013995
0x1800139fb  call    cs:__imp_LocalFree
0x180013a01  jmp     short loc_180013995
0x180013a03  mov     [rbp+40h+var_AE], r12
0x180013a07  lea     rax, [rbp+40h+var_B0]
0x180013a0b  mov     [rbp+40h+Block], rax
0x180013a0f  lea     rax, [rbp+40h+var_B0]
0x180013a13  mov     [rbp+40h+var_B8], rax
0x180013a17  mov     [rbp+40h+var_A6], r12d
0x180013a1b  mov     [rbp+40h+var_A2], r12w
0x180013a20  mov     [rbp+40h+var_B0], r12w
0x180013a25  test    rdi, rdi
0x180013a28  jz      loc_180013AF8
0x180013a2e  cmp     [rdi], r12w
0x180013a32  jz      loc_180013AF8
0x180013a38  lea     rcx, [rsp+140h+var_E0]
0x180013a3d  mov     [rsp+140h+var_E0], r12
0x180013a42  mov     [rsp+140h+var_C8], r12d
0x180013a47  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180013a4c  mov     rdx, rax
0x180013a4f  lea     r8, [rsp+140h+var_C8]
0x180013a54  mov     rcx, rdi
0x180013a57  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180013a5d  mov     edi, eax
0x180013a5f  test    eax, eax
0x180013a61  jns     short loc_180013AC5
0x180013a63  mov     r9d, 18Fh
0x180013a69  mov     edx, 1
0x180013a6e  mov     ecx, edi
0x180013a70  call    Log_HREvent_1
0x180013a75  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013a7a  test    rcx, rcx
0x180013a7d  jz      short loc_180013A85
0x180013a7f  call    cs:__imp_LocalFree
0x180013a85  mov     rcx, [rbp+40h+Block]; Block
0x180013a89  lea     rax, [rbp+40h+var_B0]
0x180013a8d  cmp     rcx, rax
0x180013a90  jz      short loc_180013A9E
0x180013a92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013a99  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013a9e  mov     rcx, [rsp+140h+var_D0]; hMem
0x180013aa3  test    rcx, rcx
0x180013aa6  jz      short loc_180013AAE
0x180013aa8  call    cs:__imp_LocalFree
0x180013aae  mov     rcx, [rsp+140h+hMem]; hMem
0x180013ab3  test    rcx, rcx
0x180013ab6  jz      short loc_180013ABE
0x180013ab8  call    cs:__imp_LocalFree
0x180013abe  mov     eax, edi
0x180013ac0  jmp     loc_180013E36
0x180013ac5  mov     r8, [rsp+140h+var_E0]
0x180013aca  lea     rdx, aImagePlacement; "<image placement=\"appLogoOverride\" sr"...
0x180013ad1  lea     rcx, [rbp+40h+Block]
0x180013ad5  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013ada  mov     edi, eax
0x180013adc  test    eax, eax
0x180013ade  jns     short loc_180013AE8
0x180013ae0  mov     r9d, 191h
0x180013ae6  jmp     short loc_180013A69
0x180013ae8  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013aed  test    rcx, rcx
0x180013af0  jz      short loc_180013AF8
0x180013af2  call    cs:__imp_LocalFree
0x180013af8  mov     [rbp+40h+var_8E], r12
0x180013afc  lea     rax, [rbp+40h+var_90]
0x180013b00  mov     [rbp+40h+var_A0], rax
0x180013b04  lea     rax, [rbp+40h+var_90]
0x180013b08  mov     [rbp+40h+var_98], rax
0x180013b0c  mov     [rbp+40h+var_86], r12d
0x180013b10  mov     [rbp+40h+var_82], r12w
0x180013b15  mov     [rbp+40h+var_90], r12w
0x180013b1a  test    rsi, rsi
0x180013b1d  jz      loc_180013BE2
0x180013b23  cmp     [rsi], r12w
0x180013b27  jz      loc_180013BE2
0x180013b2d  lea     rcx, [rsp+140h+var_E0]
0x180013b32  mov     [rsp+140h+var_E0], r12
0x180013b37  mov     [rsp+140h+var_C8], r12d
0x180013b3c  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180013b41  mov     rdx, rax
0x180013b44  lea     r8, [rsp+140h+var_C8]
0x180013b49  mov     rcx, rsi
0x180013b4c  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180013b52  mov     edi, eax
0x180013b54  test    eax, eax
0x180013b56  jns     short loc_180013BAF
0x180013b58  mov     r9d, 19Ah
0x180013b5e  mov     edx, 1
0x180013b63  mov     ecx, edi
0x180013b65  call    Log_HREvent_1
0x180013b6a  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013b6f  test    rcx, rcx
0x180013b72  jz      short loc_180013B7A
0x180013b74  call    cs:__imp_LocalFree
0x180013b7a  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013b81  mov     rcx, [rbp+40h+var_A0]; Block
0x180013b85  lea     rax, [rbp+40h+var_90]
0x180013b89  cmp     rcx, rax
0x180013b8c  jz      short loc_180013B96
0x180013b8e  mov     rdx, rbx
0x180013b91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013b96  mov     rcx, [rbp+40h+Block]
0x180013b9a  lea     rax, [rbp+40h+var_B0]
0x180013b9e  cmp     rcx, rax
0x180013ba1  jz      loc_180013A9E
0x180013ba7  mov     rdx, rbx
0x180013baa  jmp     loc_180013A99
0x180013baf  mov     r8, [rsp+140h+var_E0]
0x180013bb4  lea     rdx, aHintPeopleRemo; "hint-people=\"remoteid:%s\""
0x180013bbb  lea     rcx, [rbp+40h+var_A0]
0x180013bbf  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013bc4  mov     edi, eax
0x180013bc6  test    eax, eax
0x180013bc8  jns     short loc_180013BD2
0x180013bca  mov     r9d, 19Ch
0x180013bd0  jmp     short loc_180013B5E
0x180013bd2  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013bd7  test    rcx, rcx
0x180013bda  jz      short loc_180013BE2
0x180013bdc  call    cs:__imp_LocalFree
0x180013be2  mov     [rbp+40h+var_6E], r12
0x180013be6  lea     rax, [rbp+40h+var_70]
0x180013bea  mov     [rbp+40h+var_80], rax
0x180013bee  lea     rax, [rbp+40h+var_70]
0x180013bf2  mov     [rbp+40h+var_78], rax
0x180013bf6  mov     [rbp+40h+var_66], r12d
0x180013bfa  mov     [rbp+40h+var_62], r12w
0x180013bff  mov     [rbp+40h+var_70], r12w
0x180013c04  test    r14, r14
0x180013c07  jz      loc_180013CBC
0x180013c0d  cmp     [r14], r12w
0x180013c11  jz      loc_180013CBC
0x180013c17  lea     rcx, [rsp+140h+var_E0]
0x180013c1c  mov     [rsp+140h+var_E0], r12
0x180013c21  mov     [rsp+140h+var_C8], r12d
0x180013c26  call    ??$replace@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<ushort *,void * (*)(void *),&LocalFree(void *),0> &)
0x180013c2b  mov     rdx, rax
0x180013c2e  lea     r8, [rsp+140h+var_C8]
0x180013c33  mov     rcx, r14
0x180013c36  call    cs:__imp_?XMLHEscapeString@@YAJPEBGPEAPEAGPEAK@Z; XMLHEscapeString(ushort const *,ushort * *,ulong *)
0x180013c3c  mov     edi, eax
0x180013c3e  test    eax, eax
0x180013c40  jns     short loc_180013C89
0x180013c42  mov     r9d, 1A4h
0x180013c48  mov     edx, 1
0x180013c4d  mov     ecx, edi
0x180013c4f  call    Log_HREvent_1
0x180013c54  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013c59  test    rcx, rcx
0x180013c5c  jz      short loc_180013C64
0x180013c5e  call    cs:__imp_LocalFree
0x180013c64  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013c6b  mov     rcx, [rbp+40h+var_80]; Block
0x180013c6f  lea     rax, [rbp+40h+var_70]
0x180013c73  cmp     rcx, rax
0x180013c76  jz      loc_180013B81
0x180013c7c  mov     rdx, rbx
0x180013c7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c84  jmp     loc_180013B81
0x180013c89  mov     r8, [rsp+140h+var_E0]
0x180013c8e  lea     rdx, aImagePlacement_0; "<image placement=\"inline\" src=\"%s\" "...
0x180013c95  lea     rcx, [rbp+40h+var_80]
0x180013c99  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013c9e  mov     edi, eax
0x180013ca0  test    eax, eax
0x180013ca2  jns     short loc_180013CAC
0x180013ca4  mov     r9d, 1A6h
0x180013caa  jmp     short loc_180013C48
0x180013cac  mov     rcx, [rsp+140h+var_E0]; hMem
0x180013cb1  test    rcx, rcx
0x180013cb4  jz      short loc_180013CBC
0x180013cb6  call    cs:__imp_LocalFree
0x180013cbc  mov     [rbp+40h+var_4E], r12
0x180013cc0  lea     rax, [rbp+40h+var_50]
0x180013cc4  mov     [rbp+40h+var_60], rax
0x180013cc8  lea     rax, [rbp+40h+var_50]
0x180013ccc  mov     [rbp+40h+var_58], rax
0x180013cd0  mov     [rbp+40h+var_46], r12d
0x180013cd4  mov     [rbp+40h+var_42], r12w
0x180013cd9  mov     [rbp+40h+var_50], r12w
0x180013cde  test    r15, r15
0x180013ce1  jz      short loc_180013D39
0x180013ce3  cmp     [r15], r12w
0x180013ce7  jz      short loc_180013D39
0x180013ce9  mov     r8, r15
0x180013cec  lea     rdx, aAudioSrcSLoopT; "<audio src = \"%s\" loop=\"true\"/>"
0x180013cf3  lea     rcx, [rbp+40h+var_60]
0x180013cf7  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013cfc  mov     edi, eax
0x180013cfe  test    eax, eax
0x180013d00  jns     short loc_180013D57
0x180013d02  mov     r9d, 1ACh
0x180013d08  mov     edx, 1
0x180013d0d  mov     ecx, edi
0x180013d0f  call    Log_HREvent_1
0x180013d14  mov     rcx, [rbp+40h+var_60]; Block
0x180013d18  lea     rax, [rbp+40h+var_50]
0x180013d1c  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013d23  cmp     rcx, rax
0x180013d26  jz      loc_180013C6B
0x180013d2c  mov     rdx, rbx
0x180013d2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013d34  jmp     loc_180013C6B
0x180013d39  lea     rdx, aAudioSilentTru; "<audio silent=\"true\"/>"
0x180013d40  lea     rcx, [rbp+40h+var_60]
0x180013d44  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013d49  mov     edi, eax
0x180013d4b  test    eax, eax
0x180013d4d  jns     short loc_180013D57
0x180013d4f  mov     r9d, 1B0h
0x180013d55  jmp     short loc_180013D08
0x180013d57  mov     rax, [rbp+40h+var_60]
0x180013d5b  mov     rcx, r13
0x180013d5e  mov     rdx, [rbp+40h+var_80]
0x180013d62  mov     r10, [rsp+140h+hMem]
0x180013d67  mov     r11, [rsp+140h+var_D0]
0x180013d6c  mov     rbx, [rbp+40h+Block]
0x180013d70  mov     r9, [rsp+140h+var_E8]
0x180013d75  mov     r8, [rbp+40h+var_A0]
0x180013d79  mov     [rsp+140h+var_F8], rax
0x180013d7e  mov     rax, [rsp+140h+var_F0]
0x180013d83  mov     [rsp+140h+var_100], rax
0x180013d88  mov     [rsp+140h+var_108], rdx
0x180013d8d  lea     rdx, aToastScenarioI; "<toast scenario=\"incomingCall\" %s act"...
0x180013d94  mov     [rsp+140h+var_110], r10
0x180013d99  mov     [rsp+140h+var_118], r11
0x180013d9e  mov     [rsp+140h+var_120], rbx
0x180013da3  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013da8  mov     edi, eax
0x180013daa  test    eax, eax
0x180013dac  jns     short loc_180013DB9
0x180013dae  mov     r9d, 1BDh
0x180013db4  jmp     loc_180013D08
0x180013db9  mov     rcx, [rbp+40h+var_60]; Block
  ... truncated ...
```

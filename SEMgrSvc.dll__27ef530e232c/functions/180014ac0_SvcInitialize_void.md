# SvcInitialize(void)

- ea: `0x180014ac0`
- end: `0x180014e54`
- name: `?SvcInitialize@@YAJXZ`
- size: `916`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015530`

## callees

- `0x180001008`
- `0x180001194`
- `0x1800049a0`
- `0x18000584c`
- `0x18000a89c`
- `0x18000c964`
- `0x18000f30c`
- `0x18000f424`
- `0x18000f740`
- `0x180011a64`
- `0x180012368`
- `0x1800127c0`
- `0x1800129b8`
- `0x180012a00`
- `0x180013014`
- `0x18001310c`
- `0x1800132e0`
- `0x180014254`
- `0x180014898`
- `0x180014ac0`
- `0x180014e70`
- `0x1800420ac`
- `0x18007ce94`
- `0x180089448`
- `0x1800899fc`
- `0x180089e3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014e31`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014e31`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014b13`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180014b13`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180014cd2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180014d93`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180014cd2`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180014d93`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x180014b4a`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x180014bb3`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x180014b4a`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x180014bb3`

## string_xrefs

- `0x180014d22`: `onecoreuap\ds\nfc\product\semanagement\service\src\devnodes.cpp`
- `0x180014b73`: `onecoreuap\ds\nfc\product\semanagement\service\src\semgrsvc.cpp`
- `0x180014bc4`: `onecoreuap\ds\nfc\product\semanagement\service\src\semgrsvc.cpp`
- `0x180014d62`: `Failed to start the SEMgr service`
- `0x180014dd6`: `SEMgr COM server registered`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SvcInitialize(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // r14d
  int v4; // edi
  __int64 v5; // rcx
  int inited; // ebx
  __int64 v7; // r8
  int v8; // r9d
  int ServiceDirectory; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  void **v13; // rsi
  __int64 v14; // rbx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // r8
  unsigned __int16 *v21; // r9
  int v22; // eax
  unsigned __int16 *v24; // [rsp+20h] [rbp-50h]
  int v25; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v26; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v27; // [rsp+30h] [rbp-40h]
  unsigned int v28; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned __int16 v30[4]; // [rsp+48h] [rbp-28h] BYREF
  void *Src[3]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v3 = 0;
  v29 = 0;
  v4 = 1;
  if ( (Microsoft_WindowsPhone_SEManagementProviderEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, SEMgr_Event_Service_Starting, a3, 1, Src);
  inited = CoInitializeEx(0, 0);
  if ( inited < 0 )
  {
    v4 = 0;
    goto LABEL_36;
  }
  v28 = 0;
  v24 = (unsigned __int16 *)&v28;
  ServiceDirectory = GetServiceDirectory(hServiceStatus, 0, 0, 0);
  inited = ServiceDirectory;
  if ( ServiceDirectory == 122 )
  {
    std::vector<unsigned short>::vector<unsigned short>(Src, v28);
    v24 = (unsigned __int16 *)&v28;
    v10 = GetServiceDirectory(hServiceStatus, 0, Src[0], ((char *)Src[1] - (char *)Src[0]) >> 1);
    if ( v10 )
    {
      inited = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x67,
                 (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semgrsvc.cpp",
                 (const char *)v10,
                 (unsigned int)&v28);
      std::vector<enum CRSDataTag>::~vector<enum CRSDataTag>(Src);
LABEL_12:
      if ( inited < 0 )
        goto LABEL_36;
      goto LABEL_22;
    }
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)Src[0] + v12) );
    if ( v12 > qword_180132958 )
    {
      ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
        &qword_180132940,
        v12,
        v11,
        Src[0]);
    }
    else
    {
      v13 = &qword_180132940;
      if ( (unsigned __int64)qword_180132958 > 7 )
        v13 = (void **)qword_180132940;
      qword_180132950 = v12;
      v14 = 2 * v12;
      memmove_0(v13, Src[0], 2 * v12);
      *(_WORD *)((char *)v13 + v14) = 0;
    }
    std::vector<enum CRSDataTag>::~vector<enum CRSDataTag>(Src);
  }
  else
  {
    if ( ServiceDirectory > 0 )
      inited = (unsigned __int16)ServiceDirectory | 0x80070000;
    if ( inited < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semgrsvc.cpp",
        (const char *)(unsigned int)inited,
        (int)&v28);
      goto LABEL_12;
    }
  }
LABEL_22:
  inited = ComModule::Initialize();
  if ( inited >= 0 )
  {
    if ( NfcRegUtils::GetDword((const struct NfcRegistryLocation *)&qword_1800A1B98, L"ShutdownDelay", &v29) < 0 )
      v29 = 120000;
    if ( (unsigned int)dword_18012F048 > 5 )
    {
      v28 = v29;
      *(_QWORD *)v30 = "Register shutdown delay.";
      Src[0] = "SvcInitialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v15,
        (unsigned int)&word_180119A5E,
        v16,
        v17,
        (__int64)Src,
        (__int64)v30,
        (__int64)&v28);
    }
    inited = CoRegisterServerShutdownDelay(hObject, v29);
    if ( inited >= 0 )
    {
      inited = SEManager::Initialize();
      if ( inited >= 0 )
      {
        v3 = 1;
        inited = DeviceCastle::Library::DeviceCastleProvider::OnStart((DeviceCastle::Library::DeviceCastleProvider *)&off_18012F400);
        if ( inited >= 0 )
        {
          if ( !IsScDeviceEnumServicePresent() )
          {
            inited = InitSCardDevInfoNodeMan(v19, v18, v20, v21, v24, v26, v27);
            if ( inited < 0 )
              goto LABEL_36;
            v22 = AddChildNodesForRealDevices();
            if ( v22 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xF,
                (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\devnodes.cpp",
                (const char *)(unsigned int)v22,
                v25);
          }
          inited = ComServer::RegisterFactories((ComServer *)&g_paymentServer);
          if ( inited >= 0 )
          {
            inited = ComServer::RegisterFactories((ComServer *)&g_SEManagerServer);
            if ( inited >= 0 )
            {
              if ( (unsigned int)dword_18012F048 > 5 )
              {
                Src[0] = "SEMgr COM server registered";
                *(_QWORD *)v30 = "SvcInitialize";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v5,
                  (unsigned int)&byte_180119967,
                  v7,
                  v8,
                  (__int64)v30,
                  (__int64)Src);
              }
              if ( (Microsoft_WindowsPhone_SEManagementProviderEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(v5, SEMgr_Event_Service_Started, v7, 1, Src);
              SvcAddRef();
              SvcRelease();
              inited = 0;
              goto LABEL_47;
            }
          }
        }
      }
    }
  }
LABEL_36:
  if ( (unsigned int)dword_18012F048 > 2 )
  {
    Src[0] = "Failed to start the SEMgr service";
    *(_QWORD *)v30 = "SvcInitialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)&dword_180119AAC,
      v7,
      v8,
      (__int64)v30,
      (__int64)Src);
  }
  CoRegisterServerShutdownDelay(0, 0);
  UninitSCardDevInfoNodeMan();
  ComServer::Uninitialize((ComServer *)&g_paymentServer);
  ComServer::Uninitialize((ComServer *)&g_SEManagerServer);
  UnloadMockCellular();
  if ( v3 )
    SEManager::Uninitialize();
  if ( v4 )
LABEL_47:
    CoUninitialize();
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180014ac0  push    rbp
0x180014ac2  push    rbx
0x180014ac3  push    rsi
0x180014ac4  push    rdi
0x180014ac5  push    r12
0x180014ac7  push    r14
0x180014ac9  push    r15
0x180014acb  mov     rbp, rsp
0x180014ace  sub     rsp, 70h
0x180014ad2  mov     rax, cs:__security_cookie
0x180014ad9  xor     rax, rsp
0x180014adc  mov     [rbp+var_8], rax
0x180014ae0  xor     r15d, r15d
0x180014ae3  mov     r14d, r15d
0x180014ae6  mov     [rbp+var_2C], r15d
0x180014aea  lea     edi, [r15+1]
0x180014aee  test    cs:Microsoft_WindowsPhone_SEManagementProviderEnableBits, 8
0x180014af5  jz      short loc_180014B0F
0x180014af7  lea     rax, [rbp+Src]
0x180014afb  mov     [rsp+70h+var_50], rax
0x180014b00  mov     r9d, edi
0x180014b03  lea     rdx, SEMgr_Event_Service_Starting
0x180014b0a  call    McGenEventWrite_EventWriteTransfer
0x180014b0f  xor     edx, edx; dwCoInit
0x180014b11  xor     ecx, ecx; pvReserved
0x180014b13  call    cs:__imp_CoInitializeEx
0x180014b19  mov     ebx, eax
0x180014b1b  lea     r12, aSvcinitialize; "SvcInitialize"
0x180014b22  test    eax, eax
0x180014b24  jns     short loc_180014B2E
0x180014b26  mov     edi, r15d
0x180014b29  jmp     loc_180014D57
0x180014b2e  mov     [rbp+var_30], r15d
0x180014b32  lea     rax, [rbp+var_30]
0x180014b36  mov     [rsp+70h+var_50], rax; int
0x180014b3b  xor     r9d, r9d
0x180014b3e  xor     r8d, r8d
0x180014b41  xor     edx, edx
0x180014b43  mov     rcx, cs:hServiceStatus
0x180014b4a  call    cs:__imp_GetServiceDirectory
0x180014b50  mov     ebx, eax
0x180014b52  cmp     eax, 7Ah ; 'z'
0x180014b55  jz      short loc_180014B86
0x180014b57  test    eax, eax
0x180014b59  jle     short loc_180014B64
0x180014b5b  movzx   ebx, ax
0x180014b5e  or      ebx, 80070000h
0x180014b64  test    ebx, ebx
0x180014b66  jns     loc_180014C50
0x180014b6c  mov     rcx, [rbp+38h]; this
0x180014b70  mov     r9d, ebx; char *
0x180014b73  lea     r8, aOnecoreuapDsNf_35; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180014b7a  mov     edx, 5Fh ; '_'; void *
0x180014b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b84  jmp     short loc_180014BE0
0x180014b86  mov     edx, [rbp+var_30]
0x180014b89  lea     rcx, [rbp+Src]
0x180014b8d  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x180014b92  nop
0x180014b93  mov     r8, [rbp+Src]
0x180014b97  mov     r9, [rbp+var_18]
0x180014b9b  sub     r9, r8
0x180014b9e  sar     r9, 1
0x180014ba1  lea     rax, [rbp+var_30]
0x180014ba5  mov     [rsp+70h+var_50], rax; unsigned int
0x180014baa  xor     edx, edx
0x180014bac  mov     rcx, cs:hServiceStatus
0x180014bb3  call    cs:__imp_GetServiceDirectory
0x180014bb9  test    eax, eax
0x180014bbb  jz      short loc_180014BE9
0x180014bbd  mov     rcx, [rbp+38h]; this
0x180014bc1  mov     r9d, eax; char *
0x180014bc4  lea     r8, aOnecoreuapDsNf_35; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180014bcb  mov     edx, 67h ; 'g'; void *
0x180014bd0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014bd5  mov     ebx, eax
0x180014bd7  lea     rcx, [rbp+Src]
0x180014bdb  call    ??1?$vector@W4CRSDataTag@@V?$allocator@W4CRSDataTag@@@std@@@std@@QEAA@XZ; std::vector<CRSDataTag>::~vector<CRSDataTag>(void)
0x180014be0  test    ebx, ebx
0x180014be2  jns     short loc_180014C50
0x180014be4  jmp     loc_180014D57
0x180014be9  mov     r9, [rbp+Src]
0x180014bed  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014bf1  inc     rdx
0x180014bf4  cmp     [r9+rdx*2], r15w
0x180014bf9  jnz     short loc_180014BF1
0x180014bfb  mov     rax, cs:qword_180132958
0x180014c02  cmp     rdx, rax
0x180014c05  ja      short loc_180014C3A
0x180014c07  lea     rsi, qword_180132940
0x180014c0e  cmp     rax, 7
0x180014c12  cmova   rsi, cs:qword_180132940
0x180014c1a  mov     cs:qword_180132950, rdx
0x180014c21  lea     rbx, [rdx+rdx]
0x180014c25  mov     r8, rbx; Size
0x180014c28  mov     rdx, r9; Src
0x180014c2b  mov     rcx, rsi; void *
0x180014c2e  call    memmove_0
0x180014c33  mov     [rbx+rsi], r15w
0x180014c38  jmp     short loc_180014C47
0x180014c3a  lea     rcx, qword_180132940
0x180014c41  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180014c46  nop
0x180014c47  lea     rcx, [rbp+Src]
0x180014c4b  call    ??1?$vector@W4CRSDataTag@@V?$allocator@W4CRSDataTag@@@std@@@std@@QEAA@XZ; std::vector<CRSDataTag>::~vector<CRSDataTag>(void)
0x180014c50  call    ?Initialize@ComModule@@SAJXZ; ComModule::Initialize(void)
0x180014c55  mov     ebx, eax
0x180014c57  test    eax, eax
0x180014c59  js      loc_180014D57
0x180014c5f  lea     r8, [rbp+var_2C]; unsigned int *
0x180014c63  lea     rdx, aShutdowndelay; "ShutdownDelay"
0x180014c6a  lea     rcx, qword_1800A1B98; struct NfcRegistryLocation *
0x180014c71  call    ?GetDword@NfcRegUtils@@SAJAEBUNfcRegistryLocation@@PEBGPEAK@Z; NfcRegUtils::GetDword(NfcRegistryLocation const &,ushort const *,ulong *)
0x180014c76  test    eax, eax
0x180014c78  jns     short loc_180014C81
0x180014c7a  mov     [rbp+var_2C], 1D4C0h
0x180014c81  mov     eax, cs:dword_18012F048
0x180014c87  cmp     eax, 5
0x180014c8a  jbe     short loc_180014CC8
0x180014c8c  mov     eax, [rbp+var_2C]
0x180014c8f  mov     [rbp+var_30], eax
0x180014c92  lea     rax, aRegisterShutdo; "Register shutdown delay."
0x180014c99  mov     qword ptr [rbp+var_28], rax
0x180014c9d  mov     [rbp+Src], r12
0x180014ca1  lea     rax, [rbp+var_30]
0x180014ca5  mov     [rsp+70h+var_40], rax; unsigned __int16 *
0x180014caa  lea     rax, [rbp+var_28]
0x180014cae  mov     [rsp+70h+var_48], rax; unsigned __int16 *
0x180014cb3  lea     rax, [rbp+Src]
0x180014cb7  mov     [rsp+70h+var_50], rax; int
0x180014cbc  lea     rdx, word_180119A5E
0x180014cc3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180014cc8  mov     edx, [rbp+var_2C]
0x180014ccb  mov     rcx, cs:hObject
0x180014cd2  call    cs:__imp_CoRegisterServerShutdownDelay
0x180014cd8  mov     ebx, eax
0x180014cda  test    eax, eax
0x180014cdc  js      short loc_180014D57
0x180014cde  call    ?Initialize@SEManager@@SAJXZ; SEManager::Initialize(void)
0x180014ce3  mov     ebx, eax
0x180014ce5  test    eax, eax
0x180014ce7  js      short loc_180014D57
0x180014ce9  mov     r14d, edi
0x180014cec  lea     rcx, off_18012F400; this
0x180014cf3  call    ?OnStart@DeviceCastleProvider@Library@DeviceCastle@@QEAAJXZ; DeviceCastle::Library::DeviceCastleProvider::OnStart(void)
0x180014cf8  mov     ebx, eax
0x180014cfa  test    eax, eax
0x180014cfc  js      short loc_180014D57
0x180014cfe  call    ?IsScDeviceEnumServicePresent@@YA_NXZ; IsScDeviceEnumServicePresent(void)
0x180014d03  test    al, al
0x180014d05  jnz     short loc_180014D33
0x180014d07  call    ?InitSCardDevInfoNodeMan@@YAJPEAG000000@Z; InitSCardDevInfoNodeMan(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180014d0c  mov     ebx, eax
0x180014d0e  test    eax, eax
0x180014d10  js      short loc_180014D57
0x180014d12  call    ?AddChildNodesForRealDevices@@YAJXZ; AddChildNodesForRealDevices(void)
0x180014d17  test    eax, eax
0x180014d19  jns     short loc_180014D33
0x180014d1b  mov     rcx, [rbp+38h]; this
0x180014d1f  mov     r9d, eax; char *
0x180014d22  lea     r8, aOnecoreuapDsNf_43; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180014d29  mov     edx, 0Fh; void *
0x180014d2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014d33  lea     rcx, ?g_paymentServer@@3VComServer@@A; this
0x180014d3a  call    ?RegisterFactories@ComServer@@QEAAJXZ; ComServer::RegisterFactories(void)
0x180014d3f  mov     ebx, eax
0x180014d41  test    eax, eax
0x180014d43  js      short loc_180014D57
0x180014d45  lea     rcx, ?g_SEManagerServer@@3VComServer@@A; this
0x180014d4c  call    ?RegisterFactories@ComServer@@QEAAJXZ; ComServer::RegisterFactories(void)
0x180014d51  mov     ebx, eax
0x180014d53  test    eax, eax
0x180014d55  jns     short loc_180014DCB
0x180014d57  mov     eax, cs:dword_18012F048
0x180014d5d  cmp     eax, 2
0x180014d60  jbe     short loc_180014D8F
0x180014d62  lea     rax, aFailedToStartT; "Failed to start the SEMgr service"
0x180014d69  mov     [rbp+Src], rax
0x180014d6d  mov     qword ptr [rbp+var_28], r12
0x180014d71  lea     rax, [rbp+Src]
0x180014d75  mov     [rsp+70h+var_48], rax
0x180014d7a  lea     rax, [rbp+var_28]
0x180014d7e  mov     [rsp+70h+var_50], rax
0x180014d83  lea     rdx, dword_180119AAC
0x180014d8a  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014d8f  xor     edx, edx
0x180014d91  xor     ecx, ecx
0x180014d93  call    cs:__imp_CoRegisterServerShutdownDelay
0x180014d99  call    ?UninitSCardDevInfoNodeMan@@YAJXZ; UninitSCardDevInfoNodeMan(void)
0x180014d9e  lea     rcx, ?g_paymentServer@@3VComServer@@A; this
0x180014da5  call    ?Uninitialize@ComServer@@QEAAXXZ; ComServer::Uninitialize(void)
0x180014daa  lea     rcx, ?g_SEManagerServer@@3VComServer@@A; this
0x180014db1  call    ?Uninitialize@ComServer@@QEAAXXZ; ComServer::Uninitialize(void)
0x180014db6  call    ?UnloadMockCellular@@YAXXZ; UnloadMockCellular(void)
0x180014dbb  test    r14d, r14d
0x180014dbe  jz      short loc_180014DC5
0x180014dc0  call    ?Uninitialize@SEManager@@SAJXZ; SEManager::Uninitialize(void)
0x180014dc5  test    edi, edi
0x180014dc7  jz      short loc_180014E37
0x180014dc9  jmp     short loc_180014E31
0x180014dcb  mov     eax, cs:dword_18012F048
0x180014dd1  cmp     eax, 5
0x180014dd4  jbe     short loc_180014E03
0x180014dd6  lea     rax, aSemgrComServer; "SEMgr COM server registered"
0x180014ddd  mov     [rbp+Src], rax
0x180014de1  mov     qword ptr [rbp+var_28], r12
0x180014de5  lea     rax, [rbp+Src]
0x180014de9  mov     [rsp+70h+var_48], rax
0x180014dee  lea     rax, [rbp+var_28]
0x180014df2  mov     [rsp+70h+var_50], rax
0x180014df7  lea     rdx, byte_180119967
0x180014dfe  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014e03  test    cs:Microsoft_WindowsPhone_SEManagementProviderEnableBits, dil
0x180014e0a  jz      short loc_180014E24
0x180014e0c  lea     rax, [rbp+Src]
0x180014e10  mov     [rsp+70h+var_50], rax
0x180014e15  mov     r9d, edi
0x180014e18  lea     rdx, SEMgr_Event_Service_Started
0x180014e1f  call    McGenEventWrite_EventWriteTransfer
0x180014e24  call    ?SvcAddRef@@YAXXZ; SvcAddRef(void)
0x180014e29  call    ?SvcRelease@@YAXXZ; SvcRelease(void)
0x180014e2e  mov     ebx, r15d
0x180014e31  call    cs:__imp_CoUninitialize
0x180014e37  mov     eax, ebx
0x180014e39  mov     rcx, [rbp+var_8]
0x180014e3d  xor     rcx, rsp; StackCookie
0x180014e40  call    __security_check_cookie
0x180014e45  add     rsp, 70h
0x180014e49  pop     r15
0x180014e4b  pop     r14
0x180014e4d  pop     r12
0x180014e4f  pop     rdi
0x180014e50  pop     rsi
0x180014e51  pop     rbx
0x180014e52  pop     rbp
0x180014e53  retn
```

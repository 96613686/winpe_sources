# WriteNdisInterfaceKernelSummary

- ea: `0x18003fc90`
- end: `0x18004007b`
- name: `WriteNdisInterfaceKernelSummary`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180027b90`

## callees

- `0x180005c50`
- `0x18000a430`
- `0x18000e970`
- `0x18000ead8`
- `0x18000fd70`
- `0x180010200`
- `0x180015f50`
- `0x180016a20`
- `0x180017320`
- `0x18001bb9c`
- `0x18001df48`
- `0x180029d20`
- `0x18003fc90`
- `0x180040084`
- `0x1800400bc`
- `0x1800402bc`
- `0x18005097c`
- `0x180056c2c`
- `0x180064704`
- `0x180065035`
- `0x18006c7c8`
- `0x18007234c`
- `0x1800810d0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003fcf8`
- `msvcrt!wcscat_s` at `0x18003fcf8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040058`

## string_xrefs

- `0x18003fff4`: `ProtocolList`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
LSTATUS __fastcall WriteNdisInterfaceKernelSummary(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int StoreTypeForDriver; // eax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  int PathType; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  struct Property v14; // rax
  __int64 v15; // rdx
  int v16; // edi
  unsigned __int8 *v17; // rbx
  __int64 v18; // rax
  __int16 *v19; // r9
  const unsigned __int8 *v20; // r8
  LSTATUS result; // eax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h]
  unsigned __int8 *v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  char v28; // [rsp+80h] [rbp-80h] BYREF
  GUID v29; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+B8h] [rbp-48h] BYREF
  void *Block[2]; // [rsp+188h] [rbp+88h] BYREF
  __int16 v33; // [rsp+198h] [rbp+98h]
  _BYTE v34[6]; // [rsp+19Ah] [rbp+9Ah] BYREF
  unsigned __int64 v35; // [rsp+1A0h] [rbp+A0h]
  void **v36; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v37[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t Destination[264]; // [rsp+1D0h] [rbp+D0h] BYREF

  v27 = -2;
  StoreTypeForDriver = NetSetupTransaction::GetStoreTypeForDriver(a2, a4);
  NetSetupDriverStore::GetPathToDriver(a3, StoreTypeForDriver, Destination);
  wcscat_s(Destination, 0x104u, L"\\Kernel");
  RegistryKey::CreateSubKey((HKEY *)(a2 + 24), (HKEY)&hKey, Destination, 3u, 0, 0);
  v23 = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  v9 = (_QWORD *)*a5;
  v10 = (_QWORD *)a5[1];
  while ( v9 != v10 )
  {
    PathType = NetSetupBindPath::GetPathType(*v9);
    if ( PathType )
    {
      if ( PathType == 1 )
      {
        *(_OWORD *)Block = 0;
        v33 = 0;
        *(_OWORD *)Block = *(_OWORD *)(*(_QWORD *)(v12 + 88) - 16LL);
        v33 = *(_WORD *)(v12 + 112);
        std::vector<unsigned char>::insert<unsigned char *>(
          (unsigned int)v25,
          (unsigned int)&v28,
          v25[1],
          (unsigned int)Block,
          (__int64)v34);
      }
    }
    else
    {
      v13 = *(_QWORD *)(v12 + 88);
      if ( *(_DWORD *)(v13 - 20) == 4 )
      {
        NetSetup2::details::GetObjectWithFilter<NetSetup2::ProtocolDriver>((__int64)&v36, a1, v12, v13 - 16);
        NetSetup2::ActiveObject::GetProperty(&v36, &v29, &NETSETUPPKEY_Driver_BindName, 0);
        NetSetup2::Property::GetString(&v29, Block);
        std::vector<_NETSETUPPROPKEY>::_Tidy(v30);
        std::vector<std::wstring>::push_back(&v23, Block);
        if ( v35 >= 8 )
          operator delete(Block[0]);
      }
      else
      {
        if ( *(_DWORD *)(v13 - 20) != 5 )
          goto LABEL_13;
        NetSetup2::details::GetObjectWithFilter<NetSetup2::ServiceDriver>((__int64)&v36, a1, v12, v13 - 16);
        v14.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                       (NetSetup2::ActiveObject *)&v36,
                       (const struct _NETSETUPPROPKEY *)&v29).lpVtbl;
        NetSetup2::Property::GetString(v14.lpVtbl, Block);
        std::vector<_NETSETUPPROPKEY>::_Tidy(v30);
        std::vector<std::wstring>::push_back(&v23, Block);
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(Block, v15, 0);
      }
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v37);
    }
LABEL_13:
    ++v9;
  }
  if ( (unsigned __int64)((__int64)(*((_QWORD *)&v23 + 1) - v23) >> 5) >= 0x80 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF__guid_PP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_GLOBAL_Control,
        a3 + 4,
        (__int64)(*((_QWORD *)&v23 + 1) - v23) >> 5);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023604);
    throw (HResultException *)pExceptionObject;
  }
  v16 = (int)v25[1];
  v17 = v25[0];
  if ( (unsigned __int8 *)(v25[1] - v25[0]) >= (unsigned __int8 *)0x900 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF__guid_PP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (v25[1] - v25[0]) / 0x12uLL,
        a3 + 4,
        (v25[1] - v25[0]) / 0x12uLL);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023604);
    throw (HResultException *)pExceptionObject;
  }
  v18 = RegistryKey::ConvertMultiSzToBinary(Block, &v23);
  v19 = *(__int16 **)(v18 + 8);
  v20 = *(const unsigned __int8 **)v18;
  if ( *(__int16 **)v18 == v19 )
  {
    v19 = &word_18009A2AE;
    v20 = &MultiSz::emptyMultiSz;
  }
  RegistryKey::SetValue(&hKey, L"ProtocolList", v20, (_DWORD)v19 - (_DWORD)v20, 7u);
  std::vector<_NETSETUPPROPKEY>::_Tidy(Block);
  RegistryKey::SetValue(&hKey, L"FilterList", v17, v16 - (_DWORD)v17, 3u);
  if ( v17 )
    operator delete(v17);
  result = std::vector<std::wstring>::_Tidy(&v23);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18003fc90  push    rbp
0x18003fc92  push    rbx
0x18003fc93  push    rsi
0x18003fc94  push    rdi
0x18003fc95  push    r14
0x18003fc97  lea     rbp, [rsp-2F0h]
0x18003fc9f  sub     rsp, 3F0h
0x18003fca6  mov     [rsp+410h+var_398], 0FFFFFFFFFFFFFFFEh
0x18003fcaf  mov     rax, cs:__security_cookie
0x18003fcb6  xor     rax, rsp
0x18003fcb9  mov     [rbp+310h+var_30], rax
0x18003fcc0  mov     rsi, r8
0x18003fcc3  mov     rbx, rdx
0x18003fcc6  mov     r14, rcx
0x18003fcc9  mov     rdx, r9
0x18003fccc  mov     rcx, rbx
0x18003fccf  call    ?GetStoreTypeForDriver@NetSetupTransaction@@QEBA?AW4NetSetupStoreType@@AEAVActiveObject@NetSetup2@@@Z; NetSetupTransaction::GetStoreTypeForDriver(NetSetup2::ActiveObject &)
0x18003fcd4  lea     r8, [rbp+310h+Destination]
0x18003fcdb  mov     edx, eax
0x18003fcdd  mov     rcx, rsi
0x18003fce0  call    ?GetPathToDriver@NetSetupDriverStore@@SAXAEBUNetSetupObjectId@@W4NetSetupStoreType@@QEA_W@Z; NetSetupDriverStore::GetPathToDriver(NetSetupObjectId const &,NetSetupStoreType,wchar_t * const)
0x18003fce5  lea     r8, aKernel; "\\Kernel"
0x18003fcec  mov     edx, 104h; SizeInWords
0x18003fcf1  lea     rcx, [rbp+310h+Destination]; Destination
0x18003fcf8  call    cs:__imp_wcscat_s
0x18003fcfe  lea     rcx, [rbx+18h]
0x18003fd02  mov     [rsp+410h+var_3E8], 0
0x18003fd0b  mov     qword ptr [rsp+410h+var_3F0], 0
0x18003fd14  mov     r9d, 3
0x18003fd1a  lea     r8, [rbp+310h+Destination]
0x18003fd21  lea     rdx, [rsp+410h+hKey]
0x18003fd26  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18003fd2b  nop
0x18003fd2c  xorps   xmm0, xmm0
0x18003fd2f  movdqu  [rsp+410h+var_3C8], xmm0
0x18003fd35  mov     [rsp+410h+var_3B8], 0
0x18003fd3e  movdqu  xmmword ptr [rsp+410h+var_3B0], xmm0
0x18003fd44  mov     [rsp+410h+var_3A0], 0
0x18003fd4d  mov     rdi, [rbp+310h+arg_20]
0x18003fd54  mov     rbx, [rdi]
0x18003fd57  mov     rdi, [rdi+8]
0x18003fd5b  cmp     rbx, rdi
0x18003fd5e  jz      loc_18003FEDC
0x18003fd64  mov     r8, [rbx]
0x18003fd67  mov     rcx, r8
0x18003fd6a  call    ?GetPathType@NetSetupBindPath@@QEBA?AW4_NETSETUP_BINDING_PATH_TYPE@@XZ; NetSetupBindPath::GetPathType(void)
0x18003fd6f  test    eax, eax
0x18003fd71  jz      short loc_18003FDD6
0x18003fd73  cmp     eax, 1
0x18003fd76  jnz     loc_18003FED3
0x18003fd7c  xorps   xmm0, xmm0
0x18003fd7f  xor     eax, eax
0x18003fd81  movups  xmmword ptr [rbp+310h+Block], xmm0
0x18003fd88  mov     [rbp+310h+var_278], ax
0x18003fd8f  mov     rax, [r8+58h]
0x18003fd93  movups  xmm0, xmmword ptr [rax-10h]
0x18003fd97  movdqu  xmmword ptr [rbp+310h+Block], xmm0
0x18003fd9f  movzx   eax, word ptr [r8+70h]
0x18003fda4  mov     [rbp+310h+var_278], ax
0x18003fdab  lea     rax, [rbp+310h+var_276]
0x18003fdb2  mov     qword ptr [rsp+410h+var_3F0], rax
0x18003fdb7  lea     r9, [rbp+310h+Block]
0x18003fdbe  mov     r8, [rsp+410h+var_3B0+8]
0x18003fdc3  lea     rdx, [rbp+310h+var_390]
0x18003fdc7  lea     rcx, [rsp+410h+var_3B0]
0x18003fdcc  call    ??$insert@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x18003fdd1  jmp     loc_18003FED3
0x18003fdd6  mov     r9, [r8+58h]
0x18003fdda  cmp     dword ptr [r9-14h], 4
0x18003fddf  jnz     short loc_18003FE56
0x18003fde1  add     r9, 0FFFFFFFFFFFFFFF0h
0x18003fde5  mov     rdx, r14
0x18003fde8  lea     rcx, [rbp+310h+var_268]
0x18003fdef  call    ??$GetObjectWithFilter@VProtocolDriver@NetSetup2@@@details@NetSetup2@@YA?AVProtocolDriver@1@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::GetObjectWithFilter<NetSetup2::ProtocolDriver>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18003fdf4  nop
0x18003fdf5  xor     r9d, r9d
0x18003fdf8  lea     r8, NETSETUPPKEY_Driver_BindName; unsigned int
0x18003fdff  lea     rdx, [rbp+310h+var_388]; struct _NETSETUPPROPKEY *
0x18003fe03  lea     rcx, [rbp+310h+var_268]; this
0x18003fe0a  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18003fe0f  nop
0x18003fe10  lea     rdx, [rbp+310h+Block]
0x18003fe17  lea     rcx, [rbp+310h+var_388]
0x18003fe1b  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18003fe20  nop
0x18003fe21  lea     rcx, [rbp+310h+var_370]
0x18003fe25  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18003fe2a  nop
0x18003fe2b  lea     rdx, [rbp+310h+Block]
0x18003fe32  lea     rcx, [rsp+410h+var_3C8]
0x18003fe37  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18003fe3c  nop
0x18003fe3d  cmp     [rbp+310h+var_270], 8
0x18003fe45  jb      short loc_18003FE54
0x18003fe47  mov     rcx, [rbp+310h+Block]; Block
0x18003fe4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003fe53  nop
0x18003fe54  jmp     short loc_18003FEC7
0x18003fe56  cmp     dword ptr [r9-14h], 5
0x18003fe5b  jnz     short loc_18003FED3
0x18003fe5d  add     r9, 0FFFFFFFFFFFFFFF0h
0x18003fe61  mov     rdx, r14
0x18003fe64  lea     rcx, [rbp+310h+var_268]
0x18003fe6b  call    ??$GetObjectWithFilter@VServiceDriver@NetSetup2@@@details@NetSetup2@@YA?AVServiceDriver@1@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::GetObjectWithFilter<NetSetup2::ServiceDriver>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18003fe70  nop
0x18003fe71  lea     r8, NETSETUPPKEY_Driver_BindName
0x18003fe78  lea     rdx, [rbp+310h+var_388]; struct _NETSETUPPROPKEY *
0x18003fe7c  lea     rcx, [rbp+310h+var_268]; this
0x18003fe83  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18003fe88  nop
0x18003fe89  lea     rdx, [rbp+310h+Block]
0x18003fe90  mov     rcx, rax
0x18003fe93  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18003fe98  nop
0x18003fe99  lea     rcx, [rbp+310h+var_370]
0x18003fe9d  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18003fea2  nop
0x18003fea3  lea     rdx, [rbp+310h+Block]
0x18003feaa  lea     rcx, [rsp+410h+var_3C8]
0x18003feaf  call    ?push_back@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18003feb4  nop
0x18003feb5  xor     r8d, r8d
0x18003feb8  mov     dl, 1
0x18003feba  lea     rcx, [rbp+310h+Block]
0x18003fec1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003fec6  nop
0x18003fec7  lea     rcx, [rbp+310h+var_260]
0x18003fece  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18003fed3  add     rbx, 8
0x18003fed7  jmp     loc_18003FD5B
0x18003fedc  mov     rax, qword ptr [rsp+410h+var_3C8+8]
0x18003fee1  sub     rax, qword ptr [rsp+410h+var_3C8]
0x18003fee6  sar     rax, 5
0x18003feea  cmp     rax, 80h
0x18003fef0  jb      short loc_18003FF41
0x18003fef2  lea     r8, WPP_GLOBAL_Control
0x18003fef9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff00  cmp     rcx, r8
0x18003ff03  jz      short loc_18003FF22
0x18003ff05  cmp     byte ptr [rcx+19h], 2
0x18003ff09  jb      short loc_18003FF22
0x18003ff0b  lea     r9, [rsi+4]
0x18003ff0f  mov     edx, 13h
0x18003ff14  mov     qword ptr [rsp+410h+var_3F0], rax
0x18003ff19  mov     rcx, [rcx+10h]
0x18003ff1d  call    WPP_SF__guid_PP
0x18003ff22  mov     edx, 8007050Ch; int
0x18003ff27  lea     rcx, [rbp+310h+pExceptionObject]; this
0x18003ff2b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18003ff30  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18003ff37  lea     rcx, [rbp+310h+pExceptionObject]; pExceptionObject
0x18003ff3b  call    _CxxThrowException_0
0x18003ff41  mov     rdi, [rsp+410h+var_3B0+8]
0x18003ff46  mov     rdx, rdi
0x18003ff49  mov     rbx, [rsp+410h+var_3B0]
0x18003ff4e  sub     rdx, rbx
0x18003ff51  cmp     rdx, 900h
0x18003ff58  jb      short loc_18003FFBD
0x18003ff5a  lea     r8, WPP_GLOBAL_Control
0x18003ff61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff68  cmp     rcx, r8
0x18003ff6b  jz      short loc_18003FF9E
0x18003ff6d  cmp     byte ptr [rcx+19h], 2
0x18003ff71  jb      short loc_18003FF9E
0x18003ff73  mov     rax, 0E38E38E38E38E38Fh
0x18003ff7d  mul     rdx
0x18003ff80  mov     r8, rdx
0x18003ff83  shr     r8, 4
0x18003ff87  lea     r9, [rsi+4]
0x18003ff8b  mov     edx, 14h
0x18003ff90  mov     qword ptr [rsp+410h+var_3F0], r8
0x18003ff95  mov     rcx, [rcx+10h]
0x18003ff99  call    WPP_SF__guid_PP
0x18003ff9e  mov     edx, 8007050Ch; int
0x18003ffa3  lea     rcx, [rbp+310h+pExceptionObject]; this
0x18003ffa7  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18003ffac  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18003ffb3  lea     rcx, [rbp+310h+pExceptionObject]; pExceptionObject
0x18003ffb7  call    _CxxThrowException_0
0x18003ffbd  lea     rdx, [rsp+410h+var_3C8]
0x18003ffc2  lea     rcx, [rbp+310h+Block]
0x18003ffc9  call    ?ConvertMultiSzToBinary@RegistryKey@@SA?AVMultiSz@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; RegistryKey::ConvertMultiSzToBinary(std::vector<std::wstring> const &)
0x18003ffce  nop
0x18003ffcf  mov     r9, [rax+8]
0x18003ffd3  mov     r8, [rax]
0x18003ffd6  cmp     r8, r9
0x18003ffd9  jnz     short loc_18003FFE9
0x18003ffdb  lea     r9, word_18009A2AE
0x18003ffe2  lea     r8, ?emptyMultiSz@MultiSz@@0_WB; unsigned __int8 *
0x18003ffe9  sub     r9, r8; unsigned __int64
0x18003ffec  mov     [rsp+410h+var_3F0], 7; unsigned int
0x18003fff4  lea     rdx, aProtocollist; "ProtocolList"
0x18003fffb  lea     rcx, [rsp+410h+hKey]; this
0x180040000  call    ?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z; RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)
0x180040005  nop
0x180040006  lea     rcx, [rbp+310h+Block]
0x18004000d  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180040012  sub     rdi, rbx
0x180040015  mov     [rsp+410h+var_3F0], 3; unsigned int
0x18004001d  mov     r9, rdi; unsigned __int64
0x180040020  mov     r8, rbx; unsigned __int8 *
0x180040023  lea     rdx, aFilterlist; "FilterList"
0x18004002a  lea     rcx, [rsp+410h+hKey]; this
0x18004002f  call    ?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z; RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)
0x180040034  nop
0x180040035  test    rbx, rbx
0x180040038  jz      short loc_180040043
0x18004003a  mov     rcx, rbx; Block
0x18004003d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040042  nop
0x180040043  lea     rcx, [rsp+410h+var_3C8]
0x180040048  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004004d  nop
0x18004004e  mov     rcx, [rsp+410h+hKey]; hKey
0x180040053  test    rcx, rcx
0x180040056  jz      short loc_18004005E
0x180040058  call    cs:__imp_RegCloseKey
0x18004005e  mov     rcx, [rbp+310h+var_30]
0x180040065  xor     rcx, rsp; StackCookie
0x180040068  call    __security_check_cookie
0x18004006d  add     rsp, 3F0h
0x180040074  pop     r14
0x180040076  pop     rdi
0x180040077  pop     rsi
0x180040078  pop     rbx
0x180040079  pop     rbp
0x18004007a  retn
```

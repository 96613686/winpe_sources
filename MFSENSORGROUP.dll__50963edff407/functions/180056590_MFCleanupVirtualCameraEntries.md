# MFCleanupVirtualCameraEntries

- ea: `0x180056590`
- end: `0x1800567f7`
- name: `MFCleanupVirtualCameraEntries`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000ae14`
- `0x18000c348`
- `0x18000cb74`
- `0x1800158b8`
- `0x180015d60`
- `0x180015e58`
- `0x18002d02c`
- `0x1800329bc`
- `0x180042bb8`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`
- `0x180051a1c`
- `0x180056590`
- `0x18006f7b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800566bf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800566bf`

## pseudocode

```c
__int64 MFCleanupVirtualCameraEntries()
{
  __int64 v0; // r9
  int v1; // eax
  signed int v2; // edi
  void **i; // rbx
  __int64 v4; // rdx
  __int64 v5; // rdx
  void *v6; // rbx
  _QWORD *v7; // rdx
  char *v8; // rcx
  __int64 v9; // rax
  unsigned int v11; // [rsp+30h] [rbp-69h] BYREF
  __int64 v12; // [rsp+38h] [rbp-61h] BYREF
  void *Block[3]; // [rsp+40h] [rbp-59h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF

  utl::list<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>::list<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>(Block);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 142, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids);
  v1 = FSEnumDeviceInterfaces(&GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8, 0, Block, v0);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v1);
LABEL_23:
    if ( byte_18008D62D )
    {
      v5 = 148;
      goto LABEL_27;
    }
    goto LABEL_28;
  }
  for ( i = (void **)Block[0]; i != Block; i = (void **)*i )
  {
    memset_0(sz, 0, sizeof(sz));
    v12 = 0;
    pclsid = GUID_00000000_0000_0000_0000_000000000000;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 144, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, i[2]);
    if ( (int)FSGetDeviceInterfaceProperty2(
                (LPCWSTR)i[2],
                (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId,
                0x12u,
                (unsigned __int8 *)sz,
                0x4Eu,
                &v11) >= 0
      && CLSIDFromString(sz, &pclsid) >= 0
      && (int)VerifyCOMServerByClsid(&pclsid, 0, 0, 0) >= 0 )
    {
      if ( (unsigned __int8)byte_18008D62D < 8u )
        goto LABEL_21;
      v4 = 147;
LABEL_20:
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), v4, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, i[2]);
      goto LABEL_21;
    }
    v2 = FSRemoveVirtualCameraByName((const unsigned __int16 *)i[2]);
    if ( v2 >= 0 )
    {
      if ( (unsigned __int8)byte_18008D62D < 8u )
        goto LABEL_21;
      v4 = 146;
      goto LABEL_20;
    }
    if ( byte_18008D62D )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        145,
        (unsigned int)&WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
        v2,
        (__int64)i[2]);
LABEL_21:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v12);
  }
  InternalCleanupVirtualCameraEntries_Registry();
  if ( v2 < 0 )
    goto LABEL_23;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v5 = 149;
LABEL_27:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v5,
      &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      (unsigned int)v2);
  }
LABEL_28:
  while ( 1 )
  {
    v6 = Block[0];
    if ( Block[0] == Block )
      break;
    v7 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    v8 = (char *)Block[0] + 16;
    v9 = *(_QWORD *)Block[0];
    *v7 = *(_QWORD *)Block[0];
    *(_QWORD *)(v9 + 8) = v7;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v8);
    operator delete(v6);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180056590  push    rbp
0x180056592  push    rbx
0x180056593  push    rsi
0x180056594  push    rdi
0x180056595  lea     rbp, [rsp-3Fh]
0x18005659a  sub     rsp, 0D8h
0x1800565a1  mov     rax, cs:__security_cookie
0x1800565a8  xor     rax, rsp
0x1800565ab  mov     [rbp+57h+var_30], rax
0x1800565af  lea     rcx, [rbp+57h+Block]
0x1800565b3  call    ??0?$list@U?$pair@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>>::list<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>>(void)
0x1800565b8  cmp     cs:byte_18008D62D, 8
0x1800565bf  lea     rsi, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800565c6  jb      short loc_1800565E3
0x1800565c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565cf  mov     edx, 8Eh
0x1800565d4  mov     r8, rsi
0x1800565d7  mov     rcx, [rcx+0D8h]
0x1800565de  call    WPP_SF_
0x1800565e3  lea     r8, [rbp+57h+Block]
0x1800565e7  xor     edx, edx
0x1800565e9  lea     rcx, _GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8
0x1800565f0  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800565f5  mov     edi, eax
0x1800565f7  test    eax, eax
0x1800565f9  jns     short loc_18005662C
0x1800565fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180056602  jb      loc_180056771
0x180056608  mov     rcx, cs:WPP_GLOBAL_Control
0x18005660f  mov     edx, 8Fh
0x180056614  xor     r9d, r9d
0x180056617  mov     [rsp+0F0h+var_D0], eax
0x18005661b  mov     r8, rsi
0x18005661e  mov     rcx, [rcx+10h]
0x180056622  call    WPP_SF_qD
0x180056627  jmp     loc_180056771
0x18005662c  mov     rbx, [rbp+57h+Block]
0x180056630  lea     rax, [rbp+57h+Block]
0x180056634  cmp     rbx, rax
0x180056637  jz      loc_180056768
0x18005663d  xor     edx, edx; Val
0x18005663f  lea     rcx, [rbp+57h+sz]; void *
0x180056643  lea     r8d, [rdx+50h]; Size
0x180056647  call    memset_0
0x18005664c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180056653  mov     [rbp+57h+var_B8], 0
0x18005665b  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180056660  cmp     cs:byte_18008D62D, 8
0x180056667  jb      short loc_180056688
0x180056669  mov     rcx, cs:WPP_GLOBAL_Control
0x180056670  mov     edx, 90h
0x180056675  mov     r9, [rbx+10h]
0x180056679  mov     r8, rsi
0x18005667c  mov     rcx, [rcx+0D8h]
0x180056683  call    WPP_SF_S
0x180056688  mov     rcx, [rbx+10h]; pszDeviceInterface
0x18005668c  lea     rax, [rbp+57h+var_C0]
0x180056690  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x180056695  lea     r9, [rbp+57h+sz]; unsigned __int8 *
0x180056699  mov     r8d, 12h; unsigned int
0x18005669f  mov     [rsp+0F0h+var_D0], 4Eh ; 'N'; unsigned int
0x1800566a7  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId; PropertyKey
0x1800566ae  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x1800566b3  test    eax, eax
0x1800566b5  js      short loc_1800566EE
0x1800566b7  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800566bb  lea     rcx, [rbp+57h+sz]; lpsz
0x1800566bf  call    cs:__imp_CLSIDFromString
0x1800566c5  test    eax, eax
0x1800566c7  js      short loc_1800566EE
0x1800566c9  xor     r9d, r9d; int *
0x1800566cc  lea     rcx, [rbp+57h+pclsid]; struct _GUID *
0x1800566d0  xor     r8d, r8d; int
0x1800566d3  xor     edx, edx; unsigned __int16 *
0x1800566d5  call    ?VerifyCOMServerByClsid@@YAJAEBU_GUID@@PEAGJPEAJ@Z; VerifyCOMServerByClsid(_GUID const &,ushort *,long,long *)
0x1800566da  test    eax, eax
0x1800566dc  js      short loc_1800566EE
0x1800566de  cmp     cs:byte_18008D62D, 8
0x1800566e5  jb      short loc_180056757
0x1800566e7  mov     edx, 93h
0x1800566ec  jmp     short loc_18005673D
0x1800566ee  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800566f2  call    ?FSRemoveVirtualCameraByName@@YAJPEBG@Z; FSRemoveVirtualCameraByName(ushort const *)
0x1800566f7  mov     edi, eax
0x1800566f9  test    eax, eax
0x1800566fb  jns     short loc_18005672F
0x1800566fd  cmp     cs:byte_18008D62D, 1
0x180056704  jb      short loc_180056757
0x180056706  mov     rcx, cs:WPP_GLOBAL_Control
0x18005670d  mov     edx, 91h
0x180056712  mov     rax, [rbx+10h]
0x180056716  mov     r9d, edi
0x180056719  mov     r8, rsi
0x18005671c  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180056721  mov     rcx, [rcx+0D8h]
0x180056728  call    WPP_SF_dS
0x18005672d  jmp     short loc_180056757
0x18005672f  cmp     cs:byte_18008D62D, 8
0x180056736  jb      short loc_180056757
0x180056738  mov     edx, 92h
0x18005673d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056744  mov     r8, rsi
0x180056747  mov     r9, [rbx+10h]
0x18005674b  mov     rcx, [rcx+0D8h]
0x180056752  call    WPP_SF_S
0x180056757  lea     rcx, [rbp+57h+var_B8]
0x18005675b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180056760  mov     rbx, [rbx]
0x180056763  jmp     loc_180056630
0x180056768  call    ?InternalCleanupVirtualCameraEntries_Registry@@YAJXZ; InternalCleanupVirtualCameraEntries_Registry(void)
0x18005676d  test    edi, edi
0x18005676f  jns     short loc_180056781
0x180056771  cmp     cs:byte_18008D62D, 1
0x180056778  jb      short loc_1800567A8
0x18005677a  mov     edx, 94h
0x18005677f  jmp     short loc_18005678F
0x180056781  cmp     cs:byte_18008D62D, 8
0x180056788  jb      short loc_1800567A8
0x18005678a  mov     edx, 95h
0x18005678f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056796  mov     r9d, edi
0x180056799  mov     r8, rsi
0x18005679c  mov     rcx, [rcx+0D8h]
0x1800567a3  call    WPP_SF_d
0x1800567a8  mov     rbx, [rbp+57h+Block]
0x1800567ac  lea     rax, [rbp+57h+Block]
0x1800567b0  cmp     rbx, rax
0x1800567b3  jz      short loc_1800567DD
0x1800567b5  mov     rdx, [rbx+8]
0x1800567b9  lea     rcx, [rbx+10h]
0x1800567bd  mov     rax, [rbx]
0x1800567c0  mov     [rdx], rax
0x1800567c3  mov     [rax+8], rdx
0x1800567c7  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800567cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800567d3  mov     rcx, rbx; Block
0x1800567d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800567db  jmp     short loc_1800567A8
0x1800567dd  mov     eax, edi
0x1800567df  mov     rcx, [rbp+57h+var_30]
0x1800567e3  xor     rcx, rsp; StackCookie
0x1800567e6  call    __security_check_cookie
0x1800567eb  add     rsp, 0D8h
0x1800567f2  pop     rdi
0x1800567f3  pop     rsi
0x1800567f4  pop     rbx
0x1800567f5  pop     rbp
0x1800567f6  retn
```

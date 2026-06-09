# FSMonitorService::InternalEnableVirtualCameras(void)

- ea: `0x180008d7c`
- end: `0x18000908a`
- name: `?InternalEnableVirtualCameras@FSMonitorService@@IEAAJXZ`
- size: `782`
- prototype: `__int64 __fastcall(FSMonitorService *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a994`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006ae8`
- `0x180006d38`
- `0x180006fc0`
- `0x180008d7c`
- `0x18000a728`
- `0x18000d154`
- `0x18000d4f8`
- `0x18000d62c`
- `0x180023978`
- `0x180041b60`
- `0x1800421fc`
- `0x1800452c4`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009075`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009075`

## pseudocode

```c
__int64 __fastcall FSMonitorService::InternalEnableVirtualCameras(FSMonitorService *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int v3; // esi
  void **i; // rbx
  const unsigned __int16 *v5; // rcx
  int v6; // edx
  char v7; // r8
  int v8; // edx
  struct FSMVirtualCamera *v9; // r15
  char v10; // r8
  __int64 v11; // rdx
  void **v13[11]; // [rsp+30h] [rbp-58h] BYREF
  struct FSMVirtualCamera *v14; // [rsp+90h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 272);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(v13);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 186, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this);
  v3 = FSMEnumDevicesByCategory(&GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8, 0, 0, v13);
  if ( v3 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v3);
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v11 = 195;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  for ( i = v13[0]; i != (void **)v13; i = (void **)*i )
  {
    v5 = (const unsigned __int16 *)i[2];
    v14 = 0;
    PatchV1VCamData(v5);
    if ( FSIsDeviceInterfaceEnabled((const unsigned __int16 *)i[2]) )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 8u )
        goto LABEL_33;
      v6 = 188;
      goto LABEL_32;
    }
    v3 = FSMVirtualCamera::LoadVirtualCameraByName((const unsigned __int16 *)i[2], 0, &v14);
    if ( v3 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          189,
          (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
          (_DWORD)this,
          v3,
          (__int64)i[2]);
      if ( FSRemoveVirtualCameraByName((const unsigned __int16 *)i[2]) < 0
        && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
        v8 = 190;
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    v9 = v14;
    if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)v14 + 5) + 40LL))((char *)v14 + 40)
      && !FSIsDeviceInterfaceEnabled((const unsigned __int16 *)i[2]) )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          191,
          (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
          (_DWORD)this,
          (__int64)i[2]);
      if ( (*(int (__fastcall **)(__int64))(*((_QWORD *)v9 + 5) + 72LL))((__int64)v9 + 40) < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            192,
            (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
            (_DWORD)this,
            v10,
            (__int64)i[2]);
        if ( FSRemoveVirtualCameraByName((const unsigned __int16 *)i[2]) < 0
          && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        {
          v8 = 193;
LABEL_18:
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v8,
            (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
            (_DWORD)this,
            v7,
            (__int64)i[2]);
        }
      }
LABEL_19:
      v3 = 0;
      goto LABEL_33;
    }
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    {
      v6 = 194;
LABEL_32:
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v6,
        (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
        (_DWORD)this,
        (__int64)i[2]);
    }
LABEL_33:
    wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>((__int64 *)&v14);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v11 = 196;
LABEL_39:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v11, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v3);
  }
LABEL_40:
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v13);
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008d7c  push    rbx
0x180008d7e  push    rbp
0x180008d7f  push    rsi
0x180008d80  push    rdi
0x180008d81  push    r12
0x180008d83  push    r15
0x180008d85  sub     rsp, 58h
0x180008d89  lea     rdi, [rcx+110h]
0x180008d90  mov     rbp, rcx
0x180008d93  mov     rcx, rdi; lpCriticalSection
0x180008d96  call    cs:__imp_EnterCriticalSection
0x180008d9c  lea     rcx, [rsp+88h+var_58]
0x180008da1  call    ??0?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(void)
0x180008da6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008dab  lea     r12, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008db2  cmp     al, 8
0x180008db4  jb      short loc_180008DD4
0x180008db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dbd  mov     edx, 0BAh
0x180008dc2  mov     r9, rbp
0x180008dc5  mov     r8, r12
0x180008dc8  mov     rcx, [rcx+0D8h]
0x180008dcf  call    WPP_SF_q
0x180008dd4  lea     r9, [rsp+88h+var_58]
0x180008dd9  xor     r8d, r8d
0x180008ddc  xor     edx, edx
0x180008dde  lea     rcx, _GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8
0x180008de5  call    FSMEnumDevicesByCategory
0x180008dea  mov     esi, eax
0x180008dec  test    eax, eax
0x180008dee  jns     short loc_180008E22
0x180008df0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180008df5  cmp     al, 1
0x180008df7  jb      short loc_180008E18
0x180008df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e00  mov     edx, 0BBh
0x180008e05  mov     r9, rbp
0x180008e08  mov     dword ptr [rsp+88h+var_68], esi
0x180008e0c  mov     r8, r12
0x180008e0f  mov     rcx, [rcx+10h]
0x180008e13  call    WPP_SF_qD
0x180008e18  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008e1d  jmp     loc_180009037
0x180008e22  mov     rbx, [rsp+88h+var_58]
0x180008e27  lea     rax, [rsp+88h+var_58]
0x180008e2c  cmp     rbx, rax
0x180008e2f  jz      loc_18000902E
0x180008e35  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008e39  mov     [rsp+88h+arg_0], 0
0x180008e45  call    ?PatchV1VCamData@@YAJPEBG@Z; PatchV1VCamData(ushort const *)
0x180008e4a  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008e4e  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x180008e53  test    al, al
0x180008e55  jz      short loc_180008E6E
0x180008e57  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008e5c  cmp     al, 8
0x180008e5e  jb      loc_180009019
0x180008e64  mov     edx, 0BCh
0x180008e69  jmp     loc_180008FF7
0x180008e6e  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008e72  lea     r8, [rsp+88h+arg_0]; struct FSMVirtualCamera **
0x180008e7a  xor     edx, edx; bool
0x180008e7c  call    ?LoadVirtualCameraByName@FSMVirtualCamera@@SAJPEBG_NPEAPEAV1@@Z; FSMVirtualCamera::LoadVirtualCameraByName(ushort const *,bool,FSMVirtualCamera * *)
0x180008e81  mov     esi, eax
0x180008e83  test    eax, eax
0x180008e85  jns     loc_180008F0B
0x180008e8b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008e90  cmp     al, 1
0x180008e92  jb      short loc_180008EBF
0x180008e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e9b  mov     edx, 0BDh
0x180008ea0  mov     rax, [rbx+10h]
0x180008ea4  mov     r9, rbp
0x180008ea7  mov     [rsp+88h+var_60], rax
0x180008eac  mov     r8, r12
0x180008eaf  mov     dword ptr [rsp+88h+var_68], esi
0x180008eb3  mov     rcx, [rcx+0D8h]
0x180008eba  call    WPP_SF_qDS
0x180008ebf  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008ec3  call    ?FSRemoveVirtualCameraByName@@YAJPEBG@Z; FSRemoveVirtualCameraByName(ushort const *)
0x180008ec8  mov     r8d, eax
0x180008ecb  test    eax, eax
0x180008ecd  jns     short loc_180008F04
0x180008ecf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008ed4  cmp     al, 1
0x180008ed6  jb      short loc_180008F04
0x180008ed8  mov     edx, 0BEh
0x180008edd  mov     rcx, [rbx+10h]
0x180008ee1  mov     r9, rbp
0x180008ee4  mov     [rsp+88h+var_60], rcx
0x180008ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ef0  mov     dword ptr [rsp+88h+var_68], r8d
0x180008ef5  mov     r8, r12
0x180008ef8  mov     rcx, [rcx+0D8h]
0x180008eff  call    WPP_SF_qDS
0x180008f04  xor     esi, esi
0x180008f06  jmp     loc_180009019
0x180008f0b  mov     r15, [rsp+88h+arg_0]
0x180008f13  mov     rax, [r15+28h]
0x180008f17  lea     rcx, [r15+28h]
0x180008f1b  mov     rax, [rax+28h]
0x180008f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f24  test    eax, eax
0x180008f26  jz      loc_180008FE9
0x180008f2c  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008f30  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x180008f35  test    al, al
0x180008f37  jnz     loc_180008FE9
0x180008f3d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008f42  cmp     al, 8
0x180008f44  jb      short loc_180008F6D
0x180008f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f4d  mov     edx, 0BFh
0x180008f52  mov     rax, [rbx+10h]
0x180008f56  mov     r9, rbp
0x180008f59  mov     r8, r12
0x180008f5c  mov     [rsp+88h+var_68], rax
0x180008f61  mov     rcx, [rcx+0D8h]
0x180008f68  call    WPP_SF_qS
0x180008f6d  mov     rax, [r15+28h]
0x180008f71  lea     rcx, [r15+28h]
0x180008f75  mov     rax, [rax+48h]
0x180008f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f7e  mov     r8d, eax
0x180008f81  test    eax, eax
0x180008f83  jns     loc_180008F04
0x180008f89  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008f8e  cmp     al, 1
0x180008f90  jb      short loc_180008FBE
0x180008f92  mov     rcx, [rbx+10h]
0x180008f96  mov     edx, 0C0h
0x180008f9b  mov     [rsp+88h+var_60], rcx
0x180008fa0  mov     r9, rbp
0x180008fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008faa  mov     dword ptr [rsp+88h+var_68], r8d
0x180008faf  mov     r8, r12
0x180008fb2  mov     rcx, [rcx+0D8h]
0x180008fb9  call    WPP_SF_qDS
0x180008fbe  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180008fc2  call    ?FSRemoveVirtualCameraByName@@YAJPEBG@Z; FSRemoveVirtualCameraByName(ushort const *)
0x180008fc7  mov     r8d, eax
0x180008fca  test    eax, eax
0x180008fcc  jns     loc_180008F04
0x180008fd2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008fd7  cmp     al, 1
0x180008fd9  jb      loc_180008F04
0x180008fdf  mov     edx, 0C1h
0x180008fe4  jmp     loc_180008EDD
0x180008fe9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180008fee  cmp     al, 8
0x180008ff0  jb      short loc_180009019
0x180008ff2  mov     edx, 0C2h
0x180008ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ffe  mov     r9, rbp
0x180009001  mov     rax, [rbx+10h]
0x180009005  mov     r8, r12
0x180009008  mov     [rsp+88h+var_68], rax
0x18000900d  mov     rcx, [rcx+0D8h]
0x180009014  call    WPP_SF_qS
0x180009019  lea     rcx, [rsp+88h+arg_0]
0x180009021  call    ??1?$com_ptr_t@VFSMNotification@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<FSMNotification,wil::err_returncode_policy>::~com_ptr_t<FSMNotification,wil::err_returncode_policy>(void)
0x180009026  mov     rbx, [rbx]
0x180009029  jmp     loc_180008E27
0x18000902e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180009033  test    esi, esi
0x180009035  jns     short loc_180009042
0x180009037  cmp     al, 1
0x180009039  jb      short loc_180009068
0x18000903b  mov     edx, 0C3h
0x180009040  jmp     short loc_18000904B
0x180009042  cmp     al, 8
0x180009044  jb      short loc_180009068
0x180009046  mov     edx, 0C4h
0x18000904b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009052  mov     r9, rbp
0x180009055  mov     r8, r12
0x180009058  mov     dword ptr [rsp+88h+var_68], esi
0x18000905c  mov     rcx, [rcx+0D8h]
0x180009063  call    WPP_SF_qD
0x180009068  lea     rcx, [rsp+88h+var_58]
0x18000906d  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x180009072  mov     rcx, rdi; lpCriticalSection
0x180009075  call    cs:__imp_LeaveCriticalSection
0x18000907b  mov     eax, esi
0x18000907d  add     rsp, 58h
0x180009081  pop     r15
0x180009083  pop     r12
0x180009085  pop     rdi
0x180009086  pop     rsi
0x180009087  pop     rbp
0x180009088  pop     rbx
0x180009089  retn
```

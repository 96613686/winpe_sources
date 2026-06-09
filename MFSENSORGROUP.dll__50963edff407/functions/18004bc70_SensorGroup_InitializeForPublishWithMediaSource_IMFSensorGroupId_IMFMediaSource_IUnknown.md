# SensorGroup::InitializeForPublishWithMediaSource(IMFSensorGroupId *,IMFMediaSource *,IUnknown *)

- ea: `0x18004bc70`
- end: `0x18004c20f`
- name: `?InitializeForPublishWithMediaSource@SensorGroup@@IEAAJPEAUIMFSensorGroupId@@PEAUIMFMediaSource@@PEAUIUnknown@@@Z`
- size: `1439`
- prototype: `__int64 __fastcall(SensorGroup *__hidden this, struct IMFSensorGroupId *, struct IMFMediaSource *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b1ec`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180009b74`
- `0x180011d20`
- `0x1800231c8`
- `0x180028d34`
- `0x18002c008`
- `0x180033004`
- `0x18004bc70`
- `0x18004e18c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c1ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c1ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bc9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bc9c`
- `MFPlat!MFCreateAttributes` at `0x18004bf43`
- `MFPlat!MFCreateAttributes` at `0x18004bf43`

## pseudocode

```c
__int64 __fastcall SensorGroup::InitializeForPublishWithMediaSource(
        SensorGroup *this,
        struct IMFSensorGroupId *a2,
        struct IMFMediaSource *a3,
        struct IUnknown *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  struct IMFMediaSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IMFMediaSource *, const IID *const, void **); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // ebx
  HRESULT (__stdcall *v23)(IMFMediaSource *, const IID *const, void **); // rbx
  const struct _GUID *v24; // rcx
  void *v25; // r14
  int v26; // ebx
  IMFAttributes *v27; // rdi
  __int64 (__fastcall *v28)(void *, __int64, __int64, IMFAttributes *, int, struct IUnknown *, int *); // rsi
  __int64 v29; // rax
  __int64 v30; // rcx
  void *v31; // rbx
  __int64 (__fastcall **v32)(void *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v33)(void *, GUID *, __int64 *); // rdi
  __int64 v34; // rdx
  void *v36; // [rsp+40h] [rbp-29h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-21h] BYREF
  int v38; // [rsp+50h] [rbp-19h] BYREF
  __int64 v39; // [rsp+58h] [rbp-11h] BYREF
  __int64 v40; // [rsp+60h] [rbp-9h] BYREF
  __int64 v41; // [rsp+68h] [rbp-1h] BYREF
  __int64 v42; // [rsp+70h] [rbp+7h] BYREF
  __int64 *v43; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v44[8]; // [rsp+80h] [rbp+17h] BYREF
  int v45; // [rsp+D0h] [rbp+67h] BYREF
  int v46; // [rsp+E0h] [rbp+77h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v45 = 0;
  v43 = 0;
  v42 = 0;
  v44[0] = 0;
  v41 = 0;
  ppMFAttributes = 0;
  v46 = 0;
  v40 = 0;
  v36 = 0;
  v39 = 0;
  v38 = 0;
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_63;
    v12 = 150;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 151;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v10);
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 27), v8, v9, this, a2, a3);
  ComSmartPtr<IMFSensorGroupId>::operator=((_QWORD *)this + 22, (__int64)a2);
  v10 = AutoSecurityAttributes::Set(
          (PSECURITY_DESCRIPTOR *)this + 15,
          L"O:LSD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 153;
      goto LABEL_4;
    }
LABEL_63:
    if ( byte_18008D62D )
    {
      v34 = 169;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v34, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v11);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 22);
  v14 = **v13;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v43);
  v10 = v14(v13, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, (__int64 *)&v43);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 154;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v43 + 80))(v43, &v45);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 155;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  if ( v45 != 1 )
  {
    v11 = -2147023266;
    if ( !g_wppLevels )
      goto LABEL_63;
    v15 = 156;
LABEL_62:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v11);
    goto LABEL_63;
  }
  v16 = *v43;
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v16 + 88))(v43, 0, &v39);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 157;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v17 = v42;
  lpVtbl = a3->lpVtbl;
  v42 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v10 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, __int64 *))QueryInterface)(
          a3,
          &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
          &v42);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 158;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v20 = v42;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 104LL);
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v41);
  v10 = v21(v20, &v41);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 159;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 240LL))(v41, &v46);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 160;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v22 = v46;
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v10 = MFCreateAttributes(&ppMFAttributes, v22 + 1);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 161;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v41 + 256LL))(v41, ppMFAttributes);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 162;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v10 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
          ppMFAttributes,
          MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
          2);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 163;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v23 = a3->lpVtbl->QueryInterface;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(v44);
  v10 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, __int64 *))v23)(
          a3,
          &GUID_00000000_0000_0000_c000_000000000046,
          v44);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 164;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v24 = (const struct _GUID *)v36;
  v36 = 0;
  v10 = SensorDevice::CreateSensorDevice(v24, &v36);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 165;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v25 = v36;
  v26 = *((_DWORD *)this + 42);
  v27 = ppMFAttributes;
  v28 = *(__int64 (__fastcall **)(void *, __int64, __int64, IMFAttributes *, int, struct IUnknown *, int *))(*(_QWORD *)v36 + 24LL);
  v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
  v10 = v28(v25, v44[0], v29, v27, v26, a4, &v38);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 166;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  v30 = v40;
  v31 = v36;
  v32 = *(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v36;
  v40 = 0;
  v33 = *v32;
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  v11 = v33(v31, &GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4, &v40);
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_63;
    v15 = 167;
    goto LABEL_62;
  }
  if ( !(unsigned int)CTUnkArray<IMFSensorDevice>::Add((char *)this + 96, v40) )
  {
    v11 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_63;
    v15 = 168;
    goto LABEL_62;
  }
  *((_DWORD *)this + 42) += v38;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v34 = 170;
    goto LABEL_67;
  }
LABEL_68:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v39);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v36);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v40);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(v44);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v42);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v43);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004bc70  mov     [rsp-8+arg_8], rbx
0x18004bc75  push    rbp
0x18004bc76  push    rsi
0x18004bc77  push    rdi
0x18004bc78  push    r12
0x18004bc7a  push    r13
0x18004bc7c  push    r14
0x18004bc7e  push    r15
0x18004bc80  lea     rbp, [rsp-27h]
0x18004bc85  sub     rsp, 90h
0x18004bc8c  mov     r15, rcx
0x18004bc8f  mov     r12, r9
0x18004bc92  add     rcx, 20h ; ' '; lpCriticalSection
0x18004bc96  mov     rsi, r8
0x18004bc99  mov     rbx, rdx
0x18004bc9c  call    cs:__imp_EnterCriticalSection
0x18004bca2  xor     r14d, r14d
0x18004bca5  mov     [rbp+57h+arg_0], r14d
0x18004bca9  mov     [rbp+57h+var_48], r14
0x18004bcad  mov     [rbp+57h+var_50], r14
0x18004bcb1  mov     [rbp+57h+var_40], r14
0x18004bcb5  mov     [rbp+57h+var_58], r14
0x18004bcb9  mov     [rbp+57h+ppMFAttributes], r14
0x18004bcbd  mov     [rbp+57h+arg_10], r14d
0x18004bcc1  mov     [rbp+57h+var_60], r14
0x18004bcc5  mov     [rbp+57h+var_80], r14
0x18004bcc9  mov     [rbp+57h+var_68], r14
0x18004bccd  mov     [rbp+57h+var_70], r14d
0x18004bcd1  test    rsi, rsi
0x18004bcd4  jnz     short loc_18004BCF8
0x18004bcd6  mov     eax, 80070057h
0x18004bcdb  mov     ebx, eax
0x18004bcdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bce4  jb      loc_18004C157
0x18004bcea  mov     edx, 96h
0x18004bcef  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18004bcf3  jmp     loc_18004C13D
0x18004bcf8  test    rbx, rbx
0x18004bcfb  jnz     short loc_18004BD18
0x18004bcfd  mov     eax, 80070057h
0x18004bd02  mov     ebx, eax
0x18004bd04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bd0b  jb      loc_18004C157
0x18004bd11  mov     edx, 97h
0x18004bd16  jmp     short loc_18004BCEF
0x18004bd18  cmp     cs:byte_18008D62D, 8
0x18004bd1f  jb      short loc_18004BD41
0x18004bd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd28  mov     r9, r15
0x18004bd2b  mov     [rsp+0C0h+var_98], rsi
0x18004bd30  mov     [rsp+0C0h+var_A0], rbx
0x18004bd35  mov     rcx, [rcx+0D8h]
0x18004bd3c  call    WPP_SF_qqq
0x18004bd41  lea     rdi, [r15+0B0h]
0x18004bd48  mov     rdx, rbx
0x18004bd4b  mov     rcx, rdi
0x18004bd4e  call    ??4?$ComSmartPtr@UIMFSensorGroupId@@@@QEAAPEAUIMFSensorGroupId@@PEAU1@@Z; ComSmartPtr<IMFSensorGroupId>::operator=(IMFSensorGroupId *)
0x18004bd53  lea     rcx, [r15+78h]; this
0x18004bd57  lea     rdx, aOLsdAGaBaAGaOw; "O:LSD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGX;"...
0x18004bd5e  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x18004bd63  mov     ebx, eax
0x18004bd65  test    eax, eax
0x18004bd67  jns     short loc_18004BD80
0x18004bd69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bd70  jb      loc_18004C157
0x18004bd76  mov     edx, 99h
0x18004bd7b  jmp     loc_18004BCEF
0x18004bd80  mov     rdi, [rdi]
0x18004bd83  lea     rcx, [rbp+57h+var_48]
0x18004bd87  mov     rax, [rdi]
0x18004bd8a  mov     rbx, [rax]
0x18004bd8d  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18004bd92  lea     r8, [rbp+57h+var_48]
0x18004bd96  mov     rcx, rdi
0x18004bd99  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x18004bda0  mov     rax, rbx
0x18004bda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bda8  mov     ebx, eax
0x18004bdaa  test    eax, eax
0x18004bdac  jns     short loc_18004BDC5
0x18004bdae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bdb5  jb      loc_18004C157
0x18004bdbb  mov     edx, 9Ah
0x18004bdc0  jmp     loc_18004BCEF
0x18004bdc5  mov     rcx, [rbp+57h+var_48]
0x18004bdc9  lea     rdx, [rbp+57h+arg_0]
0x18004bdcd  mov     rax, [rcx]
0x18004bdd0  mov     rax, [rax+50h]
0x18004bdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdd9  mov     ebx, eax
0x18004bddb  test    eax, eax
0x18004bddd  jns     short loc_18004BDF6
0x18004bddf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bde6  jb      loc_18004C157
0x18004bdec  mov     edx, 9Bh
0x18004bdf1  jmp     loc_18004BCEF
0x18004bdf6  cmp     [rbp+57h+arg_0], 1
0x18004bdfa  jz      short loc_18004BE18
0x18004bdfc  mov     ebx, 8007065Eh
0x18004be01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004be08  jb      loc_18004C157
0x18004be0e  mov     edx, 9Ch
0x18004be13  jmp     loc_18004C139
0x18004be18  mov     rcx, [rbp+57h+var_68]
0x18004be1c  mov     rbx, [rbp+57h+var_48]
0x18004be20  mov     rax, [rbx]
0x18004be23  mov     [rbp+57h+var_68], r14
0x18004be27  mov     rdi, [rax+58h]
0x18004be2b  test    rcx, rcx
0x18004be2e  jz      short loc_18004BE3C
0x18004be30  mov     rdx, [rcx]
0x18004be33  mov     rax, [rdx+10h]
0x18004be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be3c  lea     r8, [rbp+57h+var_68]
0x18004be40  xor     edx, edx
0x18004be42  mov     rcx, rbx
0x18004be45  mov     rax, rdi
0x18004be48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be4d  mov     ebx, eax
0x18004be4f  test    eax, eax
0x18004be51  jns     short loc_18004BE6A
0x18004be53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004be5a  jb      loc_18004C157
0x18004be60  mov     edx, 9Dh
0x18004be65  jmp     loc_18004BCEF
0x18004be6a  mov     rcx, [rbp+57h+var_50]
0x18004be6e  mov     rax, [rsi]
0x18004be71  mov     [rbp+57h+var_50], r14
0x18004be75  mov     rbx, [rax]
0x18004be78  test    rcx, rcx
0x18004be7b  jz      short loc_18004BE89
0x18004be7d  mov     rdx, [rcx]
0x18004be80  mov     rax, [rdx+10h]
0x18004be84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be89  lea     r8, [rbp+57h+var_50]
0x18004be8d  mov     rcx, rsi
0x18004be90  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x18004be97  mov     rax, rbx
0x18004be9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be9f  mov     ebx, eax
0x18004bea1  test    eax, eax
0x18004bea3  jns     short loc_18004BEBC
0x18004bea5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004beac  jb      loc_18004C157
0x18004beb2  mov     edx, 9Eh
0x18004beb7  jmp     loc_18004BCEF
0x18004bebc  mov     rdi, [rbp+57h+var_50]
0x18004bec0  lea     rcx, [rbp+57h+var_58]
0x18004bec4  mov     rax, [rdi]
0x18004bec7  mov     rbx, [rax+68h]
0x18004becb  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18004bed0  lea     rdx, [rbp+57h+var_58]
0x18004bed4  mov     rcx, rdi
0x18004bed7  mov     rax, rbx
0x18004beda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bedf  mov     ebx, eax
0x18004bee1  test    eax, eax
0x18004bee3  jns     short loc_18004BEFC
0x18004bee5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004beec  jb      loc_18004C157
0x18004bef2  mov     edx, 9Fh
0x18004bef7  jmp     loc_18004BCEF
0x18004befc  mov     rcx, [rbp+57h+var_58]
0x18004bf00  lea     rdx, [rbp+57h+arg_10]
0x18004bf04  mov     rax, [rcx]
0x18004bf07  mov     rax, [rax+0F0h]
0x18004bf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf13  mov     ebx, eax
0x18004bf15  test    eax, eax
0x18004bf17  jns     short loc_18004BF30
0x18004bf19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bf20  jb      loc_18004C157
0x18004bf26  mov     edx, 0A0h
0x18004bf2b  jmp     loc_18004BCEF
0x18004bf30  mov     ebx, [rbp+57h+arg_10]
0x18004bf33  lea     rcx, [rbp+57h+ppMFAttributes]
0x18004bf37  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18004bf3c  lea     edx, [rbx+1]; cInitialSize
0x18004bf3f  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x18004bf43  call    cs:__imp_MFCreateAttributes
0x18004bf49  mov     ebx, eax
0x18004bf4b  test    eax, eax
0x18004bf4d  jns     short loc_18004BF66
0x18004bf4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bf56  jb      loc_18004C157
0x18004bf5c  mov     edx, 0A1h
0x18004bf61  jmp     loc_18004BCEF
0x18004bf66  mov     rcx, [rbp+57h+var_58]
0x18004bf6a  mov     rdx, [rbp+57h+ppMFAttributes]
0x18004bf6e  mov     rax, [rcx]
0x18004bf71  mov     rax, [rax+100h]
0x18004bf78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf7d  mov     ebx, eax
0x18004bf7f  test    eax, eax
0x18004bf81  jns     short loc_18004BF9A
0x18004bf83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bf8a  jb      loc_18004C157
0x18004bf90  mov     edx, 0A2h
0x18004bf95  jmp     loc_18004BCEF
0x18004bf9a  mov     rcx, [rbp+57h+ppMFAttributes]
0x18004bf9e  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE
0x18004bfa5  mov     r8d, 2
0x18004bfab  mov     rax, [rcx]
0x18004bfae  mov     rax, [rax+0A8h]
0x18004bfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfba  mov     ebx, eax
0x18004bfbc  test    eax, eax
0x18004bfbe  jns     short loc_18004BFD7
0x18004bfc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004bfc7  jb      loc_18004C157
0x18004bfcd  mov     edx, 0A3h
0x18004bfd2  jmp     loc_18004BCEF
0x18004bfd7  mov     rax, [rsi]
0x18004bfda  lea     rcx, [rbp+57h+var_40]
0x18004bfde  mov     rbx, [rax]
0x18004bfe1  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18004bfe6  lea     r8, [rbp+57h+var_40]
0x18004bfea  mov     rcx, rsi
0x18004bfed  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18004bff4  mov     rax, rbx
0x18004bff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bffc  mov     ebx, eax
0x18004bffe  test    eax, eax
0x18004c000  jns     short loc_18004C019
0x18004c002  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c009  jb      loc_18004C157
0x18004c00f  mov     edx, 0A4h
0x18004c014  jmp     loc_18004BCEF
0x18004c019  mov     rcx, [rbp+57h+var_80]
0x18004c01d  mov     [rbp+57h+var_80], r14
0x18004c021  test    rcx, rcx
0x18004c024  jz      short loc_18004C032
0x18004c026  mov     rax, [rcx]
0x18004c029  mov     rax, [rax+10h]
0x18004c02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c032  lea     rdx, [rbp+57h+var_80]; void **
0x18004c036  call    ?CreateSensorDevice@SensorDevice@@SAJAEBU_GUID@@PEAPEAX@Z; SensorDevice::CreateSensorDevice(_GUID const &,void * *)
0x18004c03b  mov     ebx, eax
0x18004c03d  test    eax, eax
0x18004c03f  jns     short loc_18004C058
0x18004c041  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c048  jb      loc_18004C157
0x18004c04e  mov     edx, 0A5h
0x18004c053  jmp     loc_18004BCEF
0x18004c058  mov     r14, [rbp+57h+var_80]
0x18004c05c  mov     rcx, [rbp+57h+var_68]
0x18004c060  mov     ebx, [r15+0A8h]
0x18004c067  mov     rdi, [rbp+57h+ppMFAttributes]
0x18004c06b  mov     rax, [r14]
0x18004c06e  mov     rsi, [rax+18h]
0x18004c072  mov     rax, [rcx]
0x18004c075  mov     rax, [rax+18h]
0x18004c079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c07e  mov     rdx, [rbp+57h+var_40]
0x18004c082  lea     rcx, [rbp+57h+var_70]
0x18004c086  mov     [rsp+0C0h+var_90], rcx
0x18004c08b  mov     r8, rax
0x18004c08e  mov     [rsp+0C0h+var_98], r12
0x18004c093  mov     rcx, r14
0x18004c096  mov     r9, rdi
0x18004c099  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18004c09d  mov     rax, rsi
0x18004c0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0a5  mov     ebx, eax
0x18004c0a7  test    eax, eax
0x18004c0a9  jns     short loc_18004C0C2
0x18004c0ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c0b2  jb      loc_18004C157
0x18004c0b8  mov     edx, 0A6h
0x18004c0bd  jmp     loc_18004BCEF
0x18004c0c2  mov     rcx, [rbp+57h+var_60]
0x18004c0c6  mov     rbx, [rbp+57h+var_80]
0x18004c0ca  mov     rax, [rbx]
0x18004c0cd  mov     [rbp+57h+var_60], 0
0x18004c0d5  mov     rdi, [rax]
0x18004c0d8  test    rcx, rcx
0x18004c0db  jz      short loc_18004C0E9
0x18004c0dd  mov     rdx, [rcx]
0x18004c0e0  mov     rax, [rdx+10h]
0x18004c0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0e9  lea     r8, [rbp+57h+var_60]
0x18004c0ed  mov     rcx, rbx
0x18004c0f0  lea     rdx, _GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4
0x18004c0f7  mov     rax, rdi
0x18004c0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0ff  mov     ebx, eax
0x18004c101  test    eax, eax
0x18004c103  jns     short loc_18004C115
0x18004c105  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c10c  jb      short loc_18004C157
0x18004c10e  mov     edx, 0A7h
0x18004c113  jmp     short loc_18004C139
0x18004c115  mov     rdx, [rbp+57h+var_60]
0x18004c119  lea     rcx, [r15+60h]
0x18004c11d  call    ?Add@?$CTUnkArray@UIMFSensorDevice@@@@QEAAHPEAUIMFSensorDevice@@@Z; CTUnkArray<IMFSensorDevice>::Add(IMFSensorDevice *)
0x18004c122  test    eax, eax
0x18004c124  jnz     short loc_18004C167
0x18004c126  mov     ebx, 8007000Eh
0x18004c12b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c132  jb      short loc_18004C157
  ... truncated ...
```

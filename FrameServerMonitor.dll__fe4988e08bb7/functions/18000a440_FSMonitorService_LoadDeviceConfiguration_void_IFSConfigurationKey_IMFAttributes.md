# FSMonitorService::LoadDeviceConfiguration(void *,IFSConfigurationKey *,IMFAttributes * *)

- ea: `0x18000a440`
- end: `0x18000a62b`
- name: `?LoadDeviceConfiguration@FSMonitorService@@UEAAJPEAXPEAUIFSConfigurationKey@@PEAPEAUIMFAttributes@@@Z`
- size: `491`
- prototype: `int(FSMonitorService *__hidden this, void *, struct IFSConfigurationKey *, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005f98`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x18000a440`
- `0x180038564`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a4e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a4e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a543`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a543`
- `MFPlat!MFCreateAttributes` at `0x18000a5a6`
- `MFPlat!MFCreateAttributes` at `0x18000a5a6`

## pseudocode

```c
__int64 __fastcall FSMonitorService::LoadDeviceConfiguration(
        FSMonitorService *this,
        void *a2,
        struct IFSConfigurationKey *a3,
        struct IMFAttributes **a4)
{
  HRESULT v7; // ebx
  int v8; // r8d
  __int64 v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // r14
  int v11; // ecx
  UINT32 v12; // ebx
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-10h] BYREF
  struct IFSConfiguration *v15; // [rsp+38h] [rbp-8h] BYREF
  UINT32 cInitialSize; // [rsp+70h] [rbp+30h] BYREF

  cInitialSize = 0;
  v15 = 0;
  ppMFAttributes = 0;
  if ( a3 )
  {
    if ( !a4 )
    {
      v7 = -2147467261;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_25;
      v9 = 90;
      goto LABEL_4;
    }
    v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
    *a4 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v15);
    v7 = FSLoadDeviceConfiguration(a3, &v15);
    if ( v7 == -1072875819 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 8u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v11);
      LeaveCriticalSection(v10);
    }
    else
    {
      LeaveCriticalSection(v10);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v9 = 92;
        goto LABEL_4;
      }
      v7 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, UINT32 *))(*(_QWORD *)v15 + 240LL))(v15, &cInitialSize);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v9 = 93;
        goto LABEL_4;
      }
      v12 = cInitialSize;
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v7 = MFCreateAttributes(&ppMFAttributes, v12);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_25;
        v9 = 94;
        goto LABEL_4;
      }
      v7 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, IMFAttributes *))(*(_QWORD *)v15 + 256LL))(
             v15,
             ppMFAttributes);
      if ( v7 >= 0 )
      {
        *a4 = ppMFAttributes;
        ppMFAttributes = 0;
        goto LABEL_25;
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 95;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v7 = -2147024809;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = (unsigned int)(v8 + 89);
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v7);
    }
  }
LABEL_25:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a440  mov     [rsp-18h+arg_0], rbx
0x18000a445  mov     [rsp-18h+arg_8], rsi
0x18000a44a  push    rbp
0x18000a44b  push    rdi
0x18000a44c  push    r14
0x18000a44e  mov     rbp, rsp
0x18000a451  sub     rsp, 40h
0x18000a455  mov     [rbp+cInitialSize], 0
0x18000a45c  mov     rsi, r9
0x18000a45f  mov     [rbp+var_8], 0
0x18000a467  mov     rbx, r8
0x18000a46a  mov     [rbp+ppMFAttributes], 0
0x18000a472  mov     rdi, rcx
0x18000a475  test    r8, r8
0x18000a478  jnz     short loc_18000A4B3
0x18000a47a  mov     ebx, 80070057h
0x18000a47f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a484  cmp     al, 1
0x18000a486  jb      loc_18000A604
0x18000a48c  lea     edx, [r8+59h]
0x18000a490  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a497  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a49e  mov     r9, rdi
0x18000a4a1  mov     [rsp+40h+var_20], ebx
0x18000a4a5  mov     rcx, [rcx+10h]
0x18000a4a9  call    WPP_SF_qD
0x18000a4ae  jmp     loc_18000A604
0x18000a4b3  test    rsi, rsi
0x18000a4b6  jnz     short loc_18000A4CF
0x18000a4b8  mov     ebx, 80004003h
0x18000a4bd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a4c2  cmp     al, 1
0x18000a4c4  jb      loc_18000A604
0x18000a4ca  lea     edx, [rsi+5Ah]
0x18000a4cd  jmp     short loc_18000A490
0x18000a4cf  lea     r14, [rcx+0E8h]
0x18000a4d6  mov     qword ptr [r9], 0
0x18000a4dd  mov     rcx, r14; lpCriticalSection
0x18000a4e0  call    cs:__imp_EnterCriticalSection
0x18000a4e6  lea     rcx, [rbp+var_8]
0x18000a4ea  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18000a4ef  lea     rdx, [rbp+var_8]; struct IFSConfiguration **
0x18000a4f3  mov     rcx, rbx; struct IFSConfigurationKey *
0x18000a4f6  call    FSLoadDeviceConfiguration
0x18000a4fb  mov     ecx, 0C00D36D5h
0x18000a500  mov     ebx, eax
0x18000a502  cmp     eax, ecx
0x18000a504  jnz     short loc_18000A540
0x18000a506  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a50b  cmp     al, 8
0x18000a50d  jb      short loc_18000A532
0x18000a50f  mov     [rsp+40h+var_20], ecx
0x18000a513  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000a51a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a521  mov     edx, 5Bh ; '['
0x18000a526  mov     r9, rdi
0x18000a529  mov     rcx, [rcx+10h]
0x18000a52d  call    WPP_SF_qD
0x18000a532  mov     rcx, r14; lpCriticalSection
0x18000a535  call    cs:__imp_LeaveCriticalSection
0x18000a53b  jmp     loc_18000A604
0x18000a540  mov     rcx, r14; lpCriticalSection
0x18000a543  call    cs:__imp_LeaveCriticalSection
0x18000a549  test    ebx, ebx
0x18000a54b  jns     short loc_18000A564
0x18000a54d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a552  cmp     al, 1
0x18000a554  jb      loc_18000A604
0x18000a55a  mov     edx, 5Ch ; '\'
0x18000a55f  jmp     loc_18000A490
0x18000a564  mov     rcx, [rbp+var_8]
0x18000a568  lea     rdx, [rbp+cInitialSize]
0x18000a56c  mov     rax, [rcx]
0x18000a56f  mov     rax, [rax+0F0h]
0x18000a576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57b  mov     ebx, eax
0x18000a57d  test    eax, eax
0x18000a57f  jns     short loc_18000A594
0x18000a581  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a586  cmp     al, 1
0x18000a588  jb      short loc_18000A604
0x18000a58a  mov     edx, 5Dh ; ']'
0x18000a58f  jmp     loc_18000A490
0x18000a594  mov     ebx, [rbp+cInitialSize]
0x18000a597  lea     rcx, [rbp+ppMFAttributes]
0x18000a59b  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18000a5a0  mov     edx, ebx; cInitialSize
0x18000a5a2  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18000a5a6  call    cs:__imp_MFCreateAttributes
0x18000a5ac  mov     ebx, eax
0x18000a5ae  test    eax, eax
0x18000a5b0  jns     short loc_18000A5C5
0x18000a5b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a5b7  cmp     al, 1
0x18000a5b9  jb      short loc_18000A604
0x18000a5bb  mov     edx, 5Eh ; '^'
0x18000a5c0  jmp     loc_18000A490
0x18000a5c5  mov     rcx, [rbp+var_8]
0x18000a5c9  mov     rdx, [rbp+ppMFAttributes]
0x18000a5cd  mov     rax, [rcx]
0x18000a5d0  mov     rax, [rax+100h]
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  mov     ebx, eax
0x18000a5de  test    eax, eax
0x18000a5e0  jns     short loc_18000A5F5
0x18000a5e2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a5e7  cmp     al, 1
0x18000a5e9  jb      short loc_18000A604
0x18000a5eb  mov     edx, 5Fh ; '_'
0x18000a5f0  jmp     loc_18000A490
0x18000a5f5  mov     rax, [rbp+ppMFAttributes]
0x18000a5f9  mov     [rsi], rax
0x18000a5fc  mov     [rbp+ppMFAttributes], 0
0x18000a604  lea     rcx, [rbp+ppMFAttributes]
0x18000a608  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000a60d  lea     rcx, [rbp+var_8]
0x18000a611  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000a616  mov     rsi, [rsp+40h+arg_8]
0x18000a61b  mov     eax, ebx
0x18000a61d  mov     rbx, [rsp+40h+arg_0]
0x18000a622  add     rsp, 40h
0x18000a626  pop     r14
0x18000a628  pop     rdi
0x18000a629  pop     rbp
0x18000a62a  retn
```

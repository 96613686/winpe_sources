# RelativePanelWatcher::OnChanged(Windows::Internal::System::IRelativePanelDirectionTracker *,IInspectable *)

- ea: `0x180061f20`
- end: `0x18006212b`
- name: `?OnChanged@RelativePanelWatcher@@AEAAJPEAUIRelativePanelDirectionTracker@System@Internal@Windows@@PEAUIInspectable@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(RelativePanelWatcher *__hidden this, struct Windows::Internal::System::IRelativePanelDirectionTracker *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000aa08`
- `0x1800359cc`
- `0x180060d50`
- `0x180061f20`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061fcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062009`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061fcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062009`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061f5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061f5f`
- `MFPlat!MFInvokeCallback` at `0x1800620c1`
- `MFPlat!MFInvokeCallback` at `0x1800620c1`
- `MFPlat!MFCreateAsyncResult` at `0x18006205b`
- `MFPlat!MFCreateAsyncResult` at `0x18006205b`

## pseudocode

```c
__int64 __fastcall RelativePanelWatcher::OnChanged(
        RelativePanelWatcher *this,
        struct Windows::Internal::System::IRelativePanelDirectionTracker *a2,
        struct IInspectable *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  char v5; // al
  unsigned int v6; // esi
  IMFAsyncCallback *v7; // rbx
  IMFAsyncResult *v8; // rcx
  HRESULT v9; // eax
  int v10; // eax
  IUnknown *punkState; // [rsp+30h] [rbp-10h] BYREF
  IMFAsyncCallback *pCallback; // [rsp+38h] [rbp-8h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+60h] [rbp+20h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  pCallback = 0;
  punkState = 0;
  ppAsyncResult = 0;
  v15 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = byte_18008D62D;
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 60, &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids, this);
    v5 = byte_18008D62D;
  }
  if ( *((_BYTE *)this + 64) )
  {
    if ( (unsigned __int8)v5 >= 0x10u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        61,
        &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
        this,
        -1072873851);
    LeaveCriticalSection(v3);
    v6 = -1072873851;
  }
  else
  {
    v6 = 0;
    wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(
      (__int64 *)&pCallback,
      *((_QWORD *)this + 13));
    wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(
      (__int64 *)&punkState,
      *((_QWORD *)this + 14));
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(
      &v15,
      (__int64 *)this + 12);
    LeaveCriticalSection(v3);
    if ( v15 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v15 + 48LL))(v15, (char *)this + 88);
    v7 = pCallback;
    if ( pCallback )
    {
      v8 = ppAsyncResult;
      ppAsyncResult = 0;
      if ( v8 )
        ((void (__fastcall *)(IMFAsyncResult *))v8->lpVtbl->Release)(v8);
      v9 = MFCreateAsyncResult(0, v7, punkState, &ppAsyncResult);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
                ppAsyncResult,
                (unsigned int)v9);
        v6 = v10;
        if ( v10 >= 0 )
        {
          MFInvokeCallback(ppAsyncResult);
        }
        else if ( g_wppLevels )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids,
            this,
            v10);
        }
      }
      else if ( g_wppLevels )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids, this, v9);
      }
    }
    if ( (unsigned __int8)byte_18008D62D >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 64, &WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids, this, v6);
  }
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v15);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppAsyncResult);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&punkState);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&pCallback);
  return v6;
}

```

## disassembly

```asm
0x180061f20  mov     [rsp-18h+arg_8], rbx
0x180061f25  mov     [rsp-18h+arg_10], rsi
0x180061f2a  push    rbp
0x180061f2b  push    rdi
0x180061f2c  push    r15
0x180061f2e  mov     rbp, rsp
0x180061f31  sub     rsp, 40h
0x180061f35  lea     rbx, [rcx+18h]
0x180061f39  mov     [rbp+pCallback], 0
0x180061f41  mov     rdi, rcx
0x180061f44  mov     [rbp+punkState], 0
0x180061f4c  mov     rcx, rbx; lpCriticalSection
0x180061f4f  mov     [rbp+ppAsyncResult], 0
0x180061f57  mov     [rbp+arg_18], 0
0x180061f5f  call    cs:__imp_EnterCriticalSection
0x180061f65  mov     al, cs:byte_18008D62D
0x180061f6b  lea     r15, WPP_7b95265dd4ff3af0a35317d95cbfbcb7_Traceguids
0x180061f72  cmp     al, 10h
0x180061f74  jb      short loc_180061F9A
0x180061f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180061f7d  mov     edx, 3Ch ; '<'
0x180061f82  mov     r9, rdi
0x180061f85  mov     r8, r15
0x180061f88  mov     rcx, [rcx+0D8h]
0x180061f8f  call    WPP_SF_q
0x180061f94  mov     al, cs:byte_18008D62D
0x180061f9a  cmp     byte ptr [rdi+40h], 0
0x180061f9e  jz      short loc_180061FDD
0x180061fa0  cmp     al, 10h
0x180061fa2  jb      short loc_180061FCA
0x180061fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180061fab  mov     edx, 3Dh ; '='
0x180061fb0  mov     r9, rdi
0x180061fb3  mov     [rsp+40h+var_20], 0C00D3E85h
0x180061fbb  mov     r8, r15
0x180061fbe  mov     rcx, [rcx+0D8h]
0x180061fc5  call    WPP_SF_qD
0x180061fca  mov     rcx, rbx; lpCriticalSection
0x180061fcd  call    cs:__imp_LeaveCriticalSection
0x180061fd3  mov     esi, 0C00D3E85h
0x180061fd8  jmp     loc_1800620F2
0x180061fdd  mov     rdx, [rdi+68h]
0x180061fe1  lea     rcx, [rbp+pCallback]
0x180061fe5  xor     esi, esi
0x180061fe7  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x180061fec  mov     rdx, [rdi+70h]
0x180061ff0  lea     rcx, [rbp+punkState]
0x180061ff4  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x180061ff9  lea     rdx, [rdi+60h]
0x180061ffd  lea     rcx, [rbp+arg_18]
0x180062001  call    ??4?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy> const &)
0x180062006  mov     rcx, rbx; lpCriticalSection
0x180062009  call    cs:__imp_LeaveCriticalSection
0x18006200f  mov     rcx, [rbp+arg_18]
0x180062013  test    rcx, rcx
0x180062016  jz      short loc_180062028
0x180062018  mov     rax, [rcx]
0x18006201b  lea     rdx, [rdi+58h]
0x18006201f  mov     rax, [rax+30h]
0x180062023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062028  mov     rbx, [rbp+pCallback]
0x18006202c  test    rbx, rbx
0x18006202f  jz      loc_1800620C7
0x180062035  mov     rcx, [rbp+ppAsyncResult]
0x180062039  mov     [rbp+ppAsyncResult], rsi
0x18006203d  test    rcx, rcx
0x180062040  jz      short loc_18006204E
0x180062042  mov     rax, [rcx]
0x180062045  mov     rax, [rax+10h]
0x180062049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006204e  mov     r8, [rbp+punkState]; punkState
0x180062052  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x180062056  mov     rdx, rbx; pCallback
0x180062059  xor     ecx, ecx; punkObject
0x18006205b  call    cs:__imp_MFCreateAsyncResult
0x180062061  mov     esi, eax
0x180062063  test    eax, eax
0x180062065  jns     short loc_180062091
0x180062067  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006206e  jb      short loc_1800620C7
0x180062070  mov     edx, 3Eh ; '>'
0x180062075  mov     [rsp+40h+var_20], eax
0x180062079  mov     rcx, cs:WPP_GLOBAL_Control
0x180062080  mov     r9, rdi
0x180062083  mov     r8, r15
0x180062086  mov     rcx, [rcx+10h]
0x18006208a  call    WPP_SF_qD
0x18006208f  jmp     short loc_1800620C7
0x180062091  mov     rcx, [rbp+ppAsyncResult]
0x180062095  mov     edx, esi
0x180062097  mov     rax, [rcx]
0x18006209a  mov     rax, [rax+28h]
0x18006209e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620a3  mov     esi, eax
0x1800620a5  test    eax, eax
0x1800620a7  jns     short loc_1800620BD
0x1800620a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800620b0  jb      short loc_1800620C7
0x1800620b2  mov     edx, 3Fh ; '?'
0x1800620b7  mov     [rsp+40h+var_20], eax
0x1800620bb  jmp     short loc_180062079
0x1800620bd  mov     rcx, [rbp+ppAsyncResult]; pAsyncResult
0x1800620c1  call    cs:__imp_MFInvokeCallback
0x1800620c7  cmp     cs:byte_18008D62D, 10h
0x1800620ce  jb      short loc_1800620F2
0x1800620d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800620d7  mov     edx, 40h ; '@'
0x1800620dc  mov     r9, rdi
0x1800620df  mov     [rsp+40h+var_20], esi
0x1800620e3  mov     r8, r15
0x1800620e6  mov     rcx, [rcx+0D8h]
0x1800620ed  call    WPP_SF_qD
0x1800620f2  lea     rcx, [rbp+arg_18]
0x1800620f6  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800620fb  lea     rcx, [rbp+ppAsyncResult]
0x1800620ff  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180062104  lea     rcx, [rbp+punkState]
0x180062108  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18006210d  lea     rcx, [rbp+pCallback]
0x180062111  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180062116  mov     rbx, [rsp+40h+arg_8]
0x18006211b  mov     eax, esi
0x18006211d  mov     rsi, [rsp+40h+arg_10]
0x180062122  add     rsp, 40h
0x180062126  pop     r15
0x180062128  pop     rdi
0x180062129  pop     rbp
0x18006212a  retn
```

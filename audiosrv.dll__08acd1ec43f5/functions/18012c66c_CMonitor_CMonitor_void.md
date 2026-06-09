# CMonitor::~CMonitor(void)

- ea: `0x18012c66c`
- end: `0x18012c7c7`
- name: `??1CMonitor@@MEAA@XZ`
- size: `347`
- prototype: `void __fastcall(CMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180129010`

## callees

- `0x18000ae1c`
- `0x1800b38d4`
- `0x1800e7b40`
- `0x180128ba8`
- `0x180128bd0`
- `0x18012c66c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012c7af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012c7af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012c710`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012c710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c79d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c758`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c79d`

## pseudocode

```c
void __fastcall CMonitor::~CMonitor(CMonitor *this)
{
  _QWORD *v2; // rcx

  *(_QWORD *)this = &CMonitor::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 25) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800000) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_qq(v2[2], 24, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
    CloseThreadpoolWork(*((PTP_WORK *)this + 25));
    *((_QWORD *)this + 25) = 0;
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 184);
  ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>((char *)this + 176);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 168);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 160);
  CoTaskMemFree(*((LPVOID *)this + 19));
  *((_QWORD *)this + 19) = 0;
  ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>((char *)this + 144);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 120);
  CoTaskMemFree(*((LPVOID *)this + 14));
  *((_QWORD *)this + 14) = 0;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>((char *)this + 104);
  CoTaskMemFree(*((LPVOID *)this + 12));
  *((_QWORD *)this + 12) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>(this);
}

```

## disassembly

```asm
0x18012c66c  mov     [rsp+arg_0], rbx
0x18012c671  push    rbp
0x18012c672  sub     rsp, 30h
0x18012c676  lea     rax, ??_7CMonitor@@6BIInspectable@@@; const CMonitor::`vftable'{for `IInspectable'}
0x18012c67d  mov     rbx, rcx
0x18012c680  mov     [rcx], rax
0x18012c683  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x18012c68a  mov     [rcx+8], rax
0x18012c68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18012c695  lea     rbp, WPP_GLOBAL_Control
0x18012c69c  cmp     rcx, rbp
0x18012c69f  jz      short loc_18012C6CF
0x18012c6a1  test    dword ptr [rcx+1Ch], 800000h
0x18012c6a8  jz      short loc_18012C6CF
0x18012c6aa  cmp     byte ptr [rcx+19h], 4
0x18012c6ae  jb      short loc_18012C6CF
0x18012c6b0  mov     rcx, [rcx+10h]
0x18012c6b4  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18012c6bb  mov     edx, 17h
0x18012c6c0  mov     r9, rbx
0x18012c6c3  call    WPP_SF_q
0x18012c6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18012c6cf  mov     r9, [rbx+0C8h]
0x18012c6d6  test    r9, r9
0x18012c6d9  jz      short loc_18012C721
0x18012c6db  cmp     rcx, rbp
0x18012c6de  jz      short loc_18012C709
0x18012c6e0  test    dword ptr [rcx+1Ch], 800000h
0x18012c6e7  jz      short loc_18012C709
0x18012c6e9  cmp     byte ptr [rcx+19h], 4
0x18012c6ed  jb      short loc_18012C709
0x18012c6ef  mov     rcx, [rcx+10h]
0x18012c6f3  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18012c6fa  mov     edx, 18h
0x18012c6ff  mov     [rsp+38h+var_18], rbx
0x18012c704  call    WPP_SF_qq
0x18012c709  mov     rcx, [rbx+0C8h]; pwk
0x18012c710  call    cs:__imp_CloseThreadpoolWork
0x18012c716  mov     qword ptr [rbx+0C8h], 0
0x18012c721  lea     rcx, [rbx+0B8h]
0x18012c728  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c72d  lea     rcx, [rbx+0B0h]
0x18012c734  call    ??1?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>(void)
0x18012c739  lea     rcx, [rbx+0A8h]
0x18012c740  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c745  lea     rcx, [rbx+0A0h]
0x18012c74c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c751  mov     rcx, [rbx+98h]; pv
0x18012c758  call    cs:__imp_CoTaskMemFree
0x18012c75e  lea     rcx, [rbx+90h]
0x18012c765  mov     qword ptr [rbx+98h], 0
0x18012c770  call    ??1?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>(void)
0x18012c775  lea     rcx, [rbx+78h]
0x18012c779  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c77e  mov     rcx, [rbx+70h]; pv
0x18012c782  call    cs:__imp_CoTaskMemFree
0x18012c788  lea     rcx, [rbx+68h]
0x18012c78c  mov     qword ptr [rbx+70h], 0
0x18012c794  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c799  mov     rcx, [rbx+60h]; pv
0x18012c79d  call    cs:__imp_CoTaskMemFree
0x18012c7a3  lea     rcx, [rbx+20h]; lpCriticalSection
0x18012c7a7  mov     qword ptr [rbx+60h], 0
0x18012c7af  call    cs:__imp_DeleteCriticalSection
0x18012c7b5  mov     rcx, rbx
0x18012c7b8  mov     rbx, [rsp+38h+arg_0]
0x18012c7bd  add     rsp, 30h
0x18012c7c1  pop     rbp
0x18012c7c2  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>(void)
```

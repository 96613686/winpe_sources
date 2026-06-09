# CMonitor::~CMonitor(void)

- ea: `0x18012c41c`
- end: `0x18012c577`
- name: `??1CMonitor@@MEAA@XZ`
- size: `347`
- prototype: `void __fastcall(CMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180128dc0`

## callees

- `0x18000accc`
- `0x1800b55c4`
- `0x1800e82c0`
- `0x180128958`
- `0x180128980`
- `0x18012c41c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012c55f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18012c55f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012c4c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18012c4c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012c54d`

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
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids, this);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 25) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800000) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_qq(v2[2], 24, &WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids);
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
0x18012c41c  mov     [rsp+arg_0], rbx
0x18012c421  push    rbp
0x18012c422  sub     rsp, 30h
0x18012c426  lea     rax, ??_7CMonitor@@6BIInspectable@@@; const CMonitor::`vftable'{for `IInspectable'}
0x18012c42d  mov     rbx, rcx
0x18012c430  mov     [rcx], rax
0x18012c433  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x18012c43a  mov     [rcx+8], rax
0x18012c43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18012c445  lea     rbp, WPP_GLOBAL_Control
0x18012c44c  cmp     rcx, rbp
0x18012c44f  jz      short loc_18012C47F
0x18012c451  test    dword ptr [rcx+1Ch], 800000h
0x18012c458  jz      short loc_18012C47F
0x18012c45a  cmp     byte ptr [rcx+19h], 4
0x18012c45e  jb      short loc_18012C47F
0x18012c460  mov     rcx, [rcx+10h]
0x18012c464  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18012c46b  mov     edx, 17h
0x18012c470  mov     r9, rbx
0x18012c473  call    WPP_SF_q
0x18012c478  mov     rcx, cs:WPP_GLOBAL_Control
0x18012c47f  mov     r9, [rbx+0C8h]
0x18012c486  test    r9, r9
0x18012c489  jz      short loc_18012C4D1
0x18012c48b  cmp     rcx, rbp
0x18012c48e  jz      short loc_18012C4B9
0x18012c490  test    dword ptr [rcx+1Ch], 800000h
0x18012c497  jz      short loc_18012C4B9
0x18012c499  cmp     byte ptr [rcx+19h], 4
0x18012c49d  jb      short loc_18012C4B9
0x18012c49f  mov     rcx, [rcx+10h]
0x18012c4a3  lea     r8, WPP_755387bd23fa3df5d8dd9259737f5712_Traceguids
0x18012c4aa  mov     edx, 18h
0x18012c4af  mov     [rsp+38h+var_18], rbx
0x18012c4b4  call    WPP_SF_qq
0x18012c4b9  mov     rcx, [rbx+0C8h]; pwk
0x18012c4c0  call    cs:__imp_CloseThreadpoolWork
0x18012c4c6  mov     qword ptr [rbx+0C8h], 0
0x18012c4d1  lea     rcx, [rbx+0B8h]
0x18012c4d8  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c4dd  lea     rcx, [rbx+0B0h]
0x18012c4e4  call    ??1?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>(void)
0x18012c4e9  lea     rcx, [rbx+0A8h]
0x18012c4f0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c4f5  lea     rcx, [rbx+0A0h]
0x18012c4fc  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c501  mov     rcx, [rbx+98h]; pv
0x18012c508  call    cs:__imp_CoTaskMemFree
0x18012c50e  lea     rcx, [rbx+90h]
0x18012c515  mov     qword ptr [rbx+98h], 0
0x18012c520  call    ??1?$CComPtrBase@VCMonitorNotification@CMonitor@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMonitor::CMonitorNotification>::~CComPtrBase<CMonitor::CMonitorNotification>(void)
0x18012c525  lea     rcx, [rbx+78h]
0x18012c529  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c52e  mov     rcx, [rbx+70h]; pv
0x18012c532  call    cs:__imp_CoTaskMemFree
0x18012c538  lea     rcx, [rbx+68h]
0x18012c53c  mov     qword ptr [rbx+70h], 0
0x18012c544  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18012c549  mov     rcx, [rbx+60h]; pv
0x18012c54d  call    cs:__imp_CoTaskMemFree
0x18012c553  lea     rcx, [rbx+20h]; lpCriticalSection
0x18012c557  mov     qword ptr [rbx+60h], 0
0x18012c55f  call    cs:__imp_DeleteCriticalSection
0x18012c565  mov     rcx, rbx
0x18012c568  mov     rbx, [rsp+38h+arg_0]
0x18012c56d  add     rsp, 30h
0x18012c571  pop     rbp
0x18012c572  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IInspectable>(void)
```

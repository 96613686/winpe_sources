# DllGetClassObject

- ea: `0x1800023d0`
- end: `0x18000260e`
- name: `DllGetClassObject`
- size: `574`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016d4`
- `0x1800023d0`
- `0x1800026ac`
- `0x18000c010`

## string_xrefs

- `0x1800024b0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccomimplementationsdesktop.cpp`
- `0x1800025f0`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccomimplementationsdesktop.cpp`
- `0x1800024e9`: `CPR(pCommandHandlerFactory)`
- `0x18000249c`: `CHR(pCommandHandlerFactory->QueryInterface(riid, ppv))`
- `0x1800025b5`: `CPR(pTaskStateHandlerFactory)`
- `0x18000258a`: `CHR(pTaskStateHandlerFactory->QueryInterface(riid, ppv))`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // ebx
  _QWORD *v6; // rax
  int v7; // edx
  int v8; // ecx
  _QWORD *v9; // rdi
  int v10; // edx
  int v11; // ecx
  _QWORD *v12; // rax
  int v13; // edx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx

  if ( !ppv )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)rclsid,
        (_DWORD)riid,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomimp"
                      "lementationsdesktop.cpp",
        123,
        (__int64)"CPR(ppv)");
    return v5;
  }
  *ppv = 0;
  if ( *(_OWORD *)&CLSID_CommandHandler == *(_OWORD *)rclsid )
  {
    v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v6;
    if ( v6 )
    {
      *v6 = &DdcCommandHandlerDesktopFactory::`vftable';
      v6[2] = &g_cInstances;
      *((_DWORD *)v6 + 2) = 1;
      _InterlockedIncrement(&g_cInstances);
      v5 = (*(__int64 (__fastcall **)(_QWORD *, const IID *const, LPVOID *))*v6)(v6, riid, ppv);
      if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomi"
                        "mplementationsdesktop.cpp",
          130,
          (__int64)"CHR(pCommandHandlerFactory->QueryInterface(riid, ppv))");
LABEL_9:
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      return v5;
    }
    v5 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomimp"
                      "lementationsdesktop.cpp",
        129,
        (__int64)"CPR(pCommandHandlerFactory)");
  }
  else if ( *(_QWORD *)&CLSID_TaskStateHandler.Data1 == *(_QWORD *)&rclsid->Data1
         && *(_QWORD *)CLSID_TaskStateHandler.Data4 == *(_QWORD *)rclsid->Data4 )
  {
    v12 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v12;
    if ( v12 )
    {
      *v12 = &DdcTaskStateHandlerDesktopFactory::`vftable';
      v12[2] = &g_cInstances;
      *((_DWORD *)v12 + 2) = 1;
      _InterlockedIncrement(&g_cInstances);
      v5 = (*(__int64 (__fastcall **)(_QWORD *, const IID *const, LPVOID *))*v12)(v12, riid, ppv);
      if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v16,
          v15,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomi"
                        "mplementationsdesktop.cpp",
          136,
          (__int64)"CHR(pTaskStateHandlerFactory->QueryInterface(riid, ppv))");
      goto LABEL_9;
    }
    v5 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomimp"
                      "lementationsdesktop.cpp",
        135,
        (__int64)"CPR(pTaskStateHandlerFactory)");
  }
  else
  {
    v5 = -2147221231;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)rclsid,
        (_DWORD)riid,
        -2147221231,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomimp"
                      "lementationsdesktop.cpp",
        140,
        (__int64)"CHR(((HRESULT)0x80040111L))");
  }
  return v5;
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  mov     [rsp+arg_8], rsi
0x1800023da  push    rdi
0x1800023db  sub     rsp, 30h
0x1800023df  mov     rbx, r8
0x1800023e2  mov     rsi, rdx
0x1800023e5  test    r8, r8
0x1800023e8  jnz     short loc_180002415
0x1800023ea  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800023f1  mov     ebx, 80070057h
0x1800023f6  jz      loc_1800025FC
0x1800023fc  lea     rax, aCprPpv; "CPR(ppv)"
0x180002403  mov     [rsp+38h+var_10], rax
0x180002408  mov     [rsp+38h+var_18], 7Bh ; '{'
0x180002410  jmp     loc_1800025ED
0x180002415  mov     qword ptr [r8], 0
0x18000241c  mov     rax, qword ptr cs:CLSID_CommandHandler.Data1
0x180002423  cmp     rax, [rcx]
0x180002426  jnz     loc_180002502
0x18000242c  mov     rax, qword ptr cs:CLSID_CommandHandler.Data4
0x180002433  cmp     rax, [rcx+8]
0x180002437  jnz     loc_180002502
0x18000243d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002444  mov     ecx, 18h; unsigned __int64
0x180002449  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000244e  mov     rdi, rax
0x180002451  test    rax, rax
0x180002454  jz      short loc_1800024D3
0x180002456  lea     rax, ??_7DdcCommandHandlerDesktopFactory@@6B@; const DdcCommandHandlerDesktopFactory::`vftable'
0x18000245d  mov     [rdi], rax
0x180002460  lea     rax, ?g_cInstances@@3JC; long volatile g_cInstances
0x180002467  mov     [rdi+10h], rax
0x18000246b  mov     dword ptr [rdi+8], 1
0x180002472  lock inc cs:?g_cInstances@@3JC; long volatile g_cInstances
0x180002479  mov     rax, [rdi]
0x18000247c  mov     r8, rbx
0x18000247f  mov     rdx, rsi
0x180002482  mov     rcx, rdi
0x180002485  mov     rax, [rax]
0x180002488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248d  mov     ebx, eax
0x18000248f  test    eax, eax
0x180002491  jns     short loc_1800024BF
0x180002493  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000249a  jz      short loc_1800024BF
0x18000249c  lea     rax, aChrPcommandhan_0; "CHR(pCommandHandlerFactory->QueryInterf"...
0x1800024a3  mov     [rsp+38h+var_10], rax
0x1800024a8  mov     [rsp+38h+var_18], 82h
0x1800024b0  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800024b7  mov     r8d, ebx
0x1800024ba  call    McTemplateU0dsqs_EventWriteTransfer
0x1800024bf  mov     rax, [rdi]
0x1800024c2  mov     rcx, rdi
0x1800024c5  mov     rax, [rax+10h]
0x1800024c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ce  jmp     loc_1800025FC
0x1800024d3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800024da  mov     r8d, 8007000Eh
0x1800024e0  mov     ebx, r8d
0x1800024e3  jz      loc_1800025FC
0x1800024e9  lea     rax, aCprPcommandhan; "CPR(pCommandHandlerFactory)"
0x1800024f0  mov     [rsp+38h+var_10], rax
0x1800024f5  mov     [rsp+38h+var_18], 81h
0x1800024fd  jmp     loc_1800025F0
0x180002502  mov     rax, qword ptr cs:CLSID_TaskStateHandler.Data1
0x180002509  cmp     rax, [rcx]
0x18000250c  jnz     loc_1800025CB
0x180002512  mov     rax, qword ptr cs:CLSID_TaskStateHandler.Data4
0x180002519  cmp     rax, [rcx+8]
0x18000251d  jnz     loc_1800025CB
0x180002523  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000252a  mov     ecx, 18h; unsigned __int64
0x18000252f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002534  mov     rdi, rax
0x180002537  test    rax, rax
0x18000253a  jz      short loc_1800025A3
0x18000253c  lea     rax, ??_7DdcTaskStateHandlerDesktopFactory@@6B@; const DdcTaskStateHandlerDesktopFactory::`vftable'
0x180002543  mov     [rdi], rax
0x180002546  lea     rax, ?g_cInstances@@3JC; long volatile g_cInstances
0x18000254d  mov     [rdi+10h], rax
0x180002551  mov     dword ptr [rdi+8], 1
0x180002558  lock inc cs:?g_cInstances@@3JC; long volatile g_cInstances
0x18000255f  mov     rax, [rdi]
0x180002562  mov     r8, rbx
0x180002565  mov     rdx, rsi
0x180002568  mov     rcx, rdi
0x18000256b  mov     rax, [rax]
0x18000256e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002573  mov     ebx, eax
0x180002575  test    eax, eax
0x180002577  jns     loc_1800024BF
0x18000257d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002584  jz      loc_1800024BF
0x18000258a  lea     rax, aChrPtaskstateh; "CHR(pTaskStateHandlerFactory->QueryInte"...
0x180002591  mov     [rsp+38h+var_10], rax
0x180002596  mov     [rsp+38h+var_18], 88h
0x18000259e  jmp     loc_1800024B0
0x1800025a3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800025aa  mov     r8d, 8007000Eh
0x1800025b0  mov     ebx, r8d
0x1800025b3  jz      short loc_1800025FC
0x1800025b5  lea     rax, aCprPtaskstateh; "CPR(pTaskStateHandlerFactory)"
0x1800025bc  mov     [rsp+38h+var_10], rax
0x1800025c1  mov     [rsp+38h+var_18], 87h
0x1800025c9  jmp     short loc_1800025F0
0x1800025cb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800025d2  mov     ebx, 80040111h
0x1800025d7  jz      short loc_1800025FC
0x1800025d9  lea     rax, aChrHresult0x80; "CHR(((HRESULT)0x80040111L))"
0x1800025e0  mov     [rsp+38h+var_10], rax
0x1800025e5  mov     [rsp+38h+var_18], 8Ch
0x1800025ed  mov     r8d, ebx
0x1800025f0  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800025f7  call    McTemplateU0dsqs_EventWriteTransfer
0x1800025fc  mov     rsi, [rsp+38h+arg_8]
0x180002601  mov     eax, ebx
0x180002603  mov     rbx, [rsp+38h+arg_0]
0x180002608  add     rsp, 30h
0x18000260c  pop     rdi
0x18000260d  retn
```

# DllGetClassObject

- ea: `0x18000e090`
- end: `0x18000e1a6`
- name: `DllGetClassObject`
- size: `278`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000137c`
- `0x18000dc10`
- `0x18000e090`
- `0x18000f010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000e185`
- `RPCRT4!NdrDllGetClassObject` at `0x18000e185`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rsi
  HRESULT result; // eax
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx
  __int64 v12; // rcx

  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_DrvRecoveryOnReboot )
  {
    if ( !ppv )
      return -2147024809;
    *ppv = 0;
    if ( *(_OWORD *)&CLSID_DrvRecoveryOnReboot != *(_OWORD *)rclsid )
      return -2147221231;
    v7 = operator new(0x10u);
    v8 = v7;
    if ( !v7 )
      return -2147024882;
    *(_QWORD *)v7 = &CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vftable';
    v7[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v6 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v6;
  }
  else
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
    if ( result )
      return ATL::CAtlDllModuleT<CDsmApiModule>::DllGetClassObject(v12, rclsid, riid, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x18000e090  push    rbx
0x18000e092  push    rbp
0x18000e093  push    rsi
0x18000e094  push    rdi
0x18000e095  sub     rsp, 38h
0x18000e099  mov     rax, [rcx]
0x18000e09c  mov     rdi, r8
0x18000e09f  cmp     rax, qword ptr cs:CLSID_DrvRecoveryOnReboot.Data1
0x18000e0a6  mov     rbp, rdx
0x18000e0a9  mov     rbx, rcx
0x18000e0ac  jnz     loc_18000E150
0x18000e0b2  mov     rax, [rcx+8]
0x18000e0b6  cmp     rax, qword ptr cs:CLSID_DrvRecoveryOnReboot.Data4
0x18000e0bd  jnz     loc_18000E150
0x18000e0c3  test    r8, r8
0x18000e0c6  jnz     short loc_18000E0CF
0x18000e0c8  mov     ebx, 80070057h
0x18000e0cd  jmp     short loc_18000E14C
0x18000e0cf  mov     qword ptr [r8], 0
0x18000e0d6  mov     rax, qword ptr cs:CLSID_DrvRecoveryOnReboot.Data1
0x18000e0dd  cmp     rax, [rcx]
0x18000e0e0  jnz     short loc_18000E147
0x18000e0e2  mov     rax, qword ptr cs:CLSID_DrvRecoveryOnReboot.Data4
0x18000e0e9  cmp     rax, [rcx+8]
0x18000e0ed  jnz     short loc_18000E147
0x18000e0ef  mov     ecx, 10h; Size
0x18000e0f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e0f9  mov     rsi, rax
0x18000e0fc  test    rax, rax
0x18000e0ff  jz      short loc_18000E140
0x18000e101  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vftable'
0x18000e108  mov     [rsi], rax
0x18000e10b  mov     dword ptr [rsi+8], 1
0x18000e112  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000e119  mov     rax, [rsi]
0x18000e11c  mov     r8, rdi
0x18000e11f  mov     rdx, rbp
0x18000e122  mov     rcx, rsi
0x18000e125  mov     rax, [rax]
0x18000e128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e12d  mov     ebx, eax
0x18000e12f  mov     rcx, rsi
0x18000e132  mov     rax, [rsi]
0x18000e135  mov     rax, [rax+10h]
0x18000e139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e13e  jmp     short loc_18000E14C
0x18000e140  mov     ebx, 8007000Eh
0x18000e145  jmp     short loc_18000E14C
0x18000e147  mov     ebx, 80040111h
0x18000e14c  mov     eax, ebx
0x18000e14e  jmp     short loc_18000E19D
0x18000e150  mov     rax, cs:aProxyFileList
0x18000e157  mov     rcx, [rax+8]
0x18000e15b  mov     rax, [rcx]
0x18000e15e  test    rax, rax
0x18000e161  jz      short loc_18000E168
0x18000e163  mov     rcx, [rax]
0x18000e166  jmp     short loc_18000E16A
0x18000e168  xor     ecx, ecx
0x18000e16a  lea     rax, gPFactory
0x18000e171  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000e176  lea     r9, aProxyFileList; pProxyFileList
0x18000e17d  mov     [rsp+58h+pclsid], rcx; pclsid
0x18000e182  mov     rcx, rbx; rclsid
0x18000e185  call    cs:__imp_NdrDllGetClassObject
0x18000e18b  test    eax, eax
0x18000e18d  jz      short loc_18000E19D
0x18000e18f  mov     r9, rdi
0x18000e192  mov     r8, rbp
0x18000e195  mov     rdx, rbx
0x18000e198  call    ?DllGetClassObject@?$CAtlDllModuleT@VCDsmApiModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CDsmApiModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x18000e19d  add     rsp, 38h
0x18000e1a1  pop     rdi
0x18000e1a2  pop     rsi
0x18000e1a3  pop     rbp
0x18000e1a4  pop     rbx
0x18000e1a5  retn
```

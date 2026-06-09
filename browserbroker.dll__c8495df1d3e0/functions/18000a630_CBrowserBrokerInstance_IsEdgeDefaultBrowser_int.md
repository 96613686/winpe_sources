# CBrowserBrokerInstance::IsEdgeDefaultBrowser(int *)

- ea: `0x18000a630`
- end: `0x18000a708`
- name: `?IsEdgeDefaultBrowser@CBrowserBrokerInstance@@UEAAJPEAH@Z`
- size: `216`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006c90`
- `0x180006cc4`
- `0x18000a630`
- `0x18000e428`
- `0x18002d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a685`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a685`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBrowserBrokerInstance::IsEdgeDefaultBrowser(CBrowserBrokerInstance *this, int *a2)
{
  int PIC; // ebx
  void *v5; // [rsp+50h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(v5) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&v5);
  if ( PIC >= 0 )
  {
    ppv = 0;
    PIC = CoCreateInstance(
            &CLSID_ApplicationAssociationRegistration,
            0,
            3u,
            &GUID_4e530b0a_e611_4c77_a3ac_9031d022281b,
            &ppv);
    if ( PIC >= 0 )
    {
      v5 = 0;
      PIC = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, L"http", 1);
      if ( PIC >= 0 )
        *a2 = _o__wcsicmp(v5, L"AppXq0fevzme2pys62n3e0fbqa7peapykr8v") == 0;
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v5);
    }
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppv);
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000a630  mov     [rsp+arg_0], rbx
0x18000a635  push    rdi
0x18000a636  sub     rsp, 30h
0x18000a63a  mov     rdi, rdx
0x18000a63d  mov     dword ptr [rsp+38h+arg_10], 0
0x18000a645  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x18000a64a  mov     ecx, 1; unsigned int
0x18000a64f  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000a654  mov     ebx, eax
0x18000a656  test    eax, eax
0x18000a658  js      loc_18000A6FB
0x18000a65e  mov     [rsp+38h+arg_18], 0
0x18000a667  lea     rax, [rsp+38h+arg_18]
0x18000a66c  mov     [rsp+38h+ppv], rax; ppv
0x18000a671  lea     r9, _GUID_4e530b0a_e611_4c77_a3ac_9031d022281b; riid
0x18000a678  xor     edx, edx; pUnkOuter
0x18000a67a  lea     r8d, [rdx+3]; dwClsContext
0x18000a67e  lea     rcx, CLSID_ApplicationAssociationRegistration; rclsid
0x18000a685  call    cs:__imp_CoCreateInstance
0x18000a68b  mov     ebx, eax
0x18000a68d  test    eax, eax
0x18000a68f  js      short loc_18000A6F1
0x18000a691  mov     [rsp+38h+arg_10], 0
0x18000a69a  mov     rcx, [rsp+38h+arg_18]
0x18000a69f  mov     rax, [rcx]
0x18000a6a2  lea     rdx, [rsp+38h+arg_10]
0x18000a6a7  mov     [rsp+38h+ppv], rdx
0x18000a6ac  mov     r9d, 1
0x18000a6b2  mov     r8d, r9d
0x18000a6b5  lea     rdx, aHttp; "http"
0x18000a6bc  mov     rax, [rax+18h]
0x18000a6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c5  mov     ebx, eax
0x18000a6c7  test    eax, eax
0x18000a6c9  js      short loc_18000A6E6
0x18000a6cb  lea     rdx, aAppxq0fevzme2p; "AppXq0fevzme2pys62n3e0fbqa7peapykr8v"
0x18000a6d2  mov     rcx, [rsp+38h+arg_10]
0x18000a6d7  call    cs:__imp__o__wcsicmp
0x18000a6dd  xor     ecx, ecx
0x18000a6df  test    eax, eax
0x18000a6e1  setz    cl
0x18000a6e4  mov     [rdi], ecx
0x18000a6e6  lea     rcx, [rsp+38h+arg_10]
0x18000a6eb  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000a6f0  nop
0x18000a6f1  lea     rcx, [rsp+38h+arg_18]
0x18000a6f6  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x18000a6fb  mov     eax, ebx
0x18000a6fd  mov     rbx, [rsp+38h+arg_0]
0x18000a702  add     rsp, 30h
0x18000a706  pop     rdi
0x18000a707  retn
```

# DdcTaskSchedulerWrapper::Initialize(void)

- ea: `0x1800128fc`
- end: `0x180012a57`
- name: `?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005b34`
- `0x1800063f4`
- `0x180006da4`
- `0x18000f23c`
- `0x1800101f0`
- `0x1800107e0`
- `0x180010dd4`
- `0x18001122c`
- `0x1800118fc`
- `0x180024d9c`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x1800128fc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001292d`
- `OLEAUT32!__imp_VariantInit` at `0x18001292d`
- `OLEAUT32!__imp_VariantClear` at `0x180012a30`
- `OLEAUT32!__imp_VariantClear` at `0x180012a30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012962`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012962`

## string_xrefs

- `0x18001298f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18001297b`: `CHR(CoCreateInstance(CLSID_TaskScheduler, 0, CLSCTX_INPROC_SERVER, IID_ITaskService, (PVOID*)&pTaskService))`
- `0x180012a04`: `CHR(pTaskService->Connect(vtEmpty, vtEmpty, vtEmpty, vtEmpty))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcTaskSchedulerWrapper::Initialize(DdcTaskSchedulerWrapper *this)
{
  HRESULT v2; // ebx
  int v3; // edx
  int v4; // ecx
  int v5; // edx
  int v6; // ecx
  LPVOID v7; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG v10; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v11; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v12; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v13; // [rsp+B0h] [rbp+37h] BYREF
  LPVOID ppv; // [rsp+E0h] [rbp+67h] BYREF

  v2 = 0;
  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !*(_QWORD *)this )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
    if ( v2 >= 0 )
    {
      v10 = pvarg;
      v11 = pvarg;
      v12 = pvarg;
      v13 = pvarg;
      v2 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
             ppv,
             &v13,
             &v12,
             &v11,
             &v10);
      if ( v2 >= 0 )
      {
        v7 = ppv;
        ppv = 0;
        *(_QWORD *)this = v7;
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          v2,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          56,
          "CHR(pTaskService->Connect(vtEmpty, vtEmpty, vtEmpty, vtEmpty))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v2,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        55,
        "CHR(CoCreateInstance(CLSID_TaskScheduler, 0, CLSCTX_INPROC_SERVER, IID_ITaskService, (PVOID*)&pTaskService))");
    }
  }
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800128fc  mov     [rsp-8+arg_8], rbx
0x180012901  mov     [rsp-8+arg_10], rdi
0x180012906  push    rbp
0x180012907  lea     rbp, [rsp-57h]
0x18001290c  sub     rsp, 0D0h
0x180012913  mov     rdi, rcx
0x180012916  xor     ebx, ebx
0x180012918  mov     [rbp+57h+arg_0], rbx
0x18001291c  xorps   xmm0, xmm0
0x18001291f  xor     eax, eax
0x180012921  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180012925  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180012929  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001292d  call    cs:__imp_VariantInit
0x180012933  cmp     [rdi], rbx
0x180012936  jnz     loc_180012A2C
0x18001293c  lea     rcx, [rbp+57h+arg_0]
0x180012940  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012945  lea     rax, [rbp+57h+arg_0]
0x180012949  mov     [rsp+0D0h+ppv], rax; ppv
0x18001294e  lea     r9, IID_ITaskService; riid
0x180012955  xor     edx, edx; pUnkOuter
0x180012957  lea     r8d, [rbx+1]; dwClsContext
0x18001295b  lea     rcx, CLSID_TaskScheduler; rclsid
0x180012962  call    cs:__imp_CoCreateInstance
0x180012968  mov     ebx, eax
0x18001296a  test    eax, eax
0x18001296c  jns     short loc_1800129A3
0x18001296e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012975  jz      loc_180012A2C
0x18001297b  lea     rax, aChrCocreateins_0; "CHR(CoCreateInstance(CLSID_TaskSchedule"...
0x180012982  mov     [rsp+0D0h+var_A8], rax
0x180012987  mov     dword ptr [rsp+0D0h+ppv], 137h
0x18001298f  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012996  mov     r8d, ebx
0x180012999  call    McTemplateU0dsqs_EventWriteTransfer
0x18001299e  jmp     loc_180012A2C
0x1800129a3  mov     rcx, [rbp+57h+arg_0]
0x1800129a7  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x1800129ab  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x1800129b0  movaps  [rbp+57h+var_80], xmm1
0x1800129b4  movsd   [rbp+57h+var_70], xmm0
0x1800129b9  movaps  [rbp+57h+var_60], xmm1
0x1800129bd  movsd   [rbp+57h+var_50], xmm0
0x1800129c2  movaps  [rbp+57h+var_40], xmm1
0x1800129c6  movsd   [rbp+57h+var_30], xmm0
0x1800129cb  movaps  [rbp+57h+var_20], xmm1
0x1800129cf  movsd   [rbp+57h+var_10], xmm0
0x1800129d4  mov     rax, [rcx]
0x1800129d7  lea     rdx, [rbp+57h+var_80]
0x1800129db  mov     [rsp+0D0h+ppv], rdx
0x1800129e0  lea     r9, [rbp+57h+var_60]
0x1800129e4  lea     r8, [rbp+57h+var_40]
0x1800129e8  lea     rdx, [rbp+57h+var_20]
0x1800129ec  mov     rax, [rax+50h]
0x1800129f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129f5  mov     ebx, eax
0x1800129f7  test    eax, eax
0x1800129f9  jns     short loc_180012A1D
0x1800129fb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012a02  jz      short loc_180012A2C
0x180012a04  lea     rax, aChrPtaskservic; "CHR(pTaskService->Connect(vtEmpty, vtEm"...
0x180012a0b  mov     [rsp+0D0h+var_A8], rax
0x180012a10  mov     dword ptr [rsp+0D0h+ppv], 138h
0x180012a18  jmp     loc_18001298F
0x180012a1d  mov     rax, [rbp+57h+arg_0]
0x180012a21  mov     [rbp+57h+arg_0], 0
0x180012a29  mov     [rdi], rax
0x180012a2c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180012a30  call    cs:__imp_VariantClear
0x180012a36  nop
0x180012a37  lea     rcx, [rbp+57h+arg_0]
0x180012a3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012a40  mov     eax, ebx
0x180012a42  lea     r11, [rsp+0D0h+var_s0]
0x180012a4a  mov     rbx, [r11+18h]
0x180012a4e  mov     rdi, [r11+20h]
0x180012a52  mov     rsp, r11
0x180012a55  pop     rbp
0x180012a56  retn
```

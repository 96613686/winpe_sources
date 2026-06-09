# PimIMService::GetPoomApp(void)

- ea: `0x180007050`
- end: `0x180007132`
- name: `?GetPoomApp@PimIMService@@UEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x18000502c`
- `0x180007050`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007070`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007070`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000711a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000711a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800070a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800070a7`

## string_xrefs

- `0x1800070da`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetPoomApp(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct IUnknown **p_OwningThread; // rdi
  HRESULT Instance; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  v1 = this + 8;
  p_OwningThread = (struct IUnknown **)&this[5].OwningThread;
  EnterCriticalSection(this + 8);
  if ( *p_OwningThread )
    goto LABEL_10;
  ppv = 0;
  Instance = CoCreateInstance(&CLSID_Application, 0, 1u, &IID_IPOutlookApp3, (LPVOID *)&ppv);
  v4 = Instance;
  if ( Instance >= 0 )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))ppv->lpVtbl[2].AddRef)(ppv, 0);
    v4 = Instance;
    if ( Instance < 0 )
    {
      v5 = 1213;
      goto LABEL_6;
    }
    if ( *p_OwningThread != ppv )
      ATL::AtlComPtrAssign(p_OwningThread, ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_10:
    v4 = 0;
    goto LABEL_11;
  }
  v5 = 1211;
LABEL_6:
  Log_HREvent(
    (unsigned int)Instance,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    v5);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_11:
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180007050  mov     [rsp+arg_8], rbx
0x180007055  mov     [rsp+arg_10], rsi
0x18000705a  push    rdi
0x18000705b  sub     rsp, 30h
0x18000705f  lea     rsi, [rcx+140h]
0x180007066  lea     rdi, [rcx+0D8h]
0x18000706d  mov     rcx, rsi; lpCriticalSection
0x180007070  call    cs:__imp_EnterCriticalSection
0x180007076  cmp     qword ptr [rdi], 0
0x18000707a  jnz     loc_180007115
0x180007080  xor     edx, edx; pUnkOuter
0x180007082  mov     [rsp+38h+arg_0], 0
0x18000708b  lea     rax, [rsp+38h+arg_0]
0x180007090  lea     r9, IID_IPOutlookApp3; riid
0x180007097  mov     [rsp+38h+ppv], rax; ppv
0x18000709c  lea     rcx, CLSID_Application; rclsid
0x1800070a3  lea     r8d, [rdx+1]; dwClsContext
0x1800070a7  call    cs:__imp_CoCreateInstance
0x1800070ad  mov     ebx, eax
0x1800070af  test    eax, eax
0x1800070b1  jns     short loc_1800070BB
0x1800070b3  mov     r9d, 4BBh
0x1800070b9  jmp     short loc_1800070DA
0x1800070bb  mov     rcx, [rsp+38h+arg_0]
0x1800070c0  xor     edx, edx
0x1800070c2  mov     rax, [rcx]
0x1800070c5  mov     rax, [rax+38h]
0x1800070c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ce  mov     ebx, eax
0x1800070d0  test    eax, eax
0x1800070d2  jns     short loc_1800070F9
0x1800070d4  mov     r9d, 4BDh
0x1800070da  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800070e1  mov     edx, 1
0x1800070e6  mov     ecx, eax
0x1800070e8  call    Log_HREvent
0x1800070ed  lea     rcx, [rsp+38h+arg_0]
0x1800070f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800070f7  jmp     short loc_180007117
0x1800070f9  mov     rdx, [rsp+38h+arg_0]; struct IUnknown *
0x1800070fe  cmp     [rdi], rdx
0x180007101  jz      short loc_18000710B
0x180007103  mov     rcx, rdi; struct IUnknown **
0x180007106  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000710b  lea     rcx, [rsp+38h+arg_0]
0x180007110  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007115  xor     ebx, ebx
0x180007117  mov     rcx, rsi; lpCriticalSection
0x18000711a  call    cs:__imp_LeaveCriticalSection
0x180007120  mov     rsi, [rsp+38h+arg_10]
0x180007125  mov     eax, ebx
0x180007127  mov     rbx, [rsp+38h+arg_8]
0x18000712c  add     rsp, 30h
0x180007130  pop     rdi
0x180007131  retn
```

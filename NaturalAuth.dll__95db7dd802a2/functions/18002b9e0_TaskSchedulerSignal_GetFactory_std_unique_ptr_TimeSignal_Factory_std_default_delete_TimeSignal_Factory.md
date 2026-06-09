# TaskSchedulerSignal::GetFactory(std::unique_ptr<TimeSignal::Factory,std::default_delete<TimeSignal::Factory>> *)

- ea: `0x18002b9e0`
- end: `0x18002bb89`
- name: `?GetFactory@TaskSchedulerSignal@@SAJPEAV?$unique_ptr@VFactory@TimeSignal@@U?$default_delete@VFactory@TimeSignal@@@std@@@std@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024cb4`

## callees

- `0x18000459c`
- `0x18000a7f8`
- `0x180012b0c`
- `0x180014e7c`
- `0x1800288a4`
- `0x18002ae28`
- `0x18002b9e0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ba07`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002ba07`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002ba96`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002ba96`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba59`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba59`

## pseudocode

```c
__int64 __fastcall TaskSchedulerSignal::GetFactory(__int64 a1)
{
  int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  _QWORD *v4; // rsi
  LPVOID v5; // rdi
  __int64 v6; // rcx
  LPVOID ppv; // [rsp+50h] [rbp+20h] BYREF
  LPVOID v9; // [rsp+58h] [rbp+28h] BYREF

  ppv = 0;
  std::unique_ptr<TimeSignal::Factory>::reset(a1, 0);
  v1 = CoInitializeEx(0, 0);
  if ( v1 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v3 = 32;
LABEL_9:
    WPP_SF_d(v2[2], v3, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, (unsigned int)v1);
LABEL_10:
    CoUninitialize();
    goto LABEL_23;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v1 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_10;
    v3 = 33;
    goto LABEL_9;
  }
  v9 = ppv;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
  v1 = DeleteAllTasks((__int64 *)&v9);
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids,
        (unsigned int)v1);
    v1 = 0;
  }
  v4 = operator new(0x10u);
  v5 = ppv;
  v9 = ppv;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
  *v4 = &TaskSchedulerSignalFactory::`vftable';
  v4[1] = v5;
  if ( v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 8LL))(v5);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  v9 = 0;
  std::unique_ptr<TimeSignal::Factory>::reset(v6, v4);
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v9);
LABEL_23:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002b9e0  mov     [rsp-18h+arg_10], rbx
0x18002b9e5  mov     [rsp-18h+arg_0], rcx
0x18002b9ea  push    rbp
0x18002b9eb  push    rsi
0x18002b9ec  push    rdi
0x18002b9ed  mov     rbp, rsp
0x18002b9f0  sub     rsp, 30h
0x18002b9f4  mov     [rbp+arg_0], 0
0x18002b9fc  xor     edx, edx
0x18002b9fe  call    ?reset@?$unique_ptr@VFactory@TimeSignal@@U?$default_delete@VFactory@TimeSignal@@@std@@@std@@QEAAXPEAVFactory@TimeSignal@@@Z; std::unique_ptr<TimeSignal::Factory>::reset(TimeSignal::Factory *)
0x18002ba03  xor     edx, edx; dwCoInit
0x18002ba05  xor     ecx, ecx; pvReserved
0x18002ba07  call    cs:__imp_CoInitializeEx
0x18002ba0d  mov     ebx, eax
0x18002ba0f  test    eax, eax
0x18002ba11  jns     short loc_18002BA33
0x18002ba13  lea     rax, WPP_GLOBAL_Control
0x18002ba1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba21  cmp     rcx, rax
0x18002ba24  jz      short loc_18002BA96
0x18002ba26  test    byte ptr [rcx+1Ch], 1
0x18002ba2a  jz      short loc_18002BA96
0x18002ba2c  mov     edx, 20h ; ' '
0x18002ba31  jmp     short loc_18002BA83
0x18002ba33  lea     rcx, [rbp+arg_0]
0x18002ba37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ba3c  lea     rax, [rbp+arg_0]
0x18002ba40  mov     [rsp+30h+ppv], rax; ppv
0x18002ba45  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002ba4c  xor     edx, edx; pUnkOuter
0x18002ba4e  lea     r8d, [rdx+1]; dwClsContext
0x18002ba52  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002ba59  call    cs:__imp_CoCreateInstance
0x18002ba5f  mov     ebx, eax
0x18002ba61  test    eax, eax
0x18002ba63  jns     short loc_18002BAA1
0x18002ba65  lea     rax, WPP_GLOBAL_Control
0x18002ba6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba73  cmp     rcx, rax
0x18002ba76  jz      short loc_18002BA96
0x18002ba78  test    byte ptr [rcx+1Ch], 1
0x18002ba7c  jz      short loc_18002BA96
0x18002ba7e  mov     edx, 21h ; '!'
0x18002ba83  mov     r9d, ebx
0x18002ba86  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002ba8d  mov     rcx, [rcx+10h]
0x18002ba91  call    WPP_SF_d
0x18002ba96  call    cs:__imp_CoUninitialize
0x18002ba9c  jmp     loc_18002BB71
0x18002baa1  mov     rcx, [rbp+arg_0]
0x18002baa5  mov     [rbp+arg_8], rcx
0x18002baa9  test    rcx, rcx
0x18002baac  jz      short loc_18002BABB
0x18002baae  mov     rax, [rcx]
0x18002bab1  mov     rax, [rax+8]
0x18002bab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baba  nop
0x18002babb  lea     rcx, [rbp+arg_8]
0x18002babf  call    DeleteAllTasks
0x18002bac4  mov     ebx, eax
0x18002bac6  test    eax, eax
0x18002bac8  jns     short loc_18002BAFD
0x18002baca  lea     rax, WPP_GLOBAL_Control
0x18002bad1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bad8  cmp     rcx, rax
0x18002badb  jz      short loc_18002BAFB
0x18002badd  test    byte ptr [rcx+1Ch], 1
0x18002bae1  jz      short loc_18002BAFB
0x18002bae3  mov     edx, 22h ; '"'
0x18002bae8  mov     r9d, ebx
0x18002baeb  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002baf2  mov     rcx, [rcx+10h]
0x18002baf6  call    WPP_SF_d
0x18002bafb  xor     ebx, ebx
0x18002bafd  mov     ecx, 10h; Size
0x18002bb02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bb07  mov     rsi, rax
0x18002bb0a  mov     [rbp+arg_8], rax
0x18002bb0e  mov     rdi, [rbp+arg_0]
0x18002bb12  mov     [rbp+arg_8], rdi
0x18002bb16  test    rdi, rdi
0x18002bb19  jz      short loc_18002BB2B
0x18002bb1b  mov     rcx, [rdi]
0x18002bb1e  mov     rax, [rcx+8]
0x18002bb22  mov     rcx, rdi
0x18002bb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb2a  nop
0x18002bb2b  lea     rax, ??_7TaskSchedulerSignalFactory@@6B@; const TaskSchedulerSignalFactory::`vftable'
0x18002bb32  mov     [rsi], rax
0x18002bb35  mov     [rsi+8], rdi
0x18002bb39  test    rdi, rdi
0x18002bb3c  jz      short loc_18002BB4E
0x18002bb3e  mov     rax, [rdi]
0x18002bb41  mov     rcx, rdi
0x18002bb44  mov     rax, [rax+8]
0x18002bb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb4d  nop
0x18002bb4e  lea     rcx, [rbp+arg_8]
0x18002bb52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bb57  mov     [rbp+arg_8], 0
0x18002bb5f  mov     rdx, rsi
0x18002bb62  call    ?reset@?$unique_ptr@VFactory@TimeSignal@@U?$default_delete@VFactory@TimeSignal@@@std@@@std@@QEAAXPEAVFactory@TimeSignal@@@Z; std::unique_ptr<TimeSignal::Factory>::reset(TimeSignal::Factory *)
0x18002bb67  lea     rcx, [rbp+arg_8]
0x18002bb6b  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18002bb70  nop
0x18002bb71  lea     rcx, [rbp+arg_0]
0x18002bb75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bb7a  mov     eax, ebx
0x18002bb7c  mov     rbx, [rsp+30h+arg_10]
0x18002bb81  add     rsp, 30h
0x18002bb85  pop     rdi
0x18002bb86  pop     rsi
0x18002bb87  pop     rbp
0x18002bb88  retn
```

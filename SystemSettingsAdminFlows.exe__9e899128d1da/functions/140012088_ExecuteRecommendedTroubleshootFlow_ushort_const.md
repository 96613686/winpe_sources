# ExecuteRecommendedTroubleshootFlow(ushort const *)

- ea: `0x140012088`
- end: `0x1400121f8`
- name: `?ExecuteRecommendedTroubleshootFlow@@YAJPEBG@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140012088`
- `0x14001a2a0`
- `0x14001f3d4`
- `0x14007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400120b9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400120b9`
- `ole32!CoCreateInstance` at `0x1400120ee`
- `ole32!CoCreateInstance` at `0x1400120ee`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400120a1`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1400120a1`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012123`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012154`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400121b8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400121e3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012123`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140012154`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400121b8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400121e3`

## string_xrefs

- `0x140012101`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x140012196`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ExecuteRecommendedTroubleshootFlow(const unsigned __int16 *a1, __int64 a2)
{
  unsigned int v3; // edi
  int v4; // ebx
  HRESULT v5; // eax
  unsigned int v6; // esi
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int ppv; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v15; // [rsp+68h] [rbp+28h]
  LPVOID v16; // [rsp+70h] [rbp+30h] BYREF

  v3 = 1;
  v15 = RoInitialize(1, a2);
  v4 = _o__wtoi(a1);
  v16 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v5 = CoCreateInstance(&CLSID_MitigationState, 0, 1u, &GUID_d555b534_8777_464a_8acc_781e36aa123e, &v16);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E3,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    if ( v15 >= 0 )
      RoUninitialize();
    return v6;
  }
  v8 = v4 - 1;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
          if ( v15 >= 0 )
            RoUninitialize();
          return 2147942487LL;
        }
        v3 = 4;
      }
      else
      {
        v3 = 3;
      }
    }
    else
    {
      v3 = 2;
    }
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 48LL))(v16, v3);
  v12 = v11;
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 64LL))(v16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    if ( v15 >= 0 )
      RoUninitialize();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6FA,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    if ( v15 >= 0 )
      RoUninitialize();
    return v12;
  }
}

```

## disassembly

```asm
0x140012088  mov     [rsp-18h+arg_0], rbx
0x14001208d  push    rbp
0x14001208e  push    rsi
0x14001208f  push    rdi
0x140012090  mov     rbp, rsp
0x140012093  sub     rsp, 40h
0x140012097  mov     rbx, rcx
0x14001209a  mov     edi, 1
0x14001209f  mov     ecx, edi
0x1400120a1  call    cs:__imp_RoInitialize
0x1400120a7  mov     [rbp+arg_8], eax
0x1400120aa  lea     rax, [rbp+arg_8]
0x1400120ae  mov     [rbp+var_10], rax
0x1400120b2  mov     [rbp+var_8], dil
0x1400120b6  mov     rcx, rbx
0x1400120b9  call    cs:__imp__o__wtoi
0x1400120bf  mov     ebx, eax
0x1400120c1  mov     [rbp+arg_10], 0
0x1400120c9  lea     rcx, [rbp+arg_10]
0x1400120cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400120d2  lea     rax, [rbp+arg_10]
0x1400120d6  mov     qword ptr [rsp+40h+ppv], rax; int
0x1400120db  lea     r9, _GUID_d555b534_8777_464a_8acc_781e36aa123e; riid
0x1400120e2  mov     r8d, edi; dwClsContext
0x1400120e5  xor     edx, edx; pUnkOuter
0x1400120e7  lea     rcx, CLSID_MitigationState; rclsid
0x1400120ee  call    cs:__imp_CoCreateInstance
0x1400120f4  mov     esi, eax
0x1400120f6  test    eax, eax
0x1400120f8  jns     short loc_140012130
0x1400120fa  mov     rcx, [rbp+18h]; this
0x1400120fe  mov     r9d, eax; char *
0x140012101  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140012108  mov     edx, 6E3h; void *
0x14001210d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012112  nop
0x140012113  lea     rcx, [rbp+arg_10]
0x140012117  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001211c  nop
0x14001211d  cmp     [rbp+arg_8], 0
0x140012121  jl      short loc_140012129
0x140012123  call    cs:__imp_RoUninitialize
0x140012129  mov     eax, esi
0x14001212b  jmp     loc_1400121EB
0x140012130  sub     ebx, 1
0x140012133  jz      short loc_140012177
0x140012135  sub     ebx, 1
0x140012138  jz      short loc_140012172
0x14001213a  sub     ebx, 1
0x14001213d  jz      short loc_14001216B
0x14001213f  cmp     ebx, 1
0x140012142  jz      short loc_140012164
0x140012144  lea     rcx, [rbp+arg_10]
0x140012148  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001214d  nop
0x14001214e  cmp     [rbp+arg_8], 0
0x140012152  jl      short loc_14001215A
0x140012154  call    cs:__imp_RoUninitialize
0x14001215a  mov     eax, 80070057h
0x14001215f  jmp     loc_1400121EB
0x140012164  mov     edi, 4
0x140012169  jmp     short loc_140012177
0x14001216b  mov     edi, 3
0x140012170  jmp     short loc_140012177
0x140012172  mov     edi, 2
0x140012177  mov     rcx, [rbp+arg_10]
0x14001217b  mov     rax, [rcx]
0x14001217e  mov     edx, edi
0x140012180  mov     rax, [rax+30h]
0x140012184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012189  mov     ebx, eax
0x14001218b  test    eax, eax
0x14001218d  jns     short loc_1400121C2
0x14001218f  mov     rcx, [rbp+18h]; this
0x140012193  mov     r9d, eax; char *
0x140012196  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x14001219d  mov     edx, 6FAh; void *
0x1400121a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400121a7  nop
0x1400121a8  lea     rcx, [rbp+arg_10]
0x1400121ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400121b1  nop
0x1400121b2  cmp     [rbp+arg_8], 0
0x1400121b6  jl      short loc_1400121BE
0x1400121b8  call    cs:__imp_RoUninitialize
0x1400121be  mov     eax, ebx
0x1400121c0  jmp     short loc_1400121EB
0x1400121c2  mov     rcx, [rbp+arg_10]
0x1400121c6  mov     rax, [rcx]
0x1400121c9  mov     rax, [rax+40h]
0x1400121cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121d2  nop
0x1400121d3  lea     rcx, [rbp+arg_10]
0x1400121d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400121dc  nop
0x1400121dd  cmp     [rbp+arg_8], 0
0x1400121e1  jl      short loc_1400121E9
0x1400121e3  call    cs:__imp_RoUninitialize
0x1400121e9  xor     eax, eax
0x1400121eb  mov     rbx, [rsp+40h+arg_0]
0x1400121f0  add     rsp, 40h
0x1400121f4  pop     rdi
0x1400121f5  pop     rsi
0x1400121f6  pop     rbp
0x1400121f7  retn
```

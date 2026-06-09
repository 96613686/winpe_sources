# wWinMain

- ea: `0x1400085f4`
- end: `0x1400087d6`
- name: `wWinMain`
- size: `482`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001380`

## callees

- `0x140004764`
- `0x1400085f4`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000860a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000860a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000861d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000861d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008659`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400087c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008659`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400087c3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x140008705`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x140008705`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400086ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400087b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400086ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400087b5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000862c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000862c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000868d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000868d`

## string_xrefs

- `0x140008603`: `AppxDeploymentClient.dll`
- `0x140008613`: `AppInstallerUpdateAllTask`
- `0x140008640`: `onecore\admin\appmodel\appinstallerbackgroundupdate\main.cpp`
- `0x1400086a1`: `onecore\admin\appmodel\appinstallerbackgroundupdate\main.cpp`
- `0x140008719`: `onecore\admin\appmodel\appinstallerbackgroundupdate\main.cpp`
- `0x140008770`: `onecore\admin\appmodel\appinstallerbackgroundupdate\main.cpp`
- `0x140008752`: `AppInstallerBackgroundUpdate`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  HMODULE Library; // rbx
  void (*ProcAddress)(void); // rax
  HRESULT v6; // eax
  int v7; // edi
  HRESULT Instance; // eax
  HRESULT v10; // eax
  int v11; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  int ppvb; // [rsp+20h] [rbp-38h]
  IUnknown *pProxy; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Library = LoadLibraryExW(L"AppxDeploymentClient.dll", 0, 0);
  ProcAddress = (void (*)(void))GetProcAddress(Library, "AppInstallerUpdateAllTask");
  ProcAddress();
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecore\\admin\\appmodel\\appinstallerbackgroundupdate\\main.cpp",
      (const char *)(unsigned int)v6,
      ppv);
LABEL_3:
    if ( Library )
      FreeLibrary(Library);
    return v7;
  }
  pProxy = 0;
  Instance = CoCreateInstance(
               &GUID_9c695035_48d2_4229_8b73_4c70e756e519,
               0,
               4u,
               &GUID_c53f3549_0dbf_429a_8297_c812ba00742d,
               (LPVOID *)&pProxy);
  v7 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\admin\\appmodel\\appinstallerbackgroundupdate\\main.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
LABEL_9:
    CoUninitialize();
    goto LABEL_3;
  }
  v10 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\admin\\appmodel\\appinstallerbackgroundupdate\\main.cpp",
      (const char *)(unsigned int)v10,
      ppvb);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_9;
  }
  v11 = ((__int64 (__fastcall *)(IUnknown *, const wchar_t *, __int64))pProxy->lpVtbl[1].Release)(
          pProxy,
          L"AppInstallerBackgroundUpdate",
          1);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\admin\\appmodel\\appinstallerbackgroundupdate\\main.cpp",
      (const char *)(unsigned int)v11,
      ppvb);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_9;
  }
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  CoUninitialize();
  if ( Library )
    FreeLibrary(Library);
  return 0;
}

```

## disassembly

```asm
0x1400085f4  mov     [rsp+arg_0], rbx
0x1400085f9  push    rdi
0x1400085fa  sub     rsp, 50h
0x1400085fe  xor     r8d, r8d; dwFlags
0x140008601  xor     edx, edx; hFile
0x140008603  lea     rcx, LibFileName; "AppxDeploymentClient.dll"
0x14000860a  call    cs:__imp_LoadLibraryExW
0x140008610  mov     rbx, rax
0x140008613  lea     rdx, aAppinstallerup; "AppInstallerUpdateAllTask"
0x14000861a  mov     rcx, rax; hModule
0x14000861d  call    cs:__imp_GetProcAddress
0x140008623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008628  xor     edx, edx; dwCoInit
0x14000862a  xor     ecx, ecx; pvReserved
0x14000862c  call    cs:__imp_CoInitializeEx
0x140008632  mov     edi, eax
0x140008634  test    eax, eax
0x140008636  jns     short loc_140008666
0x140008638  mov     rcx, [rsp+58h]; this
0x14000863d  mov     r9d, eax; char *
0x140008640  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appinstallerb"...
0x140008647  mov     edx, 13h; void *
0x14000864c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008651  test    rbx, rbx
0x140008654  jz      short loc_14000865F
0x140008656  mov     rcx, rbx; hLibModule
0x140008659  call    cs:__imp_FreeLibrary
0x14000865f  mov     eax, edi
0x140008661  jmp     loc_1400087CB
0x140008666  mov     [rsp+58h+pProxy], 0
0x14000866f  lea     rax, [rsp+58h+pProxy]
0x140008674  mov     [rsp+58h+ppv], rax; int
0x140008679  lea     r9, _GUID_c53f3549_0dbf_429a_8297_c812ba00742d; riid
0x140008680  xor     edx, edx; pUnkOuter
0x140008682  lea     r8d, [rdx+4]; dwClsContext
0x140008686  lea     rcx, _GUID_9c695035_48d2_4229_8b73_4c70e756e519; rclsid
0x14000868d  call    cs:__imp_CoCreateInstance
0x140008693  mov     edi, eax
0x140008695  test    eax, eax
0x140008697  jns     short loc_1400086D5
0x140008699  mov     rcx, [rsp+58h]; this
0x14000869e  mov     r9d, eax; char *
0x1400086a1  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appinstallerb"...
0x1400086a8  mov     edx, 1Bh; void *
0x1400086ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400086b2  nop
0x1400086b3  mov     rcx, [rsp+58h+pProxy]
0x1400086b8  test    rcx, rcx
0x1400086bb  jz      short loc_1400086CA
0x1400086bd  mov     rax, [rcx]
0x1400086c0  mov     rax, [rax+10h]
0x1400086c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086c9  nop
0x1400086ca  call    cs:__imp_CoUninitialize
0x1400086d0  jmp     loc_140008651
0x1400086d5  mov     [rsp+58h+dwCapabilities], 0; dwCapabilities
0x1400086dd  mov     [rsp+58h+pAuthInfo], 0; pAuthInfo
0x1400086e6  mov     [rsp+58h+dwImpLevel], 3; dwImpLevel
0x1400086ee  mov     dword ptr [rsp+58h+ppv], 0; int
0x1400086f6  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1400086fa  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1400086fd  mov     r8d, edx; dwAuthzSvc
0x140008700  mov     rcx, [rsp+58h+pProxy]; pProxy
0x140008705  call    cs:__imp_CoSetProxyBlanket
0x14000870b  mov     edi, eax
0x14000870d  test    eax, eax
0x14000870f  jns     short loc_140008744
0x140008711  mov     rcx, [rsp+58h]; this
0x140008716  mov     r9d, eax; char *
0x140008719  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appinstallerb"...
0x140008720  mov     edx, 25h ; '%'; void *
0x140008725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000872a  nop
0x14000872b  mov     rcx, [rsp+58h+pProxy]
0x140008730  test    rcx, rcx
0x140008733  jz      short loc_140008742
0x140008735  mov     rax, [rcx]
0x140008738  mov     rax, [rax+10h]
0x14000873c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008741  nop
0x140008742  jmp     short loc_1400086CA
0x140008744  mov     rcx, [rsp+58h+pProxy]
0x140008749  mov     rax, [rcx]
0x14000874c  mov     r8d, 1
0x140008752  lea     rdx, aAppinstallerba; "AppInstallerBackgroundUpdate"
0x140008759  mov     rax, [rax+28h]
0x14000875d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008762  mov     edi, eax
0x140008764  test    eax, eax
0x140008766  jns     short loc_14000879E
0x140008768  mov     rcx, [rsp+58h]; this
0x14000876d  mov     r9d, eax; char *
0x140008770  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appinstallerb"...
0x140008777  mov     edx, 27h ; '''; void *
0x14000877c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008781  nop
0x140008782  mov     rcx, [rsp+58h+pProxy]
0x140008787  test    rcx, rcx
0x14000878a  jz      short loc_140008799
0x14000878c  mov     rax, [rcx]
0x14000878f  mov     rax, [rax+10h]
0x140008793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008798  nop
0x140008799  jmp     loc_1400086CA
0x14000879e  mov     rcx, [rsp+58h+pProxy]
0x1400087a3  test    rcx, rcx
0x1400087a6  jz      short loc_1400087B5
0x1400087a8  mov     rax, [rcx]
0x1400087ab  mov     rax, [rax+10h]
0x1400087af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087b4  nop
0x1400087b5  call    cs:__imp_CoUninitialize
0x1400087bb  test    rbx, rbx
0x1400087be  jz      short loc_1400087C9
0x1400087c0  mov     rcx, rbx; hLibModule
0x1400087c3  call    cs:__imp_FreeLibrary
0x1400087c9  xor     eax, eax
0x1400087cb  mov     rbx, [rsp+58h+arg_0]
0x1400087d0  add     rsp, 50h
0x1400087d4  pop     rdi
0x1400087d5  retn
```

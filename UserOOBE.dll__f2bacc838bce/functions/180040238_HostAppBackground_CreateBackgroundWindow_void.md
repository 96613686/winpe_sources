# HostAppBackground::CreateBackgroundWindow(void)

- ea: `0x180040238`
- end: `0x180040391`
- name: `?CreateBackgroundWindow@HostAppBackground@@QEAAJXZ`
- size: `345`
- prototype: `__int64 __fastcall(HostAppBackground *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800400a8`

## callees

- `0x180004200`
- `0x180007114`
- `0x180040238`
- `0x180041008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402b5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800402a7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x1800402a7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180040377`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180040377`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402e4`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402f1`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402fe`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004030b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402e4`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402f1`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800402fe`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004030b`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18004034e`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateWindowInBand` at `0x18004034e`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180040285`
- `ext-ms-win-gdi-dc-l1-2-0!GetStockObject` at `0x180040285`

## pseudocode

```c
__int64 __fastcall HostAppBackground::CreateBackgroundWindow(HostAppBackground *this)
{
  const char *v2; // r9
  __int64 v3; // rdx
  int SystemMetrics; // esi
  int v6; // edi
  int v7; // ebx
  int v8; // eax
  __int64 WindowInBand; // rax
  HWND v10; // rbx
  WNDCLASSEXW v11; // [rsp+70h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v11.cbSize = 80;
  memset_0(&v11.style, 0, 0x4Cu);
  v11.lpfnWndProc = (WNDPROC)HostAppBackground::s_WndProc;
  v11.hInstance = &_ImageBase;
  v11.hbrBackground = (HBRUSH)GetStockObject(4);
  v11.lpszClassName = L"UserOOBEWindowClass";
  if ( !RegisterClassExW(&v11) && GetLastError() != 1410 )
  {
    v3 = 38;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
             v2);
  }
  SystemMetrics = GetSystemMetrics(79);
  v6 = GetSystemMetrics(78);
  v7 = GetSystemMetrics(77);
  v8 = GetSystemMetrics(76);
  WindowInBand = CreateWindowInBand(
                   0x10000,
                   L"UserOOBEWindowClass",
                   0,
                   2281701376LL,
                   v8,
                   v7,
                   v6,
                   SystemMetrics,
                   0,
                   0,
                   &_ImageBase,
                   0,
                   6);
  v10 = (HWND)WindowInBand;
  if ( !WindowInBand )
  {
    v3 = 45;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\hostappenvironment.cpp",
             v2);
  }
  wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&int DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(
    this,
    WindowInBand);
  ShowWindow(v10, 8);
  return 0;
}

```

## disassembly

```asm
0x180040238  push    rbx
0x18004023a  push    rbp
0x18004023b  push    rsi
0x18004023c  push    rdi
0x18004023d  push    r12
0x18004023f  push    r13
0x180040241  push    r14
0x180040243  sub     rsp, 0C0h
0x18004024a  xor     edx, edx; Val
0x18004024c  mov     [rsp+0F8h+var_88.cbSize], 50h ; 'P'
0x180040254  mov     rbp, rcx
0x180040257  lea     rcx, [rsp+0F8h+var_88.style]; void *
0x18004025c  lea     r8d, [rdx+4Ch]; Size
0x180040260  call    memset_0
0x180040265  lea     rax, ?s_WndProc@HostAppBackground@@CA_JPEAUHWND__@@I_K_J@Z; HostAppBackground::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18004026c  mov     ecx, 4; i
0x180040271  lea     r13, __ImageBase
0x180040278  mov     [rsp+0F8h+var_88.lpfnWndProc], rax
0x18004027d  mov     [rsp+0F8h+var_88.hInstance], r13
0x180040285  call    cs:__imp_GetStockObject
0x18004028b  lea     r12, aUseroobewindow; "UserOOBEWindowClass"
0x180040292  mov     [rsp+0F8h+var_88.hbrBackground], rax
0x18004029a  lea     rcx, [rsp+0F8h+var_88]; WNDCLASSEXW *
0x18004029f  mov     [rsp+0F8h+var_88.lpszClassName], r12
0x1800402a7  call    cs:__imp_RegisterClassExW
0x1800402ad  xor     r14d, r14d
0x1800402b0  test    ax, ax
0x1800402b3  jnz     short loc_1800402DF
0x1800402b5  call    cs:__imp_GetLastError
0x1800402bb  cmp     eax, 582h
0x1800402c0  jz      short loc_1800402DF
0x1800402c2  lea     edx, [r14+26h]; void *
0x1800402c6  mov     rcx, [rsp+0F8h]; this
0x1800402ce  lea     r8, aShellLibCloude_1; "shell\\lib\\cloudexperiencehostappmanag"...
0x1800402d5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800402da  jmp     loc_18004037F
0x1800402df  mov     ecx, 4Fh ; 'O'; nIndex
0x1800402e4  call    cs:__imp_GetSystemMetrics
0x1800402ea  mov     ecx, 4Eh ; 'N'; nIndex
0x1800402ef  mov     esi, eax
0x1800402f1  call    cs:__imp_GetSystemMetrics
0x1800402f7  mov     ecx, 4Dh ; 'M'; nIndex
0x1800402fc  mov     edi, eax
0x1800402fe  call    cs:__imp_GetSystemMetrics
0x180040304  mov     ecx, 4Ch ; 'L'; nIndex
0x180040309  mov     ebx, eax
0x18004030b  call    cs:__imp_GetSystemMetrics
0x180040311  mov     [rsp+0F8h+var_98], 6
0x180040319  mov     r9d, 88000000h
0x18004031f  mov     [rsp+0F8h+var_A0], r14
0x180040324  xor     r8d, r8d
0x180040327  mov     [rsp+0F8h+var_A8], r13
0x18004032c  mov     rdx, r12
0x18004032f  mov     [rsp+0F8h+var_B0], r14
0x180040334  mov     ecx, 10000h
0x180040339  mov     [rsp+0F8h+var_B8], r14
0x18004033e  mov     [rsp+0F8h+var_C0], esi
0x180040342  mov     [rsp+0F8h+var_C8], edi
0x180040346  mov     [rsp+0F8h+var_D0], ebx
0x18004034a  mov     [rsp+0F8h+var_D8], eax
0x18004034e  call    cs:__imp_CreateWindowInBand
0x180040354  mov     rbx, rax
0x180040357  test    rax, rax
0x18004035a  jnz     short loc_180040364
0x18004035c  lea     edx, [rax+2Dh]
0x18004035f  jmp     loc_1800402C6
0x180040364  mov     rdx, rbx
0x180040367  mov     rcx, rbp
0x18004036a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHWND__@@P6AHPEAU1@@Z$1?DestroyWindow@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHWND__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::reset(HWND__ *)
0x18004036f  mov     edx, 8; nCmdShow
0x180040374  mov     rcx, rbx; hWnd
0x180040377  call    cs:__imp_ShowWindow
0x18004037d  xor     eax, eax
0x18004037f  add     rsp, 0C0h
0x180040386  pop     r14
0x180040388  pop     r13
0x18004038a  pop     r12
0x18004038c  pop     rdi
0x18004038d  pop     rsi
0x18004038e  pop     rbp
0x18004038f  pop     rbx
0x180040390  retn
```

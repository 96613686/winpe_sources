# RegisterDeploymentProxyStubCLSIDs(HINSTANCE__ *,ulong *,IUnknown * *)

- ea: `0x180001cb8`
- end: `0x180001f7f`
- name: `?RegisterDeploymentProxyStubCLSIDs@@YAJPEAUHINSTANCE__@@PEAKPEAPEAUIUnknown@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006be0`
- `0x180017b84`

## callees

- `0x180001cb8`
- `0x180002214`
- `0x180003180`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001d90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001d90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001ee2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001f4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001ee2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001f4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001db5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001db5`
- `api-ms-win-core-com-l1-1-0!CoRegisterPSClsid` at `0x180001ebc`
- `api-ms-win-core-com-l1-1-0!CoRegisterPSClsid` at `0x180001ebc`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180001e47`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180001e47`

## string_xrefs

- `0x180001cff`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`
- `0x180001dc6`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`
- `0x180001f12`: `C:\__w\1\s\src\Client\UpdateDeployment\Dll\ComReg.cpp`
- `0x180001dab`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RegisterDeploymentProxyStubCLSIDs(HINSTANCE a1, unsigned int *a2, struct IUnknown **a3)
{
  __int64 v5; // rdx
  HMODULE v7; // rbx
  unsigned int LastError; // edi
  __int64 v9; // r9
  __int64 v10; // rdx
  HMODULE Library; // rax
  const char *v12; // r9
  HMODULE v13; // r14
  __int64 v14; // rdx
  FARPROC ProcAddress; // rdi
  HRESULT v16; // eax
  unsigned int i; // esi
  struct IUnknown *v18; // rax
  LPUNKNOWN v19; // rcx
  int lpdwRegister; // [rsp+20h] [rbp-E0h]
  LPUNKNOWN pUnk; // [rsp+38h] [rbp-C8h] BYREF
  IID rclsid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwRegister[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v24[6]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( !a2 )
  {
    v5 = 33;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
      (const char *)0x80004003LL,
      lpdwRegister);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v5 = 34;
    goto LABEL_3;
  }
  v7 = 0;
  pUnk = 0;
  dwRegister[0] = 0;
  rclsid.Data1 = -1864028639;
  *(_DWORD *)&rclsid.Data2 = 1257960700;
  *(_DWORD *)rclsid.Data4 = 1330087574;
  *(_DWORD *)&rclsid.Data4[4] = -2004672912;
  if ( GetModuleFileNameW(g_hInstance, Filename, 0x105u) >= 0x105 )
  {
    LastError = -2147024774;
    v9 = 2147942522LL;
    v10 = 44;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
      (const char *)v9,
      lpdwRegister);
    goto LABEL_26;
  }
  Library = LoadLibraryExW(Filename, 0, 0x800u);
  v13 = Library;
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( ProcAddress )
    {
      v16 = ((__int64 (__fastcall *)(IID *, GUID *, LPUNKNOWN *))ProcAddress)(
              &rclsid,
              &GUID_00000000_0000_0000_c000_000000000046,
              &pUnk);
      LastError = v16;
      if ( v16 >= 0 )
      {
        v16 = CoRegisterClassObject(&rclsid, pUnk, 1u, 1u, dwRegister);
        LastError = v16;
        if ( v16 >= 0 )
        {
          v24[0] = IID_ISusUpdateDeploy;
          v24[1] = IID_IUpdateDeploymentCallback;
          v24[2] = IID_ISusCreateRemoteHandler;
          v24[3] = IID_ISusUpdatePostRebootResult;
          v24[4] = IID_ISusQueryDeploymentCustomReportingData;
          v24[5] = IID_IUpdateDeploymentHandlerInfo;
          for ( i = 0; i < 6; ++i )
          {
            v16 = CoRegisterPSClsid((const IID *const)&v24[i], &rclsid);
            LastError = v16;
            if ( v16 < 0 )
            {
              v10 = 71;
              goto LABEL_24;
            }
          }
          v7 = 0;
          if ( g_xhProxyDll )
            FreeLibrary(g_xhProxyDll);
          g_xhProxyDll = v13;
          v18 = pUnk;
          v19 = 0;
          pUnk = 0;
          *a3 = v18;
          *a2 = dwRegister[0];
          LastError = 0;
          goto LABEL_27;
        }
        v10 = 58;
      }
      else
      {
        v10 = 54;
      }
LABEL_24:
      v9 = (unsigned int)v16;
      goto LABEL_25;
    }
    v14 = 53;
  }
  else
  {
    v14 = 47;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v14,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Dll\\ComReg.cpp",
                v12);
LABEL_26:
  v19 = pUnk;
LABEL_27:
  if ( v19 )
  {
    ((void (__fastcall *)(LPUNKNOWN))v19->lpVtbl->Release)(v19);
    pUnk = 0;
  }
  if ( v7 )
    FreeLibrary(v7);
  return LastError;
}

```

## disassembly

```asm
0x180001cb8  mov     [rsp-8+arg_0], rbx
0x180001cbd  mov     [rsp-8+arg_18], rsi
0x180001cc2  push    rbp
0x180001cc3  push    rdi
0x180001cc4  push    r12
0x180001cc6  push    r14
0x180001cc8  push    r15
0x180001cca  lea     rbp, [rsp-1E0h]
0x180001cd2  sub     rsp, 2E0h
0x180001cd9  mov     rax, cs:__security_cookie
0x180001ce0  xor     rax, rsp
0x180001ce3  mov     [rbp+200h+var_30], rax
0x180001cea  mov     r15, r8
0x180001ced  mov     r12, rdx
0x180001cf0  test    rdx, rdx
0x180001cf3  jnz     short loc_180001D1C
0x180001cf5  lea     edx, [r12+21h]; void *
0x180001cfa  mov     ebx, 80004003h
0x180001cff  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180001d06  mov     r9d, ebx; char *
0x180001d09  mov     rcx, [rbp+208h]; this
0x180001d10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001d15  mov     eax, ebx
0x180001d17  jmp     loc_180001F54
0x180001d1c  test    r15, r15
0x180001d1f  jnz     short loc_180001D27
0x180001d21  lea     edx, [r15+22h]
0x180001d25  jmp     short loc_180001CFA
0x180001d27  xor     ebx, ebx
0x180001d29  mov     [rsp+300h+var_2D0], rbx
0x180001d2e  mov     [rsp+300h+pUnk], rbx
0x180001d33  mov     [rsp+300h+dwRegister], ebx
0x180001d37  mov     [rsp+300h+rclsid.Data1], 90E52E21h
0x180001d3f  mov     dword ptr [rsp+300h+rclsid.Data2], 4AFAF4FCh
0x180001d47  mov     dword ptr [rsp+300h+rclsid.Data4], 4F478696h
0x180001d4f  mov     dword ptr [rsp+300h+rclsid.Data4+4], 88831E70h
0x180001d57  mov     edi, 105h
0x180001d5c  mov     r8d, edi; nSize
0x180001d5f  lea     rdx, [rbp+200h+Filename]; lpFilename
0x180001d63  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180001d6a  call    cs:__imp_GetModuleFileNameW
0x180001d70  cmp     eax, edi
0x180001d72  jb      short loc_180001D84
0x180001d74  mov     edi, 8007007Ah
0x180001d79  mov     r9d, edi
0x180001d7c  lea     edx, [rbx+2Ch]
0x180001d7f  jmp     loc_180001F12
0x180001d84  xor     edx, edx; hFile
0x180001d86  mov     r8d, 800h; dwFlags
0x180001d8c  lea     rcx, [rbp+200h+Filename]; lpLibFileName
0x180001d90  call    cs:__imp_LoadLibraryExW
0x180001d96  mov     r14, rax
0x180001d99  mov     rbx, rax
0x180001d9c  mov     [rsp+300h+var_2D0], rax
0x180001da1  test    rax, rax
0x180001da4  jnz     short loc_180001DAB
0x180001da6  lea     edx, [rax+2Fh]
0x180001da9  jmp     short loc_180001DC6
0x180001dab  lea     rdx, ProcName; "DllGetClassObject"
0x180001db2  mov     rcx, r14; hModule
0x180001db5  call    cs:__imp_GetProcAddress
0x180001dbb  mov     rdi, rax
0x180001dbe  test    rax, rax
0x180001dc1  jnz     short loc_180001DE0
0x180001dc3  lea     edx, [rax+35h]; void *
0x180001dc6  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180001dcd  mov     rcx, [rbp+208h]; this
0x180001dd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180001dd9  mov     edi, eax
0x180001ddb  jmp     loc_180001F25
0x180001de0  mov     rcx, [rsp+300h+pUnk]
0x180001de5  test    rcx, rcx
0x180001de8  jz      short loc_180001DFF
0x180001dea  mov     rax, [rcx]
0x180001ded  mov     rax, [rax+10h]
0x180001df1  call    _guard_dispatch_icall
0x180001df6  mov     [rsp+300h+pUnk], 0
0x180001dff  lea     r8, [rsp+300h+pUnk]
0x180001e04  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180001e0b  lea     rcx, [rsp+300h+rclsid]
0x180001e10  mov     rax, rdi
0x180001e13  call    _guard_dispatch_icall
0x180001e18  mov     edi, eax
0x180001e1a  test    eax, eax
0x180001e1c  jns     short loc_180001E28
0x180001e1e  mov     edx, 36h ; '6'
0x180001e23  jmp     loc_180001F0F
0x180001e28  lea     rax, [rsp+300h+dwRegister]
0x180001e2d  mov     qword ptr [rsp+300h+lpdwRegister], rax; int
0x180001e32  mov     eax, 1
0x180001e37  mov     r9d, eax; flags
0x180001e3a  mov     r8d, eax; dwClsContext
0x180001e3d  mov     rdx, [rsp+300h+pUnk]; pUnk
0x180001e42  lea     rcx, [rsp+300h+rclsid]; rclsid
0x180001e47  call    cs:__imp_CoRegisterClassObject
0x180001e4d  mov     edi, eax
0x180001e4f  test    eax, eax
0x180001e51  jns     short loc_180001E5D
0x180001e53  mov     edx, 3Ah ; ':'
0x180001e58  jmp     loc_180001F0F
0x180001e5d  movups  xmm0, xmmword ptr cs:IID_ISusUpdateDeploy.Data1
0x180001e64  movdqu  [rsp+300h+var_2A0], xmm0
0x180001e6a  movups  xmm1, xmmword ptr cs:IID_IUpdateDeploymentCallback.Data1
0x180001e71  movdqu  [rsp+300h+var_290], xmm1
0x180001e77  movups  xmm0, xmmword ptr cs:IID_ISusCreateRemoteHandler.Data1
0x180001e7e  movdqu  [rbp+200h+var_280], xmm0
0x180001e83  movups  xmm1, xmmword ptr cs:IID_ISusUpdatePostRebootResult.Data1
0x180001e8a  movdqu  [rbp+200h+var_270], xmm1
0x180001e8f  movups  xmm0, xmmword ptr cs:IID_ISusQueryDeploymentCustomReportingData.Data1
0x180001e96  movdqu  [rbp+200h+var_260], xmm0
0x180001e9b  movups  xmm1, xmmword ptr cs:IID_IUpdateDeploymentHandlerInfo.Data1
0x180001ea2  movdqu  [rbp+200h+var_250], xmm1
0x180001ea7  xor     esi, esi
0x180001ea9  mov     eax, esi
0x180001eab  shl     rax, 4
0x180001eaf  lea     rcx, [rsp+300h+var_2A0]
0x180001eb4  add     rcx, rax; riid
0x180001eb7  lea     rdx, [rsp+300h+rclsid]; rclsid
0x180001ebc  call    cs:__imp_CoRegisterPSClsid
0x180001ec2  mov     edi, eax
0x180001ec4  test    eax, eax
0x180001ec6  js      short loc_180001F0A
0x180001ec8  inc     esi
0x180001eca  cmp     esi, 6
0x180001ecd  jb      short loc_180001EA9
0x180001ecf  xor     ebx, ebx
0x180001ed1  mov     [rsp+300h+var_2D0], rbx
0x180001ed6  mov     rcx, cs:?g_xhProxyDll@@3V?$XHandleBase@PEAUHINSTANCE__@@ULibraryPolicy@Policies@WuSmartPtr@@@WuSmartPtr@@A; hLibModule
0x180001edd  test    rcx, rcx
0x180001ee0  jz      short loc_180001EE8
0x180001ee2  call    cs:__imp_FreeLibrary
0x180001ee8  mov     cs:?g_xhProxyDll@@3V?$XHandleBase@PEAUHINSTANCE__@@ULibraryPolicy@Policies@WuSmartPtr@@@WuSmartPtr@@A, r14; WuSmartPtr::XHandleBase<HINSTANCE__ *,WuSmartPtr::Policies::LibraryPolicy> g_xhProxyDll
0x180001eef  mov     rax, [rsp+300h+pUnk]
0x180001ef4  xor     ecx, ecx
0x180001ef6  mov     [rsp+300h+pUnk], rcx
0x180001efb  mov     [r15], rax
0x180001efe  mov     eax, [rsp+300h+dwRegister]
0x180001f02  mov     [r12], eax
0x180001f06  xor     edi, edi
0x180001f08  jmp     short loc_180001F2A
0x180001f0a  mov     edx, 47h ; 'G'; void *
0x180001f0f  mov     r9d, eax; char *
0x180001f12  lea     r8, aCW1SSrcClientU_9; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180001f19  mov     rcx, [rbp+208h]; this
0x180001f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001f25  mov     rcx, [rsp+300h+pUnk]
0x180001f2a  test    rcx, rcx
0x180001f2d  jz      short loc_180001F44
0x180001f2f  mov     rax, [rcx]
0x180001f32  mov     rax, [rax+10h]
0x180001f36  call    _guard_dispatch_icall
0x180001f3b  mov     [rsp+300h+pUnk], 0
0x180001f44  test    rbx, rbx
0x180001f47  jz      short loc_180001F52
0x180001f49  mov     rcx, rbx; hLibModule
0x180001f4c  call    cs:__imp_FreeLibrary
0x180001f52  mov     eax, edi
0x180001f54  mov     rcx, [rbp+200h+var_30]
0x180001f5b  xor     rcx, rsp; StackCookie
0x180001f5e  call    __security_check_cookie
0x180001f63  lea     r11, [rsp+300h+var_20]
0x180001f6b  mov     rbx, [r11+30h]
0x180001f6f  mov     rsi, [r11+48h]
0x180001f73  mov     rsp, r11
0x180001f76  pop     r15
0x180001f78  pop     r14
0x180001f7a  pop     r12
0x180001f7c  pop     rdi
0x180001f7d  pop     rbp
0x180001f7e  retn
```

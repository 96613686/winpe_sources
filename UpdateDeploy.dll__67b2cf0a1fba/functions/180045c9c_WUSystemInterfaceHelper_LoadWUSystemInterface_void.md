# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x180045c9c`
- end: `0x180045ec7`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c0ac`
- `0x180045ed0`
- `0x180045f3c`
- `0x180045fa8`
- `0x180046014`
- `0x1800460a0`
- `0x18004a290`
- `0x18004a514`
- `0x18004f928`

## callees

- `0x180002214`
- `0x180003180`
- `0x180045c9c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180045d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180045d50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180045d6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180045d6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045d26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045d26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045d7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045d7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045ce9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045cf6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045ce9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045cf6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045cd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180045cd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045cff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045cff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045e97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045e97`

## string_xrefs

- `0x180045d1f`: `wusys.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WUSystemInterfaceHelper::LoadWUSystemInterface(WUSystemInterfaceHelper *this)
{
  int LastError; // ebx
  HMODULE Library; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  FARPROC ProcAddress; // rax
  int v7; // edi
  __int64 v8; // rcx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-D0h]
  RTL_SRWLOCK *v15; // [rsp+40h] [rbp-C8h]
  HMODULE phModule; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  AcquireSRWLockShared(&g_LoadWUSysLock);
  LastError = 0;
  if ( g_WUSystemInterface )
  {
    ReleaseSRWLockShared(&g_LoadWUSysLock);
    return 0;
  }
  ReleaseSRWLockShared(&g_LoadWUSysLock);
  AcquireSRWLockExclusive(&g_LoadWUSysLock);
  v15 = &g_LoadWUSysLock;
  if ( g_WUSystemInterface )
    goto LABEL_25;
  Library = LoadLibraryExW(L"wusys.dll", 0, 0x880u);
  g_hWUSysModule = Library;
  if ( Library )
  {
    phModule = 0;
    if ( GetModuleFileNameW(Library, Filename, 0x105u) )
      GetModuleHandleExW(1u, Filename, &phModule);
    ProcAddress = GetProcAddress(g_hWUSysModule, (LPCSTR)0xA425);
    if ( ProcAddress )
    {
      v17 = 0;
      v13 = 0;
      LOBYTE(v14) = 1;
      v7 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(1, &v13);
      if ( (_BYTE)v14 )
      {
        v8 = v17;
        v17 = v13;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( v7 >= 0 )
      {
        v11 = g_WUSystemInterface;
        g_WUSystemInterface = 0;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
                v17,
                &GUID_07186f27_adf4_4d8c_862a_5d403bd2010a,
                &g_WUSystemInterface);
        v7 = v12;
        if ( v12 >= 0 )
        {
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          goto LABEL_25;
        }
        v9 = (unsigned int)v12;
        v10 = 55;
      }
      else
      {
        v9 = (unsigned int)v7;
        v10 = 54;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)v9,
        (int)&v17);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      goto LABEL_26;
    }
    v5 = 51;
  }
  else
  {
    v5 = 40;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v5,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
                v4);
LABEL_25:
  v7 = LastError;
LABEL_26:
  ReleaseSRWLockExclusive(&g_LoadWUSysLock);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180045c9c  mov     rax, rsp
0x180045c9f  mov     [rax+8], rbx
0x180045ca3  mov     [rax+10h], rsi
0x180045ca7  mov     [rax+18h], rdi
0x180045cab  push    rbp
0x180045cac  lea     rbp, [rax-178h]
0x180045cb3  sub     rsp, 270h
0x180045cba  mov     rax, cs:__security_cookie
0x180045cc1  xor     rax, rsp
0x180045cc4  mov     [rbp+170h+var_10], rax
0x180045ccb  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x180045cd2  mov     rcx, rsi; SRWLock
0x180045cd5  call    cs:__imp_AcquireSRWLockShared
0x180045cdb  xor     ebx, ebx
0x180045cdd  mov     rcx, rsi; SRWLock
0x180045ce0  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180045ce7  jz      short loc_180045CF6
0x180045ce9  call    cs:__imp_ReleaseSRWLockShared
0x180045cef  xor     eax, eax
0x180045cf1  jmp     loc_180045E9F
0x180045cf6  call    cs:__imp_ReleaseSRWLockShared
0x180045cfc  mov     rcx, rsi; SRWLock
0x180045cff  call    cs:__imp_AcquireSRWLockExclusive
0x180045d05  mov     [rsp+270h+var_238], rsi
0x180045d0a  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180045d11  jnz     loc_180045E92
0x180045d17  xor     edx, edx; hFile
0x180045d19  mov     r8d, 880h; dwFlags
0x180045d1f  lea     rcx, aWusysDll; "wusys.dll"
0x180045d26  call    cs:__imp_LoadLibraryExW
0x180045d2c  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x180045d33  test    rax, rax
0x180045d36  jnz     short loc_180045D3D
0x180045d38  lea     edx, [rax+28h]
0x180045d3b  jmp     short loc_180045D8B
0x180045d3d  mov     [rsp+270h+phModule], rbx
0x180045d42  mov     r8d, 105h; nSize
0x180045d48  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180045d4d  mov     rcx, rax; hModule
0x180045d50  call    cs:__imp_GetModuleFileNameW
0x180045d56  mov     edi, 1
0x180045d5b  test    eax, eax
0x180045d5d  jz      short loc_180045D71
0x180045d5f  lea     r8, [rsp+270h+phModule]; phModule
0x180045d64  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x180045d69  mov     ecx, edi; dwFlags
0x180045d6b  call    cs:__imp_GetModuleHandleExW
0x180045d71  mov     edx, 0A425h; lpProcName
0x180045d76  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x180045d7d  call    cs:__imp_GetProcAddress
0x180045d83  test    rax, rax
0x180045d86  jnz     short loc_180045DA5
0x180045d88  lea     edx, [rax+33h]; void *
0x180045d8b  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x180045d92  mov     rcx, [rbp+178h]; this
0x180045d99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045d9e  mov     ebx, eax
0x180045da0  jmp     loc_180045E92
0x180045da5  mov     [rsp+270h+var_228], rbx
0x180045daa  lea     rdx, [rsp+270h+var_228]
0x180045daf  mov     qword ptr [rsp+270h+var_250], rdx; int
0x180045db4  mov     [rsp+270h+var_248], rbx
0x180045db9  mov     byte ptr [rsp+270h+var_240], dil
0x180045dbe  lea     rdx, [rsp+270h+var_248]
0x180045dc3  mov     ecx, edi
0x180045dc5  call    _guard_dispatch_icall
0x180045dca  mov     edi, eax
0x180045dcc  cmp     byte ptr [rsp+270h+var_240], bl
0x180045dd0  jz      short loc_180045DF4
0x180045dd2  mov     r8, qword ptr [rsp+270h+var_250]
0x180045dd7  mov     rcx, [r8]
0x180045dda  mov     rdx, [rsp+270h+var_248]
0x180045ddf  mov     [r8], rdx
0x180045de2  test    rcx, rcx
0x180045de5  jz      short loc_180045DF4
0x180045de7  mov     rax, [rcx]
0x180045dea  mov     rax, [rax+10h]
0x180045dee  call    _guard_dispatch_icall
0x180045df3  nop
0x180045df4  test    edi, edi
0x180045df6  jns     short loc_180045E02
0x180045df8  mov     r9d, edi
0x180045dfb  mov     edx, 36h ; '6'
0x180045e00  jmp     short loc_180045E4E
0x180045e02  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180045e09  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180045e10  test    rcx, rcx
0x180045e13  jz      short loc_180045E22
0x180045e15  mov     rax, [rcx]
0x180045e18  mov     rax, [rax+10h]
0x180045e1c  call    _guard_dispatch_icall
0x180045e21  nop
0x180045e22  mov     rcx, [rsp+270h+var_228]
0x180045e27  mov     rax, [rcx]
0x180045e2a  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x180045e31  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x180045e38  mov     rax, [rax]
0x180045e3b  call    _guard_dispatch_icall
0x180045e40  mov     edi, eax
0x180045e42  test    eax, eax
0x180045e44  jns     short loc_180045E7B
0x180045e46  mov     r9d, eax; char *
0x180045e49  mov     edx, 37h ; '7'; void *
0x180045e4e  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x180045e55  mov     rcx, [rbp+178h]; this
0x180045e5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045e61  nop
0x180045e62  mov     rcx, [rsp+270h+var_228]
0x180045e67  test    rcx, rcx
0x180045e6a  jz      short loc_180045E79
0x180045e6c  mov     rax, [rcx]
0x180045e6f  mov     rax, [rax+10h]
0x180045e73  call    _guard_dispatch_icall
0x180045e78  nop
0x180045e79  jmp     short loc_180045E94
0x180045e7b  mov     rcx, [rsp+270h+var_228]
0x180045e80  test    rcx, rcx
0x180045e83  jz      short loc_180045E92
0x180045e85  mov     rax, [rcx]
0x180045e88  mov     rax, [rax+10h]
0x180045e8c  call    _guard_dispatch_icall
0x180045e91  nop
0x180045e92  mov     edi, ebx
0x180045e94  mov     rcx, rsi; SRWLock
0x180045e97  call    cs:__imp_ReleaseSRWLockExclusive
0x180045e9d  mov     eax, edi
0x180045e9f  mov     rcx, [rbp+170h+var_10]
0x180045ea6  xor     rcx, rsp; StackCookie
0x180045ea9  call    __security_check_cookie
0x180045eae  lea     r11, [rsp+270h+var_s0]
0x180045eb6  mov     rbx, [r11+10h]
0x180045eba  mov     rsi, [r11+18h]
0x180045ebe  mov     rdi, [r11+20h]
0x180045ec2  mov     rsp, r11
0x180045ec5  pop     rbp
0x180045ec6  retn
```

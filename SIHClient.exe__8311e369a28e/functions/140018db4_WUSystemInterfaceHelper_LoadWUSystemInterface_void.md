# WUSystemInterfaceHelper::LoadWUSystemInterface(void)

- ea: `0x140018db4`
- end: `0x140018fdf`
- name: `?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ`
- size: `555`
- prototype: `__int64 __fastcall(WUSystemInterfaceHelper *__hidden this)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140018fe8`
- `0x140019054`
- `0x1400190c0`
- `0x14001912c`
- `0x1400191b8`
- `0x140019248`
- `0x14001936c`
- `0x140035ce4`
- `0x1400396ac`
- `0x140044994`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x140018db4`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140018e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140018e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018e95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018e95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140018e68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140018e68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018e3e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018e3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018e0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018ded`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018ded`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140018e17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140018e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018faf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140018faf`

## string_xrefs

- `0x140018e37`: `wusys.dll`

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
0x140018db4  mov     rax, rsp
0x140018db7  mov     [rax+8], rbx
0x140018dbb  mov     [rax+10h], rsi
0x140018dbf  mov     [rax+18h], rdi
0x140018dc3  push    rbp
0x140018dc4  lea     rbp, [rax-178h]
0x140018dcb  sub     rsp, 270h
0x140018dd2  mov     rax, cs:__security_cookie
0x140018dd9  xor     rax, rsp
0x140018ddc  mov     [rbp+170h+var_10], rax
0x140018de3  lea     rsi, ?g_LoadWUSysLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadWUSysLock
0x140018dea  mov     rcx, rsi; SRWLock
0x140018ded  call    cs:__imp_AcquireSRWLockShared
0x140018df3  xor     ebx, ebx
0x140018df5  mov     rcx, rsi; SRWLock
0x140018df8  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140018dff  jz      short loc_140018E0E
0x140018e01  call    cs:__imp_ReleaseSRWLockShared
0x140018e07  xor     eax, eax
0x140018e09  jmp     loc_140018FB7
0x140018e0e  call    cs:__imp_ReleaseSRWLockShared
0x140018e14  mov     rcx, rsi; SRWLock
0x140018e17  call    cs:__imp_AcquireSRWLockExclusive
0x140018e1d  mov     [rsp+270h+var_238], rsi
0x140018e22  cmp     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140018e29  jnz     loc_140018FAA
0x140018e2f  xor     edx, edx; hFile
0x140018e31  mov     r8d, 880h; dwFlags
0x140018e37  lea     rcx, aWusysDll; "wusys.dll"
0x140018e3e  call    cs:__imp_LoadLibraryExW
0x140018e44  mov     cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWUSysModule
0x140018e4b  test    rax, rax
0x140018e4e  jnz     short loc_140018E55
0x140018e50  lea     edx, [rax+28h]
0x140018e53  jmp     short loc_140018EA3
0x140018e55  mov     [rsp+270h+phModule], rbx
0x140018e5a  mov     r8d, 105h; nSize
0x140018e60  lea     rdx, [rsp+270h+Filename]; lpFilename
0x140018e65  mov     rcx, rax; hModule
0x140018e68  call    cs:__imp_GetModuleFileNameW
0x140018e6e  mov     edi, 1
0x140018e73  test    eax, eax
0x140018e75  jz      short loc_140018E89
0x140018e77  lea     r8, [rsp+270h+phModule]; phModule
0x140018e7c  lea     rdx, [rsp+270h+Filename]; lpModuleName
0x140018e81  mov     ecx, edi; dwFlags
0x140018e83  call    cs:__imp_GetModuleHandleExW
0x140018e89  mov     edx, 0A425h; lpProcName
0x140018e8e  mov     rcx, cs:?g_hWUSysModule@@3PEAUHINSTANCE__@@EA; hModule
0x140018e95  call    cs:__imp_GetProcAddress
0x140018e9b  test    rax, rax
0x140018e9e  jnz     short loc_140018EBD
0x140018ea0  lea     edx, [rax+33h]; void *
0x140018ea3  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x140018eaa  mov     rcx, [rbp+178h]; this
0x140018eb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140018eb6  mov     ebx, eax
0x140018eb8  jmp     loc_140018FAA
0x140018ebd  mov     [rsp+270h+var_228], rbx
0x140018ec2  lea     rdx, [rsp+270h+var_228]
0x140018ec7  mov     qword ptr [rsp+270h+var_250], rdx; int
0x140018ecc  mov     [rsp+270h+var_248], rbx
0x140018ed1  mov     byte ptr [rsp+270h+var_240], dil
0x140018ed6  lea     rdx, [rsp+270h+var_248]
0x140018edb  mov     ecx, edi
0x140018edd  call    _guard_dispatch_icall
0x140018ee2  mov     edi, eax
0x140018ee4  cmp     byte ptr [rsp+270h+var_240], bl
0x140018ee8  jz      short loc_140018F0C
0x140018eea  mov     r8, qword ptr [rsp+270h+var_250]
0x140018eef  mov     rcx, [r8]
0x140018ef2  mov     rdx, [rsp+270h+var_248]
0x140018ef7  mov     [r8], rdx
0x140018efa  test    rcx, rcx
0x140018efd  jz      short loc_140018F0C
0x140018eff  mov     rax, [rcx]
0x140018f02  mov     rax, [rax+10h]
0x140018f06  call    _guard_dispatch_icall
0x140018f0b  nop
0x140018f0c  test    edi, edi
0x140018f0e  jns     short loc_140018F1A
0x140018f10  mov     r9d, edi
0x140018f13  mov     edx, 36h ; '6'
0x140018f18  jmp     short loc_140018F66
0x140018f1a  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140018f21  mov     cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A, rbx; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140018f28  test    rcx, rcx
0x140018f2b  jz      short loc_140018F3A
0x140018f2d  mov     rax, [rcx]
0x140018f30  mov     rax, [rax+10h]
0x140018f34  call    _guard_dispatch_icall
0x140018f39  nop
0x140018f3a  mov     rcx, [rsp+270h+var_228]
0x140018f3f  mov     rax, [rcx]
0x140018f42  lea     r8, ?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x140018f49  lea     rdx, _GUID_07186f27_adf4_4d8c_862a_5d403bd2010a
0x140018f50  mov     rax, [rax]
0x140018f53  call    _guard_dispatch_icall
0x140018f58  mov     edi, eax
0x140018f5a  test    eax, eax
0x140018f5c  jns     short loc_140018F93
0x140018f5e  mov     r9d, eax; char *
0x140018f61  mov     edx, 37h ; '7'; void *
0x140018f66  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x140018f6d  mov     rcx, [rbp+178h]; this
0x140018f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018f79  nop
0x140018f7a  mov     rcx, [rsp+270h+var_228]
0x140018f7f  test    rcx, rcx
0x140018f82  jz      short loc_140018F91
0x140018f84  mov     rax, [rcx]
0x140018f87  mov     rax, [rax+10h]
0x140018f8b  call    _guard_dispatch_icall
0x140018f90  nop
0x140018f91  jmp     short loc_140018FAC
0x140018f93  mov     rcx, [rsp+270h+var_228]
0x140018f98  test    rcx, rcx
0x140018f9b  jz      short loc_140018FAA
0x140018f9d  mov     rax, [rcx]
0x140018fa0  mov     rax, [rax+10h]
0x140018fa4  call    _guard_dispatch_icall
0x140018fa9  nop
0x140018faa  mov     edi, ebx
0x140018fac  mov     rcx, rsi; SRWLock
0x140018faf  call    cs:__imp_ReleaseSRWLockExclusive
0x140018fb5  mov     eax, edi
0x140018fb7  mov     rcx, [rbp+170h+var_10]
0x140018fbe  xor     rcx, rsp; StackCookie
0x140018fc1  call    __security_check_cookie
0x140018fc6  lea     r11, [rsp+270h+var_s0]
0x140018fce  mov     rbx, [r11+10h]
0x140018fd2  mov     rsi, [r11+18h]
0x140018fd6  mov     rdi, [r11+20h]
0x140018fda  mov     rsp, r11
0x140018fdd  pop     rbp
0x140018fde  retn
```

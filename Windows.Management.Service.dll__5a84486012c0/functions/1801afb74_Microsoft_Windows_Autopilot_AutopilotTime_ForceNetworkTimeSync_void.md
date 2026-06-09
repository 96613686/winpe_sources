# Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)

- ea: `0x1801afb74`
- end: `0x1801afcbb`
- name: `?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801984ac`

## callees

- `0x180067a54`
- `0x1800813fc`
- `0x1800873a4`
- `0x1801afb74`
- `0x1801b2e6c`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801afbd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801afbd3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801afbb5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801afbb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801afc17`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801afc17`

## string_xrefs

- `0x1801afb90`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801afc37`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801afc96`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801afbae`: `w32time.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(
        const unsigned __int16 *a1,
        unsigned int a2)
{
  int started; // eax
  unsigned int v3; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbp
  __int64 v6; // rdx
  unsigned int v7; // ebx
  DWORD v8; // esi
  int i; // edi
  unsigned int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  unsigned int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HMODULE v15; // [rsp+50h] [rbp+8h] BYREF

  started = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(a1, a2);
  v3 = started;
  if ( started >= 0 )
  {
    Library = LoadLibraryExW(L"w32time.DLL", 0, 0x800u);
    v15 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "W32TimeSyncNow");
      if ( ProcAddress )
      {
        v7 = 0;
        v8 = 1000;
        for ( i = 0; ; ++i )
        {
          if ( i >= 3 )
          {
            if ( v7 == 1 )
            {
              v3 = -2095972095;
              goto LABEL_25;
            }
LABEL_20:
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v15);
            return 0;
          }
          v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
          v7 = v10;
          if ( !v10 )
            goto LABEL_20;
          if ( v10 != 1 )
            break;
          Sleep(v8);
          v8 *= 2;
        }
        if ( v10 == 2 )
        {
          v3 = -2095972094;
          v6 = 78;
          goto LABEL_23;
        }
        v11 = retaddr;
        if ( v10 == 3 )
        {
          v3 = -2095972093;
          v6 = 79;
          goto LABEL_24;
        }
        if ( v10 == 4 )
        {
          v3 = -2095972092;
          v6 = 80;
          goto LABEL_24;
        }
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x53,
               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
               (const char *)v10,
               v13);
        goto LABEL_25;
      }
      v6 = 59;
    }
    else
    {
      v6 = 55;
    }
    v3 = -2147467263;
LABEL_23:
    v11 = retaddr;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      v11,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
      (const char *)v3,
      v13);
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v15);
    return v3;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
    (const char *)(unsigned int)started,
    v13);
  return v3;
}

```

## disassembly

```asm
0x1801afb74  push    rbx
0x1801afb76  push    rbp
0x1801afb77  push    rsi
0x1801afb78  push    rdi
0x1801afb79  sub     rsp, 28h
0x1801afb7d  call    ?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)
0x1801afb82  mov     ebx, eax
0x1801afb84  test    eax, eax
0x1801afb86  jns     short loc_1801AFBA6
0x1801afb88  mov     rcx, [rsp+48h]; this
0x1801afb8d  mov     r9d, eax; char *
0x1801afb90  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801afb97  mov     edx, 33h ; '3'; void *
0x1801afb9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801afba1  jmp     loc_1801AFCB0
0x1801afba6  xor     edx, edx; hFile
0x1801afba8  mov     r8d, 800h; dwFlags
0x1801afbae  lea     rcx, aW32timeDll; "w32time.DLL"
0x1801afbb5  call    cs:__imp_LoadLibraryExW
0x1801afbbb  mov     [rsp+48h+arg_0], rax
0x1801afbc0  test    rax, rax
0x1801afbc3  jz      loc_1801AFC87
0x1801afbc9  lea     rdx, aW32timesyncnow; "W32TimeSyncNow"
0x1801afbd0  mov     rcx, rax; hModule
0x1801afbd3  call    cs:__imp_GetProcAddress
0x1801afbd9  mov     rbp, rax
0x1801afbdc  test    rax, rax
0x1801afbdf  jnz     short loc_1801AFBE9
0x1801afbe1  lea     edx, [rax+3Bh]
0x1801afbe4  jmp     loc_1801AFC8C
0x1801afbe9  xor     ebx, ebx
0x1801afbeb  mov     esi, 3E8h
0x1801afbf0  xor     edi, edi
0x1801afbf2  cmp     edi, 3
0x1801afbf5  jge     short loc_1801AFC6D
0x1801afbf7  mov     edx, 1
0x1801afbfc  xor     ecx, ecx
0x1801afbfe  lea     r8d, [rdx+11h]
0x1801afc02  mov     rax, rbp
0x1801afc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801afc0a  mov     ebx, eax
0x1801afc0c  test    eax, eax
0x1801afc0e  jz      short loc_1801AFC79
0x1801afc10  cmp     eax, 1
0x1801afc13  jnz     short loc_1801AFC23
0x1801afc15  mov     ecx, esi; dwMilliseconds
0x1801afc17  call    cs:__imp_Sleep
0x1801afc1d  add     esi, esi
0x1801afc1f  inc     edi
0x1801afc21  jmp     short loc_1801AFBF2
0x1801afc23  cmp     eax, 2
0x1801afc26  jnz     short loc_1801AFC32
0x1801afc28  mov     ebx, 83120102h
0x1801afc2d  lea     edx, [rax+4Ch]
0x1801afc30  jmp     short loc_1801AFC91
0x1801afc32  mov     rcx, [rsp+48h]; this
0x1801afc37  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801afc3e  cmp     eax, 3
0x1801afc41  jnz     short loc_1801AFC4D
0x1801afc43  mov     ebx, 83120103h
0x1801afc48  lea     edx, [rax+4Ch]
0x1801afc4b  jmp     short loc_1801AFC9D
0x1801afc4d  cmp     eax, 4
0x1801afc50  jnz     short loc_1801AFC5C
0x1801afc52  mov     ebx, 83120104h
0x1801afc57  lea     edx, [rax+4Ch]
0x1801afc5a  jmp     short loc_1801AFC9D
0x1801afc5c  mov     r9d, eax; char *
0x1801afc5f  mov     edx, 53h ; 'S'; void *
0x1801afc64  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801afc69  mov     ebx, eax
0x1801afc6b  jmp     short loc_1801AFCA6
0x1801afc6d  cmp     ebx, 1
0x1801afc70  jnz     short loc_1801AFC79
0x1801afc72  mov     ebx, 83120101h
0x1801afc77  jmp     short loc_1801AFCA6
0x1801afc79  lea     rcx, [rsp+48h+arg_0]
0x1801afc7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801afc83  xor     eax, eax
0x1801afc85  jmp     short loc_1801AFCB2
0x1801afc87  mov     edx, 37h ; '7'; void *
0x1801afc8c  mov     ebx, 80004001h
0x1801afc91  mov     rcx, [rsp+48h]; this
0x1801afc96  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801afc9d  mov     r9d, ebx; char *
0x1801afca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801afca5  nop
0x1801afca6  lea     rcx, [rsp+48h+arg_0]
0x1801afcab  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801afcb0  mov     eax, ebx
0x1801afcb2  add     rsp, 28h
0x1801afcb6  pop     rdi
0x1801afcb7  pop     rsi
0x1801afcb8  pop     rbp
0x1801afcb9  pop     rbx
0x1801afcba  retn
```

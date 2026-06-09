# Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)

- ea: `0x1801b5480`
- end: `0x1801b55da`
- name: `?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `346`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019d6fc`

## callees

- `0x180067e54`
- `0x180081e80`
- `0x180088144`
- `0x1801b5480`
- `0x1801b88a4`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801b54e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801b54e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801b54c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801b54c1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b552f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801b552f`

## string_xrefs

- `0x1801b549c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801b5555`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801b55b4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1801b54ba`: `w32time.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1801b5480  push    rbx
0x1801b5482  push    rbp
0x1801b5483  push    rsi
0x1801b5484  push    rdi
0x1801b5485  sub     rsp, 28h
0x1801b5489  call    ?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)
0x1801b548e  mov     ebx, eax
0x1801b5490  test    eax, eax
0x1801b5492  jns     short loc_1801B54B2
0x1801b5494  mov     rcx, [rsp+48h]; this
0x1801b5499  mov     r9d, eax; char *
0x1801b549c  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b54a3  mov     edx, 33h ; '3'; void *
0x1801b54a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b54ad  jmp     loc_1801B55CE
0x1801b54b2  xor     edx, edx; hFile
0x1801b54b4  mov     r8d, 800h; dwFlags
0x1801b54ba  lea     rcx, aW32timeDll; "w32time.DLL"
0x1801b54c1  call    cs:__imp_LoadLibraryExW
0x1801b54c8  nop     dword ptr [rax+rax+00h]
0x1801b54cd  mov     [rsp+48h+arg_0], rax
0x1801b54d2  test    rax, rax
0x1801b54d5  jz      loc_1801B55A5
0x1801b54db  lea     rdx, aW32timesyncnow; "W32TimeSyncNow"
0x1801b54e2  mov     rcx, rax; hModule
0x1801b54e5  call    cs:__imp_GetProcAddress
0x1801b54ec  nop     dword ptr [rax+rax+00h]
0x1801b54f1  mov     rbp, rax
0x1801b54f4  test    rax, rax
0x1801b54f7  jnz     short loc_1801B5501
0x1801b54f9  lea     edx, [rax+3Bh]
0x1801b54fc  jmp     loc_1801B55AA
0x1801b5501  xor     ebx, ebx
0x1801b5503  mov     esi, 3E8h
0x1801b5508  xor     edi, edi
0x1801b550a  cmp     edi, 3
0x1801b550d  jge     short loc_1801B558B
0x1801b550f  mov     edx, 1
0x1801b5514  xor     ecx, ecx
0x1801b5516  lea     r8d, [rdx+11h]
0x1801b551a  mov     rax, rbp
0x1801b551d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5522  mov     ebx, eax
0x1801b5524  test    eax, eax
0x1801b5526  jz      short loc_1801B5597
0x1801b5528  cmp     eax, 1
0x1801b552b  jnz     short loc_1801B5541
0x1801b552d  mov     ecx, esi; dwMilliseconds
0x1801b552f  call    cs:__imp_Sleep
0x1801b5536  nop     dword ptr [rax+rax+00h]
0x1801b553b  add     esi, esi
0x1801b553d  inc     edi
0x1801b553f  jmp     short loc_1801B550A
0x1801b5541  cmp     eax, 2
0x1801b5544  jnz     short loc_1801B5550
0x1801b5546  mov     ebx, 83120102h
0x1801b554b  lea     edx, [rax+4Ch]
0x1801b554e  jmp     short loc_1801B55AF
0x1801b5550  mov     rcx, [rsp+48h]; this
0x1801b5555  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b555c  cmp     eax, 3
0x1801b555f  jnz     short loc_1801B556B
0x1801b5561  mov     ebx, 83120103h
0x1801b5566  lea     edx, [rax+4Ch]
0x1801b5569  jmp     short loc_1801B55BB
0x1801b556b  cmp     eax, 4
0x1801b556e  jnz     short loc_1801B557A
0x1801b5570  mov     ebx, 83120104h
0x1801b5575  lea     edx, [rax+4Ch]
0x1801b5578  jmp     short loc_1801B55BB
0x1801b557a  mov     r9d, eax; char *
0x1801b557d  mov     edx, 53h ; 'S'; void *
0x1801b5582  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801b5587  mov     ebx, eax
0x1801b5589  jmp     short loc_1801B55C4
0x1801b558b  cmp     ebx, 1
0x1801b558e  jnz     short loc_1801B5597
0x1801b5590  mov     ebx, 83120101h
0x1801b5595  jmp     short loc_1801B55C4
0x1801b5597  lea     rcx, [rsp+48h+arg_0]
0x1801b559c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801b55a1  xor     eax, eax
0x1801b55a3  jmp     short loc_1801B55D0
0x1801b55a5  mov     edx, 37h ; '7'; void *
0x1801b55aa  mov     ebx, 80004001h
0x1801b55af  mov     rcx, [rsp+48h]; this
0x1801b55b4  lea     r8, aOnecoreuapAdmi_47; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b55bb  mov     r9d, ebx; char *
0x1801b55be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b55c3  nop
0x1801b55c4  lea     rcx, [rsp+48h+arg_0]
0x1801b55c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801b55ce  mov     eax, ebx
0x1801b55d0  add     rsp, 28h
0x1801b55d4  pop     rdi
0x1801b55d5  pop     rsi
0x1801b55d6  pop     rbp
0x1801b55d7  pop     rbx
0x1801b55d8  retn
```

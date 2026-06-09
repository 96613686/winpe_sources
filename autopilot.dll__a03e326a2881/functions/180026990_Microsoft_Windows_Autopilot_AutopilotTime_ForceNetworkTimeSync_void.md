# Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)

- ea: `0x180026990`
- end: `0x180026aee`
- name: `?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `350`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ab88`
- `0x18002230c`

## callees

- `0x1800105f4`
- `0x1800166dc`
- `0x180026990`
- `0x18002769c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800269f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800269f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800269d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800269d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026a49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026abc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026a49`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026abc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026a35`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026a35`

## string_xrefs

- `0x1800269ac`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180026a66`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180026a81`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180026ad1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1800269cc`: `w32time.DLL`

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
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rbp
  unsigned int v8; // edi
  __int64 v9; // rdx
  DWORD v10; // esi
  int v11; // edi
  unsigned int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  unsigned int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  started = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(a1, a2);
  v3 = started;
  if ( started >= 0 )
  {
    Library = LoadLibraryExW(L"w32time.DLL", 0, 0x800u);
    v6 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "W32TimeSyncNow");
      if ( ProcAddress )
      {
        v10 = 1000;
        v11 = 0;
        while ( 1 )
        {
          v12 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
          if ( !v12 )
          {
            v8 = 0;
            goto LABEL_22;
          }
          if ( v12 != 1 )
            break;
          Sleep(v10);
          if ( ++v11 >= 3 )
          {
            FreeLibrary(v6);
            return 2198995201LL;
          }
          v10 *= 2;
        }
        if ( v12 == 2 )
        {
          v8 = -2095972094;
          v9 = 78;
          goto LABEL_14;
        }
        v13 = retaddr;
        if ( v12 == 3 )
        {
          v8 = -2095972093;
          v9 = 79;
          goto LABEL_15;
        }
        if ( v12 == 4 )
        {
          v8 = -2095972092;
          v9 = 80;
          goto LABEL_15;
        }
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x53,
               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
               (const char *)v12,
               v14);
      }
      else
      {
        v8 = -2147467263;
        v9 = 59;
LABEL_14:
        v13 = retaddr;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          v13,
          (void *)v9,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
          (const char *)v8,
          v14);
      }
LABEL_22:
      FreeLibrary(v6);
    }
    else
    {
      v8 = -2147467263;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
        (const char *)0x80004001LL,
        v14);
    }
    return v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottime.cpp",
      (const char *)(unsigned int)started,
      v14);
    return v3;
  }
}

```

## disassembly

```asm
0x180026990  push    rbx
0x180026992  push    rbp
0x180026993  push    rsi
0x180026994  push    rdi
0x180026995  sub     rsp, 28h
0x180026999  call    ?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)
0x18002699e  mov     ebx, eax
0x1800269a0  test    eax, eax
0x1800269a2  jns     short loc_1800269C4
0x1800269a4  mov     rcx, [rsp+48h]; this
0x1800269a9  mov     r9d, eax; char *
0x1800269ac  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800269b3  mov     edx, 33h ; '3'; void *
0x1800269b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269bd  mov     eax, ebx
0x1800269bf  jmp     loc_180026AE5
0x1800269c4  xor     edx, edx; hFile
0x1800269c6  mov     r8d, 800h; dwFlags
0x1800269cc  lea     rcx, aW32timeDll; "w32time.DLL"
0x1800269d3  call    cs:__imp_LoadLibraryExW
0x1800269d9  mov     rbx, rax
0x1800269dc  mov     [rsp+48h+arg_0], rax
0x1800269e1  test    rax, rax
0x1800269e4  jz      loc_180026AC4
0x1800269ea  lea     rdx, aW32timesyncnow; "W32TimeSyncNow"
0x1800269f1  mov     rcx, rax; hModule
0x1800269f4  call    cs:__imp_GetProcAddress
0x1800269fa  mov     rbp, rax
0x1800269fd  test    rax, rax
0x180026a00  jnz     short loc_180026A0C
0x180026a02  mov     edi, 80004001h
0x180026a07  lea     edx, [rax+3Bh]
0x180026a0a  jmp     short loc_180026A66
0x180026a0c  mov     esi, 3E8h
0x180026a11  xor     edi, edi
0x180026a13  mov     edx, 1
0x180026a18  xor     ecx, ecx
0x180026a1a  lea     r8d, [rdx+11h]
0x180026a1e  mov     rax, rbp
0x180026a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a26  test    eax, eax
0x180026a28  jz      loc_180026AB7
0x180026a2e  cmp     eax, 1
0x180026a31  jnz     short loc_180026A59
0x180026a33  mov     ecx, esi; dwMilliseconds
0x180026a35  call    cs:__imp_Sleep
0x180026a3b  inc     edi
0x180026a3d  cmp     edi, 3
0x180026a40  jge     short loc_180026A46
0x180026a42  add     esi, esi
0x180026a44  jmp     short loc_180026A13
0x180026a46  mov     rcx, rbx; hLibModule
0x180026a49  call    cs:__imp_FreeLibrary
0x180026a4f  mov     eax, 83120101h
0x180026a54  jmp     loc_180026AE5
0x180026a59  cmp     eax, 2
0x180026a5c  jnz     short loc_180026A7C
0x180026a5e  mov     edi, 83120102h
0x180026a63  lea     edx, [rax+4Ch]; void *
0x180026a66  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026a6d  mov     rcx, [rsp+48h]; this
0x180026a72  mov     r9d, edi; char *
0x180026a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a7a  jmp     short loc_180026AB9
0x180026a7c  mov     rcx, [rsp+48h]; this
0x180026a81  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026a88  cmp     eax, 3
0x180026a8b  jnz     short loc_180026A97
0x180026a8d  mov     edi, 83120103h
0x180026a92  lea     edx, [rax+4Ch]
0x180026a95  jmp     short loc_180026A72
0x180026a97  cmp     eax, 4
0x180026a9a  jnz     short loc_180026AA6
0x180026a9c  mov     edi, 83120104h
0x180026aa1  lea     edx, [rax+4Ch]
0x180026aa4  jmp     short loc_180026A72
0x180026aa6  mov     r9d, eax; char *
0x180026aa9  mov     edx, 53h ; 'S'; void *
0x180026aae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180026ab3  mov     edi, eax
0x180026ab5  jmp     short loc_180026AB9
0x180026ab7  xor     edi, edi
0x180026ab9  mov     rcx, rbx; hLibModule
0x180026abc  call    cs:__imp_FreeLibrary
0x180026ac2  jmp     short loc_180026AE3
0x180026ac4  mov     rcx, [rsp+48h]; this
0x180026ac9  mov     edi, 80004001h
0x180026ace  mov     r9d, edi; char *
0x180026ad1  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026ad8  mov     edx, 37h ; '7'; void *
0x180026add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ae2  nop
0x180026ae3  mov     eax, edi
0x180026ae5  add     rsp, 28h
0x180026ae9  pop     rdi
0x180026aea  pop     rsi
0x180026aeb  pop     rbp
0x180026aec  pop     rbx
0x180026aed  retn
```

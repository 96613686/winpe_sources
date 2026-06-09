# Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(void)

- ea: `0x180027904`
- end: `0x180027a81`
- name: `?ForceNetworkTimeSync@AutopilotTime@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `381`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b220`
- `0x180022dd4`

## callees

- `0x180010764`
- `0x180016b80`
- `0x180027904`
- `0x1800286f4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002796e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002796e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027947`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027947`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800279cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027a48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800279cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027a48`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800279b5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800279b5`

## string_xrefs

- `0x180027920`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x1800279f2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180027a0d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180027a63`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottime.cpp`
- `0x180027940`: `w32time.DLL`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotTime::ForceNetworkTimeSync(
        const unsigned __int16 *a1,
        __int64 a2)
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
0x180027904  push    rbx
0x180027906  push    rbp
0x180027907  push    rsi
0x180027908  push    rdi
0x180027909  sub     rsp, 28h
0x18002790d  call    ?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)
0x180027912  mov     ebx, eax
0x180027914  test    eax, eax
0x180027916  jns     short loc_180027938
0x180027918  mov     rcx, [rsp+48h]; this
0x18002791d  mov     r9d, eax; char *
0x180027920  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027927  mov     edx, 33h ; '3'; void *
0x18002792c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027931  mov     eax, ebx
0x180027933  jmp     loc_180027A77
0x180027938  xor     edx, edx; hFile
0x18002793a  mov     r8d, 800h; dwFlags
0x180027940  lea     rcx, aW32timeDll; "w32time.DLL"
0x180027947  call    cs:__imp_LoadLibraryExW
0x18002794e  nop     dword ptr [rax+rax+00h]
0x180027953  mov     rbx, rax
0x180027956  mov     [rsp+48h+arg_0], rax
0x18002795b  test    rax, rax
0x18002795e  jz      loc_180027A56
0x180027964  lea     rdx, aW32timesyncnow; "W32TimeSyncNow"
0x18002796b  mov     rcx, rax; hModule
0x18002796e  call    cs:__imp_GetProcAddress
0x180027975  nop     dword ptr [rax+rax+00h]
0x18002797a  mov     rbp, rax
0x18002797d  test    rax, rax
0x180027980  jnz     short loc_18002798C
0x180027982  mov     edi, 80004001h
0x180027987  lea     edx, [rax+3Bh]
0x18002798a  jmp     short loc_1800279F2
0x18002798c  mov     esi, 3E8h
0x180027991  xor     edi, edi
0x180027993  mov     edx, 1
0x180027998  xor     ecx, ecx
0x18002799a  lea     r8d, [rdx+11h]
0x18002799e  mov     rax, rbp
0x1800279a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279a6  test    eax, eax
0x1800279a8  jz      loc_180027A43
0x1800279ae  cmp     eax, 1
0x1800279b1  jnz     short loc_1800279E5
0x1800279b3  mov     ecx, esi; dwMilliseconds
0x1800279b5  call    cs:__imp_Sleep
0x1800279bc  nop     dword ptr [rax+rax+00h]
0x1800279c1  inc     edi
0x1800279c3  cmp     edi, 3
0x1800279c6  jge     short loc_1800279CC
0x1800279c8  add     esi, esi
0x1800279ca  jmp     short loc_180027993
0x1800279cc  mov     rcx, rbx; hLibModule
0x1800279cf  call    cs:__imp_FreeLibrary
0x1800279d6  nop     dword ptr [rax+rax+00h]
0x1800279db  mov     eax, 83120101h
0x1800279e0  jmp     loc_180027A77
0x1800279e5  cmp     eax, 2
0x1800279e8  jnz     short loc_180027A08
0x1800279ea  mov     edi, 83120102h
0x1800279ef  lea     edx, [rax+4Ch]; void *
0x1800279f2  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800279f9  mov     rcx, [rsp+48h]; this
0x1800279fe  mov     r9d, edi; char *
0x180027a01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a06  jmp     short loc_180027A45
0x180027a08  mov     rcx, [rsp+48h]; this
0x180027a0d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027a14  cmp     eax, 3
0x180027a17  jnz     short loc_180027A23
0x180027a19  mov     edi, 83120103h
0x180027a1e  lea     edx, [rax+4Ch]
0x180027a21  jmp     short loc_1800279FE
0x180027a23  cmp     eax, 4
0x180027a26  jnz     short loc_180027A32
0x180027a28  mov     edi, 83120104h
0x180027a2d  lea     edx, [rax+4Ch]
0x180027a30  jmp     short loc_1800279FE
0x180027a32  mov     r9d, eax; char *
0x180027a35  mov     edx, 53h ; 'S'; void *
0x180027a3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027a3f  mov     edi, eax
0x180027a41  jmp     short loc_180027A45
0x180027a43  xor     edi, edi
0x180027a45  mov     rcx, rbx; hLibModule
0x180027a48  call    cs:__imp_FreeLibrary
0x180027a4f  nop     dword ptr [rax+rax+00h]
0x180027a54  jmp     short loc_180027A75
0x180027a56  mov     rcx, [rsp+48h]; this
0x180027a5b  mov     edi, 80004001h
0x180027a60  mov     r9d, edi; char *
0x180027a63  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027a6a  mov     edx, 37h ; '7'; void *
0x180027a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a74  nop
0x180027a75  mov     eax, edi
0x180027a77  add     rsp, 28h
0x180027a7b  pop     rdi
0x180027a7c  pop     rsi
0x180027a7d  pop     rbp
0x180027a7e  pop     rbx
0x180027a7f  retn
```

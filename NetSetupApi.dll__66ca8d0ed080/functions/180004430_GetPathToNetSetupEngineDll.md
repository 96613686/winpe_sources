# GetPathToNetSetupEngineDll

- ea: `0x180004430`
- end: `0x1800046d4`
- name: `GetPathToNetSetupEngineDll`
- size: `676`
- prototype: `errno_t __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180004260`

## callees

- `0x180004430`
- `0x1800046dc`
- `0x180006608`
- `0x18000895c`
- `0x18000cab4`
- `0x18000cb40`
- `0x1800119f0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800044a7`
- `msvcrt!wcsrchr` at `0x1800044a7`
- `msvcrt!wcscpy_s` at `0x1800044d0`
- `msvcrt!wcscpy_s` at `0x1800044d0`
- `ntdll!RtlCaptureStackBackTrace` at `0x180004566`
- `ntdll!RtlCaptureStackBackTrace` at `0x180004566`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180004468`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180004468`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180004491`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180004491`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045ab`

## string_xrefs

- `0x1800044bd`: `NetSetupEngine.dll`

## pseudocode

```c
errno_t __fastcall GetPathToNetSetupEngineDll(wchar_t *Str)
{
  wchar_t *v2; // rax
  errno_t result; // eax
  struct NetSetupExceptionTrace near **v4; // rbx
  signed int LastError; // eax
  signed int v6; // eax
  _QWORD pExceptionObject[26]; // [rsp+20h] [rbp-E8h] BYREF
  HMODULE hModule; // [rsp+F0h] [rbp-18h] BYREF

  hModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)GetPathToNetSetupEngineDll, &hModule) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  if ( !GetModuleFileNameW(hModule, Str, 0x104u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v6);
    throw (HResultException *)pExceptionObject;
  }
  v2 = wcsrchr(Str, 0x5Cu);
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f1172f7f51b138cada6e87324e167680_Traceguids, Str);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024770);
    throw (HResultException *)pExceptionObject;
  }
  result = wcscpy_s(v2 + 1, 260 - (v2 + 1 - Str), L"NetSetupEngine.dll");
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f1172f7f51b138cada6e87324e167680_Traceguids, Str);
    wil::ResultException::ResultException((wil::ResultException *)pExceptionObject, -2147024770);
    pExceptionObject[0] = &Win32Exception::`vftable';
    v4 = &g_NetSetupExceptionTraces + 17 * g_NetSetupNextExceptionTrace;
    g_NetSetupNextExceptionTrace = ((_BYTE)g_NetSetupNextExceptionTrace + 1) & 3;
    *(_DWORD *)v4 = RtlCaptureStackBackTrace(1u, 0x10u, (PVOID *)v4 + 1, 0);
    throw (HResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180004430  mov     r11, rsp
0x180004433  push    rdi
0x180004434  sub     rsp, 100h
0x18000443b  mov     rax, cs:__security_cookie
0x180004442  xor     rax, rsp
0x180004445  mov     [rsp+108h+var_10], rax
0x18000444d  mov     rdi, rcx
0x180004450  mov     qword ptr [r11-18h], 0
0x180004458  mov     ecx, 6; dwFlags
0x18000445d  lea     r8, [r11-18h]; phModule
0x180004461  lea     rdx, GetPathToNetSetupEngineDll; lpModuleName
0x180004468  call    cs:__imp_GetModuleHandleExW
0x18000446e  test    eax, eax
0x180004470  jz      loc_1800045D7
0x180004476  mov     rcx, [rsp+108h+hModule]; hModule
0x18000447e  mov     rdx, rdi; lpFilename
0x180004481  mov     [rsp+108h+arg_8], rbx
0x180004489  mov     ebx, 104h
0x18000448e  mov     r8d, ebx; nSize
0x180004491  call    cs:__imp_GetModuleFileNameW
0x180004497  test    eax, eax
0x180004499  jz      loc_180004617
0x18000449f  mov     edx, 5Ch ; '\'; Ch
0x1800044a4  mov     rcx, rdi; Str
0x1800044a7  call    cs:__imp_wcsrchr
0x1800044ad  test    rax, rax
0x1800044b0  jz      loc_18000465B
0x1800044b6  lea     rcx, [rax+2]; Destination
0x1800044ba  mov     rax, rcx
0x1800044bd  lea     r8, aNetsetupengine; "NetSetupEngine.dll"
0x1800044c4  sub     rax, rdi
0x1800044c7  sar     rax, 1
0x1800044ca  sub     rbx, rax
0x1800044cd  mov     rdx, rbx; SizeInWords
0x1800044d0  call    cs:__imp_wcscpy_s
0x1800044d6  test    eax, eax
0x1800044d8  jnz     short loc_1800044FB
0x1800044da  mov     rbx, [rsp+108h+arg_8]
0x1800044e2  mov     rcx, [rsp+108h+var_10]
0x1800044ea  xor     rcx, rsp; StackCookie
0x1800044ed  call    __security_check_cookie
0x1800044f2  add     rsp, 100h
0x1800044f9  pop     rdi
0x1800044fa  retn
0x1800044fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004502  lea     rax, WPP_GLOBAL_Control
0x180004509  cmp     rcx, rax
0x18000450c  jnz     loc_1800046AD
0x180004512  mov     edx, 8007007Eh; int
0x180004517  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18000451c  call    ??0ResultException@wil@@QEAA@J@Z; wil::ResultException::ResultException(long)
0x180004521  lea     rcx, ?g_NetSetupExceptionTraces@@3PAUNetSetupExceptionTrace@@A; NetSetupExceptionTrace near * g_NetSetupExceptionTraces
0x180004528  xor     r9d, r9d; BackTraceHash
0x18000452b  lea     rax, ??_7Win32Exception@@6B@; const Win32Exception::`vftable'
0x180004532  mov     edx, 10h; FramesToCapture
0x180004537  mov     [rsp+108h+pExceptionObject], rax
0x18000453c  mov     eax, cs:?g_NetSetupNextExceptionTrace@@3KC; ulong volatile g_NetSetupNextExceptionTrace
0x180004542  imul    rbx, rax, 88h
0x180004549  mov     eax, cs:?g_NetSetupNextExceptionTrace@@3KC; ulong volatile g_NetSetupNextExceptionTrace
0x18000454f  add     rbx, rcx
0x180004552  inc     eax
0x180004554  and     eax, 3
0x180004557  mov     ecx, 1; FramesToSkip
0x18000455c  mov     cs:?g_NetSetupNextExceptionTrace@@3KC, eax; ulong volatile g_NetSetupNextExceptionTrace
0x180004562  lea     r8, [rbx+8]; BackTrace
0x180004566  call    cs:__imp_RtlCaptureStackBackTrace
0x18000456c  movzx   eax, ax
0x18000456f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180004576  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18000457b  mov     [rbx], eax
0x18000457d  call    _CxxThrowException_0
0x180004583  call    cs:__imp_GetLastError
0x180004589  test    eax, eax
0x18000458b  jg      short loc_18000460A
0x18000458d  mov     edx, eax; int
0x18000458f  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180004594  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180004599  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800045a0  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800045a5  call    _CxxThrowException_0
0x1800045ab  call    cs:__imp_GetLastError
0x1800045b1  test    eax, eax
0x1800045b3  jg      loc_18000464E
0x1800045b9  mov     edx, eax; int
0x1800045bb  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800045c0  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800045c5  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800045cc  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800045d1  call    _CxxThrowException_0
0x1800045d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045de  lea     rax, WPP_GLOBAL_Control
0x1800045e5  cmp     rcx, rax
0x1800045e8  jz      short loc_180004583
0x1800045ea  cmp     byte ptr [rcx+19h], 2
0x1800045ee  jb      short loc_180004583
0x1800045f0  mov     rcx, [rcx+10h]
0x1800045f4  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x1800045fb  mov     edx, 0Ah
0x180004600  call    WPP_SF_
0x180004605  jmp     loc_180004583
0x18000460a  movzx   eax, ax
0x18000460d  or      eax, 80070000h
0x180004612  jmp     loc_18000458D
0x180004617  mov     rcx, cs:WPP_GLOBAL_Control
0x18000461e  lea     rax, WPP_GLOBAL_Control
0x180004625  cmp     rcx, rax
0x180004628  jz      short loc_1800045AB
0x18000462a  cmp     byte ptr [rcx+19h], 2
0x18000462e  jb      loc_1800045AB
0x180004634  mov     rcx, [rcx+10h]
0x180004638  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000463f  mov     edx, 0Bh
0x180004644  call    WPP_SF_
0x180004649  jmp     loc_1800045AB
0x18000464e  movzx   eax, ax
0x180004651  or      eax, 80070000h
0x180004656  jmp     loc_1800045B9
0x18000465b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004662  lea     rax, WPP_GLOBAL_Control
0x180004669  cmp     rcx, rax
0x18000466c  jz      short loc_18000468C
0x18000466e  cmp     byte ptr [rcx+19h], 2
0x180004672  jb      short loc_18000468C
0x180004674  mov     rcx, [rcx+10h]
0x180004678  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x18000467f  mov     edx, 0Ch
0x180004684  mov     r9, rdi
0x180004687  call    WPP_SF_S
0x18000468c  mov     edx, 8007007Eh; int
0x180004691  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180004696  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000469b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800046a2  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800046a7  call    _CxxThrowException_0
0x1800046ad  cmp     byte ptr [rcx+19h], 2
0x1800046b1  jb      loc_180004512
0x1800046b7  mov     rcx, [rcx+10h]
0x1800046bb  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x1800046c2  mov     edx, 0Dh
0x1800046c7  mov     r9, rdi
0x1800046ca  call    WPP_SF_S
0x1800046cf  jmp     loc_180004512
```

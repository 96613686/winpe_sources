# IncrementOutstandingHandles

- ea: `0x180004260`
- end: `0x18000441e`
- name: `IncrementOutstandingHandles`
- size: `446`
- prototype: `void()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003b90`

## callees

- `0x180004260`
- `0x180004430`
- `0x180006608`
- `0x18000895c`
- `0x18000cab4`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800042fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800042fa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800042d9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800042d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004332`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000429b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000429b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004359`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042a1`

## pseudocode

```c
void IncrementOutstandingHandles()
{
  unsigned int v0; // eax
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed int LastError; // eax
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-2F8h] BYREF
  WCHAR LibFileName[264]; // [rsp+110h] [rbp-228h] BYREF

  AcquireSRWLockExclusive(&g_NetSetupHandleCountLock);
  dword_180025A68 = GetCurrentThreadId();
  v0 = g_NumNetSetupHandles;
  if ( !g_NumNetSetupHandles )
  {
    GetPathToNetSetupEngineDll(LibFileName);
    Library = LoadLibraryExW(LibFileName, 0, 0);
    v2 = Library;
    if ( !Library )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024770);
      throw (HResultException *)pExceptionObject;
    }
    g_NetSetupGetEnginePfn = (struct NetSetupImplementation *(*)(unsigned int, struct _NETSETUP_ENVIRONMENT *))GetProcAddress(Library, "NetSetupGetEngine");
    if ( !g_NetSetupGetEnginePfn )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f1172f7f51b138cada6e87324e167680_Traceguids);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, LastError);
      throw (HResultException *)pExceptionObject;
    }
    g_NetSetupEngine = v2;
    v0 = g_NumNetSetupHandles;
  }
  g_NumNetSetupHandles = v0 + 1;
  dword_180025A68 = 0;
  ReleaseSRWLockExclusive(&g_NetSetupHandleCountLock);
}

```

## disassembly

```asm
0x180004260  push    rdi
0x180004262  sub     rsp, 330h
0x180004269  mov     [rsp+338h+var_318], 0FFFFFFFFFFFFFFFEh
0x180004272  mov     [rsp+338h+arg_0], rbx
0x18000427a  mov     rax, cs:__security_cookie
0x180004281  xor     rax, rsp
0x180004284  mov     [rsp+338h+var_18], rax
0x18000428c  lea     rdi, ?g_NetSetupHandleCountLock@@3VRtlSrwLock@@A; RtlSrwLock g_NetSetupHandleCountLock
0x180004293  mov     [rsp+338h+var_300], rdi
0x180004298  mov     rcx, rdi; SRWLock
0x18000429b  call    cs:__imp_AcquireSRWLockExclusive
0x1800042a1  call    cs:__imp_GetCurrentThreadId
0x1800042a7  mov     cs:dword_180025A68, eax
0x1800042ad  mov     [rsp+338h+var_308], 2
0x1800042b5  mov     eax, cs:?g_NumNetSetupHandles@@3KA; ulong g_NumNetSetupHandles
0x1800042bb  test    eax, eax
0x1800042bd  jnz     short loc_18000431D
0x1800042bf  lea     rcx, [rsp+338h+LibFileName]; Str
0x1800042c7  call    GetPathToNetSetupEngineDll
0x1800042cc  xor     r8d, r8d; dwFlags
0x1800042cf  xor     edx, edx; hFile
0x1800042d1  lea     rcx, [rsp+338h+LibFileName]; lpLibFileName
0x1800042d9  call    cs:__imp_LoadLibraryExW
0x1800042df  mov     rbx, rax
0x1800042e2  mov     [rsp+338h+var_310], rax
0x1800042e7  test    rax, rax
0x1800042ea  jz      loc_180004386
0x1800042f0  lea     rdx, ProcName; "NetSetupGetEngine"
0x1800042f7  mov     rcx, rax; hModule
0x1800042fa  call    cs:__imp_GetProcAddress
0x180004300  mov     cs:?g_NetSetupGetEnginePfn@@3P6APEAVNetSetupImplementation@@KPEAU_NETSETUP_ENVIRONMENT@@@ZEA, rax; NetSetupImplementation * (*g_NetSetupGetEnginePfn)(ulong,_NETSETUP_ENVIRONMENT *)
0x180004307  test    rax, rax
0x18000430a  jz      loc_1800043D5
0x180004310  mov     cs:?g_NetSetupEngine@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_NetSetupEngine
0x180004317  mov     eax, cs:?g_NumNetSetupHandles@@3KA; ulong g_NumNetSetupHandles
0x18000431d  inc     eax
0x18000431f  mov     cs:?g_NumNetSetupHandles@@3KA, eax; ulong g_NumNetSetupHandles
0x180004325  mov     cs:dword_180025A68, 0
0x18000432f  mov     rcx, rdi; SRWLock
0x180004332  call    cs:__imp_ReleaseSRWLockExclusive
0x180004338  mov     rcx, [rsp+338h+var_18]
0x180004340  xor     rcx, rsp; StackCookie
0x180004343  call    __security_check_cookie
0x180004348  mov     rbx, [rsp+338h+arg_0]
0x180004350  add     rsp, 330h
0x180004357  pop     rdi
0x180004358  retn
0x180004359  call    cs:__imp_GetLastError
0x18000435f  nop
0x180004360  test    eax, eax
0x180004362  jg      loc_180004410
0x180004368  mov     edx, eax; int
0x18000436a  lea     rcx, [rsp+338h+pExceptionObject]; this
0x18000436f  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180004374  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000437b  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x180004380  call    _CxxThrowException_0
0x180004386  lea     rax, WPP_GLOBAL_Control
0x18000438d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004394  cmp     rcx, rax
0x180004397  jz      short loc_1800043B4
0x180004399  cmp     byte ptr [rcx+19h], 2
0x18000439d  jb      short loc_1800043B4
0x18000439f  mov     edx, 0Eh
0x1800043a4  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x1800043ab  mov     rcx, [rcx+10h]
0x1800043af  call    WPP_SF_
0x1800043b4  mov     edx, 8007007Eh; int
0x1800043b9  lea     rcx, [rsp+338h+pExceptionObject]; this
0x1800043be  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800043c3  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800043ca  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x1800043cf  call    _CxxThrowException_0
0x1800043d5  lea     rax, WPP_GLOBAL_Control
0x1800043dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e3  cmp     rcx, rax
0x1800043e6  jz      loc_180004359
0x1800043ec  cmp     byte ptr [rcx+19h], 2
0x1800043f0  jb      loc_180004359
0x1800043f6  mov     edx, 0Fh
0x1800043fb  lea     r8, WPP_f1172f7f51b138cada6e87324e167680_Traceguids
0x180004402  mov     rcx, [rcx+10h]
0x180004406  call    WPP_SF_
0x18000440b  jmp     loc_180004359
0x180004410  movzx   eax, ax
0x180004413  or      eax, 80070000h
0x180004418  jmp     loc_180004368
```

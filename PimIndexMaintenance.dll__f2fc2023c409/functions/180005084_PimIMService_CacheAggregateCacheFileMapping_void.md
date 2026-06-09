# PimIMService::CacheAggregateCacheFileMapping(void)

- ea: `0x180005084`
- end: `0x1800051f5`
- name: `?CacheAggregateCacheFileMapping@PimIMService@@QEAAJXZ`
- size: `369`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000c970`

## callees

- `0x180002da8`
- `0x180005084`
- `0x18000b654`
- `0x18000bf5c`
- `0x18000d0e0`
- `0x180021240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000517b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000517b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000519b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000519b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051a5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005131`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180005131`
- `PIMSTORE!GetAggregateCacheGeneration` at `0x1800050ac`
- `PIMSTORE!GetAggregateCacheGeneration` at `0x1800050ac`
- `UserDataPlatformHelperUtil!RunServicesInProc` at `0x1800050dc`
- `UserDataPlatformHelperUtil!RunServicesInProc` at `0x1800050dc`

## string_xrefs

- `0x1800050be`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180005164`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800051c0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800050e2`: `AggregateCacheFileMapping`
- `0x1800050ef`: `UT_AggregateCacheFileMapping`

## pseudocode

```c
__int64 __fastcall PimIMService::CacheAggregateCacheFileMapping(PimIMService *this)
{
  int AggregateCacheGeneration; // ebx
  __int64 v2; // r9
  int v3; // ebx
  int v4; // eax
  const wchar_t *v5; // r9
  HANDLE v6; // rbx
  int v7; // eax
  signed int LastError; // eax
  int v10; // [rsp+30h] [rbp-238h] BYREF
  __int64 v11; // [rsp+38h] [rbp-230h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-228h] BYREF

  v10 = 0;
  AggregateCacheGeneration = GetAggregateCacheGeneration(&v10);
  if ( AggregateCacheGeneration < 0 )
  {
    v2 = 3396;
LABEL_3:
    Log_HREvent(
      (unsigned int)AggregateCacheGeneration,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v2);
    return (unsigned int)AggregateCacheGeneration;
  }
  v3 = v10;
  v4 = RunServicesInProc(0);
  v5 = L"UT_AggregateCacheFileMapping";
  if ( !v4 )
    v5 = L"AggregateCacheFileMapping";
  AggregateCacheGeneration = StringCchPrintfW(pszDest, 0x104u, L"%s%x", v5, v3);
  if ( AggregateCacheGeneration < 0 )
  {
    v2 = 3404;
    goto LABEL_3;
  }
  v11 = 0;
  v6 = OpenFileMappingW(4u, 0, pszDest);
  if ( v6 )
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v11);
    v7 = PimIMService::_ScheduleAggregateCacheBackup((PimIMService *)&myService, 0, 0);
    if ( v7 < 0 )
      Log_HREvent(
        (unsigned int)v7,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        3414);
    EnterCriticalSection(&stru_18002DE00);
    v11 = qword_18002DDD0;
    qword_18002DDD0 = (__int64)v6;
    LeaveCriticalSection(&stru_18002DE00);
    AggregateCacheGeneration = 0;
  }
  else
  {
    LastError = GetLastError();
    AggregateCacheGeneration = LastError;
    if ( LastError > 0 )
      AggregateCacheGeneration = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      (unsigned int)AggregateCacheGeneration,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3411);
  }
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v11);
  return (unsigned int)AggregateCacheGeneration;
}

```

## disassembly

```asm
0x180005084  push    rbx
0x180005086  sub     rsp, 260h
0x18000508d  mov     rax, cs:__security_cookie
0x180005094  xor     rax, rsp
0x180005097  mov     [rsp+268h+var_18], rax
0x18000509f  lea     rcx, [rsp+268h+var_238]
0x1800050a4  mov     [rsp+268h+var_238], 0
0x1800050ac  call    cs:__imp_GetAggregateCacheGeneration
0x1800050b2  mov     ebx, eax
0x1800050b4  test    eax, eax
0x1800050b6  jns     short loc_1800050D6
0x1800050b8  mov     r9d, 0D44h
0x1800050be  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800050c5  mov     edx, 1
0x1800050ca  mov     ecx, ebx
0x1800050cc  call    Log_HREvent
0x1800050d1  jmp     loc_1800051DA
0x1800050d6  mov     ebx, [rsp+268h+var_238]
0x1800050da  xor     ecx, ecx
0x1800050dc  call    cs:__imp_RunServicesInProc
0x1800050e2  lea     rcx, aAggregatecache; "AggregateCacheFileMapping"
0x1800050e9  mov     [rsp+268h+var_248], ebx
0x1800050ed  test    eax, eax
0x1800050ef  lea     r9, aUtAggregatecac; "UT_AggregateCacheFileMapping"
0x1800050f6  lea     r8, aSX; "%s%x"
0x1800050fd  mov     edx, 104h; cchDest
0x180005102  cmovz   r9, rcx
0x180005106  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18000510b  call    StringCchPrintfW
0x180005110  mov     ebx, eax
0x180005112  test    eax, eax
0x180005114  jns     short loc_18000511E
0x180005116  mov     r9d, 0D4Ch
0x18000511c  jmp     short loc_1800050BE
0x18000511e  xor     edx, edx; bInheritHandle
0x180005120  mov     [rsp+268h+var_230], 0
0x180005129  lea     r8, [rsp+268h+pszDest]; lpName
0x18000512e  lea     ecx, [rdx+4]; dwDesiredAccess
0x180005131  call    cs:__imp_OpenFileMappingW
0x180005137  mov     rbx, rax
0x18000513a  test    rax, rax
0x18000513d  jz      short loc_1800051A5
0x18000513f  lea     rcx, [rsp+268h+var_230]
0x180005144  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180005149  xor     r8d, r8d; int
0x18000514c  lea     rcx, ?myService@@3VPimIMService@@A; this
0x180005153  xor     edx, edx; int
0x180005155  call    ?_ScheduleAggregateCacheBackup@PimIMService@@AEAAJHH@Z; PimIMService::_ScheduleAggregateCacheBackup(int,int)
0x18000515a  test    eax, eax
0x18000515c  jns     short loc_180005174
0x18000515e  mov     r9d, 0D56h
0x180005164  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000516b  xor     edx, edx
0x18000516d  mov     ecx, eax
0x18000516f  call    Log_HREvent
0x180005174  lea     rcx, stru_18002DE00; lpCriticalSection
0x18000517b  call    cs:__imp_EnterCriticalSection
0x180005181  mov     rax, cs:qword_18002DDD0
0x180005188  lea     rcx, stru_18002DE00; lpCriticalSection
0x18000518f  mov     [rsp+268h+var_230], rax
0x180005194  mov     cs:qword_18002DDD0, rbx
0x18000519b  call    cs:__imp_LeaveCriticalSection
0x1800051a1  xor     ebx, ebx
0x1800051a3  jmp     short loc_1800051D0
0x1800051a5  call    cs:__imp_GetLastError
0x1800051ab  mov     ebx, eax
0x1800051ad  test    eax, eax
0x1800051af  jle     short loc_1800051BA
0x1800051b1  movzx   ebx, ax
0x1800051b4  or      ebx, 80070000h
0x1800051ba  mov     r9d, 0D53h
0x1800051c0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800051c7  xor     edx, edx
0x1800051c9  mov     ecx, ebx
0x1800051cb  call    Log_HREvent
0x1800051d0  lea     rcx, [rsp+268h+var_230]
0x1800051d5  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800051da  mov     eax, ebx
0x1800051dc  mov     rcx, [rsp+268h+var_18]
0x1800051e4  xor     rcx, rsp; StackCookie
0x1800051e7  call    __security_check_cookie
0x1800051ec  add     rsp, 260h
0x1800051f3  pop     rbx
0x1800051f4  retn
```

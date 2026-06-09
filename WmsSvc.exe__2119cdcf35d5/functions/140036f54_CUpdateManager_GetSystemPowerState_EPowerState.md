# CUpdateManager::GetSystemPowerState(_EPowerState *)

- ea: `0x140036f54`
- end: `0x1400371bd`
- name: `?GetSystemPowerState@CUpdateManager@@IEAAJPEAW4_EPowerState@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(CUpdateManager *__hidden this, enum _EPowerState *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140035acc`
- `0x140037d90`

## callees

- `0x140036f54`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006ea54`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x140036f98`
- `KERNEL32!GetSystemTime` at `0x140036f98`
- `KERNEL32!SystemTimeToFileTime` at `0x140036fa8`
- `KERNEL32!SystemTimeToFileTime` at `0x140037080`
- `KERNEL32!SystemTimeToFileTime` at `0x140036fa8`
- `KERNEL32!SystemTimeToFileTime` at `0x140037080`
- `KERNEL32!GetLastError` at `0x140036fb6`
- `KERNEL32!GetLastError` at `0x14003708a`
- `KERNEL32!GetLastError` at `0x140036fb6`
- `KERNEL32!GetLastError` at `0x14003708a`
- `KERNEL32!IsDebuggerPresent` at `0x14003700d`
- `KERNEL32!IsDebuggerPresent` at `0x1400370e1`
- `KERNEL32!IsDebuggerPresent` at `0x14003700d`
- `KERNEL32!IsDebuggerPresent` at `0x1400370e1`

## string_xrefs

- `0x140036fe0`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x1400370b4`: `termsrv\wms\src\devices\wmssvc\updatemanager.cpp`
- `0x140036fd9`: `CUpdateManager::GetSystemPowerState`
- `0x1400370ad`: `CUpdateManager::GetSystemPowerState`
- `0x14003713c`: `CUpdateManager::GetSystemPowerState Last power state = %s\n`
- `0x14003714a`: `CUpdateManager::GetSystemPowerState %i seconds have gone by since the last wake\n`
- `0x14003717b`: `CUpdateManager::GetSystemPowerState > 10 seconds have gone by, setting power state to %s.\n`
- `0x140037186`: `CUpdateManager::GetSystemPowerState <= 10 seconds have gone by, setting power state to %s.\n`

## pseudocode

```c
__int64 __fastcall CUpdateManager::GetSystemPowerState(CUpdateManager *this, enum _EPowerState *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // r8
  unsigned __int64 v8; // r9
  signed int v9; // eax
  unsigned __int64 v10; // rsi
  const unsigned __int16 *v11; // rax
  unsigned __int64 v12; // r9
  unsigned int v13; // edi
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rcx
  signed int v17; // [rsp+30h] [rbp-58h]
  signed int v18; // [rsp+38h] [rbp-50h]
  struct _FILETIME FileTime; // [rsp+40h] [rbp-48h] BYREF
  struct _FILETIME v20; // [rsp+48h] [rbp-40h] BYREF
  SYSTEMTIME SystemTime; // [rsp+50h] [rbp-38h] BYREF

  FileTime = 0;
  v20 = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x6ABu,
      L"CUpdateManager::GetSystemPowerState",
      L"CBRAEx",
      L"fSuccess",
      v5);
    if ( IsDebuggerPresent() )
    {
      v6 = 1707;
LABEL_8:
      v18 = v5;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
        v6,
        L"CUpdateManager::GetSystemPowerState",
        L"CBRAEx",
        L"fSuccess",
        v18);
      return (unsigned int)v5;
    }
    v7 = 1707;
    goto LABEL_10;
  }
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 324), &v20) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      0x6AEu,
      L"CUpdateManager::GetSystemPowerState",
      L"CBRAEx",
      L"fSuccess",
      v5);
    if ( IsDebuggerPresent() )
    {
      v6 = 1710;
      goto LABEL_8;
    }
    v7 = 1710;
LABEL_10:
    v17 = v5;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\updatemanager.cpp",
      v7,
      L"CUpdateManager::GetSystemPowerState",
      L"CBRAEx",
      L"fSuccess",
      v17);
    return (unsigned int)v5;
  }
  v5 = 0;
  v10 = (*(_QWORD *)&FileTime - *(_QWORD *)&v20) / 0x989680uLL;
  v11 = Utils::StringTableHelper(
          (Utils *)*((unsigned int *)this + 80),
          (unsigned int)&qword_14009C220,
          (const struct Utils::SStringMap *)4,
          v8);
  DEBUGMSG(L"CUpdateManager::GetSystemPowerState Last power state = %s\n", v11);
  DEBUGMSG(L"CUpdateManager::GetSystemPowerState %i seconds have gone by since the last wake\n", (unsigned int)v10);
  if ( v10 <= 0xA )
    v13 = *((_DWORD *)this + 80);
  else
    v13 = 3;
  v14 = Utils::StringTableHelper((Utils *)v13, (unsigned int)&qword_14009C220, (const struct Utils::SStringMap *)4, v12);
  v15 = L"CUpdateManager::GetSystemPowerState > 10 seconds have gone by, setting power state to %s.\n";
  if ( v10 <= 0xA )
    v15 = L"CUpdateManager::GetSystemPowerState <= 10 seconds have gone by, setting power state to %s.\n";
  DEBUGMSG(v15, v14);
  *(_DWORD *)a2 = v13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140036f54  mov     r11, rsp
0x140036f57  mov     [r11+18h], rbx
0x140036f5b  mov     [r11+20h], rbp
0x140036f5f  push    rsi
0x140036f60  push    rdi
0x140036f61  push    r14
0x140036f63  sub     rsp, 70h
0x140036f67  mov     rax, cs:__security_cookie
0x140036f6e  xor     rax, rsp
0x140036f71  mov     [rsp+88h+var_28], rax
0x140036f76  mov     rdi, rcx
0x140036f79  mov     qword ptr [r11-48h], 0
0x140036f81  xorps   xmm0, xmm0
0x140036f84  mov     qword ptr [r11-40h], 0
0x140036f8c  lea     rcx, [r11-38h]; lpSystemTime
0x140036f90  mov     r14, rdx
0x140036f93  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x140036f98  call    cs:__imp_GetSystemTime
0x140036f9e  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x140036fa3  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x140036fa8  call    cs:__imp_SystemTimeToFileTime
0x140036fae  test    eax, eax
0x140036fb0  jnz     loc_140037074
0x140036fb6  call    cs:__imp_GetLastError
0x140036fbc  mov     ebx, eax
0x140036fbe  test    eax, eax
0x140036fc0  jle     short loc_140036FCB
0x140036fc2  movzx   ebx, ax
0x140036fc5  or      ebx, 80070000h
0x140036fcb  mov     eax, 80004005h
0x140036fd0  lea     r14, aCbraex; "CBRAEx"
0x140036fd7  test    ebx, ebx
0x140036fd9  lea     rsi, aCupdatemanager_58; "CUpdateManager::GetSystemPowerState"
0x140036fe0  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x140036fe7  mov     r9, r14; unsigned __int16 *
0x140036fea  cmovns  ebx, eax
0x140036fed  lea     rbp, aFsuccess; "fSuccess"
0x140036ff4  mov     [rsp+88h+var_60], ebx; int
0x140036ff8  mov     r8, rsi; unsigned __int16 *
0x140036ffb  mov     edx, 6ABh; unsigned int
0x140037000  mov     [rsp+88h+var_68], rbp; unsigned __int16 *
0x140037005  mov     rcx, rdi; unsigned __int16 *
0x140037008  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003700d  call    cs:__imp_IsDebuggerPresent
0x140037013  test    eax, eax
0x140037015  jz      short loc_140037049
0x140037017  mov     r9d, 6ABh
0x14003701d  mov     [rsp+88h+var_50], ebx
0x140037021  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140037028  mov     [rsp+88h+var_58], rbp
0x14003702d  mov     r8, rdi
0x140037030  mov     qword ptr [rsp+88h+var_60], r14
0x140037035  mov     ecx, 2; unsigned __int8
0x14003703a  mov     [rsp+88h+var_68], rsi
0x14003703f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140037044  jmp     loc_140037199
0x140037049  mov     r8d, 6ABh
0x14003704f  mov     dword ptr [rsp+88h+var_58], ebx
0x140037053  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14003705a  mov     qword ptr [rsp+88h+var_60], rbp
0x14003705f  mov     r9, rsi
0x140037062  mov     rdx, rdi
0x140037065  mov     [rsp+88h+var_68], r14
0x14003706a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14003706f  jmp     loc_140037199
0x140037074  lea     rcx, [rdi+144h]; lpSystemTime
0x14003707b  lea     rdx, [rsp+88h+var_40]; lpFileTime
0x140037080  call    cs:__imp_SystemTimeToFileTime
0x140037086  test    eax, eax
0x140037088  jnz     short loc_140037101
0x14003708a  call    cs:__imp_GetLastError
0x140037090  mov     ebx, eax
0x140037092  test    eax, eax
0x140037094  jle     short loc_14003709F
0x140037096  movzx   ebx, ax
0x140037099  or      ebx, 80070000h
0x14003709f  mov     eax, 80004005h
0x1400370a4  lea     r14, aCbraex; "CBRAEx"
0x1400370ab  test    ebx, ebx
0x1400370ad  lea     rsi, aCupdatemanager_58; "CUpdateManager::GetSystemPowerState"
0x1400370b4  lea     rdi, aTermsrvWmsSrcD_7; "termsrv\\wms\\src\\devices\\wmssvc\\upd"...
0x1400370bb  mov     r9, r14; unsigned __int16 *
0x1400370be  cmovns  ebx, eax
0x1400370c1  lea     rbp, aFsuccess; "fSuccess"
0x1400370c8  mov     [rsp+88h+var_60], ebx; int
0x1400370cc  mov     r8, rsi; unsigned __int16 *
0x1400370cf  mov     edx, 6AEh; unsigned int
0x1400370d4  mov     [rsp+88h+var_68], rbp; unsigned __int16 *
0x1400370d9  mov     rcx, rdi; unsigned __int16 *
0x1400370dc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400370e1  call    cs:__imp_IsDebuggerPresent
0x1400370e7  test    eax, eax
0x1400370e9  jz      short loc_1400370F6
0x1400370eb  mov     r9d, 6AEh
0x1400370f1  jmp     loc_14003701D
0x1400370f6  mov     r8d, 6AEh
0x1400370fc  jmp     loc_14003704F
0x140037101  mov     rcx, qword ptr [rsp+88h+FileTime.dwLowDateTime]
0x140037106  mov     rax, 0D6BF94D5E57A42BDh
0x140037110  sub     rcx, qword ptr [rsp+88h+var_40.dwLowDateTime]
0x140037115  xor     ebx, ebx
0x140037117  mul     rcx
0x14003711a  mov     ecx, [rdi+140h]; this
0x140037120  lea     ebp, [rbx+4]
0x140037123  mov     rsi, rdx
0x140037126  mov     r8d, ebp; struct Utils::SStringMap *
0x140037129  lea     rdx, qword_14009C220; unsigned int
0x140037130  shr     rsi, 17h
0x140037134  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140037139  mov     rdx, rax
0x14003713c  lea     rcx, aCupdatemanager_30; "CUpdateManager::GetSystemPowerState Las"...
0x140037143  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037148  mov     edx, esi
0x14003714a  lea     rcx, aCupdatemanager_61; "CUpdateManager::GetSystemPowerState %i "...
0x140037151  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037156  cmp     rsi, 0Ah
0x14003715a  jbe     short loc_140037161
0x14003715c  lea     edi, [rbx+3]
0x14003715f  jmp     short loc_140037167
0x140037161  mov     edi, [rdi+140h]
0x140037167  mov     r8, rbp; struct Utils::SStringMap *
0x14003716a  lea     rdx, qword_14009C220; unsigned int
0x140037171  mov     ecx, edi; this
0x140037173  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140037178  mov     rdx, rax
0x14003717b  lea     rcx, aCupdatemanager_67; "CUpdateManager::GetSystemPowerState > 1"...
0x140037182  cmp     rsi, 0Ah
0x140037186  lea     rax, aCupdatemanager_47; "CUpdateManager::GetSystemPowerState <= "...
0x14003718d  cmovbe  rcx, rax; unsigned __int16 *
0x140037191  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140037196  mov     [r14], edi
0x140037199  mov     eax, ebx
0x14003719b  mov     rcx, [rsp+88h+var_28]
0x1400371a0  xor     rcx, rsp; StackCookie
0x1400371a3  call    __security_check_cookie
0x1400371a8  lea     r11, [rsp+88h+var_18]
0x1400371ad  mov     rbx, [r11+30h]
0x1400371b1  mov     rbp, [r11+38h]
0x1400371b5  mov     rsp, r11
0x1400371b8  pop     r14
0x1400371ba  pop     rdi
0x1400371bb  pop     rsi
0x1400371bc  retn
```

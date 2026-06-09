# InternalLoadDriver

- ea: `0x180002eb0`
- end: `0x18000344b`
- name: `InternalLoadDriver`
- size: `1435`
- prototype: `__int64 __fastcall(LPCWSTR lpValue, const WCHAR *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002c80`

## callees

- `0x180001cb0`
- `0x180002eb0`
- `0x180003460`
- `0x180003bd0`
- `0x18000f5d8`
- `0x1800106c0`
- `0x180012d08`
- `0x180012e1c`
- `0x180012e94`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002f3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800031c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003225`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800032ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002f3f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800031c9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003225`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800032ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002f99`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800031e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003243`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800033dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003408`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002f99`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800031e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003243`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800033dc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003408`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002f10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002f10`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800030d1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800030d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003035`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003062`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003094`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003035`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003062`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003218`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800032a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000320b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800031ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000320b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000341d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003148`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000318a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003148`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000318a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000317e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000317e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800031a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800031a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800033f2`

## pseudocode

```c
__int64 __fastcall InternalLoadDriver(LPCWSTR lpValue, const WCHAR *a2, _WORD *a3)
{
  HGLOBAL v6; // rax
  _BYTE *v7; // rax
  int i; // ecx
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rsi
  HGLOBAL v12; // rcx
  __int64 v13; // rsi
  int v14; // r14d
  WCHAR *j; // rdx
  WCHAR v16; // cx
  UINT v17; // r15d
  HMODULE Library; // r14
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  FARPROC ProcAddress; // r15
  char *v23; // rax
  HGLOBAL v24; // rcx
  char *v25; // rax
  __int64 v27; // rbx
  char *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  HGLOBAL v31; // rcx
  char LastError; // al
  WCHAR String1[128]; // [rsp+30h] [rbp-138h] BYREF

  EnterCriticalSection(&DriverListCritSec);
  if ( hInstalledDriverList )
  {
    if ( cInstalledDrivers + 1 < cInstalledDrivers )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_55;
      }
      v30 = 13;
      goto LABEL_54;
    }
    v6 = GlobalReAlloc(hInstalledDriverList, (unsigned int)(32 * (cInstalledDrivers + 1)), 0x42u);
  }
  else
  {
    v6 = GlobalAlloc(0x42u, 0x20u);
  }
  if ( !v6 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_55;
    }
    v30 = 14;
LABEL_54:
    WPP_SF_(v29[2], v30, &WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids);
LABEL_55:
    LeaveCriticalSection(&DriverListCritSec);
    return 0;
  }
  ++cInstalledDrivers;
  hInstalledDriverList = v6;
  v7 = GlobalLock(v6);
  for ( i = 0; i < cInstalledDrivers; ++i )
  {
    v9 = 32LL * i;
    if ( !*(_QWORD *)&v7[v9 + 16] && (v7[v9] & 2) == 0 )
      break;
  }
  v10 = i + 1;
  if ( i + 1 < cInstalledDrivers )
    --cInstalledDrivers;
  v11 = i;
  v12 = hInstalledDriverList;
  v13 = 32 * v11;
  *(_DWORD *)&v7[v13] |= 2u;
  GlobalUnlock(v12);
  LeaveCriticalSection(&DriverListCritSec);
  EnterCriticalSection(&DriverLoadFreeCritSec);
  if ( !a2 )
    a2 = wszDrivers;
  if ( !lpValue )
    goto LABEL_70;
  if ( !*lpValue )
    goto LABEL_70;
  v14 = 128;
  String1[0] = 0;
  if ( !(unsigned int)winmmGetPrivateProfileString(a2, lpValue, String1, 0x80u) )
    goto LABEL_70;
  String1[127] = 0;
  if ( CompareStringW(0x7Fu, 1u, String1, -1, L"wdmaud.drv", -1) == 2
    && CompareStringW(0x7Fu, 1u, String1, -1, lpValue, -1) != 2
    && CompareStringW(0x7Fu, 1u, lpValue, -1, L"midi", -1) != 2 )
  {
    goto LABEL_70;
  }
  for ( j = String1; *j; ++j )
  {
    if ( *j == 32 )
    {
      *j++ = 0;
      break;
    }
  }
  if ( a3 )
  {
    do
    {
      if ( !v14 )
        break;
      v16 = *j;
      --v14;
      *a3++ = *j++;
    }
    while ( v16 );
    *(a3 - 1) = 0;
  }
  v17 = SetErrorMode(1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids, String1);
  }
  Library = LoadLibraryExW(String1, 0, 0x1000u);
  SetErrorMode(v17);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DriverProc");
    if ( ProcAddress )
    {
      EnterCriticalSection(&DriverListCritSec);
      v23 = (char *)GlobalLock(hInstalledDriverList);
      v24 = hInstalledDriverList;
      *(_QWORD *)&v23[v13 + 24] = ProcAddress;
      *(_QWORD *)&v23[v13 + 16] = Library;
      GlobalUnlock(v24);
      LeaveCriticalSection(&DriverListCritSec);
      if ( (unsigned int)GetDrvrUsage(Library) != 1 )
      {
LABEL_38:
        LeaveCriticalSection(&DriverLoadFreeCritSec);
        goto LABEL_39;
      }
      v27 = InternalBroadcastDriverMessage(v10, 1, 0, 0);
      EnterCriticalSection(&DriverListCritSec);
      v28 = (char *)GlobalLock(hInstalledDriverList);
      if ( v27 )
      {
        if ( v28 )
        {
          *(_DWORD *)&v28[v13] |= 1u;
          GlobalUnlock(hInstalledDriverList);
        }
        LeaveCriticalSection(&DriverListCritSec);
        InternalBroadcastDriverMessage(v10, 2, 0, 0);
        goto LABEL_38;
      }
      if ( v28 )
      {
        v31 = hInstalledDriverList;
        *(_QWORD *)&v28[v13 + 24] = 0;
        *(_QWORD *)&v28[v13 + 16] = 0;
        GlobalUnlock(v31);
      }
      LeaveCriticalSection(&DriverListCritSec);
      FreeLibrary(Library);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v21, (__int64)lpValue);
      }
      FreeLibrary(Library);
    }
  }
  else
  {
LABEL_70:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids,
        (_DWORD)lpValue,
        LastError);
    }
  }
  LeaveCriticalSection(&DriverLoadFreeCritSec);
  v10 = 0;
LABEL_39:
  EnterCriticalSection(&DriverListCritSec);
  v25 = (char *)GlobalLock(hInstalledDriverList);
  if ( v25 )
  {
    *(_DWORD *)&v25[v13] &= ~2u;
    GlobalUnlock(hInstalledDriverList);
  }
  LeaveCriticalSection(&DriverListCritSec);
  return (int)v10;
}

```

## disassembly

```asm
0x180002eb0  push    rbx
0x180002eb2  push    rbp
0x180002eb3  push    r15
0x180002eb5  sub     rsp, 150h
0x180002ebc  mov     rax, cs:__security_cookie
0x180002ec3  xor     rax, rsp
0x180002ec6  mov     [rsp+168h+var_38], rax
0x180002ece  mov     rbx, rcx
0x180002ed1  mov     r15, r8
0x180002ed4  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002edb  mov     rbp, rdx
0x180002ede  call    cs:__imp_EnterCriticalSection
0x180002ee4  mov     rcx, cs:hInstalledDriverList; hMem
0x180002eeb  test    rcx, rcx
0x180002eee  jz      loc_1800030C7
0x180002ef4  mov     edx, cs:cInstalledDrivers
0x180002efa  lea     eax, [rdx+1]
0x180002efd  cmp     eax, edx
0x180002eff  jl      loc_1800032EA
0x180002f05  inc     edx
0x180002f07  mov     r8d, 42h ; 'B'; uFlags
0x180002f0d  shl     edx, 5; dwBytes
0x180002f10  call    cs:__imp_GlobalReAlloc
0x180002f16  test    rax, rax
0x180002f19  jz      loc_180003313
0x180002f1f  inc     cs:cInstalledDrivers
0x180002f25  mov     rcx, rax; hMem
0x180002f28  mov     [rsp+168h+arg_18], rsi
0x180002f30  mov     [rsp+168h+var_20], rdi
0x180002f38  mov     cs:hInstalledDriverList, rax
0x180002f3f  call    cs:__imp_GlobalLock
0x180002f45  mov     r8d, cs:cInstalledDrivers
0x180002f4c  xor     ecx, ecx
0x180002f4e  test    r8d, r8d
0x180002f51  jle     short loc_180002F6D
0x180002f53  movsxd  rdx, ecx
0x180002f56  shl     rdx, 5
0x180002f5a  cmp     qword ptr [rdx+rax+10h], 0
0x180002f60  jz      loc_1800030B8
0x180002f66  inc     ecx
0x180002f68  cmp     ecx, r8d
0x180002f6b  jl      short loc_180002F53
0x180002f6d  lea     edi, [rcx+1]
0x180002f70  cmp     edi, r8d
0x180002f73  jge     short loc_180002F7F
0x180002f75  dec     r8d
0x180002f78  mov     cs:cInstalledDrivers, r8d
0x180002f7f  movsxd  rsi, ecx
0x180002f82  mov     rcx, cs:hInstalledDriverList; hMem
0x180002f89  shl     rsi, 5
0x180002f8d  mov     [rsp+168h+var_28], r14
0x180002f95  or      dword ptr [rsi+rax], 2
0x180002f99  call    cs:__imp_GlobalUnlock
0x180002f9f  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002fa6  call    cs:__imp_LeaveCriticalSection
0x180002fac  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180002fb3  call    cs:__imp_EnterCriticalSection
0x180002fb9  test    rbp, rbp
0x180002fbc  lea     rax, wszDrivers; "DRIVERS32"
0x180002fc3  cmovz   rbp, rax
0x180002fc7  test    rbx, rbx
0x180002fca  jz      loc_1800030DC
0x180002fd0  cmp     word ptr [rbx], 0
0x180002fd4  jz      loc_1800030DC
0x180002fda  xor     eax, eax
0x180002fdc  lea     r8, [rsp+168h+String1]; pvData
0x180002fe1  mov     r14d, 80h
0x180002fe7  mov     [rsp+168h+String1], ax
0x180002fec  mov     r9d, r14d
0x180002fef  mov     rdx, rbx; lpValue
0x180002ff2  mov     rcx, rbp; lpString1
0x180002ff5  call    winmmGetPrivateProfileString
0x180002ffa  test    eax, eax
0x180002ffc  jz      loc_1800030DC
0x180003002  xor     eax, eax
0x180003004  mov     [rsp+168h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000300c  mov     [rsp+168h+var_3A], ax
0x180003014  lea     r8, [rsp+168h+String1]; lpString1
0x180003019  lea     rax, aWdmaudDrv; "wdmaud.drv"
0x180003020  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003026  mov     edx, 1; dwCmpFlags
0x18000302b  mov     [rsp+168h+lpString2], rax; lpString2
0x180003030  mov     ecx, 7Fh; Locale
0x180003035  call    cs:__imp_CompareStringW
0x18000303b  cmp     eax, 2
0x18000303e  jnz     short loc_18000309F
0x180003040  mov     [rsp+168h+cchCount2], 0FFFFFFFFh; cchCount2
0x180003048  lea     r8, [rsp+168h+String1]; lpString1
0x18000304d  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003053  mov     [rsp+168h+lpString2], rbx; lpString2
0x180003058  mov     edx, 1; dwCmpFlags
0x18000305d  mov     ecx, 7Fh; Locale
0x180003062  call    cs:__imp_CompareStringW
0x180003068  cmp     eax, 2
0x18000306b  jz      short loc_18000309F
0x18000306d  lea     rax, aMidi; "midi"
0x180003074  mov     [rsp+168h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000307c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003082  mov     [rsp+168h+lpString2], rax; lpString2
0x180003087  mov     r8, rbx; lpString1
0x18000308a  mov     edx, 1; dwCmpFlags
0x18000308f  mov     ecx, 7Fh; Locale
0x180003094  call    cs:__imp_CompareStringW
0x18000309a  cmp     eax, 2
0x18000309d  jnz     short loc_1800030DC
0x18000309f  lea     rdx, [rsp+168h+String1]
0x1800030a4  movzx   eax, word ptr [rdx]
0x1800030a7  test    ax, ax
0x1800030aa  jz      short loc_180003119
0x1800030ac  cmp     ax, 20h ; ' '
0x1800030b0  jz      short loc_180003110
0x1800030b2  add     rdx, 2
0x1800030b6  jmp     short loc_1800030A4
0x1800030b8  test    byte ptr [rdx+rax], 2
0x1800030bc  jz      loc_180002F6D
0x1800030c2  jmp     loc_180002F66
0x1800030c7  mov     edx, 20h ; ' '; dwBytes
0x1800030cc  mov     ecx, 42h ; 'B'; uFlags
0x1800030d1  call    cs:__imp_GlobalAlloc
0x1800030d7  jmp     loc_180002F16
0x1800030dc  lea     rbp, WPP_GLOBAL_Control
0x1800030e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800030ea  cmp     rax, rbp
0x1800030ed  jz      short loc_1800030FC
0x1800030ef  test    dword ptr [rax+1Ch], 400000h
0x1800030f6  jnz     loc_180003413
0x1800030fc  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180003103  call    cs:__imp_LeaveCriticalSection
0x180003109  xor     edi, edi
0x18000310b  jmp     loc_180003211
0x180003110  xor     eax, eax
0x180003112  mov     [rdx], ax
0x180003115  add     rdx, 2
0x180003119  test    r15, r15
0x18000311c  jz      short loc_180003143
0x18000311e  test    r14d, r14d
0x180003121  jz      short loc_18000313C
0x180003123  movzx   ecx, word ptr [rdx]
0x180003126  dec     r14d
0x180003129  mov     [r15], cx
0x18000312d  add     rdx, 2
0x180003131  add     r15, 2
0x180003135  xor     eax, eax
0x180003137  cmp     ax, cx
0x18000313a  jnz     short loc_18000311E
0x18000313c  xor     eax, eax
0x18000313e  mov     [r15-2], ax
0x180003143  mov     ecx, 1; uMode
0x180003148  call    cs:__imp_SetErrorMode
0x18000314e  mov     r15d, eax
0x180003151  mov     rcx, cs:WPP_GLOBAL_Control
0x180003158  lea     rbp, WPP_GLOBAL_Control
0x18000315f  cmp     rcx, rbp
0x180003162  jz      short loc_180003171
0x180003164  test    dword ptr [rcx+1Ch], 400000h
0x18000316b  jnz     loc_18000335E
0x180003171  xor     edx, edx; hFile
0x180003173  lea     rcx, [rsp+168h+String1]; lpLibFileName
0x180003178  mov     r8d, 1000h; dwFlags
0x18000317e  call    cs:__imp_LoadLibraryExW
0x180003184  mov     ecx, r15d; uMode
0x180003187  mov     r14, rax
0x18000318a  call    cs:__imp_SetErrorMode
0x180003190  test    r14, r14
0x180003193  jz      loc_1800030E3
0x180003199  lea     rdx, ProcName; "DriverProc"
0x1800031a0  mov     rcx, r14; hModule
0x1800031a3  call    cs:__imp_GetProcAddress
0x1800031a9  mov     r15, rax
0x1800031ac  test    rax, rax
0x1800031af  jz      loc_180003387
0x1800031b5  lea     rcx, DriverListCritSec; lpCriticalSection
0x1800031bc  call    cs:__imp_EnterCriticalSection
0x1800031c2  mov     rcx, cs:hInstalledDriverList; hMem
0x1800031c9  call    cs:__imp_GlobalLock
0x1800031cf  mov     rcx, cs:hInstalledDriverList; hMem
0x1800031d6  mov     [rsi+rax+18h], r15
0x1800031db  mov     [rsi+rax+10h], r14
0x1800031e0  call    cs:__imp_GlobalUnlock
0x1800031e6  lea     rcx, DriverListCritSec; lpCriticalSection
0x1800031ed  call    cs:__imp_LeaveCriticalSection
0x1800031f3  mov     rcx, r14
0x1800031f6  call    GetDrvrUsage
0x1800031fb  cmp     eax, 1
0x1800031fe  jz      loc_180003285
0x180003204  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x18000320b  call    cs:__imp_LeaveCriticalSection
0x180003211  lea     rcx, DriverListCritSec; lpCriticalSection
0x180003218  call    cs:__imp_EnterCriticalSection
0x18000321e  mov     rcx, cs:hInstalledDriverList; hMem
0x180003225  call    cs:__imp_GlobalLock
0x18000322b  mov     r14, [rsp+168h+var_28]
0x180003233  test    rax, rax
0x180003236  jz      short loc_180003249
0x180003238  and     dword ptr [rsi+rax], 0FFFFFFFDh
0x18000323c  mov     rcx, cs:hInstalledDriverList; hMem
0x180003243  call    cs:__imp_GlobalUnlock
0x180003249  lea     rcx, DriverListCritSec; lpCriticalSection
0x180003250  call    cs:__imp_LeaveCriticalSection
0x180003256  mov     rsi, [rsp+168h+arg_18]
0x18000325e  movsxd  rax, edi
0x180003261  mov     rdi, [rsp+168h+var_20]
0x180003269  mov     rcx, [rsp+168h+var_38]
0x180003271  xor     rcx, rsp; StackCookie
0x180003274  call    __security_check_cookie
0x180003279  add     rsp, 150h
0x180003280  pop     r15
0x180003282  pop     rbp
0x180003283  pop     rbx
0x180003284  retn
0x180003285  xor     r9d, r9d
0x180003288  xor     r8d, r8d
0x18000328b  mov     edx, 1
0x180003290  mov     ecx, edi
0x180003292  call    InternalBroadcastDriverMessage
0x180003297  lea     rcx, DriverListCritSec; lpCriticalSection
0x18000329e  mov     rbx, rax
0x1800032a1  call    cs:__imp_EnterCriticalSection
0x1800032a7  mov     rcx, cs:hInstalledDriverList; hMem
0x1800032ae  call    cs:__imp_GlobalLock
0x1800032b4  test    rbx, rbx
0x1800032b7  jz      loc_1800033BE
0x1800032bd  test    rax, rax
0x1800032c0  jnz     loc_1800033FD
0x1800032c6  lea     rcx, DriverListCritSec; lpCriticalSection
0x1800032cd  call    cs:__imp_LeaveCriticalSection
0x1800032d3  xor     r9d, r9d
0x1800032d6  xor     r8d, r8d
0x1800032d9  mov     edx, 2
0x1800032de  mov     ecx, edi
0x1800032e0  call    InternalBroadcastDriverMessage
0x1800032e5  jmp     loc_180003204
0x1800032ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032f1  lea     rbp, WPP_GLOBAL_Control
0x1800032f8  cmp     rcx, rbp
0x1800032fb  jz      short loc_18000334A
0x1800032fd  test    dword ptr [rcx+1Ch], 400000h
0x180003304  jz      short loc_18000334A
0x180003306  cmp     byte ptr [rcx+19h], 1
0x18000330a  jb      short loc_18000334A
0x18000330c  mov     edx, 0Dh
0x180003311  jmp     short loc_18000333A
0x180003313  mov     rcx, cs:WPP_GLOBAL_Control
0x18000331a  lea     rbp, WPP_GLOBAL_Control
0x180003321  cmp     rcx, rbp
0x180003324  jz      short loc_18000334A
0x180003326  test    dword ptr [rcx+1Ch], 400000h
0x18000332d  jz      short loc_18000334A
0x18000332f  cmp     byte ptr [rcx+19h], 1
0x180003333  jb      short loc_18000334A
0x180003335  mov     edx, 0Eh
0x18000333a  mov     rcx, [rcx+10h]
0x18000333e  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x180003345  call    WPP_SF_
0x18000334a  lea     rcx, DriverListCritSec; lpCriticalSection
0x180003351  call    cs:__imp_LeaveCriticalSection
0x180003357  xor     eax, eax
0x180003359  jmp     loc_180003269
0x18000335e  cmp     byte ptr [rcx+19h], 4
0x180003362  jb      loc_180003171
0x180003368  mov     rcx, [rcx+10h]
0x18000336c  lea     r9, [rsp+168h+String1]
0x180003371  mov     edx, 11h
0x180003376  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x18000337d  call    WPP_SF_S
0x180003382  jmp     loc_180003171
0x180003387  mov     rcx, cs:WPP_GLOBAL_Control
0x18000338e  cmp     rcx, rbp
0x180003391  jz      short loc_1800033B0
0x180003393  test    dword ptr [rcx+1Ch], 400000h
0x18000339a  jz      short loc_1800033B0
0x18000339c  cmp     byte ptr [rcx+19h], 1
0x1800033a0  jb      short loc_1800033B0
0x1800033a2  mov     rcx, [rcx+10h]
0x1800033a6  mov     [rsp+168h+lpString2], rbx
0x1800033ab  call    WPP_SF_sS
0x1800033b0  mov     rcx, r14; hLibModule
0x1800033b3  call    cs:__imp_FreeLibrary
0x1800033b9  jmp     loc_1800030FC
0x1800033be  test    rax, rax
0x1800033c1  jz      short loc_1800033E2
0x1800033c3  mov     rcx, cs:hInstalledDriverList; hMem
0x1800033ca  mov     qword ptr [rsi+rax+18h], 0
0x1800033d3  mov     qword ptr [rsi+rax+10h], 0
0x1800033dc  call    cs:__imp_GlobalUnlock
0x1800033e2  lea     rcx, DriverListCritSec; lpCriticalSection
0x1800033e9  call    cs:__imp_LeaveCriticalSection
0x1800033ef  mov     rcx, r14; hLibModule
0x1800033f2  call    cs:__imp_FreeLibrary
0x1800033f8  jmp     loc_1800030FC
0x1800033fd  or      dword ptr [rsi+rax], 1
0x180003401  mov     rcx, cs:hInstalledDriverList; hMem
0x180003408  call    cs:__imp_GlobalUnlock
0x18000340e  jmp     loc_1800032C6
0x180003413  cmp     byte ptr [rax+19h], 1
0x180003417  jb      loc_1800030FC
0x18000341d  call    cs:__imp_GetLastError
0x180003423  mov     rcx, cs:WPP_GLOBAL_Control
0x18000342a  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x180003431  mov     edx, 0Fh
  ... truncated ...
```

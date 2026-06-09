# InternalOpenDriver

- ea: `0x180002c80`
- end: `0x180002e9d`
- name: `InternalOpenDriver`
- size: `541`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800027d8`
- `0x18000296c`
- `0x180002bf0`

## callees

- `0x180002a20`
- `0x180002c80`
- `0x180002eb0`
- `0x1800106c0`
- `0x180012d30`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002cca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002d3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002ddb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002cca`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002d3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002ddb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002cea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002d82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002df9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e41`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002cea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002d82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002df9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002e41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002dce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002dce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e4e`

## pseudocode

```c
__int64 __fastcall InternalOpenDriver(const WCHAR *a1, const WCHAR *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v5; // rbp
  _QWORD *v6; // rax
  char *v7; // rax
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, _WORD *, __int64); // rsi
  __int64 v11; // rdi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  HGLOBAL v14; // rcx
  _WORD v15[128]; // [rsp+30h] [rbp-138h] BYREF

  result = InternalLoadDriver(a1, a2, v15);
  v5 = result;
  if ( result )
  {
    EnterCriticalSection(&DriverListCritSec);
    v6 = GlobalLock(hInstalledDriverList);
    if ( v6 )
    {
      v6[4 * v5 - 3] = (unsigned int)v5;
      GlobalUnlock(hInstalledDriverList);
    }
    LeaveCriticalSection(&DriverListCritSec);
    EnterCriticalSection(&DriverListCritSec);
    if ( hInstalledDriverList
      && (int)v5 <= cInstalledDrivers
      && (_DWORD)v5
      && (v7 = (char *)GlobalLock(hInstalledDriverList)) != 0 )
    {
      v8 = v5 - 1;
      do
      {
        if ( v8 == (_DWORD)v5 )
        {
          GlobalUnlock(hInstalledDriverList);
          goto LABEL_16;
        }
        v9 = 32LL * v8++;
      }
      while ( !*(_QWORD *)&v7[v9 + 16] );
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _WORD *, __int64))&v7[v9 + 24];
      v11 = *(_QWORD *)&v7[v9 + 8];
      GlobalUnlock(hInstalledDriverList);
      LeaveCriticalSection(&DriverListCritSec);
      v12 = v10(v11, v8, 3, v15, a3);
      if ( !v12 )
        goto LABEL_17;
      EnterCriticalSection(&DriverListCritSec);
      v13 = GlobalLock(hInstalledDriverList);
      if ( v13 )
      {
        v14 = hInstalledDriverList;
        v13[4 * v5 - 3] = v12;
        GlobalUnlock(v14);
      }
      LeaveCriticalSection(&DriverListCritSec);
      return v5;
    }
    else
    {
LABEL_16:
      LeaveCriticalSection(&DriverListCritSec);
LABEL_17:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids, 0);
      }
      InternalFreeDriver((unsigned int)v5);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002c80  push    rbp
0x180002c82  push    r14
0x180002c84  sub     rsp, 158h
0x180002c8b  mov     rax, cs:__security_cookie
0x180002c92  xor     rax, rsp
0x180002c95  mov     [rsp+168h+var_38], rax
0x180002c9d  mov     r14, r8
0x180002ca0  lea     r8, [rsp+168h+var_138]
0x180002ca5  call    InternalLoadDriver
0x180002caa  mov     rbp, rax
0x180002cad  test    rax, rax
0x180002cb0  jz      loc_180002E72
0x180002cb6  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002cbd  call    cs:__imp_EnterCriticalSection
0x180002cc3  mov     rcx, cs:hInstalledDriverList; hMem
0x180002cca  call    cs:__imp_GlobalLock
0x180002cd0  test    rax, rax
0x180002cd3  jz      short loc_180002CF0
0x180002cd5  mov     edx, ebp
0x180002cd7  mov     rcx, rbp
0x180002cda  shl     rcx, 5
0x180002cde  mov     [rcx+rax-18h], rdx
0x180002ce3  mov     rcx, cs:hInstalledDriverList; hMem
0x180002cea  call    cs:__imp_GlobalUnlock
0x180002cf0  mov     [rsp+168h+var_18], rbx
0x180002cf8  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002cff  mov     [rsp+168h+var_28], rdi
0x180002d07  call    cs:__imp_LeaveCriticalSection
0x180002d0d  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002d14  call    cs:__imp_EnterCriticalSection
0x180002d1a  mov     rcx, cs:hInstalledDriverList; hMem
0x180002d21  test    rcx, rcx
0x180002d24  jz      loc_180002E47
0x180002d2a  cmp     ebp, cs:cInstalledDrivers
0x180002d30  jg      loc_180002E47
0x180002d36  test    ebp, ebp
0x180002d38  jz      loc_180002E47
0x180002d3e  call    cs:__imp_GlobalLock
0x180002d44  test    rax, rax
0x180002d47  jz      loc_180002E47
0x180002d4d  lea     ebx, [rbp-1]
0x180002d50  cmp     ebx, ebp
0x180002d52  jz      loc_180002E3A
0x180002d58  movsxd  rdi, ebx
0x180002d5b  shl     rdi, 5
0x180002d5f  inc     ebx
0x180002d61  cmp     qword ptr [rdi+rax+10h], 0
0x180002d67  jz      short loc_180002D50
0x180002d69  mov     rcx, cs:hInstalledDriverList; hMem
0x180002d70  mov     [rsp+168h+var_20], rsi
0x180002d78  mov     rsi, [rdi+rax+18h]
0x180002d7d  mov     rdi, [rdi+rax+8]
0x180002d82  call    cs:__imp_GlobalUnlock
0x180002d88  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002d8f  call    cs:__imp_LeaveCriticalSection
0x180002d95  movsxd  rdx, ebx
0x180002d98  lea     r9, [rsp+168h+var_138]
0x180002d9d  mov     r8d, 3
0x180002da3  mov     [rsp+168h+var_148], r14
0x180002da8  mov     rcx, rdi
0x180002dab  mov     rax, rsi
0x180002dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db3  mov     rsi, [rsp+168h+var_20]
0x180002dbb  mov     rbx, rax
0x180002dbe  test    rax, rax
0x180002dc1  jz      loc_180002E54
0x180002dc7  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002dce  call    cs:__imp_EnterCriticalSection
0x180002dd4  mov     rcx, cs:hInstalledDriverList; hMem
0x180002ddb  call    cs:__imp_GlobalLock
0x180002de1  test    rax, rax
0x180002de4  jz      short loc_180002DFF
0x180002de6  mov     rcx, cs:hInstalledDriverList; hMem
0x180002ded  mov     rdx, rbp
0x180002df0  shl     rdx, 5
0x180002df4  mov     [rdx+rax-18h], rbx
0x180002df9  call    cs:__imp_GlobalUnlock
0x180002dff  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002e06  call    cs:__imp_LeaveCriticalSection
0x180002e0c  mov     rax, rbp
0x180002e0f  mov     rbx, [rsp+168h+var_18]
0x180002e17  mov     rdi, [rsp+168h+var_28]
0x180002e1f  mov     rcx, [rsp+168h+var_38]
0x180002e27  xor     rcx, rsp; StackCookie
0x180002e2a  call    __security_check_cookie
0x180002e2f  add     rsp, 158h
0x180002e36  pop     r14
0x180002e38  pop     rbp
0x180002e39  retn
0x180002e3a  mov     rcx, cs:hInstalledDriverList; hMem
0x180002e41  call    cs:__imp_GlobalUnlock
0x180002e47  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002e4e  call    cs:__imp_LeaveCriticalSection
0x180002e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e5b  lea     rax, WPP_GLOBAL_Control
0x180002e62  cmp     rcx, rax
0x180002e65  jnz     short loc_180002E74
0x180002e67  mov     ecx, ebp
0x180002e69  call    InternalFreeDriver
0x180002e6e  xor     eax, eax
0x180002e70  jmp     short loc_180002E0F
0x180002e72  jmp     short loc_180002E1F
0x180002e74  test    dword ptr [rcx+1Ch], 400000h
0x180002e7b  jz      short loc_180002E67
0x180002e7d  cmp     byte ptr [rcx+19h], 1
0x180002e81  jb      short loc_180002E67
0x180002e83  mov     rcx, [rcx+10h]
0x180002e87  lea     r8, WPP_373fbcb0dce73d0ae16fa0096022dd77_Traceguids
0x180002e8e  mov     edx, 0Ch
0x180002e93  xor     r9d, r9d
0x180002e96  call    WPP_SF_P
0x180002e9b  jmp     short loc_180002E67
```

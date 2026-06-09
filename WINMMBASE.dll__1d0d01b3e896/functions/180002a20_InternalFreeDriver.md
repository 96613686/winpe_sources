# InternalFreeDriver

- ea: `0x180002a20`
- end: `0x180002be4`
- name: `InternalFreeDriver`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800011e4`
- `0x180001564`
- `0x180001c30`
- `0x180001f30`
- `0x1800027d8`
- `0x180002c80`

## callees

- `0x180001cb0`
- `0x180002a20`
- `0x180003bd0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002a5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002ae6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002a5d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002ae6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002b4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002bbd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002aa3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002b4d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002bbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002bd7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002acc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002acc`

## pseudocode

```c
__int64 __fastcall InternalFreeDriver(unsigned int a1)
{
  char *v2; // rax
  int v3; // ecx
  HMODULE v4; // rdi
  __int64 v5; // rcx
  int DrvrUsage; // esi
  char *v7; // rax
  char *v8; // rdx
  char *v10; // r8
  HGLOBAL v11; // rcx
  int i; // ecx
  __int64 v13; // r9
  int v14; // eax

  EnterCriticalSection(&DriverLoadFreeCritSec);
  EnterCriticalSection(&DriverListCritSec);
  if ( !a1 || (int)a1 > cInstalledDrivers )
    goto LABEL_20;
  v2 = (char *)GlobalLock(hInstalledDriverList);
  v3 = a1 - 1;
  if ( (int)(a1 - 1) < 0 || v3 > cInstalledDrivers )
  {
    GlobalUnlock(hInstalledDriverList);
LABEL_20:
    LeaveCriticalSection(&DriverListCritSec);
    LeaveCriticalSection(&DriverLoadFreeCritSec);
    return 0;
  }
  v4 = 0;
  if ( v2 )
  {
    v5 = 32LL * v3;
    *(_QWORD *)&v2[v5 + 8] = 0;
    v4 = *(HMODULE *)&v2[v5 + 16];
    GlobalUnlock(hInstalledDriverList);
  }
  LeaveCriticalSection(&DriverListCritSec);
  DrvrUsage = GetDrvrUsage(v4);
  if ( DrvrUsage == 1 )
  {
    InternalBroadcastDriverMessage(a1, 5, 0, 0);
    InternalBroadcastDriverMessage(a1, 6, 0, 0);
  }
  FreeLibrary(v4);
  EnterCriticalSection(&DriverListCritSec);
  v7 = (char *)GlobalLock(hInstalledDriverList);
  v8 = v7;
  if ( v7 )
  {
    v10 = &v7[32 * a1 - 32];
    if ( (*v10 & 1) != 0 )
    {
      for ( i = 0; i < cInstalledDrivers; ++i )
      {
        v13 = 32LL * i;
        if ( *(_QWORD *)&v8[v13 + 16] == *((_QWORD *)v10 + 2) )
        {
          v14 = *(_DWORD *)&v8[v13];
          if ( (v14 & 1) == 0 )
          {
            *(_DWORD *)&v8[v13] = v14 | 1;
            break;
          }
        }
      }
    }
    *(_DWORD *)v10 &= ~1u;
    v11 = hInstalledDriverList;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    GlobalUnlock(v11);
  }
  LeaveCriticalSection(&DriverListCritSec);
  LeaveCriticalSection(&DriverLoadFreeCritSec);
  return (unsigned int)(DrvrUsage - 1);
}

```

## disassembly

```asm
0x180002a20  push    rbx
0x180002a22  sub     rsp, 30h
0x180002a26  mov     ebx, ecx
0x180002a28  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180002a2f  call    cs:__imp_EnterCriticalSection
0x180002a35  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002a3c  call    cs:__imp_EnterCriticalSection
0x180002a42  test    ebx, ebx
0x180002a44  jz      loc_180002BC3
0x180002a4a  cmp     ebx, cs:cInstalledDrivers
0x180002a50  jg      loc_180002BC3
0x180002a56  mov     rcx, cs:hInstalledDriverList; hMem
0x180002a5d  call    cs:__imp_GlobalLock
0x180002a63  lea     ecx, [rbx-1]
0x180002a66  test    ecx, ecx
0x180002a68  js      loc_180002BB6
0x180002a6e  cmp     ecx, cs:cInstalledDrivers
0x180002a74  jg      loc_180002BB6
0x180002a7a  mov     [rsp+38h+arg_0], rsi
0x180002a7f  mov     [rsp+38h+arg_8], rdi
0x180002a84  xor     edi, edi
0x180002a86  test    rax, rax
0x180002a89  jz      short loc_180002AA9
0x180002a8b  movsxd  rcx, ecx
0x180002a8e  shl     rcx, 5
0x180002a92  mov     [rcx+rax+8], rdi
0x180002a97  mov     rdi, [rcx+rax+10h]
0x180002a9c  mov     rcx, cs:hInstalledDriverList; hMem
0x180002aa3  call    cs:__imp_GlobalUnlock
0x180002aa9  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002ab0  call    cs:__imp_LeaveCriticalSection
0x180002ab6  mov     rcx, rdi
0x180002ab9  call    GetDrvrUsage
0x180002abe  mov     esi, eax
0x180002ac0  cmp     eax, 1
0x180002ac3  jz      loc_180002B55
0x180002ac9  mov     rcx, rdi; hLibModule
0x180002acc  call    cs:__imp_FreeLibrary
0x180002ad2  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002ad9  call    cs:__imp_EnterCriticalSection
0x180002adf  mov     rcx, cs:hInstalledDriverList; hMem
0x180002ae6  call    cs:__imp_GlobalLock
0x180002aec  mov     rdi, [rsp+38h+arg_8]
0x180002af1  mov     rdx, rax
0x180002af4  test    rax, rax
0x180002af7  jnz     short loc_180002B21
0x180002af9  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002b00  call    cs:__imp_LeaveCriticalSection
0x180002b06  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180002b0d  call    cs:__imp_LeaveCriticalSection
0x180002b13  lea     eax, [rsi-1]
0x180002b16  mov     rsi, [rsp+38h+arg_0]
0x180002b1b  add     rsp, 30h
0x180002b1f  pop     rbx
0x180002b20  retn
0x180002b21  lea     r8d, [rbx-1]
0x180002b25  shl     r8, 5
0x180002b29  add     r8, rdx
0x180002b2c  test    byte ptr [r8], 1
0x180002b30  jnz     short loc_180002B7E
0x180002b32  and     dword ptr [r8], 0FFFFFFFEh
0x180002b36  mov     rcx, cs:hInstalledDriverList; hMem
0x180002b3d  mov     qword ptr [r8+10h], 0
0x180002b45  mov     qword ptr [r8+18h], 0
0x180002b4d  call    cs:__imp_GlobalUnlock
0x180002b53  jmp     short loc_180002AF9
0x180002b55  xor     r9d, r9d
0x180002b58  xor     r8d, r8d
0x180002b5b  mov     edx, 5
0x180002b60  mov     ecx, ebx
0x180002b62  call    InternalBroadcastDriverMessage
0x180002b67  xor     r9d, r9d
0x180002b6a  xor     r8d, r8d
0x180002b6d  mov     edx, 6
0x180002b72  mov     ecx, ebx
0x180002b74  call    InternalBroadcastDriverMessage
0x180002b79  jmp     loc_180002AC9
0x180002b7e  mov     r10d, cs:cInstalledDrivers
0x180002b85  xor     ecx, ecx
0x180002b87  cmp     ecx, r10d
0x180002b8a  jge     short loc_180002B32
0x180002b8c  mov     rax, [r8+10h]
0x180002b90  movsxd  r9, ecx
0x180002b93  shl     r9, 5
0x180002b97  cmp     [r9+rdx+10h], rax
0x180002b9c  jnz     short loc_180002BA6
0x180002b9e  mov     eax, [r9+rdx]
0x180002ba2  test    al, 1
0x180002ba4  jz      short loc_180002BAA
0x180002ba6  inc     ecx
0x180002ba8  jmp     short loc_180002B87
0x180002baa  or      eax, 1
0x180002bad  mov     [r9+rdx], eax
0x180002bb1  jmp     loc_180002B32
0x180002bb6  mov     rcx, cs:hInstalledDriverList; hMem
0x180002bbd  call    cs:__imp_GlobalUnlock
0x180002bc3  lea     rcx, DriverListCritSec; lpCriticalSection
0x180002bca  call    cs:__imp_LeaveCriticalSection
0x180002bd0  lea     rcx, DriverLoadFreeCritSec; lpCriticalSection
0x180002bd7  call    cs:__imp_LeaveCriticalSection
0x180002bdd  xor     eax, eax
0x180002bdf  jmp     loc_180002B1B
```

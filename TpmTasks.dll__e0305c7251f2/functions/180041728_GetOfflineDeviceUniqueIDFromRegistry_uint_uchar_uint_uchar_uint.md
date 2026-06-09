# GetOfflineDeviceUniqueIDFromRegistry(uint,uchar *,uint *,uchar *,uint *)

- ea: `0x180041728`
- end: `0x18004190c`
- name: `?GetOfflineDeviceUniqueIDFromRegistry@@YAJIPEAEPEAI01@Z`
- size: `484`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180040efc`

## callees

- `0x1800078b0`
- `0x18004128c`
- `0x18004141c`
- `0x180041728`
- `0x180041a38`
- `0x180041f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041851`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180041851`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800417ea`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800417ea`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800417c3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800417c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041819`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004182b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004182b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004185a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004185a`

## string_xrefs

- `0x1800417b8`: `OFFLINEDEVICEID-CREATERANDOMSEED`
- `0x1800417dc`: `OFFLINEDEVICEID-CREATERANDOMSEED`

## pseudocode

```c
__int64 __fastcall GetOfflineDeviceUniqueIDFromRegistry(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  bool v4; // cf
  signed int RandomSeed; // ebx
  int RandomSeedFromRegistry; // eax
  unsigned __int8 *v9; // rdx
  unsigned int v10; // ecx
  HANDLE MutexW; // rdi
  signed int LastError; // eax
  DWORD v13; // eax
  unsigned int v14; // edx
  signed int v15; // eax
  int v17; // eax
  unsigned int v18; // edx
  __int128 v19; // xmm1
  unsigned int v20; // [rsp+30h] [rbp-50h] BYREF
  UCHAR pbBuffer[16]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v22; // [rsp+48h] [rbp-38h]
  unsigned __int8 v23[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h]

  v4 = *a3 < 0x20;
  v20 = 32;
  *(_OWORD *)pbBuffer = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  if ( v4 )
  {
    *a3 = 32;
    return (unsigned int)-2147024774;
  }
  RandomSeedFromRegistry = GetRandomSeedFromRegistry(pbBuffer, (unsigned int)a2);
  RandomSeed = RandomSeedFromRegistry;
  if ( RandomSeedFromRegistry >= 0 )
  {
    MutexW = 0;
    goto LABEL_27;
  }
  if ( (RandomSeedFromRegistry & 0x1FFF0000) == 0x70000 && (_WORD)RandomSeedFromRegistry == 2 )
  {
    MutexW = CreateMutexW(0, 0, L"OFFLINEDEVICEID-CREATERANDOMSEED");
    if ( MutexW )
      goto LABEL_13;
    if ( GetLastError() == 5 )
    {
      MutexW = OpenMutexW(0x100000u, 0, L"OFFLINEDEVICEID-CREATERANDOMSEED");
      if ( MutexW )
        goto LABEL_13;
    }
    LastError = GetLastError();
    RandomSeed = LastError;
    if ( LastError > 0 )
      RandomSeed = (unsigned __int16)LastError | 0x80070000;
    if ( RandomSeed >= 0 )
    {
LABEL_13:
      v13 = WaitForSingleObject(MutexW, 0x2710u);
      if ( v13 != 258 )
      {
        if ( v13 != -1 )
        {
          v17 = GetRandomSeedFromRegistry(pbBuffer, v14);
          RandomSeed = v17;
          if ( v17 >= 0
            || (v17 & 0x1FFF0000) == 0x70000
            && (_WORD)v17 == 2
            && (RandomSeed = GenerateRandomSeed(pbBuffer, (unsigned int)v9), RandomSeed >= 0)
            && (RandomSeed = StoreRandomSeedInRegistry(pbBuffer, v18), RandomSeed >= 0) )
          {
LABEL_27:
            RandomSeed = GenerateOfflineDeviceID(v10, v9, 0x20u, pbBuffer, v23, &v20);
            if ( RandomSeed >= 0 )
            {
              v19 = v24;
              *(_OWORD *)a4 = *(_OWORD *)v23;
              *((_OWORD *)a4 + 1) = v19;
              *a3 = 32;
            }
          }
LABEL_19:
          if ( MutexW )
          {
            ReleaseMutex(MutexW);
            CloseHandle(MutexW);
          }
          return (unsigned int)RandomSeed;
        }
        v15 = GetLastError();
        RandomSeed = v15;
        if ( v15 > 0 )
          RandomSeed = (unsigned __int16)v15 | 0x80070000;
        if ( RandomSeed < 0 )
          goto LABEL_19;
      }
      RandomSeed = -2147023436;
      goto LABEL_19;
    }
  }
  return (unsigned int)RandomSeed;
}

```

## disassembly

```asm
0x180041728  mov     [rsp-18h+arg_0], rbx
0x18004172d  mov     [rsp-18h+arg_8], rsi
0x180041732  push    rbp
0x180041733  push    rdi
0x180041734  push    r14
0x180041736  mov     rbp, rsp
0x180041739  sub     rsp, 80h
0x180041740  mov     rax, cs:__security_cookie
0x180041747  xor     rax, rsp
0x18004174a  mov     [rbp+var_8], rax
0x18004174e  cmp     dword ptr [r8], 20h ; ' '
0x180041752  xorps   xmm0, xmm0
0x180041755  xorps   xmm1, xmm1
0x180041758  mov     [rbp+var_50], 20h ; ' '
0x18004175f  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x180041763  mov     r14, r9
0x180041766  mov     rsi, r8
0x180041769  movups  [rbp+var_38], xmm0
0x18004176d  movups  xmmword ptr [rbp+var_28], xmm1
0x180041771  movups  [rbp+var_18], xmm1
0x180041775  jnb     short loc_180041788
0x180041777  mov     dword ptr [r8], 20h ; ' '
0x18004177e  mov     ebx, 8007007Ah
0x180041783  jmp     loc_180041860
0x180041788  lea     rcx, [rbp+pbBuffer]; lpData
0x18004178c  call    ?GetRandomSeedFromRegistry@@YAJPEAEI@Z; GetRandomSeedFromRegistry(uchar *,uint)
0x180041791  mov     ebx, eax
0x180041793  test    eax, eax
0x180041795  js      short loc_18004179E
0x180041797  xor     edi, edi
0x180041799  jmp     loc_1800418C5
0x18004179e  and     eax, 1FFF0000h
0x1800417a3  cmp     eax, 70000h
0x1800417a8  jnz     loc_180041860
0x1800417ae  cmp     bx, 2
0x1800417b2  jnz     loc_180041860
0x1800417b8  lea     r8, aOfflinedevicei; "OFFLINEDEVICEID-CREATERANDOMSEED"
0x1800417bf  xor     edx, edx; bInitialOwner
0x1800417c1  xor     ecx, ecx; lpMutexAttributes
0x1800417c3  call    cs:__imp_CreateMutexW
0x1800417c9  mov     rdi, rax
0x1800417cc  test    rax, rax
0x1800417cf  jnz     short loc_180041811
0x1800417d1  call    cs:__imp_GetLastError
0x1800417d7  cmp     eax, 5
0x1800417da  jnz     short loc_1800417F8
0x1800417dc  lea     r8, aOfflinedevicei; "OFFLINEDEVICEID-CREATERANDOMSEED"
0x1800417e3  xor     edx, edx; bInheritHandle
0x1800417e5  mov     ecx, 100000h; dwDesiredAccess
0x1800417ea  call    cs:__imp_OpenMutexW
0x1800417f0  mov     rdi, rax
0x1800417f3  test    rax, rax
0x1800417f6  jnz     short loc_180041811
0x1800417f8  call    cs:__imp_GetLastError
0x1800417fe  mov     ebx, eax
0x180041800  test    eax, eax
0x180041802  jle     short loc_18004180D
0x180041804  movzx   ebx, ax
0x180041807  or      ebx, 80070000h
0x18004180d  test    ebx, ebx
0x18004180f  js      short loc_180041860
0x180041811  mov     edx, 2710h; dwMilliseconds
0x180041816  mov     rcx, rdi; hHandle
0x180041819  call    cs:__imp_WaitForSingleObject
0x18004181f  cmp     eax, 102h
0x180041824  jz      short loc_180041844
0x180041826  cmp     eax, 0FFFFFFFFh
0x180041829  jnz     short loc_180041886
0x18004182b  call    cs:__imp_GetLastError
0x180041831  mov     ebx, eax
0x180041833  test    eax, eax
0x180041835  jle     short loc_180041840
0x180041837  movzx   ebx, ax
0x18004183a  or      ebx, 80070000h
0x180041840  test    ebx, ebx
0x180041842  js      short loc_180041849
0x180041844  mov     ebx, 800705B4h
0x180041849  test    rdi, rdi
0x18004184c  jz      short loc_180041860
0x18004184e  mov     rcx, rdi; hMutex
0x180041851  call    cs:__imp_ReleaseMutex
0x180041857  mov     rcx, rdi; hObject
0x18004185a  call    cs:__imp_CloseHandle
0x180041860  mov     eax, ebx
0x180041862  mov     rcx, [rbp+var_8]
0x180041866  xor     rcx, rsp; StackCookie
0x180041869  call    __security_check_cookie
0x18004186e  lea     r11, [rsp+80h+var_s0]
0x180041876  mov     rbx, [r11+20h]
0x18004187a  mov     rsi, [r11+28h]
0x18004187e  mov     rsp, r11
0x180041881  pop     r14
0x180041883  pop     rdi
0x180041884  pop     rbp
0x180041885  retn
0x180041886  lea     rcx, [rbp+pbBuffer]; lpData
0x18004188a  call    ?GetRandomSeedFromRegistry@@YAJPEAEI@Z; GetRandomSeedFromRegistry(uchar *,uint)
0x18004188f  mov     ebx, eax
0x180041891  test    eax, eax
0x180041893  jns     short loc_1800418C5
0x180041895  and     eax, 1FFF0000h
0x18004189a  cmp     eax, 70000h
0x18004189f  jnz     short loc_180041849
0x1800418a1  cmp     bx, 2
0x1800418a5  jnz     short loc_180041849
0x1800418a7  lea     rcx, [rbp+pbBuffer]; pbBuffer
0x1800418ab  call    ?GenerateRandomSeed@@YAJPEAEI@Z; GenerateRandomSeed(uchar *,uint)
0x1800418b0  mov     ebx, eax
0x1800418b2  test    eax, eax
0x1800418b4  js      short loc_180041849
0x1800418b6  lea     rcx, [rbp+pbBuffer]; lpData
0x1800418ba  call    ?StoreRandomSeedInRegistry@@YAJPEAEI@Z; StoreRandomSeedInRegistry(uchar *,uint)
0x1800418bf  mov     ebx, eax
0x1800418c1  test    eax, eax
0x1800418c3  js      short loc_180041849
0x1800418c5  lea     rax, [rbp+var_50]
0x1800418c9  mov     r8d, 20h ; ' '; unsigned int
0x1800418cf  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800418d4  lea     r9, [rbp+pbBuffer]; unsigned __int8 *
0x1800418d8  lea     rax, [rbp+var_28]
0x1800418dc  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x1800418e1  call    ?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z; GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)
0x1800418e6  mov     ebx, eax
0x1800418e8  test    eax, eax
0x1800418ea  js      loc_180041849
0x1800418f0  movups  xmm0, xmmword ptr [rbp+var_28]
0x1800418f4  movups  xmm1, [rbp+var_18]
0x1800418f8  movups  xmmword ptr [r14], xmm0
0x1800418fc  movups  xmmword ptr [r14+10h], xmm1
0x180041901  mov     dword ptr [rsi], 20h ; ' '
0x180041907  jmp     loc_180041849
```

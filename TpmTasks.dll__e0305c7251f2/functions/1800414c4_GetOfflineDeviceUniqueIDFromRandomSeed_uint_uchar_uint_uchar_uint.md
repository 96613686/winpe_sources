# GetOfflineDeviceUniqueIDFromRandomSeed(uint,uchar *,uint *,uchar *,uint *)

- ea: `0x1800414c4`
- end: `0x180041722`
- name: `?GetOfflineDeviceUniqueIDFromRandomSeed@@YAJIPEAEPEAI01@Z`
- size: `606`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180040efc`

## callees

- `0x1800078b0`
- `0x18004128c`
- `0x18004141c`
- `0x1800414c4`
- `0x180041b80`
- `0x180041c64`
- `0x180042080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004161e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18004161e`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800415b7`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800415b7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180041590`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180041590`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800415e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800415e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004159e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004159e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041627`

## string_xrefs

- `0x180041585`: `OFFLINEDEVICEID-CREATERANDOMSEED`
- `0x1800415a9`: `OFFLINEDEVICEID-CREATERANDOMSEED`

## pseudocode

```c
__int64 __fastcall GetOfflineDeviceUniqueIDFromRandomSeed(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  int RandomSeed; // ebx
  int UEFIVarAndUEFICRC; // eax
  unsigned __int8 *v8; // rdx
  unsigned int v9; // ecx
  HANDLE MutexW; // rdi
  signed int LastError; // eax
  DWORD v12; // eax
  signed int v13; // eax
  int v15; // eax
  __int128 v16; // xmm1
  unsigned int v17; // [rsp+28h] [rbp-58h]
  unsigned int v18; // [rsp+28h] [rbp-58h]
  unsigned int v19; // [rsp+28h] [rbp-58h]
  int v20; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-4Ch] BYREF
  UCHAR pbBuffer[16]; // [rsp+38h] [rbp-48h] BYREF
  __int128 v23; // [rsp+48h] [rbp-38h]
  unsigned __int8 v24[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+68h] [rbp-18h]

  v20 = 0;
  *(_OWORD *)pbBuffer = 0;
  v21 = 32;
  v23 = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  if ( *a3 < 0x20 )
  {
    *a3 = 32;
    return (unsigned int)-2147024774;
  }
  if ( !(unsigned __int8)IsUEFIFW(a1, a2) )
    return (unsigned int)-2147023091;
  UEFIVarAndUEFICRC = GetUEFIVarAndUEFICRC(
                        L"OfflineUniqueIDRandomSeed",
                        L"OfflineUniqueIDRandomSeedCRC",
                        pbBuffer,
                        0x20u,
                        &v20,
                        v17);
  RandomSeed = UEFIVarAndUEFICRC;
  if ( UEFIVarAndUEFICRC >= 0 )
  {
    MutexW = 0;
    goto LABEL_30;
  }
  if ( (UEFIVarAndUEFICRC & 0x1FFF0000) == 0x70000 && (_WORD)UEFIVarAndUEFICRC == 203 )
  {
    MutexW = CreateMutexW(0, 0, L"OFFLINEDEVICEID-CREATERANDOMSEED");
    if ( MutexW )
      goto LABEL_15;
    if ( GetLastError() == 5 )
    {
      MutexW = OpenMutexW(0x100000u, 0, L"OFFLINEDEVICEID-CREATERANDOMSEED");
      if ( MutexW )
        goto LABEL_15;
    }
    LastError = GetLastError();
    RandomSeed = LastError;
    if ( LastError > 0 )
      RandomSeed = (unsigned __int16)LastError | 0x80070000;
    if ( RandomSeed >= 0 )
    {
LABEL_15:
      v12 = WaitForSingleObject(MutexW, 0x2710u);
      if ( v12 != 258 )
      {
        if ( v12 != -1 )
        {
          v15 = GetUEFIVarAndUEFICRC(
                  L"OfflineUniqueIDRandomSeed",
                  L"OfflineUniqueIDRandomSeedCRC",
                  pbBuffer,
                  0x20u,
                  &v20,
                  v18);
          RandomSeed = v15;
          if ( v15 >= 0
            || (v15 & 0x1FFF0000) == 0x70000
            && (_WORD)v15 == 203
            && (RandomSeed = GenerateRandomSeed(pbBuffer, (unsigned int)v8), RandomSeed >= 0)
            && (RandomSeed = StoreRandomSeedInUEFI(pbBuffer), RandomSeed >= 0)
            && (RandomSeed = GetUEFIVarAndUEFICRC(
                               L"OfflineUniqueIDRandomSeed",
                               L"OfflineUniqueIDRandomSeedCRC",
                               pbBuffer,
                               0x20u,
                               &v20,
                               v19),
                RandomSeed >= 0) )
          {
LABEL_30:
            RandomSeed = GenerateOfflineDeviceID(v9, v8, 0x20u, pbBuffer, v24, &v21);
            if ( RandomSeed >= 0 )
            {
              v16 = v25;
              *(_OWORD *)a4 = *(_OWORD *)v24;
              *((_OWORD *)a4 + 1) = v16;
              *a3 = 32;
            }
          }
LABEL_21:
          if ( MutexW )
          {
            ReleaseMutex(MutexW);
            CloseHandle(MutexW);
          }
          return (unsigned int)RandomSeed;
        }
        v13 = GetLastError();
        RandomSeed = v13;
        if ( v13 > 0 )
          RandomSeed = (unsigned __int16)v13 | 0x80070000;
        if ( RandomSeed < 0 )
          goto LABEL_21;
      }
      RandomSeed = -2147023436;
      goto LABEL_21;
    }
  }
  return (unsigned int)RandomSeed;
}

```

## disassembly

```asm
0x1800414c4  mov     [rsp-28h+arg_0], rbx
0x1800414c9  push    rbp
0x1800414ca  push    rsi
0x1800414cb  push    rdi
0x1800414cc  push    r14
0x1800414ce  push    r15
0x1800414d0  mov     rbp, rsp
0x1800414d3  sub     rsp, 80h
0x1800414da  mov     rax, cs:__security_cookie
0x1800414e1  xor     rax, rsp
0x1800414e4  mov     [rbp+var_8], rax
0x1800414e8  mov     r15d, 20h ; ' '
0x1800414ee  mov     [rbp+var_50], 0
0x1800414f5  xorps   xmm0, xmm0
0x1800414f8  xorps   xmm1, xmm1
0x1800414fb  mov     r14, r9
0x1800414fe  mov     rsi, r8
0x180041501  movups  xmmword ptr [rbp+pbBuffer], xmm0
0x180041505  mov     [rbp+var_4C], r15d
0x180041509  movups  [rbp+var_38], xmm0
0x18004150d  movups  xmmword ptr [rbp+var_28], xmm1
0x180041511  movups  [rbp+var_18], xmm1
0x180041515  cmp     [r8], r15d
0x180041518  jnb     short loc_180041527
0x18004151a  mov     [r8], r15d
0x18004151d  mov     ebx, 8007007Ah
0x180041522  jmp     loc_18004162D
0x180041527  call    IsUEFIFW
0x18004152c  test    al, al
0x18004152e  jnz     short loc_18004153A
0x180041530  mov     ebx, 8007070Dh
0x180041535  jmp     loc_18004162D
0x18004153a  lea     rax, [rbp+var_50]
0x18004153e  mov     r9d, r15d; nSize
0x180041541  lea     r8, [rbp+pbBuffer]; pBuffer
0x180041545  mov     [rsp+80h+var_60], rax; PVOID
0x18004154a  lea     rdx, aOfflineuniquei_0; "OfflineUniqueIDRandomSeedCRC"
0x180041551  lea     rcx, aOfflineuniquei; "OfflineUniqueIDRandomSeed"
0x180041558  call    ?GetUEFIVarAndUEFICRC@@YAJPEBG0PEAEI1I@Z; GetUEFIVarAndUEFICRC(ushort const *,ushort const *,uchar *,uint,uchar *,uint)
0x18004155d  mov     ebx, eax
0x18004155f  test    eax, eax
0x180041561  js      short loc_18004156A
0x180041563  xor     edi, edi
0x180041565  jmp     loc_1800416E1
0x18004156a  and     eax, 1FFF0000h
0x18004156f  cmp     eax, 70000h
0x180041574  jnz     loc_18004162D
0x18004157a  cmp     bx, 0CBh
0x18004157f  jnz     loc_18004162D
0x180041585  lea     r8, aOfflinedevicei; "OFFLINEDEVICEID-CREATERANDOMSEED"
0x18004158c  xor     edx, edx; bInitialOwner
0x18004158e  xor     ecx, ecx; lpMutexAttributes
0x180041590  call    cs:__imp_CreateMutexW
0x180041596  mov     rdi, rax
0x180041599  test    rax, rax
0x18004159c  jnz     short loc_1800415DE
0x18004159e  call    cs:__imp_GetLastError
0x1800415a4  cmp     eax, 5
0x1800415a7  jnz     short loc_1800415C5
0x1800415a9  lea     r8, aOfflinedevicei; "OFFLINEDEVICEID-CREATERANDOMSEED"
0x1800415b0  xor     edx, edx; bInheritHandle
0x1800415b2  mov     ecx, 100000h; dwDesiredAccess
0x1800415b7  call    cs:__imp_OpenMutexW
0x1800415bd  mov     rdi, rax
0x1800415c0  test    rax, rax
0x1800415c3  jnz     short loc_1800415DE
0x1800415c5  call    cs:__imp_GetLastError
0x1800415cb  mov     ebx, eax
0x1800415cd  test    eax, eax
0x1800415cf  jle     short loc_1800415DA
0x1800415d1  movzx   ebx, ax
0x1800415d4  or      ebx, 80070000h
0x1800415da  test    ebx, ebx
0x1800415dc  js      short loc_18004162D
0x1800415de  mov     edx, 2710h; dwMilliseconds
0x1800415e3  mov     rcx, rdi; hHandle
0x1800415e6  call    cs:__imp_WaitForSingleObject
0x1800415ec  cmp     eax, 102h
0x1800415f1  jz      short loc_180041611
0x1800415f3  cmp     eax, 0FFFFFFFFh
0x1800415f6  jnz     short loc_180041652
0x1800415f8  call    cs:__imp_GetLastError
0x1800415fe  mov     ebx, eax
0x180041600  test    eax, eax
0x180041602  jle     short loc_18004160D
0x180041604  movzx   ebx, ax
0x180041607  or      ebx, 80070000h
0x18004160d  test    ebx, ebx
0x18004160f  js      short loc_180041616
0x180041611  mov     ebx, 800705B4h
0x180041616  test    rdi, rdi
0x180041619  jz      short loc_18004162D
0x18004161b  mov     rcx, rdi; hMutex
0x18004161e  call    cs:__imp_ReleaseMutex
0x180041624  mov     rcx, rdi; hObject
0x180041627  call    cs:__imp_CloseHandle
0x18004162d  mov     eax, ebx
0x18004162f  mov     rcx, [rbp+var_8]
0x180041633  xor     rcx, rsp; StackCookie
0x180041636  call    __security_check_cookie
0x18004163b  mov     rbx, [rsp+80h+arg_0]
0x180041643  add     rsp, 80h
0x18004164a  pop     r15
0x18004164c  pop     r14
0x18004164e  pop     rdi
0x18004164f  pop     rsi
0x180041650  pop     rbp
0x180041651  retn
0x180041652  lea     rax, [rbp+var_50]
0x180041656  mov     r9d, r15d; nSize
0x180041659  lea     r8, [rbp+pbBuffer]; pBuffer
0x18004165d  mov     [rsp+80h+var_60], rax; PVOID
0x180041662  lea     rdx, aOfflineuniquei_0; "OfflineUniqueIDRandomSeedCRC"
0x180041669  lea     rcx, aOfflineuniquei; "OfflineUniqueIDRandomSeed"
0x180041670  call    ?GetUEFIVarAndUEFICRC@@YAJPEBG0PEAEI1I@Z; GetUEFIVarAndUEFICRC(ushort const *,ushort const *,uchar *,uint,uchar *,uint)
0x180041675  mov     ebx, eax
0x180041677  test    eax, eax
0x180041679  jns     short loc_1800416E1
0x18004167b  and     eax, 1FFF0000h
0x180041680  cmp     eax, 70000h
0x180041685  jnz     short loc_180041616
0x180041687  cmp     bx, 0CBh
0x18004168c  jnz     short loc_180041616
0x18004168e  lea     rcx, [rbp+pbBuffer]; pbBuffer
0x180041692  call    ?GenerateRandomSeed@@YAJPEAEI@Z; GenerateRandomSeed(uchar *,uint)
0x180041697  mov     ebx, eax
0x180041699  test    eax, eax
0x18004169b  js      loc_180041616
0x1800416a1  lea     rcx, [rbp+pbBuffer]; unsigned __int8 *
0x1800416a5  call    ?StoreRandomSeedInUEFI@@YAJPEAEI@Z; StoreRandomSeedInUEFI(uchar *,uint)
0x1800416aa  mov     ebx, eax
0x1800416ac  test    eax, eax
0x1800416ae  js      loc_180041616
0x1800416b4  lea     rax, [rbp+var_50]
0x1800416b8  mov     r9d, r15d; nSize
0x1800416bb  lea     r8, [rbp+pbBuffer]; pBuffer
0x1800416bf  mov     [rsp+80h+var_60], rax; PVOID
0x1800416c4  lea     rdx, aOfflineuniquei_0; "OfflineUniqueIDRandomSeedCRC"
0x1800416cb  lea     rcx, aOfflineuniquei; "OfflineUniqueIDRandomSeed"
0x1800416d2  call    ?GetUEFIVarAndUEFICRC@@YAJPEBG0PEAEI1I@Z; GetUEFIVarAndUEFICRC(ushort const *,ushort const *,uchar *,uint,uchar *,uint)
0x1800416d7  mov     ebx, eax
0x1800416d9  test    eax, eax
0x1800416db  js      loc_180041616
0x1800416e1  lea     rax, [rbp+var_4C]
0x1800416e5  mov     r8d, r15d; unsigned int
0x1800416e8  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800416ed  lea     r9, [rbp+pbBuffer]; unsigned __int8 *
0x1800416f1  lea     rax, [rbp+var_28]
0x1800416f5  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x1800416fa  call    ?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z; GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)
0x1800416ff  mov     ebx, eax
0x180041701  test    eax, eax
0x180041703  js      loc_180041616
0x180041709  movups  xmm0, xmmword ptr [rbp+var_28]
0x18004170d  movups  xmm1, [rbp+var_18]
0x180041711  movups  xmmword ptr [r14], xmm0
0x180041715  movups  xmmword ptr [r14+10h], xmm1
0x18004171a  mov     [rsi], r15d
0x18004171d  jmp     loc_180041616
```

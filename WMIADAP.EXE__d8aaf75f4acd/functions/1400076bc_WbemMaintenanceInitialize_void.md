# WbemMaintenanceInitialize(void)

- ea: `0x1400076bc`
- end: `0x140007818`
- name: `?WbemMaintenanceInitialize@@YAJXZ`
- size: `348`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006bb4`

## callees

- `0x14000661c`
- `0x1400068c0`
- `0x1400076bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400077ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400077e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400077ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400077e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400076ee`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140007741`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000778f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400076ee`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140007741`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000778f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007753`

## pseudocode

```c
__int64 WbemMaintenanceInitialize(void)
{
  unsigned int v0; // edx
  struct _SECURITY_ATTRIBUTES *v1; // rcx
  signed int LastError; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  _BYTE v6[8]; // [rsp+20h] [rbp-38h] BYREF
  LPSECURITY_ATTRIBUTES lpMutexAttributes; // [rsp+28h] [rbp-30h]

  WmiSecurityAttributes::WmiSecurityAttributes((WmiSecurityAttributes *)v6);
  v1 = lpMutexAttributes;
  if ( !lpMutexAttributes )
  {
    v3 = -2147467259;
    goto LABEL_24;
  }
  if ( !qword_140024090 )
  {
    qword_140024090 = CreateMutexW(lpMutexAttributes, 0, L"Global\\RefreshRA_Mutex");
    if ( !qword_140024090 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_24;
      }
LABEL_22:
      v3 = -2147024882;
      goto LABEL_24;
    }
    v1 = lpMutexAttributes;
  }
  if ( !qword_140024070 )
  {
    qword_140024070 = (__int64)CreateMutexW(v1, 0, L"Global\\RefreshRA_Mutex_Lib");
    if ( !qword_140024070 )
      goto LABEL_10;
    v1 = lpMutexAttributes;
  }
  if ( (hMutex || (hMutex = CreateMutexW(v1, 0, L"Global\\RefreshRA_Mutex_Flag")) != 0)
    && (hEvent || (hEvent = CreateEventW(0, 1, 0, 0)) != 0)
    && (hHandle || (hHandle = CreateEventW(0, 1, 0, 0)) != 0) )
  {
    v3 = 0;
    goto LABEL_24;
  }
LABEL_10:
  v4 = GetLastError();
  if ( v4 == 183 )
    goto LABEL_22;
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  v3 = v4;
LABEL_24:
  WmiSecurityAttributes::~WmiSecurityAttributes((WmiSecurityAttributes *)v6, v0);
  return v3;
}

```

## disassembly

```asm
0x1400076bc  push    rbx
0x1400076be  sub     rsp, 50h
0x1400076c2  lea     rcx, [rsp+58h+var_38]; this
0x1400076c7  call    ??0WmiSecurityAttributes@@QEAA@H@Z; WmiSecurityAttributes::WmiSecurityAttributes(int)
0x1400076cc  nop
0x1400076cd  mov     rcx, [rsp+58h+lpMutexAttributes]; lpMutexAttributes
0x1400076d2  test    rcx, rcx
0x1400076d5  jz      loc_140007801
0x1400076db  cmp     cs:qword_140024090, 0
0x1400076e3  jnz     short loc_14000772E
0x1400076e5  lea     r8, aGlobalRefreshr; "Global\\RefreshRA_Mutex"
0x1400076ec  xor     edx, edx; bInitialOwner
0x1400076ee  call    cs:__imp_CreateMutexW
0x1400076f4  mov     cs:qword_140024090, rax
0x1400076fb  test    rax, rax
0x1400076fe  jnz     short loc_140007729
0x140007700  call    cs:__imp_GetLastError
0x140007706  mov     ebx, eax
0x140007708  cmp     eax, 0B7h
0x14000770d  jz      loc_1400077FA
0x140007713  test    eax, eax
0x140007715  jle     loc_140007806
0x14000771b  movzx   ebx, ax
0x14000771e  or      ebx, 80070000h
0x140007724  jmp     loc_140007806
0x140007729  mov     rcx, [rsp+58h+lpMutexAttributes]; lpMutexAttributes
0x14000772e  cmp     cs:qword_140024070, 0
0x140007736  jnz     short loc_14000777C
0x140007738  lea     r8, aGlobalRefreshr_1; "Global\\RefreshRA_Mutex_Lib"
0x14000773f  xor     edx, edx; bInitialOwner
0x140007741  call    cs:__imp_CreateMutexW
0x140007747  mov     cs:qword_140024070, rax
0x14000774e  test    rax, rax
0x140007751  jnz     short loc_140007777
0x140007753  call    cs:__imp_GetLastError
0x140007759  cmp     eax, 0B7h
0x14000775e  jz      loc_1400077FA
0x140007764  test    eax, eax
0x140007766  jle     short loc_140007770
0x140007768  movzx   eax, ax
0x14000776b  or      eax, 80070000h
0x140007770  mov     ebx, eax
0x140007772  jmp     loc_140007806
0x140007777  mov     rcx, [rsp+58h+lpMutexAttributes]; lpMutexAttributes
0x14000777c  cmp     cs:hMutex, 0
0x140007784  jnz     short loc_1400077A1
0x140007786  lea     r8, aGlobalRefreshr_0; "Global\\RefreshRA_Mutex_Flag"
0x14000778d  xor     edx, edx; bInitialOwner
0x14000778f  call    cs:__imp_CreateMutexW
0x140007795  mov     cs:hMutex, rax
0x14000779c  test    rax, rax
0x14000779f  jz      short loc_140007753
0x1400077a1  mov     ebx, 1
0x1400077a6  cmp     cs:hEvent, 0
0x1400077ae  jnz     short loc_1400077CC
0x1400077b0  xor     r9d, r9d; lpName
0x1400077b3  xor     r8d, r8d; bInitialState
0x1400077b6  mov     edx, ebx; bManualReset
0x1400077b8  xor     ecx, ecx; lpEventAttributes
0x1400077ba  call    cs:__imp_CreateEventW
0x1400077c0  mov     cs:hEvent, rax
0x1400077c7  test    rax, rax
0x1400077ca  jz      short loc_140007753
0x1400077cc  cmp     cs:hHandle, 0
0x1400077d4  jnz     short loc_1400077F6
0x1400077d6  xor     r9d, r9d; lpName
0x1400077d9  xor     r8d, r8d; bInitialState
0x1400077dc  mov     edx, ebx; bManualReset
0x1400077de  xor     ecx, ecx; lpEventAttributes
0x1400077e0  call    cs:__imp_CreateEventW
0x1400077e6  mov     cs:hHandle, rax
0x1400077ed  test    rax, rax
0x1400077f0  jz      loc_140007753
0x1400077f6  xor     ebx, ebx
0x1400077f8  jmp     short loc_140007806
0x1400077fa  mov     ebx, 8007000Eh
0x1400077ff  jmp     short loc_140007806
0x140007801  mov     ebx, 80004005h
0x140007806  lea     rcx, [rsp+58h+var_38]; this
0x14000780b  call    ??1WmiSecurityAttributes@@QEAA@XZ; WmiSecurityAttributes::~WmiSecurityAttributes(void)
0x140007810  mov     eax, ebx
0x140007812  add     rsp, 50h
0x140007816  pop     rbx
0x140007817  retn
```

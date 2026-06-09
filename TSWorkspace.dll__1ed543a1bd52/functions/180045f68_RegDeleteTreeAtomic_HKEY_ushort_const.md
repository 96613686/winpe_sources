# RegDeleteTreeAtomic(HKEY__ *,ushort const *)

- ea: `0x180045f68`
- end: `0x1800461a7`
- name: `?RegDeleteTreeAtomic@@YAJPEAUHKEY__@@PEBG@Z`
- size: `575`
- prototype: `int(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e6fc`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x180045f68`

## import_xrefs

- `ADVAPI32!RegOpenKeyTransactedW` at `0x180046058`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180046058`
- `ADVAPI32!RegCloseKey` at `0x180046187`
- `ADVAPI32!RegCloseKey` at `0x180046187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004615b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004615b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046196`
- `KERNEL32!RegDeleteTreeW` at `0x1800460d5`
- `KERNEL32!RegDeleteTreeW` at `0x1800460d5`
- `ktmw32!CreateTransaction` at `0x180045fa8`
- `ktmw32!CreateTransaction` at `0x180045fa8`
- `ktmw32!CommitTransaction` at `0x180046121`
- `ktmw32!CommitTransaction` at `0x180046121`

## string_xrefs

- `0x180045f81`: `RegDeleteTreeAtomic`

## pseudocode

```c
__int64 __fastcall RegDeleteTreeAtomic(HKEY a1, const unsigned __int16 *a2)
{
  HANDLE Transaction; // rbp
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  signed int v8; // eax
  LSTATUS v9; // ebx
  unsigned int v10; // esi
  unsigned int v11; // eax
  __int64 v12; // rdx
  signed int v13; // eax
  HKEY phkResult; // [rsp+70h] [rbp+8h] BYREF

  phkResult = 0;
  Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0x2710u, (LPWSTR)L"RegDeleteTreeAtomic");
  if ( Transaction == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 30;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids,
      CurrentThreadActivityIdPrefix,
      v5);
LABEL_9:
    v8 = GetLastError();
    v9 = v8;
    if ( v8 <= 0 )
      goto LABEL_39;
    v9 = (unsigned __int16)v8;
    goto LABEL_11;
  }
  v9 = RegOpenKeyTransactedW(HKEY_CURRENT_USER, 0, 0, 0x10009u, &phkResult, Transaction, 0);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 31;
LABEL_20:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids, v11, v10);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  v9 = RegDeleteTreeW(phkResult, a2);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 32;
      goto LABEL_20;
    }
LABEL_21:
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9;
LABEL_11:
      v9 |= 0x80070000;
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( !CommitTransaction(Transaction) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 33;
    goto LABEL_8;
  }
  v9 = 0;
LABEL_39:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( Transaction != (HANDLE)-1LL )
    CloseHandle(Transaction);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180045f68  mov     [rsp+phkResult], rcx
0x180045f6d  push    rbx
0x180045f6e  push    rbp
0x180045f6f  push    rsi
0x180045f70  push    rdi
0x180045f71  sub     rsp, 48h
0x180045f75  xor     r9d, r9d; IsolationLevel
0x180045f78  mov     [rsp+68h+phkResult], 0
0x180045f81  lea     rax, aRegdeletetreea; "RegDeleteTreeAtomic"
0x180045f88  mov     rdi, rdx
0x180045f8b  mov     [rsp+68h+Description], rax; Description
0x180045f90  xor     edx, edx; UOW
0x180045f92  mov     [rsp+68h+Timeout], 2710h; Timeout
0x180045f9a  xor     ecx, ecx; lpTransactionAttributes
0x180045f9c  lea     r8d, [r9+1]; CreateOptions
0x180045fa0  mov     [rsp+68h+IsolationFlags], 0; IsolationFlags
0x180045fa8  call    cs:__imp_CreateTransaction
0x180045fae  mov     rbp, rax
0x180045fb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045fb5  jnz     short loc_18004602E
0x180045fb7  mov     rdx, cs:WPP_GLOBAL_Control
0x180045fbe  lea     rcx, WPP_GLOBAL_Control
0x180045fc5  mov     edi, 80070000h
0x180045fca  cmp     rdx, rcx
0x180045fcd  jz      short loc_180046014
0x180045fcf  test    byte ptr [rdx+1Ch], 8
0x180045fd3  jz      short loc_180046014
0x180045fd5  cmp     byte ptr [rdx+19h], 2
0x180045fd9  jb      short loc_180046014
0x180045fdb  call    cs:__imp_GetLastError
0x180045fe1  mov     ebx, eax
0x180045fe3  test    eax, eax
0x180045fe5  jle     short loc_180045FEC
0x180045fe7  movzx   ebx, ax
0x180045fea  or      ebx, edi
0x180045fec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180045ff1  mov     edx, 1Eh
0x180045ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ffd  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x180046004  mov     r9d, eax
0x180046007  mov     [rsp+68h+IsolationFlags], ebx
0x18004600b  mov     rcx, [rcx+10h]
0x18004600f  call    WPP_SF_Dd
0x180046014  call    cs:__imp_GetLastError
0x18004601a  mov     ebx, eax
0x18004601c  test    eax, eax
0x18004601e  jle     loc_18004617D
0x180046024  movzx   ebx, ax
0x180046027  or      ebx, edi
0x180046029  jmp     loc_18004617D
0x18004602e  mov     [rsp+68h+Description], 0; pExtendedParemeter
0x180046037  lea     rax, [rsp+68h+phkResult]
0x18004603c  mov     qword ptr [rsp+68h+Timeout], rbp; hTransaction
0x180046041  mov     r9d, 10009h; samDesired
0x180046047  xor     r8d, r8d; ulOptions
0x18004604a  mov     qword ptr [rsp+68h+IsolationFlags], rax; phkResult
0x18004604f  xor     edx, edx; lpSubKey
0x180046051  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180046058  call    cs:__imp_RegOpenKeyTransactedW
0x18004605e  mov     ebx, eax
0x180046060  test    eax, eax
0x180046062  jz      short loc_1800460CD
0x180046064  mov     rax, cs:WPP_GLOBAL_Control
0x18004606b  lea     rcx, WPP_GLOBAL_Control
0x180046072  mov     edi, 80070000h
0x180046077  cmp     rax, rcx
0x18004607a  jz      short loc_1800460BD
0x18004607c  test    byte ptr [rax+1Ch], 8
0x180046080  jz      short loc_1800460BD
0x180046082  cmp     byte ptr [rax+19h], 2
0x180046086  jb      short loc_1800460BD
0x180046088  test    ebx, ebx
0x18004608a  jg      short loc_180046090
0x18004608c  mov     esi, ebx
0x18004608e  jmp     short loc_180046095
0x180046090  movzx   esi, bx
0x180046093  or      esi, edi
0x180046095  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004609a  mov     edx, 1Fh
0x18004609f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460a6  lea     r8, WPP_818651e07d4c36e166bc01172f1aaacc_Traceguids
0x1800460ad  mov     r9d, eax
0x1800460b0  mov     [rsp+68h+IsolationFlags], esi
0x1800460b4  mov     rcx, [rcx+10h]
0x1800460b8  call    WPP_SF_Dd
0x1800460bd  test    ebx, ebx
0x1800460bf  jle     loc_18004617D
0x1800460c5  movzx   ebx, bx
0x1800460c8  jmp     loc_180046027
0x1800460cd  mov     rcx, [rsp+68h+phkResult]; hKey
0x1800460d2  mov     rdx, rdi; lpSubKey
0x1800460d5  call    cs:__imp_RegDeleteTreeW
0x1800460db  mov     ebx, eax
0x1800460dd  test    eax, eax
0x1800460df  jz      short loc_18004611E
0x1800460e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800460e8  lea     rcx, WPP_GLOBAL_Control
0x1800460ef  mov     edi, 80070000h
0x1800460f4  cmp     rax, rcx
0x1800460f7  jz      short loc_1800460BD
0x1800460f9  test    byte ptr [rax+1Ch], 8
0x1800460fd  jz      short loc_1800460BD
0x1800460ff  cmp     byte ptr [rax+19h], 2
0x180046103  jb      short loc_1800460BD
0x180046105  test    ebx, ebx
0x180046107  jg      short loc_18004610D
0x180046109  mov     esi, ebx
0x18004610b  jmp     short loc_180046112
0x18004610d  movzx   esi, bx
0x180046110  or      esi, edi
0x180046112  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046117  mov     edx, 20h ; ' '
0x18004611c  jmp     short loc_18004609F
0x18004611e  mov     rcx, rbp; TransactionHandle
0x180046121  call    cs:__imp_CommitTransaction
0x180046127  test    eax, eax
0x180046129  jnz     short loc_18004617B
0x18004612b  mov     rax, cs:WPP_GLOBAL_Control
0x180046132  lea     rcx, WPP_GLOBAL_Control
0x180046139  mov     edi, 80070000h
0x18004613e  cmp     rax, rcx
0x180046141  jz      loc_180046014
0x180046147  test    byte ptr [rax+1Ch], 8
0x18004614b  jz      loc_180046014
0x180046151  cmp     byte ptr [rax+19h], 2
0x180046155  jb      loc_180046014
0x18004615b  call    cs:__imp_GetLastError
0x180046161  mov     ebx, eax
0x180046163  test    eax, eax
0x180046165  jle     short loc_18004616C
0x180046167  movzx   ebx, ax
0x18004616a  or      ebx, edi
0x18004616c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180046171  mov     edx, 21h ; '!'
0x180046176  jmp     loc_180045FF6
0x18004617b  xor     ebx, ebx
0x18004617d  mov     rcx, [rsp+68h+phkResult]; hKey
0x180046182  test    rcx, rcx
0x180046185  jz      short loc_18004618D
0x180046187  call    cs:__imp_RegCloseKey
0x18004618d  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180046191  jz      short loc_18004619C
0x180046193  mov     rcx, rbp; hObject
0x180046196  call    cs:__imp_CloseHandle
0x18004619c  mov     eax, ebx
0x18004619e  add     rsp, 48h
0x1800461a2  pop     rdi
0x1800461a3  pop     rsi
0x1800461a4  pop     rbp
0x1800461a5  pop     rbx
0x1800461a6  retn
```

# TBNCryptGetOrGenerateKey(_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *,TOKENBINDING_KEY_PARAMETERS_TYPE,ushort const *,unsigned __int64 *)

- ea: `0x1800ebf78`
- end: `0x1800ec4f1`
- name: `?TBNCryptGetOrGenerateKey@@YAJPEAU_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE@@W4TOKENBINDING_KEY_PARAMETERS_TYPE@@PEBGPEA_K@Z`
- size: `1401`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800ebeb0`

## callees

- `0x1800ea53c`
- `0x1800ea980`
- `0x1800eaac8`
- `0x1800eac04`
- `0x1800eb23c`
- `0x1800ebb70`
- `0x1800ebf78`
- `0x1800ec558`
- `0x1800ec6bc`
- `0x1800ec74c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec0fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec1a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec26c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec0fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec1a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec26c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ec417`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec144`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec144`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800ec399`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800ec399`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800ec0a7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800ec0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec0b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec0b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec14c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec3a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec46a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ec46a`
- `ncrypt!NCryptFreeObject` at `0x1800ec4a3`
- `ncrypt!NCryptFreeObject` at `0x1800ec4a3`

## pseudocode

```c
__int64 __fastcall TBNCryptGetOrGenerateKey(__int64 a1, unsigned int a2, const unsigned __int16 *a3, NCRYPT_HANDLE *a4)
{
  LPCWSTR v6; // r12
  signed int v8; // ebx
  signed int v9; // eax
  HANDLE Semaphore; // r14
  int v11; // r8d
  const WCHAR *v12; // r9
  signed int LastError; // eax
  signed int v14; // esi
  int v15; // r8d
  const WCHAR *v16; // rcx
  DWORD v17; // esi
  signed int v18; // eax
  char v19; // al
  int v20; // r8d
  int v21; // edx
  char v22; // al
  int v23; // r8d
  int v24; // edx
  char v25; // al
  const WCHAR *v26; // r9
  int v27; // eax
  const WCHAR *v28; // r9
  int v29; // eax
  __int128 v30; // xmm1
  __int64 (__fastcall *v31)(_OWORD *, unsigned __int16 *, NCRYPT_HANDLE *); // rax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  signed int v34; // eax
  NCRYPT_HANDLE v35; // rax
  char dwFlags; // [rsp+28h] [rbp-39h]
  char dwDesiredAccess; // [rsp+30h] [rbp-31h]
  char dwDesiredAccessa; // [rsp+30h] [rbp-31h]
  char CurrentThreadId; // [rsp+38h] [rbp-29h]
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp-19h] BYREF
  enum TOKENBINDING_KEY_PARAMETERS_TYPE *v42; // [rsp+50h] [rbp-11h] BYREF
  LPCWSTR lpName; // [rsp+58h] [rbp-9h]
  _OWORD v44[2]; // [rsp+68h] [rbp+7h] BYREF
  __int64 v45; // [rsp+88h] [rbp+27h]
  unsigned __int16 *v46; // [rsp+C8h] [rbp+67h] BYREF
  NCRYPT_HANDLE *v47; // [rsp+E0h] [rbp+7Fh]

  v47 = a4;
  v42 = 0;
  hObject = 0;
  v6 = 0;
  v46 = 0;
  lpName = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, enum TOKENBINDING_KEY_PARAMETERS_TYPE **))(a1 + 24))(a2, &v42);
  if ( v8 < 0 )
    goto LABEL_86;
  v8 = TBCreateKeyName(a2, a3, &v46);
  if ( v8 >= 0 )
  {
    v9 = TBNCryptOpenKey((struct _TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *)a1, v46, 0, &hObject);
    v8 = v9;
    if ( v9 != -2146893802 )
    {
      Semaphore = 0;
      if ( v9 != -2146893807 )
        goto LABEL_77;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      dwDesiredAccess = GetCurrentThreadId();
      LODWORD(v12) = (_DWORD)a3;
      if ( !a3 )
        v12 = L"NULL";
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v11, (_DWORD)v12, v8, dwDesiredAccess);
    }
    v8 = TBCreateSemaphoreName(v46);
    if ( v8 < 0 )
    {
      v6 = lpName;
      goto LABEL_82;
    }
    v6 = lpName;
    Semaphore = CreateSemaphoreExW(0, 1, 1, lpName, 0, 0x1F0003u);
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    else
      v8 = LastError;
    if ( !Semaphore || LastError && LastError != 183 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_77;
      dwDesiredAccessa = GetCurrentThreadId();
      v21 = 11;
      dwFlags = v8;
LABEL_74:
      if ( !a3 )
        a3 = L"NULL";
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v20, (_DWORD)a3, dwFlags, dwDesiredAccessa);
      goto LABEL_77;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = a3;
      if ( !a3 )
        v16 = L"NULL";
      WPP_SF_dSdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)L"NULL",
        v15,
        v14 == 183,
        (__int64)v16,
        v8,
        CurrentThreadId);
    }
    v17 = WaitForSingleObject(Semaphore, 0x2710u);
    v18 = GetLastError();
    if ( v17 )
    {
      switch ( v17 )
      {
        case 0x80u:
          v8 = -2147024161;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v22 = GetCurrentThreadId();
            v24 = 15;
            goto LABEL_35;
          }
          break;
        case 0x102u:
          v8 = -2147024775;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v22 = GetCurrentThreadId();
            v24 = 14;
LABEL_35:
            if ( !a3 )
              a3 = L"NULL";
            WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v23, (_DWORD)a3, v22, v8);
          }
          break;
        case 0xFFFFFFFF:
          v8 = v18 > 0 ? (unsigned __int16)v18 | 0x80070000 : v18;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_77;
          v19 = GetCurrentThreadId();
          dwDesiredAccessa = v8;
          v21 = 13;
          dwFlags = v19;
          goto LABEL_74;
        default:
          goto LABEL_77;
      }
LABEL_80:
      CloseHandle(Semaphore);
      goto LABEL_82;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v25 = GetCurrentThreadId();
      LODWORD(v26) = (_DWORD)a3;
      if ( !a3 )
        v26 = L"NULL";
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_f65b0a976b663debdd800f933ed82b37_Traceguids,
        (_DWORD)v26,
        v25);
    }
    v27 = TBNCryptOpenKey((struct _TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *)a1, v46, 0, &hObject);
    if ( v27 == -2146893802 || v27 == -2146893807 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LODWORD(v28) = (_DWORD)a3;
        if ( !a3 )
          v28 = L"NULL";
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_f65b0a976b663debdd800f933ed82b37_Traceguids,
          (_DWORD)v28,
          v27);
      }
      v29 = TBNCryptDeleteKey(v42, a3);
      if ( v29 < 0 )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v33 = 19;
          goto LABEL_61;
        }
      }
      else
      {
        v30 = *((_OWORD *)v42 + 1);
        v44[0] = *(_OWORD *)v42;
        v31 = *(__int64 (__fastcall **)(_OWORD *, unsigned __int16 *, NCRYPT_HANDLE *))(a1 + 32);
        v45 = *((_QWORD *)v42 + 4);
        v44[1] = v30;
        v29 = v31(v44, v46, &hObject);
        if ( v29 < 0 )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v33 = 18;
LABEL_61:
            WPP_SF_d(v32[2], v33, &WPP_f65b0a976b663debdd800f933ed82b37_Traceguids, (unsigned int)v29);
          }
        }
      }
    }
    if ( ReleaseSemaphore(Semaphore, 1, 0) )
    {
      v8 = 0;
    }
    else
    {
      v34 = GetLastError();
      v8 = v34;
      if ( v34 > 0 )
        v8 = (unsigned __int16)v34 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( !a3 )
          a3 = L"NULL";
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_f65b0a976b663debdd800f933ed82b37_Traceguids,
          (_DWORD)a3,
          v8);
      }
    }
LABEL_77:
    if ( v8 >= 0 )
    {
      v35 = hObject;
      hObject = 0;
      *v47 = v35;
    }
    if ( !Semaphore )
      goto LABEL_82;
    goto LABEL_80;
  }
LABEL_82:
  if ( v46 )
    TBFree(v46);
  if ( v6 )
    TBFree(v6);
LABEL_86:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_f65b0a976b663debdd800f933ed82b37_Traceguids,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ebf78  mov     rax, rsp
0x1800ebf7b  mov     [rax+10h], rbx
0x1800ebf7f  mov     [rax+18h], rsi
0x1800ebf83  mov     [rax+20h], r9
0x1800ebf87  push    rbp
0x1800ebf88  push    rdi
0x1800ebf89  push    r12
0x1800ebf8b  push    r14
0x1800ebf8d  push    r15
0x1800ebf8f  lea     rbp, [rax-5Fh]
0x1800ebf93  sub     rsp, 90h
0x1800ebf9a  mov     r15, rcx
0x1800ebf9d  mov     [rbp+57h+var_68], 0
0x1800ebfa5  mov     esi, edx
0x1800ebfa7  mov     [rbp+57h+hObject], 0
0x1800ebfaf  xor     r12d, r12d
0x1800ebfb2  mov     [rbp+57h+arg_0], 0
0x1800ebfba  lea     rdx, [rbp+57h+var_68]
0x1800ebfbe  mov     [rbp+57h+lpName], r12
0x1800ebfc2  mov     rax, [r15+18h]
0x1800ebfc6  mov     ecx, esi
0x1800ebfc8  mov     rdi, r8
0x1800ebfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebfd0  lea     r14, WPP_GLOBAL_Control
0x1800ebfd7  mov     ebx, eax
0x1800ebfd9  test    eax, eax
0x1800ebfdb  js      loc_1800EC49A
0x1800ebfe1  lea     r8, [rbp+57h+arg_0]
0x1800ebfe5  mov     rdx, rdi
0x1800ebfe8  mov     ecx, esi
0x1800ebfea  call    TBCreateKeyName
0x1800ebfef  mov     ebx, eax
0x1800ebff1  test    eax, eax
0x1800ebff3  js      loc_1800EC47D
0x1800ebff9  mov     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x1800ebffd  lea     r9, [rbp+57h+hObject]; unsigned __int64 *
0x1800ec001  xor     r8d, r8d; int
0x1800ec004  mov     rcx, r15; struct _TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *
0x1800ec007  call    ?TBNCryptOpenKey@@YAJPEAU_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE@@PEBGHPEA_K@Z; TBNCryptOpenKey(_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *,ushort const *,int,unsigned __int64 *)
0x1800ec00c  mov     ebx, eax
0x1800ec00e  cmp     eax, 80090016h
0x1800ec013  jz      short loc_1800EC023
0x1800ec015  xor     r14d, r14d
0x1800ec018  cmp     eax, 80090011h
0x1800ec01d  jnz     loc_1800EC44B
0x1800ec023  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec02a  lea     rsi, WPP_GLOBAL_Control
0x1800ec031  lea     r14, aNull_1; "NULL"
0x1800ec038  cmp     rax, rsi
0x1800ec03b  jz      short loc_1800EC070
0x1800ec03d  test    byte ptr [rax+1Ch], 4
0x1800ec041  jz      short loc_1800EC070
0x1800ec043  call    cs:__imp_GetCurrentThreadId
0x1800ec049  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec050  test    rdi, rdi
0x1800ec053  mov     dword ptr [rsp+0B0h+dwDesiredAccess], eax
0x1800ec057  mov     r9, rdi
0x1800ec05a  cmovz   r9, r14
0x1800ec05e  mov     dword ptr [rsp+0B0h+dwFlags], ebx
0x1800ec062  mov     edx, 0Ah
0x1800ec067  mov     rcx, [rcx+10h]
0x1800ec06b  call    WPP_SF_Sdd
0x1800ec070  mov     rcx, [rbp+57h+arg_0]; unsigned __int16 *
0x1800ec074  lea     rdx, [rbp+57h+lpName]
0x1800ec078  call    TBCreateSemaphoreName
0x1800ec07d  mov     ebx, eax
0x1800ec07f  test    eax, eax
0x1800ec081  js      loc_1800EC472
0x1800ec087  mov     eax, 1
0x1800ec08c  mov     dword ptr [rsp+0B0h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800ec094  mov     dword ptr [rsp+0B0h+dwFlags], r12d; dwFlags
0x1800ec099  mov     r8d, eax; lMaximumCount
0x1800ec09c  mov     r12, [rbp+57h+lpName]
0x1800ec0a0  mov     edx, eax; lInitialCount
0x1800ec0a2  mov     r9, r12; lpName
0x1800ec0a5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800ec0a7  call    cs:__imp_CreateSemaphoreExW
0x1800ec0ad  mov     r14, rax
0x1800ec0b0  call    cs:__imp_GetLastError
0x1800ec0b6  mov     esi, eax
0x1800ec0b8  test    eax, eax
0x1800ec0ba  jg      short loc_1800EC0C0
0x1800ec0bc  mov     ebx, eax
0x1800ec0be  jmp     short loc_1800EC0C9
0x1800ec0c0  movzx   ebx, si
0x1800ec0c3  or      ebx, 80070000h
0x1800ec0c9  test    r14, r14
0x1800ec0cc  jz      loc_1800EC3FE
0x1800ec0d2  test    esi, esi
0x1800ec0d4  jz      short loc_1800EC0E2
0x1800ec0d6  cmp     esi, 0B7h
0x1800ec0dc  jnz     loc_1800EC3FE
0x1800ec0e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec0e9  lea     rcx, WPP_GLOBAL_Control
0x1800ec0f0  cmp     rax, rcx
0x1800ec0f3  jz      short loc_1800EC13C
0x1800ec0f5  test    byte ptr [rax+1Ch], 4
0x1800ec0f9  jz      short loc_1800EC13C
0x1800ec0fb  call    cs:__imp_GetCurrentThreadId
0x1800ec101  test    rdi, rdi
0x1800ec104  mov     dword ptr [rsp+0B0h+var_80], eax
0x1800ec108  lea     rdx, aNull_1; "NULL"
0x1800ec10f  mov     dword ptr [rsp+0B0h+dwDesiredAccess], ebx
0x1800ec113  mov     rcx, rdi
0x1800ec116  cmovz   rcx, rdx
0x1800ec11a  xor     r9d, r9d
0x1800ec11d  mov     qword ptr [rsp+0B0h+dwFlags], rcx
0x1800ec122  cmp     esi, 0B7h
0x1800ec128  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec12f  setz    r9b
0x1800ec133  mov     rcx, [rcx+10h]
0x1800ec137  call    WPP_SF_dSdd
0x1800ec13c  mov     edx, 2710h; dwMilliseconds
0x1800ec141  mov     rcx, r14; hHandle
0x1800ec144  call    cs:__imp_WaitForSingleObject
0x1800ec14a  mov     esi, eax
0x1800ec14c  call    cs:__imp_GetLastError
0x1800ec152  test    esi, esi
0x1800ec154  jz      loc_1800EC253
0x1800ec15a  cmp     esi, 80h
0x1800ec160  jz      loc_1800EC220
0x1800ec166  cmp     esi, 102h
0x1800ec16c  jz      short loc_1800EC1C1
0x1800ec16e  cmp     esi, 0FFFFFFFFh
0x1800ec171  jnz     loc_1800EC44B
0x1800ec177  test    eax, eax
0x1800ec179  jg      short loc_1800EC17F
0x1800ec17b  mov     ebx, eax
0x1800ec17d  jmp     short loc_1800EC188
0x1800ec17f  movzx   ebx, ax
0x1800ec182  or      ebx, 80070000h
0x1800ec188  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec18f  lea     rax, WPP_GLOBAL_Control
0x1800ec196  cmp     rcx, rax
0x1800ec199  jz      loc_1800EC44B
0x1800ec19f  test    byte ptr [rcx+1Ch], 4
0x1800ec1a3  jz      loc_1800EC44B
0x1800ec1a9  call    cs:__imp_GetCurrentThreadId
0x1800ec1af  mov     dword ptr [rsp+0B0h+dwDesiredAccess], ebx
0x1800ec1b3  mov     edx, 0Dh
0x1800ec1b8  mov     dword ptr [rsp+0B0h+dwFlags], eax
0x1800ec1bc  jmp     loc_1800EC42A
0x1800ec1c1  mov     ebx, 80070079h
0x1800ec1c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec1cd  lea     rcx, WPP_GLOBAL_Control
0x1800ec1d4  cmp     rax, rcx
0x1800ec1d7  jz      loc_1800EC467
0x1800ec1dd  test    byte ptr [rax+1Ch], 4
0x1800ec1e1  jz      loc_1800EC467
0x1800ec1e7  call    cs:__imp_GetCurrentThreadId
0x1800ec1ed  mov     edx, 0Eh
0x1800ec1f2  test    rdi, rdi
0x1800ec1f5  mov     dword ptr [rsp+0B0h+dwDesiredAccess], ebx
0x1800ec1f9  lea     rcx, aNull_1; "NULL"
0x1800ec200  mov     dword ptr [rsp+0B0h+dwFlags], eax
0x1800ec204  cmovz   rdi, rcx
0x1800ec208  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec20f  mov     r9, rdi
0x1800ec212  mov     rcx, [rcx+10h]
0x1800ec216  call    WPP_SF_Sdd
0x1800ec21b  jmp     loc_1800EC467
0x1800ec220  mov     ebx, 800702DFh
0x1800ec225  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec22c  lea     rcx, WPP_GLOBAL_Control
0x1800ec233  cmp     rax, rcx
0x1800ec236  jz      loc_1800EC467
0x1800ec23c  test    byte ptr [rax+1Ch], 4
0x1800ec240  jz      loc_1800EC467
0x1800ec246  call    cs:__imp_GetCurrentThreadId
0x1800ec24c  mov     edx, 0Fh
0x1800ec251  jmp     short loc_1800EC1F2
0x1800ec253  mov     rax, cs:WPP_GLOBAL_Control
0x1800ec25a  lea     rsi, WPP_GLOBAL_Control
0x1800ec261  cmp     rax, rsi
0x1800ec264  jz      short loc_1800EC2A5
0x1800ec266  test    byte ptr [rax+1Ch], 4
0x1800ec26a  jz      short loc_1800EC2A5
0x1800ec26c  call    cs:__imp_GetCurrentThreadId
0x1800ec272  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec279  lea     rbx, aNull_1; "NULL"
0x1800ec280  test    rdi, rdi
0x1800ec283  mov     dword ptr [rsp+0B0h+dwFlags], eax
0x1800ec287  mov     r9, rdi
0x1800ec28a  lea     r8, WPP_f65b0a976b663debdd800f933ed82b37_Traceguids
0x1800ec291  cmovz   r9, rbx
0x1800ec295  mov     edx, 10h
0x1800ec29a  mov     rcx, [rcx+10h]
0x1800ec29e  call    WPP_SF_Sd
0x1800ec2a3  jmp     short loc_1800EC2AC
0x1800ec2a5  lea     rbx, aNull_1; "NULL"
0x1800ec2ac  mov     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x1800ec2b0  lea     r9, [rbp+57h+hObject]; unsigned __int64 *
0x1800ec2b4  xor     r8d, r8d; int
0x1800ec2b7  mov     rcx, r15; struct _TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *
0x1800ec2ba  call    ?TBNCryptOpenKey@@YAJPEAU_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE@@PEBGHPEA_K@Z; TBNCryptOpenKey(_TOKENBINDING_NCRYPT_INTERNAL_INTERFACE *,ushort const *,int,unsigned __int64 *)
0x1800ec2bf  cmp     eax, 80090016h
0x1800ec2c4  jz      short loc_1800EC2D1
0x1800ec2c6  cmp     eax, 80090011h
0x1800ec2cb  jnz     loc_1800EC38F
0x1800ec2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec2d8  cmp     rcx, rsi
0x1800ec2db  jz      short loc_1800EC306
0x1800ec2dd  test    byte ptr [rcx+1Ch], 4
0x1800ec2e1  jz      short loc_1800EC306
0x1800ec2e3  mov     rcx, [rcx+10h]
0x1800ec2e7  lea     r8, WPP_f65b0a976b663debdd800f933ed82b37_Traceguids
0x1800ec2ee  test    rdi, rdi
0x1800ec2f1  mov     dword ptr [rsp+0B0h+dwFlags], eax
0x1800ec2f5  mov     r9, rdi
0x1800ec2f8  mov     edx, 11h
0x1800ec2fd  cmovz   r9, rbx
0x1800ec301  call    WPP_SF_Sd
0x1800ec306  mov     rcx, [rbp+57h+var_68]; enum TOKENBINDING_KEY_PARAMETERS_TYPE *
0x1800ec30a  mov     rdx, rdi; unsigned __int16 *
0x1800ec30d  call    ?TBNCryptDeleteKey@@YAJPEAW4TOKENBINDING_KEY_PARAMETERS_TYPE@@PEBG@Z; TBNCryptDeleteKey(TOKENBINDING_KEY_PARAMETERS_TYPE *,ushort const *)
0x1800ec312  test    eax, eax
0x1800ec314  js      short loc_1800EC365
0x1800ec316  mov     rax, [rbp+57h+var_68]
0x1800ec31a  lea     r8, [rbp+57h+hObject]
0x1800ec31e  mov     rdx, [rbp+57h+arg_0]
0x1800ec322  lea     rcx, [rbp+57h+var_50]
0x1800ec326  movups  xmm0, xmmword ptr [rax]
0x1800ec329  movups  xmm1, xmmword ptr [rax+10h]
0x1800ec32d  movaps  [rbp+57h+var_50], xmm0
0x1800ec331  movsd   xmm0, qword ptr [rax+20h]
0x1800ec336  mov     rax, [r15+20h]
0x1800ec33a  movsd   [rbp+57h+var_30], xmm0
0x1800ec33f  movaps  [rbp+57h+var_40], xmm1
0x1800ec343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec348  test    eax, eax
0x1800ec34a  jns     short loc_1800EC38F
0x1800ec34c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec353  cmp     rcx, rsi
0x1800ec356  jz      short loc_1800EC38F
0x1800ec358  test    byte ptr [rcx+1Ch], 4
0x1800ec35c  jz      short loc_1800EC38F
0x1800ec35e  mov     edx, 12h
0x1800ec363  jmp     short loc_1800EC37C
0x1800ec365  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec36c  cmp     rcx, rsi
0x1800ec36f  jz      short loc_1800EC38F
0x1800ec371  test    byte ptr [rcx+1Ch], 4
0x1800ec375  jz      short loc_1800EC38F
0x1800ec377  mov     edx, 13h
0x1800ec37c  mov     rcx, [rcx+10h]
0x1800ec380  lea     r8, WPP_f65b0a976b663debdd800f933ed82b37_Traceguids
0x1800ec387  mov     r9d, eax
0x1800ec38a  call    WPP_SF_d
0x1800ec38f  xor     r8d, r8d; lpPreviousCount
0x1800ec392  mov     rcx, r14; hSemaphore
0x1800ec395  lea     edx, [r8+1]; lReleaseCount
0x1800ec399  call    cs:__imp_ReleaseSemaphore
0x1800ec39f  test    eax, eax
0x1800ec3a1  jnz     short loc_1800EC3FA
0x1800ec3a3  call    cs:__imp_GetLastError
0x1800ec3a9  mov     ebx, eax
0x1800ec3ab  test    eax, eax
0x1800ec3ad  jle     short loc_1800EC3B8
0x1800ec3af  movzx   ebx, ax
0x1800ec3b2  or      ebx, 80070000h
0x1800ec3b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec3bf  cmp     rcx, rsi
0x1800ec3c2  jz      loc_1800EC44B
0x1800ec3c8  test    byte ptr [rcx+1Ch], 4
0x1800ec3cc  jz      short loc_1800EC44B
0x1800ec3ce  mov     rcx, [rcx+10h]
0x1800ec3d2  lea     rax, aNull_1; "NULL"
0x1800ec3d9  test    rdi, rdi
0x1800ec3dc  mov     dword ptr [rsp+0B0h+dwFlags], ebx
0x1800ec3e0  mov     edx, 14h
0x1800ec3e5  lea     r8, WPP_f65b0a976b663debdd800f933ed82b37_Traceguids
0x1800ec3ec  cmovz   rdi, rax
0x1800ec3f0  mov     r9, rdi
0x1800ec3f3  call    WPP_SF_Sd
0x1800ec3f8  jmp     short loc_1800EC44B
0x1800ec3fa  xor     ebx, ebx
0x1800ec3fc  jmp     short loc_1800EC44B
0x1800ec3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec405  lea     rax, WPP_GLOBAL_Control
0x1800ec40c  cmp     rcx, rax
0x1800ec40f  jz      short loc_1800EC44B
0x1800ec411  test    byte ptr [rcx+1Ch], 4
0x1800ec415  jz      short loc_1800EC44B
0x1800ec417  call    cs:__imp_GetCurrentThreadId
0x1800ec41d  mov     dword ptr [rsp+0B0h+dwDesiredAccess], eax
0x1800ec421  mov     edx, 0Bh
0x1800ec426  mov     dword ptr [rsp+0B0h+dwFlags], ebx
0x1800ec42a  test    rdi, rdi
0x1800ec42d  lea     rcx, aNull_1; "NULL"
0x1800ec434  cmovz   rdi, rcx
0x1800ec438  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ec43f  mov     r9, rdi
0x1800ec442  mov     rcx, [rcx+10h]
0x1800ec446  call    WPP_SF_Sdd
0x1800ec44b  test    ebx, ebx
0x1800ec44d  js      short loc_1800EC462
0x1800ec44f  mov     rax, [rbp+57h+hObject]
0x1800ec453  mov     rcx, [rbp+57h+arg_18]
0x1800ec457  mov     [rbp+57h+hObject], 0
0x1800ec45f  mov     [rcx], rax
  ... truncated ...
```

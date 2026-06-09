# LoadProviderEx

- ea: `0x180007d60`
- end: `0x180008888`
- name: `LoadProviderEx`
- size: `2856`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x180007d60`
- `0x18000a070`
- `0x18000dac4`
- `0x18000fa6c`
- `0x18001aa70`
- `0x18001b79d`
- `0x18001c010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180007dbf`
- `ntdll!_wcsicmp` at `0x180007dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d9d`

## string_xrefs

- `0x180007e33`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180007f00`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180007f16`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180007f5c`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180007f8d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000808e`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008102`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008150`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008188`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800081c1`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000823e`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008393`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008692`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008748`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000877d`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800087ac`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x1800087e0`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadProviderEx(__int64 a1, int a2, __int64 a3, __int64 *a4, void *a5)
{
  const char *v7; // rdx
  __int16 *v8; // r8
  __int64 i; // rbx
  HMODULE v10; // r12
  unsigned int v11; // eax
  const CHAR *v12; // rdx
  FARPROC ProcAddress; // r10
  unsigned int v14; // esi
  int v15; // r14d
  int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  unsigned int v20; // ecx
  char v21; // al
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // r8d
  int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v31; // r8d
  __int64 v32; // rax
  int v33; // kr08_4
  __int64 v34; // rcx
  unsigned int v35; // eax
  void *Src; // [rsp+40h] [rbp-28h] BYREF
  HMODULE v37; // [rsp+48h] [rbp-20h] BYREF
  __int64 v38[3]; // [rsp+50h] [rbp-18h] BYREF
  int v39; // [rsp+C0h] [rbp+58h]

  Src = 0;
  v37 = 0;
  if ( g_fLoaderInitialized )
  {
    EnterCriticalSection(&g_csLoaderLock);
    for ( i = g_pLoadedProviderList; i; i = *(_QWORD *)(i + 24) )
    {
      if ( !_wcsicmp(**(const wchar_t ***)(a1 + 40), *(const wchar_t **)i) )
        break;
    }
    v38[0] = i;
    if ( i )
    {
      v10 = *(HMODULE *)(i + 8);
    }
    else
    {
      v29 = LoadImage(a1, &v37);
      v14 = v29;
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v7,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            (unsigned int)"sResult",
            v29,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            169);
        v10 = v37;
        v16 = 1;
        goto LABEL_16;
      }
      v10 = v37;
    }
    v11 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 == 2 )
    {
      v12 = "GetHashInterface";
    }
    else if ( v11 == 1 )
    {
      v12 = "GetCipherInterface";
    }
    else if ( v11 > 0x10001 )
    {
      v17 = v11 - 65538;
      if ( v17 )
      {
        if ( v17 != 2 )
        {
LABEL_26:
          v14 = -1073741637;
          LOBYTE(v15) = -69;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v7,
              (_DWORD)v8,
              (unsigned int)"sResult",
              187,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              104);
          goto LABEL_13;
        }
        v12 = "GetKeyProtectionInterface";
      }
      else
      {
        v12 = "GetSChannelInterface";
      }
    }
    else
    {
      if ( v11 != 65537 )
      {
        switch ( v11 )
        {
          case 3u:
            v12 = "GetAsymmetricEncryptionInterface";
            goto LABEL_9;
          case 4u:
            v12 = "GetSecretAgreementInterface";
            goto LABEL_9;
          case 5u:
            v12 = "GetSignatureInterface";
            goto LABEL_9;
          case 6u:
            v12 = "GetRngInterface";
            goto LABEL_9;
          case 7u:
            v12 = "GetKeyDerivationInterface";
            goto LABEL_9;
          case 8u:
            v12 = "GetKeyEncapsulationInterface";
            goto LABEL_9;
          default:
            goto LABEL_26;
        }
      }
      v12 = "GetKeyStorageInterface";
    }
LABEL_9:
    ProcAddress = GetProcAddress(v10, v12);
    if ( !ProcAddress )
    {
      v14 = -1073741511;
      LOBYTE(v15) = 57;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v7,
          (_DWORD)v8,
          (unsigned int)"sResult",
          57,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          115);
      goto LABEL_13;
    }
    v18 = *(_DWORD *)a1;
    if ( *(_DWORD *)a1 == 1 )
    {
      v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
              *(_QWORD *)(a1 + 16),
              *(_QWORD *)(a1 + 8),
              &Src,
              0);
      v15 = v19;
      if ( v19 >= 0 )
        goto LABEL_31;
      goto LABEL_135;
    }
    if ( v18 == 65540 )
    {
      v27 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 16), &Src, 0);
      v15 = v27;
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v7,
            (_DWORD)v8,
            (unsigned int)"ntStatus",
            v27,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            60);
        goto LABEL_36;
      }
      goto LABEL_31;
    }
    if ( v18 > 0x10001 )
    {
      if ( v18 != 65538 )
      {
LABEL_133:
        v15 = -1073741637;
        v34 = 3221225659LL;
LABEL_35:
        DebugTraceError(v34, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
LABEL_36:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v7,
            (_DWORD)v8,
            (unsigned int)"sResult",
            v15,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
            135);
LABEL_39:
        v14 = v15;
        if ( v15 )
        {
LABEL_13:
          v16 = 1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v7,
              (_DWORD)v8,
              (unsigned int)"sResult",
              v15,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              186);
          goto LABEL_16;
        }
        v22 = *(_DWORD *)a1;
        if ( *(_DWORD *)a1 == 1 )
        {
LABEL_41:
          v23 = 96;
        }
        else if ( v22 > 0x10001 )
        {
          v35 = v22 - 65538;
          if ( v35 )
          {
            if ( v35 != 2 )
            {
LABEL_149:
              v14 = -1073741811;
              DebugTraceError(3221225485LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
              goto LABEL_153;
            }
            v23 = 40;
          }
          else
          {
            v23 = 392;
          }
        }
        else
        {
          if ( v22 != 65537 )
          {
            switch ( v22 )
            {
              case 2u:
              case 5u:
              case 8u:
                goto LABEL_41;
              case 3u:
                v23 = 112;
                goto LABEL_42;
              case 4u:
                v23 = 104;
                goto LABEL_42;
              case 6u:
                v23 = 48;
                goto LABEL_42;
              case 7u:
                v23 = 88;
                goto LABEL_42;
              default:
                goto LABEL_149;
            }
          }
          v23 = 256;
        }
LABEL_42:
        memcpy_0(a5, Src, v23);
        if ( i )
        {
          v24 = *(_DWORD *)(i + 16);
          v25 = v24 + 1;
          if ( v24 + 1 >= v24 )
          {
            *(_DWORD *)(i + 16) = v25;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v25, a1, i, *(_QWORD *)i, v25);
            }
LABEL_47:
            *a4 = i;
LABEL_48:
            LeaveCriticalSection(&g_csLoaderLock);
            return v14;
          }
          v14 = -1073741670;
          DebugTraceError(3221225626LL, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
        }
        else
        {
          v30 = NewLoadedProviderHandle(a1, v10, v38);
          v14 = v30;
          if ( !v30 )
          {
            i = v38[0];
            v32 = g_pLoadedProviderList;
            g_pLoadedProviderList = v38[0];
            *(_QWORD *)(v38[0] + 24) = v32;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            {
              WPP_SF_qqSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v31, a1, i, *(_QWORD *)i, *(_DWORD *)(i + 16));
            }
            goto LABEL_47;
          }
          DebugTraceError(v30, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
          i = v38[0];
        }
LABEL_153:
        v16 = 1;
LABEL_16:
        if ( !i && v10 )
          FreeImage(v10);
        goto LABEL_17;
      }
      v19 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 16), &Src, 0);
      v15 = v19;
      if ( v19 >= 0 )
      {
LABEL_31:
        v20 = *(_DWORD *)a1;
        v7 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c";
        v39 = 0;
        if ( *(_DWORD *)a1 == 1 )
        {
          if ( *(_WORD *)Src )
            goto LABEL_33;
          DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
          v21 = -69;
          v7 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c";
          v15 = -1073741637;
LABEL_66:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              (_DWORD)v8,
              (unsigned int)"sResult",
              v21,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
              130);
          goto LABEL_39;
        }
        if ( v20 > 0x10001 )
        {
          v28 = v20 - 65538;
          if ( v28 )
          {
            if ( v28 != 2 )
            {
LABEL_62:
              v21 = -69;
              v7 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c";
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                  (_DWORD)v8,
                  (unsigned int)"ntStatus",
                  187,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
                  170);
                v21 = -69;
                v7 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c";
              }
              v15 = -1073741637;
              goto LABEL_66;
            }
            if ( !*(_WORD *)Src )
            {
              v39 = -1073741637;
LABEL_73:
              DebugTraceError(3221225659LL, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
              v7 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c";
            }
          }
          else if ( !*(_WORD *)Src )
          {
            v39 = -1073741637;
            goto LABEL_73;
          }
        }
        else
        {
          if ( v20 != 65537 )
          {
            v33 = (int)v8;
            v8 = &_ImageBase;
            switch ( v20 )
            {
              case 2u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 3u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 4u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 5u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 6u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 7u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              case 8u:
                if ( *(_WORD *)Src )
                  goto LABEL_33;
                v39 = -1073741637;
                break;
              default:
                LODWORD(v8) = v33;
                goto LABEL_62;
            }
            goto LABEL_73;
          }
          if ( !*(_WORD *)Src )
          {
            v39 = -1073741637;
            goto LABEL_73;
          }
        }
LABEL_33:
        v21 = v39;
        v15 = v39;
        if ( v39 >= 0 )
          goto LABEL_39;
        goto LABEL_66;
      }
    }
    else
    {
      if ( v18 != 65537 )
      {
        switch ( v18 )
        {
          case 2u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 3u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 4u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 5u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 6u:
            v19 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 16), &Src, 0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 7u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          case 8u:
            v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void **, _QWORD))ProcAddress)(
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 8),
                    &Src,
                    0);
            v15 = v19;
            if ( v19 < 0 )
              goto LABEL_135;
            goto LABEL_31;
          default:
            goto LABEL_133;
        }
      }
      v19 = ((__int64 (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(*(_QWORD *)(a1 + 16), &Src, 0);
      v15 = v19;
      if ( v19 >= 0 )
        goto LABEL_31;
    }
LABEL_135:
    v34 = (unsigned int)v19;
    goto LABEL_35;
  }
  v16 = 0;
  v14 = -1073741595;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      (unsigned int)"sResult",
      229,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      143);
LABEL_17:
  *a4 = 0;
  if ( v16 )
    goto LABEL_48;
  return v14;
}

```

## disassembly

```asm
0x180007d60  mov     [rsp-40h+arg_10], r8d
0x180007d65  push    rbp
0x180007d66  push    rbx
0x180007d67  push    rsi
0x180007d68  push    rdi
0x180007d69  push    r12
0x180007d6b  push    r13
0x180007d6d  push    r14
0x180007d6f  push    r15
0x180007d71  mov     rbp, rsp
0x180007d74  sub     rsp, 68h
0x180007d78  xor     r14d, r14d
0x180007d7b  mov     r13, r9
0x180007d7e  cmp     cs:g_fLoaderInitialized, r14d
0x180007d85  mov     rdi, rcx
0x180007d88  mov     [rbp+Src], r14
0x180007d8c  mov     [rbp+var_20], r14
0x180007d90  jz      loc_180008061
0x180007d96  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180007d9d  call    cs:__imp_EnterCriticalSection
0x180007da4  nop     dword ptr [rax+rax+00h]
0x180007da9  mov     rbx, cs:g_pLoadedProviderList
0x180007db0  test    rbx, rbx
0x180007db3  jz      short loc_180007DD8
0x180007db5  mov     rcx, [rdi+28h]
0x180007db9  mov     rdx, [rbx]; String2
0x180007dbc  mov     rcx, [rcx]; String1
0x180007dbf  call    cs:__imp__wcsicmp
0x180007dc6  nop     dword ptr [rax+rax+00h]
0x180007dcb  test    eax, eax
0x180007dcd  jz      short loc_180007DD8
0x180007dcf  mov     rbx, [rbx+18h]
0x180007dd3  test    rbx, rbx
0x180007dd6  jnz     short loc_180007DB5
0x180007dd8  mov     [rbp+var_18], rbx
0x180007ddc  test    rbx, rbx
0x180007ddf  jz      loc_18000824A
0x180007de5  mov     r12, [rbx+8]
0x180007de9  mov     eax, [rdi]
0x180007deb  lea     r14, __ImageBase
0x180007df2  cmp     eax, 2
0x180007df5  jnz     loc_180007E9F
0x180007dfb  lea     rdx, ProcName; "GetHashInterface"
0x180007e02  mov     rcx, r12; hModule
0x180007e05  call    cs:__imp_GetProcAddress
0x180007e0c  nop     dword ptr [rax+rax+00h]
0x180007e11  mov     r10, rax
0x180007e14  test    rax, rax
0x180007e17  jnz     loc_180007F22
0x180007e1d  mov     esi, 0C0000139h
0x180007e22  mov     r14d, esi
0x180007e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e2c  lea     r15, WPP_GLOBAL_Control
0x180007e33  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007e3a  cmp     rcx, r15
0x180007e3d  jz      short loc_180007E49
0x180007e3f  test    byte ptr [rcx+1Ch], 1
0x180007e43  jnz     loc_18000860E
0x180007e49  mov     edi, 1
0x180007e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e55  cmp     rcx, r15
0x180007e58  jz      short loc_180007E82
0x180007e5a  test    [rcx+1Ch], dil
0x180007e5e  jz      short loc_180007E82
0x180007e60  mov     rcx, [rcx+10h]
0x180007e64  lea     r9, aSresult; "sResult"
0x180007e6b  mov     [rsp+68h+var_38], 9BAh
0x180007e73  mov     [rsp+68h+var_40], rax
0x180007e78  mov     dword ptr [rsp+68h+var_48], r14d
0x180007e7d  call    WPP_SF_sDsd
0x180007e82  xor     r14d, r14d
0x180007e85  test    rbx, rbx
0x180007e88  jz      loc_180008803
0x180007e8e  mov     [r13+0], r14
0x180007e92  test    edi, edi
0x180007e94  jz      loc_18000804D
0x180007e9a  jmp     loc_18000803A
0x180007e9f  cmp     eax, 1
0x180007ea2  jnz     short loc_180007EB0
0x180007ea4  lea     rdx, aGetcipherinter_0; "GetCipherInterface"
0x180007eab  jmp     loc_180007E02
0x180007eb0  cmp     eax, 10001h
0x180007eb5  ja      short loc_180007ED6
0x180007eb7  jz      loc_1800085EA
0x180007ebd  add     eax, 0FFFFFFFDh; switch 6 cases
0x180007ec0  cmp     eax, 5
0x180007ec3  ja      short def_180007ED0; jumptable 0000000180007ED0 default case
0x180007ec5  mov     eax, ds:(jpt_180007ED0 - 180000000h)[r14+rax*4]
0x180007ecd  add     rax, r14
0x180007ed0  jmp     rax; switch jump
0x180007ed6  sub     eax, 10002h
0x180007edb  jz      loc_180008602
0x180007ee1  cmp     eax, 2
0x180007ee4  jz      loc_1800085F6
0x180007eea  mov     esi, 0C00000BBh; jumptable 0000000180007ED0 default case
0x180007eef  mov     r14d, esi
0x180007ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ef9  lea     r15, WPP_GLOBAL_Control
0x180007f00  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f07  cmp     rcx, r15
0x180007f0a  jz      short loc_180007F16
0x180007f0c  test    byte ptr [rcx+1Ch], 1
0x180007f10  jnz     loc_18000812B
0x180007f16  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f1d  jmp     loc_180007E49
0x180007f22  mov     eax, [rdi]
0x180007f24  lea     r15, WPP_GLOBAL_Control
0x180007f2b  mov     esi, 1
0x180007f30  cmp     eax, esi
0x180007f32  jnz     loc_1800080BB
0x180007f38  mov     rdx, [rdi+8]
0x180007f3c  lea     r8, [rbp+Src]
0x180007f40  mov     rcx, [rdi+10h]
0x180007f44  xor     r9d, r9d
0x180007f47  mov     rax, r10
0x180007f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f4f  mov     r14d, eax
0x180007f52  test    eax, eax
0x180007f54  js      loc_18000869E
0x180007f5a  mov     ecx, [rdi]
0x180007f5c  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f63  xor     eax, eax
0x180007f65  mov     [rbp+arg_10], eax
0x180007f68  cmp     ecx, esi
0x180007f6a  jnz     loc_18000815C
0x180007f70  mov     rax, [rbp+Src]
0x180007f74  cmp     si, [rax]
0x180007f77  ja      loc_180008727
0x180007f7d  mov     eax, [rbp+arg_10]
0x180007f80  mov     r14d, eax
0x180007f83  test    eax, eax
0x180007f85  js      loc_1800081CB
0x180007f8b  jmp     short loc_180007FD7
0x180007f8d  lea     rsi, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f94  mov     r8, rsi
0x180007f97  lea     rdx, aNtstatus; "ntStatus"
0x180007f9e  call    DebugTraceError
0x180007fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007faa  cmp     rcx, r15
0x180007fad  jz      short loc_180007FD7
0x180007faf  test    byte ptr [rcx+1Ch], 1
0x180007fb3  jz      short loc_180007FD7
0x180007fb5  mov     [rsp+68h+var_38], 787h
0x180007fbd  mov     [rsp+68h+var_40], rsi
0x180007fc2  mov     dword ptr [rsp+68h+var_48], r14d
0x180007fc7  mov     rcx, [rcx+10h]
0x180007fcb  lea     r9, aSresult; "sResult"
0x180007fd2  call    WPP_SF_sDsd
0x180007fd7  mov     esi, r14d
0x180007fda  test    r14d, r14d
0x180007fdd  jnz     loc_180007F16
0x180007fe3  mov     eax, [rdi]
0x180007fe5  cmp     eax, 1
0x180007fe8  jnz     loc_180008275
0x180007fee  mov     eax, 60h ; '`'; jumptable 00000001800082A3 cases 2,5,8
0x180007ff3  mov     rdx, [rbp+Src]; Src
0x180007ff7  mov     rcx, [rbp+arg_20]; void *
0x180007ffb  mov     r8d, eax; Size
0x180007ffe  call    memcpy_0
0x180008003  test    rbx, rbx
0x180008006  jz      loc_1800082F7
0x18000800c  mov     eax, [rbx+10h]
0x18000800f  lea     r8d, [rax+1]
0x180008013  cmp     r8d, eax
0x180008016  jb      loc_1800087A6
0x18000801c  mov     [rbx+10h], r8d
0x180008020  mov     rcx, cs:WPP_GLOBAL_Control
0x180008027  cmp     rcx, r15
0x18000802a  jz      short loc_180008036
0x18000802c  test    byte ptr [rcx+1Ch], 20h
0x180008030  jnz     loc_1800087CB
0x180008036  mov     [r13+0], rbx
0x18000803a  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180008041  call    cs:__imp_LeaveCriticalSection
0x180008048  nop     dword ptr [rax+rax+00h]
0x18000804d  mov     eax, esi
0x18000804f  add     rsp, 68h
0x180008053  pop     r15
0x180008055  pop     r14
0x180008057  pop     r13
0x180008059  pop     r12
0x18000805b  pop     rdi
0x18000805c  pop     rsi
0x18000805d  pop     rbx
0x18000805e  pop     rbp
0x18000805f  retn
0x180008061  mov     edi, r14d
0x180008064  mov     esi, 0C00000E5h
0x180008069  mov     rcx, cs:WPP_GLOBAL_Control
0x180008070  lea     r15, WPP_GLOBAL_Control
0x180008077  cmp     rcx, r15
0x18000807a  jz      loc_180007E8E
0x180008080  test    byte ptr [rcx+1Ch], 1
0x180008084  jz      loc_180007E8E
0x18000808a  mov     rcx, [rcx+10h]
0x18000808e  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008095  mov     [rsp+68h+var_38], 98Fh
0x18000809d  lea     r9, aSresult; "sResult"
0x1800080a4  mov     [rsp+68h+var_40], r8
0x1800080a9  mov     dword ptr [rsp+68h+var_48], 0C00000E5h
0x1800080b1  call    WPP_SF_sDsd
0x1800080b6  jmp     loc_180007E8E
0x1800080bb  cmp     eax, 10004h
0x1800080c0  jnz     loc_1800082B3
0x1800080c6  mov     rcx, [rdi+10h]
0x1800080ca  lea     rdx, [rbp+Src]
0x1800080ce  xor     r8d, r8d
0x1800080d1  mov     rax, r10
0x1800080d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d9  mov     r14d, eax
0x1800080dc  test    eax, eax
0x1800080de  jns     loc_180007F5A
0x1800080e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080eb  cmp     rcx, r15
0x1800080ee  jz      loc_180008692
0x1800080f4  test    [rcx+1Ch], sil
0x1800080f8  jz      loc_180008692
0x1800080fe  mov     rcx, [rcx+10h]
0x180008102  lea     rsi, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008109  mov     [rsp+68h+var_38], 63Ch
0x180008111  lea     r9, aNtstatus; "ntStatus"
0x180008118  mov     [rsp+68h+var_40], rsi
0x18000811d  mov     dword ptr [rsp+68h+var_48], eax
0x180008121  call    WPP_SF_sDsd
0x180008126  jmp     loc_180007FA3
0x18000812b  mov     [rsp+68h+var_38], 768h
0x180008133  mov     [rsp+68h+var_40], rax
0x180008138  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x180008140  mov     rcx, [rcx+10h]
0x180008144  lea     r9, aSresult; "sResult"
0x18000814b  call    WPP_SF_sDsd
0x180008150  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008157  jmp     loc_180007E49
0x18000815c  cmp     ecx, 10001h
0x180008162  ja      loc_1800081FB
0x180008168  jz      loc_1800086E9
0x18000816e  add     ecx, 0FFFFFFFEh; switch 7 cases
0x180008171  cmp     ecx, 6
0x180008174  jbe     loc_180008465
0x18000817a  mov     esi, 0C00000BBh; jumptable 0000000180008477 default case
0x18000817f  mov     eax, esi
0x180008181  mov     rcx, cs:WPP_GLOBAL_Control
0x180008188  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000818f  cmp     rcx, r15
0x180008192  jz      short loc_1800081C8
0x180008194  test    byte ptr [rcx+1Ch], 1
0x180008198  jz      short loc_1800081C8
0x18000819a  mov     rcx, [rcx+10h]
0x18000819e  lea     r9, aNtstatus; "ntStatus"
0x1800081a5  mov     [rsp+68h+var_38], 5AAh
0x1800081ad  mov     [rsp+68h+var_40], rdx
0x1800081b2  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x1800081ba  call    WPP_SF_sDsd
0x1800081bf  mov     eax, esi
0x1800081c1  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800081c8  mov     r14d, esi
0x1800081cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081d2  cmp     rcx, r15
0x1800081d5  jz      loc_180007FD7
0x1800081db  test    byte ptr [rcx+1Ch], 1
0x1800081df  jz      loc_180007FD7
0x1800081e5  mov     [rsp+68h+var_38], 782h
0x1800081ed  mov     [rsp+68h+var_40], rdx
0x1800081f2  mov     dword ptr [rsp+68h+var_48], eax
0x1800081f6  jmp     loc_180007FC7
0x1800081fb  sub     ecx, 10002h
0x180008201  jz      loc_180008708
0x180008207  cmp     ecx, 2
0x18000820a  jnz     def_180008477; jumptable 0000000180008477 default case
0x180008210  mov     rax, [rbp+Src]
0x180008214  cmp     si, [rax]
0x180008217  jbe     loc_180007F7D
0x18000821d  mov     [rbp+arg_10], 0C00000BBh
0x180008224  mov     r9d, 59Ah
0x18000822a  mov     r8, rdx
0x18000822d  mov     ecx, 0C00000BBh
0x180008232  lea     rdx, aNtstatus; "ntStatus"
0x180008239  call    DebugTraceError
0x18000823e  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008245  jmp     loc_180007F7D
0x18000824a  lea     rdx, [rbp+var_20]
0x18000824e  mov     rcx, rdi
0x180008251  call    _LoadImage
0x180008256  mov     esi, eax
0x180008258  test    eax, eax
0x18000825a  jnz     loc_180008376
0x180008260  mov     r12, [rbp+var_20]
0x180008264  jmp     loc_180007DE9
0x180008269  lea     rdx, aGetrnginterfac_0; jumptable 0000000180007ED0 case 6
0x180008270  jmp     loc_180007E02
0x180008275  cmp     eax, 10001h
0x18000827a  ja      loc_180008761
0x180008280  jz      loc_180008757
0x180008286  add     eax, 0FFFFFFFEh; switch 7 cases
0x180008289  cmp     eax, 6
0x18000828c  ja      def_1800082A3; jumptable 00000001800082A3 default case
0x180008292  lea     rcx, __ImageBase
0x180008299  mov     eax, ds:(jpt_1800082A3 - 180000000h)[rcx+rax*4]
0x1800082a0  add     rax, rcx
0x1800082a3  jmp     rax; switch jump
  ... truncated ...
```

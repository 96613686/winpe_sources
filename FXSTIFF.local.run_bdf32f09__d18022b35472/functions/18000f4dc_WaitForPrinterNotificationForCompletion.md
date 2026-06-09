# WaitForPrinterNotificationForCompletion

- ea: `0x18000f4dc`
- end: `0x18000f7a6`
- name: `WaitForPrinterNotificationForCompletion`
- size: `714`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f2f8`

## callees

- `0x180009a7c`
- `0x180009aa4`
- `0x18000f4dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f5c0`
- `KERNEL32!GetLastError` at `0x18000f70a`
- `KERNEL32!GetLastError` at `0x18000f734`
- `KERNEL32!GetLastError` at `0x18000f5c0`
- `KERNEL32!GetLastError` at `0x18000f70a`
- `KERNEL32!GetLastError` at `0x18000f734`
- `KERNEL32!WaitForSingleObject` at `0x18000f60b`
- `KERNEL32!WaitForSingleObject` at `0x18000f6a9`
- `KERNEL32!WaitForSingleObject` at `0x18000f60b`
- `KERNEL32!WaitForSingleObject` at `0x18000f6a9`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18000f64e`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18000f64e`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18000f78a`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18000f78a`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18000f5b1`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18000f5b1`

## pseudocode

```c
__int64 __fastcall WaitForPrinterNotificationForCompletion(HANDLE hPrinter, int a2)
{
  _QWORD *v3; // rcx
  unsigned int v4; // ebx
  HANDLE v5; // rax
  void *v6; // rdi
  DWORD v7; // eax
  DWORD v8; // eax
  unsigned int v9; // edx
  __int64 v10; // rcx
  DWORD LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v16; // [rsp+20h] [rbp-50h] BYREF
  int v17; // [rsp+28h] [rbp-48h]
  int v18; // [rsp+2Ch] [rbp-44h]
  __int16 *v19; // [rsp+30h] [rbp-40h]
  _QWORD pPrinterNotifyOptions[3]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD pvReserved[4]; // [rsp+50h] [rbp-20h] BYREF
  DWORD pdwChange; // [rsp+A0h] [rbp+30h] BYREF
  __int16 v23; // [rsp+A8h] [rbp+38h] BYREF
  __int16 v24; // [rsp+AAh] [rbp+3Ah]
  LPVOID ppPrinterNotifyInfo; // [rsp+B0h] [rbp+40h] BYREF

  v24 = HIWORD(a2);
  v17 = 0;
  v23 = 10;
  v16 = 1;
  v19 = &v23;
  v18 = 1;
  pPrinterNotifyOptions[2] = &v16;
  pPrinterNotifyOptions[0] = 2;
  pPrinterNotifyOptions[1] = 1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !hPrinter )
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 2u )
      WPP_SF_(v3[2], 64, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    return v4;
  }
  v5 = FindFirstPrinterChangeNotification(hPrinter, 0x600u, 0, pPrinterNotifyOptions);
  v6 = v5;
  if ( v5 != (HANDLE)-1LL )
  {
    v8 = WaitForSingleObject(v5, 0x1F4u);
    if ( !v8 )
    {
      while ( 1 )
      {
        pdwChange = 1536;
        ppPrinterNotifyInfo = 0;
        pvReserved[0] = 2;
        pvReserved[1] = 0;
        pvReserved[2] = 0;
        if ( !FindNextPrinterChangeNotification(v6, &pdwChange, pvReserved, &ppPrinterNotifyInfo) )
          break;
        if ( (pdwChange & 0x600) != 0 )
        {
          if ( ppPrinterNotifyInfo )
          {
            v9 = 0;
            if ( *((_DWORD *)ppPrinterNotifyInfo + 2) )
            {
              while ( 1 )
              {
                v10 = 32LL * v9;
                if ( *(_WORD *)((char *)ppPrinterNotifyInfo + v10 + 16) == 1
                  && *(_WORD *)((char *)ppPrinterNotifyInfo + v10 + 18) == 10
                  && (*(_DWORD *)((_BYTE *)ppPrinterNotifyInfo + v10 + 32) & 0x180) != 0 )
                {
                  break;
                }
                if ( ++v9 >= *((_DWORD *)ppPrinterNotifyInfo + 2) )
                  goto LABEL_24;
              }
              v4 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
              }
              goto LABEL_46;
            }
          }
        }
LABEL_24:
        v8 = WaitForSingleObject(v6, 0x1F4u);
        if ( v8 )
          goto LABEL_25;
      }
      LastError = GetLastError();
      v4 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 68;
        goto LABEL_36;
      }
      goto LABEL_46;
    }
LABEL_25:
    v4 = 258;
    if ( v8 == 258 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v13 = 67;
      v14 = 258;
    }
    else
    {
      if ( v8 != -1 )
      {
        v4 = 1627;
LABEL_46:
        FindClosePrinterChangeNotification(v6);
        return v4;
      }
      LastError = GetLastError();
      v4 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v13 = 66;
LABEL_36:
      v14 = LastError;
    }
    WPP_SF_d(v12[2], v13, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v14);
    goto LABEL_46;
  }
  v7 = GetLastError();
  v4 = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v7);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f4dc  mov     [rsp-28h+arg_18], rbx
0x18000f4e1  mov     [rsp-28h+arg_8], edx
0x18000f4e5  push    rbp
0x18000f4e6  push    rsi
0x18000f4e7  push    rdi
0x18000f4e8  push    r12
0x18000f4ea  push    r15
0x18000f4ec  mov     rbp, rsp
0x18000f4ef  sub     rsp, 70h
0x18000f4f3  mov     eax, 0Ah
0x18000f4f8  mov     [rbp+var_48], 0
0x18000f4ff  mov     word ptr [rbp+arg_8], ax
0x18000f503  mov     rbx, rcx
0x18000f506  lea     ecx, [rax-9]
0x18000f509  lea     rax, [rbp+arg_8]
0x18000f50d  mov     [rbp+var_50], rcx
0x18000f511  mov     [rbp+var_40], rax
0x18000f515  lea     esi, [rcx+1]
0x18000f518  lea     rax, [rbp+var_50]
0x18000f51c  mov     [rbp+var_44], ecx
0x18000f51f  mov     [rbp+var_28], rax
0x18000f523  mov     [rbp+pPrinterNotifyOptions], rsi
0x18000f527  mov     [rbp+var_30], rcx
0x18000f52b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f532  lea     r15, WPP_GLOBAL_Control
0x18000f539  lea     r12, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18000f540  cmp     rcx, r15
0x18000f543  jz      short loc_18000F567
0x18000f545  test    [rcx+1Ch], sil
0x18000f549  jz      short loc_18000F567
0x18000f54b  cmp     byte ptr [rcx+19h], 5
0x18000f54f  jb      short loc_18000F567
0x18000f551  mov     rcx, [rcx+10h]
0x18000f555  lea     edx, [rsi+3Dh]
0x18000f558  mov     r8, r12
0x18000f55b  call    WPP_SF_
0x18000f560  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f567  test    rbx, rbx
0x18000f56a  jnz     short loc_18000F5A2
0x18000f56c  mov     ebx, 57h ; 'W'
0x18000f571  cmp     rcx, r15
0x18000f574  jz      loc_18000F790
0x18000f57a  test    [rcx+1Ch], sil
0x18000f57e  jz      loc_18000F790
0x18000f584  cmp     [rcx+19h], sil
0x18000f588  jb      loc_18000F790
0x18000f58e  mov     rcx, [rcx+10h]
0x18000f592  lea     edx, [rbx-17h]
0x18000f595  mov     r8, r12
0x18000f598  call    WPP_SF_
0x18000f59d  jmp     loc_18000F790
0x18000f5a2  lea     r9, [rbp+pPrinterNotifyOptions]; pPrinterNotifyOptions
0x18000f5a6  xor     r8d, r8d; fdwOptions
0x18000f5a9  mov     edx, 600h; fdwFilter
0x18000f5ae  mov     rcx, rbx; hPrinter
0x18000f5b1  call    cs:__imp_FindFirstPrinterChangeNotification
0x18000f5b7  mov     rdi, rax
0x18000f5ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f5be  jnz     short loc_18000F603
0x18000f5c0  call    cs:__imp_GetLastError
0x18000f5c6  mov     ebx, eax
0x18000f5c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5cf  cmp     rcx, r15
0x18000f5d2  jz      loc_18000F790
0x18000f5d8  test    [rcx+1Ch], sil
0x18000f5dc  jz      loc_18000F790
0x18000f5e2  cmp     [rcx+19h], sil
0x18000f5e6  jb      loc_18000F790
0x18000f5ec  mov     rcx, [rcx+10h]
0x18000f5f0  lea     edx, [rdi+42h]
0x18000f5f3  mov     r9d, eax
0x18000f5f6  mov     r8, r12
0x18000f5f9  call    WPP_SF_d
0x18000f5fe  jmp     loc_18000F790
0x18000f603  mov     edx, 1F4h; dwMilliseconds
0x18000f608  mov     rcx, rdi; hHandle
0x18000f60b  call    cs:__imp_WaitForSingleObject
0x18000f611  test    eax, eax
0x18000f613  jnz     loc_18000F6B7
0x18000f619  lea     ebx, [rax+1]
0x18000f61c  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x18000f620  mov     [rbp+pdwChange], 600h
0x18000f627  lea     r8, [rbp+pvReserved]; pvReserved
0x18000f62b  mov     [rbp+ppPrinterNotifyInfo], 0
0x18000f633  lea     rdx, [rbp+pdwChange]; pdwChange
0x18000f637  mov     [rbp+pvReserved], rsi
0x18000f63b  mov     rcx, rdi; hChange
0x18000f63e  mov     [rbp+var_18], 0
0x18000f646  mov     [rbp+var_10], 0
0x18000f64e  call    cs:__imp_FindNextPrinterChangeNotification
0x18000f654  test    eax, eax
0x18000f656  jz      loc_18000F70A
0x18000f65c  test    [rbp+pdwChange], 600h
0x18000f663  jz      short loc_18000F6A1
0x18000f665  mov     rax, [rbp+ppPrinterNotifyInfo]
0x18000f669  test    rax, rax
0x18000f66c  jz      short loc_18000F6A1
0x18000f66e  xor     edx, edx
0x18000f670  cmp     [rax+8], edx
0x18000f673  jbe     short loc_18000F6A1
0x18000f675  mov     ecx, edx
0x18000f677  shl     rcx, 5
0x18000f67b  cmp     [rcx+rax+10h], bx
0x18000f680  jnz     short loc_18000F69A
0x18000f682  mov     r8d, 0Ah
0x18000f688  cmp     [rcx+rax+12h], r8w
0x18000f68e  jnz     short loc_18000F69A
0x18000f690  test    dword ptr [rcx+rax+20h], 180h
0x18000f698  jnz     short loc_18000F6D3
0x18000f69a  add     edx, ebx
0x18000f69c  cmp     edx, [rax+8]
0x18000f69f  jb      short loc_18000F675
0x18000f6a1  mov     edx, 1F4h; dwMilliseconds
0x18000f6a6  mov     rcx, rdi; hHandle
0x18000f6a9  call    cs:__imp_WaitForSingleObject
0x18000f6af  test    eax, eax
0x18000f6b1  jz      loc_18000F61C
0x18000f6b7  mov     ebx, 102h
0x18000f6bc  cmp     eax, ebx
0x18000f6be  jz      loc_18000F75B
0x18000f6c4  cmp     eax, 0FFFFFFFFh
0x18000f6c7  jz      short loc_18000F734
0x18000f6c9  mov     ebx, 65Bh
0x18000f6ce  jmp     loc_18000F787
0x18000f6d3  xor     ebx, ebx
0x18000f6d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6dc  cmp     rcx, r15
0x18000f6df  jz      loc_18000F787
0x18000f6e5  test    [rcx+1Ch], sil
0x18000f6e9  jz      loc_18000F787
0x18000f6ef  cmp     byte ptr [rcx+19h], 5
0x18000f6f3  jb      loc_18000F787
0x18000f6f9  mov     rcx, [rcx+10h]
0x18000f6fd  lea     edx, [rbx+45h]
0x18000f700  mov     r8, r12
0x18000f703  call    WPP_SF_
0x18000f708  jmp     short loc_18000F787
0x18000f70a  call    cs:__imp_GetLastError
0x18000f710  mov     ebx, eax
0x18000f712  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f719  cmp     rcx, r15
0x18000f71c  jz      short loc_18000F787
0x18000f71e  test    [rcx+1Ch], sil
0x18000f722  jz      short loc_18000F787
0x18000f724  cmp     [rcx+19h], sil
0x18000f728  jb      short loc_18000F787
0x18000f72a  mov     edx, 44h ; 'D'
0x18000f72f  mov     r9d, eax
0x18000f732  jmp     short loc_18000F77B
0x18000f734  call    cs:__imp_GetLastError
0x18000f73a  mov     ebx, eax
0x18000f73c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f743  cmp     rcx, r15
0x18000f746  jz      short loc_18000F787
0x18000f748  test    [rcx+1Ch], sil
0x18000f74c  jz      short loc_18000F787
0x18000f74e  cmp     [rcx+19h], sil
0x18000f752  jb      short loc_18000F787
0x18000f754  mov     edx, 42h ; 'B'
0x18000f759  jmp     short loc_18000F72F
0x18000f75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f762  cmp     rcx, r15
0x18000f765  jz      short loc_18000F787
0x18000f767  test    [rcx+1Ch], sil
0x18000f76b  jz      short loc_18000F787
0x18000f76d  cmp     [rcx+19h], sil
0x18000f771  jb      short loc_18000F787
0x18000f773  mov     edx, 43h ; 'C'
0x18000f778  mov     r9d, ebx
0x18000f77b  mov     rcx, [rcx+10h]
0x18000f77f  mov     r8, r12
0x18000f782  call    WPP_SF_d
0x18000f787  mov     rcx, rdi; hChange
0x18000f78a  call    cs:__imp_FindClosePrinterChangeNotification
0x18000f790  mov     eax, ebx
0x18000f792  mov     rbx, [rsp+70h+arg_18]
0x18000f79a  add     rsp, 70h
0x18000f79e  pop     r15
0x18000f7a0  pop     r12
0x18000f7a2  pop     rdi
0x18000f7a3  pop     rsi
0x18000f7a4  pop     rbp
0x18000f7a5  retn
```

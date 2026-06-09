# WaitForPrinterNotificationForCompletion

- ea: `0x18000fcb8`
- end: `0x18000ffb6`
- name: `WaitForPrinterNotificationForCompletion`
- size: `766`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000faac`

## callees

- `0x180009f04`
- `0x180009f34`
- `0x18000fcb8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fda2`
- `KERNEL32!GetLastError` at `0x18000ff07`
- `KERNEL32!GetLastError` at `0x18000ff37`
- `KERNEL32!GetLastError` at `0x18000fda2`
- `KERNEL32!GetLastError` at `0x18000ff07`
- `KERNEL32!GetLastError` at `0x18000ff37`
- `KERNEL32!WaitForSingleObject` at `0x18000fdf3`
- `KERNEL32!WaitForSingleObject` at `0x18000fe9d`
- `KERNEL32!WaitForSingleObject` at `0x18000fdf3`
- `KERNEL32!WaitForSingleObject` at `0x18000fe9d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18000fe3c`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x18000fe3c`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18000ff93`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x18000ff93`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18000fd8d`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x18000fd8d`

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
0x18000fcb8  mov     [rsp-28h+arg_18], rbx
0x18000fcbd  mov     [rsp-28h+arg_8], edx
0x18000fcc1  push    rbp
0x18000fcc2  push    rsi
0x18000fcc3  push    rdi
0x18000fcc4  push    r12
0x18000fcc6  push    r15
0x18000fcc8  mov     rbp, rsp
0x18000fccb  sub     rsp, 70h
0x18000fccf  mov     eax, 0Ah
0x18000fcd4  mov     [rbp+var_48], 0
0x18000fcdb  mov     word ptr [rbp+arg_8], ax
0x18000fcdf  mov     rbx, rcx
0x18000fce2  lea     ecx, [rax-9]
0x18000fce5  lea     rax, [rbp+arg_8]
0x18000fce9  mov     [rbp+var_50], rcx
0x18000fced  mov     [rbp+var_40], rax
0x18000fcf1  lea     esi, [rcx+1]
0x18000fcf4  lea     rax, [rbp+var_50]
0x18000fcf8  mov     [rbp+var_44], ecx
0x18000fcfb  mov     [rbp+var_28], rax
0x18000fcff  mov     [rbp+pPrinterNotifyOptions], rsi
0x18000fd03  mov     [rbp+var_30], rcx
0x18000fd07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd0e  lea     r15, WPP_GLOBAL_Control
0x18000fd15  lea     r12, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18000fd1c  cmp     rcx, r15
0x18000fd1f  jz      short loc_18000FD43
0x18000fd21  test    [rcx+1Ch], sil
0x18000fd25  jz      short loc_18000FD43
0x18000fd27  cmp     byte ptr [rcx+19h], 5
0x18000fd2b  jb      short loc_18000FD43
0x18000fd2d  mov     rcx, [rcx+10h]
0x18000fd31  lea     edx, [rsi+3Dh]
0x18000fd34  mov     r8, r12
0x18000fd37  call    WPP_SF_
0x18000fd3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd43  test    rbx, rbx
0x18000fd46  jnz     short loc_18000FD7E
0x18000fd48  mov     ebx, 57h ; 'W'
0x18000fd4d  cmp     rcx, r15
0x18000fd50  jz      loc_18000FF9F
0x18000fd56  test    [rcx+1Ch], sil
0x18000fd5a  jz      loc_18000FF9F
0x18000fd60  cmp     [rcx+19h], sil
0x18000fd64  jb      loc_18000FF9F
0x18000fd6a  mov     rcx, [rcx+10h]
0x18000fd6e  lea     edx, [rbx-17h]
0x18000fd71  mov     r8, r12
0x18000fd74  call    WPP_SF_
0x18000fd79  jmp     loc_18000FF9F
0x18000fd7e  lea     r9, [rbp+pPrinterNotifyOptions]; pPrinterNotifyOptions
0x18000fd82  xor     r8d, r8d; fdwOptions
0x18000fd85  mov     edx, 600h; fdwFilter
0x18000fd8a  mov     rcx, rbx; hPrinter
0x18000fd8d  call    cs:__imp_FindFirstPrinterChangeNotification
0x18000fd94  nop     dword ptr [rax+rax+00h]
0x18000fd99  mov     rdi, rax
0x18000fd9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fda0  jnz     short loc_18000FDEB
0x18000fda2  call    cs:__imp_GetLastError
0x18000fda9  nop     dword ptr [rax+rax+00h]
0x18000fdae  mov     ebx, eax
0x18000fdb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdb7  cmp     rcx, r15
0x18000fdba  jz      loc_18000FF9F
0x18000fdc0  test    [rcx+1Ch], sil
0x18000fdc4  jz      loc_18000FF9F
0x18000fdca  cmp     [rcx+19h], sil
0x18000fdce  jb      loc_18000FF9F
0x18000fdd4  mov     rcx, [rcx+10h]
0x18000fdd8  lea     edx, [rdi+42h]
0x18000fddb  mov     r9d, eax
0x18000fdde  mov     r8, r12
0x18000fde1  call    WPP_SF_d
0x18000fde6  jmp     loc_18000FF9F
0x18000fdeb  mov     edx, 1F4h; dwMilliseconds
0x18000fdf0  mov     rcx, rdi; hHandle
0x18000fdf3  call    cs:__imp_WaitForSingleObject
0x18000fdfa  nop     dword ptr [rax+rax+00h]
0x18000fdff  test    eax, eax
0x18000fe01  jnz     loc_18000FEB1
0x18000fe07  lea     ebx, [rax+1]
0x18000fe0a  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x18000fe0e  mov     [rbp+pdwChange], 600h
0x18000fe15  lea     r8, [rbp+pvReserved]; pvReserved
0x18000fe19  mov     [rbp+ppPrinterNotifyInfo], 0
0x18000fe21  lea     rdx, [rbp+pdwChange]; pdwChange
0x18000fe25  mov     [rbp+pvReserved], rsi
0x18000fe29  mov     rcx, rdi; hChange
0x18000fe2c  mov     [rbp+var_18], 0
0x18000fe34  mov     [rbp+var_10], 0
0x18000fe3c  call    cs:__imp_FindNextPrinterChangeNotification
0x18000fe43  nop     dword ptr [rax+rax+00h]
0x18000fe48  test    eax, eax
0x18000fe4a  jz      loc_18000FF07
0x18000fe50  test    [rbp+pdwChange], 600h
0x18000fe57  jz      short loc_18000FE95
0x18000fe59  mov     rax, [rbp+ppPrinterNotifyInfo]
0x18000fe5d  test    rax, rax
0x18000fe60  jz      short loc_18000FE95
0x18000fe62  xor     edx, edx
0x18000fe64  cmp     [rax+8], edx
0x18000fe67  jbe     short loc_18000FE95
0x18000fe69  mov     ecx, edx
0x18000fe6b  shl     rcx, 5
0x18000fe6f  cmp     [rcx+rax+10h], bx
0x18000fe74  jnz     short loc_18000FE8E
0x18000fe76  mov     r8d, 0Ah
0x18000fe7c  cmp     [rcx+rax+12h], r8w
0x18000fe82  jnz     short loc_18000FE8E
0x18000fe84  test    dword ptr [rcx+rax+20h], 180h
0x18000fe8c  jnz     short loc_18000FECD
0x18000fe8e  add     edx, ebx
0x18000fe90  cmp     edx, [rax+8]
0x18000fe93  jb      short loc_18000FE69
0x18000fe95  mov     edx, 1F4h; dwMilliseconds
0x18000fe9a  mov     rcx, rdi; hHandle
0x18000fe9d  call    cs:__imp_WaitForSingleObject
0x18000fea4  nop     dword ptr [rax+rax+00h]
0x18000fea9  test    eax, eax
0x18000feab  jz      loc_18000FE0A
0x18000feb1  mov     ebx, 102h
0x18000feb6  cmp     eax, ebx
0x18000feb8  jz      loc_18000FF64
0x18000febe  cmp     eax, 0FFFFFFFFh
0x18000fec1  jz      short loc_18000FF37
0x18000fec3  mov     ebx, 65Bh
0x18000fec8  jmp     loc_18000FF90
0x18000fecd  xor     ebx, ebx
0x18000fecf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fed6  cmp     rcx, r15
0x18000fed9  jz      loc_18000FF90
0x18000fedf  test    [rcx+1Ch], sil
0x18000fee3  jz      loc_18000FF90
0x18000fee9  cmp     byte ptr [rcx+19h], 5
0x18000feed  jb      loc_18000FF90
0x18000fef3  mov     rcx, [rcx+10h]
0x18000fef7  lea     edx, [rbx+45h]
0x18000fefa  mov     r8, r12
0x18000fefd  call    WPP_SF_
0x18000ff02  jmp     loc_18000FF90
0x18000ff07  call    cs:__imp_GetLastError
0x18000ff0e  nop     dword ptr [rax+rax+00h]
0x18000ff13  mov     ebx, eax
0x18000ff15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff1c  cmp     rcx, r15
0x18000ff1f  jz      short loc_18000FF90
0x18000ff21  test    [rcx+1Ch], sil
0x18000ff25  jz      short loc_18000FF90
0x18000ff27  cmp     [rcx+19h], sil
0x18000ff2b  jb      short loc_18000FF90
0x18000ff2d  mov     edx, 44h ; 'D'
0x18000ff32  mov     r9d, eax
0x18000ff35  jmp     short loc_18000FF84
0x18000ff37  call    cs:__imp_GetLastError
0x18000ff3e  nop     dword ptr [rax+rax+00h]
0x18000ff43  mov     ebx, eax
0x18000ff45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff4c  cmp     rcx, r15
0x18000ff4f  jz      short loc_18000FF90
0x18000ff51  test    [rcx+1Ch], sil
0x18000ff55  jz      short loc_18000FF90
0x18000ff57  cmp     [rcx+19h], sil
0x18000ff5b  jb      short loc_18000FF90
0x18000ff5d  mov     edx, 42h ; 'B'
0x18000ff62  jmp     short loc_18000FF32
0x18000ff64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff6b  cmp     rcx, r15
0x18000ff6e  jz      short loc_18000FF90
0x18000ff70  test    [rcx+1Ch], sil
0x18000ff74  jz      short loc_18000FF90
0x18000ff76  cmp     [rcx+19h], sil
0x18000ff7a  jb      short loc_18000FF90
0x18000ff7c  mov     edx, 43h ; 'C'
0x18000ff81  mov     r9d, ebx
0x18000ff84  mov     rcx, [rcx+10h]
0x18000ff88  mov     r8, r12
0x18000ff8b  call    WPP_SF_d
0x18000ff90  mov     rcx, rdi; hChange
0x18000ff93  call    cs:__imp_FindClosePrinterChangeNotification
0x18000ff9a  nop     dword ptr [rax+rax+00h]
0x18000ff9f  mov     eax, ebx
0x18000ffa1  mov     rbx, [rsp+70h+arg_18]
0x18000ffa9  add     rsp, 70h
0x18000ffad  pop     r15
0x18000ffaf  pop     r12
0x18000ffb1  pop     rdi
0x18000ffb2  pop     rsi
0x18000ffb3  pop     rbp
0x18000ffb4  retn
```

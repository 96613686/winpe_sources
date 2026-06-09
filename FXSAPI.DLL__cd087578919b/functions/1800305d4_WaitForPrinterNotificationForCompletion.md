# WaitForPrinterNotificationForCompletion

- ea: `0x1800305d4`
- end: `0x1800308d7`
- name: `WaitForPrinterNotificationForCompletion`
- size: `771`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f9ac`
- `0x180031098`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800305d4`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18003070e`
- `KERNEL32!WaitForSingleObject` at `0x1800307c3`
- `KERNEL32!WaitForSingleObject` at `0x18003070e`
- `KERNEL32!WaitForSingleObject` at `0x1800307c3`
- `KERNEL32!GetLastError` at `0x1800306bd`
- `KERNEL32!GetLastError` at `0x18003082d`
- `KERNEL32!GetLastError` at `0x18003085d`
- `KERNEL32!GetLastError` at `0x1800306bd`
- `KERNEL32!GetLastError` at `0x18003082d`
- `KERNEL32!GetLastError` at `0x18003085d`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180030755`
- `WINSPOOL!FindNextPrinterChangeNotification` at `0x180030755`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x1800306a8`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x1800306a8`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x1800308b9`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x1800308b9`

## pseudocode

```c
__int64 __fastcall WaitForPrinterNotificationForCompletion(HANDLE hPrinter, int a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebx
  HANDLE v6; // rax
  void *v7; // rdi
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int v10; // edx
  __int64 v11; // rcx
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v17; // [rsp+20h] [rbp-50h] BYREF
  int v18; // [rsp+28h] [rbp-48h]
  int v19; // [rsp+2Ch] [rbp-44h]
  __int16 *v20; // [rsp+30h] [rbp-40h]
  _QWORD pPrinterNotifyOptions[3]; // [rsp+38h] [rbp-38h] BYREF
  _QWORD pvReserved[4]; // [rsp+50h] [rbp-20h] BYREF
  __int16 v23; // [rsp+B0h] [rbp+40h] BYREF
  DWORD pdwChange; // [rsp+C0h] [rbp+50h] BYREF
  LPVOID ppPrinterNotifyInfo; // [rsp+C8h] [rbp+58h] BYREF

  v18 = 0;
  v23 = 10;
  v17 = 1;
  v20 = &v23;
  v19 = 1;
  pPrinterNotifyOptions[2] = &v17;
  pPrinterNotifyOptions[0] = 2;
  pPrinterNotifyOptions[1] = 1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !hPrinter )
  {
    v5 = 87;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 64, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    return v5;
  }
  v6 = FindFirstPrinterChangeNotification(hPrinter, 0x600u, 0, pPrinterNotifyOptions);
  v7 = v6;
  if ( v6 != (HANDLE)-1LL )
  {
    v9 = WaitForSingleObject(v6, 0x1F4u);
    if ( !v9 )
    {
      while ( 1 )
      {
        pdwChange = 1536;
        ppPrinterNotifyInfo = 0;
        pvReserved[0] = 2;
        pvReserved[1] = 0;
        pvReserved[2] = 0;
        if ( !FindNextPrinterChangeNotification(v7, &pdwChange, pvReserved, &ppPrinterNotifyInfo) )
          break;
        if ( (pdwChange & 0x600) != 0 )
        {
          if ( ppPrinterNotifyInfo )
          {
            v10 = 0;
            if ( *((_DWORD *)ppPrinterNotifyInfo + 2) )
            {
              while ( 1 )
              {
                v11 = 32LL * v10;
                if ( *(_DWORD *)((char *)ppPrinterNotifyInfo + v11 + 16) == 655361
                  && (*(_DWORD *)((_BYTE *)ppPrinterNotifyInfo + v11 + 32) & 0x180) != 0
                  && (a2 == -1 || a2 == *(_DWORD *)((char *)ppPrinterNotifyInfo + v11 + 24)) )
                {
                  break;
                }
                if ( ++v10 >= *((_DWORD *)ppPrinterNotifyInfo + 2) )
                  goto LABEL_25;
              }
              v5 = 0;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
              }
              goto LABEL_47;
            }
          }
        }
LABEL_25:
        v9 = WaitForSingleObject(v7, 0x1F4u);
        if ( v9 )
          goto LABEL_26;
      }
      LastError = GetLastError();
      v5 = LastError;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 68;
        goto LABEL_37;
      }
      goto LABEL_47;
    }
LABEL_26:
    v5 = 258;
    if ( v9 == 258 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v14 = 67;
      v15 = 258;
    }
    else
    {
      if ( v9 != -1 )
      {
        v5 = 1627;
LABEL_47:
        FindClosePrinterChangeNotification(v7);
        return v5;
      }
      LastError = GetLastError();
      v5 = LastError;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v14 = 66;
LABEL_37:
      v15 = LastError;
    }
    WPP_SF_d(v13[2], v14, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v15);
    goto LABEL_47;
  }
  v8 = GetLastError();
  v5 = v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x1800305d4  push    rbp
0x1800305d6  push    rbx
0x1800305d7  push    rsi
0x1800305d8  push    rdi
0x1800305d9  push    r12
0x1800305db  push    r13
0x1800305dd  push    r14
0x1800305df  mov     rbp, rsp
0x1800305e2  sub     rsp, 70h
0x1800305e6  mov     eax, 0Ah
0x1800305eb  mov     [rbp+var_48], 0
0x1800305f2  mov     [rbp+arg_0], ax
0x1800305f6  mov     rbx, rcx
0x1800305f9  mov     esi, edx
0x1800305fb  lea     ecx, [rax-9]
0x1800305fe  lea     rax, [rbp+arg_0]
0x180030602  mov     [rbp+var_50], rcx
0x180030606  mov     [rbp+var_40], rax
0x18003060a  lea     r14d, [rcx+1]
0x18003060e  lea     rax, [rbp+var_50]
0x180030612  mov     [rbp+var_44], ecx
0x180030615  mov     [rbp+var_28], rax
0x180030619  mov     [rbp+pPrinterNotifyOptions], r14
0x18003061d  mov     [rbp+var_30], rcx
0x180030621  mov     rcx, cs:WPP_GLOBAL_Control
0x180030628  lea     r12, WPP_GLOBAL_Control
0x18003062f  lea     r13, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x180030636  cmp     rcx, r12
0x180030639  jz      short loc_18003065E
0x18003063b  test    [rcx+1Ch], r14b
0x18003063f  jz      short loc_18003065E
0x180030641  cmp     byte ptr [rcx+19h], 5
0x180030645  jb      short loc_18003065E
0x180030647  mov     rcx, [rcx+10h]
0x18003064b  lea     edx, [r14+3Dh]
0x18003064f  mov     r8, r13
0x180030652  call    WPP_SF_
0x180030657  mov     rcx, cs:WPP_GLOBAL_Control
0x18003065e  test    rbx, rbx
0x180030661  jnz     short loc_180030699
0x180030663  mov     ebx, 57h ; 'W'
0x180030668  cmp     rcx, r12
0x18003066b  jz      loc_1800308C5
0x180030671  test    [rcx+1Ch], r14b
0x180030675  jz      loc_1800308C5
0x18003067b  cmp     [rcx+19h], r14b
0x18003067f  jb      loc_1800308C5
0x180030685  mov     rcx, [rcx+10h]
0x180030689  lea     edx, [rbx-17h]
0x18003068c  mov     r8, r13
0x18003068f  call    WPP_SF_
0x180030694  jmp     loc_1800308C5
0x180030699  lea     r9, [rbp+pPrinterNotifyOptions]; pPrinterNotifyOptions
0x18003069d  xor     r8d, r8d; fdwOptions
0x1800306a0  mov     edx, 600h; fdwFilter
0x1800306a5  mov     rcx, rbx; hPrinter
0x1800306a8  call    cs:__imp_FindFirstPrinterChangeNotification
0x1800306af  nop     dword ptr [rax+rax+00h]
0x1800306b4  mov     rdi, rax
0x1800306b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800306bb  jnz     short loc_180030706
0x1800306bd  call    cs:__imp_GetLastError
0x1800306c4  nop     dword ptr [rax+rax+00h]
0x1800306c9  mov     ebx, eax
0x1800306cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306d2  cmp     rcx, r12
0x1800306d5  jz      loc_1800308C5
0x1800306db  test    [rcx+1Ch], r14b
0x1800306df  jz      loc_1800308C5
0x1800306e5  cmp     [rcx+19h], r14b
0x1800306e9  jb      loc_1800308C5
0x1800306ef  mov     rcx, [rcx+10h]
0x1800306f3  lea     edx, [rdi+42h]
0x1800306f6  mov     r9d, eax
0x1800306f9  mov     r8, r13
0x1800306fc  call    WPP_SF_d
0x180030701  jmp     loc_1800308C5
0x180030706  mov     edx, 1F4h; dwMilliseconds
0x18003070b  mov     rcx, rdi; hHandle
0x18003070e  call    cs:__imp_WaitForSingleObject
0x180030715  nop     dword ptr [rax+rax+00h]
0x18003071a  test    eax, eax
0x18003071c  jnz     loc_1800307D7
0x180030722  mov     ebx, 600h
0x180030727  lea     r9, [rbp+ppPrinterNotifyInfo]; ppPrinterNotifyInfo
0x18003072b  mov     [rbp+pdwChange], ebx
0x18003072e  lea     r8, [rbp+pvReserved]; pvReserved
0x180030732  mov     [rbp+ppPrinterNotifyInfo], 0
0x18003073a  lea     rdx, [rbp+pdwChange]; pdwChange
0x18003073e  mov     [rbp+pvReserved], r14
0x180030742  mov     rcx, rdi; hChange
0x180030745  mov     [rbp+var_18], 0
0x18003074d  mov     [rbp+var_10], 0
0x180030755  call    cs:__imp_FindNextPrinterChangeNotification
0x18003075c  nop     dword ptr [rax+rax+00h]
0x180030761  test    eax, eax
0x180030763  jz      loc_18003082D
0x180030769  test    [rbp+pdwChange], ebx
0x18003076c  jz      short loc_1800307BB
0x18003076e  mov     rax, [rbp+ppPrinterNotifyInfo]
0x180030772  test    rax, rax
0x180030775  jz      short loc_1800307BB
0x180030777  xor     edx, edx
0x180030779  cmp     [rax+8], edx
0x18003077c  jbe     short loc_1800307BB
0x18003077e  lea     r8d, [rdx+1]
0x180030782  mov     ecx, edx
0x180030784  shl     rcx, 5
0x180030788  cmp     [rcx+rax+10h], r8w
0x18003078e  jnz     short loc_1800307B3
0x180030790  mov     r9d, 0Ah
0x180030796  cmp     [rcx+rax+12h], r9w
0x18003079c  jnz     short loc_1800307B3
0x18003079e  test    dword ptr [rcx+rax+20h], 180h
0x1800307a6  jz      short loc_1800307B3
0x1800307a8  cmp     esi, 0FFFFFFFFh
0x1800307ab  jz      short loc_1800307F3
0x1800307ad  cmp     esi, [rcx+rax+18h]
0x1800307b1  jz      short loc_1800307F3
0x1800307b3  add     edx, r8d
0x1800307b6  cmp     edx, [rax+8]
0x1800307b9  jb      short loc_180030782
0x1800307bb  mov     edx, 1F4h; dwMilliseconds
0x1800307c0  mov     rcx, rdi; hHandle
0x1800307c3  call    cs:__imp_WaitForSingleObject
0x1800307ca  nop     dword ptr [rax+rax+00h]
0x1800307cf  test    eax, eax
0x1800307d1  jz      loc_180030727
0x1800307d7  mov     ebx, 102h
0x1800307dc  cmp     eax, ebx
0x1800307de  jz      loc_18003088A
0x1800307e4  cmp     eax, 0FFFFFFFFh
0x1800307e7  jz      short loc_18003085D
0x1800307e9  mov     ebx, 65Bh
0x1800307ee  jmp     loc_1800308B6
0x1800307f3  xor     ebx, ebx
0x1800307f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307fc  cmp     rcx, r12
0x1800307ff  jz      loc_1800308B6
0x180030805  test    [rcx+1Ch], r14b
0x180030809  jz      loc_1800308B6
0x18003080f  cmp     byte ptr [rcx+19h], 5
0x180030813  jb      loc_1800308B6
0x180030819  mov     rcx, [rcx+10h]
0x18003081d  lea     edx, [rbx+45h]
0x180030820  mov     r8, r13
0x180030823  call    WPP_SF_
0x180030828  jmp     loc_1800308B6
0x18003082d  call    cs:__imp_GetLastError
0x180030834  nop     dword ptr [rax+rax+00h]
0x180030839  mov     ebx, eax
0x18003083b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030842  cmp     rcx, r12
0x180030845  jz      short loc_1800308B6
0x180030847  test    [rcx+1Ch], r14b
0x18003084b  jz      short loc_1800308B6
0x18003084d  cmp     [rcx+19h], r14b
0x180030851  jb      short loc_1800308B6
0x180030853  mov     edx, 44h ; 'D'
0x180030858  mov     r9d, eax
0x18003085b  jmp     short loc_1800308AA
0x18003085d  call    cs:__imp_GetLastError
0x180030864  nop     dword ptr [rax+rax+00h]
0x180030869  mov     ebx, eax
0x18003086b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030872  cmp     rcx, r12
0x180030875  jz      short loc_1800308B6
0x180030877  test    [rcx+1Ch], r14b
0x18003087b  jz      short loc_1800308B6
0x18003087d  cmp     [rcx+19h], r14b
0x180030881  jb      short loc_1800308B6
0x180030883  mov     edx, 42h ; 'B'
0x180030888  jmp     short loc_180030858
0x18003088a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030891  cmp     rcx, r12
0x180030894  jz      short loc_1800308B6
0x180030896  test    [rcx+1Ch], r14b
0x18003089a  jz      short loc_1800308B6
0x18003089c  cmp     [rcx+19h], r14b
0x1800308a0  jb      short loc_1800308B6
0x1800308a2  mov     edx, 43h ; 'C'
0x1800308a7  mov     r9d, ebx
0x1800308aa  mov     rcx, [rcx+10h]
0x1800308ae  mov     r8, r13
0x1800308b1  call    WPP_SF_d
0x1800308b6  mov     rcx, rdi; hChange
0x1800308b9  call    cs:__imp_FindClosePrinterChangeNotification
0x1800308c0  nop     dword ptr [rax+rax+00h]
0x1800308c5  mov     eax, ebx
0x1800308c7  add     rsp, 70h
0x1800308cb  pop     r14
0x1800308cd  pop     r13
0x1800308cf  pop     r12
0x1800308d1  pop     rdi
0x1800308d2  pop     rsi
0x1800308d3  pop     rbx
0x1800308d4  pop     rbp
0x1800308d5  retn
```

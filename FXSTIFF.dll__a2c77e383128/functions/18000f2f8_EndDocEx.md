# EndDocEx

- ea: `0x18000f2f8`
- end: `0x18000f4d3`
- name: `EndDocEx`
- size: `475`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, __int64, __int64, HDC)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006530`
- `0x18000e530`

## callees

- `0x180009a7c`
- `0x180009aa4`
- `0x180009b4c`
- `0x18000f2f8`
- `0x18000f4dc`

## import_xrefs

- `GDI32!EndDoc` at `0x18000f38b`
- `GDI32!EndDoc` at `0x18000f38b`
- `KERNEL32!GetLastError` at `0x18000f395`
- `KERNEL32!GetLastError` at `0x18000f3f1`
- `KERNEL32!GetLastError` at `0x18000f49b`
- `KERNEL32!GetLastError` at `0x18000f395`
- `KERNEL32!GetLastError` at `0x18000f3f1`
- `KERNEL32!GetLastError` at `0x18000f49b`
- `KERNEL32!SetLastError` at `0x18000f4be`
- `KERNEL32!SetLastError` at `0x18000f4be`
- `WINSPOOL!ClosePrinter` at `0x18000f479`
- `WINSPOOL!ClosePrinter` at `0x18000f479`
- `WINSPOOL!OpenPrinterW` at `0x18000f3e7`
- `WINSPOOL!OpenPrinterW` at `0x18000f3e7`

## pseudocode

```c
__int64 __fastcall EndDocEx(LPWSTR pPrinterName, __int64 a2, __int64 a3, HDC a4)
{
  _QWORD *v6; // rcx
  DWORD v7; // ebx
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HANDLE v11; // rcx
  int v12; // edi
  char v13; // al
  int v14; // edx
  int v15; // r8d
  DWORD v16; // eax
  HANDLE phPrinter; // [rsp+30h] [rbp-38h] BYREF

  phPrinter = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    v7 = 87;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(v6[2], 71, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    goto LABEL_39;
  }
  if ( EndDoc(a4) <= 0 )
  {
    LastError = GetLastError();
    v7 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v10 = 72;
LABEL_38:
    WPP_SF_d(v9[2], v10, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
    goto LABEL_39;
  }
  v11 = phPrinter;
  v12 = 0;
  if ( pPrinterName )
  {
    if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
    {
      v13 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)pPrinterName, v13);
      }
      v7 = 0;
      goto LABEL_39;
    }
    v11 = phPrinter;
    v12 = 1;
  }
  v7 = 0;
  if ( v11 )
  {
    v16 = WaitForPrinterNotificationForCompletion(v11);
    v7 = v16;
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v16);
      }
      v7 = 0;
    }
    v11 = phPrinter;
  }
  if ( v12
    && !ClosePrinter(v11)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    LastError = GetLastError();
    v9 = WPP_GLOBAL_Control;
    v10 = 75;
    goto LABEL_38;
  }
LABEL_39:
  SetLastError(v7);
  return 1;
}

```

## disassembly

```asm
0x18000f2f8  push    rbx
0x18000f2fa  push    rbp
0x18000f2fb  push    rdi
0x18000f2fc  push    r14
0x18000f2fe  sub     rsp, 48h
0x18000f302  mov     rdi, r9
0x18000f305  mov     [rsp+68h+phPrinter], 0
0x18000f30e  mov     rbx, rcx
0x18000f311  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f318  lea     rbp, WPP_GLOBAL_Control
0x18000f31f  lea     r14, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18000f326  cmp     rcx, rbp
0x18000f329  jz      short loc_18000F34F
0x18000f32b  test    byte ptr [rcx+1Ch], 2
0x18000f32f  jz      short loc_18000F34F
0x18000f331  cmp     byte ptr [rcx+19h], 5
0x18000f335  jb      short loc_18000F34F
0x18000f337  mov     rcx, [rcx+10h]
0x18000f33b  mov     edx, 46h ; 'F'
0x18000f340  mov     r8, r14
0x18000f343  call    WPP_SF_
0x18000f348  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f34f  test    rdi, rdi
0x18000f352  jnz     short loc_18000F388
0x18000f354  lea     ebx, [rdi+57h]
0x18000f357  cmp     rcx, rbp
0x18000f35a  jz      loc_18000F4BC
0x18000f360  test    byte ptr [rcx+1Ch], 2
0x18000f364  jz      loc_18000F4BC
0x18000f36a  cmp     byte ptr [rcx+19h], 2
0x18000f36e  jb      loc_18000F4BC
0x18000f374  mov     rcx, [rcx+10h]
0x18000f378  lea     edx, [rdi+47h]
0x18000f37b  mov     r8, r14
0x18000f37e  call    WPP_SF_
0x18000f383  jmp     loc_18000F4BC
0x18000f388  mov     rcx, rdi; hdc
0x18000f38b  call    cs:__imp_EndDoc
0x18000f391  test    eax, eax
0x18000f393  jg      short loc_18000F3CB
0x18000f395  call    cs:__imp_GetLastError
0x18000f39b  mov     ebx, eax
0x18000f39d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3a4  cmp     rcx, rbp
0x18000f3a7  jz      loc_18000F4BC
0x18000f3ad  test    byte ptr [rcx+1Ch], 2
0x18000f3b1  jz      loc_18000F4BC
0x18000f3b7  cmp     byte ptr [rcx+19h], 2
0x18000f3bb  jb      loc_18000F4BC
0x18000f3c1  mov     edx, 48h ; 'H'
0x18000f3c6  jmp     loc_18000F4AD
0x18000f3cb  mov     rcx, [rsp+68h+phPrinter]
0x18000f3d0  xor     edi, edi
0x18000f3d2  test    rcx, rcx
0x18000f3d5  jnz     short loc_18000F430
0x18000f3d7  test    rbx, rbx
0x18000f3da  jz      short loc_18000F430
0x18000f3dc  xor     r8d, r8d; pDefault
0x18000f3df  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x18000f3e4  mov     rcx, rbx; pPrinterName
0x18000f3e7  call    cs:__imp_OpenPrinterW
0x18000f3ed  test    eax, eax
0x18000f3ef  jnz     short loc_18000F426
0x18000f3f1  call    cs:__imp_GetLastError
0x18000f3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3fe  cmp     rcx, rbp
0x18000f401  jz      short loc_18000F41F
0x18000f403  test    byte ptr [rcx+1Ch], 2
0x18000f407  jz      short loc_18000F41F
0x18000f409  cmp     byte ptr [rcx+19h], 2
0x18000f40d  jb      short loc_18000F41F
0x18000f40f  mov     rcx, [rcx+10h]
0x18000f413  mov     r9, rbx
0x18000f416  mov     [rsp+68h+var_48], eax
0x18000f41a  call    WPP_SF_Sl
0x18000f41f  xor     ebx, ebx
0x18000f421  jmp     loc_18000F4BC
0x18000f426  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18000f42b  mov     edi, 1
0x18000f430  xor     ebx, ebx
0x18000f432  test    rcx, rcx
0x18000f435  jz      short loc_18000F475
0x18000f437  call    WaitForPrinterNotificationForCompletion
0x18000f43c  mov     ebx, eax
0x18000f43e  test    eax, eax
0x18000f440  jz      short loc_18000F470
0x18000f442  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f449  cmp     rcx, rbp
0x18000f44c  jz      short loc_18000F46E
0x18000f44e  test    byte ptr [rcx+1Ch], 2
0x18000f452  jz      short loc_18000F46E
0x18000f454  cmp     byte ptr [rcx+19h], 3
0x18000f458  jb      short loc_18000F46E
0x18000f45a  mov     rcx, [rcx+10h]
0x18000f45e  mov     edx, 4Ah ; 'J'
0x18000f463  mov     r9d, eax
0x18000f466  mov     r8, r14
0x18000f469  call    WPP_SF_d
0x18000f46e  xor     ebx, ebx
0x18000f470  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18000f475  test    edi, edi
0x18000f477  jz      short loc_18000F4BC
0x18000f479  call    cs:__imp_ClosePrinter
0x18000f47f  test    eax, eax
0x18000f481  jnz     short loc_18000F4BC
0x18000f483  mov     rax, cs:WPP_GLOBAL_Control
0x18000f48a  cmp     rax, rbp
0x18000f48d  jz      short loc_18000F4BC
0x18000f48f  test    byte ptr [rax+1Ch], 2
0x18000f493  jz      short loc_18000F4BC
0x18000f495  cmp     byte ptr [rax+19h], 3
0x18000f499  jb      short loc_18000F4BC
0x18000f49b  call    cs:__imp_GetLastError
0x18000f4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a8  mov     edx, 4Bh ; 'K'
0x18000f4ad  mov     rcx, [rcx+10h]
0x18000f4b1  mov     r9d, eax
0x18000f4b4  mov     r8, r14
0x18000f4b7  call    WPP_SF_d
0x18000f4bc  mov     ecx, ebx; dwErrCode
0x18000f4be  call    cs:__imp_SetLastError
0x18000f4c4  mov     eax, 1
0x18000f4c9  add     rsp, 48h
0x18000f4cd  pop     r14
0x18000f4cf  pop     rdi
0x18000f4d0  pop     rbp
0x18000f4d1  pop     rbx
0x18000f4d2  retn
```

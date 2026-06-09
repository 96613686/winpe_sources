# EndDocEx

- ea: `0x18002f9ac`
- end: `0x18002fbc0`
- name: `EndDocEx`
- size: `532`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025df0`
- `0x1800386f0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x18002f9ac`
- `0x1800305d4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002fba1`
- `KERNEL32!SetLastError` at `0x18002fba1`
- `KERNEL32!GetLastError` at `0x18002fa52`
- `KERNEL32!GetLastError` at `0x18002faba`
- `KERNEL32!GetLastError` at `0x18002fb78`
- `KERNEL32!GetLastError` at `0x18002fa52`
- `KERNEL32!GetLastError` at `0x18002faba`
- `KERNEL32!GetLastError` at `0x18002fb78`
- `WINSPOOL!OpenPrinterW` at `0x18002faaa`
- `WINSPOOL!OpenPrinterW` at `0x18002faaa`
- `WINSPOOL!ClosePrinter` at `0x18002fb50`
- `WINSPOOL!ClosePrinter` at `0x18002fb50`
- `GDI32!EndDoc` at `0x18002fa42`
- `GDI32!EndDoc` at `0x18002fa42`

## pseudocode

```c
__int64 __fastcall EndDocEx(LPWSTR pPrinterName, void *a2, __int64 a3, HDC a4)
{
  _QWORD *v6; // rcx
  DWORD v7; // ebx
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HANDLE v11; // rcx
  int v12; // esi
  char v13; // al
  DWORD v14; // eax
  HANDLE phPrinter; // [rsp+78h] [rbp+10h] BYREF

  phPrinter = a2;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    v7 = 87;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(v6[2], 71, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
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
    WPP_SF_d(v9[2], v10, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
    goto LABEL_39;
  }
  v11 = phPrinter;
  v12 = 0;
  if ( !phPrinter && pPrinterName )
  {
    if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
    {
      v13 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          (unsigned int)WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
          (_DWORD)pPrinterName,
          v13);
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
    v14 = WaitForPrinterNotificationForCompletion(v11);
    v7 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v14);
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
0x18002f9ac  mov     [rsp+phPrinter], rdx
0x18002f9b1  push    rbx
0x18002f9b2  push    rbp
0x18002f9b3  push    rsi
0x18002f9b4  push    rdi
0x18002f9b5  push    r12
0x18002f9b7  push    r15
0x18002f9b9  sub     rsp, 38h
0x18002f9bd  mov     rbx, r9
0x18002f9c0  mov     ebp, r8d
0x18002f9c3  mov     rdi, rcx
0x18002f9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9cd  lea     r15, WPP_GLOBAL_Control
0x18002f9d4  lea     r12, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18002f9db  cmp     rcx, r15
0x18002f9de  jz      short loc_18002FA04
0x18002f9e0  test    byte ptr [rcx+1Ch], 2
0x18002f9e4  jz      short loc_18002FA04
0x18002f9e6  cmp     byte ptr [rcx+19h], 5
0x18002f9ea  jb      short loc_18002FA04
0x18002f9ec  mov     rcx, [rcx+10h]
0x18002f9f0  mov     edx, 46h ; 'F'
0x18002f9f5  mov     r8, r12
0x18002f9f8  call    WPP_SF_
0x18002f9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa04  test    rbx, rbx
0x18002fa07  jnz     short loc_18002FA3F
0x18002fa09  mov     ebx, 57h ; 'W'
0x18002fa0e  cmp     rcx, r15
0x18002fa11  jz      loc_18002FB9F
0x18002fa17  test    byte ptr [rcx+1Ch], 2
0x18002fa1b  jz      loc_18002FB9F
0x18002fa21  cmp     byte ptr [rcx+19h], 2
0x18002fa25  jb      loc_18002FB9F
0x18002fa2b  mov     rcx, [rcx+10h]
0x18002fa2f  lea     edx, [rbx-10h]
0x18002fa32  mov     r8, r12
0x18002fa35  call    WPP_SF_
0x18002fa3a  jmp     loc_18002FB9F
0x18002fa3f  mov     rcx, rbx; hdc
0x18002fa42  call    cs:__imp_EndDoc
0x18002fa49  nop     dword ptr [rax+rax+00h]
0x18002fa4e  test    eax, eax
0x18002fa50  jg      short loc_18002FA8E
0x18002fa52  call    cs:__imp_GetLastError
0x18002fa59  nop     dword ptr [rax+rax+00h]
0x18002fa5e  mov     ebx, eax
0x18002fa60  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa67  cmp     rcx, r15
0x18002fa6a  jz      loc_18002FB9F
0x18002fa70  test    byte ptr [rcx+1Ch], 2
0x18002fa74  jz      loc_18002FB9F
0x18002fa7a  cmp     byte ptr [rcx+19h], 2
0x18002fa7e  jb      loc_18002FB9F
0x18002fa84  mov     edx, 48h ; 'H'
0x18002fa89  jmp     loc_18002FB90
0x18002fa8e  mov     rcx, [rsp+68h+phPrinter]
0x18002fa93  xor     esi, esi
0x18002fa95  test    rcx, rcx
0x18002fa98  jnz     short loc_18002FB05
0x18002fa9a  test    rdi, rdi
0x18002fa9d  jz      short loc_18002FB05
0x18002fa9f  xor     r8d, r8d; pDefault
0x18002faa2  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x18002faa7  mov     rcx, rdi; pPrinterName
0x18002faaa  call    cs:__imp_OpenPrinterW
0x18002fab1  nop     dword ptr [rax+rax+00h]
0x18002fab6  test    eax, eax
0x18002fab8  jnz     short loc_18002FAFB
0x18002faba  call    cs:__imp_GetLastError
0x18002fac1  nop     dword ptr [rax+rax+00h]
0x18002fac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002facd  cmp     rcx, r15
0x18002fad0  jz      short loc_18002FAF4
0x18002fad2  test    byte ptr [rcx+1Ch], 2
0x18002fad6  jz      short loc_18002FAF4
0x18002fad8  cmp     byte ptr [rcx+19h], 2
0x18002fadc  jb      short loc_18002FAF4
0x18002fade  mov     rcx, [rcx+10h]
0x18002fae2  lea     edx, [rsi+49h]
0x18002fae5  mov     r9, rdi
0x18002fae8  mov     [rsp+68h+var_48], eax
0x18002faec  mov     r8, r12
0x18002faef  call    WPP_SF_Sd
0x18002faf4  xor     ebx, ebx
0x18002faf6  jmp     loc_18002FB9F
0x18002fafb  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18002fb00  mov     esi, 1
0x18002fb05  xor     ebx, ebx
0x18002fb07  test    rcx, rcx
0x18002fb0a  jz      short loc_18002FB4C
0x18002fb0c  mov     edx, ebp
0x18002fb0e  call    WaitForPrinterNotificationForCompletion
0x18002fb13  mov     ebx, eax
0x18002fb15  test    eax, eax
0x18002fb17  jz      short loc_18002FB47
0x18002fb19  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb20  cmp     rcx, r15
0x18002fb23  jz      short loc_18002FB45
0x18002fb25  test    byte ptr [rcx+1Ch], 2
0x18002fb29  jz      short loc_18002FB45
0x18002fb2b  cmp     byte ptr [rcx+19h], 3
0x18002fb2f  jb      short loc_18002FB45
0x18002fb31  mov     rcx, [rcx+10h]
0x18002fb35  mov     edx, 4Ah ; 'J'
0x18002fb3a  mov     r9d, eax
0x18002fb3d  mov     r8, r12
0x18002fb40  call    WPP_SF_d
0x18002fb45  xor     ebx, ebx
0x18002fb47  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18002fb4c  test    esi, esi
0x18002fb4e  jz      short loc_18002FB9F
0x18002fb50  call    cs:__imp_ClosePrinter
0x18002fb57  nop     dword ptr [rax+rax+00h]
0x18002fb5c  test    eax, eax
0x18002fb5e  jnz     short loc_18002FB9F
0x18002fb60  mov     rax, cs:WPP_GLOBAL_Control
0x18002fb67  cmp     rax, r15
0x18002fb6a  jz      short loc_18002FB9F
0x18002fb6c  test    byte ptr [rax+1Ch], 2
0x18002fb70  jz      short loc_18002FB9F
0x18002fb72  cmp     byte ptr [rax+19h], 3
0x18002fb76  jb      short loc_18002FB9F
0x18002fb78  call    cs:__imp_GetLastError
0x18002fb7f  nop     dword ptr [rax+rax+00h]
0x18002fb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb8b  mov     edx, 4Bh ; 'K'
0x18002fb90  mov     rcx, [rcx+10h]
0x18002fb94  mov     r9d, eax
0x18002fb97  mov     r8, r12
0x18002fb9a  call    WPP_SF_d
0x18002fb9f  mov     ecx, ebx; dwErrCode
0x18002fba1  call    cs:__imp_SetLastError
0x18002fba8  nop     dword ptr [rax+rax+00h]
0x18002fbad  mov     eax, 1
0x18002fbb2  add     rsp, 38h
0x18002fbb6  pop     r15
0x18002fbb8  pop     r12
0x18002fbba  pop     rdi
0x18002fbbb  pop     rsi
0x18002fbbc  pop     rbp
0x18002fbbd  pop     rbx
0x18002fbbe  retn
```

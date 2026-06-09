# IsLocalFaxPrinterInstalled

- ea: `0x18002ffb8`
- end: `0x180030153`
- name: `IsLocalFaxPrinterInstalled`
- size: `411`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002f480`
- `0x18002f7b0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180016124`
- `0x18002bb58`
- `0x18002f2c4`
- `0x18002fbc8`
- `0x18002ffb8`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003003b`
- `KERNEL32!GetLastError` at `0x18003009e`
- `KERNEL32!GetLastError` at `0x18003003b`
- `KERNEL32!GetLastError` at `0x18003009e`

## pseudocode

```c
__int64 __fastcall IsLocalFaxPrinterInstalled(int *a1)
{
  unsigned int v2; // edx
  unsigned int v3; // r8d
  DWORD v4; // eax
  DWORD v5; // ebx
  void *FaxPrinterInfo; // rax
  void *v7; // rbx
  DWORD LastError; // eax
  int v10; // eax
  WCHAR pPrinterName[2]; // [rsp+20h] [rbp-638h] BYREF
  _BYTE v12[1564]; // [rsp+24h] [rbp-634h] BYREF

  *(_DWORD *)pPrinterName = 0;
  memset_0(v12, 0, 0x614u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  if ( (unsigned int)GetFirstFaxPrinterName(pPrinterName, v2, v3) )
  {
    FaxPrinterInfo = GetFaxPrinterInfo(pPrinterName);
    v7 = FaxPrinterInfo;
    if ( FaxPrinterInfo )
    {
      if ( (*((_BYTE *)FaxPrinterInfo + 124) & 4) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids,
            pPrinterName);
        }
        v10 = 0;
      }
      else
      {
        v10 = 1;
      }
      *a1 = v10;
      pMemFree(v7);
      return 0;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, LastError);
    }
    return v5;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids, v4);
  }
  if ( v5 != 3012 )
    return v5;
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x18002ffb8  mov     [rsp+arg_8], rbx
0x18002ffbd  mov     [rsp+arg_10], rbp
0x18002ffc2  push    rdi
0x18002ffc3  sub     rsp, 650h
0x18002ffca  mov     rax, cs:__security_cookie
0x18002ffd1  xor     rax, rsp
0x18002ffd4  mov     [rsp+658h+var_18], rax
0x18002ffdc  mov     rdi, rcx
0x18002ffdf  mov     dword ptr [rsp+658h+pPrinterName], 0
0x18002ffe7  lea     rcx, [rsp+658h+var_634]; void *
0x18002ffec  xor     edx, edx; Val
0x18002ffee  mov     r8d, 614h; Size
0x18002fff4  call    memset_0
0x18002fff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180030000  lea     rbp, WPP_GLOBAL_Control
0x180030007  cmp     rcx, rbp
0x18003000a  jz      short loc_18003002D
0x18003000c  test    byte ptr [rcx+1Ch], 2
0x180030010  jz      short loc_18003002D
0x180030012  cmp     byte ptr [rcx+19h], 5
0x180030016  jb      short loc_18003002D
0x180030018  mov     rcx, [rcx+10h]
0x18003001c  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x180030023  mov     edx, 14h
0x180030028  call    WPP_SF_
0x18003002d  lea     rcx, [rsp+658h+pPrinterName]; unsigned __int16 *
0x180030032  call    ?GetFirstFaxPrinterName@@YAHPEAGKK@Z; GetFirstFaxPrinterName(ushort *,ulong,ulong)
0x180030037  test    eax, eax
0x180030039  jnz     short loc_18003008C
0x18003003b  call    cs:__imp_GetLastError
0x180030042  nop     dword ptr [rax+rax+00h]
0x180030047  mov     ebx, eax
0x180030049  mov     rcx, cs:WPP_GLOBAL_Control
0x180030050  cmp     rcx, rbp
0x180030053  jz      short loc_180030079
0x180030055  test    byte ptr [rcx+1Ch], 2
0x180030059  jz      short loc_180030079
0x18003005b  cmp     byte ptr [rcx+19h], 2
0x18003005f  jb      short loc_180030079
0x180030061  mov     rcx, [rcx+10h]
0x180030065  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18003006c  mov     edx, 15h
0x180030071  mov     r9d, eax
0x180030074  call    WPP_SF_d
0x180030079  cmp     ebx, 0BC4h
0x18003007f  jnz     short loc_1800300DC
0x180030081  mov     dword ptr [rdi], 0
0x180030087  jmp     loc_18003012B
0x18003008c  lea     rcx, [rsp+658h+pPrinterName]; pPrinterName
0x180030091  call    GetFaxPrinterInfo
0x180030096  mov     rbx, rax
0x180030099  test    rax, rax
0x18003009c  jnz     short loc_1800300E0
0x18003009e  call    cs:__imp_GetLastError
0x1800300a5  nop     dword ptr [rax+rax+00h]
0x1800300aa  mov     ebx, eax
0x1800300ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300b3  cmp     rcx, rbp
0x1800300b6  jz      short loc_1800300DC
0x1800300b8  test    byte ptr [rcx+1Ch], 2
0x1800300bc  jz      short loc_1800300DC
0x1800300be  cmp     byte ptr [rcx+19h], 2
0x1800300c2  jb      short loc_1800300DC
0x1800300c4  mov     rcx, [rcx+10h]
0x1800300c8  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x1800300cf  mov     edx, 16h
0x1800300d4  mov     r9d, eax
0x1800300d7  call    WPP_SF_d
0x1800300dc  mov     eax, ebx
0x1800300de  jmp     short loc_18003012D
0x1800300e0  test    byte ptr [rax+7Ch], 4
0x1800300e4  jz      short loc_18003011C
0x1800300e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300ed  cmp     rcx, rbp
0x1800300f0  jz      short loc_180030118
0x1800300f2  test    byte ptr [rcx+1Ch], 2
0x1800300f6  jz      short loc_180030118
0x1800300f8  cmp     byte ptr [rcx+19h], 5
0x1800300fc  jb      short loc_180030118
0x1800300fe  mov     rcx, [rcx+10h]
0x180030102  lea     r9, [rsp+658h+pPrinterName]
0x180030107  mov     edx, 17h
0x18003010c  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x180030113  call    WPP_SF_S
0x180030118  xor     eax, eax
0x18003011a  jmp     short loc_180030121
0x18003011c  mov     eax, 1
0x180030121  mov     rcx, rbx; lpMem
0x180030124  mov     [rdi], eax
0x180030126  call    pMemFree
0x18003012b  xor     eax, eax
0x18003012d  mov     rcx, [rsp+658h+var_18]
0x180030135  xor     rcx, rsp; StackCookie
0x180030138  call    __security_check_cookie
0x18003013d  lea     r11, [rsp+658h+var_8]
0x180030145  mov     rbx, [r11+18h]
0x180030149  mov     rbp, [r11+20h]
0x18003014d  mov     rsp, r11
0x180030150  pop     rdi
0x180030151  retn
```

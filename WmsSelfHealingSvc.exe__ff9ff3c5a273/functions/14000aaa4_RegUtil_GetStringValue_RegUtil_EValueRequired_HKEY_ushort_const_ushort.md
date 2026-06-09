# RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)

- ea: `0x14000aaa4`
- end: `0x14000ad17`
- name: `?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `627`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400076e0`

## callees

- `0x1400011d4`
- `0x140001b34`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000aaa4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14000aaf2`
- `ADVAPI32!RegGetValueW` at `0x14000accb`
- `ADVAPI32!RegGetValueW` at `0x14000aaf2`
- `ADVAPI32!RegGetValueW` at `0x14000accb`
- `KERNEL32!IsDebuggerPresent` at `0x14000ab49`
- `KERNEL32!IsDebuggerPresent` at `0x14000abf2`
- `KERNEL32!IsDebuggerPresent` at `0x14000ac6e`
- `KERNEL32!IsDebuggerPresent` at `0x14000ab49`
- `KERNEL32!IsDebuggerPresent` at `0x14000abf2`
- `KERNEL32!IsDebuggerPresent` at `0x14000ac6e`

## string_xrefs

- `0x14000ab28`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x14000abce`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x14000ac4d`: `termsrv\wms\src\common\srcutils\registry.cpp`

## pseudocode

```c
__int64 __fastcall RegUtil::GetStringValue(__int64 a1, HKEY a2, __int64 a3, _QWORD *a4)
{
  void *v4; // rbp
  LSTATUS ValueW; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r13d
  __int64 v10; // r9
  __int64 v11; // r8
  LSTATUS v12; // eax
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-40h]
  LPDWORD pcbData; // [rsp+30h] [rbp-38h]
  const unsigned __int16 *pcbDataa; // [rsp+30h] [rbp-38h]
  int v17; // [rsp+38h] [rbp-30h]
  DWORD v18; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v18 = 0;
  ValueW = RegGetValueW(a2, 0, L"ProductDumpsDir", 2u, 0, 0, &v18);
  v8 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v8 = (unsigned __int16)ValueW | 0x80070000;
    v9 = 94;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v9,
      L"RegUtil::GetStringValue",
      L"CBRAEx",
      L"lr == 0L",
      v8);
    if ( IsDebuggerPresent() )
    {
      v17 = v8;
      v10 = v9;
      pcbDataa = L"lr == 0L";
LABEL_7:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        v10,
        L"RegUtil::GetStringValue",
        L"CBRAEx",
        pcbDataa,
        v17);
      goto LABEL_25;
    }
    LODWORD(pcbData) = v8;
    v11 = v9;
    pvData = L"lr == 0L";
    goto LABEL_10;
  }
  if ( (v18 & 1) != 0 )
  {
    v8 = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x60u,
      L"RegUtil::GetStringValue",
      L"CBRAEx",
      L"cb % sizeof (WCHAR) == 0",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v17 = -2147418113;
      v10 = 96;
      pcbDataa = L"cb % sizeof (WCHAR) == 0";
      goto LABEL_7;
    }
    LODWORD(pcbData) = -2147418113;
    v11 = 96;
    pvData = L"cb % sizeof (WCHAR) == 0";
LABEL_10:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      v11,
      L"RegUtil::GetStringValue",
      L"CBRAEx",
      pvData,
      pcbData);
    goto LABEL_25;
  }
  v4 = operator new(v18);
  if ( v4 )
  {
    v12 = RegGetValueW(a2, 0, L"ProductDumpsDir", 2u, 0, v4, &v18);
    v8 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      v9 = 102;
      goto LABEL_5;
    }
    v8 = 0;
    *a4 = v4;
    v4 = 0;
  }
  else
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x63u,
      L"RegUtil::GetStringValue",
      L"CPR",
      L"pv",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        99,
        L"RegUtil::GetStringValue",
        L"CPR",
        L"pv",
        -2147024882);
    }
    else
    {
      LODWORD(pcbData) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        99,
        L"RegUtil::GetStringValue",
        L"CPR",
        L"pv",
        pcbData);
    }
  }
LABEL_25:
  operator delete(v4);
  return v8;
}

```

## disassembly

```asm
0x14000aaa4  mov     r11, rsp
0x14000aaa7  mov     [r11+10h], rbx
0x14000aaab  mov     [r11+18h], rbp
0x14000aaaf  mov     [rsp+arg_0], ecx
0x14000aab3  push    rsi
0x14000aab4  push    rdi
0x14000aab5  push    r13
0x14000aab7  push    r14
0x14000aab9  push    r15
0x14000aabb  sub     rsp, 40h
0x14000aabf  xor     ebp, ebp
0x14000aac1  mov     [rsp+68h+arg_0], 0
0x14000aac9  mov     rsi, rdx
0x14000aacc  lea     rax, [r11+8]
0x14000aad0  mov     [r11-38h], rax
0x14000aad4  lea     r8, aProductdumpsdi; "ProductDumpsDir"
0x14000aadb  mov     rdi, r9
0x14000aade  mov     [r11-40h], rbp
0x14000aae2  lea     r14d, [rbp+2]
0x14000aae6  mov     [r11-48h], rbp
0x14000aaea  mov     r9d, r14d; dwFlags
0x14000aaed  xor     edx, edx; lpSubKey
0x14000aaef  mov     rcx, rsi; hkey
0x14000aaf2  call    cs:__imp_RegGetValueW
0x14000aaf8  mov     ebx, eax
0x14000aafa  test    eax, eax
0x14000aafc  jz      loc_14000ABAA
0x14000ab02  jle     short loc_14000AB0D
0x14000ab04  movzx   ebx, ax
0x14000ab07  or      ebx, 80070000h
0x14000ab0d  mov     r13d, 5Eh ; '^'
0x14000ab13  lea     rsi, aRegutilGetstri; "RegUtil::GetStringValue"
0x14000ab1a  mov     dword ptr [rsp+68h+pvData], ebx; int
0x14000ab1e  lea     r14, aCbraex; "CBRAEx"
0x14000ab25  mov     r8, rsi; unsigned __int16 *
0x14000ab28  lea     rdi, aTermsrvWmsSrcC_3; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14000ab2f  mov     r9, r14; unsigned __int16 *
0x14000ab32  lea     r15, aLr0l; "lr == 0L"
0x14000ab39  mov     rcx, rdi; unsigned __int16 *
0x14000ab3c  mov     edx, r13d; unsigned int
0x14000ab3f  mov     [rsp+68h+pdwType], r15; unsigned __int16 *
0x14000ab44  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ab49  call    cs:__imp_IsDebuggerPresent
0x14000ab4f  test    eax, eax
0x14000ab51  jz      short loc_14000AB82
0x14000ab53  mov     [rsp+68h+var_30], ebx
0x14000ab57  mov     r9d, r13d
0x14000ab5a  mov     [rsp+68h+pcbData], r15
0x14000ab5f  mov     [rsp+68h+pvData], r14
0x14000ab64  mov     r8, rdi
0x14000ab67  mov     [rsp+68h+pdwType], rsi
0x14000ab6c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000ab73  mov     ecx, 2; unsigned __int8
0x14000ab78  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000ab7d  jmp     loc_14000ACF4
0x14000ab82  mov     dword ptr [rsp+68h+pcbData], ebx
0x14000ab86  mov     r8d, r13d
0x14000ab89  mov     [rsp+68h+pvData], r15
0x14000ab8e  mov     [rsp+68h+pdwType], r14
0x14000ab93  mov     r9, rsi
0x14000ab96  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000ab9d  mov     rdx, rdi
0x14000aba0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000aba5  jmp     loc_14000ACF4
0x14000abaa  test    byte ptr [rsp+68h+arg_0], 1
0x14000abaf  jz      short loc_14000AC1E
0x14000abb1  mov     ebx, 8000FFFFh
0x14000abb6  lea     r14, aCbraex; "CBRAEx"
0x14000abbd  lea     rsi, aRegutilGetstri; "RegUtil::GetStringValue"
0x14000abc4  mov     dword ptr [rsp+68h+pvData], ebx; int
0x14000abc8  mov     r15d, 60h ; '`'
0x14000abce  lea     rdi, aTermsrvWmsSrcC_3; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14000abd5  lea     r13, aCbSizeofWchar0; "cb % sizeof (WCHAR) == 0"
0x14000abdc  mov     r9, r14; unsigned __int16 *
0x14000abdf  mov     r8, rsi; unsigned __int16 *
0x14000abe2  mov     [rsp+68h+pdwType], r13; unsigned __int16 *
0x14000abe7  mov     edx, r15d; unsigned int
0x14000abea  mov     rcx, rdi; unsigned __int16 *
0x14000abed  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000abf2  call    cs:__imp_IsDebuggerPresent
0x14000abf8  test    eax, eax
0x14000abfa  jz      short loc_14000AC0D
0x14000abfc  mov     [rsp+68h+var_30], ebx
0x14000ac00  mov     r9d, r15d
0x14000ac03  mov     [rsp+68h+pcbData], r13
0x14000ac08  jmp     loc_14000AB5F
0x14000ac0d  mov     dword ptr [rsp+68h+pcbData], ebx
0x14000ac11  mov     r8d, r15d
0x14000ac14  mov     [rsp+68h+pvData], r13
0x14000ac19  jmp     loc_14000AB8E
0x14000ac1e  mov     ecx, [rsp+68h+arg_0]; Size
0x14000ac22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ac27  mov     rbp, rax
0x14000ac2a  test    rax, rax
0x14000ac2d  jnz     short loc_14000ACA4
0x14000ac2f  lea     r14d, [rax+63h]
0x14000ac33  mov     ebx, 8007000Eh
0x14000ac38  lea     r13, aCpr; "CPR"
0x14000ac3f  mov     dword ptr [rsp+68h+pvData], ebx; int
0x14000ac43  lea     rsi, aRegutilGetstri; "RegUtil::GetStringValue"
0x14000ac4a  mov     r9, r13; unsigned __int16 *
0x14000ac4d  lea     rdi, aTermsrvWmsSrcC_3; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x14000ac54  mov     r8, rsi; unsigned __int16 *
0x14000ac57  lea     r15, aPv; "pv"
0x14000ac5e  mov     edx, r14d; unsigned int
0x14000ac61  mov     rcx, rdi; unsigned __int16 *
0x14000ac64  mov     [rsp+68h+pdwType], r15; unsigned __int16 *
0x14000ac69  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000ac6e  call    cs:__imp_IsDebuggerPresent
0x14000ac74  test    eax, eax
0x14000ac76  jz      short loc_14000AC8E
0x14000ac78  mov     [rsp+68h+var_30], ebx
0x14000ac7c  mov     r9d, r14d
0x14000ac7f  mov     [rsp+68h+pcbData], r15
0x14000ac84  mov     [rsp+68h+pvData], r13
0x14000ac89  jmp     loc_14000AB64
0x14000ac8e  mov     dword ptr [rsp+68h+pcbData], ebx
0x14000ac92  mov     r8d, r14d
0x14000ac95  mov     [rsp+68h+pvData], r15
0x14000ac9a  mov     [rsp+68h+pdwType], r13
0x14000ac9f  jmp     loc_14000AB93
0x14000aca4  lea     rax, [rsp+68h+arg_0]
0x14000aca9  mov     r9d, r14d; dwFlags
0x14000acac  mov     [rsp+68h+pcbData], rax; pcbData
0x14000acb1  lea     r8, aProductdumpsdi; "ProductDumpsDir"
0x14000acb8  mov     [rsp+68h+pvData], rbp; pvData
0x14000acbd  xor     edx, edx; lpSubKey
0x14000acbf  mov     rcx, rsi; hkey
0x14000acc2  mov     [rsp+68h+pdwType], 0; pdwType
0x14000accb  call    cs:__imp_RegGetValueW
0x14000acd1  mov     ebx, eax
0x14000acd3  test    eax, eax
0x14000acd5  jz      short loc_14000ACED
0x14000acd7  jle     short loc_14000ACE2
0x14000acd9  movzx   ebx, ax
0x14000acdc  or      ebx, 80070000h
0x14000ace2  mov     r13d, 66h ; 'f'
0x14000ace8  jmp     loc_14000AB13
0x14000aced  xor     ebx, ebx
0x14000acef  mov     [rdi], rbp
0x14000acf2  xor     ebp, ebp
0x14000acf4  mov     rcx, rbp; Block
0x14000acf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000acfc  lea     r11, [rsp+68h+var_28]
0x14000ad01  mov     eax, ebx
0x14000ad03  mov     rbx, [r11+38h]
0x14000ad07  mov     rbp, [r11+40h]
0x14000ad0b  mov     rsp, r11
0x14000ad0e  pop     r15
0x14000ad10  pop     r14
0x14000ad12  pop     r13
0x14000ad14  pop     rdi
0x14000ad15  pop     rsi
0x14000ad16  retn
```

# LoadMUILibraryW

- ea: `0x140026010`
- end: `0x1400264ce`
- name: `LoadMUILibraryW`
- size: `1214`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140001bc8`
- `0x140006cd8`

## callees

- `0x14000dba4`
- `0x140025948`
- `0x140025a54`
- `0x140025b7c`
- `0x140025bf0`
- `0x140025d64`
- `0x140026010`
- `0x14002661e`
- `0x140026650`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400263d8`
- `KERNEL32!FreeLibrary` at `0x14002646d`
- `KERNEL32!FreeLibrary` at `0x14002649c`
- `KERNEL32!FreeLibrary` at `0x1400263d8`
- `KERNEL32!FreeLibrary` at `0x14002646d`
- `KERNEL32!FreeLibrary` at `0x14002649c`
- `KERNEL32!LoadLibraryExW` at `0x140026071`
- `KERNEL32!LoadLibraryExW` at `0x14002648b`
- `KERNEL32!LoadLibraryExW` at `0x140026071`
- `KERNEL32!LoadLibraryExW` at `0x14002648b`
- `KERNEL32!FindResourceExW` at `0x1400260fa`
- `KERNEL32!FindResourceExW` at `0x1400260fa`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140026123`
- `KERNEL32!GetUserDefaultUILanguage` at `0x140026123`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140026219`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140026219`
- `KERNEL32!GetLocaleInfoW` at `0x140026153`
- `KERNEL32!GetLocaleInfoW` at `0x140026153`
- `KERNEL32!SearchPathW` at `0x1400260b4`
- `KERNEL32!SearchPathW` at `0x1400260b4`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v6; // rdi
  WCHAR *v7; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v11; // r15
  bool v12; // zf
  __int64 InstallLanguage; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR LCData[32]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_14003F880 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_14003F880 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_14003F880 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v6);
    return 0;
  }
  if ( FilePart )
  {
    v7 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v7 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v6, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( !LangID )
    {
      if ( (dword_14003F880 & 4) == 0 )
      {
        if ( (dword_14003F880 & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
            v12 = (_WORD)InstallLanguage == 1033;
LABEL_36:
            if ( !v12 )
            {
              LookupLangID(1033, v21, v23, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
LABEL_38:
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
            if ( MUIFile )
            {
LABEL_46:
              FreeLibrary(v6);
              return MUIFile;
            }
          }
        }
        goto LABEL_39;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage != 1028 )
        goto LABEL_15;
      UserDefaultUILanguage = 3076;
      if ( !GetLocaleInfoW(0x404u, 8u, LCData, 32) || !wcsncmp_0(LCData, &word_14003A1F0, 3u) )
        goto LABEL_15;
      while ( 1 )
      {
        UserDefaultUILanguage = 1028;
LABEL_15:
        if ( !(unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
        if ( MUIFile )
          goto LABEL_46;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
        if ( MUIFile )
          goto LABEL_46;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
          if ( MUIFile )
            goto LABEL_46;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              goto LABEL_39;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_38;
          v12 = v11 == 1033;
          goto LABEL_36;
        }
      }
    }
    if ( (dword_14003F880 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
LABEL_45:
      if ( MUIFile )
        goto LABEL_46;
    }
  }
LABEL_39:
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType(v15, v14) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v17, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140026010  mov     [rsp-8+arg_8], rbx
0x140026015  push    rbp
0x140026016  push    rsi
0x140026017  push    rdi
0x140026018  push    r12
0x14002601a  push    r13
0x14002601c  push    r14
0x14002601e  push    r15
0x140026020  lea     rbp, [rsp-3B0h]
0x140026028  sub     rsp, 4B0h
0x14002602f  mov     rax, cs:__security_cookie
0x140026036  xor     rax, rsp
0x140026039  mov     [rbp+3E0h+var_40], rax
0x140026040  xor     r13d, r13d
0x140026043  movzx   ebx, r8w
0x140026047  mov     [rsp+4E0h+FilePart], r13
0x14002604c  mov     r12, rcx
0x14002604f  test    rcx, rcx
0x140026052  jz      loc_1400264A2
0x140026058  call    GetOSType
0x14002605d  mov     cs:dword_14003F880, eax
0x140026063  xor     edx, edx; hFile
0x140026065  and     eax, 20h
0x140026068  mov     rcx, r12; lpLibFileName
0x14002606b  or      eax, 2
0x14002606e  mov     r8d, eax; dwFlags
0x140026071  call    cs:__imp_LoadLibraryExW
0x140026077  mov     rdi, rax
0x14002607a  test    rax, rax
0x14002607d  jz      loc_1400264A2
0x140026083  test    byte ptr cs:dword_14003F880, 20h
0x14002608a  jnz     loc_1400264A4
0x140026090  lea     rax, [rsp+4E0h+FilePart]
0x140026095  mov     r9d, 104h; nBufferLength
0x14002609b  mov     [rsp+4E0h+lpFilePart], rax; lpFilePart
0x1400260a0  xor     r8d, r8d; lpExtension
0x1400260a3  lea     rax, [rbp+3E0h+Buffer]
0x1400260aa  mov     rdx, r12; lpFileName
0x1400260ad  xor     ecx, ecx; lpPath
0x1400260af  mov     [rsp+4E0h+lpBuffer], rax; lpBuffer
0x1400260b4  call    cs:__imp_SearchPathW
0x1400260ba  test    eax, eax
0x1400260bc  jz      loc_140026499
0x1400260c2  mov     rcx, [rsp+4E0h+FilePart]
0x1400260c7  test    rcx, rcx
0x1400260ca  jnz     short loc_1400260DD
0x1400260cc  lea     rax, [rbp+3E0h+Buffer]
0x1400260d3  mov     esi, r13d
0x1400260d6  mov     [rsp+4E0h+FilePart], rax
0x1400260db  jmp     short loc_1400260E9
0x1400260dd  lea     rsi, [rbp+3E0h+Buffer]
0x1400260e4  mov     [rcx-2], r13w
0x1400260e9  xor     r9d, r9d; wLanguage
0x1400260ec  lea     rdx, Type; "MUI"
0x1400260f3  mov     rcx, rdi; hModule
0x1400260f6  lea     r8d, [r9+1]; lpName
0x1400260fa  call    cs:__imp_FindResourceExW
0x140026100  test    rax, rax
0x140026103  jz      loc_1400263CB
0x140026109  test    bx, bx
0x14002610c  jnz     loc_140026425
0x140026112  mov     eax, cs:dword_14003F880
0x140026118  test    al, 4
0x14002611a  jz      loc_1400262D0
0x140026120  mov     rbx, r13
0x140026123  call    cs:__imp_GetUserDefaultUILanguage
0x140026129  mov     r15d, 404h
0x14002612f  movzx   r14d, ax
0x140026133  cmp     ax, r15w
0x140026137  jnz     short loc_14002617E
0x140026139  mov     r9d, 20h ; ' '; cchData
0x14002613f  lea     r8, [rbp+3E0h+LCData]; lpLCData
0x140026146  mov     ecx, r15d; Locale
0x140026149  mov     r14d, 0C04h
0x14002614f  lea     edx, [r9-18h]; LCType
0x140026153  call    cs:__imp_GetLocaleInfoW
0x140026159  test    eax, eax
0x14002615b  jz      short loc_14002617E
0x14002615d  mov     r8d, 3; MaxCount
0x140026163  lea     rdx, word_14003A1F0; String2
0x14002616a  lea     rcx, [rbp+3E0h+LCData]; String1
0x140026171  call    wcsncmp_0
0x140026176  test    eax, eax
0x140026178  jz      short loc_14002617E
0x14002617a  movzx   r14d, r15w
0x14002617e  lea     r9, [rbp+3E0h+var_3F0]
0x140026182  movzx   ecx, r14w
0x140026186  lea     r8, [rbp+3E0h+var_340]
0x14002618d  lea     rdx, [rsp+4E0h+var_4A0]
0x140026192  call    LookupLangID
0x140026197  test    eax, eax
0x140026199  jz      loc_140026461
0x14002619f  mov     r9, [rsp+4E0h+FilePart]
0x1400261a4  lea     r8, [rsp+4E0h+var_4A0]
0x1400261a9  mov     rdx, rsi
0x1400261ac  mov     rcx, rdi
0x1400261af  call    LoadMUIFile
0x1400261b4  mov     rbx, rax
0x1400261b7  test    rax, rax
0x1400261ba  jnz     loc_14002646A
0x1400261c0  mov     r9, [rsp+4E0h+FilePart]
0x1400261c5  lea     r8, [rbp+3E0h+var_340]
0x1400261cc  mov     rdx, rsi
0x1400261cf  mov     rcx, rdi
0x1400261d2  call    LoadMUIFile
0x1400261d7  mov     rbx, rax
0x1400261da  test    rax, rax
0x1400261dd  jnz     loc_14002646A
0x1400261e3  cmp     [rbp+3E0h+var_3F0], r13w
0x1400261e8  jz      short loc_14002620A
0x1400261ea  mov     r9, [rsp+4E0h+FilePart]
0x1400261ef  lea     r8, [rbp+3E0h+var_3F0]
0x1400261f3  mov     rdx, rsi
0x1400261f6  mov     rcx, rdi
0x1400261f9  call    LoadMUIFile
0x1400261fe  mov     rbx, rax
0x140026201  test    rax, rax
0x140026204  jnz     loc_14002646A
0x14002620a  mov     eax, 0C04h
0x14002620f  cmp     r14w, ax
0x140026213  jz      loc_14002617A
0x140026219  call    cs:__imp_GetSystemDefaultUILanguage
0x14002621f  movzx   r15d, ax
0x140026223  cmp     ax, r14w
0x140026227  jz      loc_1400262B8
0x14002622d  lea     r9, [rbp+3E0h+var_3F0]
0x140026231  movzx   ecx, ax
0x140026234  lea     r8, [rbp+3E0h+var_340]
0x14002623b  lea     rdx, [rsp+4E0h+var_4A0]
0x140026240  call    LookupLangID
0x140026245  test    eax, eax
0x140026247  jz      loc_1400263CB
0x14002624d  mov     r9, [rsp+4E0h+FilePart]
0x140026252  lea     r8, [rsp+4E0h+var_4A0]
0x140026257  mov     rdx, rsi
0x14002625a  mov     rcx, rdi
0x14002625d  call    LoadMUIFile
0x140026262  mov     rbx, rax
0x140026265  test    rax, rax
0x140026268  jnz     loc_14002646A
0x14002626e  mov     r9, [rsp+4E0h+FilePart]
0x140026273  lea     r8, [rbp+3E0h+var_340]
0x14002627a  mov     rdx, rsi
0x14002627d  mov     rcx, rdi
0x140026280  call    LoadMUIFile
0x140026285  mov     rbx, rax
0x140026288  test    rax, rax
0x14002628b  jnz     loc_14002646A
0x140026291  cmp     [rbp+3E0h+var_3F0], r13w
0x140026296  jz      short loc_1400262B8
0x140026298  mov     r9, [rsp+4E0h+FilePart]
0x14002629d  lea     r8, [rbp+3E0h+var_3F0]
0x1400262a1  mov     rdx, rsi
0x1400262a4  mov     rcx, rdi
0x1400262a7  call    LoadMUIFile
0x1400262ac  mov     rbx, rax
0x1400262af  test    rax, rax
0x1400262b2  jnz     loc_14002646A
0x1400262b8  mov     ecx, 409h
0x1400262bd  cmp     cx, r14w
0x1400262c1  jz      loc_1400263AC
0x1400262c7  cmp     cx, r15w
0x1400262cb  jmp     loc_140026375
0x1400262d0  test    al, 3
0x1400262d2  jz      loc_1400263CB
0x1400262d8  call    GetInstallLanguage
0x1400262dd  lea     r9, [rbp+3E0h+var_3F0]
0x1400262e1  movzx   ecx, ax
0x1400262e4  lea     r8, [rbp+3E0h+var_340]
0x1400262eb  movzx   r14d, ax
0x1400262ef  lea     rdx, [rsp+4E0h+var_4A0]
0x1400262f4  call    LookupLangID
0x1400262f9  test    eax, eax
0x1400262fb  jz      loc_1400263CB
0x140026301  mov     r9, [rsp+4E0h+FilePart]
0x140026306  lea     r8, [rsp+4E0h+var_4A0]
0x14002630b  mov     rdx, rsi
0x14002630e  mov     rcx, rdi
0x140026311  call    LoadMUIFile
0x140026316  mov     rbx, rax
0x140026319  test    rax, rax
0x14002631c  jnz     loc_14002646A
0x140026322  mov     r9, [rsp+4E0h+FilePart]
0x140026327  lea     r8, [rbp+3E0h+var_340]
0x14002632e  mov     rdx, rsi
0x140026331  mov     rcx, rdi
0x140026334  call    LoadMUIFile
0x140026339  mov     rbx, rax
0x14002633c  test    rax, rax
0x14002633f  jnz     loc_14002646A
0x140026345  cmp     [rbp+3E0h+var_3F0], r13w
0x14002634a  jz      short loc_14002636C
0x14002634c  mov     r9, [rsp+4E0h+FilePart]
0x140026351  lea     r8, [rbp+3E0h+var_3F0]
0x140026355  mov     rdx, rsi
0x140026358  mov     rcx, rdi
0x14002635b  call    LoadMUIFile
0x140026360  mov     rbx, rax
0x140026363  test    rax, rax
0x140026366  jnz     loc_14002646A
0x14002636c  mov     ecx, 409h
0x140026371  cmp     cx, r14w
0x140026375  jz      short loc_1400263AC
0x140026377  xor     r9d, r9d
0x14002637a  lea     r8, [rbp+3E0h+var_340]
0x140026381  lea     rdx, [rsp+4E0h+var_4A0]
0x140026386  call    LookupLangID
0x14002638b  mov     r9, [rsp+4E0h+FilePart]
0x140026390  lea     r8, [rsp+4E0h+var_4A0]
0x140026395  mov     rdx, rsi
0x140026398  mov     rcx, rdi
0x14002639b  call    LoadMUIFile
0x1400263a0  mov     rbx, rax
0x1400263a3  test    rax, rax
0x1400263a6  jnz     loc_14002646A
0x1400263ac  mov     r9, [rsp+4E0h+FilePart]
0x1400263b1  xor     r8d, r8d
0x1400263b4  mov     rdx, rsi
0x1400263b7  mov     rcx, rdi
0x1400263ba  call    LoadMUIFile
0x1400263bf  mov     rbx, rax
0x1400263c2  test    rax, rax
0x1400263c5  jnz     loc_14002646A
0x1400263cb  test    dil, 1
0x1400263cf  jz      loc_140026494
0x1400263d5  mov     rcx, rdi; hLibModule
0x1400263d8  call    cs:__imp_FreeLibrary
0x1400263de  call    GetOSType
0x1400263e3  test    al, 38h
0x1400263e5  jz      loc_140026478
0x1400263eb  mov     rax, [rsp+4E0h+FilePart]
0x1400263f0  lea     r8, aSS; "%s\\%s"
0x1400263f7  mov     r9, rsi
0x1400263fa  mov     [rsp+4E0h+lpBuffer], rax
0x1400263ff  mov     edx, 104h; unsigned __int64
0x140026404  lea     rcx, [rbp+3E0h+Buffer]; unsigned __int16 *
0x14002640b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140026410  xor     r8d, r8d
0x140026413  lea     rcx, [rbp+3E0h+Buffer]
0x14002641a  lea     edx, [r8+1]
0x14002641e  call    MapMUIFile
0x140026423  jmp     short loc_140026491
0x140026425  test    byte ptr cs:dword_14003F880, 7
0x14002642c  jz      short loc_1400263CB
0x14002642e  xor     r9d, r9d
0x140026431  lea     r8, [rbp+3E0h+var_340]
0x140026438  lea     rdx, [rsp+4E0h+var_4A0]
0x14002643d  movzx   ecx, bx
0x140026440  call    LookupLangID
0x140026445  test    eax, eax
0x140026447  jz      short loc_1400263CB
0x140026449  mov     r9, [rsp+4E0h+FilePart]
0x14002644e  lea     r8, [rsp+4E0h+var_4A0]
0x140026453  mov     rdx, rsi
0x140026456  mov     rcx, rdi
0x140026459  call    LoadMUIFile
0x14002645e  mov     rbx, rax
0x140026461  test    rbx, rbx
0x140026464  jz      loc_1400263CB
0x14002646a  mov     rcx, rdi; hLibModule
0x14002646d  call    cs:__imp_FreeLibrary
0x140026473  mov     rax, rbx
0x140026476  jmp     short loc_1400264A4
0x140026478  call    GetOSType
0x14002647d  test    al, 26h
0x14002647f  mov     r8d, r13d
0x140026482  mov     rcx, r12; lpLibFileName
0x140026485  setnz   r8b; dwFlags
0x140026489  xor     edx, edx; hFile
0x14002648b  call    cs:__imp_LoadLibraryExW
0x140026491  mov     rdi, rax
0x140026494  mov     rax, rdi
0x140026497  jmp     short loc_1400264A4
0x140026499  mov     rcx, rdi; hLibModule
0x14002649c  call    cs:__imp_FreeLibrary
0x1400264a2  xor     eax, eax
0x1400264a4  mov     rcx, [rbp+3E0h+var_40]
0x1400264ab  xor     rcx, rsp; StackCookie
0x1400264ae  call    __security_check_cookie
0x1400264b3  mov     rbx, [rsp+4E0h+arg_8]
0x1400264bb  add     rsp, 4B0h
0x1400264c2  pop     r15
0x1400264c4  pop     r14
0x1400264c6  pop     r13
0x1400264c8  pop     r12
0x1400264ca  pop     rdi
0x1400264cb  pop     rsi
0x1400264cc  pop     rbp
0x1400264cd  retn
```

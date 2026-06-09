# ScriptUtils::GetAllowedRightsFromAcl(_ACL *,void *,ulong *)

- ea: `0x14002cbcc`
- end: `0x14002cdff`
- name: `?GetAllowedRightsFromAcl@ScriptUtils@@YAJPEAU_ACL@@PEAXPEAK@Z`
- size: `563`
- prototype: `__int64 __fastcall(PACL pAcl, PSID pSid1, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14002c950`

## callees

- `0x14002cbcc`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!GetAclInformation` at `0x14002cc23`
- `ADVAPI32!GetAclInformation` at `0x14002cc23`
- `ADVAPI32!GetAce` at `0x14002cc6f`
- `ADVAPI32!GetAce` at `0x14002cc6f`
- `ADVAPI32!EqualSid` at `0x14002cc92`
- `ADVAPI32!EqualSid` at `0x14002cc92`
- `KERNEL32!GetLastError` at `0x14002cc2d`
- `KERNEL32!GetLastError` at `0x14002cd28`
- `KERNEL32!GetLastError` at `0x14002cc2d`
- `KERNEL32!GetLastError` at `0x14002cd28`
- `KERNEL32!IsDebuggerPresent` at `0x14002ccf2`
- `KERNEL32!IsDebuggerPresent` at `0x14002cd83`
- `KERNEL32!IsDebuggerPresent` at `0x14002ccf2`
- `KERNEL32!IsDebuggerPresent` at `0x14002cd83`

## string_xrefs

- `0x14002ccbf`: `ScriptUtils::GetAllowedRightsFromAcl`
- `0x14002cd51`: `ScriptUtils::GetAllowedRightsFromAcl`

## pseudocode

```c
__int64 __fastcall ScriptUtils::GetAllowedRightsFromAcl(PACL pAcl, PSID pSid1, _DWORD *a3, unsigned int *a4)
{
  signed int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r12d
  DWORD v10; // edi
  signed int LastError; // eax
  LPVOID pAce; // [rsp+40h] [rbp-48h] BYREF
  DWORD v14; // [rsp+48h] [rbp-40h] BYREF
  __int64 v15; // [rsp+4Ch] [rbp-3Ch]

  *a3 = 0;
  v14 = 0;
  pAce = 0;
  v15 = 8;
  if ( GetAclInformation(pAcl, &v14, 0xCu, AclSizeInformation) )
  {
    v8 = 0;
    if ( !v14 )
      return v8;
    v10 = 0;
    while ( GetAce(pAcl, v10, &pAce) )
    {
      if ( !pAce )
      {
        v8 = -2147024882;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
          0x30u,
          L"ScriptUtils::GetAllowedRightsFromAcl",
          L"CPR",
          L"pACE",
          -2147024882);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
            48,
            L"ScriptUtils::GetAllowedRightsFromAcl",
            L"CPR",
            L"pACE",
            -2147024882);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
            48,
            L"ScriptUtils::GetAllowedRightsFromAcl",
            L"CPR",
            L"pACE",
            -2147024882);
        return v8;
      }
      if ( !*(_BYTE *)pAce && EqualSid(pSid1, (char *)pAce + 8) )
        *a3 |= *((_DWORD *)pAce + 1);
      if ( ++v10 >= v14 )
        return v8;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = 47;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v9 = 36;
  }
  if ( (v8 & 0x80000000) == 0 )
    v8 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
    v9,
    L"ScriptUtils::GetAllowedRightsFromAcl",
    L"CBRAEx",
    L"fRet",
    v8);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
      v9,
      L"ScriptUtils::GetAllowedRightsFromAcl",
      L"CBRAEx",
      L"fRet",
      v8);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
      v9,
      L"ScriptUtils::GetAllowedRightsFromAcl",
      L"CBRAEx",
      L"fRet",
      v8);
  return v8;
}

```

## disassembly

```asm
0x14002cbcc  mov     r11, rsp
0x14002cbcf  mov     [r11+20h], rbx
0x14002cbd3  push    rbp
0x14002cbd4  push    rsi
0x14002cbd5  push    rdi
0x14002cbd6  push    r12
0x14002cbd8  push    r14
0x14002cbda  sub     rsp, 60h
0x14002cbde  mov     rax, cs:__security_cookie
0x14002cbe5  xor     rax, rsp
0x14002cbe8  mov     [rsp+88h+var_30], rax
0x14002cbed  mov     r9d, 2; dwAclInformationClass
0x14002cbf3  mov     dword ptr [r8], 0
0x14002cbfa  mov     rsi, r8
0x14002cbfd  mov     [rsp+88h+var_40], 0
0x14002cc05  mov     r14, rdx
0x14002cc08  mov     qword ptr [r11-48h], 0
0x14002cc10  lea     rdx, [r11-40h]; pAclInformation
0x14002cc14  mov     qword ptr [r11-3Ch], 8
0x14002cc1c  lea     r8d, [r9+0Ah]; nAclInformationLength
0x14002cc20  mov     rbp, rcx
0x14002cc23  call    cs:__imp_GetAclInformation
0x14002cc29  test    eax, eax
0x14002cc2b  jnz     short loc_14002CC4D
0x14002cc2d  call    cs:__imp_GetLastError
0x14002cc33  mov     ebx, eax
0x14002cc35  test    eax, eax
0x14002cc37  jle     short loc_14002CC42
0x14002cc39  movzx   ebx, ax
0x14002cc3c  or      ebx, 80070000h
0x14002cc42  mov     r12d, 24h ; '$'
0x14002cc48  jmp     loc_14002CD43
0x14002cc4d  mov     eax, [rsp+88h+var_40]
0x14002cc51  xor     ebx, ebx
0x14002cc53  test    eax, eax
0x14002cc55  jz      loc_14002CDDC
0x14002cc5b  xor     edi, edi
0x14002cc5d  test    eax, eax
0x14002cc5f  jz      loc_14002CDDC
0x14002cc65  lea     r8, [rsp+88h+pAce]; pAce
0x14002cc6a  mov     edx, edi; dwAceIndex
0x14002cc6c  mov     rcx, rbp; pAcl
0x14002cc6f  call    cs:__imp_GetAce
0x14002cc75  test    eax, eax
0x14002cc77  jz      loc_14002CD28
0x14002cc7d  mov     rdx, [rsp+88h+pAce]
0x14002cc82  test    rdx, rdx
0x14002cc85  jz      short loc_14002CCB3
0x14002cc87  cmp     [rdx], bl
0x14002cc89  jnz     short loc_14002CCA6
0x14002cc8b  add     rdx, 8; pSid2
0x14002cc8f  mov     rcx, r14; pSid1
0x14002cc92  call    cs:__imp_EqualSid
0x14002cc98  test    eax, eax
0x14002cc9a  jz      short loc_14002CCA6
0x14002cc9c  mov     rax, [rsp+88h+pAce]
0x14002cca1  mov     ecx, [rax+4]
0x14002cca4  or      [rsi], ecx
0x14002cca6  inc     edi
0x14002cca8  cmp     edi, [rsp+88h+var_40]
0x14002ccac  jb      short loc_14002CC65
0x14002ccae  jmp     loc_14002CDDC
0x14002ccb3  mov     ebx, 8007000Eh
0x14002ccb8  lea     r12, aCpr; "CPR"
0x14002ccbf  lea     rsi, aScriptutilsGet; "ScriptUtils::GetAllowedRightsFromAcl"
0x14002ccc6  mov     [rsp+88h+var_60], ebx; int
0x14002ccca  mov     ebp, 30h ; '0'
0x14002cccf  lea     rdi, aTermsrvWmsSrcD_1; "termsrv\\wms\\src\\devices\\wmssvc\\scr"...
0x14002ccd6  lea     r14, aPace; "pACE"
0x14002ccdd  mov     r9, r12; unsigned __int16 *
0x14002cce0  mov     r8, rsi; unsigned __int16 *
0x14002cce3  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x14002cce8  mov     edx, ebp; unsigned int
0x14002ccea  mov     rcx, rdi; unsigned __int16 *
0x14002cced  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ccf2  call    cs:__imp_IsDebuggerPresent
0x14002ccf8  test    eax, eax
0x14002ccfa  jz      short loc_14002CD12
0x14002ccfc  mov     [rsp+88h+var_50], ebx
0x14002cd00  mov     r9d, ebp
0x14002cd03  mov     [rsp+88h+var_58], r14
0x14002cd08  mov     qword ptr [rsp+88h+var_60], r12
0x14002cd0d  jmp     loc_14002CD9E
0x14002cd12  mov     dword ptr [rsp+88h+var_58], ebx
0x14002cd16  mov     r8d, ebp
0x14002cd19  mov     qword ptr [rsp+88h+var_60], r14
0x14002cd1e  mov     [rsp+88h+var_68], r12
0x14002cd23  jmp     loc_14002CDCA
0x14002cd28  call    cs:__imp_GetLastError
0x14002cd2e  mov     ebx, eax
0x14002cd30  test    eax, eax
0x14002cd32  jle     short loc_14002CD3D
0x14002cd34  movzx   ebx, ax
0x14002cd37  or      ebx, 80070000h
0x14002cd3d  mov     r12d, 2Fh ; '/'
0x14002cd43  mov     eax, 80004005h
0x14002cd48  lea     r14, aCbraex; "CBRAEx"
0x14002cd4f  test    ebx, ebx
0x14002cd51  lea     rsi, aScriptutilsGet; "ScriptUtils::GetAllowedRightsFromAcl"
0x14002cd58  lea     rdi, aTermsrvWmsSrcD_1; "termsrv\\wms\\src\\devices\\wmssvc\\scr"...
0x14002cd5f  mov     r9, r14; unsigned __int16 *
0x14002cd62  cmovns  ebx, eax
0x14002cd65  lea     rbp, aFret; "fRet"
0x14002cd6c  mov     [rsp+88h+var_60], ebx; int
0x14002cd70  mov     r8, rsi; unsigned __int16 *
0x14002cd73  mov     edx, r12d; unsigned int
0x14002cd76  mov     [rsp+88h+var_68], rbp; unsigned __int16 *
0x14002cd7b  mov     rcx, rdi; unsigned __int16 *
0x14002cd7e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002cd83  call    cs:__imp_IsDebuggerPresent
0x14002cd89  test    eax, eax
0x14002cd8b  jz      short loc_14002CDB9
0x14002cd8d  mov     [rsp+88h+var_50], ebx
0x14002cd91  mov     r9d, r12d
0x14002cd94  mov     [rsp+88h+var_58], rbp
0x14002cd99  mov     qword ptr [rsp+88h+var_60], r14
0x14002cd9e  mov     r8, rdi
0x14002cda1  mov     [rsp+88h+var_68], rsi
0x14002cda6  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002cdad  mov     ecx, 2; unsigned __int8
0x14002cdb2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002cdb7  jmp     short loc_14002CDDC
0x14002cdb9  mov     dword ptr [rsp+88h+var_58], ebx
0x14002cdbd  mov     r8d, r12d
0x14002cdc0  mov     qword ptr [rsp+88h+var_60], rbp
0x14002cdc5  mov     [rsp+88h+var_68], r14
0x14002cdca  mov     r9, rsi
0x14002cdcd  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002cdd4  mov     rdx, rdi
0x14002cdd7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002cddc  mov     eax, ebx
0x14002cdde  mov     rcx, [rsp+88h+var_30]
0x14002cde3  xor     rcx, rsp; StackCookie
0x14002cde6  call    __security_check_cookie
0x14002cdeb  mov     rbx, [rsp+88h+arg_18]
0x14002cdf3  add     rsp, 60h
0x14002cdf7  pop     r14
0x14002cdf9  pop     r12
0x14002cdfb  pop     rdi
0x14002cdfc  pop     rsi
0x14002cdfd  pop     rbp
0x14002cdfe  retn
```

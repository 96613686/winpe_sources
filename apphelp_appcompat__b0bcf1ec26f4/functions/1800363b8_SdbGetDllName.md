# SdbGetDllName

- ea: `0x1800363b8`
- end: `0x18003663a`
- name: `SdbGetDllName`
- size: `642`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18000607c`
- `0x180047ed0`

## callees

- `0x1800055e0`
- `0x180006c20`
- `0x180009e94`
- `0x180009f10`
- `0x18000ae70`
- `0x18000f114`
- `0x1800212c4`
- `0x18002bf3c`
- `0x1800363b8`
- `0x180039a5a`
- `0x180039a66`
- `0x18004842c`
- `0x18004ec04`
- `0x180059270`

## import_xrefs

- `ntdll!ZwQuerySystemInformation` at `0x180036559`
- `ntdll!ZwQuerySystemInformation` at `0x180036559`

## string_xrefs

- `0x1800364a4`: `AcPlugin_`
- `0x180036418`: `SdbGetDllName`
- `0x18003647c`: `SdbGetDllName`
- `0x1800364f1`: `SdbGetDllName`
- `0x180036587`: `SdbGetDllName`
- `0x180036447`: `No DLLFILE for the SHIM in LIBRARY`
- `0x18003646f`: `Can't read DLL name`
- `0x1800364e4`: `Can't get shim plugin directory [%x]`
- `0x18003657a`: `Ignoring reference to non-system DLLFILE '%ls'`

## pseudocode

```c
__int64 __fastcall SdbGetDllName(__int64 a1, int a2, _WORD *a3, unsigned int a4)
{
  __int64 v4; // rsi
  unsigned int ItemFromItemRef; // eax
  HRESULT ShimPluginDirectory; // ebx
  unsigned int FirstTagRef; // eax
  __int64 SystemInformation; // [rsp+38h] [rbp-460h] BYREF
  wchar_t String1[264]; // [rsp+40h] [rbp-458h] BYREF
  wchar_t pszDest[264]; // [rsp+250h] [rbp-248h] BYREF

  v4 = a4;
  SystemInformation = 0;
  *a3 = 0;
  ItemFromItemRef = SdbGetItemFromItemRef(a1, a2, 24577, 16388, 28676);
  if ( !ItemFromItemRef )
  {
    AslLogCallPrintf(1, "SdbGetDllName", 2032, "No SHIM in LIBRARY");
    return (unsigned int)-1073741275;
  }
  FirstTagRef = SdbFindFirstTagRef(a1, ItemFromItemRef, 24586);
  if ( !FirstTagRef )
  {
    AslLogCallPrintf(1, "SdbGetDllName", 2045, "No DLLFILE for the SHIM in LIBRARY");
    return (unsigned int)-1073741275;
  }
  if ( (unsigned int)SdbReadStringTagRef(a1, FirstTagRef, String1, 260) )
  {
    pszDest[0] = 0;
    if ( wcsnicmp_0(String1, L"AcPlugin_", 9u)
      || (ShimPluginDirectory = SdbpGetShimPluginDirectory(pszDest), (int)(ShimPluginDirectory + 0x80000000) < 0)
      || ShimPluginDirectory == -1073741275 )
    {
      if ( wcsicmp_0(String1, L"INTERNAL") )
      {
        if ( (unsigned int)SdbIsKnownShimDll(String1)
          || (LODWORD(SystemInformation) = 8,
              ShimPluginDirectory = ZwQuerySystemInformation(
                                      MaxSystemInfoClass|SystemProcessInformation,
                                      &SystemInformation,
                                      8u,
                                      0),
              ShimPluginDirectory >= 0)
          && (SystemInformation & 0x200000000LL) != 0 )
        {
          if ( !pszDest[0]
            || (ShimPluginDirectory = StringCchCatW(pszDest, 0x104u, String1), ShimPluginDirectory >= 0)
            && (ShimPluginDirectory = StringCchCopyW(String1, 0x104u, pszDest), ShimPluginDirectory >= 0) )
          {
            ShimPluginDirectory = RtlStringCchCopyW(a3, v4, String1);
            if ( ShimPluginDirectory >= 0 )
              return 0;
          }
        }
        else
        {
          AslLogCallPrintf(3, "SdbGetDllName", 2093, "Ignoring reference to non-system DLLFILE '%ls'", String1);
          if ( ShimPluginDirectory >= 0 )
            return (unsigned int)-1073700864;
        }
      }
      else
      {
        return (unsigned int)RtlStringCchCopyW(a3, v4, String1);
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetDllName", 2074, "Can't get shim plugin directory [%x]", ShimPluginDirectory);
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbGetDllName", 2051, "Can't read DLL name");
    return (unsigned int)-1073741480;
  }
  return (unsigned int)ShimPluginDirectory;
}

```

## disassembly

```asm
0x1800363b8  push    rbx
0x1800363ba  push    rsi
0x1800363bb  push    rdi
0x1800363bc  push    r14
0x1800363be  sub     rsp, 478h
0x1800363c5  mov     rax, cs:__security_cookie
0x1800363cc  xor     rax, rsp
0x1800363cf  mov     [rsp+498h+var_38], rax
0x1800363d7  mov     esi, r9d
0x1800363da  mov     rdi, r8
0x1800363dd  mov     rbx, rcx
0x1800363e0  xor     r14d, r14d
0x1800363e3  mov     [rsp+498h+SystemInformation], r14
0x1800363e8  mov     [r8], r14w
0x1800363ec  mov     eax, 7004h
0x1800363f1  mov     r9d, 4004h
0x1800363f7  mov     r8d, 6001h
0x1800363fd  mov     word ptr [rsp+498h+var_478], ax
0x180036402  call    SdbGetItemFromItemRef
0x180036407  test    eax, eax
0x180036409  jnz     short loc_180036433
0x18003640b  lea     r9, aNoShimInLibrar; "No SHIM in LIBRARY"
0x180036412  mov     r8d, 7F0h
0x180036418  lea     rdx, aSdbgetdllname; "SdbGetDllName"
0x18003641f  mov     ecx, 1
0x180036424  call    AslLogCallPrintf
0x180036429  mov     ebx, 0C0000225h
0x18003642e  jmp     loc_18003660C
0x180036433  mov     r8d, 600Ah
0x180036439  mov     edx, eax
0x18003643b  mov     rcx, rbx
0x18003643e  call    SdbFindFirstTagRef
0x180036443  test    eax, eax
0x180036445  jnz     short loc_180036456
0x180036447  lea     r9, aNoDllfileForTh; "No DLLFILE for the SHIM in LIBRARY"
0x18003644e  mov     r8d, 7FDh
0x180036454  jmp     short loc_180036418
0x180036456  mov     r9d, 104h
0x18003645c  lea     r8, [rsp+498h+String1]
0x180036461  mov     edx, eax
0x180036463  mov     rcx, rbx
0x180036466  call    SdbReadStringTagRef
0x18003646b  test    eax, eax
0x18003646d  jnz     short loc_180036495
0x18003646f  lea     r9, aCanTReadDllNam; "Can't read DLL name"
0x180036476  mov     r8d, 803h
0x18003647c  lea     rdx, aSdbgetdllname; "SdbGetDllName"
0x180036483  lea     ecx, [rax+1]
0x180036486  call    AslLogCallPrintf
0x18003648b  mov     ebx, 0C0000158h
0x180036490  jmp     loc_18003660C
0x180036495  mov     [rsp+498h+pszDest], r14w
0x18003649e  mov     r8d, 9; MaxCount
0x1800364a4  lea     rdx, aAcplugin; "AcPlugin_"
0x1800364ab  lea     rcx, [rsp+498h+String1]; String1
0x1800364b0  call    _wcsnicmp_0
0x1800364b5  test    eax, eax
0x1800364b7  jnz     short loc_180036507
0x1800364b9  lea     rcx, [rsp+498h+pszDest]; SourceString
0x1800364c1  call    SdbpGetShimPluginDirectory
0x1800364c6  mov     ebx, eax
0x1800364c8  mov     [rsp+498h+var_468], eax
0x1800364cc  mov     eax, 80000000h
0x1800364d1  lea     ecx, [rbx+rax]
0x1800364d4  test    eax, ecx
0x1800364d6  jnz     short loc_180036507
0x1800364d8  cmp     ebx, 0C0000225h
0x1800364de  jz      short loc_180036507
0x1800364e0  mov     dword ptr [rsp+498h+var_478], ebx
0x1800364e4  lea     r9, aCanTGetShimPlu; "Can't get shim plugin directory [%x]"
0x1800364eb  mov     r8d, 81Ah
0x1800364f1  lea     rdx, aSdbgetdllname; "SdbGetDllName"
0x1800364f8  mov     ecx, 1
0x1800364fd  call    AslLogCallPrintf
0x180036502  jmp     loc_180036610
0x180036507  lea     rdx, aInternal; "INTERNAL"
0x18003650e  lea     rcx, [rsp+498h+String1]; String1
0x180036513  call    _wcsicmp_0
0x180036518  test    eax, eax
0x18003651a  jnz     short loc_180036537
0x18003651c  mov     rdx, rsi
0x18003651f  lea     r8, [rsp+498h+String1]
0x180036524  mov     rcx, rdi
0x180036527  call    RtlStringCchCopyW
0x18003652c  mov     ebx, eax
0x18003652e  mov     [rsp+498h+var_468], eax
0x180036532  jmp     loc_180036610
0x180036537  lea     rcx, [rsp+498h+String1]; String1
0x18003653c  call    SdbIsKnownShimDll
0x180036541  test    eax, eax
0x180036543  jnz     short loc_1800365A3
0x180036545  lea     r8d, [rax+8]; SystemInformationLength
0x180036549  mov     dword ptr [rsp+498h+SystemInformation], r8d
0x18003654e  xor     r9d, r9d; ReturnLength
0x180036551  lea     rdx, [rsp+498h+SystemInformation]; SystemInformation
0x180036556  lea     ecx, [rax+67h]; SystemInformationClass
0x180036559  call    cs:__imp_ZwQuerySystemInformation
0x18003655f  mov     ebx, eax
0x180036561  mov     [rsp+498h+var_468], eax
0x180036565  test    eax, eax
0x180036567  js      short loc_180036570
0x180036569  test    byte ptr [rsp+498h+SystemInformation+4], 2
0x18003656e  jnz     short loc_1800365A3
0x180036570  lea     rax, [rsp+498h+String1]
0x180036575  mov     [rsp+498h+var_478], rax
0x18003657a  lea     r9, aIgnoringRefere; "Ignoring reference to non-system DLLFIL"...
0x180036581  mov     r8d, 82Dh
0x180036587  lea     rdx, aSdbgetdllname; "SdbGetDllName"
0x18003658e  mov     ecx, 3
0x180036593  call    AslLogCallPrintf
0x180036598  test    ebx, ebx
0x18003659a  js      short loc_180036610
0x18003659c  mov     ebx, 0C000A000h
0x1800365a1  jmp     short loc_18003660C
0x1800365a3  cmp     [rsp+498h+pszDest], r14w
0x1800365ac  jz      short loc_1800365F0
0x1800365ae  lea     r8, [rsp+498h+String1]; pszSrc
0x1800365b3  mov     edx, 104h; cchDest
0x1800365b8  lea     rcx, [rsp+498h+pszDest]; pszDest
0x1800365c0  call    StringCchCatW
0x1800365c5  mov     ebx, eax
0x1800365c7  mov     [rsp+498h+var_468], eax
0x1800365cb  test    eax, eax
0x1800365cd  js      short loc_180036610
0x1800365cf  lea     r8, [rsp+498h+pszDest]; pszSrc
0x1800365d7  mov     edx, 104h; cchDest
0x1800365dc  lea     rcx, [rsp+498h+String1]; pszDest
0x1800365e1  call    StringCchCopyW
0x1800365e6  mov     ebx, eax
0x1800365e8  mov     [rsp+498h+var_468], eax
0x1800365ec  test    eax, eax
0x1800365ee  js      short loc_180036610
0x1800365f0  mov     rdx, rsi
0x1800365f3  lea     r8, [rsp+498h+String1]
0x1800365f8  mov     rcx, rdi
0x1800365fb  call    RtlStringCchCopyW
0x180036600  mov     ebx, eax
0x180036602  mov     [rsp+498h+var_468], eax
0x180036606  test    eax, eax
0x180036608  cmovns  ebx, r14d
0x18003660c  mov     [rsp+498h+var_468], ebx
0x180036610  jmp     short loc_18003661B
0x180036612  mov     ebx, 0C0000602h
0x180036617  mov     [rsp+498h+var_468], ebx
0x18003661b  mov     eax, ebx
0x18003661d  mov     rcx, [rsp+498h+var_38]
0x180036625  xor     rcx, rsp; StackCookie
0x180036628  call    __security_check_cookie
0x18003662d  add     rsp, 478h
0x180036634  pop     r14
0x180036636  pop     rdi
0x180036637  pop     rsi
0x180036638  pop     rbx
0x180036639  retn
0x1800595e0  push    rbp
0x1800595e2  sub     rsp, 30h
0x1800595e6  mov     rbp, rdx
0x1800595e9  call    ShimExceptionHandler
0x1800595ee  nop
0x1800595ef  add     rsp, 30h
0x1800595f3  pop     rbp
0x1800595f4  retn
```

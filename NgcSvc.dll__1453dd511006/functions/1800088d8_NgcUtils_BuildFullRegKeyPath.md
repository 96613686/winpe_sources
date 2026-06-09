# NgcUtils::BuildFullRegKeyPath

- ea: `0x1800088d8`
- end: `0x180008af5`
- name: `NgcUtils::BuildFullRegKeyPath`
- size: `541`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004526c`

## callees

- `0x180006fa0`
- `0x18000782c`
- `0x1800088d8`
- `0x18000e570`
- `0x18000e960`
- `0x180016350`
- `0x180048304`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008acb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008acb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000893b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000893b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008925`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008a07`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008925`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180008a07`

## string_xrefs

- `0x180008959`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180008988`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180008a18`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180008a62`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x1800089a8`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::BuildFullRegKeyPath(unsigned __int16 *a1, __int64 a2)
{
  _WORD *v4; // rbx
  int PersistedRegistryLocationW; // eax
  signed int v6; // edi
  NgcUtils *v7; // rax
  NgcUtils *v8; // rsi
  NgcUtils *i; // rcx
  unsigned int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  SIZE_T uBytes; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  char *v18[4]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v4 = 0;
  hMem = 0;
  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"NgcCredprov",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6"
                                  "886603-9D2F-4EB2-B667-1971041FA96B}",
                                 0,
                                 0);
  v6 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    v7 = (NgcUtils *)LocalAlloc(0, (unsigned int)uBytes);
    v8 = v7;
    if ( !v7 )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
        (const char *)0x8007000ELL,
        (int)&uBytes);
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
        (const char *)(unsigned int)v6,
        v14);
      return (unsigned int)v6;
    }
    for ( i = (NgcUtils *)((char *)v7 + (unsigned int)uBytes); v7 != i; v7 = (NgcUtils *)((char *)v7 + 1) )
      *(_BYTE *)v7 = 0;
    v11 = GetPersistedRegistryLocationW(
            L"NgcCredprov",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
            v8,
            (unsigned int)uBytes);
    if ( !v11 )
    {
      if ( a1 )
      {
        hMem = 0;
        v13 = NgcUtils::CombineSeparateStrings(
                v8,
                v12,
                a1,
                (const unsigned __int16 *)&hMem,
                (unsigned __int16 **)&uBytes);
        v6 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC9,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
            (const char *)(unsigned int)v13,
            v15);
          if ( hMem )
            LocalFree(hMem);
          LocalFree(v8);
          goto LABEL_9;
        }
        v4 = hMem;
        LocalFree(v8);
      }
      else
      {
        v4 = v8;
        hMem = v8;
      }
      goto LABEL_19;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC0,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
           (const char *)v11,
           (unsigned int)&uBytes);
    LocalFree(v8);
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_19;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)(unsigned int)v6,
      (int)&uBytes);
  }
  if ( v6 < 0 )
    goto LABEL_9;
LABEL_19:
  std::wstring::wstring(v18, v4);
  std::wstring::operator=(a2, v18);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v18);
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x1800088d8  mov     [rsp-28h+arg_10], rbx
0x1800088dd  push    rbp
0x1800088de  push    rsi
0x1800088df  push    rdi
0x1800088e0  push    r14
0x1800088e2  push    r15
0x1800088e4  mov     rbp, rsp
0x1800088e7  sub     rsp, 70h
0x1800088eb  mov     rax, cs:__security_cookie
0x1800088f2  xor     rax, rsp
0x1800088f5  mov     [rbp+var_10], rax
0x1800088f9  mov     r15, rdx
0x1800088fc  mov     r14, rcx
0x1800088ff  xor     ebx, ebx
0x180008901  mov     [rbp+hMem], rbx
0x180008905  mov     dword ptr [rbp+uBytes], ebx
0x180008908  lea     rax, [rbp+uBytes]
0x18000890c  mov     qword ptr [rsp+70h+var_50], rax; int
0x180008911  xor     r9d, r9d
0x180008914  xor     r8d, r8d
0x180008917  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000891e  lea     rcx, aNgccredprov; "NgcCredprov"
0x180008925  call    cs:__imp_GetPersistedRegistryLocationW
0x18000892b  mov     edi, eax
0x18000892d  cmp     eax, 0EAh
0x180008932  jnz     short loc_18000896C
0x180008934  mov     edi, dword ptr [rbp+uBytes]
0x180008937  mov     edx, edi; uBytes
0x180008939  xor     ecx, ecx; uFlags
0x18000893b  call    cs:__imp_LocalAlloc
0x180008941  mov     rsi, rax
0x180008944  test    rax, rax
0x180008947  jnz     loc_1800089DC
0x18000894d  mov     rcx, [rbp+28h]; this
0x180008951  mov     edi, 8007000Eh
0x180008956  mov     r9d, edi; char *
0x180008959  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180008960  mov     edx, 0B9h; void *
0x180008965  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000896a  jmp     short loc_1800089A1
0x18000896c  test    eax, eax
0x18000896e  jle     short loc_180008979
0x180008970  movzx   edi, ax
0x180008973  or      edi, 80070000h
0x180008979  test    edi, edi
0x18000897b  jns     loc_180008AA1
0x180008981  mov     rcx, [rbp+28h]; this
0x180008985  mov     r9d, edi; char *
0x180008988  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000898f  mov     edx, 0B6h; void *
0x180008994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008999  test    edi, edi
0x18000899b  jns     loc_180008AA1
0x1800089a1  mov     rcx, [rbp+28h]; this
0x1800089a5  mov     r9d, edi; char *
0x1800089a8  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800089af  mov     edx, 1Fh; void *
0x1800089b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089b9  nop
0x1800089ba  mov     eax, edi
0x1800089bc  mov     rcx, [rbp+var_10]
0x1800089c0  xor     rcx, rsp; StackCookie
0x1800089c3  call    __security_check_cookie
0x1800089c8  mov     rbx, [rsp+70h+arg_10]
0x1800089d0  add     rsp, 70h
0x1800089d4  pop     r15
0x1800089d6  pop     r14
0x1800089d8  pop     rdi
0x1800089d9  pop     rsi
0x1800089da  pop     rbp
0x1800089db  retn
0x1800089dc  lea     rcx, [rdi+rax]
0x1800089e0  cmp     rsi, rcx
0x1800089e3  jnz     loc_180008AE1
0x1800089e9  lea     rax, [rbp+uBytes]
0x1800089ed  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800089f2  mov     r9d, dword ptr [rbp+uBytes]
0x1800089f6  mov     r8, rsi
0x1800089f9  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008a00  lea     rcx, aNgccredprov; "NgcCredprov"
0x180008a07  call    cs:__imp_GetPersistedRegistryLocationW
0x180008a0d  test    eax, eax
0x180008a0f  jz      short loc_180008A39
0x180008a11  mov     rcx, [rbp+28h]; this
0x180008a15  mov     r9d, eax; char *
0x180008a18  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180008a1f  mov     edx, 0C0h; void *
0x180008a24  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008a29  mov     edi, eax
0x180008a2b  mov     rcx, rsi; hMem
0x180008a2e  call    cs:__imp_LocalFree
0x180008a34  jmp     loc_180008999
0x180008a39  test    r14, r14
0x180008a3c  jz      loc_180008AD8
0x180008a42  mov     [rbp+hMem], rbx
0x180008a46  lea     r9, [rbp+hMem]; unsigned __int16 *
0x180008a4a  mov     r8, r14; unsigned __int16 *
0x180008a4d  mov     rcx, rsi; this
0x180008a50  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180008a55  mov     edi, eax
0x180008a57  test    eax, eax
0x180008a59  jns     short loc_180008A90
0x180008a5b  mov     rcx, [rbp+28h]; this
0x180008a5f  mov     r9d, eax; char *
0x180008a62  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180008a69  mov     edx, 0C9h; void *
0x180008a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a73  mov     rcx, [rbp+hMem]; hMem
0x180008a77  test    rcx, rcx
0x180008a7a  jz      short loc_180008A82
0x180008a7c  call    cs:__imp_LocalFree
0x180008a82  mov     rcx, rsi; hMem
0x180008a85  call    cs:__imp_LocalFree
0x180008a8b  jmp     loc_1800089A1
0x180008a90  mov     rbx, [rbp+hMem]
0x180008a94  mov     [rbp+hMem], rbx
0x180008a98  mov     rcx, rsi; hMem
0x180008a9b  call    cs:__imp_LocalFree
0x180008aa1  mov     rdx, rbx
0x180008aa4  lea     rcx, [rbp+var_30]
0x180008aa8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180008aad  lea     rdx, [rbp+var_30]
0x180008ab1  mov     rcx, r15
0x180008ab4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008ab9  lea     rcx, [rbp+var_30]
0x180008abd  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180008ac2  nop
0x180008ac3  test    rbx, rbx
0x180008ac6  jz      short loc_180008AD1
0x180008ac8  mov     rcx, rbx; hMem
0x180008acb  call    cs:__imp_LocalFree
0x180008ad1  xor     eax, eax
0x180008ad3  jmp     loc_1800089BC
0x180008ad8  mov     rbx, rsi
0x180008adb  mov     [rbp+hMem], rbx
0x180008adf  jmp     short loc_180008AA1
0x180008ae1  xor     r8d, r8d
0x180008ae4  mov     [rax], r8b
0x180008ae7  inc     rax
0x180008aea  cmp     rax, rcx
0x180008aed  jnz     short loc_180008AE1
0x180008aef  jmp     loc_1800089E9
```

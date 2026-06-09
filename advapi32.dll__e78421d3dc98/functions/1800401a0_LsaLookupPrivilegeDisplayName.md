# LsaLookupPrivilegeDisplayName

- ea: `0x1800401a0`
- end: `0x180040429`
- name: `LsaLookupPrivilegeDisplayName`
- size: `649`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PLSA_UNICODE_STRING Name, PLSA_UNICODE_STRING *DisplayName, PSHORT LanguageReturned)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18004fde0`

## callees

- `0x1800401a0`
- `0x180065090`

## import_xrefs

- `msvcrt!swscanf_s` at `0x1800402de`
- `msvcrt!swscanf_s` at `0x1800402de`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180040239`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180040297`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180040239`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180040297`
- `KERNELBASE!LocalAlloc` at `0x180040263`
- `KERNELBASE!LocalAlloc` at `0x180040263`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x18004035b`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x18004035b`
- `KERNELBASE!GetUserDefaultUILanguage` at `0x18004034d`
- `KERNELBASE!GetUserDefaultUILanguage` at `0x18004034d`
- `KERNEL32!LocalFree` at `0x1800403d0`
- `KERNEL32!LocalFree` at `0x1800403fe`
- `KERNEL32!LocalFree` at `0x1800403d0`
- `KERNEL32!LocalFree` at `0x1800403fe`
- `KERNEL32!GetThreadUILanguage` at `0x180040325`
- `KERNEL32!GetThreadUILanguage` at `0x18004033f`
- `KERNEL32!GetThreadUILanguage` at `0x180040325`
- `KERNEL32!GetThreadUILanguage` at `0x18004033f`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800403d8`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800403d8`
- `RPCRT4!NdrClientCall3` at `0x1800403a5`
- `RPCRT4!NdrClientCall3` at `0x1800403a5`

## pseudocode

```c
NTSTATUS __stdcall LsaLookupPrivilegeDisplayName(
        LSA_HANDLE PolicyHandle,
        PLSA_UNICODE_STRING Name,
        PLSA_UNICODE_STRING *DisplayName,
        PSHORT LanguageReturned)
{
  PLSA_UNICODE_STRING v4; // r15
  wchar_t *v7; // r14
  char v8; // r12
  NTSTATUS ThreadPreferredUILanguages; // eax
  NTSTATUS Pointer; // ebx
  wchar_t *v11; // rax
  signed __int16 ThreadUILanguage; // si
  signed __int16 UserDefaultUILanguage; // bx
  const wchar_t *i; // r15
  __int64 v15; // rax
  CLIENT_CALL_RETURN v16; // rax
  __int16 v17; // [rsp+54h] [rbp-154h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-150h] BYREF
  int v19; // [rsp+5Ch] [rbp-14Ch] BYREF
  PLSA_UNICODE_STRING Simple; // [rsp+60h] [rbp-148h]
  int v21; // [rsp+68h] [rbp-140h]
  HLOCAL hMem; // [rsp+70h] [rbp-138h] BYREF
  wchar_t *v23; // [rsp+78h] [rbp-130h]
  PSHORT v24; // [rsp+80h] [rbp-128h]
  PLSA_UNICODE_STRING *v25; // [rsp+88h] [rbp-120h]
  wchar_t Buffer[104]; // [rsp+90h] [rbp-118h] BYREF

  v24 = LanguageReturned;
  v25 = DisplayName;
  v4 = Name;
  Simple = Name;
  v17 = -1;
  hMem = 0;
  v19 = 0;
  v18 = 100;
  if ( !PolicyHandle )
    return -1073741816;
  v7 = Buffer;
  v23 = Buffer;
  v8 = 0;
  ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(4, &v19, Buffer, &v18);
  Pointer = ThreadPreferredUILanguages;
  if ( !ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789 )
  {
    if ( v18 > 0x64 )
    {
      v11 = (wchar_t *)LocalAlloc(0x40u, 2LL * v18);
      v7 = v11;
      v23 = v11;
      if ( !v11 )
      {
        Pointer = -1073741801;
        goto LABEL_31;
      }
      v8 = 1;
      Pointer = RtlGetThreadPreferredUILanguages(4, &v19, v11, &v18);
      if ( Pointer )
        goto LABEL_31;
    }
    ThreadUILanguage = -1;
    UserDefaultUILanguage = -1;
    if ( v19 )
    {
      for ( i = v7; ; i += v15 + 1 )
      {
        if ( (unsigned int)(i - v7) >= v18 || !*i )
          goto LABEL_21;
        if ( swscanf_s(i, L"%hx", &v17) == -1 )
          break;
        if ( ThreadUILanguage == -1 )
        {
          ThreadUILanguage = v17;
        }
        else if ( ThreadUILanguage != v17 )
        {
          UserDefaultUILanguage = v17;
LABEL_21:
          v4 = Simple;
          goto LABEL_22;
        }
        v15 = -1;
        do
          ++v15;
        while ( i[v15] );
      }
      Pointer = -1073741811;
      goto LABEL_31;
    }
LABEL_22:
    if ( ThreadUILanguage == -1 )
    {
      ThreadUILanguage = GetThreadUILanguage();
    }
    else
    {
      if ( UserDefaultUILanguage != -1 )
        goto LABEL_28;
      UserDefaultUILanguage = GetThreadUILanguage();
      if ( ThreadUILanguage != UserDefaultUILanguage )
        goto LABEL_28;
    }
    UserDefaultUILanguage = GetUserDefaultUILanguage();
LABEL_28:
    if ( ThreadUILanguage == UserDefaultUILanguage )
      UserDefaultUILanguage = GetSystemDefaultUILanguage();
    Simple = 0;
    v16.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_180067210,
                    0x21u,
                    0,
                    *((_QWORD *)PolicyHandle + 1),
                    v4,
                    ThreadUILanguage,
                    UserDefaultUILanguage,
                    &hMem,
                    v24).Pointer;
    Pointer = (NTSTATUS)v16.Pointer;
    Simple = (PLSA_UNICODE_STRING)v16.Simple;
    v21 = (int)v16.Pointer;
    *v25 = (PLSA_UNICODE_STRING)hMem;
  }
LABEL_31:
  if ( v8 )
    LocalFree(v7);
  return Pointer;
}

```

## disassembly

```asm
0x1800401a0  push    rbx
0x1800401a2  push    rsi
0x1800401a3  push    rdi
0x1800401a4  push    r12
0x1800401a6  push    r13
0x1800401a8  push    r14
0x1800401aa  push    r15
0x1800401ac  sub     rsp, 170h
0x1800401b3  mov     rax, cs:__security_cookie
0x1800401ba  xor     rax, rsp
0x1800401bd  mov     [rsp+1A8h+var_48], rax
0x1800401c5  mov     [rsp+1A8h+var_128], r9
0x1800401cd  mov     [rsp+1A8h+var_120], r8
0x1800401d5  mov     r15, rdx
0x1800401d8  mov     [rsp+1A8h+var_148], rdx
0x1800401dd  mov     r13, rcx
0x1800401e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800401e4  mov     [rsp+1A8h+var_154], ax
0x1800401e9  xor     edi, edi
0x1800401eb  mov     [rsp+1A8h+hMem], rdi
0x1800401f0  mov     [rsp+1A8h+var_14C], edi
0x1800401f4  mov     [rsp+1A8h+var_150], 64h ; 'd'
0x1800401fc  test    rcx, rcx
0x1800401ff  jnz     short loc_18004020B
0x180040201  mov     eax, 0C0000008h
0x180040206  jmp     loc_180040406
0x18004020b  lea     r14, [rsp+1A8h+Buffer]
0x180040213  mov     [rsp+1A8h+var_130], r14
0x180040218  mov     r12b, dil
0x18004021b  mov     [rsp+1A8h+var_158], dil
0x180040220  lea     r9, [rsp+1A8h+var_150]
0x180040225  lea     r8, [rsp+1A8h+Buffer]
0x18004022d  lea     rdx, [rsp+1A8h+var_14C]
0x180040232  mov     esi, 4
0x180040237  mov     ecx, esi
0x180040239  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18004023f  mov     ebx, eax
0x180040241  test    eax, eax
0x180040243  jz      short loc_180040250
0x180040245  cmp     eax, 0C0000023h
0x18004024a  jnz     loc_1800403F6
0x180040250  cmp     [rsp+1A8h+var_150], 64h ; 'd'
0x180040255  jbe     short loc_1800402A7
0x180040257  mov     edx, [rsp+1A8h+var_150]
0x18004025b  add     rdx, rdx; uBytes
0x18004025e  mov     ecx, 40h ; '@'; uFlags
0x180040263  call    cs:__imp_LocalAlloc
0x180040269  mov     r14, rax
0x18004026c  mov     [rsp+1A8h+var_130], rax
0x180040271  test    rax, rax
0x180040274  jnz     short loc_180040280
0x180040276  mov     ebx, 0C0000017h
0x18004027b  jmp     loc_1800403F6
0x180040280  mov     r12b, 1
0x180040283  mov     [rsp+1A8h+var_158], r12b
0x180040288  lea     r9, [rsp+1A8h+var_150]
0x18004028d  mov     r8, rax
0x180040290  lea     rdx, [rsp+1A8h+var_14C]
0x180040295  mov     ecx, esi
0x180040297  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18004029d  mov     ebx, eax
0x18004029f  test    eax, eax
0x1800402a1  jnz     loc_1800403F6
0x1800402a7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800402ab  movzx   esi, cx
0x1800402ae  movzx   ebx, cx
0x1800402b1  cmp     [rsp+1A8h+var_14C], edi
0x1800402b5  jz      short loc_180040320
0x1800402b7  mov     r15, r14
0x1800402ba  mov     rax, r15
0x1800402bd  sub     rax, r14
0x1800402c0  sar     rax, 1
0x1800402c3  cmp     eax, [rsp+1A8h+var_150]
0x1800402c7  jnb     short loc_18004031B
0x1800402c9  cmp     [r15], di
0x1800402cd  jz      short loc_18004031B
0x1800402cf  lea     r8, [rsp+1A8h+var_154]
0x1800402d4  lea     rdx, aHx; "%hx"
0x1800402db  mov     rcx, r15; Buffer
0x1800402de  call    cs:__imp_swscanf_s
0x1800402e4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800402e8  cmp     eax, ecx
0x1800402ea  jz      short loc_180040330
0x1800402ec  cmp     si, cx
0x1800402ef  jnz     short loc_1800402F8
0x1800402f1  movzx   esi, [rsp+1A8h+var_154]
0x1800402f6  jmp     short loc_1800402FF
0x1800402f8  cmp     si, [rsp+1A8h+var_154]
0x1800402fd  jnz     short loc_180040316
0x1800402ff  mov     rax, rcx
0x180040302  inc     rax
0x180040305  cmp     [r15+rax*2], di
0x18004030a  jnz     short loc_180040302
0x18004030c  lea     r15, [r15+rax*2]
0x180040310  add     r15, 2
0x180040314  jmp     short loc_1800402BA
0x180040316  movzx   ebx, [rsp+1A8h+var_154]
0x18004031b  mov     r15, [rsp+1A8h+var_148]
0x180040320  cmp     si, cx
0x180040323  jnz     short loc_18004033A
0x180040325  call    cs:__imp_GetThreadUILanguage
0x18004032b  movzx   esi, ax
0x18004032e  jmp     short loc_18004034D
0x180040330  mov     ebx, 0C000000Dh
0x180040335  jmp     loc_1800403F6
0x18004033a  cmp     bx, cx
0x18004033d  jnz     short loc_180040356
0x18004033f  call    cs:__imp_GetThreadUILanguage
0x180040345  movzx   ebx, ax
0x180040348  cmp     si, ax
0x18004034b  jnz     short loc_180040356
0x18004034d  call    cs:__imp_GetUserDefaultUILanguage
0x180040353  movzx   ebx, ax
0x180040356  cmp     si, bx
0x180040359  jnz     short loc_180040364
0x18004035b  call    cs:__imp_GetSystemDefaultUILanguage
0x180040361  movzx   ebx, ax
0x180040364  mov     [rsp+1A8h+var_148], rdi
0x180040369  movsx   eax, bx
0x18004036c  movsx   ecx, si
0x18004036f  mov     rdx, [rsp+1A8h+var_128]
0x180040377  mov     [rsp+1A8h+var_168], rdx
0x18004037c  lea     rdx, [rsp+1A8h+hMem]
0x180040381  mov     [rsp+1A8h+var_170], rdx
0x180040386  mov     [rsp+1A8h+var_178], eax
0x18004038a  mov     [rsp+1A8h+var_180], ecx
0x18004038e  mov     [rsp+1A8h+var_188], r15
0x180040393  mov     r9, [r13+8]
0x180040397  xor     r8d, r8d; pReturnValue
0x18004039a  lea     edx, [r8+21h]; nProcNum
0x18004039e  lea     rcx, stru_180067210; pProxyInfo
0x1800403a5  call    cs:__imp_NdrClientCall3
0x1800403ab  mov     rbx, rax
0x1800403ae  mov     [rsp+1A8h+var_148], rax
0x1800403b3  mov     [rsp+1A8h+var_140], eax
0x1800403b7  mov     rax, [rsp+1A8h+hMem]
0x1800403bc  mov     rcx, [rsp+1A8h+var_120]
0x1800403c4  mov     [rcx], rax
0x1800403c7  jmp     short loc_1800403F6
0x1800403c9  mov     ebx, eax
0x1800403cb  mov     rcx, [rsp+1A8h+hMem]; hMem
0x1800403d0  call    cs:__imp_LocalFree
0x1800403d6  mov     ecx, ebx; Status
0x1800403d8  call    cs:__imp_I_RpcMapWin32Status
0x1800403de  mov     ebx, 0C0000001h
0x1800403e3  test    eax, eax
0x1800403e5  cmovs   ebx, eax
0x1800403e8  mov     [rsp+1A8h+var_140], ebx
0x1800403ec  mov     r14, [rsp+1A8h+var_130]
0x1800403f1  mov     r12b, [rsp+1A8h+var_158]
0x1800403f6  test    r12b, r12b
0x1800403f9  jz      short loc_180040404
0x1800403fb  mov     rcx, r14; hMem
0x1800403fe  call    cs:__imp_LocalFree
0x180040404  mov     eax, ebx
0x180040406  mov     rcx, [rsp+1A8h+var_48]
0x18004040e  xor     rcx, rsp; StackCookie
0x180040411  call    __security_check_cookie
0x180040416  add     rsp, 170h
0x18004041d  pop     r15
0x18004041f  pop     r14
0x180040421  pop     r13
0x180040423  pop     r12
0x180040425  pop     rdi
0x180040426  pop     rsi
0x180040427  pop     rbx
0x180040428  retn
0x180065b20  push    rbp
0x180065b22  sub     rsp, 50h
0x180065b26  mov     rbp, rdx
0x180065b29  mov     rcx, [rcx]
0x180065b2c  mov     ecx, [rcx]; ExceptionCode
0x180065b2e  call    cs:__imp_I_RpcExceptionFilter
0x180065b34  nop
0x180065b35  add     rsp, 50h
0x180065b39  pop     rbp
0x180065b3a  retn
```

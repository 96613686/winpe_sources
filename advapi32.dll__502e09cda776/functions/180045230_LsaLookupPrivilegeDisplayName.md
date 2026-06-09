# LsaLookupPrivilegeDisplayName

- ea: `0x180045230`
- end: `0x180045502`
- name: `LsaLookupPrivilegeDisplayName`
- size: `722`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PLSA_UNICODE_STRING Name, PLSA_UNICODE_STRING *DisplayName, PSHORT LanguageReturned)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180056490`

## callees

- `0x180045230`
- `0x1800720b0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x180045380`
- `msvcrt!swscanf_s` at `0x180045380`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800452c9`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180045333`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800452c9`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180045333`
- `KERNELBASE!LocalAlloc` at `0x1800452f9`
- `KERNELBASE!LocalAlloc` at `0x1800452f9`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x180045415`
- `KERNELBASE!GetSystemDefaultUILanguage` at `0x180045415`
- `KERNELBASE!GetUserDefaultUILanguage` at `0x180045401`
- `KERNELBASE!GetUserDefaultUILanguage` at `0x180045401`
- `KERNEL32!LocalFree` at `0x180045496`
- `KERNEL32!LocalFree` at `0x1800454d0`
- `KERNEL32!LocalFree` at `0x180045496`
- `KERNEL32!LocalFree` at `0x1800454d0`
- `KERNEL32!GetThreadUILanguage` at `0x1800453cd`
- `KERNEL32!GetThreadUILanguage` at `0x1800453ed`
- `KERNEL32!GetThreadUILanguage` at `0x1800453cd`
- `KERNEL32!GetThreadUILanguage` at `0x1800453ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800454a4`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800454a4`
- `RPCRT4!NdrClientCall3` at `0x180045465`
- `RPCRT4!NdrClientCall3` at `0x180045465`

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
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_1800751F0,
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
0x180045230  push    rbx
0x180045232  push    rsi
0x180045233  push    rdi
0x180045234  push    r12
0x180045236  push    r13
0x180045238  push    r14
0x18004523a  push    r15
0x18004523c  sub     rsp, 170h
0x180045243  mov     rax, cs:__security_cookie
0x18004524a  xor     rax, rsp
0x18004524d  mov     [rsp+1A8h+var_48], rax
0x180045255  mov     [rsp+1A8h+var_128], r9
0x18004525d  mov     [rsp+1A8h+var_120], r8
0x180045265  mov     r15, rdx
0x180045268  mov     [rsp+1A8h+var_148], rdx
0x18004526d  mov     r13, rcx
0x180045270  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045274  mov     [rsp+1A8h+var_154], ax
0x180045279  xor     edi, edi
0x18004527b  mov     [rsp+1A8h+hMem], rdi
0x180045280  mov     [rsp+1A8h+var_14C], edi
0x180045284  mov     [rsp+1A8h+var_150], 64h ; 'd'
0x18004528c  test    rcx, rcx
0x18004528f  jnz     short loc_18004529B
0x180045291  mov     eax, 0C0000008h
0x180045296  jmp     loc_1800454DE
0x18004529b  lea     r14, [rsp+1A8h+Buffer]
0x1800452a3  mov     [rsp+1A8h+var_130], r14
0x1800452a8  mov     r12b, dil
0x1800452ab  mov     [rsp+1A8h+var_158], dil
0x1800452b0  lea     r9, [rsp+1A8h+var_150]
0x1800452b5  lea     r8, [rsp+1A8h+Buffer]
0x1800452bd  lea     rdx, [rsp+1A8h+var_14C]
0x1800452c2  mov     esi, 4
0x1800452c7  mov     ecx, esi
0x1800452c9  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800452d0  nop     dword ptr [rax+rax+00h]
0x1800452d5  mov     ebx, eax
0x1800452d7  test    eax, eax
0x1800452d9  jz      short loc_1800452E6
0x1800452db  cmp     eax, 0C0000023h
0x1800452e0  jnz     loc_1800454C8
0x1800452e6  cmp     [rsp+1A8h+var_150], 64h ; 'd'
0x1800452eb  jbe     short loc_180045349
0x1800452ed  mov     edx, [rsp+1A8h+var_150]
0x1800452f1  add     rdx, rdx; uBytes
0x1800452f4  mov     ecx, 40h ; '@'; uFlags
0x1800452f9  call    cs:__imp_LocalAlloc
0x180045300  nop     dword ptr [rax+rax+00h]
0x180045305  mov     r14, rax
0x180045308  mov     [rsp+1A8h+var_130], rax
0x18004530d  test    rax, rax
0x180045310  jnz     short loc_18004531C
0x180045312  mov     ebx, 0C0000017h
0x180045317  jmp     loc_1800454C8
0x18004531c  mov     r12b, 1
0x18004531f  mov     [rsp+1A8h+var_158], r12b
0x180045324  lea     r9, [rsp+1A8h+var_150]
0x180045329  mov     r8, rax
0x18004532c  lea     rdx, [rsp+1A8h+var_14C]
0x180045331  mov     ecx, esi
0x180045333  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18004533a  nop     dword ptr [rax+rax+00h]
0x18004533f  mov     ebx, eax
0x180045341  test    eax, eax
0x180045343  jnz     loc_1800454C8
0x180045349  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004534d  movzx   esi, cx
0x180045350  movzx   ebx, cx
0x180045353  cmp     [rsp+1A8h+var_14C], edi
0x180045357  jz      short loc_1800453C8
0x180045359  mov     r15, r14
0x18004535c  mov     rax, r15
0x18004535f  sub     rax, r14
0x180045362  sar     rax, 1
0x180045365  cmp     eax, [rsp+1A8h+var_150]
0x180045369  jnb     short loc_1800453C3
0x18004536b  cmp     [r15], di
0x18004536f  jz      short loc_1800453C3
0x180045371  lea     r8, [rsp+1A8h+var_154]
0x180045376  lea     rdx, aHx; "%hx"
0x18004537d  mov     rcx, r15; Buffer
0x180045380  call    cs:__imp_swscanf_s
0x180045387  nop     dword ptr [rax+rax+00h]
0x18004538c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180045390  cmp     eax, ecx
0x180045392  jz      short loc_1800453DE
0x180045394  cmp     si, cx
0x180045397  jnz     short loc_1800453A0
0x180045399  movzx   esi, [rsp+1A8h+var_154]
0x18004539e  jmp     short loc_1800453A7
0x1800453a0  cmp     si, [rsp+1A8h+var_154]
0x1800453a5  jnz     short loc_1800453BE
0x1800453a7  mov     rax, rcx
0x1800453aa  inc     rax
0x1800453ad  cmp     [r15+rax*2], di
0x1800453b2  jnz     short loc_1800453AA
0x1800453b4  lea     r15, [r15+rax*2]
0x1800453b8  add     r15, 2
0x1800453bc  jmp     short loc_18004535C
0x1800453be  movzx   ebx, [rsp+1A8h+var_154]
0x1800453c3  mov     r15, [rsp+1A8h+var_148]
0x1800453c8  cmp     si, cx
0x1800453cb  jnz     short loc_1800453E8
0x1800453cd  call    cs:__imp_GetThreadUILanguage
0x1800453d4  nop     dword ptr [rax+rax+00h]
0x1800453d9  movzx   esi, ax
0x1800453dc  jmp     short loc_180045401
0x1800453de  mov     ebx, 0C000000Dh
0x1800453e3  jmp     loc_1800454C8
0x1800453e8  cmp     bx, cx
0x1800453eb  jnz     short loc_180045410
0x1800453ed  call    cs:__imp_GetThreadUILanguage
0x1800453f4  nop     dword ptr [rax+rax+00h]
0x1800453f9  movzx   ebx, ax
0x1800453fc  cmp     si, ax
0x1800453ff  jnz     short loc_180045410
0x180045401  call    cs:__imp_GetUserDefaultUILanguage
0x180045408  nop     dword ptr [rax+rax+00h]
0x18004540d  movzx   ebx, ax
0x180045410  cmp     si, bx
0x180045413  jnz     short loc_180045424
0x180045415  call    cs:__imp_GetSystemDefaultUILanguage
0x18004541c  nop     dword ptr [rax+rax+00h]
0x180045421  movzx   ebx, ax
0x180045424  mov     [rsp+1A8h+var_148], rdi
0x180045429  movsx   eax, bx
0x18004542c  movsx   ecx, si
0x18004542f  mov     rdx, [rsp+1A8h+var_128]
0x180045437  mov     [rsp+1A8h+var_168], rdx
0x18004543c  lea     rdx, [rsp+1A8h+hMem]
0x180045441  mov     [rsp+1A8h+var_170], rdx
0x180045446  mov     [rsp+1A8h+var_178], eax
0x18004544a  mov     [rsp+1A8h+var_180], ecx
0x18004544e  mov     [rsp+1A8h+var_188], r15
0x180045453  mov     r9, [r13+8]
0x180045457  xor     r8d, r8d; pReturnValue
0x18004545a  lea     edx, [r8+21h]; nProcNum
0x18004545e  lea     rcx, stru_1800751F0; pProxyInfo
0x180045465  call    cs:__imp_NdrClientCall3
0x18004546c  nop     dword ptr [rax+rax+00h]
0x180045471  mov     rbx, rax
0x180045474  mov     [rsp+1A8h+var_148], rax
0x180045479  mov     [rsp+1A8h+var_140], eax
0x18004547d  mov     rax, [rsp+1A8h+hMem]
0x180045482  mov     rcx, [rsp+1A8h+var_120]
0x18004548a  mov     [rcx], rax
0x18004548d  jmp     short loc_1800454C8
0x18004548f  mov     ebx, eax
0x180045491  mov     rcx, [rsp+1A8h+hMem]; hMem
0x180045496  call    cs:__imp_LocalFree
0x18004549d  nop     dword ptr [rax+rax+00h]
0x1800454a2  mov     ecx, ebx; Status
0x1800454a4  call    cs:__imp_I_RpcMapWin32Status
0x1800454ab  nop     dword ptr [rax+rax+00h]
0x1800454b0  mov     ebx, 0C0000001h
0x1800454b5  test    eax, eax
0x1800454b7  cmovs   ebx, eax
0x1800454ba  mov     [rsp+1A8h+var_140], ebx
0x1800454be  mov     r14, [rsp+1A8h+var_130]
0x1800454c3  mov     r12b, [rsp+1A8h+var_158]
0x1800454c8  test    r12b, r12b
0x1800454cb  jz      short loc_1800454DC
0x1800454cd  mov     rcx, r14; hMem
0x1800454d0  call    cs:__imp_LocalFree
0x1800454d7  nop     dword ptr [rax+rax+00h]
0x1800454dc  mov     eax, ebx
0x1800454de  mov     rcx, [rsp+1A8h+var_48]
0x1800454e6  xor     rcx, rsp; StackCookie
0x1800454e9  call    __security_check_cookie
0x1800454ee  add     rsp, 170h
0x1800454f5  pop     r15
0x1800454f7  pop     r14
0x1800454f9  pop     r13
0x1800454fb  pop     r12
0x1800454fd  pop     rdi
0x1800454fe  pop     rsi
0x1800454ff  pop     rbx
0x180045500  retn
0x180072c99  push    rbp
0x180072c9b  sub     rsp, 50h
0x180072c9f  mov     rbp, rdx
0x180072ca2  mov     rcx, [rcx]
0x180072ca5  mov     ecx, [rcx]; ExceptionCode
0x180072ca7  call    cs:__imp_I_RpcExceptionFilter
0x180072cae  nop     dword ptr [rax+rax+00h]
0x180072cb3  nop
0x180072cb4  add     rsp, 50h
0x180072cb8  pop     rbp
0x180072cb9  retn
```

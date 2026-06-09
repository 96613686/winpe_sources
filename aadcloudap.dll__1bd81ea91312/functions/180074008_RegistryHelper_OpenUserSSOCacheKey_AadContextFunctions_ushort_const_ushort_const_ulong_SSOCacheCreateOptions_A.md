# RegistryHelper::OpenUserSSOCacheKey(AadContextFunctions *,ushort const *,ushort const *,ulong,SSOCacheCreateOptions,Auto<HKEY__ *,RegistryFunctor,DummyContext> &)

- ea: `0x180074008`
- end: `0x1800745d3`
- name: `?OpenUserSSOCacheKey@RegistryHelper@@CAJPEAVAadContextFunctions@@PEBG1KW4SSOCacheCreateOptions@@AEAV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@@Z`
- size: `1483`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800739c8`
- `0x180074794`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180019868`
- `0x1800256d0`
- `0x180071e14`
- `0x180071f1c`
- `0x180072334`
- `0x180074008`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074288`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074304`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074366`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074288`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074304`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074366`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007415c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800744cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007415c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800744cc`

## string_xrefs

- `0x18007406d`: `RegistryHelper::OpenUserSSOCacheKey`
- `0x1800741ab`: `SSOCache`
- `0x180074427`: `SSOCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegistryHelper::OpenUserSSOCacheKey(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        REGSAM a4,
        char a5,
        HKEY *a6)
{
  HKEY *v10; // r12
  unsigned __int16 *v11; // rdi
  signed int v12; // ecx
  LSTATUS v13; // eax
  int v14; // esi
  LSTATUS Key; // eax
  DWORD v16; // esi
  LSTATUS v17; // eax
  int v18; // edi
  LSTATUS v19; // eax
  __int64 v20; // r8
  int v21; // ecx
  HKEY v22; // rbx
  unsigned int v23; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HKEY v32[3]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v33[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v34; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  HKEY hKey[3]; // [rsp+B8h] [rbp-48h] BYREF
  const char *v38[14]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v39; // [rsp+150h] [rbp+50h] BYREF

  v39 = 0;
  v34 = 0;
  v36 = a1;
  v35 = 0;
  dwDisposition = 0;
  memset(hKey, 0, sizeof(hKey));
  v29 = 0;
  v31 = 0;
  v30 = 0;
  memset(v33, 0, sizeof(v33));
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v38,
    (int)"registry.cpp",
    (int)"RegistryHelper::OpenUserSSOCacheKey",
    (int)&v39);
  if ( !a1 || !a3 || !*a3 || !a2 || !*a2 )
  {
    v12 = -1073741811;
    LODWORD(lpSecurityAttributes) = 1136;
    goto LABEL_48;
  }
  v10 = a6;
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(a6);
  v11 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 64, 520);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v34);
  v34 = v11;
  v35 = 520;
  if ( !v11 )
  {
    v12 = -1073741801;
    LODWORD(lpSecurityAttributes) = 1144;
LABEL_48:
    v39 = v12;
    goto LABEL_49;
  }
  if ( (a4 & 6) != 6 )
  {
    v14 = StringCchPrintfW(
            v11,
            0x104u,
            L"%s\\%s\\%s\\%s",
            a2,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AAD",
            L"SSOCache",
            a3);
    if ( v14 < 0 )
    {
      LODWORD(lpSecurityAttributes) = 1190;
      goto LABEL_16;
    }
    if ( !*v11 )
    {
      v12 = -1073741595;
      LODWORD(lpSecurityAttributes) = 1193;
      goto LABEL_48;
    }
    v18 = RegOpenKeyExW(HKEY_USERS, v11, 0, a4, &v29);
    goto LABEL_41;
  }
  v13 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x20006u, hKey);
  v12 = v13;
  if ( v13 )
  {
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0xC0070000;
    v39 = v12;
    if ( v12 < 0 )
    {
      LODWORD(lpSecurityAttributes) = 1156;
LABEL_49:
      LODWORD(phkResult) = v12;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        phkResult,
        "registry.cpp",
        lpSecurityAttributes,
        "NTSTATUS",
        &base);
      goto LABEL_50;
    }
  }
  v14 = StringCchPrintfW(v11, 0x104u, L"%s\\%s", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AAD", L"SSOCache");
  if ( v14 >= 0 )
  {
    if ( !*v11 )
    {
      v12 = -1073741595;
      LODWORD(lpSecurityAttributes) = 1162;
      goto LABEL_48;
    }
    Key = RegCreateKeyExW(hKey[0], v11, 0, 0, 0, 0x20006u, 0, v33, 0);
    v12 = Key;
    if ( Key )
    {
      if ( Key > 0 )
        v12 = (unsigned __int16)Key | 0xC0070000;
      v39 = v12;
      if ( v12 < 0 )
      {
        LODWORD(lpSecurityAttributes) = 1169;
        goto LABEL_49;
      }
    }
    v16 = a5 & 1;
    v17 = RegCreateKeyExW(v33[0], a3, 0, 0, v16, a4, 0, &v29, &dwDisposition);
    v18 = v17;
    if ( (a5 & 2) != 0 )
    {
      if ( v17 )
      {
LABEL_42:
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0xC0070000;
        v39 = v18;
        if ( v18 < 0 )
        {
          LODWORD(lpSecurityAttributes) = 1201;
          LODWORD(phkResulta) = v18;
          WPPTraceLogA(
            2,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            2,
            phkResulta,
            "registry.cpp",
            lpSecurityAttributes,
            "NTSTATUS",
            &base);
          goto LABEL_50;
        }
LABEL_46:
        v22 = v29;
        v29 = 0;
        v30 = 0;
        Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v10);
        *v10 = v22;
        goto LABEL_50;
      }
      if ( dwDisposition != 1 )
        goto LABEL_46;
      memset(v32, 0, sizeof(v32));
      v19 = RegCreateKeyExW(v33[0], a3, 0, 0, v16, 0xF003Fu, 0, v32, 0);
      v18 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v21 = (unsigned __int16)v19 | 0xC0070000;
        else
          v21 = v19;
        v39 = v21;
        LODWORD(lpSecurityAttributes) = 1182;
        goto LABEL_32;
      }
      v21 = RegistryHelper::AddDaclAllowAce(a1, v32, v20);
      v39 = v21;
      if ( v21 < 0 )
      {
        LODWORD(lpSecurityAttributes) = 1185;
LABEL_32:
        LODWORD(phkResulta) = v21;
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          phkResulta,
          "registry.cpp",
          lpSecurityAttributes,
          "NTSTATUS",
          &base);
        Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v32);
        goto LABEL_50;
      }
      Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v32);
    }
LABEL_41:
    if ( !v18 )
      goto LABEL_46;
    goto LABEL_42;
  }
  LODWORD(lpSecurityAttributes) = 1159;
LABEL_16:
  LODWORD(phkResult) = v14;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", lpSecurityAttributes, "HRESULT", &base);
  v39 = v14 & 0xAFFFFFFF | 0x40000000;
LABEL_50:
  v23 = v39;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v38);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v33);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(&v29);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(hKey);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v34);
  return v23;
}

```

## disassembly

```asm
0x180074008  push    rbp
0x18007400a  push    rbx
0x18007400b  push    rsi
0x18007400c  push    rdi
0x18007400d  push    r12
0x18007400f  push    r13
0x180074011  push    r14
0x180074013  push    r15
0x180074015  lea     rbp, [rsp-8]
0x18007401a  sub     rsp, 108h
0x180074021  mov     r13d, r9d
0x180074024  mov     r14, r8
0x180074027  mov     rsi, rdx
0x18007402a  mov     r15, rcx
0x18007402d  xor     ebx, ebx
0x18007402f  mov     [rbp+40h+arg_0], ebx
0x180074032  mov     [rbp+40h+var_A0], rbx
0x180074036  mov     [rbp+40h+var_90], rcx
0x18007403a  mov     [rbp+40h+var_98], rbx
0x18007403e  mov     [rsp+140h+dwDisposition], ebx
0x180074042  mov     [rbp+40h+hKey], rbx
0x180074046  mov     [rbp+40h+var_78], rbx
0x18007404a  mov     [rbp+40h+var_80], rbx
0x18007404e  mov     [rsp+140h+var_E8], rbx
0x180074053  mov     [rsp+140h+var_D8], rbx
0x180074058  mov     [rsp+140h+var_E0], rbx
0x18007405d  mov     [rbp+40h+var_B8], rbx
0x180074061  mov     [rbp+40h+var_A8], rbx
0x180074065  mov     [rbp+40h+var_B0], rbx
0x180074069  lea     r9, [rbp+40h+arg_0]
0x18007406d  lea     r8, aRegistryhelper_8; "RegistryHelper::OpenUserSSOCacheKey"
0x180074074  lea     rdi, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x18007407b  mov     rdx, rdi
0x18007407e  lea     rcx, [rbp+40h+var_70]
0x180074082  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180074087  nop
0x180074088  test    r15, r15
0x18007408b  jz      loc_18007453E
0x180074091  test    r14, r14
0x180074094  jz      loc_18007453E
0x18007409a  cmp     [r14], bx
0x18007409e  jz      loc_18007453E
0x1800740a4  test    rsi, rsi
0x1800740a7  jz      loc_18007453E
0x1800740ad  cmp     [rsi], bx
0x1800740b0  jz      loc_18007453E
0x1800740b6  mov     r12, [rbp+40h+arg_28]
0x1800740ba  mov     rcx, r12
0x1800740bd  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x1800740c2  mov     rax, [r15]
0x1800740c5  mov     ebx, 208h
0x1800740ca  mov     r8d, ebx
0x1800740cd  mov     edx, 40h ; '@'
0x1800740d2  mov     rcx, r15
0x1800740d5  mov     rax, [rax+8]
0x1800740d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800740de  mov     rdi, rax
0x1800740e1  lea     rcx, [rbp+40h+var_A0]
0x1800740e5  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x1800740ea  mov     [rbp+40h+var_A0], rdi
0x1800740ee  mov     [rbp+40h+var_98], rbx
0x1800740f2  mov     ebx, 2
0x1800740f7  test    rdi, rdi
0x1800740fa  jnz     short loc_180074132
0x1800740fc  mov     ecx, 0C0000017h
0x180074101  lea     rax, base
0x180074108  mov     [rsp+140h+lpdwDisposition], rax
0x18007410d  lea     rax, aNtstatus; "NTSTATUS"
0x180074114  mov     [rsp+140h+var_108], rax
0x180074119  mov     dword ptr [rsp+140h+lpSecurityAttributes], 478h
0x180074121  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180074128  mov     qword ptr [rsp+140h+samDesired], rax
0x18007412d  jmp     loc_18007456D
0x180074132  mov     eax, r13d
0x180074135  and     eax, 6
0x180074138  cmp     al, 6
0x18007413a  jnz     loc_180074422
0x180074140  lea     rax, [rbp+40h+hKey]
0x180074144  mov     [rsp+140h+phkResult], rax; phkResult
0x180074149  mov     r9d, 20006h; samDesired
0x18007414f  xor     r8d, r8d; ulOptions
0x180074152  mov     rdx, rsi; lpSubKey
0x180074155  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18007415c  call    cs:__imp_RegOpenKeyExW
0x180074162  mov     ecx, eax
0x180074164  test    eax, eax
0x180074166  jz      short loc_1800741AB
0x180074168  jle     short loc_180074173
0x18007416a  movzx   ecx, cx
0x18007416d  or      ecx, 0C0070000h
0x180074173  mov     [rbp+40h+arg_0], ecx
0x180074176  test    ecx, ecx
0x180074178  jns     short loc_1800741AB
0x18007417a  lea     rax, base
0x180074181  mov     [rsp+140h+lpdwDisposition], rax
0x180074186  lea     rax, aNtstatus; "NTSTATUS"
0x18007418d  mov     [rsp+140h+var_108], rax
0x180074192  mov     dword ptr [rsp+140h+lpSecurityAttributes], 484h
0x18007419a  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x1800741a1  mov     qword ptr [rsp+140h+samDesired], rax
0x1800741a6  jmp     loc_180074570
0x1800741ab  lea     rax, aSsocache; "SSOCache"
0x1800741b2  mov     [rsp+140h+phkResult], rax
0x1800741b7  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800741be  lea     r8, aSS_5; "%s\\%s"
0x1800741c5  mov     edx, 104h; unsigned __int64
0x1800741ca  mov     rcx, rdi; unsigned __int16 *
0x1800741cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800741d2  mov     esi, eax
0x1800741d4  test    eax, eax
0x1800741d6  jns     short loc_18007422B
0x1800741d8  lea     rax, base
0x1800741df  mov     [rsp+140h+lpdwDisposition], rax
0x1800741e4  lea     rax, aHresult; "HRESULT"
0x1800741eb  mov     [rsp+140h+var_108], rax
0x1800741f0  mov     dword ptr [rsp+140h+lpSecurityAttributes], 487h
0x1800741f8  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x1800741ff  mov     qword ptr [rsp+140h+samDesired], rax
0x180074204  mov     dword ptr [rsp+140h+phkResult], esi
0x180074208  mov     r9d, ebx
0x18007420b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180074212  xor     edx, edx
0x180074214  mov     ecx, ebx
0x180074216  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007421b  btr     esi, 1Ch
0x18007421f  bts     esi, 1Eh
0x180074223  mov     [rbp+40h+arg_0], esi
0x180074226  jmp     loc_180074587
0x18007422b  xor     esi, esi
0x18007422d  cmp     [rdi], si
0x180074230  jnz     short loc_18007425C
0x180074232  mov     ecx, 0C00000E5h
0x180074237  lea     rax, base
0x18007423e  mov     [rsp+140h+lpdwDisposition], rax
0x180074243  lea     rax, aNtstatus; "NTSTATUS"
0x18007424a  mov     [rsp+140h+var_108], rax
0x18007424f  mov     dword ptr [rsp+140h+lpSecurityAttributes], 48Ah
0x180074257  jmp     loc_180074121
0x18007425c  mov     [rsp+140h+lpdwDisposition], rsi; lpdwDisposition
0x180074261  lea     rax, [rbp+40h+var_B8]
0x180074265  mov     [rsp+140h+var_108], rax; phkResult
0x18007426a  mov     [rsp+140h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18007426f  mov     [rsp+140h+samDesired], 20006h; samDesired
0x180074277  mov     dword ptr [rsp+140h+phkResult], esi; dwOptions
0x18007427b  xor     r9d, r9d; lpClass
0x18007427e  xor     r8d, r8d; Reserved
0x180074281  mov     rdx, rdi; lpSubKey
0x180074284  mov     rcx, [rbp+40h+hKey]; hKey
0x180074288  call    cs:__imp_RegCreateKeyExW
0x18007428e  mov     ecx, eax
0x180074290  test    eax, eax
0x180074292  jz      short loc_1800742CB
0x180074294  jle     short loc_18007429F
0x180074296  movzx   ecx, ax
0x180074299  or      ecx, 0C0070000h
0x18007429f  mov     [rbp+40h+arg_0], ecx
0x1800742a2  test    ecx, ecx
0x1800742a4  jns     short loc_1800742CB
0x1800742a6  lea     rax, base
0x1800742ad  mov     [rsp+140h+lpdwDisposition], rax
0x1800742b2  lea     rax, aNtstatus; "NTSTATUS"
0x1800742b9  mov     [rsp+140h+var_108], rax
0x1800742be  mov     dword ptr [rsp+140h+lpSecurityAttributes], 491h
0x1800742c6  jmp     loc_18007419A
0x1800742cb  mov     esi, dword ptr [rbp+40h+arg_20]
0x1800742ce  and     esi, 1
0x1800742d1  lea     rax, [rsp+140h+dwDisposition]
0x1800742d6  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x1800742db  lea     rax, [rsp+140h+var_E8]
0x1800742e0  mov     [rsp+140h+var_108], rax; phkResult
0x1800742e5  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800742ee  mov     [rsp+140h+samDesired], r13d; samDesired
0x1800742f3  mov     dword ptr [rsp+140h+phkResult], esi; dwOptions
0x1800742f7  xor     r9d, r9d; lpClass
0x1800742fa  xor     r8d, r8d; Reserved
0x1800742fd  mov     rdx, r14; lpSubKey
0x180074300  mov     rcx, [rbp+40h+var_B8]; hKey
0x180074304  call    cs:__imp_RegCreateKeyExW
0x18007430a  mov     edi, eax
0x18007430c  xor     r13d, r13d
0x18007430f  test    [rbp+40h+arg_20], bl
0x180074312  jz      loc_1800744D7
0x180074318  test    eax, eax
0x18007431a  jnz     loc_1800744DB
0x180074320  cmp     [rsp+140h+dwDisposition], 1
0x180074325  jnz     loc_180074521
0x18007432b  mov     [rsp+140h+var_D0], r13
0x180074330  mov     [rbp+40h+var_C0], r13
0x180074334  mov     [rsp+140h+var_C8], r13
0x180074339  mov     [rsp+140h+lpdwDisposition], r13; lpdwDisposition
0x18007433e  lea     rax, [rsp+140h+var_D0]
0x180074343  mov     [rsp+140h+var_108], rax; phkResult
0x180074348  mov     [rsp+140h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18007434d  mov     [rsp+140h+samDesired], 0F003Fh; samDesired
0x180074355  mov     dword ptr [rsp+140h+phkResult], esi; dwOptions
0x180074359  xor     r9d, r9d; lpClass
0x18007435c  xor     r8d, r8d; Reserved
0x18007435f  mov     rdx, r14; lpSubKey
0x180074362  mov     rcx, [rbp+40h+var_B8]; hKey
0x180074366  call    cs:__imp_RegCreateKeyExW
0x18007436c  mov     edi, eax
0x18007436e  test    eax, eax
0x180074370  jz      short loc_1800743DB
0x180074372  jg      short loc_180074378
0x180074374  mov     ecx, eax
0x180074376  jmp     short loc_180074381
0x180074378  movzx   ecx, ax
0x18007437b  or      ecx, 0C0070000h
0x180074381  mov     [rbp+40h+arg_0], ecx
0x180074384  test    ecx, ecx
0x180074386  jns     short loc_1800743DB
0x180074388  lea     rax, base
0x18007438f  mov     [rsp+140h+lpdwDisposition], rax
0x180074394  lea     rax, aNtstatus; "NTSTATUS"
0x18007439b  mov     [rsp+140h+var_108], rax
0x1800743a0  mov     dword ptr [rsp+140h+lpSecurityAttributes], 49Eh
0x1800743a8  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x1800743af  mov     qword ptr [rsp+140h+samDesired], rax
0x1800743b4  mov     dword ptr [rsp+140h+phkResult], ecx
0x1800743b8  mov     r9d, ebx
0x1800743bb  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800743c2  xor     edx, edx
0x1800743c4  mov     ecx, ebx
0x1800743c6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800743cb  nop
0x1800743cc  lea     rcx, [rsp+140h+var_D0]
0x1800743d1  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x1800743d6  jmp     loc_180074587
0x1800743db  lea     rdx, [rsp+140h+var_D0]
0x1800743e0  mov     rcx, r15
0x1800743e3  call    ?AddDaclAllowAce@RegistryHelper@@CAJPEAVAadContextFunctions@@AEBV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@PEBGK@Z; RegistryHelper::AddDaclAllowAce(AadContextFunctions *,Auto<HKEY__ *,RegistryFunctor,DummyContext> const &,ushort const *,ulong)
0x1800743e8  mov     ecx, eax
0x1800743ea  mov     [rbp+40h+arg_0], eax
0x1800743ed  test    eax, eax
0x1800743ef  jns     short loc_180074413
0x1800743f1  lea     rax, base
0x1800743f8  mov     [rsp+140h+lpdwDisposition], rax
0x1800743fd  lea     rax, aNtstatus; "NTSTATUS"
0x180074404  mov     [rsp+140h+var_108], rax
0x180074409  mov     dword ptr [rsp+140h+lpSecurityAttributes], 4A1h
0x180074411  jmp     short loc_1800743A8
0x180074413  lea     rcx, [rsp+140h+var_D0]
0x180074418  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x18007441d  jmp     loc_1800744D7
0x180074422  mov     [rsp+140h+lpSecurityAttributes], r14
0x180074427  lea     rax, aSsocache; "SSOCache"
0x18007442e  mov     qword ptr [rsp+140h+samDesired], rax
0x180074433  lea     rax, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007443a  mov     [rsp+140h+phkResult], rax
0x18007443f  mov     r9, rsi
0x180074442  lea     r8, aSSSS_2; "%s\\%s\\%s\\%s"
0x180074449  mov     edx, 104h; unsigned __int64
0x18007444e  mov     rcx, rdi; unsigned __int16 *
0x180074451  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180074456  mov     esi, eax
0x180074458  xor     eax, eax
0x18007445a  test    esi, esi
0x18007445c  jns     short loc_180074483
0x18007445e  lea     rax, base
0x180074465  mov     [rsp+140h+lpdwDisposition], rax
0x18007446a  lea     rax, aHresult; "HRESULT"
0x180074471  mov     [rsp+140h+var_108], rax
0x180074476  mov     dword ptr [rsp+140h+lpSecurityAttributes], 4A6h
0x18007447e  jmp     loc_1800741F8
0x180074483  cmp     [rdi], ax
0x180074486  jnz     short loc_1800744B2
0x180074488  mov     ecx, 0C00000E5h
0x18007448d  lea     rax, base
0x180074494  mov     [rsp+140h+lpdwDisposition], rax
0x180074499  lea     rax, aNtstatus; "NTSTATUS"
0x1800744a0  mov     [rsp+140h+var_108], rax
0x1800744a5  mov     dword ptr [rsp+140h+lpSecurityAttributes], 4A9h
0x1800744ad  jmp     loc_180074121
0x1800744b2  lea     rax, [rsp+140h+var_E8]
0x1800744b7  mov     [rsp+140h+phkResult], rax; phkResult
0x1800744bc  mov     r9d, r13d; samDesired
0x1800744bf  xor     r8d, r8d; ulOptions
0x1800744c2  mov     rdx, rdi; lpSubKey
0x1800744c5  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800744cc  call    cs:__imp_RegOpenKeyExW
0x1800744d2  mov     edi, eax
0x1800744d4  xor     r13d, r13d
0x1800744d7  test    edi, edi
0x1800744d9  jz      short loc_180074521
0x1800744db  test    edi, edi
0x1800744dd  jle     short loc_1800744E8
0x1800744df  movzx   edi, di
0x1800744e2  or      edi, 0C0070000h
0x1800744e8  mov     [rbp+40h+arg_0], edi
0x1800744eb  test    edi, edi
0x1800744ed  jns     short loc_180074521
0x1800744ef  lea     rax, base
0x1800744f6  mov     [rsp+140h+lpdwDisposition], rax
0x1800744fb  lea     rax, aNtstatus; "NTSTATUS"
0x180074502  mov     [rsp+140h+var_108], rax
0x180074507  mov     dword ptr [rsp+140h+lpSecurityAttributes], 4B1h
0x18007450f  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180074516  mov     qword ptr [rsp+140h+samDesired], rax
0x18007451b  mov     dword ptr [rsp+140h+phkResult], edi
0x18007451f  jmp     short loc_180074574
  ... truncated ...
```

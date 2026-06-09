# RegistryHelper::GetThumbprintKey(AadContextFunctions *,_GUID,ushort const *,bool,ulong,Auto<HKEY__ *,RegistryFunctor,DummyContext> &)

- ea: `0x1800731f8`
- end: `0x1800734aa`
- name: `?GetThumbprintKey@RegistryHelper@@CAJPEAVAadContextFunctions@@U_GUID@@PEBG_NKAEAV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@@Z`
- size: `690`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072478`
- `0x1800737f0`
- `0x1800745dc`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180071e14`
- `0x180072334`
- `0x1800731f8`
- `0x180073c70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007330f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073384`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007330f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073384`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800733cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800733cc`

## string_xrefs

- `0x18007324e`: `RegistryHelper::GetThumbprintKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegistryHelper::GetThumbprintKey(
        __int64 a1,
        __int128 *a2,
        const WCHAR *a3,
        char a4,
        REGSAM a5,
        HKEY *a6)
{
  HKEY *v10; // rdi
  REGSAM samDesired; // r14d
  __int64 v12; // r8
  int Key; // eax
  HKEY v14; // rbx
  unsigned int v15; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-B9h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-A9h]
  HKEY v19; // [rsp+50h] [rbp-89h] BYREF
  __int64 v20; // [rsp+58h] [rbp-81h]
  __int64 v21; // [rsp+60h] [rbp-79h]
  HKEY phkResult[3]; // [rsp+68h] [rbp-71h] BYREF
  HKEY hKey[4]; // [rsp+80h] [rbp-59h] BYREF
  __int128 v24; // [rsp+A0h] [rbp-39h] BYREF
  const char *v25[14]; // [rsp+B0h] [rbp-29h] BYREF
  int v26; // [rsp+130h] [rbp+57h] BYREF

  v26 = 0;
  memset(hKey, 0, 24);
  memset(phkResult, 0, sizeof(phkResult));
  v19 = 0;
  v21 = 0;
  v20 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v25,
    (int)"registry.cpp",
    (int)"RegistryHelper::GetThumbprintKey",
    (int)&v26);
  if ( !a1 || !a3 )
  {
    Key = -1073741811;
    v26 = -1073741811;
    LODWORD(lpSecurityAttributes) = 437;
    goto LABEL_23;
  }
  v10 = a6;
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(a6);
  v24 = *a2;
  samDesired = a5;
  LOBYTE(v12) = 1;
  Key = RegistryHelper::OpenIdentityProviderKey(a1, &v24, v12, a5, hKey);
  v26 = Key;
  if ( Key < 0 )
  {
    LODWORD(lpSecurityAttributes) = 447;
LABEL_23:
    dwOptions[0] = Key;
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      *(_QWORD *)dwOptions,
      "registry.cpp",
      lpSecurityAttributes,
      "NTSTATUS",
      &base);
    goto LABEL_24;
  }
  Key = RegCreateKeyExW(hKey[0], L"ThrottlingData", 0, 0, 1u, samDesired, 0, phkResult, 0);
  if ( Key )
  {
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0xC0070000;
    v26 = Key;
    LODWORD(lpSecurityAttributes) = 462;
    goto LABEL_23;
  }
  if ( a4 )
  {
    Key = RegCreateKeyExW(phkResult[0], a3, 0, 0, 1u, 0x20006u, 0, &v19, 0);
    if ( Key )
    {
      if ( Key > 0 )
        Key = (unsigned __int16)Key | 0xC0070000;
      v26 = Key;
      LODWORD(lpSecurityAttributes) = 480;
      goto LABEL_23;
    }
  }
  else
  {
    Key = RegOpenKeyExW(phkResult[0], a3, 0, 0x20019u, &v19);
    if ( Key )
    {
      if ( Key > 0 )
        Key = (unsigned __int16)Key | 0xC0070000;
      v26 = Key;
      LODWORD(lpSecurityAttributes) = 494;
      goto LABEL_23;
    }
  }
  v14 = v19;
  v19 = 0;
  v20 = 0;
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(v10);
  *v10 = v14;
LABEL_24:
  v15 = v26;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v25);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(&v19);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(phkResult);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(hKey);
  return v15;
}

```

## disassembly

```asm
0x1800731f8  push    rbp
0x1800731fa  push    rbx
0x1800731fb  push    rsi
0x1800731fc  push    rdi
0x1800731fd  push    r12
0x1800731ff  push    r13
0x180073201  push    r14
0x180073203  push    r15
0x180073205  lea     rbp, [rsp-0Fh]
0x18007320a  sub     rsp, 0E8h
0x180073211  mov     r15b, r9b
0x180073214  mov     rbx, r8
0x180073217  mov     r14, rdx
0x18007321a  mov     rsi, rcx
0x18007321d  xor     r12d, r12d
0x180073220  mov     [rbp+47h+arg_0], r12d
0x180073224  mov     [rbp+47h+hKey], r12
0x180073228  mov     [rbp+47h+var_90], r12
0x18007322c  mov     [rbp+47h+var_98], r12
0x180073230  mov     [rbp+47h+var_B8], r12
0x180073234  mov     [rbp+47h+var_A8], r12
0x180073238  mov     [rbp+47h+var_B0], r12
0x18007323c  mov     [rsp+120h+var_D0], r12
0x180073241  mov     [rbp+47h+var_C0], r12
0x180073245  mov     [rsp+120h+var_C8], r12
0x18007324a  lea     r9, [rbp+47h+arg_0]
0x18007324e  lea     r8, aRegistryhelper_11; "RegistryHelper::GetThumbprintKey"
0x180073255  lea     r13, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x18007325c  mov     rdx, r13
0x18007325f  lea     rcx, [rbp+47h+var_70]
0x180073263  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180073268  nop
0x180073269  test    rsi, rsi
0x18007326c  jz      loc_180073422
0x180073272  test    rbx, rbx
0x180073275  jz      loc_180073422
0x18007327b  mov     rdi, [rbp+47h+arg_28]
0x18007327f  mov     rcx, rdi
0x180073282  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073287  movaps  xmm0, xmmword ptr [r14]
0x18007328b  movdqa  [rbp+47h+var_80], xmm0
0x180073290  lea     rax, [rbp+47h+hKey]
0x180073294  mov     qword ptr [rsp+120h+dwOptions], rax
0x180073299  mov     r14d, [rbp+47h+arg_20]
0x18007329d  mov     r9d, r14d
0x1800732a0  mov     r8b, 1
0x1800732a3  lea     rdx, [rbp+47h+var_80]
0x1800732a7  mov     rcx, rsi
0x1800732aa  call    ?OpenIdentityProviderKey@RegistryHelper@@CAJPEAVAadContextFunctions@@U_GUID@@_NKAEAV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@@Z; RegistryHelper::OpenIdentityProviderKey(AadContextFunctions *,_GUID,bool,ulong,Auto<HKEY__ *,RegistryFunctor,DummyContext> &)
0x1800732af  mov     [rbp+47h+arg_0], eax
0x1800732b2  test    eax, eax
0x1800732b4  jns     short loc_1800732DB
0x1800732b6  lea     rcx, base
0x1800732bd  mov     [rsp+120h+lpdwDisposition], rcx
0x1800732c2  lea     rcx, aNtstatus; "NTSTATUS"
0x1800732c9  mov     [rsp+120h+phkResult], rcx
0x1800732ce  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1BFh
0x1800732d6  jmp     loc_18007344A
0x1800732db  mov     [rsp+120h+lpdwDisposition], r12; lpdwDisposition
0x1800732e0  lea     rax, [rbp+47h+var_B8]
0x1800732e4  mov     [rsp+120h+phkResult], rax; phkResult
0x1800732e9  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800732ee  mov     [rsp+120h+samDesired], r14d; samDesired
0x1800732f3  mov     r14d, 1
0x1800732f9  mov     [rsp+120h+dwOptions], r14d; dwOptions
0x1800732fe  xor     r9d, r9d; lpClass
0x180073301  xor     r8d, r8d; Reserved
0x180073304  lea     rdx, SubKey; "ThrottlingData"
0x18007330b  mov     rcx, [rbp+47h+hKey]; hKey
0x18007330f  call    cs:__imp_RegCreateKeyExW
0x180073315  mov     esi, 0C0070000h
0x18007331a  test    eax, eax
0x18007331c  jz      short loc_180073351
0x18007331e  jle     short loc_180073325
0x180073320  movzx   eax, ax
0x180073323  or      eax, esi
0x180073325  mov     [rbp+47h+arg_0], eax
0x180073328  test    eax, eax
0x18007332a  jns     short loc_180073351
0x18007332c  lea     rcx, base
0x180073333  mov     [rsp+120h+lpdwDisposition], rcx
0x180073338  lea     rcx, aNtstatus; "NTSTATUS"
0x18007333f  mov     [rsp+120h+phkResult], rcx
0x180073344  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1CEh
0x18007334c  jmp     loc_18007344A
0x180073351  lea     rax, [rsp+120h+var_D0]
0x180073356  xor     r8d, r8d; ulOptions
0x180073359  mov     rdx, rbx; lpSubKey
0x18007335c  mov     rcx, [rbp+47h+var_B8]; hKey
0x180073360  test    r15b, r15b
0x180073363  jz      short loc_1800733C1
0x180073365  mov     [rsp+120h+lpdwDisposition], r12; lpdwDisposition
0x18007336a  mov     [rsp+120h+phkResult], rax; phkResult
0x18007336f  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180073374  mov     [rsp+120h+samDesired], 20006h; samDesired
0x18007337c  mov     [rsp+120h+dwOptions], r14d; dwOptions
0x180073381  xor     r9d, r9d; lpClass
0x180073384  call    cs:__imp_RegCreateKeyExW
0x18007338a  test    eax, eax
0x18007338c  jz      short loc_180073406
0x18007338e  jle     short loc_180073395
0x180073390  movzx   eax, ax
0x180073393  or      eax, esi
0x180073395  mov     [rbp+47h+arg_0], eax
0x180073398  test    eax, eax
0x18007339a  jns     short loc_180073406
0x18007339c  lea     rcx, base
0x1800733a3  mov     [rsp+120h+lpdwDisposition], rcx
0x1800733a8  lea     rcx, aNtstatus; "NTSTATUS"
0x1800733af  mov     [rsp+120h+phkResult], rcx
0x1800733b4  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1E0h
0x1800733bc  jmp     loc_18007344A
0x1800733c1  mov     qword ptr [rsp+120h+dwOptions], rax; phkResult
0x1800733c6  mov     r9d, 20019h; samDesired
0x1800733cc  call    cs:__imp_RegOpenKeyExW
0x1800733d2  test    eax, eax
0x1800733d4  jz      short loc_180073406
0x1800733d6  jle     short loc_1800733DD
0x1800733d8  movzx   eax, ax
0x1800733db  or      eax, esi
0x1800733dd  mov     [rbp+47h+arg_0], eax
0x1800733e0  test    eax, eax
0x1800733e2  jns     short loc_180073406
0x1800733e4  lea     rcx, base
0x1800733eb  mov     [rsp+120h+lpdwDisposition], rcx
0x1800733f0  lea     rcx, aNtstatus; "NTSTATUS"
0x1800733f7  mov     [rsp+120h+phkResult], rcx
0x1800733fc  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1EEh
0x180073404  jmp     short loc_18007344A
0x180073406  mov     rbx, [rsp+120h+var_D0]
0x18007340b  mov     [rsp+120h+var_D0], r12
0x180073410  mov     [rsp+120h+var_C8], r12
0x180073415  mov     rcx, rdi
0x180073418  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x18007341d  mov     [rdi], rbx
0x180073420  jmp     short loc_180073469
0x180073422  mov     eax, 0C000000Dh
0x180073427  mov     [rbp+47h+arg_0], eax
0x18007342a  lea     rcx, base
0x180073431  mov     [rsp+120h+lpdwDisposition], rcx
0x180073436  lea     rcx, aNtstatus; "NTSTATUS"
0x18007343d  mov     [rsp+120h+phkResult], rcx
0x180073442  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1B5h
0x18007344a  mov     qword ptr [rsp+120h+samDesired], r13
0x18007344f  mov     ecx, 2
0x180073454  mov     [rsp+120h+dwOptions], eax
0x180073458  mov     r9d, ecx
0x18007345b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180073462  xor     edx, edx
0x180073464  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180073469  mov     ebx, [rbp+47h+arg_0]
0x18007346c  lea     rcx, [rbp+47h+var_70]
0x180073470  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180073475  nop
0x180073476  lea     rcx, [rsp+120h+var_D0]
0x18007347b  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073480  nop
0x180073481  lea     rcx, [rbp+47h+var_B8]
0x180073485  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x18007348a  nop
0x18007348b  lea     rcx, [rbp+47h+hKey]
0x18007348f  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073494  mov     eax, ebx
0x180073496  add     rsp, 0E8h
0x18007349d  pop     r15
0x18007349f  pop     r14
0x1800734a1  pop     r13
0x1800734a3  pop     r12
0x1800734a5  pop     rdi
0x1800734a6  pop     rsi
0x1800734a7  pop     rbx
0x1800734a8  pop     rbp
0x1800734a9  retn
```

# RegistryHelper::OpenIdentityProviderKey(AadContextFunctions *,_GUID,bool,ulong,Auto<HKEY__ *,RegistryFunctor,DummyContext> &)

- ea: `0x180073c70`
- end: `0x180074000`
- name: `?OpenIdentityProviderKey@RegistryHelper@@CAJPEAVAadContextFunctions@@U_GUID@@_NKAEAV?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@@Z`
- size: `912`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800727f8`
- `0x180072fd8`
- `0x1800731f8`
- `0x180074a74`
- `0x180074d64`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180019868`
- `0x1800256d0`
- `0x180071e14`
- `0x180072334`
- `0x180073c70`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180073d93`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180073d93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073f04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073f04`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180073e62`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180073e62`

## string_xrefs

- `0x180073cd8`: `RegistryHelper::OpenIdentityProviderKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RegistryHelper::OpenIdentityProviderKey(__int64 a1, const GUID *a2, char a3, REGSAM a4, HKEY *a5)
{
  OLECHAR *v8; // r15
  unsigned __int16 *v9; // r12
  unsigned __int16 *v10; // rsi
  int v11; // ebx
  int PersistedRegistryLocationW; // eax
  signed int v13; // ecx
  LSTATUS v14; // eax
  HKEY v15; // rbx
  unsigned int v16; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-B1h]
  int v19; // [rsp+30h] [rbp-A1h]
  int v20; // [rsp+30h] [rbp-A1h]
  unsigned int v21; // [rsp+50h] [rbp-81h] BYREF
  REGSAM samDesired; // [rsp+54h] [rbp-7Dh]
  HKEY v23; // [rsp+58h] [rbp-79h] BYREF
  __int64 v24; // [rsp+60h] [rbp-71h]
  __int64 v25; // [rsp+68h] [rbp-69h]
  unsigned __int16 *v26; // [rsp+70h] [rbp-61h] BYREF
  __int64 v27; // [rsp+78h] [rbp-59h]
  __int64 v28; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v29; // [rsp+88h] [rbp-49h] BYREF
  __int64 v30; // [rsp+90h] [rbp-41h]
  __int64 v31; // [rsp+98h] [rbp-39h]
  OLECHAR *v32; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-29h]
  __int64 v34; // [rsp+B0h] [rbp-21h]
  const char *v35[13]; // [rsp+B8h] [rbp-19h] BYREF

  samDesired = a4;
  v21 = 0;
  v32 = 0;
  v34 = a1;
  v33 = 0;
  v29 = 0;
  v31 = a1;
  v30 = 0;
  v26 = 0;
  v28 = a1;
  v27 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v35,
    (int)"registry.cpp",
    (int)"RegistryHelper::OpenIdentityProviderKey",
    (int)&v21);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(a5);
  v8 = (OLECHAR *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 64, 82);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v32);
  v32 = v8;
  v33 = 82;
  v9 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 64, 520);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v29);
  v29 = v9;
  v30 = 520;
  v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 64, 520);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v26);
  v26 = v10;
  v27 = 520;
  if ( !StringFromGUID2(a2, v8, 82) )
  {
    v19 = 700;
LABEL_23:
    v13 = -1073741595;
    v21 = -1073741595;
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v11 = StringCchPrintfW(v10, 0x104u, L"%s\\%s", L"Software\\Microsoft\\IdentityStore\\Providers", v8);
    if ( v11 < 0 )
    {
      v20 = 727;
      goto LABEL_6;
    }
    goto LABEL_14;
  }
  v11 = StringCchPrintfW(v9, 0x104u, L"%s\\%s", L"Software\\Microsoft\\IdentityStore\\LoadParameters", v8);
  if ( v11 >= 0 )
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(L"IDStoreLoadParametersAad", v9, v10, 520, 0);
    v13 = PersistedRegistryLocationW;
    if ( PersistedRegistryLocationW )
    {
      if ( PersistedRegistryLocationW > 0 )
        v13 = (unsigned __int16)PersistedRegistryLocationW | 0xC0070000;
      v21 = v13;
      if ( v13 < 0 )
      {
        v19 = 719;
        goto LABEL_24;
      }
    }
LABEL_14:
    if ( !v10 || !*v10 )
    {
      v19 = 732;
      goto LABEL_23;
    }
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, samDesired, &v23);
    v13 = v14;
    if ( !v14 )
      goto LABEL_21;
    if ( v14 > 0 )
      v13 = (unsigned __int16)v14 | 0xC0070000;
    v21 = v13;
    if ( v13 >= 0 )
    {
LABEL_21:
      v15 = v23;
      v23 = 0;
      v24 = 0;
      Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(a5);
      *a5 = v15;
      goto LABEL_25;
    }
    v19 = 742;
LABEL_24:
    LODWORD(phkResult) = v13;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", v19, "NTSTATUS", &base);
    goto LABEL_25;
  }
  v20 = 708;
LABEL_6:
  LODWORD(phkResult) = v11;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, phkResult, "registry.cpp", v20, "HRESULT", &base);
  v21 = v11 & 0xAFFFFFFF | 0x40000000;
LABEL_25:
  v16 = v21;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v35);
  Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(&v23);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v26);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v29);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v32);
  return v16;
}

```

## disassembly

```asm
0x180073c70  mov     [rsp-8+arg_10], rbx
0x180073c75  push    rbp
0x180073c76  push    rsi
0x180073c77  push    rdi
0x180073c78  push    r12
0x180073c7a  push    r13
0x180073c7c  push    r14
0x180073c7e  push    r15
0x180073c80  lea     rbp, [rsp-1Fh]
0x180073c85  sub     rsp, 0F0h
0x180073c8c  mov     [rbp+4Fh+samDesired], r9d
0x180073c90  mov     r13b, r8b
0x180073c93  mov     rdi, rdx
0x180073c96  mov     rbx, rcx
0x180073c99  mov     r14, [rbp+4Fh+arg_20]
0x180073c9d  xor     eax, eax
0x180073c9f  mov     [rsp+120h+var_D0], eax
0x180073ca3  mov     [rbp+4Fh+var_80], rax
0x180073ca7  mov     [rbp+4Fh+var_70], rcx
0x180073cab  mov     [rbp+4Fh+var_78], rax
0x180073caf  mov     [rbp+4Fh+var_98], rax
0x180073cb3  mov     [rbp+4Fh+var_88], rcx
0x180073cb7  mov     [rbp+4Fh+var_90], rax
0x180073cbb  mov     [rbp+4Fh+var_B0], rax
0x180073cbf  mov     [rbp+4Fh+var_A0], rcx
0x180073cc3  mov     [rbp+4Fh+var_A8], rax
0x180073cc7  mov     [rbp+4Fh+var_C8], rax
0x180073ccb  mov     [rbp+4Fh+var_B8], rax
0x180073ccf  mov     [rbp+4Fh+var_C0], rax
0x180073cd3  lea     r9, [rsp+120h+var_D0]
0x180073cd8  lea     r8, aRegistryhelper; "RegistryHelper::OpenIdentityProviderKey"
0x180073cdf  lea     rdx, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180073ce6  lea     rcx, [rbp+4Fh+var_68]
0x180073cea  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180073cef  nop
0x180073cf0  mov     rcx, r14
0x180073cf3  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073cf8  mov     rax, [rbx]
0x180073cfb  mov     r12d, 52h ; 'R'
0x180073d01  mov     r8d, r12d
0x180073d04  lea     esi, [r12-12h]
0x180073d09  mov     edx, esi
0x180073d0b  mov     rcx, rbx
0x180073d0e  mov     rax, [rax+8]
0x180073d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d17  mov     r15, rax
0x180073d1a  lea     rcx, [rbp+4Fh+var_80]
0x180073d1e  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073d23  mov     [rbp+4Fh+var_80], r15
0x180073d27  mov     [rbp+4Fh+var_78], r12
0x180073d2b  mov     rcx, [rbx]
0x180073d2e  mov     rax, [rcx+8]
0x180073d32  mov     r8d, 208h
0x180073d38  mov     edx, esi
0x180073d3a  mov     rcx, rbx
0x180073d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d42  mov     r12, rax
0x180073d45  lea     rcx, [rbp+4Fh+var_98]
0x180073d49  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073d4e  mov     [rbp+4Fh+var_98], r12
0x180073d52  mov     eax, 208h
0x180073d57  mov     [rbp+4Fh+var_90], rax
0x180073d5b  mov     r9, [rbx]
0x180073d5e  mov     r8d, eax
0x180073d61  mov     edx, esi
0x180073d63  mov     rcx, rbx
0x180073d66  mov     rax, [r9+8]
0x180073d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d6f  mov     rsi, rax
0x180073d72  lea     rcx, [rbp+4Fh+var_B0]
0x180073d76  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073d7b  mov     [rbp+4Fh+var_B0], rsi
0x180073d7f  mov     [rbp+4Fh+var_A8], 208h
0x180073d87  mov     r8d, 52h ; 'R'; cchMax
0x180073d8d  mov     rdx, r15; lpsz
0x180073d90  mov     rcx, rdi; rguid
0x180073d93  call    cs:__imp_StringFromGUID2
0x180073d99  xor     edi, edi
0x180073d9b  test    eax, eax
0x180073d9d  jnz     short loc_180073DC4
0x180073d9f  lea     rax, base
0x180073da6  mov     [rsp+120h+var_E0], rax
0x180073dab  lea     rax, aNtstatus; "NTSTATUS"
0x180073db2  mov     [rsp+120h+var_E8], rax
0x180073db7  mov     [rsp+120h+var_F0], 2BCh
0x180073dbf  jmp     loc_180073F7E
0x180073dc4  mov     [rsp+120h+phkResult], r15
0x180073dc9  lea     r8, aSS_5; "%s\\%s"
0x180073dd0  mov     edx, 104h; unsigned __int64
0x180073dd5  test    r13b, r13b
0x180073dd8  jz      loc_180073EA6
0x180073dde  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\IdentityStore\\Loa"...
0x180073de5  mov     rcx, r12; unsigned __int16 *
0x180073de8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180073ded  mov     ebx, eax
0x180073def  test    eax, eax
0x180073df1  jns     short loc_180073E4A
0x180073df3  lea     rax, base
0x180073dfa  mov     [rsp+120h+var_E0], rax
0x180073dff  lea     rax, aHresult; "HRESULT"
0x180073e06  mov     [rsp+120h+var_E8], rax
0x180073e0b  mov     [rsp+120h+var_F0], 2C4h
0x180073e13  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180073e1a  mov     [rsp+120h+var_F8], rax
0x180073e1f  mov     dword ptr [rsp+120h+phkResult], ebx
0x180073e23  mov     ecx, 2
0x180073e28  mov     r9d, ecx
0x180073e2b  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180073e32  xor     edx, edx
0x180073e34  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180073e39  btr     ebx, 1Ch
0x180073e3d  bts     ebx, 1Eh
0x180073e41  mov     [rsp+120h+var_D0], ebx
0x180073e45  jmp     loc_180073FAD
0x180073e4a  mov     [rsp+120h+phkResult], rdi
0x180073e4f  mov     r9d, 208h
0x180073e55  mov     r8, rsi
0x180073e58  mov     rdx, r12
0x180073e5b  lea     rcx, aIdstoreloadpar; "IDStoreLoadParametersAad"
0x180073e62  call    cs:__imp_GetPersistedRegistryLocationW
0x180073e68  mov     ecx, eax
0x180073e6a  test    eax, eax
0x180073e6c  jz      short loc_180073EE0
0x180073e6e  jle     short loc_180073E79
0x180073e70  movzx   ecx, ax
0x180073e73  or      ecx, 0C0070000h
0x180073e79  mov     [rsp+120h+var_D0], ecx
0x180073e7d  test    ecx, ecx
0x180073e7f  jns     short loc_180073EE0
0x180073e81  lea     rax, base
0x180073e88  mov     [rsp+120h+var_E0], rax
0x180073e8d  lea     rax, aNtstatus; "NTSTATUS"
0x180073e94  mov     [rsp+120h+var_E8], rax
0x180073e99  mov     [rsp+120h+var_F0], 2CFh
0x180073ea1  jmp     loc_180073F87
0x180073ea6  lea     r9, aSoftwareMicros_4; "Software\\Microsoft\\IdentityStore\\Pro"...
0x180073ead  mov     rcx, rsi; unsigned __int16 *
0x180073eb0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180073eb5  mov     ebx, eax
0x180073eb7  test    eax, eax
0x180073eb9  jns     short loc_180073EE0
0x180073ebb  lea     rax, base
0x180073ec2  mov     [rsp+120h+var_E0], rax
0x180073ec7  lea     rax, aHresult; "HRESULT"
0x180073ece  mov     [rsp+120h+var_E8], rax
0x180073ed3  mov     [rsp+120h+var_F0], 2D7h
0x180073edb  jmp     loc_180073E13
0x180073ee0  test    rsi, rsi
0x180073ee3  jz      short loc_180073F5E
0x180073ee5  cmp     [rsi], di
0x180073ee8  jz      short loc_180073F5E
0x180073eea  lea     rax, [rbp+4Fh+var_C8]
0x180073eee  mov     [rsp+120h+phkResult], rax; phkResult
0x180073ef3  mov     r9d, [rbp+4Fh+samDesired]; samDesired
0x180073ef7  xor     r8d, r8d; ulOptions
0x180073efa  mov     rdx, rsi; lpSubKey
0x180073efd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073f04  call    cs:__imp_RegOpenKeyExW
0x180073f0a  mov     ecx, eax
0x180073f0c  test    eax, eax
0x180073f0e  jz      short loc_180073F45
0x180073f10  jle     short loc_180073F1B
0x180073f12  movzx   ecx, ax
0x180073f15  or      ecx, 0C0070000h
0x180073f1b  mov     [rsp+120h+var_D0], ecx
0x180073f1f  test    ecx, ecx
0x180073f21  jns     short loc_180073F45
0x180073f23  lea     rax, base
0x180073f2a  mov     [rsp+120h+var_E0], rax
0x180073f2f  lea     rax, aNtstatus; "NTSTATUS"
0x180073f36  mov     [rsp+120h+var_E8], rax
0x180073f3b  mov     [rsp+120h+var_F0], 2E6h
0x180073f43  jmp     short loc_180073F87
0x180073f45  mov     rbx, [rbp+4Fh+var_C8]
0x180073f49  mov     [rbp+4Fh+var_C8], rdi
0x180073f4d  mov     [rbp+4Fh+var_C0], rdi
0x180073f51  mov     rcx, r14
0x180073f54  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073f59  mov     [r14], rbx
0x180073f5c  jmp     short loc_180073FAD
0x180073f5e  lea     rax, base
0x180073f65  mov     [rsp+120h+var_E0], rax
0x180073f6a  lea     rax, aNtstatus; "NTSTATUS"
0x180073f71  mov     [rsp+120h+var_E8], rax
0x180073f76  mov     [rsp+120h+var_F0], 2DCh
0x180073f7e  mov     ecx, 0C00000E5h
0x180073f83  mov     [rsp+120h+var_D0], ecx
0x180073f87  lea     rax, aOnecoreuapDsEx_6+20h; "registry.cpp"
0x180073f8e  mov     [rsp+120h+var_F8], rax
0x180073f93  mov     dword ptr [rsp+120h+phkResult], ecx
0x180073f97  mov     ecx, 2
0x180073f9c  mov     r9d, ecx
0x180073f9f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180073fa6  xor     edx, edx
0x180073fa8  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180073fad  mov     ebx, [rsp+120h+var_D0]
0x180073fb1  lea     rcx, [rbp+4Fh+var_68]
0x180073fb5  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180073fba  nop
0x180073fbb  lea     rcx, [rbp+4Fh+var_C8]
0x180073fbf  call    ?Clear@?$Auto@PEAUHKEY__@@VRegistryFunctor@@VDummyContext@@@@QEAAXXZ; Auto<HKEY__ *,RegistryFunctor,DummyContext>::Clear(void)
0x180073fc4  nop
0x180073fc5  lea     rcx, [rbp+4Fh+var_B0]
0x180073fc9  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073fce  nop
0x180073fcf  lea     rcx, [rbp+4Fh+var_98]
0x180073fd3  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073fd8  nop
0x180073fd9  lea     rcx, [rbp+4Fh+var_80]
0x180073fdd  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180073fe2  nop
0x180073fe3  mov     eax, ebx
0x180073fe5  mov     rbx, [rsp+120h+arg_10]
0x180073fed  add     rsp, 0F0h
0x180073ff4  pop     r15
0x180073ff6  pop     r14
0x180073ff8  pop     r13
0x180073ffa  pop     r12
0x180073ffc  pop     rdi
0x180073ffd  pop     rsi
0x180073ffe  pop     rbp
0x180073fff  retn
```

# SITE_BINDINGS_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x1800165d0`
- end: `0x180016ac4`
- name: `?SetConfigProperties@SITE_BINDINGS_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(SITE_BINDINGS_CUSTOM_MAPPER *this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f90`
- `0x180003460`
- `0x18000b178`
- `0x18000ef4c`
- `0x1800165d0`
- `0x18002735c`
- `0x1800273c4`
- `0x1800278cc`
- `0x180028654`
- `0x180028c64`
- `0x180028f20`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001674c`
- `msvcrt!_wcsicmp` at `0x18001674c`
- `WS2_32!FreeAddrInfoW` at `0x180016a7e`
- `WS2_32!FreeAddrInfoW` at `0x180016a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016909`
- `iisutil!?IsEmpty@MULTISZ@@QEBAHXZ` at `0x1800169ed`
- `iisutil!?IsEmpty@MULTISZ@@QEBAHXZ` at `0x1800169ed`
- `iisutil!?Append@MULTISZ@@QEAAHPEBGK@Z` at `0x1800167aa`
- `iisutil!?Append@MULTISZ@@QEAAHPEBGK@Z` at `0x1800167aa`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800166df`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x1800166df`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180016a1f`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180016a1f`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800169fc`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x1800169fc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001680b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001680b`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180016642`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180016642`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180016a89`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180016a89`

## string_xrefs

- `0x180016727`: `protocol`
- `0x180016853`: `protocol`
- `0x1800168eb`: `GenerateSSLProperties() failed with %08x during SetConfigProperties()\n`
- `0x18001693a`: `GetSSLProperties() failed with %08x during SetConfigProperties()\n`
- `0x18001697e`: `SetHttpSysSSLData() failed with %08x during SetConfigProperties()\n`

## pseudocode

```c
__int64 __fastcall SITE_BINDINGS_CUSTOM_MAPPER::SetConfigProperties(
        SITE_BINDINGS_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int v5; // r15d
  struct addrinfoW *v7; // rsi
  int v10; // eax
  const wchar_t *v11; // r13
  unsigned int v12; // edi
  signed int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // edi
  int SSLProperties; // eax
  signed int LastError; // eax
  int v20; // eax
  int SockAddress; // eax
  int v22; // eax
  ABO_WRAPPER *v23; // rcx
  __int64 v24; // rax
  wchar_t *v25; // rdx
  wchar_t *v26; // rax
  ABO_WRAPPER *v27; // rcx
  wchar_t *Str; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  struct addrinfoW *v33; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v35[64]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[240]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = 0;
  v31 = 0;
  v7 = 0;
  v32 = 0;
  v30 = 0;
  String1 = 0;
  Str = 0;
  v33 = 0;
  SSL_DATA::SSL_DATA((SSL_DATA *)v36);
  MULTISZ::MULTISZ((MULTISZ *)v35);
  if ( !a5 || !a3 || !a2 || !a4 )
  {
    v13 = -2147024809;
    goto LABEL_54;
  }
  v10 = *((_DWORD *)a2 + 36);
  if ( v10 == 1023 )
  {
    v11 = L"http";
  }
  else
  {
    if ( v10 != 2021 )
    {
      v13 = -2147024846;
      goto LABEL_54;
    }
    v11 = L"https";
    v5 = 1;
  }
  v12 = 0;
  v13 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a5 + 40LL))(a5, &v32);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 24LL))(v32, &v31);
    if ( v13 >= 0 )
    {
      MULTISZ::Reset((MULTISZ *)v35);
      if ( v31 )
      {
        do
        {
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 32LL))(v32, v12, &v30);
          if ( v13 < 0 )
            goto LABEL_54;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
                  v30,
                  L"protocol",
                  &String1,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_54;
          v14 = _wcsicmp(String1, v11);
          v15 = 0;
          if ( !v14 )
          {
            if ( v5 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
                      v30,
                      L"bindingInformation",
                      &Str,
                      0,
                      0);
              if ( v13 < 0 )
                goto LABEL_54;
              v16 = -1;
              do
                ++v16;
              while ( Str[v16] );
              if ( !MULTISZ::Append((MULTISZ *)v35, Str, v16) )
              {
                LastError = GetLastError();
                v13 = LastError;
                if ( LastError > 0 )
                  v13 = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_54;
              }
            }
            v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 64LL))(v32, v12, 0);
            if ( v13 < 0 )
              goto LABEL_54;
            --v12;
            --v31;
          }
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 16LL))(v30, v15);
          ++v12;
          v30 = 0;
        }
        while ( v12 < v31 );
      }
      v17 = 0;
      Str = (wchar_t *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
      if ( !*Str )
      {
LABEL_47:
        if ( !MULTISZ::IsEmpty((MULTISZ *)v35) )
        {
          v26 = (wchar_t *)MULTISZ::First((MULTISZ *)v35);
          Str = v26;
          do
          {
            v13 = ABO_WRAPPER::RemoveBinding(v27, v26);
            if ( v13 < 0 )
              break;
            v26 = (wchar_t *)MULTISZ::Next((MULTISZ *)v35, Str);
            Str = v26;
          }
          while ( v26 );
        }
        goto LABEL_54;
      }
      while ( 1 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v32 + 48LL))(
                v32,
                L"binding",
                &v30);
        if ( v13 < 0 )
          goto LABEL_54;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v30 + 128LL))(
                v30,
                L"protocol",
                v11,
                0);
        if ( v13 < 0 )
          goto LABEL_54;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t *, _QWORD))(*(_QWORD *)v30 + 128LL))(
                v30,
                L"bindingInformation",
                Str,
                0);
        if ( v13 < 0 )
          goto LABEL_54;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v32 + 56LL))(
                v32,
                v30,
                0xFFFFFFFFLL,
                0);
        if ( v13 < 0 )
          goto LABEL_54;
        if ( v5 )
          break;
LABEL_42:
        v24 = -1;
        do
          ++v24;
        while ( Str[v24] );
        v25 = &Str[v24 + 1];
        Str = v25;
        if ( v30 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v25 = Str;
          v30 = 0;
        }
        if ( !*v25 )
          goto LABEL_47;
      }
      if ( !v17 )
      {
        SSLProperties = GenerateSSLProperties(a4, Str);
        if ( SSLProperties < 0 )
        {
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L"GenerateSSLProperties() failed with %08x during SetConfigProperties()\n",
            (unsigned int)SSLProperties);
LABEL_32:
          v13 = 0;
          goto LABEL_42;
        }
        v20 = GetSSLProperties(a4, (struct SSL_DATA *)v36);
        if ( v20 < 0 )
        {
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L"GetSSLProperties() failed with %08x during SetConfigProperties()\n",
            (unsigned int)v20);
          goto LABEL_32;
        }
        v17 = 1;
      }
      SockAddress = GetSockAddress(Str, &v33);
      v7 = v33;
      v13 = SockAddress;
      if ( SockAddress < 0 )
        goto LABEL_54;
      v22 = SetHttpSysSSLData(v33, (struct SSL_DATA *)v36, a4, Str);
      if ( v22 >= 0 )
      {
        v13 = ABO_WRAPPER::AddBinding(v23, Str);
        if ( v13 < 0 )
          goto LABEL_54;
        goto LABEL_42;
      }
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"SetHttpSysSSLData() failed with %08x during SetConfigProperties()\n",
        (unsigned int)v22);
      goto LABEL_32;
    }
  }
LABEL_54:
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v7 )
    FreeAddrInfoW(v7);
  MULTISZ::~MULTISZ((MULTISZ *)v35);
  SSL_DATA::~SSL_DATA((SSL_DATA *)v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800165d0  mov     [rsp-8+arg_0], rbx
0x1800165d5  push    rbp
0x1800165d6  push    rsi
0x1800165d7  push    rdi
0x1800165d8  push    r12
0x1800165da  push    r13
0x1800165dc  push    r14
0x1800165de  push    r15
0x1800165e0  lea     rbp, [rsp-0A0h]
0x1800165e8  sub     rsp, 1A0h
0x1800165ef  mov     rax, cs:__security_cookie
0x1800165f6  xor     rax, rsp
0x1800165f9  mov     [rbp+0D0h+var_40], rax
0x180016600  mov     rdi, [rbp+0D0h+arg_20]
0x180016607  lea     rcx, [rbp+0D0h+var_130]; this
0x18001660b  xor     r15d, r15d
0x18001660e  mov     r12, r9
0x180016611  mov     [rsp+1D0h+var_190], r15d
0x180016616  mov     esi, r15d
0x180016619  mov     [rsp+1D0h+var_188], r15
0x18001661e  mov     r14, r8
0x180016621  mov     [rsp+1D0h+var_198], r15
0x180016626  mov     rbx, rdx
0x180016629  mov     [rsp+1D0h+String1], r15
0x18001662e  mov     [rsp+1D0h+Str], r15
0x180016633  mov     [rsp+1D0h+var_180], r15
0x180016638  call    ??0SSL_DATA@@QEAA@XZ; SSL_DATA::SSL_DATA(void)
0x18001663d  lea     rcx, [rsp+1D0h+var_170]
0x180016642  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180016648  test    rdi, rdi
0x18001664b  jz      loc_180016A38
0x180016651  test    r14, r14
0x180016654  jz      loc_180016A38
0x18001665a  test    rbx, rbx
0x18001665d  jz      loc_180016A38
0x180016663  test    r12, r12
0x180016666  jz      loc_180016A38
0x18001666c  mov     eax, [rbx+90h]
0x180016672  cmp     eax, 3FFh
0x180016677  jnz     short loc_180016682
0x180016679  lea     r13, aHttp; "http"
0x180016680  jmp     short loc_18001669A
0x180016682  cmp     eax, 7E5h
0x180016687  jnz     loc_180016A31
0x18001668d  lea     r13, aHttps; "https"
0x180016694  mov     r15d, 1
0x18001669a  mov     rax, [rdi]
0x18001669d  lea     rdx, [rsp+1D0h+var_188]
0x1800166a2  mov     rcx, rdi
0x1800166a5  mov     rax, [rax+28h]
0x1800166a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ae  xor     edi, edi
0x1800166b0  mov     ebx, eax
0x1800166b2  test    eax, eax
0x1800166b4  js      loc_180016A3D
0x1800166ba  mov     rcx, [rsp+1D0h+var_188]
0x1800166bf  lea     rdx, [rsp+1D0h+var_190]
0x1800166c4  mov     rax, [rcx]
0x1800166c7  mov     rax, [rax+18h]
0x1800166cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166d0  mov     ebx, eax
0x1800166d2  test    eax, eax
0x1800166d4  js      loc_180016A3D
0x1800166da  lea     rcx, [rsp+1D0h+var_170]
0x1800166df  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x1800166e5  xor     eax, eax
0x1800166e7  cmp     [rsp+1D0h+var_190], eax
0x1800166eb  jbe     loc_180016805
0x1800166f1  mov     rcx, [rsp+1D0h+var_188]
0x1800166f6  lea     r8, [rsp+1D0h+var_198]
0x1800166fb  mov     edx, edi
0x1800166fd  mov     rax, [rcx]
0x180016700  mov     rax, [rax+20h]
0x180016704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016709  xor     edx, edx
0x18001670b  mov     ebx, eax
0x18001670d  test    eax, eax
0x18001670f  js      loc_180016A3D
0x180016715  mov     rcx, [rsp+1D0h+var_198]
0x18001671a  lea     r8, [rsp+1D0h+String1]
0x18001671f  mov     [rsp+1D0h+var_1B0], rdx
0x180016724  xor     r9d, r9d
0x180016727  lea     rdx, aProtocol; "protocol"
0x18001672e  mov     rax, [rcx]
0x180016731  mov     rax, [rax+40h]
0x180016735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673a  mov     ebx, eax
0x18001673c  test    eax, eax
0x18001673e  js      loc_180016A3D
0x180016744  mov     rcx, [rsp+1D0h+String1]; String1
0x180016749  mov     rdx, r13; String2
0x18001674c  call    cs:__imp__wcsicmp
0x180016752  xor     edx, edx
0x180016754  test    eax, eax
0x180016756  jnz     loc_1800167E1
0x18001675c  test    r15d, r15d
0x18001675f  jz      short loc_1800167B8
0x180016761  mov     rcx, [rsp+1D0h+var_198]
0x180016766  lea     r8, [rsp+1D0h+Str]
0x18001676b  mov     [rsp+1D0h+var_1B0], rdx
0x180016770  xor     r9d, r9d
0x180016773  lea     rdx, aBindinginforma; "bindingInformation"
0x18001677a  mov     rax, [rcx]
0x18001677d  mov     rax, [rax+40h]
0x180016781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016786  mov     ebx, eax
0x180016788  xor     eax, eax
0x18001678a  test    ebx, ebx
0x18001678c  js      loc_180016A3D
0x180016792  mov     rdx, [rsp+1D0h+Str]
0x180016797  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001679b  inc     r8
0x18001679e  cmp     [rdx+r8*2], ax
0x1800167a3  jnz     short loc_18001679B
0x1800167a5  lea     rcx, [rsp+1D0h+var_170]
0x1800167aa  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBGK@Z; MULTISZ::Append(ushort const *,ulong)
0x1800167b0  test    eax, eax
0x1800167b2  jz      loc_180016909
0x1800167b8  mov     rcx, [rsp+1D0h+var_188]
0x1800167bd  xor     r8d, r8d
0x1800167c0  mov     edx, edi
0x1800167c2  mov     rax, [rcx]
0x1800167c5  mov     rax, [rax+40h]
0x1800167c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ce  mov     ebx, eax
0x1800167d0  test    eax, eax
0x1800167d2  js      loc_180016A3D
0x1800167d8  or      eax, 0FFFFFFFFh
0x1800167db  add     edi, eax
0x1800167dd  add     [rsp+1D0h+var_190], eax
0x1800167e1  mov     rcx, [rsp+1D0h+var_198]
0x1800167e6  mov     rax, [rcx]
0x1800167e9  mov     rax, [rax+10h]
0x1800167ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f2  xor     eax, eax
0x1800167f4  inc     edi
0x1800167f6  mov     [rsp+1D0h+var_198], rax
0x1800167fb  cmp     edi, [rsp+1D0h+var_190]
0x1800167ff  jb      loc_1800166F1
0x180016805  lea     rcx, [r14+10h]
0x180016809  mov     edi, eax
0x18001680b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180016811  xor     r14d, r14d
0x180016814  mov     rcx, [rax+18h]
0x180016818  mov     [rsp+1D0h+Str], rcx
0x18001681d  cmp     [rcx], r14w
0x180016821  jz      loc_1800169E8
0x180016827  mov     rcx, [rsp+1D0h+var_188]
0x18001682c  lea     r8, [rsp+1D0h+var_198]
0x180016831  lea     rdx, aBinding; "binding"
0x180016838  mov     rax, [rcx]
0x18001683b  mov     rax, [rax+30h]
0x18001683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016844  mov     ebx, eax
0x180016846  test    eax, eax
0x180016848  js      loc_180016A40
0x18001684e  mov     rcx, [rsp+1D0h+var_198]
0x180016853  lea     rdx, aProtocol; "protocol"
0x18001685a  xor     r9d, r9d
0x18001685d  mov     r8, r13
0x180016860  mov     rax, [rcx]
0x180016863  mov     rax, [rax+80h]
0x18001686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001686f  mov     ebx, eax
0x180016871  test    eax, eax
0x180016873  js      loc_180016A40
0x180016879  mov     rcx, [rsp+1D0h+var_198]
0x18001687e  lea     rdx, aBindinginforma; "bindingInformation"
0x180016885  mov     r8, [rsp+1D0h+Str]
0x18001688a  xor     r9d, r9d
0x18001688d  mov     rax, [rcx]
0x180016890  mov     rax, [rax+80h]
0x180016897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001689c  mov     ebx, eax
0x18001689e  test    eax, eax
0x1800168a0  js      loc_180016A40
0x1800168a6  mov     rcx, [rsp+1D0h+var_188]
0x1800168ab  xor     r9d, r9d
0x1800168ae  mov     rdx, [rsp+1D0h+var_198]
0x1800168b3  or      r8d, 0FFFFFFFFh
0x1800168b7  mov     rax, [rcx]
0x1800168ba  mov     rax, [rax+38h]
0x1800168be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c3  mov     ebx, eax
0x1800168c5  test    eax, eax
0x1800168c7  js      loc_180016A40
0x1800168cd  test    r15d, r15d
0x1800168d0  jz      loc_18001699E
0x1800168d6  test    edi, edi
0x1800168d8  jnz     short loc_180016948
0x1800168da  mov     rdx, [rsp+1D0h+Str]; unsigned __int16 *
0x1800168df  mov     rcx, r12; struct ABO_NODE *
0x1800168e2  call    ?GenerateSSLProperties@@YAJPEAVABO_NODE@@PEBG@Z; GenerateSSLProperties(ABO_NODE *,ushort const *)
0x1800168e7  test    eax, eax
0x1800168e9  jns     short loc_18001692A
0x1800168eb  lea     rdx, aGeneratesslpro_0; "GenerateSSLProperties() failed with %08"...
0x1800168f2  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800168f9  mov     r8d, eax
0x1800168fc  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180016901  mov     ebx, r14d
0x180016904  jmp     loc_18001699E
0x180016909  call    cs:__imp_GetLastError
0x18001690f  xor     r14d, r14d
0x180016912  mov     ebx, eax
0x180016914  test    eax, eax
0x180016916  jle     loc_180016A40
0x18001691c  movzx   ebx, ax
0x18001691f  or      ebx, 80070000h
0x180016925  jmp     loc_180016A40
0x18001692a  lea     rdx, [rbp+0D0h+var_130]; struct SSL_DATA *
0x18001692e  mov     rcx, r12; struct ABO_NODE *
0x180016931  call    ?GetSSLProperties@@YAJPEAVABO_NODE@@PEAUSSL_DATA@@@Z; GetSSLProperties(ABO_NODE *,SSL_DATA *)
0x180016936  test    eax, eax
0x180016938  jns     short loc_180016943
0x18001693a  lea     rdx, aGetsslproperti_0; "GetSSLProperties() failed with %08x dur"...
0x180016941  jmp     short loc_1800168F2
0x180016943  mov     edi, 1
0x180016948  mov     rcx, [rsp+1D0h+Str]; Str
0x18001694d  lea     rdx, [rsp+1D0h+var_180]; struct addrinfoW **
0x180016952  call    ?GetSockAddress@@YAJPEBGPEAPEAUaddrinfoW@@@Z; GetSockAddress(ushort const *,addrinfoW * *)
0x180016957  mov     rsi, [rsp+1D0h+var_180]
0x18001695c  mov     ebx, eax
0x18001695e  test    eax, eax
0x180016960  js      loc_180016A40
0x180016966  mov     r9, [rsp+1D0h+Str]; unsigned __int16 *
0x18001696b  lea     rdx, [rbp+0D0h+var_130]; struct SSL_DATA *
0x18001696f  mov     r8, r12; struct ABO_NODE *
0x180016972  mov     rcx, rsi; struct addrinfoW *
0x180016975  call    ?SetHttpSysSSLData@@YAJPEAUaddrinfoW@@PEAUSSL_DATA@@PEAVABO_NODE@@PEBG@Z; SetHttpSysSSLData(addrinfoW *,SSL_DATA *,ABO_NODE *,ushort const *)
0x18001697a  test    eax, eax
0x18001697c  jns     short loc_18001698A
0x18001697e  lea     rdx, aSethttpsysssld; "SetHttpSysSSLData() failed with %08x du"...
0x180016985  jmp     loc_1800168F2
0x18001698a  mov     rdx, [rsp+1D0h+Str]; unsigned __int16 *
0x18001698f  call    ?AddBinding@ABO_WRAPPER@@QEAAJPEBG@Z; ABO_WRAPPER::AddBinding(ushort const *)
0x180016994  mov     ebx, eax
0x180016996  test    eax, eax
0x180016998  js      loc_180016A40
0x18001699e  mov     rcx, [rsp+1D0h+Str]
0x1800169a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800169a7  inc     rax
0x1800169aa  cmp     [rcx+rax*2], r14w
0x1800169af  jnz     short loc_1800169A7
0x1800169b1  lea     rdx, [rcx+2]
0x1800169b5  mov     rcx, [rsp+1D0h+var_198]
0x1800169ba  lea     rdx, [rdx+rax*2]
0x1800169be  mov     [rsp+1D0h+Str], rdx
0x1800169c3  test    rcx, rcx
0x1800169c6  jz      short loc_1800169DE
0x1800169c8  mov     rax, [rcx]
0x1800169cb  mov     rax, [rax+10h]
0x1800169cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d4  mov     rdx, [rsp+1D0h+Str]
0x1800169d9  mov     [rsp+1D0h+var_198], r14
0x1800169de  cmp     [rdx], r14w
0x1800169e2  jnz     loc_180016827
0x1800169e8  lea     rcx, [rsp+1D0h+var_170]
0x1800169ed  call    cs:__imp_?IsEmpty@MULTISZ@@QEBAHXZ; MULTISZ::IsEmpty(void)
0x1800169f3  test    eax, eax
0x1800169f5  jnz     short loc_180016A40
0x1800169f7  lea     rcx, [rsp+1D0h+var_170]
0x1800169fc  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180016a02  mov     [rsp+1D0h+Str], rax
0x180016a07  mov     rdx, rax; unsigned __int16 *
0x180016a0a  call    ?RemoveBinding@ABO_WRAPPER@@QEAAJPEBG@Z; ABO_WRAPPER::RemoveBinding(ushort const *)
0x180016a0f  mov     ebx, eax
0x180016a11  test    eax, eax
0x180016a13  js      short loc_180016A40
0x180016a15  mov     rdx, [rsp+1D0h+Str]
0x180016a1a  lea     rcx, [rsp+1D0h+var_170]
0x180016a1f  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180016a25  mov     [rsp+1D0h+Str], rax
0x180016a2a  test    rax, rax
0x180016a2d  jnz     short loc_180016A07
0x180016a2f  jmp     short loc_180016A40
0x180016a31  mov     ebx, 80070032h
0x180016a36  jmp     short loc_180016A3D
0x180016a38  mov     ebx, 80070057h
0x180016a3d  xor     r14d, r14d
0x180016a40  mov     rcx, [rsp+1D0h+var_188]
0x180016a45  test    rcx, rcx
0x180016a48  jz      short loc_180016A5B
0x180016a4a  mov     rax, [rcx]
0x180016a4d  mov     rax, [rax+10h]
0x180016a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a56  mov     [rsp+1D0h+var_188], r14
0x180016a5b  mov     rcx, [rsp+1D0h+var_198]
0x180016a60  test    rcx, rcx
0x180016a63  jz      short loc_180016A76
0x180016a65  mov     rax, [rcx]
0x180016a68  mov     rax, [rax+10h]
0x180016a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a71  mov     [rsp+1D0h+var_198], r14
0x180016a76  test    rsi, rsi
0x180016a79  jz      short loc_180016A84
0x180016a7b  mov     rcx, rsi; pAddrInfo
0x180016a7e  call    cs:__imp_FreeAddrInfoW
0x180016a84  lea     rcx, [rsp+1D0h+var_170]
0x180016a89  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180016a8f  lea     rcx, [rbp+0D0h+var_130]; this
  ... truncated ...
```

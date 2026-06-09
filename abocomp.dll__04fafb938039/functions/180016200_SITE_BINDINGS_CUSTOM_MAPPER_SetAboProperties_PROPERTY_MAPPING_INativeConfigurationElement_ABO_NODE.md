# SITE_BINDINGS_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180016200`
- end: `0x1800165bc`
- name: `?SetAboProperties@SITE_BINDINGS_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(SITE_BINDINGS_CUSTOM_MAPPER *this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f90`
- `0x180003460`
- `0x18000a6fc`
- `0x18000b178`
- `0x180016200`
- `0x18002735c`
- `0x1800273c4`
- `0x1800278cc`
- `0x180028654`
- `0x180028c64`
- `0x180028f20`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001638c`
- `msvcrt!_wcsicmp` at `0x18001646c`
- `msvcrt!_wcsicmp` at `0x18001638c`
- `msvcrt!_wcsicmp` at `0x18001646c`
- `WS2_32!FreeAddrInfoW` at `0x180016577`
- `WS2_32!FreeAddrInfoW` at `0x180016577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001651d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001651d`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x1800164b8`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x1800164b8`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180016259`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180016259`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800164fe`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800164fe`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800163a3`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001647f`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800163a3`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001647f`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800164f0`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800164f0`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001658a`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001658a`

## string_xrefs

- `0x18001630e`: `protocol`
- `0x1800163c7`: `GenerateSSLProperties() failed with %08x during SetAboProperties()\n`
- `0x1800163f5`: `GetSSLProperties() failed with %08x during SetAboProperties()\n`
- `0x18001643a`: `SetHttpSysSSLData() failed with %08x during SetAboProperties()\n`

## pseudocode

```c
__int64 __fastcall SITE_BINDINGS_CUSTOM_MAPPER::SetAboProperties(
        SITE_BINDINGS_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  struct addrinfoW *v7; // rdi
  signed int v8; // ebx
  int v9; // r15d
  unsigned int i; // esi
  int v11; // eax
  int SSLProperties; // eax
  int v13; // eax
  int SockAddress; // eax
  int v15; // eax
  ABO_WRAPPER *v16; // rcx
  DWORD v17; // eax
  signed int LastError; // eax
  wchar_t *Str; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  struct addrinfoW *v25; // [rsp+58h] [rbp-A8h] BYREF
  struct _METADATA_RECORD v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v28[240]; // [rsp+C0h] [rbp-40h] BYREF

  v21 = 0;
  v23 = 0;
  v22 = 0;
  String1 = 0;
  Str = 0;
  MULTISZ::MULTISZ((MULTISZ *)v27);
  v25 = 0;
  v7 = 0;
  SSL_DATA::SSL_DATA((SSL_DATA *)v28);
  if ( a2 && a3 && a4 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v23);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(v23, &v21);
      if ( v8 >= 0 )
      {
        v9 = 0;
        for ( i = 0; i < v21; ++i )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 32LL))(v23, i, &v22);
          if ( v8 < 0 )
            goto LABEL_38;
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                 v22,
                 L"protocol",
                 &String1,
                 0,
                 0);
          if ( v8 < 0 )
            goto LABEL_38;
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                 v22,
                 L"bindingInformation",
                 &Str,
                 0,
                 0);
          if ( v8 < 0 )
            goto LABEL_38;
          if ( *Str == 42 )
            ++Str;
          v11 = *((_DWORD *)a2 + 36);
          if ( v11 == 2021 )
          {
            if ( !_wcsicmp(String1, L"https") )
            {
              if ( !MULTISZ::Append((MULTISZ *)v27, Str) )
                goto LABEL_35;
              if ( !v9 )
              {
                SSLProperties = GenerateSSLProperties(a4, Str);
                if ( SSLProperties < 0 )
                {
                  ABO_MAPPER_LOG::WriteLogEntry(
                    g_pAboLog,
                    L"GenerateSSLProperties() failed with %08x during SetAboProperties()\n",
                    (unsigned int)SSLProperties);
LABEL_18:
                  v8 = 0;
                  goto LABEL_30;
                }
                v13 = GetSSLProperties(a4, (struct SSL_DATA *)v28);
                if ( v13 < 0 )
                {
                  ABO_MAPPER_LOG::WriteLogEntry(
                    g_pAboLog,
                    L"GetSSLProperties() failed with %08x during SetAboProperties()\n",
                    (unsigned int)v13);
                  goto LABEL_18;
                }
                v9 = 1;
              }
              SockAddress = GetSockAddress(Str, &v25);
              v7 = v25;
              v8 = SockAddress;
              if ( SockAddress < 0 )
                goto LABEL_38;
              v15 = SetHttpSysSSLData(v25, (struct SSL_DATA *)v28, a4, Str);
              if ( v15 >= 0 )
              {
                v8 = ABO_WRAPPER::AddBinding(v16, Str);
                if ( v8 < 0 )
                  goto LABEL_38;
                goto LABEL_30;
              }
              ABO_MAPPER_LOG::WriteLogEntry(
                g_pAboLog,
                L"SetHttpSysSSLData() failed with %08x during SetAboProperties()\n",
                (unsigned int)v15);
              goto LABEL_18;
            }
          }
          else if ( v11 == 1023 && !_wcsicmp(String1, L"http") && !MULTISZ::Append((MULTISZ *)v27, Str) )
          {
LABEL_35:
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_38;
          }
LABEL_30:
          if ( v22 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v22 = 0;
          }
        }
        if ( MULTISZ::QueryStringCount((MULTISZ *)v27) )
        {
          v17 = *((_DWORD *)a2 + 36);
          v26.dwMDAttributes = 0;
          v26.dwMDUserType = 1;
          *(&v26.dwMDDataLen + 1) = 0;
          *(_QWORD *)&v26.dwMDDataTag = 0;
          v26.dwMDIdentifier = v17;
          v26.dwMDDataType = 5;
          v26.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v27);
          v26.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v27);
          v8 = ABO_NODE::SetData(a4, &v26, 1);
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_38:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v7 )
    FreeAddrInfoW(v7);
  SSL_DATA::~SSL_DATA((SSL_DATA *)v28);
  MULTISZ::~MULTISZ((MULTISZ *)v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016200  mov     [rsp-8+arg_0], rbx
0x180016205  push    rbp
0x180016206  push    rsi
0x180016207  push    rdi
0x180016208  push    r12
0x18001620a  push    r13
0x18001620c  push    r14
0x18001620e  push    r15
0x180016210  lea     rbp, [rsp-0C0h]
0x180016218  sub     rsp, 1C0h
0x18001621f  mov     rax, cs:__security_cookie
0x180016226  xor     rax, rsp
0x180016229  mov     [rbp+0F0h+var_40], rax
0x180016230  xor     r12d, r12d
0x180016233  lea     rcx, [rbp+0F0h+var_168]
0x180016237  mov     [rsp+1F0h+var_1B8], r12d
0x18001623c  mov     r14, r9
0x18001623f  mov     [rsp+1F0h+var_1A8], r12
0x180016244  mov     rbx, r8
0x180016247  mov     [rsp+1F0h+var_1B0], r12
0x18001624c  mov     r13, rdx
0x18001624f  mov     [rsp+1F0h+String1], r12
0x180016254  mov     [rsp+1F0h+Str], r12
0x180016259  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001625f  lea     rcx, [rbp+0F0h+var_130]; this
0x180016263  mov     [rsp+1F0h+var_198], r12
0x180016268  mov     edi, r12d
0x18001626b  call    ??0SSL_DATA@@QEAA@XZ; SSL_DATA::SSL_DATA(void)
0x180016270  test    r13, r13
0x180016273  jz      loc_180016534
0x180016279  test    rbx, rbx
0x18001627c  jz      loc_180016534
0x180016282  test    r14, r14
0x180016285  jz      loc_180016534
0x18001628b  mov     rax, [rbx]
0x18001628e  lea     rdx, [rsp+1F0h+var_1A8]
0x180016293  mov     rcx, rbx
0x180016296  mov     rax, [rax+28h]
0x18001629a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001629f  mov     ebx, eax
0x1800162a1  test    eax, eax
0x1800162a3  js      loc_180016539
0x1800162a9  mov     rcx, [rsp+1F0h+var_1A8]
0x1800162ae  lea     rdx, [rsp+1F0h+var_1B8]
0x1800162b3  mov     rax, [rcx]
0x1800162b6  mov     rax, [rax+18h]
0x1800162ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162bf  mov     ebx, eax
0x1800162c1  test    eax, eax
0x1800162c3  js      loc_180016539
0x1800162c9  mov     r15d, r12d
0x1800162cc  mov     esi, r12d
0x1800162cf  cmp     [rsp+1F0h+var_1B8], r12d
0x1800162d4  jbe     loc_1800164B4
0x1800162da  mov     rcx, [rsp+1F0h+var_1A8]
0x1800162df  lea     r8, [rsp+1F0h+var_1B0]
0x1800162e4  mov     edx, esi
0x1800162e6  mov     rax, [rcx]
0x1800162e9  mov     rax, [rax+20h]
0x1800162ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f2  mov     ebx, eax
0x1800162f4  test    eax, eax
0x1800162f6  js      loc_180016539
0x1800162fc  mov     rcx, [rsp+1F0h+var_1B0]
0x180016301  lea     r8, [rsp+1F0h+String1]
0x180016306  xor     r9d, r9d
0x180016309  mov     [rsp+1F0h+var_1D0], r12
0x18001630e  lea     rdx, aProtocol; "protocol"
0x180016315  mov     rax, [rcx]
0x180016318  mov     rax, [rax+40h]
0x18001631c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016321  mov     ebx, eax
0x180016323  test    eax, eax
0x180016325  js      loc_180016539
0x18001632b  mov     rcx, [rsp+1F0h+var_1B0]
0x180016330  lea     r8, [rsp+1F0h+Str]
0x180016335  xor     r9d, r9d
0x180016338  mov     [rsp+1F0h+var_1D0], r12
0x18001633d  lea     rdx, aBindinginforma; "bindingInformation"
0x180016344  mov     rax, [rcx]
0x180016347  mov     rax, [rax+40h]
0x18001634b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016350  mov     ebx, eax
0x180016352  test    eax, eax
0x180016354  js      loc_180016539
0x18001635a  mov     rax, [rsp+1F0h+Str]
0x18001635f  cmp     word ptr [rax], 2Ah ; '*'
0x180016363  jnz     short loc_18001636E
0x180016365  add     rax, 2
0x180016369  mov     [rsp+1F0h+Str], rax
0x18001636e  mov     eax, [r13+90h]
0x180016375  cmp     eax, 7E5h
0x18001637a  jnz     loc_180016459
0x180016380  mov     rcx, [rsp+1F0h+String1]; String1
0x180016385  lea     rdx, aHttps; "https"
0x18001638c  call    cs:__imp__wcsicmp
0x180016392  test    eax, eax
0x180016394  jnz     loc_18001648D
0x18001639a  mov     rdx, [rsp+1F0h+Str]
0x18001639f  lea     rcx, [rbp+0F0h+var_168]
0x1800163a3  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800163a9  test    eax, eax
0x1800163ab  jz      loc_18001651D
0x1800163b1  test    r15d, r15d
0x1800163b4  jnz     short loc_180016404
0x1800163b6  mov     rdx, [rsp+1F0h+Str]; unsigned __int16 *
0x1800163bb  mov     rcx, r14; struct ABO_NODE *
0x1800163be  call    ?GenerateSSLProperties@@YAJPEAVABO_NODE@@PEBG@Z; GenerateSSLProperties(ABO_NODE *,ushort const *)
0x1800163c3  test    eax, eax
0x1800163c5  jns     short loc_1800163E5
0x1800163c7  lea     rdx, aGeneratesslpro; "GenerateSSLProperties() failed with %08"...
0x1800163ce  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800163d5  mov     r8d, eax
0x1800163d8  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800163dd  mov     ebx, r12d
0x1800163e0  jmp     loc_18001648D
0x1800163e5  lea     rdx, [rbp+0F0h+var_130]; struct SSL_DATA *
0x1800163e9  mov     rcx, r14; struct ABO_NODE *
0x1800163ec  call    ?GetSSLProperties@@YAJPEAVABO_NODE@@PEAUSSL_DATA@@@Z; GetSSLProperties(ABO_NODE *,SSL_DATA *)
0x1800163f1  test    eax, eax
0x1800163f3  jns     short loc_1800163FE
0x1800163f5  lea     rdx, aGetsslproperti; "GetSSLProperties() failed with %08x dur"...
0x1800163fc  jmp     short loc_1800163CE
0x1800163fe  mov     r15d, 1
0x180016404  mov     rcx, [rsp+1F0h+Str]; Str
0x180016409  lea     rdx, [rsp+1F0h+var_198]; struct addrinfoW **
0x18001640e  call    ?GetSockAddress@@YAJPEBGPEAPEAUaddrinfoW@@@Z; GetSockAddress(ushort const *,addrinfoW * *)
0x180016413  mov     rdi, [rsp+1F0h+var_198]
0x180016418  mov     ebx, eax
0x18001641a  test    eax, eax
0x18001641c  js      loc_180016539
0x180016422  mov     r9, [rsp+1F0h+Str]; unsigned __int16 *
0x180016427  lea     rdx, [rbp+0F0h+var_130]; struct SSL_DATA *
0x18001642b  mov     r8, r14; struct ABO_NODE *
0x18001642e  mov     rcx, rdi; struct addrinfoW *
0x180016431  call    ?SetHttpSysSSLData@@YAJPEAUaddrinfoW@@PEAUSSL_DATA@@PEAVABO_NODE@@PEBG@Z; SetHttpSysSSLData(addrinfoW *,SSL_DATA *,ABO_NODE *,ushort const *)
0x180016436  test    eax, eax
0x180016438  jns     short loc_180016443
0x18001643a  lea     rdx, aSethttpsysssld_0; "SetHttpSysSSLData() failed with %08x du"...
0x180016441  jmp     short loc_1800163CE
0x180016443  mov     rdx, [rsp+1F0h+Str]; unsigned __int16 *
0x180016448  call    ?AddBinding@ABO_WRAPPER@@QEAAJPEBG@Z; ABO_WRAPPER::AddBinding(ushort const *)
0x18001644d  mov     ebx, eax
0x18001644f  test    eax, eax
0x180016451  js      loc_180016539
0x180016457  jmp     short loc_18001648D
0x180016459  cmp     eax, 3FFh
0x18001645e  jnz     short loc_18001648D
0x180016460  mov     rcx, [rsp+1F0h+String1]; String1
0x180016465  lea     rdx, aHttp; "http"
0x18001646c  call    cs:__imp__wcsicmp
0x180016472  test    eax, eax
0x180016474  jnz     short loc_18001648D
0x180016476  mov     rdx, [rsp+1F0h+Str]
0x18001647b  lea     rcx, [rbp+0F0h+var_168]
0x18001647f  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180016485  test    eax, eax
0x180016487  jz      loc_18001651D
0x18001648d  mov     rcx, [rsp+1F0h+var_1B0]
0x180016492  test    rcx, rcx
0x180016495  jz      short loc_1800164A8
0x180016497  mov     rax, [rcx]
0x18001649a  mov     rax, [rax+10h]
0x18001649e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164a3  mov     [rsp+1F0h+var_1B0], r12
0x1800164a8  inc     esi
0x1800164aa  cmp     esi, [rsp+1F0h+var_1B8]
0x1800164ae  jb      loc_1800162DA
0x1800164b4  lea     rcx, [rbp+0F0h+var_168]
0x1800164b8  call    cs:__imp_?QueryStringCount@MULTISZ@@QEBAKXZ; MULTISZ::QueryStringCount(void)
0x1800164be  test    eax, eax
0x1800164c0  jz      short loc_180016539
0x1800164c2  mov     eax, [r13+90h]
0x1800164c9  lea     rcx, [rbp+0F0h+var_168]
0x1800164cd  mov     ebx, 1
0x1800164d2  mov     [rsp+1F0h+var_190.dwMDAttributes], r12d
0x1800164d7  mov     [rsp+1F0h+var_190.dwMDUserType], ebx
0x1800164db  mov     dword ptr [rsp+1F0h+var_190+14h], r12d
0x1800164e0  mov     qword ptr [rbp+0F0h+var_190.dwMDDataTag], r12
0x1800164e4  mov     [rsp+1F0h+var_190.dwMDIdentifier], eax
0x1800164e8  mov     [rsp+1F0h+var_190.dwMDDataType], 5
0x1800164f0  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x1800164f6  lea     rcx, [rbp+0F0h+var_168]
0x1800164fa  mov     [rsp+1F0h+var_190.dwMDDataLen], eax
0x1800164fe  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180016504  mov     r8d, ebx; int
0x180016507  lea     rdx, [rsp+1F0h+var_190]; struct _METADATA_RECORD *
0x18001650c  mov     rcx, r14; this
0x18001650f  mov     [rsp+1F0h+var_190.pbMDData], rax
0x180016514  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x180016519  mov     ebx, eax
0x18001651b  jmp     short loc_180016539
0x18001651d  call    cs:__imp_GetLastError
0x180016523  mov     ebx, eax
0x180016525  test    eax, eax
0x180016527  jle     short loc_180016539
0x180016529  movzx   ebx, ax
0x18001652c  or      ebx, 80070000h
0x180016532  jmp     short loc_180016539
0x180016534  mov     ebx, 80070057h
0x180016539  mov     rcx, [rsp+1F0h+var_1A8]
0x18001653e  test    rcx, rcx
0x180016541  jz      short loc_180016554
0x180016543  mov     rax, [rcx]
0x180016546  mov     rax, [rax+10h]
0x18001654a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654f  mov     [rsp+1F0h+var_1A8], r12
0x180016554  mov     rcx, [rsp+1F0h+var_1B0]
0x180016559  test    rcx, rcx
0x18001655c  jz      short loc_18001656F
0x18001655e  mov     rax, [rcx]
0x180016561  mov     rax, [rax+10h]
0x180016565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001656a  mov     [rsp+1F0h+var_1B0], r12
0x18001656f  test    rdi, rdi
0x180016572  jz      short loc_18001657D
0x180016574  mov     rcx, rdi; pAddrInfo
0x180016577  call    cs:__imp_FreeAddrInfoW
0x18001657d  lea     rcx, [rbp+0F0h+var_130]; this
0x180016581  call    ??1SSL_DATA@@QEAA@XZ; SSL_DATA::~SSL_DATA(void)
0x180016586  lea     rcx, [rbp+0F0h+var_168]
0x18001658a  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180016590  mov     eax, ebx
0x180016592  mov     rcx, [rbp+0F0h+var_40]
0x180016599  xor     rcx, rsp; StackCookie
0x18001659c  call    __security_check_cookie
0x1800165a1  mov     rbx, [rsp+1F0h+arg_0]
0x1800165a9  add     rsp, 1C0h
0x1800165b0  pop     r15
0x1800165b2  pop     r14
0x1800165b4  pop     r13
0x1800165b6  pop     r12
0x1800165b8  pop     rdi
0x1800165b9  pop     rsi
0x1800165ba  pop     rbp
0x1800165bb  retn
```

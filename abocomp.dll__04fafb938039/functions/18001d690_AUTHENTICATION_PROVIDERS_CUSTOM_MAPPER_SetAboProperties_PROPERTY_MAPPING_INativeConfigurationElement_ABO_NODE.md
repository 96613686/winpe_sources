# AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001d690`
- end: `0x18001d9a0`
- name: `?SetAboProperties@AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `784`
- prototype: `int(AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001d690`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001d8ba`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001d8ba`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d702`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d702`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d979`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d979`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8ab`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d8ab`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d82b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d844`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d82b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d844`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d816`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001d816`

## string_xrefs

- `0x18001d733`: `system.webServer/security/authentication/windowsAuthentication`

## pseudocode

```c
__int64 __fastcall AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER::SetAboProperties(
        AUTHENTICATION_PROVIDERS_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  int MergedConfigElement; // ebx
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v16; // [rsp+58h] [rbp-A8h] BYREF
  struct _METADATA_RECORD v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[56]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v19[256]; // [rsp+C0h] [rbp-40h] BYREF

  v15 = 0;
  v11 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v16 = 0;
  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v18, v19, 0x100u);
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/security/authentication/windowsAuthentication",
                            &v15,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v15 + 32LL))(
                              v15,
                              L"providers",
                              &v14);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 40LL))(v14, &v13);
        if ( MergedConfigElement >= 0 )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v13 + 24LL))(v13, &v12);
          if ( MergedConfigElement >= 0 )
          {
            v8 = 0;
            if ( v12 )
            {
              while ( 1 )
              {
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 32LL))(
                                        v13,
                                        v8,
                                        &v11);
                if ( MergedConfigElement < 0 )
                  break;
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
                                        v11,
                                        L"value",
                                        &v16,
                                        0,
                                        0);
                if ( MergedConfigElement < 0 )
                  break;
                if ( !STRU::IsEmpty((STRU *)v18) )
                {
                  MergedConfigElement = STRU::Append((STRU *)v18, L",");
                  if ( MergedConfigElement < 0 )
                    break;
                }
                MergedConfigElement = STRU::Append((STRU *)v18, v16);
                if ( MergedConfigElement < 0 )
                  break;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                ++v8;
                v11 = 0;
                if ( v8 >= v12 )
                  goto LABEL_15;
              }
            }
            else
            {
LABEL_15:
              v17.dwMDIdentifier = *((_DWORD *)a2 + 36);
              v17.dwMDUserType = *((_DWORD *)a2 + 37);
              v17.dwMDDataType = *((_DWORD *)a2 + 38);
              v17.dwMDAttributes = *((_DWORD *)a2 + 39);
              *(&v17.dwMDDataLen + 1) = 0;
              *(_QWORD *)&v17.dwMDDataTag = 0;
              v17.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v18);
              v17.dwMDDataLen = STRU::QueryCB((STRU *)v18) + 2;
              MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v17, a2);
            }
          }
        }
      }
    }
  }
  else
  {
    MergedConfigElement = -2147024809;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  v9 = v11;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v9 = 0;
    v11 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v9 = v11;
    v14 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
    v9 = v11;
    v15 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v11 = 0;
  }
  STRU::~STRU((STRU *)v18);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001d690  push    rbp
0x18001d692  push    rbx
0x18001d693  push    rsi
0x18001d694  push    rdi
0x18001d695  push    r14
0x18001d697  push    r15
0x18001d699  lea     rbp, [rsp-1D8h]
0x18001d6a1  sub     rsp, 2D8h
0x18001d6a8  mov     rax, cs:__security_cookie
0x18001d6af  xor     rax, rsp
0x18001d6b2  mov     [rbp+200h+var_40], rax
0x18001d6b9  xor     r15d, r15d
0x18001d6bc  lea     rcx, [rbp+200h+var_240]; void *
0x18001d6c0  mov     rbx, r8
0x18001d6c3  mov     [rsp+300h+var_2B0], r15
0x18001d6c8  mov     rsi, rdx
0x18001d6cb  mov     [rsp+300h+var_2D0], r15
0x18001d6d0  xor     edx, edx; Val
0x18001d6d2  mov     [rsp+300h+var_2B8], r15
0x18001d6d7  mov     r8d, 200h; Size
0x18001d6dd  mov     [rsp+300h+var_2C0], r15
0x18001d6e2  mov     [rsp+300h+var_2C8], r15d
0x18001d6e7  mov     r14, r9
0x18001d6ea  mov     [rsp+300h+var_2A8], r15
0x18001d6ef  call    memset_0
0x18001d6f4  mov     r8d, 100h
0x18001d6fa  lea     rdx, [rbp+200h+var_240]
0x18001d6fe  lea     rcx, [rbp+200h+var_278]
0x18001d702  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d708  test    rsi, rsi
0x18001d70b  jz      loc_18001D8DB
0x18001d711  test    rbx, rbx
0x18001d714  jz      loc_18001D8DB
0x18001d71a  test    r14, r14
0x18001d71d  jz      loc_18001D8DB
0x18001d723  mov     r9d, [rsi+0ACh]
0x18001d72a  lea     r8, [rsp+300h+var_2B0]; struct INativeConfigurationElement **
0x18001d72f  and     r9d, 1; int
0x18001d733  lea     rdx, aSystemWebserve_23; "system.webServer/security/authenticatio"...
0x18001d73a  mov     rcx, r14; this
0x18001d73d  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001d742  mov     ebx, eax
0x18001d744  test    eax, eax
0x18001d746  js      loc_18001D8E0
0x18001d74c  mov     rcx, [rsp+300h+var_2B0]
0x18001d751  lea     r8, [rsp+300h+var_2B8]
0x18001d756  lea     rdx, aProviders; "providers"
0x18001d75d  mov     rax, [rcx]
0x18001d760  mov     rax, [rax+20h]
0x18001d764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d769  mov     ebx, eax
0x18001d76b  test    eax, eax
0x18001d76d  js      loc_18001D8E0
0x18001d773  mov     rcx, [rsp+300h+var_2B8]
0x18001d778  lea     rdx, [rsp+300h+var_2C0]
0x18001d77d  mov     rax, [rcx]
0x18001d780  mov     rax, [rax+28h]
0x18001d784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d789  mov     ebx, eax
0x18001d78b  test    eax, eax
0x18001d78d  js      loc_18001D8E0
0x18001d793  mov     rcx, [rsp+300h+var_2C0]
0x18001d798  lea     rdx, [rsp+300h+var_2C8]
0x18001d79d  mov     rax, [rcx]
0x18001d7a0  mov     rax, [rax+18h]
0x18001d7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a9  mov     ebx, eax
0x18001d7ab  test    eax, eax
0x18001d7ad  js      loc_18001D8E0
0x18001d7b3  mov     edi, r15d
0x18001d7b6  cmp     [rsp+300h+var_2C8], r15d
0x18001d7bb  jbe     loc_18001D876
0x18001d7c1  mov     rcx, [rsp+300h+var_2C0]
0x18001d7c6  lea     r8, [rsp+300h+var_2D0]
0x18001d7cb  mov     edx, edi
0x18001d7cd  mov     rax, [rcx]
0x18001d7d0  mov     rax, [rax+20h]
0x18001d7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d9  mov     ebx, eax
0x18001d7db  test    eax, eax
0x18001d7dd  js      loc_18001D8E0
0x18001d7e3  mov     rcx, [rsp+300h+var_2D0]
0x18001d7e8  lea     r8, [rsp+300h+var_2A8]
0x18001d7ed  xor     r9d, r9d
0x18001d7f0  mov     [rsp+300h+var_2E0], r15
0x18001d7f5  lea     rdx, aValue; "value"
0x18001d7fc  mov     rax, [rcx]
0x18001d7ff  mov     rax, [rax+40h]
0x18001d803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d808  mov     ebx, eax
0x18001d80a  test    eax, eax
0x18001d80c  js      loc_18001D8E0
0x18001d812  lea     rcx, [rbp+200h+var_278]
0x18001d816  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18001d81c  test    al, al
0x18001d81e  jnz     short loc_18001D83B
0x18001d820  lea     rdx, asc_180032E60; ","
0x18001d827  lea     rcx, [rbp+200h+var_278]
0x18001d82b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001d831  mov     ebx, eax
0x18001d833  test    eax, eax
0x18001d835  js      loc_18001D8E0
0x18001d83b  mov     rdx, [rsp+300h+var_2A8]
0x18001d840  lea     rcx, [rbp+200h+var_278]
0x18001d844  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001d84a  mov     ebx, eax
0x18001d84c  test    eax, eax
0x18001d84e  js      loc_18001D8E0
0x18001d854  mov     rcx, [rsp+300h+var_2D0]
0x18001d859  mov     rax, [rcx]
0x18001d85c  mov     rax, [rax+10h]
0x18001d860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d865  inc     edi
0x18001d867  mov     [rsp+300h+var_2D0], r15
0x18001d86c  cmp     edi, [rsp+300h+var_2C8]
0x18001d870  jb      loc_18001D7C1
0x18001d876  mov     eax, [rsi+90h]
0x18001d87c  lea     rcx, [rbp+200h+var_278]
0x18001d880  mov     [rsp+300h+var_2A0.dwMDIdentifier], eax
0x18001d884  mov     eax, [rsi+94h]
0x18001d88a  mov     [rsp+300h+var_2A0.dwMDUserType], eax
0x18001d88e  mov     eax, [rsi+98h]
0x18001d894  mov     [rsp+300h+var_2A0.dwMDDataType], eax
0x18001d898  mov     eax, [rsi+9Ch]
0x18001d89e  mov     [rsp+300h+var_2A0.dwMDAttributes], eax
0x18001d8a2  mov     dword ptr [rsp+300h+var_2A0+14h], r15d
0x18001d8a7  mov     qword ptr [rbp+200h+var_2A0.dwMDDataTag], r15
0x18001d8ab  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d8b1  lea     rcx, [rbp+200h+var_278]
0x18001d8b5  mov     [rsp+300h+var_2A0.pbMDData], rax
0x18001d8ba  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18001d8c0  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001d8c3  lea     rdx, [rsp+300h+var_2A0]; struct _METADATA_RECORD *
0x18001d8c8  add     eax, 2
0x18001d8cb  mov     rcx, r14; this
0x18001d8ce  mov     [rsp+300h+var_2A0.dwMDDataLen], eax
0x18001d8d2  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001d8d7  mov     ebx, eax
0x18001d8d9  jmp     short loc_18001D8E0
0x18001d8db  mov     ebx, 80070057h
0x18001d8e0  mov     rcx, [rsp+300h+var_2C0]
0x18001d8e5  test    rcx, rcx
0x18001d8e8  jz      short loc_18001D8FB
0x18001d8ea  mov     rax, [rcx]
0x18001d8ed  mov     rax, [rax+10h]
0x18001d8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f6  mov     [rsp+300h+var_2C0], r15
0x18001d8fb  mov     rcx, [rsp+300h+var_2D0]
0x18001d900  test    rcx, rcx
0x18001d903  jz      short loc_18001D919
0x18001d905  mov     rax, [rcx]
0x18001d908  mov     rax, [rax+10h]
0x18001d90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d911  mov     rcx, r15
0x18001d914  mov     [rsp+300h+var_2D0], rcx
0x18001d919  mov     rdx, [rsp+300h+var_2B8]
0x18001d91e  test    rdx, rdx
0x18001d921  jz      short loc_18001D93C
0x18001d923  mov     rax, [rdx]
0x18001d926  mov     rcx, rdx
0x18001d929  mov     rax, [rax+10h]
0x18001d92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d932  mov     rcx, [rsp+300h+var_2D0]
0x18001d937  mov     [rsp+300h+var_2B8], r15
0x18001d93c  mov     rdx, [rsp+300h+var_2B0]
0x18001d941  test    rdx, rdx
0x18001d944  jz      short loc_18001D95F
0x18001d946  mov     rax, [rdx]
0x18001d949  mov     rcx, rdx
0x18001d94c  mov     rax, [rax+10h]
0x18001d950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d955  mov     rcx, [rsp+300h+var_2D0]
0x18001d95a  mov     [rsp+300h+var_2B0], r15
0x18001d95f  test    rcx, rcx
0x18001d962  jz      short loc_18001D975
0x18001d964  mov     rax, [rcx]
0x18001d967  mov     rax, [rax+10h]
0x18001d96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d970  mov     [rsp+300h+var_2D0], r15
0x18001d975  lea     rcx, [rbp+200h+var_278]
0x18001d979  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d97f  mov     eax, ebx
0x18001d981  mov     rcx, [rbp+200h+var_40]
0x18001d988  xor     rcx, rsp; StackCookie
0x18001d98b  call    __security_check_cookie
0x18001d990  add     rsp, 2D8h
0x18001d997  pop     r15
0x18001d999  pop     r14
0x18001d99b  pop     rdi
0x18001d99c  pop     rsi
0x18001d99d  pop     rbx
0x18001d99e  pop     rbp
0x18001d99f  retn
```

# DEFAULT_LOAD_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001e530`
- end: `0x18001e817`
- name: `?SetAboProperties@DEFAULT_LOAD_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `743`
- prototype: `int(DEFAULT_LOAD_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001e530`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001e75a`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001e75a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e5a2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e5a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e7f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001e7f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e74b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001e74b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e6cb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e6e4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e6cb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e6e4`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001e6b6`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001e6b6`

## pseudocode

```c
__int64 __fastcall DEFAULT_LOAD_CUSTOM_MAPPER::SetAboProperties(
        DEFAULT_LOAD_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  int MergedConfigElement; // ebx
  unsigned int v8; // edi
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v14; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _METADATA_RECORD v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[56]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v18[256]; // [rsp+C0h] [rbp-40h] BYREF

  v14 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v15 = 0;
  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v17, v18, 0x100u);
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/defaultDocument",
                            &v14,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v14 + 32LL))(
                              v14,
                              L"files",
                              &v13);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v12);
        if ( MergedConfigElement >= 0 )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(v12, &v10);
          if ( MergedConfigElement >= 0 )
          {
            v8 = 0;
            if ( v10 )
            {
              while ( 1 )
              {
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 32LL))(
                                        v12,
                                        v8,
                                        &v11);
                if ( MergedConfigElement < 0 )
                  break;
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
                                        v11,
                                        L"value",
                                        &v15,
                                        0,
                                        0);
                if ( MergedConfigElement < 0 )
                  break;
                if ( !STRU::IsEmpty((STRU *)v17) )
                {
                  MergedConfigElement = STRU::Append((STRU *)v17, L",");
                  if ( MergedConfigElement < 0 )
                    break;
                }
                MergedConfigElement = STRU::Append((STRU *)v17, v15);
                if ( MergedConfigElement < 0 )
                  break;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                ++v8;
                v11 = 0;
                if ( v8 >= v10 )
                  goto LABEL_15;
              }
            }
            else
            {
LABEL_15:
              v16.dwMDIdentifier = *((_DWORD *)a2 + 36);
              v16.dwMDUserType = *((_DWORD *)a2 + 37);
              v16.dwMDDataType = *((_DWORD *)a2 + 38);
              v16.dwMDAttributes = *((_DWORD *)a2 + 39);
              *(&v16.dwMDDataLen + 1) = 0;
              *(_QWORD *)&v16.dwMDDataTag = 0;
              v16.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v17);
              v16.dwMDDataLen = STRU::QueryCB((STRU *)v17) + 2;
              MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v16, a2);
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
  if ( v14 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  STRU::~STRU((STRU *)v17);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001e530  push    rbp
0x18001e532  push    rbx
0x18001e533  push    rsi
0x18001e534  push    rdi
0x18001e535  push    r14
0x18001e537  push    r15
0x18001e539  lea     rbp, [rsp-1D8h]
0x18001e541  sub     rsp, 2D8h
0x18001e548  mov     rax, cs:__security_cookie
0x18001e54f  xor     rax, rsp
0x18001e552  mov     [rbp+200h+var_40], rax
0x18001e559  xor     r15d, r15d
0x18001e55c  lea     rcx, [rbp+200h+var_240]; void *
0x18001e560  mov     rbx, r8
0x18001e563  mov     [rsp+300h+var_2B0], r15
0x18001e568  mov     rsi, rdx
0x18001e56b  mov     [rsp+300h+var_2C0], r15
0x18001e570  xor     edx, edx; Val
0x18001e572  mov     [rsp+300h+var_2D0], r15d
0x18001e577  mov     r8d, 200h; Size
0x18001e57d  mov     [rsp+300h+var_2C8], r15
0x18001e582  mov     [rsp+300h+var_2B8], r15
0x18001e587  mov     r14, r9
0x18001e58a  mov     [rsp+300h+var_2A8], r15
0x18001e58f  call    memset_0
0x18001e594  mov     r8d, 100h
0x18001e59a  lea     rdx, [rbp+200h+var_240]
0x18001e59e  lea     rcx, [rbp+200h+var_278]
0x18001e5a2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e5a8  test    rsi, rsi
0x18001e5ab  jz      loc_18001E77B
0x18001e5b1  test    rbx, rbx
0x18001e5b4  jz      loc_18001E77B
0x18001e5ba  test    r14, r14
0x18001e5bd  jz      loc_18001E77B
0x18001e5c3  mov     r9d, [rsi+0ACh]
0x18001e5ca  lea     r8, [rsp+300h+var_2B0]; struct INativeConfigurationElement **
0x18001e5cf  and     r9d, 1; int
0x18001e5d3  lea     rdx, aSystemWebserve_4; "system.webServer/defaultDocument"
0x18001e5da  mov     rcx, r14; this
0x18001e5dd  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001e5e2  mov     ebx, eax
0x18001e5e4  test    eax, eax
0x18001e5e6  js      loc_18001E780
0x18001e5ec  mov     rcx, [rsp+300h+var_2B0]
0x18001e5f1  lea     r8, [rsp+300h+var_2B8]
0x18001e5f6  lea     rdx, aFiles; "files"
0x18001e5fd  mov     rax, [rcx]
0x18001e600  mov     rax, [rax+20h]
0x18001e604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e609  mov     ebx, eax
0x18001e60b  test    eax, eax
0x18001e60d  js      loc_18001E780
0x18001e613  mov     rcx, [rsp+300h+var_2B8]
0x18001e618  lea     rdx, [rsp+300h+var_2C0]
0x18001e61d  mov     rax, [rcx]
0x18001e620  mov     rax, [rax+28h]
0x18001e624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e629  mov     ebx, eax
0x18001e62b  test    eax, eax
0x18001e62d  js      loc_18001E780
0x18001e633  mov     rcx, [rsp+300h+var_2C0]
0x18001e638  lea     rdx, [rsp+300h+var_2D0]
0x18001e63d  mov     rax, [rcx]
0x18001e640  mov     rax, [rax+18h]
0x18001e644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e649  mov     ebx, eax
0x18001e64b  test    eax, eax
0x18001e64d  js      loc_18001E780
0x18001e653  mov     edi, r15d
0x18001e656  cmp     [rsp+300h+var_2D0], r15d
0x18001e65b  jbe     loc_18001E716
0x18001e661  mov     rcx, [rsp+300h+var_2C0]
0x18001e666  lea     r8, [rsp+300h+var_2C8]
0x18001e66b  mov     edx, edi
0x18001e66d  mov     rax, [rcx]
0x18001e670  mov     rax, [rax+20h]
0x18001e674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e679  mov     ebx, eax
0x18001e67b  test    eax, eax
0x18001e67d  js      loc_18001E780
0x18001e683  mov     rcx, [rsp+300h+var_2C8]
0x18001e688  lea     r8, [rsp+300h+var_2A8]
0x18001e68d  xor     r9d, r9d
0x18001e690  mov     [rsp+300h+var_2E0], r15
0x18001e695  lea     rdx, aValue; "value"
0x18001e69c  mov     rax, [rcx]
0x18001e69f  mov     rax, [rax+40h]
0x18001e6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6a8  mov     ebx, eax
0x18001e6aa  test    eax, eax
0x18001e6ac  js      loc_18001E780
0x18001e6b2  lea     rcx, [rbp+200h+var_278]
0x18001e6b6  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18001e6bc  test    al, al
0x18001e6be  jnz     short loc_18001E6DB
0x18001e6c0  lea     rdx, asc_180032E60; ","
0x18001e6c7  lea     rcx, [rbp+200h+var_278]
0x18001e6cb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001e6d1  mov     ebx, eax
0x18001e6d3  test    eax, eax
0x18001e6d5  js      loc_18001E780
0x18001e6db  mov     rdx, [rsp+300h+var_2A8]
0x18001e6e0  lea     rcx, [rbp+200h+var_278]
0x18001e6e4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001e6ea  mov     ebx, eax
0x18001e6ec  test    eax, eax
0x18001e6ee  js      loc_18001E780
0x18001e6f4  mov     rcx, [rsp+300h+var_2C8]
0x18001e6f9  mov     rax, [rcx]
0x18001e6fc  mov     rax, [rax+10h]
0x18001e700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e705  inc     edi
0x18001e707  mov     [rsp+300h+var_2C8], r15
0x18001e70c  cmp     edi, [rsp+300h+var_2D0]
0x18001e710  jb      loc_18001E661
0x18001e716  mov     eax, [rsi+90h]
0x18001e71c  lea     rcx, [rbp+200h+var_278]
0x18001e720  mov     [rsp+300h+var_2A0.dwMDIdentifier], eax
0x18001e724  mov     eax, [rsi+94h]
0x18001e72a  mov     [rsp+300h+var_2A0.dwMDUserType], eax
0x18001e72e  mov     eax, [rsi+98h]
0x18001e734  mov     [rsp+300h+var_2A0.dwMDDataType], eax
0x18001e738  mov     eax, [rsi+9Ch]
0x18001e73e  mov     [rsp+300h+var_2A0.dwMDAttributes], eax
0x18001e742  mov     dword ptr [rsp+300h+var_2A0+14h], r15d
0x18001e747  mov     qword ptr [rbp+200h+var_2A0.dwMDDataTag], r15
0x18001e74b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001e751  lea     rcx, [rbp+200h+var_278]
0x18001e755  mov     [rsp+300h+var_2A0.pbMDData], rax
0x18001e75a  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18001e760  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001e763  lea     rdx, [rsp+300h+var_2A0]; struct _METADATA_RECORD *
0x18001e768  add     eax, 2
0x18001e76b  mov     rcx, r14; this
0x18001e76e  mov     [rsp+300h+var_2A0.dwMDDataLen], eax
0x18001e772  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001e777  mov     ebx, eax
0x18001e779  jmp     short loc_18001E780
0x18001e77b  mov     ebx, 80070057h
0x18001e780  mov     rcx, [rsp+300h+var_2B8]
0x18001e785  test    rcx, rcx
0x18001e788  jz      short loc_18001E79B
0x18001e78a  mov     rax, [rcx]
0x18001e78d  mov     rax, [rax+10h]
0x18001e791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e796  mov     [rsp+300h+var_2B8], r15
0x18001e79b  mov     rcx, [rsp+300h+var_2B0]
0x18001e7a0  test    rcx, rcx
0x18001e7a3  jz      short loc_18001E7B6
0x18001e7a5  mov     rax, [rcx]
0x18001e7a8  mov     rax, [rax+10h]
0x18001e7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7b1  mov     [rsp+300h+var_2B0], r15
0x18001e7b6  mov     rcx, [rsp+300h+var_2C8]
0x18001e7bb  test    rcx, rcx
0x18001e7be  jz      short loc_18001E7D1
0x18001e7c0  mov     rax, [rcx]
0x18001e7c3  mov     rax, [rax+10h]
0x18001e7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7cc  mov     [rsp+300h+var_2C8], r15
0x18001e7d1  mov     rcx, [rsp+300h+var_2C0]
0x18001e7d6  test    rcx, rcx
0x18001e7d9  jz      short loc_18001E7EC
0x18001e7db  mov     rax, [rcx]
0x18001e7de  mov     rax, [rax+10h]
0x18001e7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7e7  mov     [rsp+300h+var_2C0], r15
0x18001e7ec  lea     rcx, [rbp+200h+var_278]
0x18001e7f0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001e7f6  mov     eax, ebx
0x18001e7f8  mov     rcx, [rbp+200h+var_40]
0x18001e7ff  xor     rcx, rsp; StackCookie
0x18001e802  call    __security_check_cookie
0x18001e807  add     rsp, 2D8h
0x18001e80e  pop     r15
0x18001e810  pop     r14
0x18001e812  pop     rdi
0x18001e813  pop     rsi
0x18001e814  pop     rbx
0x18001e815  pop     rbp
0x18001e816  retn
```

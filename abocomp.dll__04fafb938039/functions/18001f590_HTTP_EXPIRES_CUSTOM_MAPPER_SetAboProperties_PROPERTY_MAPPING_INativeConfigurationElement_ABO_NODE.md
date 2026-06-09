# HTTP_EXPIRES_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001f590`
- end: `0x18001f8b8`
- name: `?SetAboProperties@HTTP_EXPIRES_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `808`
- prototype: `int(HTTP_EXPIRES_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180003460`
- `0x18000a838`
- `0x18001f590`
- `0x180026b44`
- `0x18002c010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001f7bc`
- `msvcrt!_ultow` at `0x18001f7bc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f68e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f71e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f7f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f68e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f71e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f7f3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001f840`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001f840`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f88d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f88d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f707`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f7ce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f707`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f7ce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f5d1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f5d1`

## string_xrefs

- `0x18001f614`: `cacheControlMode`
- `0x18001f743`: `cacheControlMaxAge`

## pseudocode

```c
__int64 __fastcall HTTP_EXPIRES_CUSTOM_MAPPER::SetAboProperties(
        HTTP_EXPIRES_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  struct INativePropertyExtendedInfo *v7; // rdx
  int v8; // ebx
  wchar_t *v9; // rdx
  int v10; // eax
  struct INativePropertyExtendedInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  struct _METADATA_RECORD v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[56]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t Buffer[64]; // [rsp+B0h] [rbp-50h] BYREF

  v13 = 0;
  v15 = 0;
  STRU::STRU((STRU *)v17);
  v16 = 0;
  v7 = 0;
  v12 = 0;
  if ( a2 && a3 && a4 )
  {
    v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 48LL))(
           a3,
           L"cacheControlMode",
           &v13,
           0,
           &v12);
    if ( v8 >= 0 && (unsigned int)FSetHere(v12) )
    {
      v7 = v12;
      if ( v12 )
      {
        (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v12 + 16LL))(v12);
        v7 = 0;
        v12 = 0;
      }
      if ( v13 )
      {
        if ( v13 == 2 )
        {
          v8 = STRU::Copy((STRU *)v17, L"D,");
          if ( v8 < 0 )
            goto LABEL_28;
          v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 80LL))(
                 a3,
                 L"cacheControlMaxAge",
                 &v15,
                 0,
                 &v12);
          if ( v8 < 0 || !(unsigned int)FSetHere(v12) )
            goto LABEL_28;
          if ( v12 )
          {
            (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v12 + 16LL))(v12);
            v12 = 0;
          }
          _ultow(v15 / 10000000, Buffer, 16);
          v8 = STRU::Append((STRU *)v17, L"0x");
          if ( v8 < 0 )
            goto LABEL_28;
          v9 = Buffer;
        }
        else
        {
          if ( v13 != 3 )
            goto LABEL_30;
          v8 = STRU::Copy((STRU *)v17, L"S,");
          if ( v8 < 0 )
            goto LABEL_28;
          v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 64LL))(
                 a3,
                 L"httpExpires",
                 &v16,
                 0,
                 &v12);
          if ( v8 < 0 || !(unsigned int)FSetHere(v12) )
            goto LABEL_28;
          if ( v12 )
          {
            (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v12 + 16LL))(v12);
            v12 = 0;
          }
          v9 = v16;
        }
        v10 = STRU::Append((STRU *)v17, v9);
      }
      else
      {
        v10 = STRU::Copy((STRU *)v17, &word_18002E968);
      }
      v8 = v10;
      if ( v10 >= 0 )
      {
        v14.dwMDIdentifier = *((_DWORD *)a2 + 36);
        v14.dwMDUserType = *((_DWORD *)a2 + 37);
        v14.dwMDDataType = *((_DWORD *)a2 + 38);
        v14.dwMDAttributes = *((_DWORD *)a2 + 39);
        v14.pbMDData = v17;
        *(&v14.dwMDDataLen + 1) = 0;
        *(_QWORD *)&v14.dwMDDataTag = 0;
        v14.dwMDDataLen = 2 * STRU::QueryCCH((STRU *)v17) + 2;
        v8 = ABO_NODE::SetDataByMapping(a4, &v14, a2);
      }
    }
LABEL_28:
    v7 = v12;
    goto LABEL_30;
  }
  v8 = -2147024809;
LABEL_30:
  if ( v7 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v7 + 16LL))(v7);
    v12 = 0;
  }
  STRU::~STRU((STRU *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f590  mov     [rsp-8+arg_0], rbx
0x18001f595  push    rbp
0x18001f596  push    rsi
0x18001f597  push    rdi
0x18001f598  push    r14
0x18001f59a  push    r15
0x18001f59c  lea     rbp, [rsp-40h]
0x18001f5a1  sub     rsp, 140h
0x18001f5a8  mov     rax, cs:__security_cookie
0x18001f5af  xor     rax, rsp
0x18001f5b2  mov     [rbp+60h+var_30], rax
0x18001f5b6  xor     r15d, r15d
0x18001f5b9  lea     rcx, [rsp+160h+var_E8]
0x18001f5be  mov     [rsp+160h+var_128], r15d
0x18001f5c3  mov     r14, r9
0x18001f5c6  mov     [rsp+160h+var_F8], r15
0x18001f5cb  mov     rsi, r8
0x18001f5ce  mov     rdi, rdx
0x18001f5d1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f5d7  mov     [rsp+160h+var_F0], r15
0x18001f5dc  mov     edx, r15d
0x18001f5df  mov     [rsp+160h+var_130], rdx
0x18001f5e4  test    rdi, rdi
0x18001f5e7  jz      loc_18001F86A
0x18001f5ed  test    rsi, rsi
0x18001f5f0  jz      loc_18001F86A
0x18001f5f6  test    r14, r14
0x18001f5f9  jz      loc_18001F86A
0x18001f5ff  mov     rax, [rsi]
0x18001f602  lea     rcx, [rsp+160h+var_130]
0x18001f607  mov     [rsp+160h+var_140], rcx
0x18001f60c  lea     r8, [rsp+160h+var_128]
0x18001f611  xor     r9d, r9d
0x18001f614  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x18001f61b  mov     rcx, rsi
0x18001f61e  mov     rax, [rax+30h]
0x18001f622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f627  mov     ebx, eax
0x18001f629  test    eax, eax
0x18001f62b  js      loc_18001F863
0x18001f631  mov     rcx, [rsp+160h+var_130]; struct INativePropertyExtendedInfo *
0x18001f636  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001f63b  test    eax, eax
0x18001f63d  jz      loc_18001F863
0x18001f643  mov     rdx, [rsp+160h+var_130]
0x18001f648  test    rdx, rdx
0x18001f64b  jz      short loc_18001F664
0x18001f64d  mov     rcx, [rdx]
0x18001f650  mov     rax, [rcx+10h]
0x18001f654  mov     rcx, rdx
0x18001f657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f65c  mov     edx, r15d
0x18001f65f  mov     [rsp+160h+var_130], rdx
0x18001f664  mov     eax, [rsp+160h+var_128]
0x18001f668  test    eax, eax
0x18001f66a  jz      loc_18001F7E7
0x18001f670  sub     eax, 2
0x18001f673  jz      loc_18001F712
0x18001f679  cmp     eax, 1
0x18001f67c  jnz     loc_18001F86F
0x18001f682  lea     rdx, aS; "S,"
0x18001f689  lea     rcx, [rsp+160h+var_E8]
0x18001f68e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f694  mov     ebx, eax
0x18001f696  test    eax, eax
0x18001f698  js      loc_18001F863
0x18001f69e  mov     rax, [rsi]
0x18001f6a1  lea     rcx, [rsp+160h+var_130]
0x18001f6a6  mov     [rsp+160h+var_140], rcx
0x18001f6ab  lea     r8, [rsp+160h+var_F0]
0x18001f6b0  xor     r9d, r9d
0x18001f6b3  lea     rdx, aHttpexpires; "httpExpires"
0x18001f6ba  mov     rcx, rsi
0x18001f6bd  mov     rax, [rax+40h]
0x18001f6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6c6  mov     ebx, eax
0x18001f6c8  test    eax, eax
0x18001f6ca  js      loc_18001F863
0x18001f6d0  mov     rcx, [rsp+160h+var_130]; struct INativePropertyExtendedInfo *
0x18001f6d5  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001f6da  test    eax, eax
0x18001f6dc  jz      loc_18001F863
0x18001f6e2  mov     rcx, [rsp+160h+var_130]
0x18001f6e7  test    rcx, rcx
0x18001f6ea  jz      short loc_18001F6FD
0x18001f6ec  mov     rax, [rcx]
0x18001f6ef  mov     rax, [rax+10h]
0x18001f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6f8  mov     [rsp+160h+var_130], r15
0x18001f6fd  mov     rdx, [rsp+160h+var_F0]
0x18001f702  lea     rcx, [rsp+160h+var_E8]
0x18001f707  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001f70d  jmp     loc_18001F7F9
0x18001f712  lea     rdx, aD; "D,"
0x18001f719  lea     rcx, [rsp+160h+var_E8]
0x18001f71e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f724  mov     ebx, eax
0x18001f726  test    eax, eax
0x18001f728  js      loc_18001F863
0x18001f72e  mov     rax, [rsi]
0x18001f731  lea     rcx, [rsp+160h+var_130]
0x18001f736  mov     [rsp+160h+var_140], rcx
0x18001f73b  lea     r8, [rsp+160h+var_F8]
0x18001f740  xor     r9d, r9d
0x18001f743  lea     rdx, aCachecontrolma; "cacheControlMaxAge"
0x18001f74a  mov     rcx, rsi
0x18001f74d  mov     rax, [rax+50h]
0x18001f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f756  mov     ebx, eax
0x18001f758  test    eax, eax
0x18001f75a  js      loc_18001F863
0x18001f760  mov     rcx, [rsp+160h+var_130]; struct INativePropertyExtendedInfo *
0x18001f765  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001f76a  test    eax, eax
0x18001f76c  jz      loc_18001F863
0x18001f772  mov     rcx, [rsp+160h+var_130]
0x18001f777  test    rcx, rcx
0x18001f77a  jz      short loc_18001F78D
0x18001f77c  mov     rax, [rcx]
0x18001f77f  mov     rax, [rax+10h]
0x18001f783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f788  mov     [rsp+160h+var_130], r15
0x18001f78d  mov     rax, 0D6BF94D5E57A42BDh
0x18001f797  mov     r8d, 10h; Radix
0x18001f79d  imul    [rsp+160h+var_F8]
0x18001f7a2  mov     rcx, rdx
0x18001f7a5  lea     rdx, [rbp+60h+Buffer]; Buffer
0x18001f7a9  add     rcx, [rsp+160h+var_F8]
0x18001f7ae  sar     rcx, 17h
0x18001f7b2  mov     rax, rcx
0x18001f7b5  shr     rax, 3Fh
0x18001f7b9  add     rcx, rax; Value
0x18001f7bc  call    cs:__imp__ultow
0x18001f7c2  lea     rdx, a0x; "0x"
0x18001f7c9  lea     rcx, [rsp+160h+var_E8]
0x18001f7ce  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001f7d4  mov     ebx, eax
0x18001f7d6  test    eax, eax
0x18001f7d8  js      loc_18001F863
0x18001f7de  lea     rdx, [rbp+60h+Buffer]
0x18001f7e2  jmp     loc_18001F702
0x18001f7e7  lea     rdx, word_18002E968
0x18001f7ee  lea     rcx, [rsp+160h+var_E8]
0x18001f7f3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f7f9  mov     ebx, eax
0x18001f7fb  test    eax, eax
0x18001f7fd  js      short loc_18001F863
0x18001f7ff  mov     eax, [rdi+90h]
0x18001f805  lea     rcx, [rsp+160h+var_E8]
0x18001f80a  mov     [rsp+160h+var_120.dwMDIdentifier], eax
0x18001f80e  mov     eax, [rdi+94h]
0x18001f814  mov     [rsp+160h+var_120.dwMDUserType], eax
0x18001f818  mov     eax, [rdi+98h]
0x18001f81e  mov     [rsp+160h+var_120.dwMDDataType], eax
0x18001f822  mov     eax, [rdi+9Ch]
0x18001f828  mov     [rsp+160h+var_120.dwMDAttributes], eax
0x18001f82c  lea     rax, [rsp+160h+var_E8]
0x18001f831  mov     [rsp+160h+var_120.pbMDData], rax
0x18001f836  mov     dword ptr [rsp+160h+var_120+14h], r15d
0x18001f83b  mov     qword ptr [rsp+160h+var_120.dwMDDataTag], r15
0x18001f840  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18001f846  mov     r8, rdi; struct PROPERTY_MAPPING *
0x18001f849  lea     rdx, [rsp+160h+var_120]; struct _METADATA_RECORD *
0x18001f84e  mov     rcx, r14; this
0x18001f851  lea     eax, ds:2[rax*2]
0x18001f858  mov     [rsp+160h+var_120.dwMDDataLen], eax
0x18001f85c  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001f861  mov     ebx, eax
0x18001f863  mov     rdx, [rsp+160h+var_130]
0x18001f868  jmp     short loc_18001F86F
0x18001f86a  mov     ebx, 80070057h
0x18001f86f  test    rdx, rdx
0x18001f872  jz      short loc_18001F888
0x18001f874  mov     rax, [rdx]
0x18001f877  mov     rcx, rdx
0x18001f87a  mov     rax, [rax+10h]
0x18001f87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f883  mov     [rsp+160h+var_130], r15
0x18001f888  lea     rcx, [rsp+160h+var_E8]
0x18001f88d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f893  mov     eax, ebx
0x18001f895  mov     rcx, [rbp+60h+var_30]
0x18001f899  xor     rcx, rsp; StackCookie
0x18001f89c  call    __security_check_cookie
0x18001f8a1  mov     rbx, [rsp+160h+arg_0]
0x18001f8a9  add     rsp, 140h
0x18001f8b0  pop     r15
0x18001f8b2  pop     r14
0x18001f8b4  pop     rdi
0x18001f8b5  pop     rsi
0x18001f8b6  pop     rbp
0x18001f8b7  retn
```

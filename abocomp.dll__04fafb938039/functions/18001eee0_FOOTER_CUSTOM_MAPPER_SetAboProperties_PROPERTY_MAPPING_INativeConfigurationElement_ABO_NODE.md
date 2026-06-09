# FOOTER_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001eee0`
- end: `0x18001f1e1`
- name: `?SetAboProperties@FOOTER_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `769`
- prototype: `int(FOOTER_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001eee0`
- `0x180026a60`
- `0x180026b44`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f06a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f0a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f06a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f0a8`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001f119`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001f119`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ef52`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ef7a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ef52`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ef7a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f1a8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f1b2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f1a8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f1b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f096`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f10a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f096`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f10a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f0c1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f0c1`

## pseudocode

```c
__int64 __fastcall FOOTER_CUSTOM_MAPPER::SetAboProperties(
        FOOTER_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  struct INativePropertyExtendedInfo *v7; // rdx
  struct INativePropertyExtendedInfo *v8; // rcx
  int MergedConfigElement; // ebx
  const unsigned __int16 *Str; // rdx
  struct INativePropertyExtendedInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  struct INativePropertyExtendedInfo *v14; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpSrc; // [rsp+50h] [rbp-B0h] BYREF
  struct _METADATA_RECORD v17; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[56]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v20[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v21[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v15 = 0;
  v13 = 0;
  lpSrc = 0;
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, v20, 0x100u);
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v19, v21, 0x100u);
  v7 = 0;
  v8 = 0;
  v14 = 0;
  v12 = 0;
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/staticContent",
                            &v15,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)v15 + 64LL))(
                              v15,
                              L"defaultDocFooter",
                              &lpSrc,
                              0,
                              &v14);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 72LL))(
                                a3,
                                L"isDocFooterFileName",
                                &v13,
                                0,
                                &v12);
        if ( MergedConfigElement >= 0 && ((unsigned int)FSetHere(v12) || (unsigned int)FSetHere(v14)) )
        {
          if ( v13 )
          {
            MergedConfigElement = STRU::Copy((STRU *)v18, L"FILE:");
            if ( MergedConfigElement >= 0 )
            {
              MergedConfigElement = ExpandEnvironmentVariables(lpSrc, (struct STRU *)v19);
              if ( MergedConfigElement >= 0 )
              {
                Str = STRU::QueryStr((STRU *)v19);
                goto LABEL_15;
              }
            }
          }
          else
          {
            MergedConfigElement = STRU::Copy((STRU *)v18, L"STRING:");
            if ( MergedConfigElement >= 0 )
            {
              Str = lpSrc;
LABEL_15:
              MergedConfigElement = STRU::Append((STRU *)v18, Str);
              if ( MergedConfigElement >= 0 )
              {
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
    v7 = v14;
    v8 = v12;
    goto LABEL_19;
  }
  MergedConfigElement = -2147024809;
LABEL_19:
  if ( v7 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = v12;
    v14 = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v8 + 16LL))(v8);
    v12 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  STRU::~STRU((STRU *)v19);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001eee0  mov     [rsp-8+arg_0], rbx
0x18001eee5  mov     [rsp-8+arg_8], rsi
0x18001eeea  push    rbp
0x18001eeeb  push    rdi
0x18001eeec  push    r14
0x18001eeee  lea     rbp, [rsp-400h]
0x18001eef6  sub     rsp, 500h
0x18001eefd  mov     rax, cs:__security_cookie
0x18001ef04  xor     rax, rsp
0x18001ef07  mov     [rbp+410h+var_20], rax
0x18001ef0e  mov     rsi, r8
0x18001ef11  mov     [rsp+510h+var_4C8], 0
0x18001ef1a  mov     rdi, rdx
0x18001ef1d  mov     [rsp+510h+var_4D8], 0
0x18001ef25  xor     edx, edx; Val
0x18001ef27  mov     [rsp+510h+lpSrc], 0
0x18001ef30  mov     r8d, 200h; Size
0x18001ef36  lea     rcx, [rbp+410h+var_420]; void *
0x18001ef3a  mov     r14, r9
0x18001ef3d  call    memset_0
0x18001ef42  mov     ebx, 100h
0x18001ef47  lea     rdx, [rbp+410h+var_420]
0x18001ef4b  mov     r8d, ebx
0x18001ef4e  lea     rcx, [rbp+410h+var_490]
0x18001ef52  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001ef58  xor     edx, edx; Val
0x18001ef5a  lea     rcx, [rbp+410h+var_220]; void *
0x18001ef61  mov     r8d, 200h; Size
0x18001ef67  call    memset_0
0x18001ef6c  mov     r8d, ebx
0x18001ef6f  lea     rdx, [rbp+410h+var_220]
0x18001ef76  lea     rcx, [rbp+410h+var_458]
0x18001ef7a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001ef80  xor     edx, edx
0x18001ef82  xor     ecx, ecx
0x18001ef84  mov     [rsp+510h+var_4D0], rdx
0x18001ef89  mov     [rsp+510h+var_4E0], rcx
0x18001ef8e  test    rdi, rdi
0x18001ef91  jz      loc_18001F144
0x18001ef97  test    rsi, rsi
0x18001ef9a  jz      loc_18001F144
0x18001efa0  test    r14, r14
0x18001efa3  jz      loc_18001F144
0x18001efa9  mov     r9d, [rdi+0ACh]
0x18001efb0  lea     r8, [rsp+510h+var_4C8]; struct INativeConfigurationElement **
0x18001efb5  and     r9d, 1; int
0x18001efb9  lea     rdx, aSystemWebserve_0; "system.webServer/staticContent"
0x18001efc0  mov     rcx, r14; this
0x18001efc3  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001efc8  mov     ebx, eax
0x18001efca  test    eax, eax
0x18001efcc  js      loc_18001F138
0x18001efd2  mov     rcx, [rsp+510h+var_4C8]
0x18001efd7  lea     rdx, [rsp+510h+var_4D0]
0x18001efdc  mov     [rsp+510h+var_4F0], rdx
0x18001efe1  lea     r8, [rsp+510h+lpSrc]
0x18001efe6  xor     r9d, r9d
0x18001efe9  lea     rdx, aDefaultdocfoot; "defaultDocFooter"
0x18001eff0  mov     rax, [rcx]
0x18001eff3  mov     rax, [rax+40h]
0x18001eff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001effc  mov     ebx, eax
0x18001effe  test    eax, eax
0x18001f000  js      loc_18001F138
0x18001f006  mov     rax, [rsi]
0x18001f009  lea     rcx, [rsp+510h+var_4E0]
0x18001f00e  mov     [rsp+510h+var_4F0], rcx
0x18001f013  lea     r8, [rsp+510h+var_4D8]
0x18001f018  xor     r9d, r9d
0x18001f01b  lea     rdx, aIsdocfooterfil; "isDocFooterFileName"
0x18001f022  mov     rcx, rsi
0x18001f025  mov     rax, [rax+48h]
0x18001f029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f02e  mov     ebx, eax
0x18001f030  test    eax, eax
0x18001f032  js      loc_18001F138
0x18001f038  mov     rcx, [rsp+510h+var_4E0]; struct INativePropertyExtendedInfo *
0x18001f03d  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001f042  test    eax, eax
0x18001f044  jnz     short loc_18001F058
0x18001f046  mov     rcx, [rsp+510h+var_4D0]; struct INativePropertyExtendedInfo *
0x18001f04b  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001f050  test    eax, eax
0x18001f052  jz      loc_18001F138
0x18001f058  cmp     [rsp+510h+var_4D8], 0
0x18001f05d  lea     rcx, [rbp+410h+var_490]
0x18001f061  jz      short loc_18001F0A1
0x18001f063  lea     rdx, aFile_1; "FILE:"
0x18001f06a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f070  mov     ebx, eax
0x18001f072  test    eax, eax
0x18001f074  js      loc_18001F138
0x18001f07a  mov     rcx, [rsp+510h+lpSrc]; lpSrc
0x18001f07f  lea     rdx, [rbp+410h+var_458]; struct STRU *
0x18001f083  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x18001f088  mov     ebx, eax
0x18001f08a  test    eax, eax
0x18001f08c  js      loc_18001F138
0x18001f092  lea     rcx, [rbp+410h+var_458]
0x18001f096  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001f09c  mov     rdx, rax
0x18001f09f  jmp     short loc_18001F0BD
0x18001f0a1  lea     rdx, aString; "STRING:"
0x18001f0a8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f0ae  mov     ebx, eax
0x18001f0b0  test    eax, eax
0x18001f0b2  js      loc_18001F138
0x18001f0b8  mov     rdx, [rsp+510h+lpSrc]
0x18001f0bd  lea     rcx, [rbp+410h+var_490]
0x18001f0c1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001f0c7  mov     ebx, eax
0x18001f0c9  test    eax, eax
0x18001f0cb  js      short loc_18001F138
0x18001f0cd  mov     eax, [rdi+90h]
0x18001f0d3  lea     rcx, [rbp+410h+var_490]
0x18001f0d7  mov     [rsp+510h+var_4B8.dwMDIdentifier], eax
0x18001f0db  mov     eax, [rdi+94h]
0x18001f0e1  mov     [rsp+510h+var_4B8.dwMDUserType], eax
0x18001f0e5  mov     eax, [rdi+98h]
0x18001f0eb  mov     [rsp+510h+var_4B8.dwMDDataType], eax
0x18001f0ef  mov     eax, [rdi+9Ch]
0x18001f0f5  mov     [rsp+510h+var_4B8.dwMDAttributes], eax
0x18001f0f9  mov     dword ptr [rsp+510h+var_4B8+14h], 0
0x18001f101  mov     qword ptr [rsp+510h+var_4B8.dwMDDataTag], 0
0x18001f10a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001f110  lea     rcx, [rbp+410h+var_490]
0x18001f114  mov     [rsp+510h+var_4B8.pbMDData], rax
0x18001f119  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18001f11f  mov     r8, rdi; struct PROPERTY_MAPPING *
0x18001f122  lea     rdx, [rsp+510h+var_4B8]; struct _METADATA_RECORD *
0x18001f127  add     eax, 2
0x18001f12a  mov     rcx, r14; this
0x18001f12d  mov     [rsp+510h+var_4B8.dwMDDataLen], eax
0x18001f131  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001f136  mov     ebx, eax
0x18001f138  mov     rdx, [rsp+510h+var_4D0]
0x18001f13d  mov     rcx, [rsp+510h+var_4E0]
0x18001f142  jmp     short loc_18001F149
0x18001f144  mov     ebx, 80070057h
0x18001f149  test    rdx, rdx
0x18001f14c  jz      short loc_18001F16B
0x18001f14e  mov     rax, [rdx]
0x18001f151  mov     rcx, rdx
0x18001f154  mov     rax, [rax+10h]
0x18001f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f15d  mov     rcx, [rsp+510h+var_4E0]
0x18001f162  mov     [rsp+510h+var_4D0], 0
0x18001f16b  test    rcx, rcx
0x18001f16e  jz      short loc_18001F185
0x18001f170  mov     rax, [rcx]
0x18001f173  mov     rax, [rax+10h]
0x18001f177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f17c  mov     [rsp+510h+var_4E0], 0
0x18001f185  mov     rcx, [rsp+510h+var_4C8]
0x18001f18a  test    rcx, rcx
0x18001f18d  jz      short loc_18001F1A4
0x18001f18f  mov     rax, [rcx]
0x18001f192  mov     rax, [rax+10h]
0x18001f196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f19b  mov     [rsp+510h+var_4C8], 0
0x18001f1a4  lea     rcx, [rbp+410h+var_458]
0x18001f1a8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f1ae  lea     rcx, [rbp+410h+var_490]
0x18001f1b2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f1b8  mov     eax, ebx
0x18001f1ba  mov     rcx, [rbp+410h+var_20]
0x18001f1c1  xor     rcx, rsp; StackCookie
0x18001f1c4  call    __security_check_cookie
0x18001f1c9  lea     r11, [rsp+510h+var_10]
0x18001f1d1  mov     rbx, [r11+20h]
0x18001f1d5  mov     rsi, [r11+28h]
0x18001f1d9  mov     rsp, r11
0x18001f1dc  pop     r14
0x18001f1de  pop     rdi
0x18001f1df  pop     rbp
0x18001f1e0  retn
```

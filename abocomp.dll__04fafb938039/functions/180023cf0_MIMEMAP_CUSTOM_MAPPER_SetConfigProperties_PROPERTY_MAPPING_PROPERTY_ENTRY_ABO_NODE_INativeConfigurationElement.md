# MIMEMAP_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180023cf0`
- end: `0x180024255`
- name: `?SetConfigProperties@MIMEMAP_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `1381`
- prototype: `int(MIMEMAP_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003460`
- `0x180009488`
- `0x180009818`
- `0x1800103e8`
- `0x180023cf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023fb0`
- `msvcrt!_wcsicmp` at `0x180023fb0`
- `iisutil!SplitCommaDelimitedString` at `0x180023f2d`
- `iisutil!SplitCommaDelimitedString` at `0x180023f2d`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180023f51`
- `iisutil!?Next@MULTISZ@@QEBAPEBGPEBG@Z` at `0x180023f51`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180023f41`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180023f41`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023f03`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023f76`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800241e3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180024200`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023f03`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023f76`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800241e3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180024200`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002421c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002421c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800241ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800241ce`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180023fc2`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180023fc2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023d6e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180023d6e`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180023d4f`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180023d4f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180024226`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180024226`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180023d64`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180023d64`

## string_xrefs

- `0x180023f17`: `fileExtension`
- `0x180023fda`: `remove`

## pseudocode

```c
__int64 __fastcall MIMEMAP_CUSTOM_MAPPER::SetConfigProperties(
        MIMEMAP_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  int MergedConfigElement; // edi
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  __int64 v11; // rax
  unsigned int v12; // edx
  int v13; // ebx
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // r14
  const unsigned __int16 *v16; // r15
  int v17; // esi
  _QWORD **Ptr; // rax
  __int64 v19; // rax
  unsigned int i; // esi
  _QWORD **v21; // rax
  __int64 v22; // rbx
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeConfigurationElement *v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v29; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[56]; // [rsp+D8h] [rbp-28h] BYREF

  v26 = 0;
  v27 = 0;
  v29 = 0;
  v25 = 0;
  v28 = 0;
  v24 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v33);
  String2 = 0;
  v31 = 0;
  BUFFER::BUFFER((BUFFER *)v32);
  STRU::STRU((STRU *)v34);
  if ( a2 && a3 && a4 && a5 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/staticContent",
                            &v29,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v29 + 40LL))(
                              v29,
                              &v27);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 24LL))(v27, &v24);
        if ( MergedConfigElement >= 0 )
        {
          v9 = 0;
          if ( v24 )
          {
            while ( 1 )
            {
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v27 + 32LL))(
                                      v27,
                                      v9,
                                      &v25);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = CONFIG_ELEMENT_LIST::AddEntry((CONFIG_ELEMENT_LIST *)&v31, v25, v10);
              if ( MergedConfigElement < 0 )
                break;
              ++v9;
              v25 = 0;
              if ( v9 >= v24 )
                goto LABEL_12;
            }
          }
          else
          {
LABEL_12:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            v11 = *(_QWORD *)a5;
            v27 = 0;
            MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(v11 + 40))(
                                    a5,
                                    &v26);
            if ( MergedConfigElement >= 0 )
            {
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 72LL))(
                                      v26,
                                      &v24);
              if ( MergedConfigElement >= 0 )
              {
                v12 = v24;
                v13 = 0;
                if ( v24 )
                {
                  while ( 1 )
                  {
                    MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 96LL))(
                                            v26,
                                            v12 - v13 - 1,
                                            0);
                    if ( MergedConfigElement < 0 )
                      break;
                    v12 = v24;
                    if ( ++v13 >= v24 )
                      goto LABEL_17;
                  }
                }
                else
                {
LABEL_17:
                  MergedConfigElement = ABO_NODE::GetLocationPath(a4, (struct STRU *)v34, *((_DWORD *)a2 + 43) & 1);
                  if ( MergedConfigElement >= 0 )
                  {
                    v14 = (const unsigned __int16 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16))
                                                    + 3);
                    if ( *v14 )
                    {
                      while ( 1 )
                      {
                        MergedConfigElement = SplitCommaDelimitedString(v14, 1, 1, (struct MULTISZ *)v33);
                        if ( MergedConfigElement < 0 )
                          break;
                        v15 = MULTISZ::First((MULTISZ *)v33);
                        v16 = MULTISZ::Next((MULTISZ *)v33, v15);
                        if ( !v16 )
                        {
                          MergedConfigElement = -2147024883;
                          break;
                        }
                        v17 = 0;
                        if ( v31 )
                        {
                          do
                          {
                            Ptr = (_QWORD **)BUFFER::QueryPtr((BUFFER *)v32);
                            MergedConfigElement = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*Ptr[v17] + 64LL))(
                                                    Ptr[v17],
                                                    L"fileExtension",
                                                    &String2,
                                                    0,
                                                    0);
                            if ( MergedConfigElement < 0 )
                              goto LABEL_40;
                            if ( !_wcsicmp(v15, String2) && !STRU::IsEmpty((STRU *)v34) )
                            {
                              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v26 + 48LL))(
                                                      v26,
                                                      L"remove",
                                                      &v28);
                              if ( MergedConfigElement < 0 )
                                goto LABEL_40;
                              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v28 + 128LL))(
                                                      v28,
                                                      L"fileExtension",
                                                      v15,
                                                      0);
                              if ( MergedConfigElement < 0 )
                                goto LABEL_40;
                              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v26 + 56LL))(
                                                      v26,
                                                      v28,
                                                      0xFFFFFFFFLL,
                                                      0);
                              if ( MergedConfigElement < 0 )
                                goto LABEL_40;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                              v28 = 0;
                            }
                          }
                          while ( ++v17 < v31 );
                        }
                        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v26 + 48LL))(
                                                v26,
                                                L"mimeMap",
                                                &v25);
                        if ( MergedConfigElement >= 0 )
                        {
                          MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v25 + 128LL))(
                                                  v25,
                                                  L"fileExtension",
                                                  v15,
                                                  0);
                          if ( MergedConfigElement >= 0 )
                          {
                            MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v25 + 128LL))(
                                                    v25,
                                                    L"mimeType",
                                                    v16,
                                                    0);
                            if ( MergedConfigElement >= 0 )
                            {
                              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v26 + 56LL))(
                                                      v26,
                                                      v25,
                                                      0xFFFFFFFFLL,
                                                      0);
                              if ( MergedConfigElement >= 0 )
                              {
                                (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v25 + 16LL))(v25);
                                v19 = -1;
                                v25 = 0;
                                do
                                  ++v19;
                                while ( v14[v19] );
                                v14 += v19 + 1;
                                if ( *v14 )
                                  continue;
                              }
                            }
                          }
                        }
                        break;
                      }
                    }
                  }
                }
              }
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
LABEL_40:
  if ( v29 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  STRU::~STRU((STRU *)v34);
  for ( i = 0; i < v31; *((_QWORD *)BUFFER::QueryPtr((BUFFER *)v32) + v22) = 0 )
  {
    v21 = (_QWORD **)BUFFER::QueryPtr((BUFFER *)v32);
    v22 = i;
    (*(void (__fastcall **)(_QWORD *))(*v21[i] + 16LL))(v21[i]);
    ++i;
  }
  v31 = 0;
  BUFFER::~BUFFER((BUFFER *)v32);
  MULTISZ::~MULTISZ((MULTISZ *)v33);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x180023cf0  mov     [rsp-8+arg_0], rbx
0x180023cf5  push    rbp
0x180023cf6  push    rsi
0x180023cf7  push    rdi
0x180023cf8  push    r12
0x180023cfa  push    r13
0x180023cfc  push    r14
0x180023cfe  push    r15
0x180023d00  lea     rbp, [rsp-20h]
0x180023d05  sub     rsp, 120h
0x180023d0c  mov     rax, cs:__security_cookie
0x180023d13  xor     rax, rsp
0x180023d16  mov     [rbp+50h+var_40], rax
0x180023d1a  mov     r14, [rbp+50h+arg_20]
0x180023d21  lea     rcx, [rbp+50h+var_B0]
0x180023d25  xor     r12d, r12d
0x180023d28  mov     rsi, r9
0x180023d2b  mov     [rsp+150h+var_110], r12
0x180023d30  mov     r13, r8
0x180023d33  mov     [rsp+150h+var_108], r12
0x180023d38  mov     r15, rdx
0x180023d3b  mov     [rsp+150h+var_F8], r12
0x180023d40  mov     [rsp+150h+var_118], r12
0x180023d45  mov     [rsp+150h+var_100], r12
0x180023d4a  mov     [rsp+150h+var_120], r12d
0x180023d4f  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180023d55  lea     rcx, [rsp+150h+var_E0]
0x180023d5a  mov     [rsp+150h+String2], r12
0x180023d5f  mov     [rsp+150h+var_E8], r12d
0x180023d64  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180023d6a  lea     rcx, [rbp+50h+var_78]
0x180023d6e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180023d74  test    r15, r15
0x180023d77  jz      loc_18002413E
0x180023d7d  test    r13, r13
0x180023d80  jz      loc_18002413E
0x180023d86  test    rsi, rsi
0x180023d89  jz      loc_18002413E
0x180023d8f  test    r14, r14
0x180023d92  jz      loc_18002413E
0x180023d98  mov     r9d, [r15+0ACh]
0x180023d9f  lea     r8, [rsp+150h+var_F8]; struct INativeConfigurationElement **
0x180023da4  and     r9d, 1; int
0x180023da8  lea     rdx, aSystemWebserve_0; "system.webServer/staticContent"
0x180023daf  mov     rcx, rsi; this
0x180023db2  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x180023db7  mov     edi, eax
0x180023db9  test    eax, eax
0x180023dbb  js      loc_180024143
0x180023dc1  mov     rcx, [rsp+150h+var_F8]
0x180023dc6  lea     rdx, [rsp+150h+var_108]
0x180023dcb  mov     rax, [rcx]
0x180023dce  mov     rax, [rax+28h]
0x180023dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd7  mov     edi, eax
0x180023dd9  test    eax, eax
0x180023ddb  js      loc_180024143
0x180023de1  mov     rcx, [rsp+150h+var_108]
0x180023de6  lea     rdx, [rsp+150h+var_120]
0x180023deb  mov     rax, [rcx]
0x180023dee  mov     rax, [rax+18h]
0x180023df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023df7  mov     edi, eax
0x180023df9  test    eax, eax
0x180023dfb  js      loc_180024143
0x180023e01  mov     ebx, r12d
0x180023e04  cmp     [rsp+150h+var_120], r12d
0x180023e09  jbe     short loc_180023E53
0x180023e0b  mov     rcx, [rsp+150h+var_108]
0x180023e10  lea     r8, [rsp+150h+var_118]
0x180023e15  mov     edx, ebx
0x180023e17  mov     rax, [rcx]
0x180023e1a  mov     rax, [rax+20h]
0x180023e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e23  mov     edi, eax
0x180023e25  test    eax, eax
0x180023e27  js      loc_180024143
0x180023e2d  mov     rdx, [rsp+150h+var_118]; struct INativeConfigurationElement *
0x180023e32  lea     rcx, [rsp+150h+var_E8]; this
0x180023e37  call    ?AddEntry@CONFIG_ELEMENT_LIST@@QEAAJPEAVINativeConfigurationElement@@K@Z; CONFIG_ELEMENT_LIST::AddEntry(INativeConfigurationElement *,ulong)
0x180023e3c  mov     edi, eax
0x180023e3e  test    eax, eax
0x180023e40  js      loc_180024143
0x180023e46  inc     ebx
0x180023e48  mov     [rsp+150h+var_118], r12
0x180023e4d  cmp     ebx, [rsp+150h+var_120]
0x180023e51  jb      short loc_180023E0B
0x180023e53  mov     rcx, [rsp+150h+var_108]
0x180023e58  mov     rax, [rcx]
0x180023e5b  mov     rax, [rax+10h]
0x180023e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e64  mov     rax, [r14]
0x180023e67  lea     rdx, [rsp+150h+var_110]
0x180023e6c  mov     rcx, r14
0x180023e6f  mov     [rsp+150h+var_108], r12
0x180023e74  mov     rax, [rax+28h]
0x180023e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e7d  mov     edi, eax
0x180023e7f  test    eax, eax
0x180023e81  js      loc_180024143
0x180023e87  mov     rcx, [rsp+150h+var_110]
0x180023e8c  lea     rdx, [rsp+150h+var_120]
0x180023e91  mov     rax, [rcx]
0x180023e94  mov     rax, [rax+48h]
0x180023e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e9d  mov     edi, eax
0x180023e9f  test    eax, eax
0x180023ea1  js      loc_180024143
0x180023ea7  mov     edx, [rsp+150h+var_120]
0x180023eab  mov     ebx, r12d
0x180023eae  test    edx, edx
0x180023eb0  jz      short loc_180023EDE
0x180023eb2  mov     rcx, [rsp+150h+var_110]
0x180023eb7  sub     edx, ebx
0x180023eb9  dec     edx
0x180023ebb  xor     r8d, r8d
0x180023ebe  mov     rax, [rcx]
0x180023ec1  mov     rax, [rax+60h]
0x180023ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eca  mov     edi, eax
0x180023ecc  test    eax, eax
0x180023ece  js      loc_180024143
0x180023ed4  mov     edx, [rsp+150h+var_120]
0x180023ed8  inc     ebx
0x180023eda  cmp     ebx, edx
0x180023edc  jb      short loc_180023EB2
0x180023ede  mov     r8d, [r15+0ACh]
0x180023ee5  lea     rdx, [rbp+50h+var_78]; struct STRU *
0x180023ee9  and     r8d, 1; int
0x180023eed  mov     rcx, rsi; this
0x180023ef0  call    ?GetLocationPath@ABO_NODE@@QEAAJPEAVSTRU@@H@Z; ABO_NODE::GetLocationPath(STRU *,int)
0x180023ef5  mov     edi, eax
0x180023ef7  test    eax, eax
0x180023ef9  js      loc_180024143
0x180023eff  lea     rcx, [r13+10h]
0x180023f03  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023f09  mov     rbx, [rax+18h]
0x180023f0d  cmp     [rbx], r12w
0x180023f11  jz      loc_180024143
0x180023f17  lea     r13, aFileextension; "fileExtension"
0x180023f1e  mov     edx, 1
0x180023f23  lea     r9, [rbp+50h+var_B0]
0x180023f27  mov     r8d, edx
0x180023f2a  mov     rcx, rbx
0x180023f2d  call    cs:__imp_?SplitCommaDelimitedString@@YAJPEBGHHPEAVMULTISZ@@@Z; SplitCommaDelimitedString(ushort const *,int,int,MULTISZ *)
0x180023f33  mov     edi, eax
0x180023f35  test    eax, eax
0x180023f37  js      loc_180024143
0x180023f3d  lea     rcx, [rbp+50h+var_B0]
0x180023f41  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180023f47  mov     rdx, rax
0x180023f4a  lea     rcx, [rbp+50h+var_B0]
0x180023f4e  mov     r14, rax
0x180023f51  call    cs:__imp_?Next@MULTISZ@@QEBAPEBGPEBG@Z; MULTISZ::Next(ushort const *)
0x180023f57  mov     r15, rax
0x180023f5a  test    rax, rax
0x180023f5d  jz      loc_180024137
0x180023f63  mov     esi, r12d
0x180023f66  cmp     [rsp+150h+var_E8], r12d
0x180023f6b  jbe     loc_180024067
0x180023f71  lea     rcx, [rsp+150h+var_E0]
0x180023f76  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023f7c  mov     ecx, esi
0x180023f7e  lea     r8, [rsp+150h+String2]
0x180023f83  xor     r9d, r9d
0x180023f86  mov     [rsp+150h+var_130], r12
0x180023f8b  mov     rdx, r13
0x180023f8e  mov     rcx, [rax+rcx*8]
0x180023f92  mov     rax, [rcx]
0x180023f95  mov     rax, [rax+40h]
0x180023f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f9e  mov     edi, eax
0x180023fa0  test    eax, eax
0x180023fa2  js      loc_180024143
0x180023fa8  mov     rdx, [rsp+150h+String2]; String2
0x180023fad  mov     rcx, r14; String1
0x180023fb0  call    cs:__imp__wcsicmp
0x180023fb6  test    eax, eax
0x180023fb8  jnz     loc_18002405B
0x180023fbe  lea     rcx, [rbp+50h+var_78]
0x180023fc2  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180023fc8  test    al, al
0x180023fca  jnz     loc_18002405B
0x180023fd0  mov     rcx, [rsp+150h+var_110]
0x180023fd5  lea     r8, [rsp+150h+var_100]
0x180023fda  lea     rdx, aRemove; "remove"
0x180023fe1  mov     rax, [rcx]
0x180023fe4  mov     rax, [rax+30h]
0x180023fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fed  mov     edi, eax
0x180023fef  test    eax, eax
0x180023ff1  js      loc_180024143
0x180023ff7  mov     rcx, [rsp+150h+var_100]
0x180023ffc  xor     r9d, r9d
0x180023fff  mov     r8, r14
0x180024002  mov     rdx, r13
0x180024005  mov     rax, [rcx]
0x180024008  mov     rax, [rax+80h]
0x18002400f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024014  mov     edi, eax
0x180024016  test    eax, eax
0x180024018  js      loc_180024143
0x18002401e  mov     rcx, [rsp+150h+var_110]
0x180024023  xor     r9d, r9d
0x180024026  mov     rdx, [rsp+150h+var_100]
0x18002402b  or      r8d, 0FFFFFFFFh
0x18002402f  mov     rax, [rcx]
0x180024032  mov     rax, [rax+38h]
0x180024036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002403b  mov     edi, eax
0x18002403d  test    eax, eax
0x18002403f  js      loc_180024143
0x180024045  mov     rcx, [rsp+150h+var_100]
0x18002404a  mov     rax, [rcx]
0x18002404d  mov     rax, [rax+10h]
0x180024051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024056  mov     [rsp+150h+var_100], r12
0x18002405b  inc     esi
0x18002405d  cmp     esi, [rsp+150h+var_E8]
0x180024061  jb      loc_180023F71
0x180024067  mov     rcx, [rsp+150h+var_110]
0x18002406c  lea     r8, [rsp+150h+var_118]
0x180024071  lea     rdx, aMimemap_0; "mimeMap"
0x180024078  mov     rax, [rcx]
0x18002407b  mov     rax, [rax+30h]
0x18002407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024084  mov     edi, eax
0x180024086  test    eax, eax
0x180024088  js      loc_180024143
0x18002408e  mov     rcx, [rsp+150h+var_118]
0x180024093  xor     r9d, r9d
0x180024096  mov     r8, r14
0x180024099  mov     rdx, r13
0x18002409c  mov     rax, [rcx]
0x18002409f  mov     rax, [rax+80h]
0x1800240a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240ab  mov     edi, eax
0x1800240ad  test    eax, eax
0x1800240af  js      loc_180024143
0x1800240b5  mov     rcx, [rsp+150h+var_118]
0x1800240ba  lea     rdx, aMimetype; "mimeType"
0x1800240c1  xor     r9d, r9d
0x1800240c4  mov     r8, r15
0x1800240c7  mov     rax, [rcx]
0x1800240ca  mov     rax, [rax+80h]
0x1800240d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240d6  mov     edi, eax
0x1800240d8  test    eax, eax
0x1800240da  js      short loc_180024143
0x1800240dc  mov     rcx, [rsp+150h+var_110]
0x1800240e1  xor     r9d, r9d
0x1800240e4  mov     rdx, [rsp+150h+var_118]
0x1800240e9  or      r8d, 0FFFFFFFFh
0x1800240ed  mov     rax, [rcx]
0x1800240f0  mov     rax, [rax+38h]
0x1800240f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240f9  mov     edi, eax
0x1800240fb  test    eax, eax
0x1800240fd  js      short loc_180024143
0x1800240ff  mov     rcx, [rsp+150h+var_118]
0x180024104  mov     rax, [rcx]
0x180024107  mov     rax, [rax+10h]
0x18002410b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024110  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024114  mov     [rsp+150h+var_118], r12
0x180024119  inc     rax
0x18002411c  cmp     [rbx+rax*2], r12w
0x180024121  jnz     short loc_180024119
0x180024123  lea     rbx, [rbx+rax*2]
0x180024127  add     rbx, 2
0x18002412b  cmp     [rbx], r12w
0x18002412f  jnz     loc_180023F1E
0x180024135  jmp     short loc_180024143
0x180024137  mov     edi, 8007000Dh
0x18002413c  jmp     short loc_180024143
0x18002413e  mov     edi, 80070057h
0x180024143  mov     rcx, [rsp+150h+var_F8]
0x180024148  test    rcx, rcx
0x18002414b  jz      short loc_18002415E
0x18002414d  mov     rax, [rcx]
0x180024150  mov     rax, [rax+10h]
0x180024154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024159  mov     [rsp+150h+var_F8], r12
0x18002415e  mov     rcx, [rsp+150h+var_108]
0x180024163  test    rcx, rcx
0x180024166  jz      short loc_180024179
0x180024168  mov     rax, [rcx]
0x18002416b  mov     rax, [rax+10h]
0x18002416f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024174  mov     [rsp+150h+var_108], r12
0x180024179  mov     rcx, [rsp+150h+var_118]
0x18002417e  test    rcx, rcx
0x180024181  jz      short loc_180024194
0x180024183  mov     rax, [rcx]
0x180024186  mov     rax, [rax+10h]
0x18002418a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002418f  mov     [rsp+150h+var_118], r12
0x180024194  mov     rcx, [rsp+150h+var_100]
0x180024199  test    rcx, rcx
0x18002419c  jz      short loc_1800241AF
  ... truncated ...
```

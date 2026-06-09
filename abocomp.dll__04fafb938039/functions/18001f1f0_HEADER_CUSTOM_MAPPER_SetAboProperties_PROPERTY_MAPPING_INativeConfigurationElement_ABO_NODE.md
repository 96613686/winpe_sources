# HEADER_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001f1f0`
- end: `0x18001f585`
- name: `?SetAboProperties@HEADER_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `917`
- prototype: `int(HEADER_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001f1f0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4c1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f3dd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001f3dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f25b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f25b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f557`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f557`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f425`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f425`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f3f8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f411`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f3f8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001f411`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001f274`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001f274`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001f496`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001f496`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001f432`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001f432`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001f4a4`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001f4a4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001f54d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001f54d`

## string_xrefs

- `0x18001f2aa`: `system.webServer/httpProtocol`

## pseudocode

```c
__int64 __fastcall HEADER_CUSTOM_MAPPER::SetAboProperties(
        HEADER_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  signed int MergedConfigElement; // ebx
  unsigned int v8; // edi
  const unsigned __int16 *Str; // rax
  signed int LastError; // eax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v18; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v19; // [rsp+68h] [rbp-98h] BYREF
  struct _METADATA_RECORD v20; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v21[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v23[256]; // [rsp+110h] [rbp+10h] BYREF

  v13 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v21, v23, 0x100u);
  v18 = 0;
  v19 = 0;
  v12 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v22);
  v17 = 0;
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/httpProtocol",
                            &v15,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 24LL))(
                              a3,
                              &v17);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v15 + 32LL))(
                                v15,
                                v17,
                                &v16);
        if ( MergedConfigElement >= 0 )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 40LL))(v16, &v14);
          if ( MergedConfigElement >= 0 )
          {
            MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 24LL))(
                                    v14,
                                    &v12);
            if ( MergedConfigElement >= 0 )
            {
              v8 = 0;
              if ( v12 )
              {
                while ( 1 )
                {
                  MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 32LL))(
                                          v14,
                                          v8,
                                          &v13);
                  if ( MergedConfigElement < 0 )
                    break;
                  MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                                          v13,
                                          L"name",
                                          &v18,
                                          0,
                                          0);
                  if ( MergedConfigElement < 0 )
                    break;
                  MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                                          v13,
                                          L"value",
                                          &v19,
                                          0,
                                          0);
                  if ( MergedConfigElement < 0 )
                    break;
                  MergedConfigElement = STRU::Copy((STRU *)v21, v18);
                  if ( MergedConfigElement < 0 )
                    break;
                  MergedConfigElement = STRU::Append((STRU *)v21, L": ");
                  if ( MergedConfigElement < 0 )
                    break;
                  MergedConfigElement = STRU::Append((STRU *)v21, v19);
                  if ( MergedConfigElement < 0 )
                    break;
                  Str = STRU::QueryStr((STRU *)v21);
                  if ( !MULTISZ::Append((MULTISZ *)v22, Str) )
                  {
                    LastError = GetLastError();
                    MergedConfigElement = LastError;
                    if ( LastError > 0 )
                      MergedConfigElement = (unsigned __int16)LastError | 0x80070000;
                    break;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  ++v8;
                  v13 = 0;
                  if ( v8 >= v12 )
                    goto LABEL_18;
                }
              }
              else
              {
LABEL_18:
                v20.dwMDIdentifier = *((_DWORD *)a2 + 36);
                v20.dwMDUserType = *((_DWORD *)a2 + 37);
                v20.dwMDDataType = *((_DWORD *)a2 + 38);
                v20.dwMDAttributes = *((_DWORD *)a2 + 39);
                *(&v20.dwMDDataLen + 1) = 0;
                *(_QWORD *)&v20.dwMDDataTag = 0;
                v20.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v22);
                v20.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v22);
                MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v20, a2);
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
  if ( v15 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v22);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001f1f0  mov     [rsp-8+arg_0], rbx
0x18001f1f5  push    rbp
0x18001f1f6  push    rsi
0x18001f1f7  push    rdi
0x18001f1f8  push    r14
0x18001f1fa  push    r15
0x18001f1fc  lea     rbp, [rsp-220h]
0x18001f204  sub     rsp, 320h
0x18001f20b  mov     rax, cs:__security_cookie
0x18001f212  xor     rax, rsp
0x18001f215  mov     [rbp+240h+var_30], rax
0x18001f21c  xor     r15d, r15d
0x18001f21f  lea     rcx, [rbp+240h+var_230]; void *
0x18001f223  mov     rdi, r8
0x18001f226  mov     [rsp+340h+var_308], r15
0x18001f22b  mov     rsi, rdx
0x18001f22e  mov     [rsp+340h+var_2F0], r15
0x18001f233  xor     edx, edx; Val
0x18001f235  mov     [rsp+340h+var_2F8], r15
0x18001f23a  mov     r8d, 200h; Size
0x18001f240  mov     [rsp+340h+var_300], r15
0x18001f245  mov     r14, r9
0x18001f248  call    memset_0
0x18001f24d  mov     r8d, 100h
0x18001f253  lea     rdx, [rbp+240h+var_230]
0x18001f257  lea     rcx, [rbp+240h+var_2A8]
0x18001f25b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f261  lea     rcx, [rbp+240h+var_270]
0x18001f265  mov     [rsp+340h+var_2E0], r15
0x18001f26a  mov     [rsp+340h+var_2D8], r15
0x18001f26f  mov     [rsp+340h+var_310], r15d
0x18001f274  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001f27a  mov     [rsp+340h+var_2E8], r15
0x18001f27f  test    rsi, rsi
0x18001f282  jz      loc_18001F4D8
0x18001f288  test    rdi, rdi
0x18001f28b  jz      loc_18001F4D8
0x18001f291  test    r14, r14
0x18001f294  jz      loc_18001F4D8
0x18001f29a  mov     r9d, [rsi+0ACh]
0x18001f2a1  lea     r8, [rsp+340h+var_2F8]; struct INativeConfigurationElement **
0x18001f2a6  and     r9d, 1; int
0x18001f2aa  lea     rdx, aSystemWebserve_24; "system.webServer/httpProtocol"
0x18001f2b1  mov     rcx, r14; this
0x18001f2b4  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001f2b9  mov     ebx, eax
0x18001f2bb  test    eax, eax
0x18001f2bd  js      loc_18001F4DD
0x18001f2c3  mov     rax, [rdi]
0x18001f2c6  lea     rdx, [rsp+340h+var_2E8]
0x18001f2cb  mov     rcx, rdi
0x18001f2ce  mov     rax, [rax+18h]
0x18001f2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2d7  mov     ebx, eax
0x18001f2d9  test    eax, eax
0x18001f2db  js      loc_18001F4DD
0x18001f2e1  mov     rcx, [rsp+340h+var_2F8]
0x18001f2e6  lea     r8, [rsp+340h+var_2F0]
0x18001f2eb  mov     rdx, [rsp+340h+var_2E8]
0x18001f2f0  mov     rax, [rcx]
0x18001f2f3  mov     rax, [rax+20h]
0x18001f2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fc  mov     ebx, eax
0x18001f2fe  test    eax, eax
0x18001f300  js      loc_18001F4DD
0x18001f306  mov     rcx, [rsp+340h+var_2F0]
0x18001f30b  lea     rdx, [rsp+340h+var_300]
0x18001f310  mov     rax, [rcx]
0x18001f313  mov     rax, [rax+28h]
0x18001f317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f31c  mov     ebx, eax
0x18001f31e  test    eax, eax
0x18001f320  js      loc_18001F4DD
0x18001f326  mov     rcx, [rsp+340h+var_300]
0x18001f32b  lea     rdx, [rsp+340h+var_310]
0x18001f330  mov     rax, [rcx]
0x18001f333  mov     rax, [rax+18h]
0x18001f337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f33c  mov     ebx, eax
0x18001f33e  test    eax, eax
0x18001f340  js      loc_18001F4DD
0x18001f346  mov     edi, r15d
0x18001f349  cmp     [rsp+340h+var_310], r15d
0x18001f34e  jbe     loc_18001F462
0x18001f354  mov     rcx, [rsp+340h+var_300]
0x18001f359  lea     r8, [rsp+340h+var_308]
0x18001f35e  mov     edx, edi
0x18001f360  mov     rax, [rcx]
0x18001f363  mov     rax, [rax+20h]
0x18001f367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f36c  mov     ebx, eax
0x18001f36e  test    eax, eax
0x18001f370  js      loc_18001F4DD
0x18001f376  mov     rcx, [rsp+340h+var_308]
0x18001f37b  lea     r8, [rsp+340h+var_2E0]
0x18001f380  xor     r9d, r9d
0x18001f383  mov     [rsp+340h+var_320], r15
0x18001f388  lea     rdx, aName; "name"
0x18001f38f  mov     rax, [rcx]
0x18001f392  mov     rax, [rax+40h]
0x18001f396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f39b  mov     ebx, eax
0x18001f39d  test    eax, eax
0x18001f39f  js      loc_18001F4DD
0x18001f3a5  mov     rcx, [rsp+340h+var_308]
0x18001f3aa  lea     r8, [rsp+340h+var_2D8]
0x18001f3af  xor     r9d, r9d
0x18001f3b2  mov     [rsp+340h+var_320], r15
0x18001f3b7  lea     rdx, aValue; "value"
0x18001f3be  mov     rax, [rcx]
0x18001f3c1  mov     rax, [rax+40h]
0x18001f3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3ca  mov     ebx, eax
0x18001f3cc  test    eax, eax
0x18001f3ce  js      loc_18001F4DD
0x18001f3d4  mov     rdx, [rsp+340h+var_2E0]
0x18001f3d9  lea     rcx, [rbp+240h+var_2A8]
0x18001f3dd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001f3e3  mov     ebx, eax
0x18001f3e5  test    eax, eax
0x18001f3e7  js      loc_18001F4DD
0x18001f3ed  lea     rdx, asc_180034724; ": "
0x18001f3f4  lea     rcx, [rbp+240h+var_2A8]
0x18001f3f8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001f3fe  mov     ebx, eax
0x18001f400  test    eax, eax
0x18001f402  js      loc_18001F4DD
0x18001f408  mov     rdx, [rsp+340h+var_2D8]
0x18001f40d  lea     rcx, [rbp+240h+var_2A8]
0x18001f411  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001f417  mov     ebx, eax
0x18001f419  test    eax, eax
0x18001f41b  js      loc_18001F4DD
0x18001f421  lea     rcx, [rbp+240h+var_2A8]
0x18001f425  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001f42b  mov     rdx, rax
0x18001f42e  lea     rcx, [rbp+240h+var_270]
0x18001f432  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001f438  test    eax, eax
0x18001f43a  jz      loc_18001F4C1
0x18001f440  mov     rcx, [rsp+340h+var_308]
0x18001f445  mov     rax, [rcx]
0x18001f448  mov     rax, [rax+10h]
0x18001f44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f451  inc     edi
0x18001f453  mov     [rsp+340h+var_308], r15
0x18001f458  cmp     edi, [rsp+340h+var_310]
0x18001f45c  jb      loc_18001F354
0x18001f462  mov     eax, [rsi+90h]
0x18001f468  lea     rcx, [rbp+240h+var_270]
0x18001f46c  mov     [rsp+340h+var_2D0.dwMDIdentifier], eax
0x18001f470  mov     eax, [rsi+94h]
0x18001f476  mov     [rsp+340h+var_2D0.dwMDUserType], eax
0x18001f47a  mov     eax, [rsi+98h]
0x18001f480  mov     [rsp+340h+var_2D0.dwMDDataType], eax
0x18001f484  mov     eax, [rsi+9Ch]
0x18001f48a  mov     [rsp+340h+var_2D0.dwMDAttributes], eax
0x18001f48e  mov     dword ptr [rbp+240h+var_2D0+14h], r15d
0x18001f492  mov     qword ptr [rbp+240h+var_2D0.dwMDDataTag], r15
0x18001f496  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x18001f49c  lea     rcx, [rbp+240h+var_270]
0x18001f4a0  mov     [rbp+240h+var_2D0.pbMDData], rax
0x18001f4a4  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x18001f4aa  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001f4ad  lea     rdx, [rsp+340h+var_2D0]; struct _METADATA_RECORD *
0x18001f4b2  mov     rcx, r14; this
0x18001f4b5  mov     [rbp+240h+var_2D0.dwMDDataLen], eax
0x18001f4b8  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001f4bd  mov     ebx, eax
0x18001f4bf  jmp     short loc_18001F4DD
0x18001f4c1  call    cs:__imp_GetLastError
0x18001f4c7  mov     ebx, eax
0x18001f4c9  test    eax, eax
0x18001f4cb  jle     short loc_18001F4DD
0x18001f4cd  movzx   ebx, ax
0x18001f4d0  or      ebx, 80070000h
0x18001f4d6  jmp     short loc_18001F4DD
0x18001f4d8  mov     ebx, 80070057h
0x18001f4dd  mov     rcx, [rsp+340h+var_2F8]
0x18001f4e2  test    rcx, rcx
0x18001f4e5  jz      short loc_18001F4F8
0x18001f4e7  mov     rax, [rcx]
0x18001f4ea  mov     rax, [rax+10h]
0x18001f4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f3  mov     [rsp+340h+var_2F8], r15
0x18001f4f8  mov     rcx, [rsp+340h+var_2F0]
0x18001f4fd  test    rcx, rcx
0x18001f500  jz      short loc_18001F513
0x18001f502  mov     rax, [rcx]
0x18001f505  mov     rax, [rax+10h]
0x18001f509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f50e  mov     [rsp+340h+var_2F0], r15
0x18001f513  mov     rcx, [rsp+340h+var_308]
0x18001f518  test    rcx, rcx
0x18001f51b  jz      short loc_18001F52E
0x18001f51d  mov     rax, [rcx]
0x18001f520  mov     rax, [rax+10h]
0x18001f524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f529  mov     [rsp+340h+var_308], r15
0x18001f52e  mov     rcx, [rsp+340h+var_300]
0x18001f533  test    rcx, rcx
0x18001f536  jz      short loc_18001F549
0x18001f538  mov     rax, [rcx]
0x18001f53b  mov     rax, [rax+10h]
0x18001f53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f544  mov     [rsp+340h+var_300], r15
0x18001f549  lea     rcx, [rbp+240h+var_270]
0x18001f54d  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001f553  lea     rcx, [rbp+240h+var_2A8]
0x18001f557  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f55d  mov     eax, ebx
0x18001f55f  mov     rcx, [rbp+240h+var_30]
0x18001f566  xor     rcx, rsp; StackCookie
0x18001f569  call    __security_check_cookie
0x18001f56e  mov     rbx, [rsp+340h+arg_0]
0x18001f576  add     rsp, 320h
0x18001f57d  pop     r15
0x18001f57f  pop     r14
0x18001f581  pop     rdi
0x18001f582  pop     rsi
0x18001f583  pop     rbp
0x18001f584  retn
```

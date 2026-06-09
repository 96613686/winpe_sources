# DEPENDENCIES_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001e820`
- end: `0x18001ecab`
- name: `?SetAboProperties@DEPENDENCIES_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `1163`
- prototype: `int(DEPENDENCIES_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001e820`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9d6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001e9d6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e896`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001e896`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ec78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ec78`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001eb13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001eb13`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e9f1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ea0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001eac4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001eadd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001e9f1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ea0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001eac4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001eadd`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001e8af`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18001e8af`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001eb9c`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18001eb9c`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001eb20`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001eb20`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001ebaa`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x18001ebaa`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001ec6e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001ec6e`

## string_xrefs

- `0x18001e8e5`: `system.webServer/security/applicationDependencies`

## pseudocode

```c
__int64 __fastcall DEPENDENCIES_CUSTOM_MAPPER::SetAboProperties(
        DEPENDENCIES_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  signed int MergedConfigElement; // ebx
  unsigned int v8; // r14d
  unsigned int i; // edi
  const unsigned __int16 *Str; // rax
  signed int LastError; // eax
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v15; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v19; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v20; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v21; // [rsp+68h] [rbp-98h] BYREF
  struct _METADATA_RECORD v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v24[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v25[256]; // [rsp+110h] [rbp+10h] BYREF

  v13 = 0;
  v17 = 0;
  v20 = 0;
  v18 = 0;
  v16 = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v23, v25, 0x100u);
  v21 = 0;
  v19 = 0;
  v15 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v24);
  v14 = 0;
  if ( a2 && a3 && a4 )
  {
    MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                            a4,
                            L"system.webServer/security/applicationDependencies",
                            &v20,
                            *((_DWORD *)a2 + 43) & 1);
    if ( MergedConfigElement >= 0 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v20 + 40LL))(
                              v20,
                              &v18);
      if ( MergedConfigElement >= 0 )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 24LL))(v18, &v15);
        if ( MergedConfigElement >= 0 )
        {
          v8 = 0;
          if ( v15 )
          {
            while ( 1 )
            {
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 32LL))(
                                      v18,
                                      v8,
                                      &v13);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                                      v13,
                                      L"name",
                                      &v21,
                                      0,
                                      0);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                                      v13,
                                      L"groupId",
                                      &v19,
                                      0,
                                      0);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = STRU::Copy((STRU *)v23, v21);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = STRU::Append((STRU *)v23, L";");
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = STRU::Append((STRU *)v23, v19);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 40LL))(v13, &v16);
              if ( MergedConfigElement < 0 )
                break;
              MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 24LL))(
                                      v16,
                                      &v14);
              if ( MergedConfigElement < 0 )
                break;
              for ( i = 0; i < v14; v17 = 0 )
              {
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 32LL))(
                                        v16,
                                        i,
                                        &v17);
                if ( MergedConfigElement < 0 )
                  goto LABEL_28;
                MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                                        v17,
                                        L"groupId",
                                        &v19,
                                        0,
                                        0);
                if ( MergedConfigElement < 0 )
                  goto LABEL_28;
                MergedConfigElement = STRU::Append((STRU *)v23, L",");
                if ( MergedConfigElement < 0 )
                  goto LABEL_28;
                MergedConfigElement = STRU::Append((STRU *)v23, v19);
                if ( MergedConfigElement < 0 )
                  goto LABEL_28;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                ++i;
              }
              Str = STRU::QueryStr((STRU *)v23);
              if ( !MULTISZ::Append((MULTISZ *)v24, Str) )
              {
                LastError = GetLastError();
                MergedConfigElement = LastError;
                if ( LastError > 0 )
                  MergedConfigElement = (unsigned __int16)LastError | 0x80070000;
                break;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              ++v8;
              v13 = 0;
              if ( v8 >= v15 )
                goto LABEL_24;
            }
          }
          else
          {
LABEL_24:
            v22.dwMDIdentifier = *((_DWORD *)a2 + 36);
            v22.dwMDUserType = *((_DWORD *)a2 + 37);
            v22.dwMDDataType = *((_DWORD *)a2 + 38);
            v22.dwMDAttributes = *((_DWORD *)a2 + 39);
            *(&v22.dwMDDataLen + 1) = 0;
            *(_QWORD *)&v22.dwMDDataTag = 0;
            v22.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v24);
            v22.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v24);
            MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v22, a2);
          }
        }
      }
    }
  }
  else
  {
    MergedConfigElement = -2147024809;
  }
LABEL_28:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v24);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001e820  mov     [rsp-8+arg_0], rbx
0x18001e825  mov     [rsp-8+arg_8], rsi
0x18001e82a  push    rbp
0x18001e82b  push    rdi
0x18001e82c  push    r12
0x18001e82e  push    r14
0x18001e830  push    r15
0x18001e832  lea     rbp, [rsp-220h]
0x18001e83a  sub     rsp, 320h
0x18001e841  mov     rax, cs:__security_cookie
0x18001e848  xor     rax, rsp
0x18001e84b  mov     [rbp+240h+var_30], rax
0x18001e852  xor     r12d, r12d
0x18001e855  lea     rcx, [rbp+240h+var_230]; void *
0x18001e859  mov     rbx, r8
0x18001e85c  mov     [rsp+340h+var_310], r12
0x18001e861  mov     rsi, rdx
0x18001e864  mov     [rsp+340h+var_2F8], r12
0x18001e869  xor     edx, edx; Val
0x18001e86b  mov     [rsp+340h+var_2E0], r12
0x18001e870  mov     r8d, 200h; Size
0x18001e876  mov     [rsp+340h+var_2F0], r12
0x18001e87b  mov     [rsp+340h+var_300], r12
0x18001e880  mov     r15, r9
0x18001e883  call    memset_0
0x18001e888  mov     r8d, 100h
0x18001e88e  lea     rdx, [rbp+240h+var_230]
0x18001e892  lea     rcx, [rbp+240h+var_2A8]
0x18001e896  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001e89c  lea     rcx, [rbp+240h+var_270]
0x18001e8a0  mov     [rsp+340h+var_2D8], r12
0x18001e8a5  mov     [rsp+340h+var_2E8], r12
0x18001e8aa  mov     [rsp+340h+var_304], r12d
0x18001e8af  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18001e8b5  mov     [rsp+340h+var_308], r12d
0x18001e8ba  test    rsi, rsi
0x18001e8bd  jz      loc_18001EBDE
0x18001e8c3  test    rbx, rbx
0x18001e8c6  jz      loc_18001EBDE
0x18001e8cc  test    r15, r15
0x18001e8cf  jz      loc_18001EBDE
0x18001e8d5  mov     r9d, [rsi+0ACh]
0x18001e8dc  lea     r8, [rsp+340h+var_2E0]; struct INativeConfigurationElement **
0x18001e8e1  and     r9d, 1; int
0x18001e8e5  lea     rdx, aSystemWebserve_9; "system.webServer/security/applicationDe"...
0x18001e8ec  mov     rcx, r15; this
0x18001e8ef  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001e8f4  mov     ebx, eax
0x18001e8f6  test    eax, eax
0x18001e8f8  js      loc_18001EBE3
0x18001e8fe  mov     rcx, [rsp+340h+var_2E0]
0x18001e903  lea     rdx, [rsp+340h+var_2F0]
0x18001e908  mov     rax, [rcx]
0x18001e90b  mov     rax, [rax+28h]
0x18001e90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e914  mov     ebx, eax
0x18001e916  test    eax, eax
0x18001e918  js      loc_18001EBE3
0x18001e91e  mov     rcx, [rsp+340h+var_2F0]
0x18001e923  lea     rdx, [rsp+340h+var_304]
0x18001e928  mov     rax, [rcx]
0x18001e92b  mov     rax, [rax+18h]
0x18001e92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e934  mov     ebx, eax
0x18001e936  test    eax, eax
0x18001e938  js      loc_18001EBE3
0x18001e93e  mov     r14d, r12d
0x18001e941  cmp     [rsp+340h+var_304], r12d
0x18001e946  jbe     loc_18001EB68
0x18001e94c  mov     rcx, [rsp+340h+var_2F0]
0x18001e951  lea     r8, [rsp+340h+var_310]
0x18001e956  mov     edx, r14d
0x18001e959  mov     rax, [rcx]
0x18001e95c  mov     rax, [rax+20h]
0x18001e960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e965  mov     ebx, eax
0x18001e967  test    eax, eax
0x18001e969  js      loc_18001EBE3
0x18001e96f  mov     rcx, [rsp+340h+var_310]
0x18001e974  lea     r8, [rsp+340h+var_2D8]
0x18001e979  xor     r9d, r9d
0x18001e97c  mov     [rsp+340h+var_320], r12
0x18001e981  lea     rdx, aName; "name"
0x18001e988  mov     rax, [rcx]
0x18001e98b  mov     rax, [rax+40h]
0x18001e98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e994  mov     ebx, eax
0x18001e996  test    eax, eax
0x18001e998  js      loc_18001EBE3
0x18001e99e  mov     rcx, [rsp+340h+var_310]
0x18001e9a3  lea     r8, [rsp+340h+var_2E8]
0x18001e9a8  xor     r9d, r9d
0x18001e9ab  mov     [rsp+340h+var_320], r12
0x18001e9b0  lea     rdx, aGroupid; "groupId"
0x18001e9b7  mov     rax, [rcx]
0x18001e9ba  mov     rax, [rax+40h]
0x18001e9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9c3  mov     ebx, eax
0x18001e9c5  test    eax, eax
0x18001e9c7  js      loc_18001EBE3
0x18001e9cd  mov     rdx, [rsp+340h+var_2D8]
0x18001e9d2  lea     rcx, [rbp+240h+var_2A8]
0x18001e9d6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001e9dc  mov     ebx, eax
0x18001e9de  test    eax, eax
0x18001e9e0  js      loc_18001EBE3
0x18001e9e6  lea     rdx, asc_180034580; ";"
0x18001e9ed  lea     rcx, [rbp+240h+var_2A8]
0x18001e9f1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001e9f7  mov     ebx, eax
0x18001e9f9  test    eax, eax
0x18001e9fb  js      loc_18001EBE3
0x18001ea01  mov     rdx, [rsp+340h+var_2E8]
0x18001ea06  lea     rcx, [rbp+240h+var_2A8]
0x18001ea0a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001ea10  mov     ebx, eax
0x18001ea12  test    eax, eax
0x18001ea14  js      loc_18001EBE3
0x18001ea1a  mov     rcx, [rsp+340h+var_310]
0x18001ea1f  lea     rdx, [rsp+340h+var_300]
0x18001ea24  mov     rax, [rcx]
0x18001ea27  mov     rax, [rax+28h]
0x18001ea2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea30  mov     ebx, eax
0x18001ea32  test    eax, eax
0x18001ea34  js      loc_18001EBE3
0x18001ea3a  mov     rcx, [rsp+340h+var_300]
0x18001ea3f  lea     rdx, [rsp+340h+var_308]
0x18001ea44  mov     rax, [rcx]
0x18001ea47  mov     rax, [rax+18h]
0x18001ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea50  mov     ebx, eax
0x18001ea52  test    eax, eax
0x18001ea54  js      loc_18001EBE3
0x18001ea5a  mov     edi, r12d
0x18001ea5d  cmp     [rsp+340h+var_308], r12d
0x18001ea62  jbe     loc_18001EB0F
0x18001ea68  mov     rcx, [rsp+340h+var_300]
0x18001ea6d  lea     r8, [rsp+340h+var_2F8]
0x18001ea72  mov     edx, edi
0x18001ea74  mov     rax, [rcx]
0x18001ea77  mov     rax, [rax+20h]
0x18001ea7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea80  mov     ebx, eax
0x18001ea82  test    eax, eax
0x18001ea84  js      loc_18001EBE3
0x18001ea8a  mov     rcx, [rsp+340h+var_2F8]
0x18001ea8f  lea     r8, [rsp+340h+var_2E8]
0x18001ea94  xor     r9d, r9d
0x18001ea97  mov     [rsp+340h+var_320], r12
0x18001ea9c  lea     rdx, aGroupid; "groupId"
0x18001eaa3  mov     rax, [rcx]
0x18001eaa6  mov     rax, [rax+40h]
0x18001eaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaaf  mov     ebx, eax
0x18001eab1  test    eax, eax
0x18001eab3  js      loc_18001EBE3
0x18001eab9  lea     rdx, asc_180032E60; ","
0x18001eac0  lea     rcx, [rbp+240h+var_2A8]
0x18001eac4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001eaca  mov     ebx, eax
0x18001eacc  test    eax, eax
0x18001eace  js      loc_18001EBE3
0x18001ead4  mov     rdx, [rsp+340h+var_2E8]
0x18001ead9  lea     rcx, [rbp+240h+var_2A8]
0x18001eadd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001eae3  mov     ebx, eax
0x18001eae5  test    eax, eax
0x18001eae7  js      loc_18001EBE3
0x18001eaed  mov     rcx, [rsp+340h+var_2F8]
0x18001eaf2  mov     rax, [rcx]
0x18001eaf5  mov     rax, [rax+10h]
0x18001eaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eafe  inc     edi
0x18001eb00  mov     [rsp+340h+var_2F8], r12
0x18001eb05  cmp     edi, [rsp+340h+var_308]
0x18001eb09  jb      loc_18001EA68
0x18001eb0f  lea     rcx, [rbp+240h+var_2A8]
0x18001eb13  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001eb19  mov     rdx, rax
0x18001eb1c  lea     rcx, [rbp+240h+var_270]
0x18001eb20  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001eb26  test    eax, eax
0x18001eb28  jz      loc_18001EBC7
0x18001eb2e  mov     rcx, [rsp+340h+var_300]
0x18001eb33  mov     rax, [rcx]
0x18001eb36  mov     rax, [rax+10h]
0x18001eb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb3f  mov     rcx, [rsp+340h+var_310]
0x18001eb44  mov     [rsp+340h+var_300], r12
0x18001eb49  mov     rax, [rcx]
0x18001eb4c  mov     rax, [rax+10h]
0x18001eb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb55  inc     r14d
0x18001eb58  mov     [rsp+340h+var_310], r12
0x18001eb5d  cmp     r14d, [rsp+340h+var_304]
0x18001eb62  jb      loc_18001E94C
0x18001eb68  mov     eax, [rsi+90h]
0x18001eb6e  lea     rcx, [rbp+240h+var_270]
0x18001eb72  mov     [rsp+340h+var_2D0.dwMDIdentifier], eax
0x18001eb76  mov     eax, [rsi+94h]
0x18001eb7c  mov     [rsp+340h+var_2D0.dwMDUserType], eax
0x18001eb80  mov     eax, [rsi+98h]
0x18001eb86  mov     [rsp+340h+var_2D0.dwMDDataType], eax
0x18001eb8a  mov     eax, [rsi+9Ch]
0x18001eb90  mov     [rsp+340h+var_2D0.dwMDAttributes], eax
0x18001eb94  mov     dword ptr [rbp+240h+var_2D0+14h], r12d
0x18001eb98  mov     qword ptr [rbp+240h+var_2D0.dwMDDataTag], r12
0x18001eb9c  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x18001eba2  lea     rcx, [rbp+240h+var_270]
0x18001eba6  mov     [rbp+240h+var_2D0.pbMDData], rax
0x18001ebaa  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x18001ebb0  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001ebb3  lea     rdx, [rsp+340h+var_2D0]; struct _METADATA_RECORD *
0x18001ebb8  mov     rcx, r15; this
0x18001ebbb  mov     [rbp+240h+var_2D0.dwMDDataLen], eax
0x18001ebbe  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001ebc3  mov     ebx, eax
0x18001ebc5  jmp     short loc_18001EBE3
0x18001ebc7  call    cs:__imp_GetLastError
0x18001ebcd  mov     ebx, eax
0x18001ebcf  test    eax, eax
0x18001ebd1  jle     short loc_18001EBE3
0x18001ebd3  movzx   ebx, ax
0x18001ebd6  or      ebx, 80070000h
0x18001ebdc  jmp     short loc_18001EBE3
0x18001ebde  mov     ebx, 80070057h
0x18001ebe3  mov     rcx, [rsp+340h+var_2E0]
0x18001ebe8  test    rcx, rcx
0x18001ebeb  jz      short loc_18001EBFE
0x18001ebed  mov     rax, [rcx]
0x18001ebf0  mov     rax, [rax+10h]
0x18001ebf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf9  mov     [rsp+340h+var_2E0], r12
0x18001ebfe  mov     rcx, [rsp+340h+var_2F8]
0x18001ec03  test    rcx, rcx
0x18001ec06  jz      short loc_18001EC19
0x18001ec08  mov     rax, [rcx]
0x18001ec0b  mov     rax, [rax+10h]
0x18001ec0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec14  mov     [rsp+340h+var_2F8], r12
0x18001ec19  mov     rcx, [rsp+340h+var_310]
0x18001ec1e  test    rcx, rcx
0x18001ec21  jz      short loc_18001EC34
0x18001ec23  mov     rax, [rcx]
0x18001ec26  mov     rax, [rax+10h]
0x18001ec2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec2f  mov     [rsp+340h+var_310], r12
0x18001ec34  mov     rcx, [rsp+340h+var_2F0]
0x18001ec39  test    rcx, rcx
0x18001ec3c  jz      short loc_18001EC4F
0x18001ec3e  mov     rax, [rcx]
0x18001ec41  mov     rax, [rax+10h]
0x18001ec45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec4a  mov     [rsp+340h+var_2F0], r12
0x18001ec4f  mov     rcx, [rsp+340h+var_300]
0x18001ec54  test    rcx, rcx
0x18001ec57  jz      short loc_18001EC6A
0x18001ec59  mov     rax, [rcx]
0x18001ec5c  mov     rax, [rax+10h]
0x18001ec60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec65  mov     [rsp+340h+var_300], r12
0x18001ec6a  lea     rcx, [rbp+240h+var_270]
0x18001ec6e  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001ec74  lea     rcx, [rbp+240h+var_2A8]
0x18001ec78  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ec7e  mov     eax, ebx
0x18001ec80  mov     rcx, [rbp+240h+var_30]
0x18001ec87  xor     rcx, rsp; StackCookie
0x18001ec8a  call    __security_check_cookie
0x18001ec8f  lea     r11, [rsp+340h+var_20]
0x18001ec97  mov     rbx, [r11+30h]
0x18001ec9b  mov     rsi, [r11+38h]
0x18001ec9f  mov     rsp, r11
0x18001eca2  pop     r15
0x18001eca4  pop     r14
0x18001eca6  pop     r12
0x18001eca8  pop     rdi
0x18001eca9  pop     rbp
0x18001ecaa  retn
```

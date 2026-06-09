# CERTIFICATE_MAPPING_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18002b940`
- end: `0x18002bbe8`
- name: `?MapSetData@CERTIFICATE_MAPPING_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(CERTIFICATE_MAPPING_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003426`
- `0x180003460`
- `0x1800034f0`
- `0x180003f14`
- `0x1800047e4`
- `0x1800187e0`
- `0x18002b940`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba49`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002bb2d`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002bb2d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b9f7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba0c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba18`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba6c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002bb49`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b9f7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba0c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba18`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002ba6c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002bb49`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b9c8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b9c8`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bbb6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002bbb6`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b99e`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b99e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002bbab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002bbab`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ba9d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ba9d`
- `iisutil!uuencode` at `0x18002ba2c`
- `iisutil!uuencode` at `0x18002ba2c`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002ba7a`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002ba7a`

## string_xrefs

- `0x18002ba3d`: `Could not encode certificate to apphost.config file`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_MAPPING_PROVIDER::MapSetData(
        CERTIFICATE_MAPPING_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  int v6; // ebx
  unsigned int v7; // ebx
  unsigned __int8 **Ptr; // rax
  signed int LastError; // eax
  const char *v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  struct INativeConfigurationElement *v14; // rax
  HANDLE_ENTRY *v15; // rdi
  int Key; // eax
  int v17; // r12d
  __int64 v18; // rsi
  const wchar_t *v19; // rax
  _DWORD *v20; // rax
  HANDLE_ENTRY *v22; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeConfigurationElement *v23; // [rsp+38h] [rbp-C8h]
  _BYTE v24[48]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[64]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v26[1504]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v27[1504]; // [rsp+690h] [rbp+590h] BYREF

  memset_0(v26, 0, sizeof(v26));
  BUFFER::BUFFER((BUFFER *)v24, v26, 0x5E0u);
  memset_0(v27, 0, 0xBB8u);
  STRU::STRU((STRU *)v25, v27, 0x5DCu);
  if ( a2 && a3 )
  {
    if ( a3 == *((struct ABO_NODE **)this + 2) )
    {
      if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 2078 )
      {
        v7 = *((_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) + 4);
        Ptr = (unsigned __int8 **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
        if ( uuencode(Ptr[3], v7, (struct BUFFER *)v24, 0) )
        {
          v10 = (const char *)BUFFER::QueryPtr((BUFFER *)v24);
          v6 = STRU::CopyA((STRU *)v25, v10);
          if ( v6 >= 0 )
          {
            v11 = *((_QWORD *)this + 3);
            v12 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v11 + 128LL);
            Str = STRU::QueryStr((STRU *)v25);
            v6 = v12(v11, L"certificate", Str, 0);
            if ( v6 >= 0 )
              *((_DWORD *)a2 + 16) = 1;
          }
        }
        else
        {
          ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Could not encode certificate to apphost.config file");
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v14 = (struct INativeConfigurationElement *)*((_QWORD *)this + 3);
        v15 = 0;
        v22 = 0;
        v23 = v14;
        if ( v14 )
        {
          Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)g_pPropertySectionTable + 8,
                  L"iisClientCertificateMappingAuthentication",
                  &v22);
          v15 = v22;
          if ( Key || (v6 = 0, v17 = 0, v18 = 0, !*((_DWORD *)v22 + 22)) )
          {
LABEL_20:
            v6 = -2147024894;
          }
          else
          {
            while ( 1 )
            {
              v22 = *(HANDLE_ENTRY **)(*((_QWORD *)v15 + 10) + 8 * v18);
              v19 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v22 + 32));
              if ( !wcscmp_0(v19, L"iisClientCertificateMappingAuthentication") )
              {
                v20 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
                if ( *((_DWORD *)v22 + 36) == *v20 )
                {
                  v17 = 1;
                  v6 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v22, a3, v23);
                  if ( v6 < 0 )
                    break;
                }
              }
              v18 = (unsigned int)(v18 + 1);
              if ( (unsigned int)v18 >= *((_DWORD *)v15 + 22) )
              {
                if ( v17 )
                  break;
                goto LABEL_20;
              }
            }
          }
        }
        else
        {
          v6 = -2147024809;
        }
        if ( v15 )
          HANDLE_ENTRY::DereferenceHandleEntry(v15);
      }
    }
    else
    {
      v6 = -2147024894;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  STRU::~STRU((STRU *)v25);
  BUFFER::~BUFFER((BUFFER *)v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002b940  mov     [rsp-8+arg_18], rbx
0x18002b945  push    rbp
0x18002b946  push    rsi
0x18002b947  push    rdi
0x18002b948  push    r12
0x18002b94a  push    r13
0x18002b94c  push    r14
0x18002b94e  push    r15
0x18002b950  lea     rbp, [rsp-1160h]
0x18002b958  mov     eax, 1260h
0x18002b95d  call    _alloca_probe
0x18002b962  sub     rsp, rax
0x18002b965  mov     rax, cs:__security_cookie
0x18002b96c  xor     rax, rsp
0x18002b96f  mov     [rbp+1190h+var_40], rax
0x18002b976  mov     r15, r8
0x18002b979  mov     r13, rdx
0x18002b97c  mov     rsi, rcx
0x18002b97f  mov     ebx, 5E0h
0x18002b984  mov     r8d, ebx; Size
0x18002b987  lea     rcx, [rbp+1190h+var_11E0]; void *
0x18002b98b  xor     edx, edx; Val
0x18002b98d  call    memset_0
0x18002b992  mov     r8d, ebx
0x18002b995  lea     rdx, [rbp+1190h+var_11E0]
0x18002b999  lea     rcx, [rsp+1290h+var_1250]
0x18002b99e  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002b9a4  xor     edx, edx; Val
0x18002b9a6  lea     rcx, [rbp+1190h+var_C00]; void *
0x18002b9ad  mov     r8d, 0BB8h; Size
0x18002b9b3  call    memset_0
0x18002b9b8  lea     r8d, [rbx-4]
0x18002b9bc  lea     rdx, [rbp+1190h+var_C00]
0x18002b9c3  lea     rcx, [rsp+1290h+var_1220]
0x18002b9c8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002b9ce  test    r13, r13
0x18002b9d1  jz      loc_18002BBA1
0x18002b9d7  test    r15, r15
0x18002b9da  jz      loc_18002BBA1
0x18002b9e0  cmp     r15, [rsi+10h]
0x18002b9e4  jz      short loc_18002B9F0
0x18002b9e6  mov     ebx, 80070002h
0x18002b9eb  jmp     loc_18002BBA6
0x18002b9f0  lea     r14, [r13+10h]
0x18002b9f4  mov     rcx, r14
0x18002b9f7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b9fd  cmp     dword ptr [rax], 81Eh
0x18002ba03  jnz     loc_18002BAD2
0x18002ba09  mov     rcx, r14
0x18002ba0c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002ba12  mov     rcx, r14
0x18002ba15  mov     ebx, [rax+10h]
0x18002ba18  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002ba1e  xor     r9d, r9d
0x18002ba21  lea     r8, [rsp+1290h+var_1250]
0x18002ba26  mov     edx, ebx
0x18002ba28  mov     rcx, [rax+18h]
0x18002ba2c  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x18002ba32  test    eax, eax
0x18002ba34  jnz     short loc_18002BA67
0x18002ba36  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002ba3d  lea     rdx, aCouldNotEncode; "Could not encode certificate to apphost"...
0x18002ba44  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002ba49  call    cs:__imp_GetLastError
0x18002ba4f  mov     ebx, eax
0x18002ba51  test    eax, eax
0x18002ba53  jle     loc_18002BBA6
0x18002ba59  movzx   ebx, ax
0x18002ba5c  or      ebx, 80070000h
0x18002ba62  jmp     loc_18002BBA6
0x18002ba67  lea     rcx, [rsp+1290h+var_1250]
0x18002ba6c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002ba72  mov     rdx, rax
0x18002ba75  lea     rcx, [rsp+1290h+var_1220]
0x18002ba7a  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002ba80  mov     ebx, eax
0x18002ba82  test    eax, eax
0x18002ba84  js      loc_18002BBA6
0x18002ba8a  mov     rdi, [rsi+18h]
0x18002ba8e  lea     rcx, [rsp+1290h+var_1220]
0x18002ba93  mov     rax, [rdi]
0x18002ba96  mov     rbx, [rax+80h]
0x18002ba9d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002baa3  xor     r9d, r9d
0x18002baa6  lea     rdx, aCertificate; "certificate"
0x18002baad  mov     r8, rax
0x18002bab0  mov     rcx, rdi
0x18002bab3  mov     rax, rbx
0x18002bab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002babb  mov     ebx, eax
0x18002babd  test    eax, eax
0x18002babf  js      loc_18002BBA6
0x18002bac5  mov     dword ptr [r13+40h], 1
0x18002bacd  jmp     loc_18002BBA6
0x18002bad2  mov     rax, [rsi+18h]
0x18002bad6  xor     edi, edi
0x18002bad8  mov     [rsp+1290h+var_1260], rdi
0x18002badd  mov     [rsp+1290h+var_1258], rax
0x18002bae2  test    rax, rax
0x18002bae5  jz      loc_18002BB8D
0x18002baeb  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18002baf2  lea     r8, [rsp+1290h+var_1260]
0x18002baf7  add     rcx, 8
0x18002bafb  lea     rdx, aIisclientcerti; "iisClientCertificateMappingAuthenticati"...
0x18002bb02  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18002bb07  mov     rdi, [rsp+1290h+var_1260]
0x18002bb0c  test    eax, eax
0x18002bb0e  jnz     short loc_18002BB86
0x18002bb10  xor     ebx, ebx
0x18002bb12  xor     r12d, r12d
0x18002bb15  xor     esi, esi
0x18002bb17  cmp     [rdi+58h], ebx
0x18002bb1a  jbe     short loc_18002BB86
0x18002bb1c  mov     rax, [rdi+50h]
0x18002bb20  mov     rax, [rax+rsi*8]
0x18002bb24  mov     [rsp+1290h+var_1260], rax
0x18002bb29  lea     rcx, [rax+20h]
0x18002bb2d  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002bb33  mov     rcx, rax; String1
0x18002bb36  lea     rdx, aIisclientcerti; "iisClientCertificateMappingAuthenticati"...
0x18002bb3d  call    wcscmp_0
0x18002bb42  test    eax, eax
0x18002bb44  jnz     short loc_18002BB7A
0x18002bb46  mov     rcx, r14
0x18002bb49  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002bb4f  mov     rdx, [rsp+1290h+var_1260]; struct PROPERTY_MAPPING *
0x18002bb54  mov     ecx, [rax]
0x18002bb56  cmp     [rdx+90h], ecx
0x18002bb5c  jnz     short loc_18002BB7A
0x18002bb5e  mov     r9, [rsp+1290h+var_1258]; struct INativeConfigurationElement *
0x18002bb63  mov     r8, r15; struct ABO_NODE *
0x18002bb66  mov     rcx, r13; struct PROPERTY_ENTRY *
0x18002bb69  mov     r12d, 1
0x18002bb6f  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18002bb74  mov     ebx, eax
0x18002bb76  test    eax, eax
0x18002bb78  js      short loc_18002BB92
0x18002bb7a  inc     esi
0x18002bb7c  cmp     esi, [rdi+58h]
0x18002bb7f  jb      short loc_18002BB1C
0x18002bb81  test    r12d, r12d
0x18002bb84  jnz     short loc_18002BB92
0x18002bb86  mov     ebx, 80070002h
0x18002bb8b  jmp     short loc_18002BB92
0x18002bb8d  mov     ebx, 80070057h
0x18002bb92  test    rdi, rdi
0x18002bb95  jz      short loc_18002BBA6
0x18002bb97  mov     rcx, rdi; this
0x18002bb9a  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18002bb9f  jmp     short loc_18002BBA6
0x18002bba1  mov     ebx, 80070057h
0x18002bba6  lea     rcx, [rsp+1290h+var_1220]
0x18002bbab  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002bbb1  lea     rcx, [rsp+1290h+var_1250]
0x18002bbb6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002bbbc  mov     eax, ebx
0x18002bbbe  mov     rcx, [rbp+1190h+var_40]
0x18002bbc5  xor     rcx, rsp; StackCookie
0x18002bbc8  call    __security_check_cookie
0x18002bbcd  mov     rbx, [rsp+1290h+arg_18]
0x18002bbd5  add     rsp, 1260h
0x18002bbdc  pop     r15
0x18002bbde  pop     r14
0x18002bbe0  pop     r13
0x18002bbe2  pop     r12
0x18002bbe4  pop     rdi
0x18002bbe5  pop     rsi
0x18002bbe6  pop     rbp
0x18002bbe7  retn
```

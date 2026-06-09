# CERTIFICATE_MAPPING_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18002b560`
- end: `0x18002b936`
- name: `?MapDeleteData@CERTIFICATE_MAPPING_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `982`
- prototype: `__int64 __fastcall(CERTIFICATE_MAPPING_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003426`
- `0x180003460`
- `0x1800034f0`
- `0x180003f14`
- `0x1800047e4`
- `0x18000ace4`
- `0x18001775c`
- `0x18002b560`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b774`
- `msvcrt!_wcsicmp` at `0x18002b774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b684`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b843`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b843`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b632`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b647`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b653`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b6a7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b85f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b632`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b647`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b653`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b6a7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b85f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b5ec`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b5ec`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b904`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b904`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b5c3`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b5c3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b8f9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b8f9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b766`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b766`
- `iisutil!uuencode` at `0x18002b667`
- `iisutil!uuencode` at `0x18002b667`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002b6b4`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002b6b4`

## string_xrefs

- `0x18002b678`: `Could not encode certificate to apphost.config file`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_MAPPING_PROVIDER::MapDeleteData(
        struct ABO_NODE **this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  int v6; // r12d
  int v7; // ebx
  BUFFER *v8; // r14
  _DWORD *Ptr; // rax
  BUFFER *v10; // rcx
  unsigned int v11; // ebx
  unsigned __int8 **v12; // rax
  signed int LastError; // eax
  const char *v14; // rax
  unsigned int v15; // edi
  const wchar_t *Str; // rax
  struct INativeConfigurationElement *v17; // r13
  HANDLE_ENTRY *v18; // rdi
  int Key; // eax
  __int64 v20; // rsi
  const wchar_t *v21; // rax
  _DWORD *v22; // rax
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE_ENTRY *v27; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  struct PROPERTY_ENTRY *v29; // [rsp+58h] [rbp-A8h]
  _BYTE v30[48]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v32[1504]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v33[1504]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v29 = a2;
  memset_0(v32, 0, sizeof(v32));
  BUFFER::BUFFER((BUFFER *)v30, v32, 0x5E0u);
  memset_0(v33, 0, 0xBB8u);
  STRU::STRU((STRU *)v31, v33, 0x5DCu);
  v6 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  String1 = 0;
  if ( a2 && a3 )
  {
    if ( a3 != this[2] )
    {
      v7 = -2147024894;
      goto LABEL_39;
    }
    v8 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
    if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 2078 )
    {
      Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
      v10 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
      v11 = Ptr[4];
      v12 = (unsigned __int8 **)BUFFER::QueryPtr(v10);
      if ( uuencode(v12[3], v11, (struct BUFFER *)v30, 0) )
      {
        v14 = (const char *)BUFFER::QueryPtr((BUFFER *)v30);
        v7 = STRU::CopyA((STRU *)v31, v14);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(struct ABO_NODE *, __int64 *))(*(_QWORD *)this[4] + 40LL))(this[4], &v26);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 24LL))(v26, &v25);
            if ( v7 >= 0 )
            {
              v15 = 0;
              if ( v25 )
              {
                while ( 1 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(v26, v15, &v24);
                  if ( v7 < 0 )
                    break;
                  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                         v24,
                         L"certificate",
                         &String1,
                         0,
                         0);
                  if ( v7 < 0 )
                    break;
                  Str = STRU::QueryStr((STRU *)v31);
                  if ( !_wcsicmp(String1, Str) )
                  {
                    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 64LL))(v26, v15, 0);
                    if ( v7 < 0 )
                      break;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                    v24 = 0;
                    goto LABEL_20;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  ++v15;
                  v24 = 0;
                  if ( v15 >= v25 )
                    goto LABEL_20;
                }
              }
              else
              {
LABEL_20:
                v7 = ABO_NODE::UnMapNodeAndChildren(a3);
              }
            }
          }
        }
      }
      else
      {
        ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Could not encode certificate to apphost.config file");
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v17 = this[3];
      v18 = 0;
      v27 = 0;
      if ( v17 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"iisClientCertificateMappingAuthentication",
                &v27);
        v18 = v27;
        if ( Key )
        {
          v7 = -2147024894;
        }
        else
        {
          v7 = 0;
          v20 = 0;
          if ( *((_DWORD *)v27 + 22) )
          {
            while ( 1 )
            {
              v27 = *(HANDLE_ENTRY **)(*((_QWORD *)v18 + 10) + 8 * v20);
              v21 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v27 + 32));
              if ( !wcscmp_0(v21, L"iisClientCertificateMappingAuthentication") )
              {
                v22 = BUFFER::QueryPtr(v8);
                if ( *((_DWORD *)v27 + 36) == *v22 )
                {
                  v6 = 1;
                  v7 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(v29, v27, a3, v17);
                  if ( v7 < 0 )
                    break;
                }
              }
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= *((_DWORD *)v18 + 22) )
              {
                if ( v6 )
                  break;
                goto LABEL_30;
              }
            }
          }
          else
          {
LABEL_30:
            v7 = -2147024894;
          }
        }
      }
      else
      {
        v7 = -2147024809;
      }
      if ( v18 )
        HANDLE_ENTRY::DereferenceHandleEntry(v18);
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
LABEL_39:
  STRU::~STRU((STRU *)v31);
  BUFFER::~BUFFER((BUFFER *)v30);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b560  mov     [rsp-8+arg_18], rbx
0x18002b565  push    rbp
0x18002b566  push    rsi
0x18002b567  push    rdi
0x18002b568  push    r12
0x18002b56a  push    r13
0x18002b56c  push    r14
0x18002b56e  push    r15
0x18002b570  lea     rbp, [rsp-1180h]
0x18002b578  mov     eax, 1280h
0x18002b57d  call    _alloca_probe
0x18002b582  sub     rsp, rax
0x18002b585  mov     rax, cs:__security_cookie
0x18002b58c  xor     rax, rsp
0x18002b58f  mov     [rbp+11B0h+var_40], rax
0x18002b596  mov     r15, r8
0x18002b599  mov     [rsp+12B0h+var_1258], rdx
0x18002b59e  mov     rbx, rdx
0x18002b5a1  mov     rsi, rcx
0x18002b5a4  mov     edi, 5E0h
0x18002b5a9  lea     rcx, [rbp+11B0h+var_11E0]; void *
0x18002b5ad  mov     r8d, edi; Size
0x18002b5b0  xor     edx, edx; Val
0x18002b5b2  call    memset_0
0x18002b5b7  mov     r8d, edi
0x18002b5ba  lea     rdx, [rbp+11B0h+var_11E0]
0x18002b5be  lea     rcx, [rsp+12B0h+var_1250]
0x18002b5c3  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002b5c9  xor     edx, edx; Val
0x18002b5cb  lea     rcx, [rbp+11B0h+var_C00]; void *
0x18002b5d2  mov     r8d, 0BB8h; Size
0x18002b5d8  call    memset_0
0x18002b5dd  lea     r8d, [rdi-4]
0x18002b5e1  lea     rdx, [rbp+11B0h+var_C00]
0x18002b5e8  lea     rcx, [rbp+11B0h+var_1220]
0x18002b5ec  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002b5f2  xor     r12d, r12d
0x18002b5f5  mov     [rsp+12B0h+var_1280], r12
0x18002b5fa  mov     [rsp+12B0h+var_1270], r12
0x18002b5ff  mov     [rsp+12B0h+var_1278], r12d
0x18002b604  mov     [rsp+12B0h+String1], r12
0x18002b609  test    rbx, rbx
0x18002b60c  jz      loc_18002B8BA
0x18002b612  test    r15, r15
0x18002b615  jz      loc_18002B8BA
0x18002b61b  cmp     r15, [rsi+10h]
0x18002b61f  jz      short loc_18002B62B
0x18002b621  mov     ebx, 80070002h
0x18002b626  jmp     loc_18002B8F5
0x18002b62b  lea     r14, [rbx+10h]
0x18002b62f  mov     rcx, r14
0x18002b632  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b638  cmp     dword ptr [rax], 81Eh
0x18002b63e  jnz     loc_18002B7E7
0x18002b644  mov     rcx, r14
0x18002b647  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b64d  mov     rcx, r14
0x18002b650  mov     ebx, [rax+10h]
0x18002b653  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b659  xor     r9d, r9d
0x18002b65c  lea     r8, [rsp+12B0h+var_1250]
0x18002b661  mov     edx, ebx
0x18002b663  mov     rcx, [rax+18h]
0x18002b667  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x18002b66d  test    eax, eax
0x18002b66f  jnz     short loc_18002B6A2
0x18002b671  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002b678  lea     rdx, aCouldNotEncode; "Could not encode certificate to apphost"...
0x18002b67f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002b684  call    cs:__imp_GetLastError
0x18002b68a  mov     ebx, eax
0x18002b68c  test    eax, eax
0x18002b68e  jle     loc_18002B8BF
0x18002b694  movzx   ebx, ax
0x18002b697  or      ebx, 80070000h
0x18002b69d  jmp     loc_18002B8BF
0x18002b6a2  lea     rcx, [rsp+12B0h+var_1250]
0x18002b6a7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b6ad  mov     rdx, rax
0x18002b6b0  lea     rcx, [rbp+11B0h+var_1220]
0x18002b6b4  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002b6ba  mov     ebx, eax
0x18002b6bc  test    eax, eax
0x18002b6be  js      loc_18002B8BF
0x18002b6c4  mov     rcx, [rsi+20h]
0x18002b6c8  lea     rdx, [rsp+12B0h+var_1270]
0x18002b6cd  mov     rax, [rcx]
0x18002b6d0  mov     rax, [rax+28h]
0x18002b6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6d9  mov     ebx, eax
0x18002b6db  test    eax, eax
0x18002b6dd  js      loc_18002B8BF
0x18002b6e3  mov     rcx, [rsp+12B0h+var_1270]
0x18002b6e8  lea     rdx, [rsp+12B0h+var_1278]
0x18002b6ed  mov     rax, [rcx]
0x18002b6f0  mov     rax, [rax+18h]
0x18002b6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6f9  mov     ebx, eax
0x18002b6fb  test    eax, eax
0x18002b6fd  js      loc_18002B8BF
0x18002b703  mov     edi, r12d
0x18002b706  cmp     [rsp+12B0h+var_1278], r12d
0x18002b70b  jbe     loc_18002B7D8
0x18002b711  mov     rcx, [rsp+12B0h+var_1270]
0x18002b716  lea     r8, [rsp+12B0h+var_1280]
0x18002b71b  mov     edx, edi
0x18002b71d  mov     rax, [rcx]
0x18002b720  mov     rax, [rax+20h]
0x18002b724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b729  mov     ebx, eax
0x18002b72b  test    eax, eax
0x18002b72d  js      loc_18002B8BF
0x18002b733  mov     rcx, [rsp+12B0h+var_1280]
0x18002b738  lea     r8, [rsp+12B0h+String1]
0x18002b73d  xor     r9d, r9d
0x18002b740  mov     [rsp+12B0h+var_1290], r12
0x18002b745  lea     rdx, aCertificate; "certificate"
0x18002b74c  mov     rax, [rcx]
0x18002b74f  mov     rax, [rax+40h]
0x18002b753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b758  mov     ebx, eax
0x18002b75a  test    eax, eax
0x18002b75c  js      loc_18002B8BF
0x18002b762  lea     rcx, [rbp+11B0h+var_1220]
0x18002b766  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002b76c  mov     rcx, [rsp+12B0h+String1]; String1
0x18002b771  mov     rdx, rax; String2
0x18002b774  call    cs:__imp__wcsicmp
0x18002b77a  test    eax, eax
0x18002b77c  jz      short loc_18002B7A2
0x18002b77e  mov     rcx, [rsp+12B0h+var_1280]
0x18002b783  mov     rax, [rcx]
0x18002b786  mov     rax, [rax+10h]
0x18002b78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b78f  inc     edi
0x18002b791  mov     [rsp+12B0h+var_1280], r12
0x18002b796  cmp     edi, [rsp+12B0h+var_1278]
0x18002b79a  jb      loc_18002B711
0x18002b7a0  jmp     short loc_18002B7D8
0x18002b7a2  mov     rcx, [rsp+12B0h+var_1270]
0x18002b7a7  xor     r8d, r8d
0x18002b7aa  mov     edx, edi
0x18002b7ac  mov     rax, [rcx]
0x18002b7af  mov     rax, [rax+40h]
0x18002b7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7b8  mov     ebx, eax
0x18002b7ba  test    eax, eax
0x18002b7bc  js      loc_18002B8BF
0x18002b7c2  mov     rcx, [rsp+12B0h+var_1280]
0x18002b7c7  mov     rax, [rcx]
0x18002b7ca  mov     rax, [rax+10h]
0x18002b7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7d3  mov     [rsp+12B0h+var_1280], r12
0x18002b7d8  mov     rcx, r15; this
0x18002b7db  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x18002b7e0  mov     ebx, eax
0x18002b7e2  jmp     loc_18002B8BF
0x18002b7e7  mov     r13, [rsi+18h]
0x18002b7eb  mov     rdi, r12
0x18002b7ee  mov     [rsp+12B0h+var_1268], r12
0x18002b7f3  test    r13, r13
0x18002b7f6  jz      loc_18002B8B3
0x18002b7fc  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18002b803  lea     r8, [rsp+12B0h+var_1268]
0x18002b808  add     rcx, 8
0x18002b80c  lea     rdx, aIisclientcerti; "iisClientCertificateMappingAuthenticati"...
0x18002b813  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18002b818  mov     rdi, [rsp+12B0h+var_1268]
0x18002b81d  test    eax, eax
0x18002b81f  jz      short loc_18002B828
0x18002b821  mov     ebx, 80070002h
0x18002b826  jmp     short loc_18002B8A4
0x18002b828  mov     ebx, r12d
0x18002b82b  xor     esi, esi
0x18002b82d  cmp     [rdi+58h], ebx
0x18002b830  jbe     short loc_18002B89C
0x18002b832  mov     rax, [rdi+50h]
0x18002b836  mov     rax, [rax+rsi*8]
0x18002b83a  mov     [rsp+12B0h+var_1268], rax
0x18002b83f  lea     rcx, [rax+20h]
0x18002b843  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002b849  mov     rcx, rax; String1
0x18002b84c  lea     rdx, aIisclientcerti; "iisClientCertificateMappingAuthenticati"...
0x18002b853  call    wcscmp_0
0x18002b858  test    eax, eax
0x18002b85a  jnz     short loc_18002B890
0x18002b85c  mov     rcx, r14
0x18002b85f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b865  mov     rdx, [rsp+12B0h+var_1268]; struct PROPERTY_MAPPING *
0x18002b86a  mov     ecx, [rax]
0x18002b86c  cmp     [rdx+90h], ecx
0x18002b872  jnz     short loc_18002B890
0x18002b874  mov     rcx, [rsp+12B0h+var_1258]; struct PROPERTY_ENTRY *
0x18002b879  mov     r9, r13; struct INativeConfigurationElement *
0x18002b87c  mov     r8, r15; struct ABO_NODE *
0x18002b87f  mov     r12d, 1
0x18002b885  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18002b88a  mov     ebx, eax
0x18002b88c  test    eax, eax
0x18002b88e  js      short loc_18002B8A1
0x18002b890  inc     esi
0x18002b892  cmp     esi, [rdi+58h]
0x18002b895  jb      short loc_18002B832
0x18002b897  test    r12d, r12d
0x18002b89a  jnz     short loc_18002B8A1
0x18002b89c  mov     ebx, 80070002h
0x18002b8a1  xor     r12d, r12d
0x18002b8a4  test    rdi, rdi
0x18002b8a7  jz      short loc_18002B8BF
0x18002b8a9  mov     rcx, rdi; this
0x18002b8ac  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18002b8b1  jmp     short loc_18002B8BF
0x18002b8b3  mov     ebx, 80070057h
0x18002b8b8  jmp     short loc_18002B8A4
0x18002b8ba  mov     ebx, 80070057h
0x18002b8bf  mov     rcx, [rsp+12B0h+var_1280]
0x18002b8c4  test    rcx, rcx
0x18002b8c7  jz      short loc_18002B8DA
0x18002b8c9  mov     rax, [rcx]
0x18002b8cc  mov     rax, [rax+10h]
0x18002b8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d5  mov     [rsp+12B0h+var_1280], r12
0x18002b8da  mov     rcx, [rsp+12B0h+var_1270]
0x18002b8df  test    rcx, rcx
0x18002b8e2  jz      short loc_18002B8F5
0x18002b8e4  mov     rax, [rcx]
0x18002b8e7  mov     rax, [rax+10h]
0x18002b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8f0  mov     [rsp+12B0h+var_1270], r12
0x18002b8f5  lea     rcx, [rbp+11B0h+var_1220]
0x18002b8f9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002b8ff  lea     rcx, [rsp+12B0h+var_1250]
0x18002b904  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b90a  mov     eax, ebx
0x18002b90c  mov     rcx, [rbp+11B0h+var_40]
0x18002b913  xor     rcx, rsp; StackCookie
0x18002b916  call    __security_check_cookie
0x18002b91b  mov     rbx, [rsp+12B0h+arg_18]
0x18002b923  add     rsp, 1280h
0x18002b92a  pop     r15
0x18002b92c  pop     r14
0x18002b92e  pop     r13
0x18002b930  pop     r12
0x18002b932  pop     rdi
0x18002b933  pop     rsi
0x18002b934  pop     rbp
0x18002b935  retn
```

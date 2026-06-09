# CERTIFICATE_CUSTOM_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18002b1a0`
- end: `0x18002b46a`
- name: `?MapSetData@CERTIFICATE_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(CERTIFICATE_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x1800034f0`
- `0x1800047b0`
- `0x180006e28`
- `0x18000a4e8`
- `0x18002aae8`
- `0x18002b1a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2fd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b250`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b26b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b2c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b2cc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b320`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b250`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b26b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b2c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b2cc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002b320`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b231`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002b231`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b445`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b445`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b207`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002b207`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b43a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b43a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b352`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002b352`
- `iisutil!uuencode` at `0x18002b2e0`
- `iisutil!uuencode` at `0x18002b2e0`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002b32e`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18002b32e`

## string_xrefs

- `0x18002b2f1`: `Could not encode certificate to apphost.config file`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_CUSTOM_PROVIDER::MapSetData(
        CERTIFICATE_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  BUFFER *v6; // rdi
  signed int v7; // ebx
  unsigned int v8; // ebx
  unsigned __int8 **Ptr; // rax
  signed int LastError; // eax
  const char *v11; // rax
  __int64 (__fastcall *v12)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  CERTIFICATE_MAPPING_PROVIDER *v14; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v15; // rax
  CUSTOM_PROPERTY_PROVIDER *v16; // rdi
  struct INativeConfigurationElement *v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[48]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[64]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v22[1504]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v23[1504]; // [rsp+690h] [rbp+590h] BYREF

  v19 = 0;
  v18 = 0;
  memset_0(v22, 0, sizeof(v22));
  BUFFER::BUFFER((BUFFER *)v20, v22, 0x5E0u);
  memset_0(v23, 0, 0xBB8u);
  STRU::STRU((STRU *)v21, v23, 0x5DCu);
  if ( a2 && a3 )
  {
    v6 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
    if ( *(_DWORD *)BUFFER::QueryPtr(v6) == 2078 && *((_DWORD *)BUFFER::QueryPtr(v6) + 3) == 3 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v19);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v19 + 48LL))(
               v19,
               L"add",
               &v18);
        if ( v7 >= 0 )
        {
          v8 = *((_DWORD *)BUFFER::QueryPtr(v6) + 4);
          Ptr = (unsigned __int8 **)BUFFER::QueryPtr(v6);
          if ( uuencode(Ptr[3], v8, (struct BUFFER *)v20, 0) )
          {
            v11 = (const char *)BUFFER::QueryPtr((BUFFER *)v20);
            v7 = STRU::CopyA((STRU *)v21, v11);
            if ( v7 >= 0 )
            {
              v12 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v18 + 128LL);
              Str = STRU::QueryStr((STRU *)v21);
              v7 = v12(v18, L"certificate", Str, 0);
              if ( v7 >= 0 )
              {
                v14 = (CERTIFICATE_MAPPING_PROVIDER *)operator new(0x28u);
                if ( v14
                  && (v15 = CERTIFICATE_MAPPING_PROVIDER::CERTIFICATE_MAPPING_PROVIDER(
                              v14,
                              a3,
                              v18,
                              *((struct INativeConfigurationElement **)this + 3)),
                      (v16 = v15) != 0) )
                {
                  v7 = ABO_NODE::AddProvider(a3, v15);
                  if ( v7 >= 0 )
                  {
                    v7 = ABO_NODE::MapNodeAndChildren(a3);
                    if ( v7 >= 0 )
                      v7 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v19 + 56LL))(
                             v19,
                             v18,
                             0xFFFFFFFFLL,
                             0);
                  }
                  CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v16);
                }
                else
                {
                  v7 = -2147024888;
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
      }
    }
    else
    {
      v7 = -2147024894;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  STRU::~STRU((STRU *)v21);
  BUFFER::~BUFFER((BUFFER *)v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b1a0  push    rbp
0x18002b1a2  push    rbx
0x18002b1a3  push    rsi
0x18002b1a4  push    rdi
0x18002b1a5  push    r14
0x18002b1a7  lea     rbp, [rsp-1160h]
0x18002b1af  mov     eax, 1260h
0x18002b1b4  call    _alloca_probe
0x18002b1b9  sub     rsp, rax
0x18002b1bc  mov     rax, cs:__security_cookie
0x18002b1c3  xor     rax, rsp
0x18002b1c6  mov     [rbp+1180h+var_30], rax
0x18002b1cd  mov     rsi, r8
0x18002b1d0  mov     [rsp+1280h+var_1248], 0
0x18002b1d9  mov     rdi, rdx
0x18002b1dc  mov     [rsp+1280h+var_1250], 0
0x18002b1e5  mov     r14, rcx
0x18002b1e8  mov     ebx, 5E0h
0x18002b1ed  mov     r8d, ebx; Size
0x18002b1f0  lea     rcx, [rbp+1180h+var_11D0]; void *
0x18002b1f4  xor     edx, edx; Val
0x18002b1f6  call    memset_0
0x18002b1fb  mov     r8d, ebx
0x18002b1fe  lea     rdx, [rbp+1180h+var_11D0]
0x18002b202  lea     rcx, [rsp+1280h+var_1240]
0x18002b207  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002b20d  xor     edx, edx; Val
0x18002b20f  lea     rcx, [rbp+1180h+var_BF0]; void *
0x18002b216  mov     r8d, 0BB8h; Size
0x18002b21c  call    memset_0
0x18002b221  lea     r8d, [rbx-4]
0x18002b225  lea     rdx, [rbp+1180h+var_BF0]
0x18002b22c  lea     rcx, [rsp+1280h+var_1210]
0x18002b231  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002b237  test    rdi, rdi
0x18002b23a  jz      loc_18002B3F2
0x18002b240  test    rsi, rsi
0x18002b243  jz      loc_18002B3F2
0x18002b249  add     rdi, 10h
0x18002b24d  mov     rcx, rdi
0x18002b250  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b256  cmp     dword ptr [rax], 81Eh
0x18002b25c  jz      short loc_18002B268
0x18002b25e  mov     ebx, 80070002h
0x18002b263  jmp     loc_18002B3F7
0x18002b268  mov     rcx, rdi
0x18002b26b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b271  cmp     dword ptr [rax+0Ch], 3
0x18002b275  jnz     short loc_18002B25E
0x18002b277  mov     rcx, [r14+18h]
0x18002b27b  lea     rdx, [rsp+1280h+var_1248]
0x18002b280  mov     rax, [rcx]
0x18002b283  mov     rax, [rax+28h]
0x18002b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b28c  mov     ebx, eax
0x18002b28e  test    eax, eax
0x18002b290  js      loc_18002B3F7
0x18002b296  mov     rcx, [rsp+1280h+var_1248]
0x18002b29b  lea     r8, [rsp+1280h+var_1250]
0x18002b2a0  lea     rdx, aAdd; "add"
0x18002b2a7  mov     rax, [rcx]
0x18002b2aa  mov     rax, [rax+30h]
0x18002b2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2b3  mov     ebx, eax
0x18002b2b5  test    eax, eax
0x18002b2b7  js      loc_18002B3F7
0x18002b2bd  mov     rcx, rdi
0x18002b2c0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b2c6  mov     rcx, rdi
0x18002b2c9  mov     ebx, [rax+10h]
0x18002b2cc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b2d2  xor     r9d, r9d
0x18002b2d5  lea     r8, [rsp+1280h+var_1240]
0x18002b2da  mov     edx, ebx
0x18002b2dc  mov     rcx, [rax+18h]
0x18002b2e0  call    cs:__imp_?uuencode@@YAHPEAEKPEAVBUFFER@@H@Z; uuencode(uchar *,ulong,BUFFER *,int)
0x18002b2e6  test    eax, eax
0x18002b2e8  jnz     short loc_18002B31B
0x18002b2ea  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002b2f1  lea     rdx, aCouldNotEncode; "Could not encode certificate to apphost"...
0x18002b2f8  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002b2fd  call    cs:__imp_GetLastError
0x18002b303  mov     ebx, eax
0x18002b305  test    eax, eax
0x18002b307  jle     loc_18002B3F7
0x18002b30d  movzx   ebx, ax
0x18002b310  or      ebx, 80070000h
0x18002b316  jmp     loc_18002B3F7
0x18002b31b  lea     rcx, [rsp+1280h+var_1240]
0x18002b320  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002b326  mov     rdx, rax
0x18002b329  lea     rcx, [rsp+1280h+var_1210]
0x18002b32e  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18002b334  mov     ebx, eax
0x18002b336  test    eax, eax
0x18002b338  js      loc_18002B3F7
0x18002b33e  mov     rax, [rsp+1280h+var_1250]
0x18002b343  mov     rcx, [rax]
0x18002b346  mov     rbx, [rcx+80h]
0x18002b34d  lea     rcx, [rsp+1280h+var_1210]
0x18002b352  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002b358  mov     rcx, [rsp+1280h+var_1250]
0x18002b35d  lea     rdx, aCertificate; "certificate"
0x18002b364  mov     r8, rax
0x18002b367  xor     r9d, r9d
0x18002b36a  mov     rax, rbx
0x18002b36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b372  mov     ebx, eax
0x18002b374  test    eax, eax
0x18002b376  js      short loc_18002B3F7
0x18002b378  mov     ecx, 28h ; '('; Size
0x18002b37d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b382  test    rax, rax
0x18002b385  jz      short loc_18002B3EB
0x18002b387  mov     r9, [r14+18h]; struct INativeConfigurationElement *
0x18002b38b  mov     rdx, rsi; struct ABO_NODE *
0x18002b38e  mov     r8, [rsp+1280h+var_1250]; struct INativeConfigurationElement *
0x18002b393  mov     rcx, rax; this
0x18002b396  call    ??0CERTIFICATE_MAPPING_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; CERTIFICATE_MAPPING_PROVIDER::CERTIFICATE_MAPPING_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x18002b39b  mov     rdi, rax
0x18002b39e  test    rax, rax
0x18002b3a1  jz      short loc_18002B3EB
0x18002b3a3  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x18002b3a6  mov     rcx, rsi; this
0x18002b3a9  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18002b3ae  mov     ebx, eax
0x18002b3b0  test    eax, eax
0x18002b3b2  js      short loc_18002B3E1
0x18002b3b4  mov     rcx, rsi; this
0x18002b3b7  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x18002b3bc  mov     ebx, eax
0x18002b3be  test    eax, eax
0x18002b3c0  js      short loc_18002B3E1
0x18002b3c2  mov     rcx, [rsp+1280h+var_1248]
0x18002b3c7  xor     r9d, r9d
0x18002b3ca  mov     rdx, [rsp+1280h+var_1250]
0x18002b3cf  or      r8d, 0FFFFFFFFh
0x18002b3d3  mov     rax, [rcx]
0x18002b3d6  mov     rax, [rax+38h]
0x18002b3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3df  mov     ebx, eax
0x18002b3e1  mov     rcx, rdi; this
0x18002b3e4  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18002b3e9  jmp     short loc_18002B3F7
0x18002b3eb  mov     ebx, 80070008h
0x18002b3f0  jmp     short loc_18002B3F7
0x18002b3f2  mov     ebx, 80070057h
0x18002b3f7  mov     rcx, [rsp+1280h+var_1250]
0x18002b3fc  test    rcx, rcx
0x18002b3ff  jz      short loc_18002B416
0x18002b401  mov     rax, [rcx]
0x18002b404  mov     rax, [rax+10h]
0x18002b408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b40d  mov     [rsp+1280h+var_1250], 0
0x18002b416  mov     rcx, [rsp+1280h+var_1248]
0x18002b41b  test    rcx, rcx
0x18002b41e  jz      short loc_18002B435
0x18002b420  mov     rax, [rcx]
0x18002b423  mov     rax, [rax+10h]
0x18002b427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b42c  mov     [rsp+1280h+var_1248], 0
0x18002b435  lea     rcx, [rsp+1280h+var_1210]
0x18002b43a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002b440  lea     rcx, [rsp+1280h+var_1240]
0x18002b445  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b44b  mov     eax, ebx
0x18002b44d  mov     rcx, [rbp+1180h+var_30]
0x18002b454  xor     rcx, rsp; StackCookie
0x18002b457  call    __security_check_cookie
0x18002b45c  add     rsp, 1260h
0x18002b463  pop     r14
0x18002b465  pop     rdi
0x18002b466  pop     rsi
0x18002b467  pop     rbx
0x18002b468  pop     rbp
0x18002b469  retn
```

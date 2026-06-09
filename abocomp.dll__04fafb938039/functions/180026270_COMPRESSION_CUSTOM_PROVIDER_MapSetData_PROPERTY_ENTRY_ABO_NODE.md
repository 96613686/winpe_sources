# COMPRESSION_CUSTOM_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180026270`
- end: `0x180026617`
- name: `?MapSetData@COMPRESSION_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `935`
- prototype: `int(COMPRESSION_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002990`
- `0x180003426`
- `0x180003f14`
- `0x1800047b0`
- `0x1800047e4`
- `0x180006e28`
- `0x18000a4e8`
- `0x1800187e0`
- `0x18002588c`
- `0x180026270`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800262ca`
- `msvcrt!_wcsicmp` at `0x1800262ca`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800262b6`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800263b3`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002649b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800262b6`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800263b3`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002649b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800262db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800262ec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026324`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026335`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800263cf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002642e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800264d5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800262db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800262ec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026324`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180026335`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800263cf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002642e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800264d5`

## string_xrefs

- `0x180026353`: `doStaticCompression`
- `0x18002630a`: `doDynamicCompression`
- `0x180026382`: `httpCompression`
- `0x1800263bc`: `httpCompression`

## pseudocode

```c
__int64 __fastcall COMPRESSION_CUSTOM_PROVIDER::MapSetData(
        COMPRESSION_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  const wchar_t *Str; // rax
  int v7; // eax
  BUFFER *v8; // rcx
  _DWORD *v9; // rax
  BUFFER *v10; // rcx
  _DWORD **v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  bool v14; // zf
  __int64 (__fastcall *v15)(__int64, const wchar_t *, __int64, _QWORD); // rax
  const wchar_t *v16; // rdx
  int v17; // ebx
  _DWORD **v18; // rax
  struct INativeConfigurationElement *v19; // rax
  HANDLE_ENTRY *v20; // rdi
  int Key; // eax
  int v22; // r12d
  __int64 v23; // r15
  const wchar_t *v24; // rax
  _DWORD *v25; // rax
  __int64 (__fastcall *v26)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD); // rbx
  const unsigned __int16 *v27; // rax
  __int64 (__fastcall *v28)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD); // rbx
  _QWORD *Ptr; // rax
  SCHEME_CUSTOM_PROVIDER *v30; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v31; // rax
  CUSTOM_PROPERTY_PROVIDER *v32; // rdi
  HANDLE_ENTRY *v34; // [rsp+30h] [rbp-10h] BYREF
  struct INativeConfigurationElement *v35; // [rsp+38h] [rbp-8h]
  struct INativeConfigurationElement *v36; // [rsp+88h] [rbp+48h] BYREF
  __int64 v37; // [rsp+98h] [rbp+58h] BYREF

  v36 = 0;
  v37 = 0;
  if ( a2 && a3 )
  {
    Str = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 56));
    v7 = _wcsicmp(Str, L"PARAMETERS");
    v8 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
    if ( v7 )
    {
      if ( *(_DWORD *)BUFFER::QueryPtr(v8) == 2237 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 40LL))(
                *((_QWORD *)this + 3),
                &v37);
        if ( v17 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v37 + 48LL))(
                  v37,
                  L"scheme",
                  &v36);
          if ( v17 >= 0 )
          {
            v26 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v36 + 128LL);
            v27 = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 56));
            v17 = v26(v36, L"name", v27, 0);
            if ( v17 >= 0 )
            {
              v28 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v36 + 128LL);
              Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
              v17 = v28(v36, L"dll", Ptr[3], 0);
              if ( v17 >= 0 )
              {
                v30 = (SCHEME_CUSTOM_PROVIDER *)operator new(0x60u);
                if ( v30
                  && (v31 = SCHEME_CUSTOM_PROVIDER::SCHEME_CUSTOM_PROVIDER(
                              v30,
                              a3,
                              v36,
                              *((struct INativeConfigurationElement **)this + 3)),
                      (v32 = v31) != 0) )
                {
                  v17 = ABO_NODE::AddProvider(a3, v31);
                  if ( v17 < 0
                    || (v17 = ABO_NODE::MapNodeAndChildren(a3), v17 < 0)
                    || (v17 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v37 + 56LL))(
                                v37,
                                v36,
                                0xFFFFFFFFLL,
                                0),
                        v17 < 0) )
                  {
                    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v32);
                  }
                  else
                  {
                    *((_DWORD *)a3 + 56) = 1;
                    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v32);
                    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v36 + 16LL))(v36);
                    v36 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                    v37 = 0;
                  }
                }
                else
                {
                  v17 = -2147024888;
                }
              }
            }
          }
        }
      }
      else
      {
        v17 = -2147024894;
      }
    }
    else
    {
      v9 = BUFFER::QueryPtr(v8);
      v10 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
      if ( *v9 == 2213 )
      {
        v11 = (_DWORD **)BUFFER::QueryPtr(v10);
        v12 = *((_QWORD *)this + 4);
        v13 = 0;
        v14 = *v11[3] == 0;
        v15 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v12 + 136LL);
        v16 = L"doDynamicCompression";
LABEL_6:
        LOBYTE(v13) = !v14;
        v17 = v15(v12, v16, v13, 0);
        goto LABEL_36;
      }
      if ( *(_DWORD *)BUFFER::QueryPtr(v10) == 2214 )
      {
        v18 = (_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
        v12 = *((_QWORD *)this + 4);
        v13 = 0;
        v14 = *v18[3] == 0;
        v15 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v12 + 136LL);
        v16 = L"doStaticCompression";
        goto LABEL_6;
      }
      v19 = (struct INativeConfigurationElement *)*((_QWORD *)this + 3);
      v20 = 0;
      v34 = 0;
      v35 = v19;
      if ( v19 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"httpCompression",
                &v34);
        v20 = v34;
        if ( Key || (v17 = 0, v22 = 0, v23 = 0, !*((_DWORD *)v34 + 22)) )
        {
LABEL_17:
          v17 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v34 = *(HANDLE_ENTRY **)(*((_QWORD *)v20 + 10) + 8 * v23);
            v24 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v34 + 32));
            if ( !wcscmp_0(v24, L"httpCompression") )
            {
              v25 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
              if ( *((_DWORD *)v34 + 36) == *v25 )
              {
                v22 = 1;
                v17 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v34, a3, v35);
                if ( v17 < 0 )
                  break;
              }
            }
            v23 = (unsigned int)(v23 + 1);
            if ( (unsigned int)v23 >= *((_DWORD *)v20 + 22) )
            {
              if ( v22 )
                break;
              goto LABEL_17;
            }
          }
        }
      }
      else
      {
        v17 = -2147024809;
      }
      if ( v20 )
        HANDLE_ENTRY::DereferenceHandleEntry(v20);
    }
  }
  else
  {
    v17 = -2147024809;
  }
LABEL_36:
  if ( v36 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180026270  mov     [rsp-38h+arg_0], rbx
0x180026275  push    rbp
0x180026276  push    rsi
0x180026277  push    rdi
0x180026278  push    r12
0x18002627a  push    r13
0x18002627c  push    r14
0x18002627e  push    r15
0x180026280  mov     rbp, rsp
0x180026283  sub     rsp, 40h
0x180026287  mov     [rbp+arg_8], 0
0x18002628f  mov     rsi, r8
0x180026292  mov     [rbp+arg_18], 0
0x18002629a  mov     r13, rdx
0x18002629d  mov     r15, rcx
0x1800262a0  test    rdx, rdx
0x1800262a3  jz      loc_1800265C6
0x1800262a9  test    r8, r8
0x1800262ac  jz      loc_1800265C6
0x1800262b2  lea     rcx, [r8+38h]
0x1800262b6  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800262bc  mov     rcx, rax; String1
0x1800262bf  lea     rdx, aParameters; "PARAMETERS"
0x1800262c6  lea     r14, [r13+10h]
0x1800262ca  call    cs:__imp__wcsicmp
0x1800262d0  mov     rcx, r14
0x1800262d3  test    eax, eax
0x1800262d5  jnz     loc_18002642E
0x1800262db  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800262e1  mov     rcx, r14
0x1800262e4  cmp     dword ptr [rax], 8A5h
0x1800262ea  jnz     short loc_180026324
0x1800262ec  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800262f2  mov     rcx, [r15+20h]
0x1800262f6  xor     r8d, r8d
0x1800262f9  mov     rax, [rax+18h]
0x1800262fd  mov     rdx, [rcx]
0x180026300  cmp     [rax], r8d
0x180026303  mov     rax, [rdx+88h]
0x18002630a  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x180026311  setnz   r8b
0x180026315  xor     r9d, r9d
0x180026318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002631d  mov     ebx, eax
0x18002631f  jmp     loc_1800265CB
0x180026324  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002632a  cmp     dword ptr [rax], 8A6h
0x180026330  jnz     short loc_18002635C
0x180026332  mov     rcx, r14
0x180026335  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002633b  mov     rcx, [r15+20h]
0x18002633f  xor     r8d, r8d
0x180026342  mov     rax, [rax+18h]
0x180026346  mov     rdx, [rcx]
0x180026349  cmp     [rax], r8d
0x18002634c  mov     rax, [rdx+88h]
0x180026353  lea     rdx, aDostaticcompre; "doStaticCompression"
0x18002635a  jmp     short loc_180026311
0x18002635c  mov     rax, [r15+18h]
0x180026360  xor     edi, edi
0x180026362  mov     [rbp+var_10], rdi
0x180026366  mov     [rbp+var_8], rax
0x18002636a  test    rax, rax
0x18002636d  jz      loc_180026413
0x180026373  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18002637a  lea     r8, [rbp+var_10]
0x18002637e  add     rcx, 8
0x180026382  lea     rdx, aHttpcompressio; "httpCompression"
0x180026389  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18002638e  mov     rdi, [rbp+var_10]
0x180026392  test    eax, eax
0x180026394  jnz     short loc_18002640C
0x180026396  xor     ebx, ebx
0x180026398  xor     r12d, r12d
0x18002639b  xor     r15d, r15d
0x18002639e  cmp     [rdi+58h], ebx
0x1800263a1  jbe     short loc_18002640C
0x1800263a3  mov     rax, [rdi+50h]
0x1800263a7  mov     rax, [rax+r15*8]
0x1800263ab  mov     [rbp+var_10], rax
0x1800263af  lea     rcx, [rax+20h]
0x1800263b3  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800263b9  mov     rcx, rax; String1
0x1800263bc  lea     rdx, aHttpcompressio; "httpCompression"
0x1800263c3  call    wcscmp_0
0x1800263c8  test    eax, eax
0x1800263ca  jnz     short loc_1800263FE
0x1800263cc  mov     rcx, r14
0x1800263cf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800263d5  mov     rdx, [rbp+var_10]; struct PROPERTY_MAPPING *
0x1800263d9  mov     ecx, [rax]
0x1800263db  cmp     [rdx+90h], ecx
0x1800263e1  jnz     short loc_1800263FE
0x1800263e3  mov     r9, [rbp+var_8]; struct INativeConfigurationElement *
0x1800263e7  mov     r8, rsi; struct ABO_NODE *
0x1800263ea  mov     rcx, r13; struct PROPERTY_ENTRY *
0x1800263ed  mov     r12d, 1
0x1800263f3  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x1800263f8  mov     ebx, eax
0x1800263fa  test    eax, eax
0x1800263fc  js      short loc_180026418
0x1800263fe  inc     r15d
0x180026401  cmp     r15d, [rdi+58h]
0x180026405  jb      short loc_1800263A3
0x180026407  test    r12d, r12d
0x18002640a  jnz     short loc_180026418
0x18002640c  mov     ebx, 80070002h
0x180026411  jmp     short loc_180026418
0x180026413  mov     ebx, 80070057h
0x180026418  test    rdi, rdi
0x18002641b  jz      loc_1800265CB
0x180026421  mov     rcx, rdi; this
0x180026424  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180026429  jmp     loc_1800265CB
0x18002642e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180026434  cmp     dword ptr [rax], 8BDh
0x18002643a  jz      short loc_180026446
0x18002643c  mov     ebx, 80070002h
0x180026441  jmp     loc_1800265CB
0x180026446  mov     rcx, [r15+18h]
0x18002644a  lea     rdx, [rbp+arg_18]
0x18002644e  mov     rax, [rcx]
0x180026451  mov     rax, [rax+28h]
0x180026455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002645a  mov     ebx, eax
0x18002645c  test    eax, eax
0x18002645e  js      loc_1800265CB
0x180026464  mov     rcx, [rbp+arg_18]
0x180026468  lea     r8, [rbp+arg_8]
0x18002646c  lea     rdx, aScheme; "scheme"
0x180026473  mov     rax, [rcx]
0x180026476  mov     rax, [rax+30h]
0x18002647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002647f  mov     ebx, eax
0x180026481  test    eax, eax
0x180026483  js      loc_1800265CB
0x180026489  mov     rax, [rbp+arg_8]
0x18002648d  lea     rcx, [rsi+38h]
0x180026491  mov     rdx, [rax]
0x180026494  mov     rbx, [rdx+80h]
0x18002649b  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800264a1  mov     rcx, [rbp+arg_8]
0x1800264a5  lea     rdx, aName; "name"
0x1800264ac  mov     r8, rax
0x1800264af  xor     r9d, r9d
0x1800264b2  mov     rax, rbx
0x1800264b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ba  mov     ebx, eax
0x1800264bc  test    eax, eax
0x1800264be  js      loc_1800265CB
0x1800264c4  mov     rax, [rbp+arg_8]
0x1800264c8  mov     rcx, [rax]
0x1800264cb  mov     rbx, [rcx+80h]
0x1800264d2  mov     rcx, r14
0x1800264d5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800264db  mov     rcx, [rbp+arg_8]
0x1800264df  lea     rdx, aDll_0; "dll"
0x1800264e6  xor     r9d, r9d
0x1800264e9  mov     r8, [rax+18h]
0x1800264ed  mov     rax, rbx
0x1800264f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264f5  mov     ebx, eax
0x1800264f7  test    eax, eax
0x1800264f9  js      loc_1800265CB
0x1800264ff  mov     ecx, 60h ; '`'; Size
0x180026504  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026509  test    rax, rax
0x18002650c  jz      loc_1800265BF
0x180026512  mov     r9, [r15+18h]; struct INativeConfigurationElement *
0x180026516  mov     rdx, rsi; struct ABO_NODE *
0x180026519  mov     r8, [rbp+arg_8]; struct INativeConfigurationElement *
0x18002651d  mov     rcx, rax; this
0x180026520  call    ??0SCHEME_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; SCHEME_CUSTOM_PROVIDER::SCHEME_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180026525  mov     rdi, rax
0x180026528  test    rax, rax
0x18002652b  jz      loc_1800265BF
0x180026531  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x180026534  mov     rcx, rsi; this
0x180026537  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18002653c  mov     ebx, eax
0x18002653e  test    eax, eax
0x180026540  js      short loc_1800265B5
0x180026542  mov     rcx, rsi; this
0x180026545  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x18002654a  mov     ebx, eax
0x18002654c  test    eax, eax
0x18002654e  js      short loc_1800265B5
0x180026550  mov     rcx, [rbp+arg_18]
0x180026554  xor     r9d, r9d
0x180026557  mov     rdx, [rbp+arg_8]
0x18002655b  or      r8d, 0FFFFFFFFh
0x18002655f  mov     rax, [rcx]
0x180026562  mov     rax, [rax+38h]
0x180026566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002656b  mov     ebx, eax
0x18002656d  test    eax, eax
0x18002656f  js      short loc_1800265B5
0x180026571  mov     rcx, rdi; this
0x180026574  mov     dword ptr [rsi+0E0h], 1
0x18002657e  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180026583  mov     rcx, [rbp+arg_8]
0x180026587  mov     rax, [rcx]
0x18002658a  mov     rax, [rax+10h]
0x18002658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026593  mov     rcx, [rbp+arg_18]
0x180026597  mov     [rbp+arg_8], 0
0x18002659f  mov     rax, [rcx]
0x1800265a2  mov     rax, [rax+10h]
0x1800265a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265ab  mov     [rbp+arg_18], 0
0x1800265b3  jmp     short loc_1800265CB
0x1800265b5  mov     rcx, rdi; this
0x1800265b8  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x1800265bd  jmp     short loc_1800265CB
0x1800265bf  mov     ebx, 80070008h
0x1800265c4  jmp     short loc_1800265CB
0x1800265c6  mov     ebx, 80070057h
0x1800265cb  mov     rcx, [rbp+arg_8]
0x1800265cf  test    rcx, rcx
0x1800265d2  jz      short loc_1800265E8
0x1800265d4  mov     rax, [rcx]
0x1800265d7  mov     rax, [rax+10h]
0x1800265db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265e0  mov     [rbp+arg_8], 0
0x1800265e8  mov     rcx, [rbp+arg_18]
0x1800265ec  test    rcx, rcx
0x1800265ef  jz      short loc_1800265FD
0x1800265f1  mov     rax, [rcx]
0x1800265f4  mov     rax, [rax+10h]
0x1800265f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265fd  mov     eax, ebx
0x1800265ff  mov     rbx, [rsp+40h+arg_0]
0x180026607  add     rsp, 40h
0x18002660b  pop     r15
0x18002660d  pop     r14
0x18002660f  pop     r13
0x180026611  pop     r12
0x180026613  pop     rdi
0x180026614  pop     rsi
0x180026615  pop     rbp
0x180026616  retn
```

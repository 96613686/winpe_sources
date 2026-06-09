# SITES_CUSTOM_PROVIDER::CreateSite(ABO_NODE *,ushort const *,ulong)

- ea: `0x180012718`
- end: `0x180012a29`
- name: `?CreateSite@SITES_CUSTOM_PROVIDER@@AEAAJPEAVABO_NODE@@PEBGK@Z`
- size: `785`
- prototype: `int(SITES_CUSTOM_PROVIDER *__hidden this, struct ABO_NODE *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180013110`
- `0x180013924`

## callees

- `0x180002990`
- `0x180003460`
- `0x1800047b0`
- `0x1800065a8`
- `0x180006e28`
- `0x1800077dc`
- `0x18000fa00`
- `0x18000fd48`
- `0x18001254c`
- `0x180012718`
- `0x180013e0c`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001277c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001277c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001290a`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001290a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001287e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001287e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012a05`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012a05`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012808`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800128fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012980`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012808`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800128fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012980`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001286a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001288b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001286a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001288b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001275b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001275b`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::CreateSite(
        SITES_CUSTOM_PROVIDER *this,
        struct ABO_NODE *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  PROPERTY_ENTRY *v8; // rdi
  int v9; // ebx
  __int64 (__fastcall *v10)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  int v12; // eax
  int v13; // esi
  const unsigned __int16 *v14; // rax
  PROPERTY_ENTRY *v15; // rax
  SITE_CUSTOM_PROVIDER *v16; // rax
  SITE_CUSTOM_PROVIDER *v17; // rsi
  const unsigned __int16 *v18; // rax
  struct INativeConfigurationElement *v20; // [rsp+30h] [rbp-59h] BYREF
  __int64 v21; // [rsp+38h] [rbp-51h] BYREF
  _METADATA_RECORD v22; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v23[56]; // [rsp+68h] [rbp-21h] BYREF

  v20 = 0;
  v21 = 0;
  STRU::STRU((STRU *)v23);
  v8 = 0;
  if ( !a3 || !a2 )
  {
    v9 = -2147024809;
    goto LABEL_24;
  }
  v9 = STRU::Copy((STRU *)v23, a3);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v21);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v21 + 48LL))(
             v21,
             L"site",
             &v20);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v20 + 112LL))(
               v20,
               L"id",
               a4,
               0);
        if ( v9 >= 0 )
        {
          do
          {
            v10 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 *, _QWORD))(*(_QWORD *)v20 + 128LL);
            Str = STRU::QueryStr((STRU *)v23);
            v9 = v10(v20, L"name", Str, 0);
            if ( v9 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v21 + 56LL))(
                      v21,
                      v20,
                      0xFFFFFFFFLL,
                      0);
              v9 = v12;
              v13 = v12;
              if ( v12 >= 0 )
                continue;
              if ( v12 == -2147024713 )
              {
                v9 = STRU::Append((STRU *)v23, L"_");
                if ( v9 >= 0 )
                {
                  v14 = STRU::QueryStr((struct ABO_NODE *)((char *)a2 + 56));
                  v9 = STRU::Append((STRU *)v23, v14);
                  if ( v9 >= 0 )
                    continue;
                }
              }
            }
            goto LABEL_24;
          }
          while ( v13 == -2147024713 );
          v15 = (PROPERTY_ENTRY *)operator new(0x50u);
          if ( !v15 )
            goto LABEL_22;
          v8 = PROPERTY_ENTRY::PROPERTY_ENTRY(v15, 1);
          if ( !v8 )
            goto LABEL_22;
          *(&v22.dwMDDataLen + 1) = 0;
          *(_QWORD *)&v22.dwMDDataTag = 0;
          v22.dwMDIdentifier = 1015;
          v22.dwMDAttributes = 1;
          v22.dwMDDataType = 2;
          v22.dwMDUserType = 1;
          v22.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v23);
          v22.dwMDDataLen = 2 * STRU::QueryCCH((STRU *)v23) + 2;
          v9 = PROPERTY_ENTRY::Create(v8, &v22);
          if ( v9 < 0 )
            goto LABEL_24;
          v9 = PROPERTY_BAG::AddEntry((struct ABO_NODE *)((char *)a2 + 184), v8, 1);
          if ( v9 < 0 )
            goto LABEL_24;
          PROPERTY_MAPPING::DereferencePropertyMapping(v8);
          v8 = 0;
          v16 = (SITE_CUSTOM_PROVIDER *)operator new(0xB0u);
          if ( !v16
            || (v17 = SITE_CUSTOM_PROVIDER::SITE_CUSTOM_PROVIDER(
                        v16,
                        a2,
                        v20,
                        *((struct INativeConfigurationElement **)this + 3))) == 0 )
          {
LABEL_22:
            v9 = -2147024888;
            goto LABEL_24;
          }
          v18 = STRU::QueryStr((STRU *)v23);
          v9 = SITE_CUSTOM_PROVIDER::Create(v17, v18);
          if ( v9 >= 0 )
            v9 = ABO_NODE::AddProvider(a2, v17);
          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v17);
        }
      }
    }
  }
LABEL_24:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v8 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v8);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012718  push    rbp
0x18001271a  push    rbx
0x18001271b  push    rsi
0x18001271c  push    rdi
0x18001271d  push    r14
0x18001271f  push    r15
0x180012721  lea     rbp, [rsp-2Fh]
0x180012726  sub     rsp, 0B8h
0x18001272d  mov     rax, cs:__security_cookie
0x180012734  xor     rax, rsp
0x180012737  mov     [rbp+57h+var_40], rax
0x18001273b  mov     r15, rcx
0x18001273e  mov     [rbp+57h+var_B0], 0
0x180012746  lea     rcx, [rbp+57h+var_78]
0x18001274a  mov     [rbp+57h+var_A8], 0
0x180012752  mov     esi, r9d
0x180012755  mov     rbx, r8
0x180012758  mov     r14, rdx
0x18001275b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012761  xor     edi, edi
0x180012763  test    rbx, rbx
0x180012766  jz      loc_1800129B5
0x18001276c  test    r14, r14
0x18001276f  jz      loc_1800129B5
0x180012775  mov     rdx, rbx
0x180012778  lea     rcx, [rbp+57h+var_78]
0x18001277c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012782  mov     ebx, eax
0x180012784  test    eax, eax
0x180012786  js      loc_1800129BA
0x18001278c  mov     rcx, [r15+18h]
0x180012790  lea     rdx, [rbp+57h+var_A8]
0x180012794  mov     rax, [rcx]
0x180012797  mov     rax, [rax+28h]
0x18001279b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a0  mov     ebx, eax
0x1800127a2  test    eax, eax
0x1800127a4  js      loc_1800129BA
0x1800127aa  mov     rcx, [rbp+57h+var_A8]
0x1800127ae  lea     r8, [rbp+57h+var_B0]
0x1800127b2  lea     rdx, aSite; "site"
0x1800127b9  mov     rax, [rcx]
0x1800127bc  mov     rax, [rax+30h]
0x1800127c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127c5  mov     ebx, eax
0x1800127c7  test    eax, eax
0x1800127c9  js      loc_1800129BA
0x1800127cf  mov     rcx, [rbp+57h+var_B0]
0x1800127d3  lea     rdx, aId; "id"
0x1800127da  xor     r9d, r9d
0x1800127dd  mov     r8d, esi
0x1800127e0  mov     rax, [rcx]
0x1800127e3  mov     rax, [rax+70h]
0x1800127e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ec  mov     ebx, eax
0x1800127ee  test    eax, eax
0x1800127f0  js      loc_1800129BA
0x1800127f6  mov     rax, [rbp+57h+var_B0]
0x1800127fa  mov     rcx, [rax]
0x1800127fd  mov     rbx, [rcx+80h]
0x180012804  lea     rcx, [rbp+57h+var_78]
0x180012808  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001280e  mov     rcx, [rbp+57h+var_B0]
0x180012812  lea     rdx, aName; "name"
0x180012819  mov     r8, rax
0x18001281c  xor     r9d, r9d
0x18001281f  mov     rax, rbx
0x180012822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012827  mov     ebx, eax
0x180012829  test    eax, eax
0x18001282b  js      loc_1800129BA
0x180012831  mov     rcx, [rbp+57h+var_A8]
0x180012835  xor     r9d, r9d
0x180012838  mov     rdx, [rbp+57h+var_B0]
0x18001283c  or      r8d, 0FFFFFFFFh
0x180012840  mov     rax, [rcx]
0x180012843  mov     rax, [rax+38h]
0x180012847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001284c  mov     ebx, eax
0x18001284e  mov     esi, eax
0x180012850  test    eax, eax
0x180012852  jns     short loc_18001289B
0x180012854  cmp     eax, 800700B7h
0x180012859  jnz     loc_1800129BA
0x18001285f  lea     rdx, asc_18003374C; "_"
0x180012866  lea     rcx, [rbp+57h+var_78]
0x18001286a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180012870  mov     ebx, eax
0x180012872  test    eax, eax
0x180012874  js      loc_1800129BA
0x18001287a  lea     rcx, [r14+38h]
0x18001287e  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012884  mov     rdx, rax
0x180012887  lea     rcx, [rbp+57h+var_78]
0x18001288b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180012891  mov     ebx, eax
0x180012893  test    eax, eax
0x180012895  js      loc_1800129BA
0x18001289b  cmp     esi, 800700B7h
0x1800128a1  jz      loc_1800127F6
0x1800128a7  mov     ecx, 50h ; 'P'; Size
0x1800128ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800128b1  test    rax, rax
0x1800128b4  jz      loc_1800129AE
0x1800128ba  mov     esi, 1
0x1800128bf  mov     rcx, rax; this
0x1800128c2  mov     edx, esi; int
0x1800128c4  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x1800128c9  mov     rdi, rax
0x1800128cc  test    rax, rax
0x1800128cf  jz      loc_1800129AE
0x1800128d5  lea     rcx, [rbp+57h+var_78]
0x1800128d9  mov     dword ptr [rbp+57h+var_A0+14h], 0
0x1800128e0  mov     qword ptr [rbp+57h+var_A0.dwMDDataTag], 0
0x1800128e8  mov     [rbp+57h+var_A0.dwMDIdentifier], 3F7h
0x1800128ef  mov     [rbp+57h+var_A0.dwMDAttributes], esi
0x1800128f2  mov     [rbp+57h+var_A0.dwMDDataType], 2
0x1800128f9  mov     [rbp+57h+var_A0.dwMDUserType], esi
0x1800128fc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012902  lea     rcx, [rbp+57h+var_78]
0x180012906  mov     [rbp+57h+var_A0.pbMDData], rax
0x18001290a  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180012910  lea     rdx, [rbp+57h+var_A0]; struct _METADATA_RECORD *
0x180012914  mov     rcx, rdi; this
0x180012917  lea     eax, ds:2[rax*2]
0x18001291e  mov     [rbp+57h+var_A0.dwMDDataLen], eax
0x180012921  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x180012926  mov     ebx, eax
0x180012928  test    eax, eax
0x18001292a  js      loc_1800129BA
0x180012930  lea     rcx, [r14+0B8h]; this
0x180012937  mov     r8d, esi; int
0x18001293a  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x18001293d  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180012942  mov     ebx, eax
0x180012944  test    eax, eax
0x180012946  js      short loc_1800129BA
0x180012948  mov     rcx, rdi; this
0x18001294b  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180012950  mov     ecx, 0B0h; Size
0x180012955  xor     edi, edi
0x180012957  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001295c  test    rax, rax
0x18001295f  jz      short loc_1800129AE
0x180012961  mov     r9, [r15+18h]; struct INativeConfigurationElement *
0x180012965  mov     rdx, r14; struct ABO_NODE *
0x180012968  mov     r8, [rbp+57h+var_B0]; struct INativeConfigurationElement *
0x18001296c  mov     rcx, rax; this
0x18001296f  call    ??0SITE_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; SITE_CUSTOM_PROVIDER::SITE_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180012974  mov     rsi, rax
0x180012977  test    rax, rax
0x18001297a  jz      short loc_1800129AE
0x18001297c  lea     rcx, [rbp+57h+var_78]
0x180012980  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012986  mov     rdx, rax; unsigned __int16 *
0x180012989  mov     rcx, rsi; this
0x18001298c  call    ?Create@SITE_CUSTOM_PROVIDER@@QEAAJPEBG@Z; SITE_CUSTOM_PROVIDER::Create(ushort const *)
0x180012991  mov     ebx, eax
0x180012993  test    eax, eax
0x180012995  js      short loc_1800129A4
0x180012997  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x18001299a  mov     rcx, r14; this
0x18001299d  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x1800129a2  mov     ebx, eax
0x1800129a4  mov     rcx, rsi; this
0x1800129a7  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x1800129ac  jmp     short loc_1800129BA
0x1800129ae  mov     ebx, 80070008h
0x1800129b3  jmp     short loc_1800129BA
0x1800129b5  mov     ebx, 80070057h
0x1800129ba  mov     rcx, [rbp+57h+var_A8]
0x1800129be  test    rcx, rcx
0x1800129c1  jz      short loc_1800129D7
0x1800129c3  mov     rax, [rcx]
0x1800129c6  mov     rax, [rax+10h]
0x1800129ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129cf  mov     [rbp+57h+var_A8], 0
0x1800129d7  mov     rcx, [rbp+57h+var_B0]
0x1800129db  test    rcx, rcx
0x1800129de  jz      short loc_1800129F4
0x1800129e0  mov     rax, [rcx]
0x1800129e3  mov     rax, [rax+10h]
0x1800129e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129ec  mov     [rbp+57h+var_B0], 0
0x1800129f4  test    rdi, rdi
0x1800129f7  jz      short loc_180012A01
0x1800129f9  mov     rcx, rdi; this
0x1800129fc  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180012a01  lea     rcx, [rbp+57h+var_78]
0x180012a05  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012a0b  mov     eax, ebx
0x180012a0d  mov     rcx, [rbp+57h+var_40]
0x180012a11  xor     rcx, rsp; StackCookie
0x180012a14  call    __security_check_cookie
0x180012a19  add     rsp, 0B8h
0x180012a20  pop     r15
0x180012a22  pop     r14
0x180012a24  pop     rdi
0x180012a25  pop     rsi
0x180012a26  pop     rbx
0x180012a27  pop     rbp
0x180012a28  retn
```

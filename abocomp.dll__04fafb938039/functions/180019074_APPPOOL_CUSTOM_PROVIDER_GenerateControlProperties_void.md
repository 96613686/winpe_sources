# APPPOOL_CUSTOM_PROVIDER::GenerateControlProperties(void)

- ea: `0x180019074`
- end: `0x1800193e9`
- name: `?GenerateControlProperties@APPPOOL_CUSTOM_PROVIDER@@AEAAJXZ`
- size: `885`
- prototype: `__int64 __fastcall(APPPOOL_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180011c50`

## callees

- `0x180002990`
- `0x1800065a8`
- `0x1800077dc`
- `0x18000fa00`
- `0x18000fd48`
- `0x18000fec4`
- `0x180016acc`
- `0x180019074`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180019134`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180019134`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001911e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001911e`

## pseudocode

```c
__int64 __fastcall APPPOOL_CUSTOM_PROVIDER::GenerateControlProperties(APPPOOL_CUSTOM_PROVIDER *this)
{
  __int64 v2; // rcx
  PROPERTY_ENTRY *v3; // rdi
  int v4; // ebx
  _DWORD *v5; // rsi
  int Entry; // eax
  PROPERTY_ENTRY *v7; // rax
  PROPERTY_ENTRY *v8; // rax
  PROPERTY_BAG *v9; // rcx
  int v10; // eax
  PROPERTY_ENTRY *v11; // rax
  PROPERTY_BAG *v12; // rcx
  int v13; // eax
  PROPERTY_ENTRY *v14; // rax
  struct _METADATA_RECORD v16; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+B0h] [rbp+48h] BYREF
  int v18; // [rsp+B8h] [rbp+50h] BYREF
  struct PROPERTY_ENTRY *v19; // [rsp+C0h] [rbp+58h] BYREF
  const unsigned __int16 *v20; // [rsp+C8h] [rbp+60h] BYREF

  v20 = 0;
  v2 = *((_QWORD *)this + 3);
  v17 = 0;
  v18 = 0;
  v3 = 0;
  v19 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v2 + 64LL))(
         v2,
         L"name",
         &v20,
         0,
         0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 72LL))(
         *((_QWORD *)this + 3),
         L"autoStart",
         &v18,
         0,
         0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = operator new(0x48u);
  if ( !v5 )
    return (unsigned int)-2147024888;
  *(_QWORD *)v5 = &APPPOOL_CONTROL_RECORD_PROVIDER::`vftable';
  STRU::STRU((STRU *)(v5 + 4));
  v5[2] = 1;
  v4 = STRU::Copy((STRU *)(v5 + 4), v20);
  if ( v4 < 0 )
    goto LABEL_33;
  Entry = PROPERTY_BAG::FindEntry((PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL), 0x2343u, &v19);
  v4 = Entry;
  if ( Entry >= 0 )
  {
    v3 = v19;
  }
  else
  {
    if ( Entry != -2147024894 )
      goto LABEL_30;
    v7 = (PROPERTY_ENTRY *)operator new(0x50u);
    if ( !v7 )
      goto LABEL_21;
    v8 = PROPERTY_ENTRY::PROPERTY_ENTRY(v7, 1);
    v3 = v8;
    if ( !v8 )
      goto LABEL_21;
    *(_QWORD *)&v16.dwMDDataTag = 0;
    v17 = 4;
    *(_QWORD *)&v16.dwMDDataLen = 4;
    v16.dwMDIdentifier = 9027;
    v16.pbMDData = (unsigned __int8 *)&v17;
    v16.dwMDAttributes = 16;
    v16.dwMDUserType = 1;
    v16.dwMDDataType = 1;
    v4 = PROPERTY_ENTRY::Create(v8, &v16);
    if ( v4 < 0 )
      goto LABEL_33;
    v4 = PROPERTY_BAG::AddEntry((PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL), v3, 1);
    if ( v4 < 0 )
      goto LABEL_33;
  }
  PROPERTY_ENTRY::SetRecordProvider(v3, (struct IPropertyRecordProvider *)v5);
  PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  v9 = (PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL);
  v19 = 0;
  v10 = PROPERTY_BAG::FindEntry(v9, 0x44Bu, &v19);
  v4 = v10;
  if ( v10 >= 0 )
  {
    v3 = v19;
  }
  else
  {
    if ( v10 != -2147024894 )
      goto LABEL_30;
    v11 = (PROPERTY_ENTRY *)operator new(0x50u);
    if ( !v11 )
    {
LABEL_20:
      v3 = 0;
      goto LABEL_21;
    }
    v3 = PROPERTY_ENTRY::PROPERTY_ENTRY(v11, 1);
    if ( !v3 )
    {
LABEL_21:
      v4 = -2147024888;
      goto LABEL_33;
    }
    v17 = 0;
    v16.pbMDData = (unsigned __int8 *)&v17;
    *(_QWORD *)&v16.dwMDDataLen = 4;
    *(_QWORD *)&v16.dwMDDataTag = 0;
    v16.dwMDIdentifier = 1099;
    v16.dwMDAttributes = 16;
    v16.dwMDUserType = 1;
    v16.dwMDDataType = 1;
    v4 = PROPERTY_ENTRY::Create(v3, &v16);
    if ( v4 < 0 )
      goto LABEL_33;
    v4 = PROPERTY_BAG::AddEntry((PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL), v3, 1);
    if ( v4 < 0 )
      goto LABEL_33;
  }
  PROPERTY_ENTRY::SetRecordProvider(v3, (struct IPropertyRecordProvider *)v5);
  PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  v12 = (PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL);
  v19 = 0;
  v13 = PROPERTY_BAG::FindEntry(v12, 0x2342u, &v19);
  v4 = v13;
  if ( v13 >= 0 )
  {
    v3 = v19;
LABEL_32:
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
    v3 = 0;
    goto LABEL_33;
  }
  if ( v13 != -2147024894 )
  {
LABEL_30:
    v3 = v19;
    goto LABEL_33;
  }
  v14 = (PROPERTY_ENTRY *)operator new(0x50u);
  if ( !v14 )
    goto LABEL_20;
  v3 = PROPERTY_ENTRY::PROPERTY_ENTRY(v14, 1);
  if ( !v3 )
    goto LABEL_21;
  *(_QWORD *)&v16.dwMDDataLen = 4;
  *(_QWORD *)&v16.dwMDDataTag = 0;
  v16.dwMDIdentifier = 9026;
  v16.dwMDAttributes = 16;
  v17 = 2 - (v18 != 0);
  v16.dwMDDataType = 1;
  v16.dwMDUserType = 1;
  v16.pbMDData = (unsigned __int8 *)&v17;
  v4 = PROPERTY_ENTRY::Create(v3, &v16);
  if ( v4 >= 0 )
  {
    v4 = PROPERTY_BAG::AddEntry((PROPERTY_BAG *)(*((_QWORD *)this + 2) + 184LL), v3, 0);
    if ( v4 >= 0 )
      goto LABEL_32;
  }
LABEL_33:
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 8LL))(v5);
  if ( v3 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019074  push    rbp
0x180019076  push    rbx
0x180019077  push    rsi
0x180019078  push    rdi
0x180019079  push    r12
0x18001907b  push    r13
0x18001907d  push    r14
0x18001907f  push    r15
0x180019081  mov     rbp, rsp
0x180019084  sub     rsp, 68h
0x180019088  xor     r15d, r15d
0x18001908b  lea     r8, [rbp+arg_18]
0x18001908f  mov     r14, rcx
0x180019092  mov     [rbp+arg_18], r15
0x180019096  mov     rcx, [rcx+18h]
0x18001909a  lea     rdx, aName; "name"
0x1800190a1  mov     [rbp+arg_0], r15d
0x1800190a5  xor     r9d, r9d
0x1800190a8  mov     [rbp+arg_8], r15d
0x1800190ac  mov     edi, r15d
0x1800190af  mov     [rbp+arg_10], r15
0x1800190b3  mov     rax, [rcx]
0x1800190b6  mov     [rsp+68h+var_48], r15
0x1800190bb  mov     rax, [rax+40h]
0x1800190bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c4  mov     ebx, eax
0x1800190c6  test    eax, eax
0x1800190c8  js      loc_1800193D6
0x1800190ce  mov     rcx, [r14+18h]
0x1800190d2  lea     r8, [rbp+arg_8]
0x1800190d6  xor     r9d, r9d
0x1800190d9  mov     [rsp+68h+var_48], r15
0x1800190de  lea     rdx, aAutostart; "autoStart"
0x1800190e5  mov     rax, [rcx]
0x1800190e8  mov     rax, [rax+48h]
0x1800190ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f1  mov     ebx, eax
0x1800190f3  test    eax, eax
0x1800190f5  js      loc_1800193D6
0x1800190fb  lea     ecx, [r15+48h]; Size
0x1800190ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019104  mov     rsi, rax
0x180019107  test    rax, rax
0x18001910a  jz      loc_1800193D1
0x180019110  lea     rax, ??_7APPPOOL_CONTROL_RECORD_PROVIDER@@6B@; const APPPOOL_CONTROL_RECORD_PROVIDER::`vftable'
0x180019117  lea     rcx, [rsi+10h]
0x18001911b  mov     [rsi], rax
0x18001911e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019124  lea     r12d, [r15+1]
0x180019128  mov     [rsi+8], r12d
0x18001912c  lea     rcx, [rsi+10h]
0x180019130  mov     rdx, [rbp+arg_18]
0x180019134  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001913a  mov     ebx, eax
0x18001913c  test    eax, eax
0x18001913e  js      loc_1800193B3
0x180019144  mov     rcx, [r14+10h]
0x180019148  lea     r8, [rbp+arg_10]; struct PROPERTY_ENTRY **
0x18001914c  mov     r13d, 0B8h
0x180019152  mov     edx, 2343h; unsigned int
0x180019157  add     rcx, r13; this
0x18001915a  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001915f  mov     ebx, eax
0x180019161  test    eax, eax
0x180019163  jns     loc_1800191FE
0x180019169  cmp     eax, 80070002h
0x18001916e  jnz     loc_18001939E
0x180019174  lea     ecx, [r15+50h]; Size
0x180019178  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001917d  test    rax, rax
0x180019180  jz      loc_1800192CA
0x180019186  mov     edx, r12d; int
0x180019189  mov     rcx, rax; this
0x18001918c  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x180019191  mov     rdi, rax
0x180019194  test    rax, rax
0x180019197  jz      loc_1800192CA
0x18001919d  lea     eax, [r15+4]
0x1800191a1  mov     qword ptr [rbp+var_38.dwMDDataTag], r15
0x1800191a5  mov     [rbp+arg_0], eax
0x1800191a8  lea     rdx, [rbp+var_38]; struct _METADATA_RECORD *
0x1800191ac  mov     qword ptr [rbp+var_38.dwMDDataLen], rax
0x1800191b0  mov     rcx, rdi; this
0x1800191b3  lea     rax, [rbp+arg_0]
0x1800191b7  mov     [rbp+var_38.dwMDIdentifier], 2343h
0x1800191be  mov     [rbp+var_38.pbMDData], rax
0x1800191c2  mov     [rbp+var_38.dwMDAttributes], 10h
0x1800191c9  mov     [rbp+var_38.dwMDUserType], r12d
0x1800191cd  mov     [rbp+var_38.dwMDDataType], r12d
0x1800191d1  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x1800191d6  mov     ebx, eax
0x1800191d8  test    eax, eax
0x1800191da  js      loc_1800193B3
0x1800191e0  mov     rcx, [r14+10h]
0x1800191e4  mov     r8d, r12d; int
0x1800191e7  add     rcx, r13; this
0x1800191ea  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x1800191ed  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x1800191f2  mov     ebx, eax
0x1800191f4  test    eax, eax
0x1800191f6  js      loc_1800193B3
0x1800191fc  jmp     short loc_180019202
0x1800191fe  mov     rdi, [rbp+arg_10]
0x180019202  mov     rdx, rsi; struct IPropertyRecordProvider *
0x180019205  mov     rcx, rdi; this
0x180019208  call    ?SetRecordProvider@PROPERTY_ENTRY@@QEAAXPEAVIPropertyRecordProvider@@@Z; PROPERTY_ENTRY::SetRecordProvider(IPropertyRecordProvider *)
0x18001920d  mov     rcx, rdi; this
0x180019210  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180019215  mov     rcx, [r14+10h]
0x180019219  lea     r8, [rbp+arg_10]; struct PROPERTY_ENTRY **
0x18001921d  add     rcx, r13; this
0x180019220  mov     [rbp+arg_10], r15
0x180019224  mov     edx, 44Bh; unsigned int
0x180019229  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001922e  mov     ebx, eax
0x180019230  test    eax, eax
0x180019232  jns     loc_1800192D4
0x180019238  cmp     eax, 80070002h
0x18001923d  jnz     loc_18001939E
0x180019243  mov     ecx, 50h ; 'P'; Size
0x180019248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001924d  test    rax, rax
0x180019250  jz      short loc_1800192C7
0x180019252  mov     edx, r12d; int
0x180019255  mov     rcx, rax; this
0x180019258  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x18001925d  mov     rdi, rax
0x180019260  test    rax, rax
0x180019263  jz      short loc_1800192CA
0x180019265  lea     rax, [rbp+arg_0]
0x180019269  mov     [rbp+arg_0], r15d
0x18001926d  lea     rdx, [rbp+var_38]; struct _METADATA_RECORD *
0x180019271  mov     [rbp+var_38.pbMDData], rax
0x180019275  mov     rcx, rdi; this
0x180019278  mov     qword ptr [rbp+var_38.dwMDDataLen], 4
0x180019280  mov     qword ptr [rbp+var_38.dwMDDataTag], r15
0x180019284  mov     [rbp+var_38.dwMDIdentifier], 44Bh
0x18001928b  mov     [rbp+var_38.dwMDAttributes], 10h
0x180019292  mov     [rbp+var_38.dwMDUserType], r12d
0x180019296  mov     [rbp+var_38.dwMDDataType], r12d
0x18001929a  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x18001929f  mov     ebx, eax
0x1800192a1  test    eax, eax
0x1800192a3  js      loc_1800193B3
0x1800192a9  mov     rcx, [r14+10h]
0x1800192ad  mov     r8d, r12d; int
0x1800192b0  add     rcx, r13; this
0x1800192b3  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x1800192b6  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x1800192bb  mov     ebx, eax
0x1800192bd  test    eax, eax
0x1800192bf  js      loc_1800193B3
0x1800192c5  jmp     short loc_1800192D8
0x1800192c7  mov     rdi, r15
0x1800192ca  mov     ebx, 80070008h
0x1800192cf  jmp     loc_1800193B3
0x1800192d4  mov     rdi, [rbp+arg_10]
0x1800192d8  mov     rdx, rsi; struct IPropertyRecordProvider *
0x1800192db  mov     rcx, rdi; this
0x1800192de  call    ?SetRecordProvider@PROPERTY_ENTRY@@QEAAXPEAVIPropertyRecordProvider@@@Z; PROPERTY_ENTRY::SetRecordProvider(IPropertyRecordProvider *)
0x1800192e3  mov     rcx, rdi; this
0x1800192e6  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x1800192eb  mov     rcx, [r14+10h]
0x1800192ef  lea     r8, [rbp+arg_10]; struct PROPERTY_ENTRY **
0x1800192f3  add     rcx, r13; this
0x1800192f6  mov     [rbp+arg_10], r15
0x1800192fa  mov     edx, 2342h; unsigned int
0x1800192ff  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180019304  mov     ebx, eax
0x180019306  test    eax, eax
0x180019308  jns     loc_1800193A4
0x18001930e  cmp     eax, 80070002h
0x180019313  jnz     loc_18001939E
0x180019319  mov     ecx, 50h ; 'P'; Size
0x18001931e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019323  test    rax, rax
0x180019326  jz      short loc_1800192C7
0x180019328  mov     edx, r12d; int
0x18001932b  mov     rcx, rax; this
0x18001932e  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x180019333  mov     rdi, rax
0x180019336  test    rax, rax
0x180019339  jz      short loc_1800192CA
0x18001933b  mov     eax, [rbp+arg_8]
0x18001933e  lea     rdx, [rbp+var_38]; struct _METADATA_RECORD *
0x180019342  neg     eax
0x180019344  mov     qword ptr [rbp+var_38.dwMDDataLen], 4
0x18001934c  lea     rax, [rbp+arg_0]
0x180019350  mov     qword ptr [rbp+var_38.dwMDDataTag], r15
0x180019354  sbb     ecx, ecx
0x180019356  mov     [rbp+var_38.dwMDIdentifier], 2342h
0x18001935d  add     ecx, 2
0x180019360  mov     [rbp+var_38.dwMDAttributes], 10h
0x180019367  mov     [rbp+arg_0], ecx
0x18001936a  mov     rcx, rdi; this
0x18001936d  mov     [rbp+var_38.dwMDDataType], r12d
0x180019371  mov     [rbp+var_38.dwMDUserType], r12d
0x180019375  mov     [rbp+var_38.pbMDData], rax
0x180019379  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x18001937e  mov     ebx, eax
0x180019380  test    eax, eax
0x180019382  js      short loc_1800193B3
0x180019384  mov     rcx, [r14+10h]
0x180019388  xor     r8d, r8d; int
0x18001938b  add     rcx, r13; this
0x18001938e  mov     rdx, rdi; struct PROPERTY_ENTRY *
0x180019391  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180019396  mov     ebx, eax
0x180019398  test    eax, eax
0x18001939a  js      short loc_1800193B3
0x18001939c  jmp     short loc_1800193A8
0x18001939e  mov     rdi, [rbp+arg_10]
0x1800193a2  jmp     short loc_1800193B3
0x1800193a4  mov     rdi, [rbp+arg_10]
0x1800193a8  mov     rcx, rdi; this
0x1800193ab  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x1800193b0  mov     rdi, r15
0x1800193b3  mov     rax, [rsi]
0x1800193b6  mov     rcx, rsi
0x1800193b9  mov     rax, [rax+8]
0x1800193bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c2  test    rdi, rdi
0x1800193c5  jz      short loc_1800193D6
0x1800193c7  mov     rcx, rdi; this
0x1800193ca  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x1800193cf  jmp     short loc_1800193D6
0x1800193d1  mov     ebx, 80070008h
0x1800193d6  mov     eax, ebx
0x1800193d8  add     rsp, 68h
0x1800193dc  pop     r15
0x1800193de  pop     r14
0x1800193e0  pop     r13
0x1800193e2  pop     r12
0x1800193e4  pop     rdi
0x1800193e5  pop     rsi
0x1800193e6  pop     rbx
0x1800193e7  pop     rbp
0x1800193e8  retn
```

# APPLICATION_CUSTOM_PROVIDER::GenerateLegacyIdentifiers(void)

- ea: `0x18001a690`
- end: `0x18001a859`
- name: `?GenerateLegacyIdentifiers@APPLICATION_CUSTOM_PROVIDER@@QEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(APPLICATION_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180016b1c`
- `0x18001a860`

## callees

- `0x18000341a`
- `0x180003460`
- `0x1800077dc`
- `0x18000a6fc`
- `0x18000fec4`
- `0x18001a690`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a7ac`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001a7ac`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001a7e4`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001a7e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001a6e0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001a6e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a836`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001a836`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001a79e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001a7f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001a79e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001a7f5`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::GenerateLegacyIdentifiers(APPLICATION_CUSTOM_PROVIDER *this)
{
  __int64 v2; // rsi
  ABO_NODE *v3; // rcx
  int Entry; // ebx
  const unsigned __int16 *Str; // rax
  unsigned __int8 *v6; // rax
  ABO_NODE *v7; // rcx
  struct PROPERTY_ENTRY *v8; // rcx
  struct PROPERTY_ENTRY *v10; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+28h] [rbp-D8h] BYREF
  struct _METADATA_RECORD v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v14[256]; // [rsp+90h] [rbp-70h] BYREF

  v11 = 0;
  memset_0(v14, 0, sizeof(v14));
  STRU::STRU((STRU *)v13, v14, 0x100u);
  v2 = *((_QWORD *)this + 2);
  v10 = 0;
  if ( (int)PROPERTY_BAG::FindEntry((PROPERTY_BAG *)(v2 + 184), 0x838u, &v10) >= 0 )
  {
    PROPERTY_MAPPING::DereferencePropertyMapping(v10);
    v10 = 0;
  }
  else
  {
    v3 = (ABO_NODE *)*((_QWORD *)this + 2);
    v12.pbMDData = (unsigned __int8 *)&v11;
    *(_QWORD *)&v12.dwMDIdentifier = 2104;
    *(_QWORD *)&v12.dwMDDataLen = 4;
    *(_QWORD *)&v12.dwMDDataTag = 0;
    v12.dwMDUserType = 100;
    v12.dwMDDataType = 1;
    Entry = ABO_NODE::SetData(v3, &v12, 1);
    if ( Entry < 0 )
    {
LABEL_8:
      v8 = v10;
      goto LABEL_10;
    }
  }
  Entry = PROPERTY_BAG::FindEntry((PROPERTY_BAG *)(v2 + 184), 0x837u, &v10);
  if ( Entry < 0 )
  {
    Str = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 256LL));
    Entry = STRU::Copy((STRU *)v13, Str);
    if ( Entry >= 0 )
    {
      *(_QWORD *)&v12.dwMDIdentifier = 2103;
      v12.dwMDUserType = 2;
      v12.dwMDDataType = 2;
      *(&v12.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v12.dwMDDataTag = 0;
      v12.dwMDDataLen = STRU::QueryCB((STRU *)v13) + 2;
      v6 = (unsigned __int8 *)STRU::QueryStr((STRU *)v13);
      v7 = (ABO_NODE *)*((_QWORD *)this + 2);
      v12.pbMDData = v6;
      Entry = ABO_NODE::SetData(v7, &v12, 1);
    }
    goto LABEL_8;
  }
  PROPERTY_MAPPING::DereferencePropertyMapping(v10);
  v8 = 0;
LABEL_10:
  if ( v8 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v8);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x18001a690  push    rbp
0x18001a692  push    rbx
0x18001a693  push    rsi
0x18001a694  push    rdi
0x18001a695  lea     rbp, [rsp-1A8h]
0x18001a69d  sub     rsp, 2A8h
0x18001a6a4  mov     rax, cs:__security_cookie
0x18001a6ab  xor     rax, rsp
0x18001a6ae  mov     [rbp+1C0h+var_30], rax
0x18001a6b5  mov     rdi, rcx
0x18001a6b8  mov     [rsp+2C0h+var_298], 0
0x18001a6c0  lea     rcx, [rbp+1C0h+var_230]; void *
0x18001a6c4  xor     edx, edx; Val
0x18001a6c6  mov     r8d, 200h; Size
0x18001a6cc  call    memset_0
0x18001a6d1  mov     r8d, 100h
0x18001a6d7  lea     rdx, [rbp+1C0h+var_230]
0x18001a6db  lea     rcx, [rsp+2C0h+var_268]
0x18001a6e0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001a6e6  mov     rsi, [rdi+10h]
0x18001a6ea  lea     r8, [rsp+2C0h+var_2A0]; struct PROPERTY_ENTRY **
0x18001a6ef  mov     ebx, 838h
0x18001a6f4  mov     [rsp+2C0h+var_2A0], 0
0x18001a6fd  mov     edx, ebx; unsigned int
0x18001a6ff  lea     rcx, [rsi+0B8h]; this
0x18001a706  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001a70b  test    eax, eax
0x18001a70d  jns     short loc_18001A760
0x18001a70f  mov     rcx, [rdi+10h]; this
0x18001a713  lea     rax, [rsp+2C0h+var_298]
0x18001a718  mov     r8d, 1; int
0x18001a71e  mov     [rsp+2C0h+var_290.pbMDData], rax
0x18001a723  lea     rdx, [rsp+2C0h+var_290]; struct _METADATA_RECORD *
0x18001a728  mov     qword ptr [rsp+2C0h+var_290.dwMDIdentifier], rbx
0x18001a72d  mov     qword ptr [rsp+2C0h+var_290.dwMDDataLen], 4
0x18001a736  mov     qword ptr [rsp+2C0h+var_290.dwMDDataTag], 0
0x18001a73f  mov     [rsp+2C0h+var_290.dwMDUserType], 64h ; 'd'
0x18001a747  mov     [rsp+2C0h+var_290.dwMDDataType], 1
0x18001a74f  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x18001a754  mov     ebx, eax
0x18001a756  test    eax, eax
0x18001a758  js      loc_18001A814
0x18001a75e  jmp     short loc_18001A773
0x18001a760  mov     rcx, [rsp+2C0h+var_2A0]; this
0x18001a765  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001a76a  mov     [rsp+2C0h+var_2A0], 0
0x18001a773  lea     r8, [rsp+2C0h+var_2A0]; struct PROPERTY_ENTRY **
0x18001a778  mov     edx, 837h; unsigned int
0x18001a77d  lea     rcx, [rsi+0B8h]; this
0x18001a784  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001a789  mov     ebx, eax
0x18001a78b  test    eax, eax
0x18001a78d  jns     loc_18001A81B
0x18001a793  mov     rcx, [rdi+10h]
0x18001a797  add     rcx, 100h
0x18001a79e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001a7a4  mov     rdx, rax
0x18001a7a7  lea     rcx, [rsp+2C0h+var_268]
0x18001a7ac  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001a7b2  mov     ebx, eax
0x18001a7b4  test    eax, eax
0x18001a7b6  js      short loc_18001A814
0x18001a7b8  mov     ebx, 2
0x18001a7bd  mov     qword ptr [rsp+2C0h+var_290.dwMDIdentifier], 837h
0x18001a7c6  lea     rcx, [rsp+2C0h+var_268]
0x18001a7cb  mov     [rsp+2C0h+var_290.dwMDUserType], ebx
0x18001a7cf  mov     [rsp+2C0h+var_290.dwMDDataType], ebx
0x18001a7d3  mov     dword ptr [rsp+2C0h+var_290+14h], 0
0x18001a7db  mov     qword ptr [rsp+2C0h+var_290.dwMDDataTag], 0
0x18001a7e4  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18001a7ea  add     eax, ebx
0x18001a7ec  lea     rcx, [rsp+2C0h+var_268]
0x18001a7f1  mov     [rsp+2C0h+var_290.dwMDDataLen], eax
0x18001a7f5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001a7fb  mov     rcx, [rdi+10h]; this
0x18001a7ff  lea     r8d, [rbx-1]; int
0x18001a803  lea     rdx, [rsp+2C0h+var_290]; struct _METADATA_RECORD *
0x18001a808  mov     [rsp+2C0h+var_290.pbMDData], rax
0x18001a80d  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x18001a812  mov     ebx, eax
0x18001a814  mov     rcx, [rsp+2C0h+var_2A0]
0x18001a819  jmp     short loc_18001A827
0x18001a81b  mov     rcx, [rsp+2C0h+var_2A0]; this
0x18001a820  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001a825  xor     ecx, ecx; this
0x18001a827  test    rcx, rcx
0x18001a82a  jz      short loc_18001A831
0x18001a82c  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001a831  lea     rcx, [rsp+2C0h+var_268]
0x18001a836  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001a83c  mov     eax, ebx
0x18001a83e  mov     rcx, [rbp+1C0h+var_30]
0x18001a845  xor     rcx, rsp; StackCookie
0x18001a848  call    __security_check_cookie
0x18001a84d  add     rsp, 2A8h
0x18001a854  pop     rdi
0x18001a855  pop     rsi
0x18001a856  pop     rbx
0x18001a857  pop     rbp
0x18001a858  retn
```

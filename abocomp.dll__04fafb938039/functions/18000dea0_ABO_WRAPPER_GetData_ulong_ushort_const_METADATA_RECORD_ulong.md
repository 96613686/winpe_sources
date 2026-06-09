# ABO_WRAPPER::GetData(ulong,ushort const *,_METADATA_RECORD *,ulong *)

- ea: `0x18000dea0`
- end: `0x18000e15f`
- name: `?GetData@ABO_WRAPPER@@UEAAJKPEBGPEAU_METADATA_RECORD@@PEAK@Z`
- size: `703`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, struct _METADATA_RECORD *@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x180008f28`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000dea0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000ff30`
- `0x18000ffd8`
- `0x180026cdc`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e0e7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e0e7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000df95`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000df95`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000df0b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000df33`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000df0b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000df33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e12b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e136`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e12b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e136`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dfcb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e000`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e034`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e05d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e08d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dfcb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e000`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e034`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e05d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e08d`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000dfee`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000dfee`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetData(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4,
        unsigned int *a5)
{
  struct ABO_TREE *v9; // rdi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  struct ABO_NODE *v12; // rbx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v14; // rax
  ABO_NODE *v15; // rbx
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rax
  ABO_NODE *v18; // rbx
  const unsigned __int16 *v19; // rax
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE_ENTRY *v22; // [rsp+38h] [rbp-C8h] BYREF
  struct ABO_NODE *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_TREE *v24; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v25; // [rsp+50h] [rbp-B0h]
  _BYTE v26[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v28[248]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v29[248]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v25 = a5;
  v23 = 0;
  memset_0(v28, 0, 0x1EAu);
  STRU::STRU((STRU *)v26, v28, 0xF5u);
  memset_0(v29, 0, 0x1EAu);
  STRU::STRU((STRU *)v27, v29, 0xF5u);
  v9 = 0;
  v22 = 0;
  v24 = 0;
  v21 = 3;
  if ( a4 )
  {
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v22);
    if ( HandleEntry >= 0 )
    {
      HandleEntry = HANDLE_ENTRY::GetFullPath(v22, a3, (struct STRU *)v26);
      if ( HandleEntry >= 0 )
      {
        CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
        CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v24);
        v9 = v24;
        HandleEntry = CurrentAboTree;
        if ( CurrentAboTree >= 0 )
        {
          if ( (a4->dwMDAttributes & 1) != 0 )
          {
            v12 = (struct ABO_NODE *)*((_QWORD *)v24 + 2);
            Str = STRU::QueryStr((STRU *)v26);
            HandleEntry = GetLastNodePath(Str, v12, (struct STRU *)v27);
            if ( HandleEntry >= 0 && !STRU::IsEmpty((STRU *)v27) )
            {
              v14 = STRU::QueryStr((STRU *)v27);
              HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v9, v14, 0, (enum ACCESS_GRANTED *)&v21);
              if ( HandleEntry >= 0 )
              {
                v15 = (ABO_NODE *)*((_QWORD *)v9 + 2);
                v16 = STRU::QueryStr((STRU *)v26);
                HandleEntry = ABO_NODE::GetInheritedData(v15, v21, v16, a4, v25);
              }
            }
          }
          else
          {
            v17 = STRU::QueryStr((STRU *)v26);
            HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v9, v17, 0, (enum ACCESS_GRANTED *)&v21);
            if ( HandleEntry >= 0 )
            {
              v18 = (ABO_NODE *)*((_QWORD *)v9 + 2);
              v19 = STRU::QueryStr((STRU *)v26);
              ABO_NODE::FindNode(v18, v19, &v23);
            }
          }
        }
        CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
      }
    }
    if ( v22 )
      HANDLE_ENTRY::DereferenceHandleEntry(v22);
    if ( v9 )
      HANDLE_ENTRY::DereferenceHandleEntry(v9);
    if ( HandleEntry == -2147024894 )
      HandleEntry = -2146646015;
  }
  else
  {
    HandleEntry = -2147024809;
  }
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000dea0  push    rbp
0x18000dea2  push    rbx
0x18000dea3  push    rsi
0x18000dea4  push    rdi
0x18000dea5  push    r13
0x18000dea7  push    r14
0x18000dea9  push    r15
0x18000deab  lea     rbp, [rsp-3C0h]
0x18000deb3  sub     rsp, 4C0h
0x18000deba  mov     rax, cs:__security_cookie
0x18000dec1  xor     rax, rsp
0x18000dec4  mov     [rbp+3F0h+var_40], rax
0x18000decb  mov     rax, [rbp+3F0h+arg_20]
0x18000ded2  mov     r13, r8
0x18000ded5  mov     ebx, edx
0x18000ded7  mov     [rsp+4F0h+var_4A0], rax
0x18000dedc  mov     r14, rcx
0x18000dedf  xor     esi, esi
0x18000dee1  xor     edx, edx; Val
0x18000dee3  mov     [rsp+4F0h+var_4B0], rsi
0x18000dee8  mov     r8d, 1EAh; Size
0x18000deee  lea     rcx, [rbp+3F0h+var_420]; void *
0x18000def2  mov     r15, r9
0x18000def5  call    memset_0
0x18000defa  mov     edi, 0F5h
0x18000deff  lea     rdx, [rbp+3F0h+var_420]
0x18000df03  mov     r8d, edi
0x18000df06  lea     rcx, [rsp+4F0h+var_498]
0x18000df0b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000df11  xor     edx, edx; Val
0x18000df13  lea     rcx, [rbp+3F0h+var_230]; void *
0x18000df1a  mov     r8d, 1EAh; Size
0x18000df20  call    memset_0
0x18000df25  mov     r8d, edi
0x18000df28  lea     rdx, [rbp+3F0h+var_230]
0x18000df2f  lea     rcx, [rbp+3F0h+var_460]
0x18000df33  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000df39  xor     edi, edi
0x18000df3b  mov     [rsp+4F0h+var_4B8], rsi
0x18000df40  mov     [rsp+4F0h+var_4A8], rdi
0x18000df45  mov     [rsp+4F0h+var_4C0], 3
0x18000df4d  test    r15, r15
0x18000df50  jnz     short loc_18000DF5C
0x18000df52  mov     ebx, 80070057h
0x18000df57  jmp     loc_18000E127
0x18000df5c  lea     r8, [rsp+4F0h+var_4B8]; struct HANDLE_ENTRY **
0x18000df61  mov     edx, ebx; unsigned int
0x18000df63  mov     rcx, r14; this
0x18000df66  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000df6b  mov     ebx, eax
0x18000df6d  test    eax, eax
0x18000df6f  js      loc_18000E0ED
0x18000df75  mov     rcx, [rsp+4F0h+var_4B8]; this
0x18000df7a  lea     r8, [rsp+4F0h+var_498]; struct STRU *
0x18000df7f  mov     rdx, r13; unsigned __int16 *
0x18000df82  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000df87  mov     ebx, eax
0x18000df89  test    eax, eax
0x18000df8b  js      loc_18000E0ED
0x18000df91  lea     rcx, [r14+20h]
0x18000df95  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000df9b  lea     rdx, [rsp+4F0h+var_4A8]; struct ABO_TREE **
0x18000dfa0  mov     rcx, r14; this
0x18000dfa3  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000dfa8  mov     rdi, [rsp+4F0h+var_4A8]
0x18000dfad  mov     ebx, eax
0x18000dfaf  test    eax, eax
0x18000dfb1  js      loc_18000E0E3
0x18000dfb7  test    byte ptr [r15+4], 1
0x18000dfbc  lea     rcx, [rsp+4F0h+var_498]
0x18000dfc1  jz      loc_18000E05D
0x18000dfc7  mov     rbx, [rdi+10h]
0x18000dfcb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000dfd1  lea     r8, [rbp+3F0h+var_460]; struct STRU *
0x18000dfd5  mov     rdx, rbx; struct ABO_NODE *
0x18000dfd8  mov     rcx, rax; unsigned __int16 *
0x18000dfdb  call    ?GetLastNodePath@@YAJPEBGPEAVABO_NODE@@PEAVSTRU@@@Z; GetLastNodePath(ushort const *,ABO_NODE *,STRU *)
0x18000dfe0  mov     ebx, eax
0x18000dfe2  test    eax, eax
0x18000dfe4  js      loc_18000E0E3
0x18000dfea  lea     rcx, [rbp+3F0h+var_460]
0x18000dfee  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000dff4  test    al, al
0x18000dff6  jnz     loc_18000E0E3
0x18000dffc  lea     rcx, [rbp+3F0h+var_460]
0x18000e000  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e006  lea     rcx, [rsp+4F0h+var_4C0]
0x18000e00b  xor     r9d, r9d
0x18000e00e  mov     [rsp+4F0h+var_4D0], rcx
0x18000e013  mov     r8, rax
0x18000e016  mov     rcx, r14
0x18000e019  mov     rdx, rdi
0x18000e01c  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000e021  mov     ebx, eax
0x18000e023  test    eax, eax
0x18000e025  js      loc_18000E0E3
0x18000e02b  mov     rbx, [rdi+10h]
0x18000e02f  lea     rcx, [rsp+4F0h+var_498]
0x18000e034  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e03a  mov     r8, [rsp+4F0h+var_4A0]
0x18000e03f  mov     r9, r15
0x18000e042  mov     edx, [rsp+4F0h+var_4C0]
0x18000e046  mov     rcx, rbx
0x18000e049  mov     [rsp+4F0h+var_4D0], r8
0x18000e04e  mov     r8, rax
0x18000e051  call    ?GetInheritedData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@PEBGPEAU_METADATA_RECORD@@PEAK@Z; ABO_NODE::GetInheritedData(ACCESS_GRANTED,ushort const *,_METADATA_RECORD *,ulong *)
0x18000e056  mov     ebx, eax
0x18000e058  jmp     loc_18000E0E3
0x18000e05d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e063  lea     rcx, [rsp+4F0h+var_4C0]
0x18000e068  xor     r9d, r9d
0x18000e06b  mov     [rsp+4F0h+var_4D0], rcx
0x18000e070  mov     r8, rax
0x18000e073  mov     rcx, r14
0x18000e076  mov     rdx, rdi
0x18000e079  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000e07e  mov     ebx, eax
0x18000e080  test    eax, eax
0x18000e082  js      short loc_18000E0E3
0x18000e084  mov     rbx, [rdi+10h]
0x18000e088  lea     rcx, [rsp+4F0h+var_498]
0x18000e08d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e093  lea     r8, [rsp+4F0h+var_4B0]; struct ABO_NODE **
0x18000e098  mov     rcx, rbx; this
0x18000e09b  mov     rdx, rax; unsigned __int16 *
0x18000e09e  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000e0a3  mov     ebx, eax
0x18000e0a5  test    eax, eax
0x18000e0a7  js      short loc_18000E0DE
0x18000e0a9  mov     edx, [rsp+4F0h+var_4C0]
0x18000e0ad  mov     ecx, [r15]
0x18000e0b0  call    ?IsReadAccessAllowed@PROPERTY_ENTRY@@SAHKW4ACCESS_GRANTED@@@Z; PROPERTY_ENTRY::IsReadAccessAllowed(ulong,ACCESS_GRANTED)
0x18000e0b5  mov     rsi, [rsp+4F0h+var_4B0]
0x18000e0ba  test    eax, eax
0x18000e0bc  jnz     short loc_18000E0C5
0x18000e0be  mov     ebx, 80070005h
0x18000e0c3  jmp     short loc_18000E0E3
0x18000e0c5  mov     r8, [rsp+4F0h+var_4A0]; unsigned int *
0x18000e0ca  lea     rcx, [rsi+0B8h]; this
0x18000e0d1  mov     rdx, r15; struct _METADATA_RECORD *
0x18000e0d4  call    ?GetData@PROPERTY_BAG@@QEAAJPEAU_METADATA_RECORD@@PEAK@Z; PROPERTY_BAG::GetData(_METADATA_RECORD *,ulong *)
0x18000e0d9  jmp     loc_18000E056
0x18000e0de  mov     rsi, [rsp+4F0h+var_4B0]
0x18000e0e3  lea     rcx, [r14+20h]
0x18000e0e7  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000e0ed  cmp     [rsp+4F0h+var_4B8], 0
0x18000e0f3  jz      short loc_18000E0FF
0x18000e0f5  mov     rcx, [rsp+4F0h+var_4B8]; this
0x18000e0fa  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e0ff  test    rsi, rsi
0x18000e102  jz      short loc_18000E10C
0x18000e104  mov     rcx, rsi; this
0x18000e107  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000e10c  test    rdi, rdi
0x18000e10f  jz      short loc_18000E119
0x18000e111  mov     rcx, rdi; this
0x18000e114  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e119  cmp     ebx, 80070002h
0x18000e11f  mov     eax, 800CC801h
0x18000e124  cmovz   ebx, eax
0x18000e127  lea     rcx, [rbp+3F0h+var_460]
0x18000e12b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e131  lea     rcx, [rsp+4F0h+var_498]
0x18000e136  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e13c  mov     eax, ebx
0x18000e13e  mov     rcx, [rbp+3F0h+var_40]
0x18000e145  xor     rcx, rsp; StackCookie
0x18000e148  call    __security_check_cookie
0x18000e14d  add     rsp, 4C0h
0x18000e154  pop     r15
0x18000e156  pop     r14
0x18000e158  pop     r13
0x18000e15a  pop     rdi
0x18000e15b  pop     rsi
0x18000e15c  pop     rbx
0x18000e15d  pop     rbp
0x18000e15e  retn
```

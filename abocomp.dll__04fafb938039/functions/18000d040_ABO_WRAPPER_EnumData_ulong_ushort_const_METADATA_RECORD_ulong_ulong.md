# ABO_WRAPPER::EnumData(ulong,ushort const *,_METADATA_RECORD *,ulong,ulong *)

- ea: `0x18000d040`
- end: `0x18000d350`
- name: `?EnumData@ABO_WRAPPER@@UEAAJKPEBGPEAU_METADATA_RECORD@@KPEAK@Z`
- size: `784`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x18000672c`
- `0x180007ac8`
- `0x1800086f0`
- `0x1800087bc`
- `0x18000b68c`
- `0x18000d040`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000fe3c`
- `0x180026cdc`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d2c2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d2c2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d158`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d158`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d0b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d0d6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d0b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d0d6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d31b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d325`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d31b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d325`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d18d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d1c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d201`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d230`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d25f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d18d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d1c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d201`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d230`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d25f`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000d1b0`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000d1b0`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::EnumData(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4,
        unsigned int a5,
        unsigned int *a6)
{
  struct ABO_TREE *v10; // r15
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  struct ABO_NODE *v13; // rbx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v15; // rax
  __int64 v16; // r14
  DWORD dwMDDataType; // ebx
  DWORD dwMDUserType; // edi
  DWORD dwMDAttributes; // esi
  const unsigned __int16 *v20; // rax
  int AllInheritedData; // eax
  const unsigned __int16 *v22; // rax
  ABO_NODE *v23; // rbx
  const unsigned __int16 *v24; // rax
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE_ENTRY *v27; // [rsp+48h] [rbp-B8h] BYREF
  struct ABO_NODE *v28; // [rsp+50h] [rbp-B0h] BYREF
  struct ABO_TREE *v29; // [rsp+58h] [rbp-A8h] BYREF
  void **v30; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v31[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v32; // [rsp+78h] [rbp-88h]
  CReaderWriterLock3 *v33; // [rsp+80h] [rbp-80h]
  _BYTE v34[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v36[248]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v37[248]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v32 = a6;
  v28 = 0;
  memset_0(v36, 0, 0x1EAu);
  STRU::STRU((STRU *)v34, v36, 0xF5u);
  memset_0(v37, 0, 0x1EAu);
  STRU::STRU((STRU *)v35, v37, 0xF5u);
  v26 = 3;
  v27 = 0;
  v30 = &PROPERTY_BAG::`vftable';
  v10 = 0;
  v31[0] = 0;
  v31[1] = 0;
  v29 = 0;
  if ( a4 )
  {
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v27);
    if ( HandleEntry >= 0 )
    {
      HandleEntry = HANDLE_ENTRY::GetFullPath(v27, a3, (struct STRU *)v34);
      if ( HandleEntry >= 0 )
      {
        v33 = (ABO_WRAPPER *)((char *)this + 32);
        CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
        CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v29);
        v10 = v29;
        HandleEntry = CurrentAboTree;
        if ( CurrentAboTree >= 0 )
        {
          if ( (a4->dwMDAttributes & 1) != 0 )
          {
            v13 = (struct ABO_NODE *)*((_QWORD *)v29 + 2);
            Str = STRU::QueryStr((STRU *)v34);
            HandleEntry = GetLastNodePath(Str, v13, (struct STRU *)v35);
            if ( HandleEntry >= 0 && !STRU::IsEmpty((STRU *)v35) )
            {
              v15 = STRU::QueryStr((STRU *)v35);
              HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v10, v15, 0, (enum ACCESS_GRANTED *)&v26);
              if ( HandleEntry >= 0 )
              {
                v16 = *((_QWORD *)v10 + 2);
                dwMDDataType = a4->dwMDDataType;
                dwMDUserType = a4->dwMDUserType;
                dwMDAttributes = a4->dwMDAttributes;
                v20 = STRU::QueryStr((STRU *)v34);
                AllInheritedData = ABO_NODE::GetAllInheritedData(
                                     v16,
                                     v26,
                                     v20,
                                     dwMDAttributes,
                                     dwMDUserType,
                                     dwMDDataType,
                                     (PROPERTY_BAG *)&v30);
                HandleEntry = AllInheritedData;
                if ( AllInheritedData >= 0 )
                  HandleEntry = PROPERTY_BAG::EnumData((PROPERTY_BAG *)&v30, a5, a4, v32);
              }
            }
          }
          else
          {
            v22 = STRU::QueryStr((STRU *)v34);
            HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v10, v22, 0, (enum ACCESS_GRANTED *)&v26);
            if ( HandleEntry >= 0 )
            {
              v23 = (ABO_NODE *)*((_QWORD *)v10 + 2);
              v24 = STRU::QueryStr((STRU *)v34);
              ABO_NODE::FindNode(v23, v24, &v28);
            }
          }
        }
        CReaderWriterLock3::WriteUnlock(v33);
      }
    }
    if ( v27 )
      HANDLE_ENTRY::DereferenceHandleEntry(v27);
    if ( v10 )
      HANDLE_ENTRY::DereferenceHandleEntry(v10);
    if ( HandleEntry == -2147024894 )
      HandleEntry = -2146646015;
  }
  else
  {
    HandleEntry = -2147024809;
  }
  v30 = &PROPERTY_BAG::`vftable';
  ARRAY_LIST::~ARRAY_LIST((ARRAY_LIST *)v31);
  STRU::~STRU((STRU *)v35);
  STRU::~STRU((STRU *)v34);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000d040  push    rbp
0x18000d042  push    rbx
0x18000d043  push    rsi
0x18000d044  push    rdi
0x18000d045  push    r12
0x18000d047  push    r13
0x18000d049  push    r14
0x18000d04b  push    r15
0x18000d04d  lea     rbp, [rsp-3F8h]
0x18000d055  sub     rsp, 4F8h
0x18000d05c  mov     rax, cs:__security_cookie
0x18000d063  xor     rax, rsp
0x18000d066  mov     [rbp+430h+var_50], rax
0x18000d06d  mov     rax, [rbp+430h+arg_28]
0x18000d074  mov     rsi, r8
0x18000d077  mov     ebx, edx
0x18000d079  mov     [rsp+530h+var_4B8], rax
0x18000d07e  mov     rdi, rcx
0x18000d081  mov     r15d, 1EAh
0x18000d087  xor     r12d, r12d
0x18000d08a  lea     rcx, [rbp+430h+var_430]; void *
0x18000d08e  mov     r8d, r15d; Size
0x18000d091  mov     [rsp+530h+var_4E0], r12
0x18000d096  xor     edx, edx; Val
0x18000d098  mov     r13, r9
0x18000d09b  call    memset_0
0x18000d0a0  mov     r14d, 0F5h
0x18000d0a6  lea     rdx, [rbp+430h+var_430]
0x18000d0aa  mov     r8d, r14d
0x18000d0ad  lea     rcx, [rbp+430h+var_4A8]
0x18000d0b1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d0b7  mov     r8d, r15d; Size
0x18000d0ba  lea     rcx, [rbp+430h+var_240]; void *
0x18000d0c1  xor     edx, edx; Val
0x18000d0c3  call    memset_0
0x18000d0c8  mov     r8d, r14d
0x18000d0cb  lea     rdx, [rbp+430h+var_240]
0x18000d0d2  lea     rcx, [rbp+430h+var_470]
0x18000d0d6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d0dc  xor     r14d, r14d
0x18000d0df  mov     [rsp+530h+var_4F0], 3
0x18000d0e7  mov     [rsp+530h+var_4E8], r14
0x18000d0ec  lea     rax, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x18000d0f3  mov     [rsp+530h+var_4D0], rax
0x18000d0f8  mov     r15d, r14d
0x18000d0fb  mov     [rsp+530h+var_4C8], r14
0x18000d100  mov     [rsp+530h+var_4C0], r14
0x18000d105  mov     [rsp+530h+var_4D8], r14
0x18000d10a  test    r13, r13
0x18000d10d  jnz     short loc_18000D119
0x18000d10f  mov     ebx, 80070057h
0x18000d114  jmp     loc_18000D308
0x18000d119  lea     r8, [rsp+530h+var_4E8]; struct HANDLE_ENTRY **
0x18000d11e  mov     edx, ebx; unsigned int
0x18000d120  mov     rcx, rdi; this
0x18000d123  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000d128  mov     ebx, eax
0x18000d12a  test    eax, eax
0x18000d12c  js      loc_18000D2C8
0x18000d132  mov     rcx, [rsp+530h+var_4E8]; this
0x18000d137  lea     r8, [rbp+430h+var_4A8]; struct STRU *
0x18000d13b  mov     rdx, rsi; unsigned __int16 *
0x18000d13e  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000d143  mov     ebx, eax
0x18000d145  test    eax, eax
0x18000d147  js      loc_18000D2C8
0x18000d14d  lea     rax, [rdi+20h]
0x18000d151  mov     rcx, rax
0x18000d154  mov     [rbp+430h+var_4B0], rax
0x18000d158  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d15e  lea     rdx, [rsp+530h+var_4D8]; struct ABO_TREE **
0x18000d163  mov     rcx, rdi; this
0x18000d166  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000d16b  mov     r15, [rsp+530h+var_4D8]
0x18000d170  mov     ebx, eax
0x18000d172  test    eax, eax
0x18000d174  js      loc_18000D2BE
0x18000d17a  test    byte ptr [r13+4], 1
0x18000d17f  lea     rcx, [rbp+430h+var_4A8]
0x18000d183  jz      loc_18000D230
0x18000d189  mov     rbx, [r15+10h]
0x18000d18d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d193  lea     r8, [rbp+430h+var_470]; struct STRU *
0x18000d197  mov     rdx, rbx; struct ABO_NODE *
0x18000d19a  mov     rcx, rax; unsigned __int16 *
0x18000d19d  call    ?GetLastNodePath@@YAJPEBGPEAVABO_NODE@@PEAVSTRU@@@Z; GetLastNodePath(ushort const *,ABO_NODE *,STRU *)
0x18000d1a2  mov     ebx, eax
0x18000d1a4  test    eax, eax
0x18000d1a6  js      loc_18000D2BE
0x18000d1ac  lea     rcx, [rbp+430h+var_470]
0x18000d1b0  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18000d1b6  test    al, al
0x18000d1b8  jnz     loc_18000D2BE
0x18000d1be  lea     rcx, [rbp+430h+var_470]
0x18000d1c2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d1c8  lea     rcx, [rsp+530h+var_4F0]
0x18000d1cd  xor     r9d, r9d
0x18000d1d0  mov     [rsp+530h+var_510], rcx
0x18000d1d5  mov     r8, rax
0x18000d1d8  mov     rcx, rdi
0x18000d1db  mov     rdx, r15
0x18000d1de  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000d1e3  mov     ebx, eax
0x18000d1e5  test    eax, eax
0x18000d1e7  js      loc_18000D2BE
0x18000d1ed  mov     r14, [r15+10h]
0x18000d1f1  lea     rcx, [rbp+430h+var_4A8]
0x18000d1f5  mov     ebx, [r13+0Ch]
0x18000d1f9  mov     edi, [r13+8]
0x18000d1fd  mov     esi, [r13+4]
0x18000d201  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d207  mov     edx, [rsp+530h+var_4F0]
0x18000d20b  lea     rcx, [rsp+530h+var_4D0]
0x18000d210  mov     [rsp+530h+var_500], rcx
0x18000d215  mov     r9d, esi
0x18000d218  mov     [rsp+530h+var_508], ebx
0x18000d21c  mov     rcx, r14
0x18000d21f  mov     r8, rax
0x18000d222  mov     dword ptr [rsp+530h+var_510], edi
0x18000d226  call    ?GetAllInheritedData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@PEBGKKKPEAVPROPERTY_BAG@@@Z; ABO_NODE::GetAllInheritedData(ACCESS_GRANTED,ushort const *,ulong,ulong,ulong,PROPERTY_BAG *)
0x18000d22b  xor     r14d, r14d
0x18000d22e  jmp     short loc_18000D29E
0x18000d230  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d236  lea     rcx, [rsp+530h+var_4F0]
0x18000d23b  xor     r9d, r9d
0x18000d23e  mov     [rsp+530h+var_510], rcx
0x18000d243  mov     r8, rax
0x18000d246  mov     rcx, rdi
0x18000d249  mov     rdx, r15
0x18000d24c  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000d251  mov     ebx, eax
0x18000d253  test    eax, eax
0x18000d255  js      short loc_18000D2BE
0x18000d257  mov     rbx, [r15+10h]
0x18000d25b  lea     rcx, [rbp+430h+var_4A8]
0x18000d25f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d265  lea     r8, [rsp+530h+var_4E0]; struct ABO_NODE **
0x18000d26a  mov     rcx, rbx; this
0x18000d26d  mov     rdx, rax; unsigned __int16 *
0x18000d270  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000d275  mov     r12, [rsp+530h+var_4E0]
0x18000d27a  mov     ebx, eax
0x18000d27c  test    eax, eax
0x18000d27e  js      short loc_18000D2BE
0x18000d280  mov     r9d, [r13+0Ch]
0x18000d284  lea     rax, [rsp+530h+var_4D0]
0x18000d289  mov     r8d, [r13+8]
0x18000d28d  mov     rcx, r12
0x18000d290  mov     edx, [rsp+530h+var_4F0]
0x18000d294  mov     [rsp+530h+var_510], rax
0x18000d299  call    ?GetAllData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@KKPEAVPROPERTY_BAG@@@Z; ABO_NODE::GetAllData(ACCESS_GRANTED,ulong,ulong,PROPERTY_BAG *)
0x18000d29e  mov     ebx, eax
0x18000d2a0  test    eax, eax
0x18000d2a2  js      short loc_18000D2BE
0x18000d2a4  mov     r9, [rsp+530h+var_4B8]; unsigned int *
0x18000d2a9  lea     rcx, [rsp+530h+var_4D0]; this
0x18000d2ae  mov     edx, [rbp+430h+arg_20]; unsigned int
0x18000d2b4  mov     r8, r13; struct _METADATA_RECORD *
0x18000d2b7  call    ?EnumData@PROPERTY_BAG@@QEAAJKPEAU_METADATA_RECORD@@PEAK@Z; PROPERTY_BAG::EnumData(ulong,_METADATA_RECORD *,ulong *)
0x18000d2bc  mov     ebx, eax
0x18000d2be  mov     rcx, [rbp+430h+var_4B0]
0x18000d2c2  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d2c8  cmp     [rsp+530h+var_4E8], r14
0x18000d2cd  jz      short loc_18000D2D9
0x18000d2cf  mov     rcx, [rsp+530h+var_4E8]; this
0x18000d2d4  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d2d9  test    r12, r12
0x18000d2dc  jz      short loc_18000D2E6
0x18000d2de  mov     rcx, r12; this
0x18000d2e1  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000d2e6  test    r15, r15
0x18000d2e9  jz      short loc_18000D2F3
0x18000d2eb  mov     rcx, r15; this
0x18000d2ee  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d2f3  mov     eax, 800CC801h
0x18000d2f8  cmp     ebx, 80070002h
0x18000d2fe  cmovz   ebx, eax
0x18000d301  lea     rax, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x18000d308  lea     rcx, [rsp+530h+var_4C8]; this
0x18000d30d  mov     [rsp+530h+var_4D0], rax
0x18000d312  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x18000d317  lea     rcx, [rbp+430h+var_470]
0x18000d31b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d321  lea     rcx, [rbp+430h+var_4A8]
0x18000d325  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d32b  mov     eax, ebx
0x18000d32d  mov     rcx, [rbp+430h+var_50]
0x18000d334  xor     rcx, rsp; StackCookie
0x18000d337  call    __security_check_cookie
0x18000d33c  add     rsp, 4F8h
0x18000d343  pop     r15
0x18000d345  pop     r14
0x18000d347  pop     r13
0x18000d349  pop     r12
0x18000d34b  pop     rdi
0x18000d34c  pop     rsi
0x18000d34d  pop     rbx
0x18000d34e  pop     rbp
0x18000d34f  retn
```

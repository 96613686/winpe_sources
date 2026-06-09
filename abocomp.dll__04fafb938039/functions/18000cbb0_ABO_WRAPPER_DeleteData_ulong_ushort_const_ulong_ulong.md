# ABO_WRAPPER::DeleteData(ulong,ushort const *,ulong,ulong)

- ea: `0x18000cbb0`
- end: `0x18000cd5f`
- name: `?DeleteData@ABO_WRAPPER@@UEAAJKPEBGKK@Z`
- size: `431`
- prototype: `__int64 __fastcall(ABO_WRAPPER *this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000cbb0`
- `0x18000cd68`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ccee`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ccee`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cc58`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cc58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000cc0d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000cc0d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cd36`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cd36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cc7b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cca7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cc7b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cca7`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::DeleteData(ABO_WRAPPER *this, unsigned int a2, const unsigned __int16 *a3)
{
  struct ABO_TREE *v6; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v10; // rbx
  const unsigned __int16 *v11; // rax
  HANDLE_ENTRY *v13; // [rsp+30h] [rbp-D0h] BYREF
  struct ABO_NODE *v14; // [rsp+38h] [rbp-C8h] BYREF
  struct ABO_TREE *v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[56]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v17[248]; // [rsp+80h] [rbp-80h] BYREF

  v14 = 0;
  memset_0(v17, 0, 0x1EAu);
  STRU::STRU((STRU *)v16, v17, 0xF5u);
  v6 = 0;
  v13 = 0;
  v15 = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v13);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v13, a3, (struct STRU *)v16);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v15);
      v6 = v15;
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v16);
        HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v6, Str, 1, 0);
        if ( HandleEntry >= 0 )
        {
          v10 = (ABO_NODE *)*((_QWORD *)v6 + 2);
          v11 = STRU::QueryStr((STRU *)v16);
          ABO_NODE::FindNode(v10, v11, &v14);
        }
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    }
  }
  if ( v13 )
    HANDLE_ENTRY::DereferenceHandleEntry(v13);
  if ( v6 )
    HANDLE_ENTRY::DereferenceHandleEntry(v6);
  if ( (unsigned int)(HandleEntry + 2147024894) <= 1 )
    HandleEntry = -2146646015;
  STRU::~STRU((STRU *)v16);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000cbb0  push    rbp
0x18000cbb2  push    rbx
0x18000cbb3  push    rsi
0x18000cbb4  push    rdi
0x18000cbb5  push    r12
0x18000cbb7  push    r13
0x18000cbb9  push    r15
0x18000cbbb  lea     rbp, [rsp-180h]
0x18000cbc3  sub     rsp, 280h
0x18000cbca  mov     rax, cs:__security_cookie
0x18000cbd1  xor     rax, rsp
0x18000cbd4  mov     [rbp+1B0h+var_40], rax
0x18000cbdb  mov     r12, r8
0x18000cbde  mov     ebx, edx
0x18000cbe0  mov     r15, rcx
0x18000cbe3  xor     edi, edi
0x18000cbe5  xor     edx, edx; Val
0x18000cbe7  mov     [rsp+2B0h+var_278], rdi
0x18000cbec  mov     r8d, 1EAh; Size
0x18000cbf2  lea     rcx, [rbp+1B0h+var_230]; void *
0x18000cbf6  mov     r13d, r9d
0x18000cbf9  call    memset_0
0x18000cbfe  mov     r8d, 0F5h
0x18000cc04  lea     rdx, [rbp+1B0h+var_230]
0x18000cc08  lea     rcx, [rsp+2B0h+var_268]
0x18000cc0d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000cc13  xor     esi, esi
0x18000cc15  mov     [rsp+2B0h+var_280], rdi
0x18000cc1a  lea     r8, [rsp+2B0h+var_280]; struct HANDLE_ENTRY **
0x18000cc1f  mov     [rsp+2B0h+var_270], rsi
0x18000cc24  mov     edx, ebx; unsigned int
0x18000cc26  mov     rcx, r15; this
0x18000cc29  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000cc2e  mov     ebx, eax
0x18000cc30  test    eax, eax
0x18000cc32  js      loc_18000CCF4
0x18000cc38  mov     rcx, [rsp+2B0h+var_280]; this
0x18000cc3d  lea     r8, [rsp+2B0h+var_268]; struct STRU *
0x18000cc42  mov     rdx, r12; unsigned __int16 *
0x18000cc45  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000cc4a  mov     ebx, eax
0x18000cc4c  test    eax, eax
0x18000cc4e  js      loc_18000CCF4
0x18000cc54  lea     rcx, [r15+20h]
0x18000cc58  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000cc5e  lea     rdx, [rsp+2B0h+var_270]; struct ABO_TREE **
0x18000cc63  mov     rcx, r15; this
0x18000cc66  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000cc6b  mov     rsi, [rsp+2B0h+var_270]
0x18000cc70  mov     ebx, eax
0x18000cc72  test    eax, eax
0x18000cc74  js      short loc_18000CCEA
0x18000cc76  lea     rcx, [rsp+2B0h+var_268]
0x18000cc7b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cc81  lea     r9d, [rdi+1]
0x18000cc85  mov     [rsp+2B0h+var_290], rdi
0x18000cc8a  mov     r8, rax
0x18000cc8d  mov     rdx, rsi
0x18000cc90  mov     rcx, r15
0x18000cc93  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000cc98  mov     ebx, eax
0x18000cc9a  test    eax, eax
0x18000cc9c  js      short loc_18000CCEA
0x18000cc9e  mov     rbx, [rsi+10h]
0x18000cca2  lea     rcx, [rsp+2B0h+var_268]
0x18000cca7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ccad  lea     r8, [rsp+2B0h+var_278]; struct ABO_NODE **
0x18000ccb2  mov     rcx, rbx; this
0x18000ccb5  mov     rdx, rax; unsigned __int16 *
0x18000ccb8  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000ccbd  mov     rdi, [rsp+2B0h+var_278]
0x18000ccc2  mov     ebx, eax
0x18000ccc4  test    eax, eax
0x18000ccc6  js      short loc_18000CCEA
0x18000ccc8  mov     r9d, [rbp+1B0h+arg_20]; unsigned int
0x18000cccf  mov     r8d, r13d; unsigned int
0x18000ccd2  mov     rdx, rdi; struct ABO_NODE *
0x18000ccd5  call    ?DeleteDataInternal@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@KK@Z; ABO_WRAPPER::DeleteDataInternal(ABO_NODE *,ulong,ulong)
0x18000ccda  mov     ebx, eax
0x18000ccdc  test    eax, eax
0x18000ccde  js      short loc_18000CCEA
0x18000cce0  mov     rcx, [rsp+2B0h+var_280]; this
0x18000cce5  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000ccea  lea     rcx, [r15+20h]
0x18000ccee  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ccf4  cmp     [rsp+2B0h+var_280], 0
0x18000ccfa  jz      short loc_18000CD06
0x18000ccfc  mov     rcx, [rsp+2B0h+var_280]; this
0x18000cd01  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cd06  test    rdi, rdi
0x18000cd09  jz      short loc_18000CD13
0x18000cd0b  mov     rcx, rdi; this
0x18000cd0e  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000cd13  test    rsi, rsi
0x18000cd16  jz      short loc_18000CD20
0x18000cd18  mov     rcx, rsi; this
0x18000cd1b  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cd20  lea     ecx, [rbx+7FF8FFFEh]
0x18000cd26  mov     eax, 800CC801h
0x18000cd2b  cmp     ecx, 1
0x18000cd2e  lea     rcx, [rsp+2B0h+var_268]
0x18000cd33  cmovbe  ebx, eax
0x18000cd36  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cd3c  mov     eax, ebx
0x18000cd3e  mov     rcx, [rbp+1B0h+var_40]
0x18000cd45  xor     rcx, rsp; StackCookie
0x18000cd48  call    __security_check_cookie
0x18000cd4d  add     rsp, 280h
0x18000cd54  pop     r15
0x18000cd56  pop     r13
0x18000cd58  pop     r12
0x18000cd5a  pop     rdi
0x18000cd5b  pop     rsi
0x18000cd5c  pop     rbx
0x18000cd5d  pop     rbp
0x18000cd5e  retn
```

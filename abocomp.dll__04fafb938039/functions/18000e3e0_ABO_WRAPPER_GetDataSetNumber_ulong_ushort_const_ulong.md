# ABO_WRAPPER::GetDataSetNumber(ulong,ushort const *,ulong *)

- ea: `0x18000e3e0`
- end: `0x18000e5cb`
- name: `?GetDataSetNumber@ABO_WRAPPER@@UEAAJKPEBGPEAK@Z`
- size: `491`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000d5d8`
- `0x18000dde0`
- `0x18000e3e0`
- `0x18000e5d4`
- `0x18000f6dc`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e520`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000e520`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e56b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e56b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e490`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e490`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e43d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e43d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e5a2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e512`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e531`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e4e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e512`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e531`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetDataSetNumber(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  HANDLE_ENTRY *v7; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  ABO_NODE *v10; // rbx
  const unsigned __int16 *Str; // rax
  struct ABO_NODE *v13; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE_ENTRY *v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h]
  struct ABO_TREE *v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[64]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18[248]; // [rsp+90h] [rbp-70h] BYREF

  v13 = 0;
  memset_0(v18, 0, 0x1EAu);
  STRU::STRU((STRU *)v17, v18, 0xF5u);
  v7 = 0;
  v14 = 0;
  v16 = 0;
  v15 = 3;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v14);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v14, a3, (struct STRU *)v17);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v16);
      v7 = v16;
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        v10 = (ABO_NODE *)*((_QWORD *)v16 + 2);
        Str = STRU::QueryStr((STRU *)v17);
        ABO_NODE::FindNode(v10, Str, &v13);
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    }
  }
  if ( v14 )
    HANDLE_ENTRY::DereferenceHandleEntry(v14);
  if ( v7 )
    HANDLE_ENTRY::DereferenceHandleEntry(v7);
  STRU::~STRU((STRU *)v17);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000e3e0  push    rbp
0x18000e3e2  push    rbx
0x18000e3e3  push    rsi
0x18000e3e4  push    rdi
0x18000e3e5  push    r12
0x18000e3e7  push    r13
0x18000e3e9  push    r15
0x18000e3eb  lea     rbp, [rsp-190h]
0x18000e3f3  sub     rsp, 290h
0x18000e3fa  mov     rax, cs:__security_cookie
0x18000e401  xor     rax, rsp
0x18000e404  mov     [rbp+1C0h+var_40], rax
0x18000e40b  mov     r12, r8
0x18000e40e  mov     ebx, edx
0x18000e410  mov     r15, rcx
0x18000e413  xor     edi, edi
0x18000e415  xor     edx, edx; Val
0x18000e417  mov     [rsp+2C0h+var_290], rdi
0x18000e41c  mov     r8d, 1EAh; Size
0x18000e422  lea     rcx, [rbp+1C0h+var_230]; void *
0x18000e426  mov     r13, r9
0x18000e429  call    memset_0
0x18000e42e  mov     r8d, 0F5h
0x18000e434  lea     rdx, [rbp+1C0h+var_230]
0x18000e438  lea     rcx, [rsp+2C0h+var_270]
0x18000e43d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e443  xor     esi, esi
0x18000e445  mov     [rsp+2C0h+var_288], rdi
0x18000e44a  lea     r8, [rsp+2C0h+var_288]; struct HANDLE_ENTRY **
0x18000e44f  mov     [rsp+2C0h+var_278], rsi
0x18000e454  mov     edx, ebx; unsigned int
0x18000e456  mov     [rsp+2C0h+var_280], 3
0x18000e45e  mov     rcx, r15; this
0x18000e461  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000e466  mov     ebx, eax
0x18000e468  test    eax, eax
0x18000e46a  js      loc_18000E571
0x18000e470  mov     rcx, [rsp+2C0h+var_288]; this
0x18000e475  lea     r8, [rsp+2C0h+var_270]; struct STRU *
0x18000e47a  mov     rdx, r12; unsigned __int16 *
0x18000e47d  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000e482  mov     ebx, eax
0x18000e484  test    eax, eax
0x18000e486  js      loc_18000E571
0x18000e48c  lea     rcx, [r15+20h]
0x18000e490  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000e496  lea     rdx, [rsp+2C0h+var_278]; struct ABO_TREE **
0x18000e49b  mov     rcx, r15; this
0x18000e49e  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000e4a3  mov     rsi, [rsp+2C0h+var_278]
0x18000e4a8  mov     ebx, eax
0x18000e4aa  test    eax, eax
0x18000e4ac  js      loc_18000E567
0x18000e4b2  mov     rbx, [rsi+10h]
0x18000e4b6  lea     rcx, [rsp+2C0h+var_270]
0x18000e4bb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e4c1  lea     r8, [rsp+2C0h+var_290]; struct ABO_NODE **
0x18000e4c6  mov     rcx, rbx; this
0x18000e4c9  mov     rdx, rax; unsigned __int16 *
0x18000e4cc  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000e4d1  mov     ebx, eax
0x18000e4d3  test    eax, eax
0x18000e4d5  jns     short loc_18000E506
0x18000e4d7  cmp     eax, 80070003h
0x18000e4dc  jnz     short loc_18000E4FF
0x18000e4de  lea     rcx, [rsp+2C0h+var_270]
0x18000e4e3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e4e9  lea     r9, [rsp+2C0h+var_290]; struct ABO_NODE **
0x18000e4ee  mov     rdx, rsi; struct ABO_TREE *
0x18000e4f1  mov     r8, rax; unsigned __int16 *
0x18000e4f4  call    ?FindInheritedAboNode@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGPEAPEAVABO_NODE@@@Z; ABO_WRAPPER::FindInheritedAboNode(ABO_TREE *,ushort const *,ABO_NODE * *)
0x18000e4f9  mov     ebx, eax
0x18000e4fb  test    eax, eax
0x18000e4fd  jns     short loc_18000E506
0x18000e4ff  mov     rdi, [rsp+2C0h+var_290]
0x18000e504  jmp     short loc_18000E567
0x18000e506  mov     rdi, [rsp+2C0h+var_290]
0x18000e50b  lea     rcx, [rdi+100h]
0x18000e512  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e518  mov     rdx, rax
0x18000e51b  lea     rcx, [rsp+2C0h+var_270]
0x18000e520  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000e526  mov     ebx, eax
0x18000e528  test    eax, eax
0x18000e52a  js      short loc_18000E567
0x18000e52c  lea     rcx, [rsp+2C0h+var_270]
0x18000e531  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e537  lea     rcx, [rsp+2C0h+var_280]
0x18000e53c  xor     r9d, r9d
0x18000e53f  mov     [rsp+2C0h+var_2A0], rcx
0x18000e544  mov     r8, rax
0x18000e547  mov     rcx, r15
0x18000e54a  mov     rdx, rsi
0x18000e54d  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000e552  mov     ebx, eax
0x18000e554  test    eax, eax
0x18000e556  js      short loc_18000E567
0x18000e558  test    r13, r13
0x18000e55b  jz      short loc_18000E567
0x18000e55d  mov     eax, [rdi+0F0h]
0x18000e563  mov     [r13+0], eax
0x18000e567  lea     rcx, [r15+20h]
0x18000e56b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000e571  cmp     [rsp+2C0h+var_288], 0
0x18000e577  jz      short loc_18000E583
0x18000e579  mov     rcx, [rsp+2C0h+var_288]; this
0x18000e57e  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e583  test    rdi, rdi
0x18000e586  jz      short loc_18000E590
0x18000e588  mov     rcx, rdi; this
0x18000e58b  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000e590  test    rsi, rsi
0x18000e593  jz      short loc_18000E59D
0x18000e595  mov     rcx, rsi; this
0x18000e598  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e59d  lea     rcx, [rsp+2C0h+var_270]
0x18000e5a2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e5a8  mov     eax, ebx
0x18000e5aa  mov     rcx, [rbp+1C0h+var_40]
0x18000e5b1  xor     rcx, rsp; StackCookie
0x18000e5b4  call    __security_check_cookie
0x18000e5b9  add     rsp, 290h
0x18000e5c0  pop     r15
0x18000e5c2  pop     r13
0x18000e5c4  pop     r12
0x18000e5c6  pop     rdi
0x18000e5c7  pop     rsi
0x18000e5c8  pop     rbx
0x18000e5c9  pop     rbp
0x18000e5ca  retn
```

# ABO_WRAPPER::GetLastChangeTime(ulong,ushort const *,_FILETIME *)

- ea: `0x18000e6e0`
- end: `0x18000e8af`
- name: `?GetLastChangeTime@ABO_WRAPPER@@UEAAJKPEBGPEAU_FILETIME@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b54c`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000e6e0`
- `0x18000f6dc`
- `0x18002c010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e84f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e84f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e798`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e798`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e73d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e73d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e886`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e886`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e7bf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e7ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e7bf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e7ef`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetLastChangeTime(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4)
{
  struct ABO_TREE *v7; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v11; // rbx
  const unsigned __int16 *v12; // rax
  HANDLE_ENTRY *v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_NODE *v16; // [rsp+48h] [rbp-B8h] BYREF
  struct ABO_TREE *v17; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[248]; // [rsp+90h] [rbp-70h] BYREF

  v16 = 0;
  memset_0(v19, 0, 0x1EAu);
  STRU::STRU((STRU *)v18, v19, 0xF5u);
  v7 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 3;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v14);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v14, a3, (struct STRU *)v18);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v17);
      v7 = v17;
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v18);
        HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v7, Str, 0, (enum ACCESS_GRANTED *)&v15);
        if ( HandleEntry >= 0 )
        {
          v11 = (ABO_NODE *)*((_QWORD *)v7 + 2);
          v12 = STRU::QueryStr((STRU *)v18);
          ABO_NODE::FindNode(v11, v12, &v16);
        }
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    }
  }
  if ( v14 )
    HANDLE_ENTRY::DereferenceHandleEntry(v14);
  if ( v7 )
    HANDLE_ENTRY::DereferenceHandleEntry(v7);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000e6e0  push    rbp
0x18000e6e2  push    rbx
0x18000e6e3  push    rsi
0x18000e6e4  push    rdi
0x18000e6e5  push    r12
0x18000e6e7  push    r13
0x18000e6e9  push    r15
0x18000e6eb  lea     rbp, [rsp-190h]
0x18000e6f3  sub     rsp, 290h
0x18000e6fa  mov     rax, cs:__security_cookie
0x18000e701  xor     rax, rsp
0x18000e704  mov     [rbp+1C0h+var_40], rax
0x18000e70b  mov     r12, r8
0x18000e70e  mov     ebx, edx
0x18000e710  mov     r15, rcx
0x18000e713  xor     edi, edi
0x18000e715  xor     edx, edx; Val
0x18000e717  mov     [rsp+2C0h+var_278], rdi
0x18000e71c  mov     r8d, 1EAh; Size
0x18000e722  lea     rcx, [rbp+1C0h+var_230]; void *
0x18000e726  mov     r13, r9
0x18000e729  call    memset_0
0x18000e72e  mov     r8d, 0F5h
0x18000e734  lea     rdx, [rbp+1C0h+var_230]
0x18000e738  lea     rcx, [rsp+2C0h+var_268]
0x18000e73d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e743  xor     esi, esi
0x18000e745  mov     [rsp+2C0h+var_288], rdi
0x18000e74a  lea     r8, [rsp+2C0h+var_288]; struct HANDLE_ENTRY **
0x18000e74f  mov     [rsp+2C0h+var_270], rsi
0x18000e754  mov     edx, ebx; unsigned int
0x18000e756  mov     [rsp+2C0h+var_290], 1
0x18000e75e  mov     rcx, r15; this
0x18000e761  mov     [rsp+2C0h+var_280], 3
0x18000e769  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000e76e  mov     ebx, eax
0x18000e770  test    eax, eax
0x18000e772  js      loc_18000E855
0x18000e778  mov     rcx, [rsp+2C0h+var_288]; this
0x18000e77d  lea     r8, [rsp+2C0h+var_268]; struct STRU *
0x18000e782  mov     rdx, r12; unsigned __int16 *
0x18000e785  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000e78a  mov     ebx, eax
0x18000e78c  test    eax, eax
0x18000e78e  js      loc_18000E855
0x18000e794  lea     rcx, [r15+20h]
0x18000e798  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000e79e  lea     rdx, [rsp+2C0h+var_270]; struct ABO_TREE **
0x18000e7a3  mov     rcx, r15; this
0x18000e7a6  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000e7ab  mov     rsi, [rsp+2C0h+var_270]
0x18000e7b0  mov     ebx, eax
0x18000e7b2  test    eax, eax
0x18000e7b4  js      loc_18000E84B
0x18000e7ba  lea     rcx, [rsp+2C0h+var_268]
0x18000e7bf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e7c5  lea     rcx, [rsp+2C0h+var_280]
0x18000e7ca  xor     r9d, r9d
0x18000e7cd  mov     [rsp+2C0h+var_2A0], rcx
0x18000e7d2  mov     r8, rax
0x18000e7d5  mov     rcx, r15
0x18000e7d8  mov     rdx, rsi
0x18000e7db  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000e7e0  mov     ebx, eax
0x18000e7e2  test    eax, eax
0x18000e7e4  js      short loc_18000E84B
0x18000e7e6  mov     rbx, [rsi+10h]
0x18000e7ea  lea     rcx, [rsp+2C0h+var_268]
0x18000e7ef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e7f5  lea     r8, [rsp+2C0h+var_278]; struct ABO_NODE **
0x18000e7fa  mov     rcx, rbx; this
0x18000e7fd  mov     rdx, rax; unsigned __int16 *
0x18000e800  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000e805  mov     rdi, [rsp+2C0h+var_278]
0x18000e80a  mov     ebx, eax
0x18000e80c  test    eax, eax
0x18000e80e  js      short loc_18000E84B
0x18000e810  lea     r8, [rsp+2C0h+var_290]; int *
0x18000e815  mov     rdx, rdi; struct ABO_NODE *
0x18000e818  call    ?CheckADSICompat@ABO_WRAPPER@@AEAAJPEAVABO_NODE@@PEAH@Z; ABO_WRAPPER::CheckADSICompat(ABO_NODE *,int *)
0x18000e81d  mov     ebx, eax
0x18000e81f  test    eax, eax
0x18000e821  js      short loc_18000E84B
0x18000e823  cmp     [rsp+2C0h+var_290], 0
0x18000e828  jnz     short loc_18000E831
0x18000e82a  mov     ebx, 80070003h
0x18000e82f  jmp     short loc_18000E84B
0x18000e831  mov     rax, [rdi+0B0h]
0x18000e838  mov     rdx, r13
0x18000e83b  mov     rcx, [rax+20h]
0x18000e83f  mov     rax, [rcx]
0x18000e842  mov     rax, [rax+48h]
0x18000e846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e84b  lea     rcx, [r15+20h]
0x18000e84f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000e855  cmp     [rsp+2C0h+var_288], 0
0x18000e85b  jz      short loc_18000E867
0x18000e85d  mov     rcx, [rsp+2C0h+var_288]; this
0x18000e862  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e867  test    rdi, rdi
0x18000e86a  jz      short loc_18000E874
0x18000e86c  mov     rcx, rdi; this
0x18000e86f  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000e874  test    rsi, rsi
0x18000e877  jz      short loc_18000E881
0x18000e879  mov     rcx, rsi; this
0x18000e87c  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e881  lea     rcx, [rsp+2C0h+var_268]
0x18000e886  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e88c  mov     eax, ebx
0x18000e88e  mov     rcx, [rbp+1C0h+var_40]
0x18000e895  xor     rcx, rsp; StackCookie
0x18000e898  call    __security_check_cookie
0x18000e89d  add     rsp, 290h
0x18000e8a4  pop     r15
0x18000e8a6  pop     r13
0x18000e8a8  pop     r12
0x18000e8aa  pop     rdi
0x18000e8ab  pop     rsi
0x18000e8ac  pop     rbx
0x18000e8ad  pop     rbp
0x18000e8ae  retn
```

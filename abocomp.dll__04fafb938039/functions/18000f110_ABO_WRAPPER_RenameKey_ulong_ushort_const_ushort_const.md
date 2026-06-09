# ABO_WRAPPER::RenameKey(ulong,ushort const *,ushort const *)

- ea: `0x18000f110`
- end: `0x18000f327`
- name: `?RenameKey@ABO_WRAPPER@@UEAAJKPEBG0@Z`
- size: `535`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180006f54`
- `0x180007148`
- `0x180007530`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f110`
- `0x18000f6dc`
- `0x18000f820`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f2bd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f2bd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f1dd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f1dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f176`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f176`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f2fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f2fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f204`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f236`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f204`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f236`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::RenameKey(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct ABO_TREE *a4)
{
  struct ABO_TREE *v8; // r14
  int FullPath; // ebx
  int HandleEntry; // eax
  HANDLE_ENTRY *v11; // r15
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v14; // rbx
  const unsigned __int16 *v15; // rax
  struct ABO_NODE *v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE_ENTRY *v18; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_TREE *v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[256]; // [rsp+90h] [rbp-70h] BYREF

  v19[1] = a4;
  v18 = 0;
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v20, v21, 0x100u);
  v8 = 0;
  v19[0] = 0;
  v17 = 0;
  if ( a4 )
  {
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v18);
    v11 = v18;
    FullPath = HandleEntry;
    if ( HandleEntry >= 0 )
    {
      FullPath = HANDLE_ENTRY::GetFullPath(v18, a3, (struct STRU *)v20);
      if ( FullPath >= 0 )
      {
        CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
        CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, v19);
        v8 = v19[0];
        FullPath = CurrentAboTree;
        if ( CurrentAboTree >= 0 )
        {
          Str = STRU::QueryStr((STRU *)v20);
          FullPath = ABO_WRAPPER::CheckAccessAndPermissions(this, v8, Str, 1, 0);
          if ( FullPath >= 0 )
          {
            v14 = (ABO_NODE *)*((_QWORD *)v8 + 2);
            v15 = STRU::QueryStr((STRU *)v20);
            ABO_NODE::FindNode(v14, v15, &v17);
          }
        }
        CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
      }
    }
    if ( v11 )
      HANDLE_ENTRY::DereferenceHandleEntry(v11);
    if ( v8 )
      HANDLE_ENTRY::DereferenceHandleEntry(v8);
  }
  else
  {
    FullPath = -2147024809;
  }
  STRU::~STRU((STRU *)v20);
  return (unsigned int)FullPath;
}

```

## disassembly

```asm
0x18000f110  push    rbp
0x18000f112  push    rbx
0x18000f113  push    rsi
0x18000f114  push    rdi
0x18000f115  push    r12
0x18000f117  push    r13
0x18000f119  push    r14
0x18000f11b  push    r15
0x18000f11d  lea     rbp, [rsp-1A8h]
0x18000f125  sub     rsp, 2A8h
0x18000f12c  mov     rax, cs:__security_cookie
0x18000f133  xor     rax, rsp
0x18000f136  mov     [rbp+1E0h+var_50], rax
0x18000f13d  mov     r12, r8
0x18000f140  mov     [rsp+2E0h+var_290], r9
0x18000f145  mov     ebx, edx
0x18000f147  mov     [rsp+2E0h+var_2A0], 0
0x18000f150  mov     r13, rcx
0x18000f153  xor     edx, edx; Val
0x18000f155  mov     r8d, 200h; Size
0x18000f15b  lea     rcx, [rbp+1E0h+var_250]; void *
0x18000f15f  mov     r15, r9
0x18000f162  call    memset_0
0x18000f167  mov     r8d, 100h
0x18000f16d  lea     rdx, [rbp+1E0h+var_250]
0x18000f171  lea     rcx, [rsp+2E0h+var_288]
0x18000f176  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000f17c  xor     r14d, r14d
0x18000f17f  xor     edi, edi
0x18000f181  xor     esi, esi
0x18000f183  mov     [rsp+2E0h+var_298], r14
0x18000f188  mov     [rsp+2E0h+var_2A8], rdi
0x18000f18d  mov     [rsp+2E0h+var_2B0], rsi
0x18000f192  test    r15, r15
0x18000f195  jnz     short loc_18000F1A1
0x18000f197  mov     ebx, 80070057h
0x18000f19c  jmp     loc_18000F2F7
0x18000f1a1  lea     r8, [rsp+2E0h+var_2A0]; struct HANDLE_ENTRY **
0x18000f1a6  mov     edx, ebx; unsigned int
0x18000f1a8  mov     rcx, r13; this
0x18000f1ab  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000f1b0  mov     r15, [rsp+2E0h+var_2A0]
0x18000f1b5  mov     ebx, eax
0x18000f1b7  test    eax, eax
0x18000f1b9  js      loc_18000F2C3
0x18000f1bf  lea     r8, [rsp+2E0h+var_288]; struct STRU *
0x18000f1c4  mov     rdx, r12; unsigned __int16 *
0x18000f1c7  mov     rcx, r15; this
0x18000f1ca  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000f1cf  mov     ebx, eax
0x18000f1d1  test    eax, eax
0x18000f1d3  js      loc_18000F2C3
0x18000f1d9  lea     rcx, [r13+20h]
0x18000f1dd  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000f1e3  lea     rdx, [rsp+2E0h+var_298]; struct ABO_TREE **
0x18000f1e8  mov     rcx, r13; this
0x18000f1eb  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000f1f0  mov     r14, [rsp+2E0h+var_298]
0x18000f1f5  mov     ebx, eax
0x18000f1f7  test    eax, eax
0x18000f1f9  js      loc_18000F2B9
0x18000f1ff  lea     rcx, [rsp+2E0h+var_288]
0x18000f204  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f20a  mov     r9d, 1
0x18000f210  mov     qword ptr [rsp+2E0h+var_2C0], rsi
0x18000f215  mov     r8, rax
0x18000f218  mov     rdx, r14
0x18000f21b  mov     rcx, r13
0x18000f21e  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000f223  mov     ebx, eax
0x18000f225  test    eax, eax
0x18000f227  js      loc_18000F2B9
0x18000f22d  mov     rbx, [r14+10h]
0x18000f231  lea     rcx, [rsp+2E0h+var_288]
0x18000f236  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f23c  lea     r8, [rsp+2E0h+var_2A8]; struct ABO_NODE **
0x18000f241  mov     rcx, rbx; this
0x18000f244  mov     rdx, rax; unsigned __int16 *
0x18000f247  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000f24c  mov     rdi, [rsp+2E0h+var_2A8]
0x18000f251  mov     ebx, eax
0x18000f253  test    eax, eax
0x18000f255  js      short loc_18000F2B9
0x18000f257  mov     r12, [rdi+10h]
0x18000f25b  test    r12, r12
0x18000f25e  jnz     short loc_18000F267
0x18000f260  mov     ebx, 80070057h
0x18000f265  jmp     short loc_18000F2B9
0x18000f267  mov     rdx, [rsp+2E0h+var_290]; unsigned __int16 *
0x18000f26c  lea     r9, [rsp+2E0h+var_2B0]; struct ABO_NODE **
0x18000f271  xor     r8d, r8d; int
0x18000f274  mov     [rsp+2E0h+var_2C0], 1; int
0x18000f27c  mov     rcx, r12; this
0x18000f27f  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x18000f284  mov     rsi, [rsp+2E0h+var_2B0]
0x18000f289  mov     ebx, eax
0x18000f28b  test    eax, eax
0x18000f28d  js      short loc_18000F2B9
0x18000f28f  mov     rdx, rdi; struct ABO_NODE *
0x18000f292  mov     rcx, rsi; this
0x18000f295  call    ?CopyPropertiesAndChildren@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::CopyPropertiesAndChildren(ABO_NODE *)
0x18000f29a  mov     ebx, eax
0x18000f29c  test    eax, eax
0x18000f29e  js      short loc_18000F2B9
0x18000f2a0  mov     rdx, rdi; struct ABO_NODE *
0x18000f2a3  mov     rcx, r12; this
0x18000f2a6  call    ?DeleteChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::DeleteChildNode(ABO_NODE *)
0x18000f2ab  mov     ebx, eax
0x18000f2ad  test    eax, eax
0x18000f2af  js      short loc_18000F2B9
0x18000f2b1  mov     rcx, r15; this
0x18000f2b4  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000f2b9  lea     rcx, [r13+20h]
0x18000f2bd  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000f2c3  test    r15, r15
0x18000f2c6  jz      short loc_18000F2D0
0x18000f2c8  mov     rcx, r15; this
0x18000f2cb  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000f2d0  test    rdi, rdi
0x18000f2d3  jz      short loc_18000F2DD
0x18000f2d5  mov     rcx, rdi; this
0x18000f2d8  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000f2dd  test    rsi, rsi
0x18000f2e0  jz      short loc_18000F2EA
0x18000f2e2  mov     rcx, rsi; this
0x18000f2e5  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000f2ea  test    r14, r14
0x18000f2ed  jz      short loc_18000F2F7
0x18000f2ef  mov     rcx, r14; this
0x18000f2f2  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000f2f7  lea     rcx, [rsp+2E0h+var_288]
0x18000f2fc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f302  mov     eax, ebx
0x18000f304  mov     rcx, [rbp+1E0h+var_50]
0x18000f30b  xor     rcx, rsp; StackCookie
0x18000f30e  call    __security_check_cookie
0x18000f313  add     rsp, 2A8h
0x18000f31a  pop     r15
0x18000f31c  pop     r14
0x18000f31e  pop     r13
0x18000f320  pop     r12
0x18000f322  pop     rdi
0x18000f323  pop     rsi
0x18000f324  pop     rbx
0x18000f325  pop     rbp
0x18000f326  retn
```

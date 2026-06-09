# ABO_WRAPPER::SetData(ulong,ushort const *,_METADATA_RECORD *)

- ea: `0x18000f390`
- end: `0x18000f621`
- name: `?SetData@ABO_WRAPPER@@UEAAJKPEBGPEAU_METADATA_RECORD@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x18000672c`
- `0x180007148`
- `0x180007ac8`
- `0x18000a6fc`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f390`
- `0x18000f6dc`
- `0x18000f820`
- `0x18002a070`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f464`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f5ac`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f464`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f5ac`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f44b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f4d5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f44b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000f4d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f3fc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000f3fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f5f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000f5f6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f4fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f52e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f55a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f4fc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f52e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000f55a`

## string_xrefs

- `0x18000f475`: `Failed to commit changes induced by setting Scriptmaps and Mimemaps data due to error = (%X)`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::SetData(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4)
{
  struct ABO_TREE *v8; // r15
  int FullPath; // edi
  LAZY_WRITER *v10; // rdi
  int HandleEntry; // eax
  HANDLE_ENTRY *v12; // rsi
  int CurrentAboTree; // eax
  unsigned __int16 *Str; // rax
  ABO_NODE *v15; // rbx
  const unsigned __int16 *v16; // rax
  struct ABO_NODE *v18; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE_ENTRY *v19; // [rsp+38h] [rbp-C8h] BYREF
  struct ABO_TREE *v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[64]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[256]; // [rsp+A0h] [rbp-60h] BYREF

  v20[1] = (struct ABO_TREE *)a4;
  v19 = 0;
  v18 = 0;
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v22, v23, 0x100u);
  v21[0] = 0;
  v8 = 0;
  v21[1] = 0;
  v20[0] = 0;
  if ( a4 )
  {
    v10 = (LAZY_WRITER *)*((_QWORD *)g_pAboWrapper + 28);
    if ( !v10
      || *(_DWORD *)v10
      || a4->dwMDIdentifier - 6014 > 1
      || (CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32)),
          FullPath = LAZY_WRITER::CommitChanges(v10, 1),
          CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32)),
          FullPath >= 0) )
    {
      HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v19);
      v12 = v19;
      FullPath = HandleEntry;
      if ( HandleEntry >= 0 )
      {
        if ( (*((_BYTE *)v19 + 76) & 2) != 0 )
        {
          FullPath = HANDLE_ENTRY::GetFullPath(v19, a3, (struct STRU *)v22);
          if ( FullPath >= 0 )
          {
            CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
            CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, v20);
            v8 = v20[0];
            FullPath = CurrentAboTree;
            if ( CurrentAboTree >= 0 )
            {
              Str = STRU::QueryStr((STRU *)v22);
              FullPath = ABO_WRAPPER::CheckAccessAndPermissions(this, v8, Str, 1, 0);
              if ( FullPath >= 0 )
              {
                v15 = (ABO_NODE *)*((_QWORD *)v8 + 2);
                v16 = STRU::QueryStr((STRU *)v22);
                ABO_NODE::FindNode(v15, v16, &v18);
              }
            }
            CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
          }
        }
        else
        {
          FullPath = -2147024891;
        }
      }
      if ( v12 )
        HANDLE_ENTRY::DereferenceHandleEntry(v12);
      if ( v8 )
        HANDLE_ENTRY::DereferenceHandleEntry(v8);
    }
    else
    {
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"Failed to commit changes induced by setting Scriptmaps and Mimemaps data due to error = (%X)",
        (unsigned int)FullPath);
    }
    if ( FullPath == -2147024894 )
      FullPath = -2146646015;
  }
  else
  {
    FullPath = -2147024809;
  }
  ARRAY_LIST::~ARRAY_LIST((ARRAY_LIST *)v21);
  STRU::~STRU((STRU *)v22);
  return (unsigned int)FullPath;
}

```

## disassembly

```asm
0x18000f390  push    rbp
0x18000f392  push    rbx
0x18000f393  push    rsi
0x18000f394  push    rdi
0x18000f395  push    r12
0x18000f397  push    r13
0x18000f399  push    r14
0x18000f39b  push    r15
0x18000f39d  lea     rbp, [rsp-1B8h]
0x18000f3a5  sub     rsp, 2B8h
0x18000f3ac  mov     rax, cs:__security_cookie
0x18000f3b3  xor     rax, rsp
0x18000f3b6  mov     [rbp+1F0h+var_50], rax
0x18000f3bd  xor     edi, edi
0x18000f3bf  mov     rbx, r9
0x18000f3c2  mov     r12, r8
0x18000f3c5  mov     [rsp+2F0h+var_2A8], rbx
0x18000f3ca  mov     esi, edx
0x18000f3cc  mov     [rsp+2F0h+var_2B8], rdi
0x18000f3d1  mov     r13, rcx
0x18000f3d4  mov     [rsp+2F0h+var_2C0], rdi
0x18000f3d9  xor     edx, edx; Val
0x18000f3db  lea     rcx, [rbp+1F0h+var_250]; void *
0x18000f3df  mov     r8d, 200h; Size
0x18000f3e5  mov     r14d, edi
0x18000f3e8  call    memset_0
0x18000f3ed  mov     r8d, 100h
0x18000f3f3  lea     rdx, [rbp+1F0h+var_250]
0x18000f3f7  lea     rcx, [rsp+2F0h+var_290]
0x18000f3fc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000f402  mov     [rsp+2F0h+var_2A0], rdi
0x18000f407  mov     r15d, edi
0x18000f40a  mov     [rsp+2F0h+var_298], rdi
0x18000f40f  mov     [rsp+2F0h+var_2B0], rdi
0x18000f414  test    rbx, rbx
0x18000f417  jnz     short loc_18000F423
0x18000f419  mov     edi, 80070057h
0x18000f41e  jmp     loc_18000F5E7
0x18000f423  mov     rax, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18000f42a  mov     rdi, [rax+0E0h]
0x18000f431  test    rdi, rdi
0x18000f434  jz      short loc_18000F489
0x18000f436  cmp     [rdi], r14d
0x18000f439  jnz     short loc_18000F489
0x18000f43b  mov     eax, [rbx]
0x18000f43d  sub     eax, 177Eh
0x18000f442  cmp     eax, 1
0x18000f445  ja      short loc_18000F489
0x18000f447  lea     rcx, [r13+20h]
0x18000f44b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000f451  mov     edx, 1; int
0x18000f456  mov     rcx, rdi; this
0x18000f459  call    ?CommitChanges@LAZY_WRITER@@QEAAJH@Z; LAZY_WRITER::CommitChanges(int)
0x18000f45e  lea     rcx, [r13+20h]
0x18000f462  mov     edi, eax
0x18000f464  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000f46a  test    edi, edi
0x18000f46c  jns     short loc_18000F489
0x18000f46e  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000f475  lea     rdx, aFailedToCommit_0; "Failed to commit changes induced by set"...
0x18000f47c  mov     r8d, edi
0x18000f47f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000f484  jmp     loc_18000F5D9
0x18000f489  lea     r8, [rsp+2F0h+var_2B8]; struct HANDLE_ENTRY **
0x18000f48e  mov     edx, esi; unsigned int
0x18000f490  mov     rcx, r13; this
0x18000f493  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000f498  mov     rsi, [rsp+2F0h+var_2B8]
0x18000f49d  mov     edi, eax
0x18000f49f  test    eax, eax
0x18000f4a1  js      loc_18000F5B2
0x18000f4a7  test    byte ptr [rsi+4Ch], 2
0x18000f4ab  jnz     short loc_18000F4B7
0x18000f4ad  mov     edi, 80070005h
0x18000f4b2  jmp     loc_18000F5B2
0x18000f4b7  lea     r8, [rsp+2F0h+var_290]; struct STRU *
0x18000f4bc  mov     rdx, r12; unsigned __int16 *
0x18000f4bf  mov     rcx, rsi; this
0x18000f4c2  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000f4c7  mov     edi, eax
0x18000f4c9  test    eax, eax
0x18000f4cb  js      loc_18000F5B2
0x18000f4d1  lea     rcx, [r13+20h]
0x18000f4d5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000f4db  lea     rdx, [rsp+2F0h+var_2B0]; struct ABO_TREE **
0x18000f4e0  mov     rcx, r13; this
0x18000f4e3  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000f4e8  mov     r15, [rsp+2F0h+var_2B0]
0x18000f4ed  mov     edi, eax
0x18000f4ef  test    eax, eax
0x18000f4f1  js      loc_18000F5A8
0x18000f4f7  lea     rcx, [rsp+2F0h+var_290]
0x18000f4fc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f502  mov     r9d, 1
0x18000f508  mov     qword ptr [rsp+2F0h+var_2D0], r14
0x18000f50d  mov     r8, rax
0x18000f510  mov     rdx, r15
0x18000f513  mov     rcx, r13
0x18000f516  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000f51b  mov     edi, eax
0x18000f51d  test    eax, eax
0x18000f51f  js      loc_18000F5A8
0x18000f525  mov     rbx, [r15+10h]
0x18000f529  lea     rcx, [rsp+2F0h+var_290]
0x18000f52e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f534  lea     r8, [rsp+2F0h+var_2C0]; struct ABO_NODE **
0x18000f539  mov     rcx, rbx; this
0x18000f53c  mov     rdx, rax; unsigned __int16 *
0x18000f53f  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000f544  mov     edi, eax
0x18000f546  test    eax, eax
0x18000f548  jns     short loc_18000F585
0x18000f54a  cmp     eax, 80070003h
0x18000f54f  jnz     short loc_18000F57E
0x18000f551  mov     rbx, [r15+10h]
0x18000f555  lea     rcx, [rsp+2F0h+var_290]
0x18000f55a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000f560  lea     r9, [rsp+2F0h+var_2C0]; struct ABO_NODE **
0x18000f565  mov     [rsp+2F0h+var_2D0], r14d; int
0x18000f56a  mov     rdx, rax; unsigned __int16 *
0x18000f56d  xor     r8d, r8d; int
0x18000f570  mov     rcx, rbx; this
0x18000f573  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x18000f578  mov     edi, eax
0x18000f57a  test    eax, eax
0x18000f57c  jns     short loc_18000F585
0x18000f57e  mov     r14, [rsp+2F0h+var_2C0]
0x18000f583  jmp     short loc_18000F5A8
0x18000f585  mov     r14, [rsp+2F0h+var_2C0]
0x18000f58a  xor     r8d, r8d; int
0x18000f58d  mov     rdx, [rsp+2F0h+var_2A8]; struct _METADATA_RECORD *
0x18000f592  mov     rcx, r14; this
0x18000f595  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x18000f59a  mov     edi, eax
0x18000f59c  test    eax, eax
0x18000f59e  js      short loc_18000F5A8
0x18000f5a0  mov     rcx, rsi; this
0x18000f5a3  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000f5a8  lea     rcx, [r13+20h]
0x18000f5ac  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000f5b2  test    rsi, rsi
0x18000f5b5  jz      short loc_18000F5BF
0x18000f5b7  mov     rcx, rsi; this
0x18000f5ba  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000f5bf  test    r14, r14
0x18000f5c2  jz      short loc_18000F5CC
0x18000f5c4  mov     rcx, r14; this
0x18000f5c7  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000f5cc  test    r15, r15
0x18000f5cf  jz      short loc_18000F5D9
0x18000f5d1  mov     rcx, r15; this
0x18000f5d4  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000f5d9  cmp     edi, 80070002h
0x18000f5df  mov     eax, 800CC801h
0x18000f5e4  cmovz   edi, eax
0x18000f5e7  lea     rcx, [rsp+2F0h+var_2A0]; this
0x18000f5ec  call    ??1ARRAY_LIST@@QEAA@XZ; ARRAY_LIST::~ARRAY_LIST(void)
0x18000f5f1  lea     rcx, [rsp+2F0h+var_290]
0x18000f5f6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f5fc  mov     eax, edi
0x18000f5fe  mov     rcx, [rbp+1F0h+var_50]
0x18000f605  xor     rcx, rsp; StackCookie
0x18000f608  call    __security_check_cookie
0x18000f60d  add     rsp, 2B8h
0x18000f614  pop     r15
0x18000f616  pop     r14
0x18000f618  pop     r13
0x18000f61a  pop     r12
0x18000f61c  pop     rdi
0x18000f61d  pop     rsi
0x18000f61e  pop     rbx
0x18000f61f  pop     rbp
0x18000f620  retn
```

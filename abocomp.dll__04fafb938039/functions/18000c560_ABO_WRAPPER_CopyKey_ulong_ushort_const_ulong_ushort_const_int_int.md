# ABO_WRAPPER::CopyKey(ulong,ushort const *,ulong,ushort const *,int,int)

- ea: `0x18000c560`
- end: `0x18000c93d`
- name: `?CopyKey@ABO_WRAPPER@@UEAAJKPEBGK0HH@Z`
- size: `989`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180006f54`
- `0x180007148`
- `0x180007530`
- `0x180007724`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000c560`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c716`
- `msvcrt!_wcsnicmp` at `0x18000c716`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000c6d8`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000c6e9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000c6d8`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000c6e9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c839`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c839`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c75a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c75a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c5d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c5ff`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c5d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c5ff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c901`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c90b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c901`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c90b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c6f7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c705`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c725`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c73d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c781`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c7b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c7d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c803`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c6f7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c705`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c725`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c73d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c781`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c7b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c7d7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c803`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CopyKey(
        ABO_WRAPPER *this,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        int a7)
{
  struct ABO_TREE *v10; // r14
  int HandleEntry; // eax
  HANDLE_ENTRY *v12; // r13
  int FullPath; // ebx
  int v14; // eax
  HANDLE_ENTRY *v15; // r15
  unsigned int v16; // ebx
  const wchar_t *v17; // rbx
  const wchar_t *v18; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // rbx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v23; // rbx
  const unsigned __int16 *v24; // rax
  size_t MaxCount; // [rsp+38h] [rbp-C8h] BYREF
  struct ABO_NODE *v27; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE_ENTRY *v28; // [rsp+48h] [rbp-B8h] BYREF
  struct ABO_TREE *v29; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v31; // [rsp+60h] [rbp-A0h]
  _BYTE v32[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v34[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v35[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v30 = a3;
  v31 = a5;
  MaxCount = 0;
  v28 = 0;
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v33, v34, 0x100u);
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v32, v35, 0x100u);
  v29 = 0;
  v10 = 0;
  v27 = 0;
  if ( a2 && a4 )
  {
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a4, (struct HANDLE_ENTRY **)&MaxCount);
    v12 = (HANDLE_ENTRY *)MaxCount;
    FullPath = HandleEntry;
    if ( HandleEntry >= 0 )
    {
      if ( (*(_BYTE *)(MaxCount + 76) & 1) != 0 && (a7 || (*(_BYTE *)(MaxCount + 76) & 2) != 0) )
      {
        FullPath = HANDLE_ENTRY::GetFullPath((HANDLE_ENTRY *)MaxCount, v30, (struct STRU *)v33);
        if ( FullPath >= 0 )
        {
          v14 = ABO_WRAPPER::GetHandleEntry(this, a4, &v28);
          v15 = v28;
          FullPath = v14;
          if ( v14 >= 0 )
          {
            if ( (*((_BYTE *)v28 + 76) & 2) != 0 )
            {
              FullPath = HANDLE_ENTRY::GetFullPath(v28, v31, (struct STRU *)v32);
              if ( FullPath >= 0 )
              {
                LODWORD(MaxCount) = STRU::QueryCCH((STRU *)v33);
                v16 = MaxCount;
                if ( STRU::QueryCCH((STRU *)v32) < v16
                  || (v17 = STRU::QueryStr((STRU *)v33),
                      v18 = STRU::QueryStr((STRU *)v32),
                      _wcsnicmp(v18, v17, (unsigned int)MaxCount))
                  || (v19 = STRU::QueryStr((STRU *)v32), v20 = (unsigned int)MaxCount, v19[(unsigned int)MaxCount] != 47)
                  && STRU::QueryStr((STRU *)v32)[v20] )
                {
                  CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
                  CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v29);
                  v10 = v29;
                  FullPath = CurrentAboTree;
                  if ( CurrentAboTree >= 0 )
                  {
                    Str = STRU::QueryStr((STRU *)v32);
                    FullPath = ABO_WRAPPER::CheckAccessAndPermissions(this, v10, Str, 1, 0);
                    if ( FullPath >= 0 )
                    {
                      v23 = (ABO_NODE *)*((_QWORD *)v10 + 2);
                      v24 = STRU::QueryStr((STRU *)v33);
                      ABO_NODE::FindNode(v23, v24, &v27);
                    }
                  }
                  CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
                }
                else
                {
                  FullPath = -2147024809;
                }
              }
            }
            else
            {
              FullPath = -2147024891;
            }
          }
          if ( v15 )
            HANDLE_ENTRY::DereferenceHandleEntry(v15);
        }
      }
      else
      {
        FullPath = -2147024891;
      }
    }
    if ( v12 )
      HANDLE_ENTRY::DereferenceHandleEntry(v12);
    if ( v10 )
      HANDLE_ENTRY::DereferenceHandleEntry(v10);
  }
  else
  {
    FullPath = -2147024809;
  }
  STRU::~STRU((STRU *)v32);
  STRU::~STRU((STRU *)v33);
  return (unsigned int)FullPath;
}

```

## disassembly

```asm
0x18000c560  mov     [rsp-8+arg_8], rbx
0x18000c565  push    rbp
0x18000c566  push    rsi
0x18000c567  push    rdi
0x18000c568  push    r12
0x18000c56a  push    r13
0x18000c56c  push    r14
0x18000c56e  push    r15
0x18000c570  lea     rbp, [rsp-3F0h]
0x18000c578  sub     rsp, 4F0h
0x18000c57f  mov     rax, cs:__security_cookie
0x18000c586  xor     rax, rsp
0x18000c589  mov     [rbp+420h+var_40], rax
0x18000c590  mov     rax, [rbp+420h+arg_20]
0x18000c597  mov     ebx, edx
0x18000c599  mov     [rsp+520h+var_4C8], r8
0x18000c59e  mov     r12, rcx
0x18000c5a1  xor     r13d, r13d
0x18000c5a4  mov     [rsp+520h+var_4C0], rax
0x18000c5a9  mov     esi, 200h
0x18000c5ae  mov     [rsp+520h+MaxCount], r13
0x18000c5b3  mov     r8d, esi; Size
0x18000c5b6  mov     [rsp+520h+var_4D8], r13
0x18000c5bb  xor     edx, edx; Val
0x18000c5bd  lea     rcx, [rbp+420h+var_440]; void *
0x18000c5c1  mov     r15d, r9d
0x18000c5c4  call    memset_0
0x18000c5c9  mov     edi, 100h
0x18000c5ce  lea     rdx, [rbp+420h+var_440]
0x18000c5d2  mov     r8d, edi
0x18000c5d5  lea     rcx, [rbp+420h+var_480]
0x18000c5d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c5df  mov     r8d, esi; Size
0x18000c5e2  lea     rcx, [rbp+420h+var_240]; void *
0x18000c5e9  xor     edx, edx; Val
0x18000c5eb  call    memset_0
0x18000c5f0  mov     r8d, edi
0x18000c5f3  lea     rdx, [rbp+420h+var_240]
0x18000c5fa  lea     rcx, [rsp+520h+var_4B8]
0x18000c5ff  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c605  mov     [rsp+520h+var_4D0], r13
0x18000c60a  mov     r14d, r13d
0x18000c60d  mov     [rsp+520h+var_4E0], r13
0x18000c612  mov     edi, r13d
0x18000c615  mov     [rsp+520h+var_4F0], r13
0x18000c61a  mov     esi, r13d
0x18000c61d  test    ebx, ebx
0x18000c61f  jz      loc_18000C8F7
0x18000c625  test    r15d, r15d
0x18000c628  jz      loc_18000C8F7
0x18000c62e  lea     r8, [rsp+520h+MaxCount]; struct HANDLE_ENTRY **
0x18000c633  mov     edx, r15d; unsigned int
0x18000c636  mov     rcx, r12; this
0x18000c639  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000c63e  mov     r13, [rsp+520h+MaxCount]
0x18000c643  mov     ebx, eax
0x18000c645  xor     eax, eax
0x18000c647  test    ebx, ebx
0x18000c649  js      loc_18000C8DB
0x18000c64f  test    byte ptr [r13+4Ch], 1
0x18000c654  jz      loc_18000C8D6
0x18000c65a  cmp     [rbp+420h+arg_30], eax
0x18000c660  jnz     short loc_18000C66D
0x18000c662  test    byte ptr [r13+4Ch], 2
0x18000c667  jz      loc_18000C8D6
0x18000c66d  mov     rdx, [rsp+520h+var_4C8]; unsigned __int16 *
0x18000c672  lea     r8, [rbp+420h+var_480]; struct STRU *
0x18000c676  mov     rcx, r13; this
0x18000c679  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000c67e  mov     ebx, eax
0x18000c680  test    eax, eax
0x18000c682  js      loc_18000C8DB
0x18000c688  lea     r8, [rsp+520h+var_4D8]; struct HANDLE_ENTRY **
0x18000c68d  mov     edx, r15d; unsigned int
0x18000c690  mov     rcx, r12; this
0x18000c693  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000c698  mov     r15, [rsp+520h+var_4D8]
0x18000c69d  mov     ebx, eax
0x18000c69f  test    eax, eax
0x18000c6a1  js      loc_18000C859
0x18000c6a7  test    byte ptr [r15+4Ch], 2
0x18000c6ac  jnz     short loc_18000C6B8
0x18000c6ae  mov     ebx, 80070005h
0x18000c6b3  jmp     loc_18000C859
0x18000c6b8  mov     rdx, [rsp+520h+var_4C0]; unsigned __int16 *
0x18000c6bd  lea     r8, [rsp+520h+var_4B8]; struct STRU *
0x18000c6c2  mov     rcx, r15; this
0x18000c6c5  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000c6ca  mov     ebx, eax
0x18000c6cc  test    eax, eax
0x18000c6ce  js      loc_18000C859
0x18000c6d4  lea     rcx, [rbp+420h+var_480]
0x18000c6d8  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000c6de  lea     rcx, [rsp+520h+var_4B8]
0x18000c6e3  mov     dword ptr [rsp+520h+MaxCount], eax
0x18000c6e7  mov     ebx, eax
0x18000c6e9  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000c6ef  cmp     eax, ebx
0x18000c6f1  jb      short loc_18000C755
0x18000c6f3  lea     rcx, [rbp+420h+var_480]
0x18000c6f7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c6fd  lea     rcx, [rsp+520h+var_4B8]
0x18000c702  mov     rbx, rax
0x18000c705  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c70b  mov     r8d, dword ptr [rsp+520h+MaxCount]; MaxCount
0x18000c710  mov     rdx, rbx; String2
0x18000c713  mov     rcx, rax; String1
0x18000c716  call    cs:__imp__wcsnicmp
0x18000c71c  test    eax, eax
0x18000c71e  jnz     short loc_18000C755
0x18000c720  lea     rcx, [rsp+520h+var_4B8]
0x18000c725  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c72b  mov     ecx, dword ptr [rsp+520h+MaxCount]
0x18000c72f  mov     ebx, ecx
0x18000c731  cmp     word ptr [rax+rcx*2], 2Fh ; '/'
0x18000c736  jz      short loc_18000C74B
0x18000c738  lea     rcx, [rsp+520h+var_4B8]
0x18000c73d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c743  xor     ecx, ecx
0x18000c745  cmp     [rax+rbx*2], cx
0x18000c749  jnz     short loc_18000C755
0x18000c74b  mov     ebx, 80070057h
0x18000c750  jmp     loc_18000C859
0x18000c755  lea     rcx, [r12+20h]
0x18000c75a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c760  lea     rdx, [rsp+520h+var_4D0]; struct ABO_TREE **
0x18000c765  mov     rcx, r12; this
0x18000c768  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000c76d  mov     r14, [rsp+520h+var_4D0]
0x18000c772  mov     ebx, eax
0x18000c774  test    eax, eax
0x18000c776  js      loc_18000C834
0x18000c77c  lea     rcx, [rsp+520h+var_4B8]
0x18000c781  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c787  mov     r9d, 1
0x18000c78d  mov     qword ptr [rsp+520h+var_500], rsi
0x18000c792  mov     r8, rax
0x18000c795  mov     rdx, r14
0x18000c798  mov     rcx, r12
0x18000c79b  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000c7a0  mov     ebx, eax
0x18000c7a2  test    eax, eax
0x18000c7a4  js      loc_18000C834
0x18000c7aa  mov     rbx, [r14+10h]
0x18000c7ae  lea     rcx, [rbp+420h+var_480]
0x18000c7b2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c7b8  lea     r8, [rsp+520h+var_4E0]; struct ABO_NODE **
0x18000c7bd  mov     rcx, rbx; this
0x18000c7c0  mov     rdx, rax; unsigned __int16 *
0x18000c7c3  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000c7c8  mov     ebx, eax
0x18000c7ca  test    eax, eax
0x18000c7cc  js      short loc_18000C82F
0x18000c7ce  mov     rbx, [r14+10h]
0x18000c7d2  lea     rcx, [rsp+520h+var_4B8]
0x18000c7d7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c7dd  lea     r8, [rsp+520h+var_4F0]; struct ABO_NODE **
0x18000c7e2  mov     rcx, rbx; this
0x18000c7e5  mov     rdx, rax; unsigned __int16 *
0x18000c7e8  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000c7ed  mov     ebx, eax
0x18000c7ef  test    eax, eax
0x18000c7f1  jns     short loc_18000C868
0x18000c7f3  cmp     eax, 80070003h
0x18000c7f8  jnz     short loc_18000C82A
0x18000c7fa  mov     rbx, [r14+10h]
0x18000c7fe  lea     rcx, [rsp+520h+var_4B8]
0x18000c803  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c809  lea     r9, [rsp+520h+var_4F0]; struct ABO_NODE **
0x18000c80e  mov     [rsp+520h+var_500], 1; int
0x18000c816  mov     rdx, rax; unsigned __int16 *
0x18000c819  xor     r8d, r8d; int
0x18000c81c  mov     rcx, rbx; this
0x18000c81f  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x18000c824  mov     ebx, eax
0x18000c826  test    eax, eax
0x18000c828  jns     short loc_18000C886
0x18000c82a  mov     rsi, [rsp+520h+var_4F0]
0x18000c82f  mov     rdi, [rsp+520h+var_4E0]
0x18000c834  lea     rcx, [r12+20h]
0x18000c839  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c83f  test    rdi, rdi
0x18000c842  jz      short loc_18000C84C
0x18000c844  mov     rcx, rdi; this
0x18000c847  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000c84c  test    rsi, rsi
0x18000c84f  jz      short loc_18000C859
0x18000c851  mov     rcx, rsi; this
0x18000c854  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000c859  test    r15, r15
0x18000c85c  jz      short loc_18000C8DB
0x18000c85e  mov     rcx, r15; this
0x18000c861  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c866  jmp     short loc_18000C8DB
0x18000c868  cmp     [rbp+420h+arg_28], 1
0x18000c86f  jnz     short loc_18000C886
0x18000c871  mov     rsi, [rsp+520h+var_4F0]
0x18000c876  mov     rcx, rsi; this
0x18000c879  call    ?DeletePropertiesAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::DeletePropertiesAndChildren(void)
0x18000c87e  mov     ebx, eax
0x18000c880  test    eax, eax
0x18000c882  jns     short loc_18000C88B
0x18000c884  jmp     short loc_18000C82F
0x18000c886  mov     rsi, [rsp+520h+var_4F0]
0x18000c88b  mov     rdi, [rsp+520h+var_4E0]
0x18000c890  mov     rcx, rsi; this
0x18000c893  mov     rdx, rdi; struct ABO_NODE *
0x18000c896  call    ?CopyPropertiesAndChildren@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::CopyPropertiesAndChildren(ABO_NODE *)
0x18000c89b  mov     ebx, eax
0x18000c89d  xor     eax, eax
0x18000c89f  test    ebx, ebx
0x18000c8a1  js      short loc_18000C834
0x18000c8a3  cmp     [rbp+420h+arg_30], eax
0x18000c8a9  jnz     short loc_18000C8C9
0x18000c8ab  mov     rcx, [rdi+10h]; this
0x18000c8af  mov     rdx, rdi; struct ABO_NODE *
0x18000c8b2  call    ?DeleteChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::DeleteChildNode(ABO_NODE *)
0x18000c8b7  mov     ebx, eax
0x18000c8b9  test    eax, eax
0x18000c8bb  js      loc_18000C834
0x18000c8c1  mov     rcx, r13; this
0x18000c8c4  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000c8c9  mov     rcx, r15; this
0x18000c8cc  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000c8d1  jmp     loc_18000C834
0x18000c8d6  mov     ebx, 80070005h
0x18000c8db  test    r13, r13
0x18000c8de  jz      short loc_18000C8E8
0x18000c8e0  mov     rcx, r13; this
0x18000c8e3  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c8e8  test    r14, r14
0x18000c8eb  jz      short loc_18000C8FC
0x18000c8ed  mov     rcx, r14; this
0x18000c8f0  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c8f5  jmp     short loc_18000C8FC
0x18000c8f7  mov     ebx, 80070057h
0x18000c8fc  lea     rcx, [rsp+520h+var_4B8]
0x18000c901  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c907  lea     rcx, [rbp+420h+var_480]
0x18000c90b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c911  mov     eax, ebx
0x18000c913  mov     rcx, [rbp+420h+var_40]
0x18000c91a  xor     rcx, rsp; StackCookie
0x18000c91d  call    __security_check_cookie
0x18000c922  mov     rbx, [rsp+520h+arg_8]
0x18000c92a  add     rsp, 4F0h
0x18000c931  pop     r15
0x18000c933  pop     r14
0x18000c935  pop     r13
0x18000c937  pop     r12
0x18000c939  pop     rdi
0x18000c93a  pop     rsi
0x18000c93b  pop     rbp
0x18000c93c  retn
```

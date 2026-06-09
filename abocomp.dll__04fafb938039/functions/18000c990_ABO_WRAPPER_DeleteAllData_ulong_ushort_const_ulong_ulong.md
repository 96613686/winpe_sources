# ABO_WRAPPER::DeleteAllData(ulong,ushort const *,ulong,ulong)

- ea: `0x18000c990`
- end: `0x18000cba7`
- name: `?DeleteAllData@ABO_WRAPPER@@UEAAJKPEBGKK@Z`
- size: `535`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int)`
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
- `0x18000c990`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`
- `0x18000fde4`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cae2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000caf6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cb08`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cae2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000caf6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cb08`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cb36`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cb36`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca40`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ca40`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c9f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c9f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cb7e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cb7e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ca67`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ca97`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ca67`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ca97`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::DeleteAllData(ABO_WRAPPER *this, unsigned int a2, const unsigned __int16 *a3, int a4)
{
  struct ABO_TREE *v7; // r15
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v11; // rbx
  const unsigned __int16 *v12; // rax
  HANDLE_ENTRY *v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h]
  struct ABO_NODE *v16; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_TREE *v17; // [rsp+48h] [rbp-B8h] BYREF
  ABO_WRAPPER *v18; // [rsp+50h] [rbp-B0h]
  _BYTE v19[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v20[248]; // [rsp+90h] [rbp-70h] BYREF

  v18 = this;
  v15 = a4;
  v16 = 0;
  memset_0(v20, 0, 0x1EAu);
  STRU::STRU((STRU *)v19, v20, 0xF5u);
  v7 = 0;
  v14 = 0;
  v17 = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v14);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v14, a3, (struct STRU *)v19);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v17);
      v7 = v17;
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v19);
        HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v7, Str, 1, 0);
        if ( HandleEntry >= 0 )
        {
          v11 = (ABO_NODE *)*((_QWORD *)v7 + 2);
          v12 = STRU::QueryStr((STRU *)v19);
          ABO_NODE::FindNode(v11, v12, &v16);
        }
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)v18 + 32));
    }
  }
  if ( v14 )
    HANDLE_ENTRY::DereferenceHandleEntry(v14);
  if ( v7 )
    HANDLE_ENTRY::DereferenceHandleEntry(v7);
  if ( (unsigned int)(HandleEntry + 2147024894) <= 1 )
    HandleEntry = -2146646015;
  STRU::~STRU((STRU *)v19);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000c990  push    rbp
0x18000c992  push    rbx
0x18000c993  push    rsi
0x18000c994  push    rdi
0x18000c995  push    r13
0x18000c997  push    r14
0x18000c999  push    r15
0x18000c99b  lea     rbp, [rsp-190h]
0x18000c9a3  sub     rsp, 290h
0x18000c9aa  mov     rax, cs:__security_cookie
0x18000c9b1  xor     rax, rsp
0x18000c9b4  mov     [rbp+1C0h+var_40], rax
0x18000c9bb  mov     r14, r8
0x18000c9be  mov     [rsp+2C0h+var_270], rcx
0x18000c9c3  mov     ebx, edx
0x18000c9c5  mov     [rsp+2C0h+var_288], r9d
0x18000c9ca  mov     rsi, rcx
0x18000c9cd  xor     edi, edi
0x18000c9cf  xor     edx, edx; Val
0x18000c9d1  mov     [rsp+2C0h+var_280], rdi
0x18000c9d6  mov     r8d, 1EAh; Size
0x18000c9dc  lea     rcx, [rbp+1C0h+var_230]; void *
0x18000c9e0  call    memset_0
0x18000c9e5  mov     r8d, 0F5h
0x18000c9eb  lea     rdx, [rbp+1C0h+var_230]
0x18000c9ef  lea     rcx, [rsp+2C0h+var_268]
0x18000c9f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c9fa  xor     r15d, r15d
0x18000c9fd  mov     [rsp+2C0h+var_290], rdi
0x18000ca02  lea     r8, [rsp+2C0h+var_290]; struct HANDLE_ENTRY **
0x18000ca07  mov     [rsp+2C0h+var_278], r15
0x18000ca0c  mov     edx, ebx; unsigned int
0x18000ca0e  mov     rcx, rsi; this
0x18000ca11  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000ca16  mov     ebx, eax
0x18000ca18  test    eax, eax
0x18000ca1a  js      loc_18000CB3C
0x18000ca20  mov     rcx, [rsp+2C0h+var_290]; this
0x18000ca25  lea     r8, [rsp+2C0h+var_268]; struct STRU *
0x18000ca2a  mov     rdx, r14; unsigned __int16 *
0x18000ca2d  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000ca32  mov     ebx, eax
0x18000ca34  test    eax, eax
0x18000ca36  js      loc_18000CB3C
0x18000ca3c  lea     rcx, [rsi+20h]
0x18000ca40  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ca46  lea     rdx, [rsp+2C0h+var_278]; struct ABO_TREE **
0x18000ca4b  mov     rcx, rsi; this
0x18000ca4e  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000ca53  mov     r15, [rsp+2C0h+var_278]
0x18000ca58  mov     ebx, eax
0x18000ca5a  test    eax, eax
0x18000ca5c  js      loc_18000CB2D
0x18000ca62  lea     rcx, [rsp+2C0h+var_268]
0x18000ca67  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ca6d  lea     r9d, [rdi+1]
0x18000ca71  mov     [rsp+2C0h+var_2A0], rdi
0x18000ca76  mov     r8, rax
0x18000ca79  mov     rdx, r15
0x18000ca7c  mov     rcx, rsi
0x18000ca7f  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000ca84  mov     ebx, eax
0x18000ca86  test    eax, eax
0x18000ca88  js      loc_18000CB2D
0x18000ca8e  mov     rbx, [r15+10h]
0x18000ca92  lea     rcx, [rsp+2C0h+var_268]
0x18000ca97  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ca9d  lea     r8, [rsp+2C0h+var_280]; struct ABO_NODE **
0x18000caa2  mov     rcx, rbx; this
0x18000caa5  mov     rdx, rax; unsigned __int16 *
0x18000caa8  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000caad  mov     rdi, [rsp+2C0h+var_280]
0x18000cab2  mov     ebx, eax
0x18000cab4  test    eax, eax
0x18000cab6  js      short loc_18000CB2D
0x18000cab8  lea     r13, [rdi+0B8h]
0x18000cabf  test    r13, r13
0x18000cac2  jz      short loc_18000CB23
0x18000cac4  mov     esi, [r13+10h]
0x18000cac8  jmp     short loc_18000CB1E
0x18000caca  mov     rax, [r13+8]
0x18000cace  mov     r14, [rax+rsi*8]
0x18000cad2  add     r14, 10h
0x18000cad6  cmp     [rbp+1C0h+arg_20], 0
0x18000cadd  jz      short loc_18000CAF3
0x18000cadf  mov     rcx, r14
0x18000cae2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000cae8  mov     ecx, [rbp+1C0h+arg_20]
0x18000caee  cmp     [rax+0Ch], ecx
0x18000caf1  jnz     short loc_18000CB1E
0x18000caf3  mov     rcx, r14
0x18000caf6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000cafc  mov     ecx, [rsp+2C0h+var_288]
0x18000cb00  cmp     [rax+8], ecx
0x18000cb03  jnz     short loc_18000CB1E
0x18000cb05  mov     rcx, r14
0x18000cb08  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000cb0e  mov     rcx, r13; this
0x18000cb11  mov     edx, [rax]; unsigned int
0x18000cb13  call    ?DeleteEntry@PROPERTY_BAG@@QEAAJK@Z; PROPERTY_BAG::DeleteEntry(ulong)
0x18000cb18  mov     ebx, eax
0x18000cb1a  test    eax, eax
0x18000cb1c  js      short loc_18000CB2D
0x18000cb1e  sub     esi, 1
0x18000cb21  jns     short loc_18000CACA
0x18000cb23  mov     rcx, [rsp+2C0h+var_290]; this
0x18000cb28  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000cb2d  mov     rcx, [rsp+2C0h+var_270]
0x18000cb32  add     rcx, 20h ; ' '
0x18000cb36  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000cb3c  cmp     [rsp+2C0h+var_290], 0
0x18000cb42  jz      short loc_18000CB4E
0x18000cb44  mov     rcx, [rsp+2C0h+var_290]; this
0x18000cb49  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cb4e  test    rdi, rdi
0x18000cb51  jz      short loc_18000CB5B
0x18000cb53  mov     rcx, rdi; this
0x18000cb56  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000cb5b  test    r15, r15
0x18000cb5e  jz      short loc_18000CB68
0x18000cb60  mov     rcx, r15; this
0x18000cb63  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cb68  lea     ecx, [rbx+7FF8FFFEh]
0x18000cb6e  mov     eax, 800CC801h
0x18000cb73  cmp     ecx, 1
0x18000cb76  lea     rcx, [rsp+2C0h+var_268]
0x18000cb7b  cmovbe  ebx, eax
0x18000cb7e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cb84  mov     eax, ebx
0x18000cb86  mov     rcx, [rbp+1C0h+var_40]
0x18000cb8d  xor     rcx, rsp; StackCookie
0x18000cb90  call    __security_check_cookie
0x18000cb95  add     rsp, 290h
0x18000cb9c  pop     r15
0x18000cb9e  pop     r14
0x18000cba0  pop     r13
0x18000cba2  pop     rdi
0x18000cba3  pop     rsi
0x18000cba4  pop     rbx
0x18000cba5  pop     rbp
0x18000cba6  retn
```

# ABO_WRAPPER::GetDataPaths(ulong,ushort const *,ulong,ulong,ulong,ushort *,ulong *)

- ea: `0x18000e170`
- end: `0x18000e3d9`
- name: `?GetDataPaths@ABO_WRAPPER@@UEAAJKPEBGKKKPEAGPEAK@Z`
- size: `617`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x180008c90`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000e170`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000ffd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e341`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x18000e337`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x18000e337`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000e2fd`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000e315`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000e2fd`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000e315`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e361`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e361`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e23e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000e23e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e1e1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e1e1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e3b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e3b0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e264`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e297`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e264`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000e297`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000e1f1`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000e1f1`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000e3a6`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000e3a6`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetDataPaths(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7)
{
  struct ABO_TREE *v10; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v14; // rbx
  const unsigned __int16 *v15; // rax
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  struct ABO_NODE *v18; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE_ENTRY *v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h]
  struct ABO_TREE *v21[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v23[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v24[248]; // [rsp+E0h] [rbp-20h] BYREF

  v21[2] = (struct ABO_TREE *)a7;
  v20 = a4;
  v18 = 0;
  memset_0(v24, 0, 0x1EAu);
  STRU::STRU((STRU *)v23, v24, 0xF5u);
  v19 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v22);
  v10 = 0;
  v17 = 3;
  v21[0] = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v19);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v19, a3, (struct STRU *)v23);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, v21);
      v10 = v21[0];
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v23);
        HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v10, Str, 0, (enum ACCESS_GRANTED *)&v17);
        if ( HandleEntry >= 0 )
        {
          v14 = (ABO_NODE *)*((_QWORD *)v10 + 2);
          v15 = STRU::QueryStr((STRU *)v23);
          ABO_NODE::FindNode(v14, v15, &v18);
        }
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    }
  }
  if ( v19 )
    HANDLE_ENTRY::DereferenceHandleEntry(v19);
  if ( v10 )
    HANDLE_ENTRY::DereferenceHandleEntry(v10);
  if ( HandleEntry == -2147024894 )
    HandleEntry = -2146646015;
  MULTISZ::~MULTISZ((MULTISZ *)v22);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000e170  push    rbp
0x18000e172  push    rbx
0x18000e173  push    rsi
0x18000e174  push    rdi
0x18000e175  push    r12
0x18000e177  push    r13
0x18000e179  push    r15
0x18000e17b  lea     rbp, [rsp-1E0h]
0x18000e183  sub     rsp, 2E0h
0x18000e18a  mov     rax, cs:__security_cookie
0x18000e191  xor     rax, rsp
0x18000e194  mov     [rbp+210h+var_40], rax
0x18000e19b  mov     rax, [rbp+210h+arg_30]
0x18000e1a2  mov     r12, r8
0x18000e1a5  mov     r13, [rbp+210h+arg_38]
0x18000e1ac  mov     ebx, edx
0x18000e1ae  mov     r15, rcx
0x18000e1b1  mov     [rsp+310h+var_2B0], rax
0x18000e1b6  xor     edi, edi
0x18000e1b8  mov     [rsp+310h+var_2C8], r9d
0x18000e1bd  xor     edx, edx; Val
0x18000e1bf  mov     [rsp+310h+var_2D8], rdi
0x18000e1c4  mov     r8d, 1EAh; Size
0x18000e1ca  lea     rcx, [rbp+210h+var_230]; void *
0x18000e1ce  call    memset_0
0x18000e1d3  mov     r8d, 0F5h
0x18000e1d9  lea     rdx, [rbp+210h+var_230]
0x18000e1dd  lea     rcx, [rbp+210h+var_270]
0x18000e1e1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e1e7  lea     rcx, [rsp+310h+var_2A8]
0x18000e1ec  mov     [rsp+310h+var_2D0], rdi
0x18000e1f1  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000e1f7  xor     esi, esi
0x18000e1f9  mov     [rsp+310h+var_2E0], 3
0x18000e201  lea     r8, [rsp+310h+var_2D0]; struct HANDLE_ENTRY **
0x18000e206  mov     [rsp+310h+var_2C0], rsi
0x18000e20b  mov     edx, ebx; unsigned int
0x18000e20d  mov     rcx, r15; this
0x18000e210  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000e215  mov     ebx, eax
0x18000e217  test    eax, eax
0x18000e219  js      loc_18000E367
0x18000e21f  mov     rcx, [rsp+310h+var_2D0]; this
0x18000e224  lea     r8, [rbp+210h+var_270]; struct STRU *
0x18000e228  mov     rdx, r12; unsigned __int16 *
0x18000e22b  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000e230  mov     ebx, eax
0x18000e232  test    eax, eax
0x18000e234  js      loc_18000E367
0x18000e23a  lea     rcx, [r15+20h]
0x18000e23e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000e244  lea     rdx, [rsp+310h+var_2C0]; struct ABO_TREE **
0x18000e249  mov     rcx, r15; this
0x18000e24c  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000e251  mov     rsi, [rsp+310h+var_2C0]
0x18000e256  mov     ebx, eax
0x18000e258  test    eax, eax
0x18000e25a  js      loc_18000E35D
0x18000e260  lea     rcx, [rbp+210h+var_270]
0x18000e264  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e26a  lea     rcx, [rsp+310h+var_2E0]
0x18000e26f  xor     r9d, r9d
0x18000e272  mov     [rsp+310h+var_2F0], rcx
0x18000e277  mov     r8, rax
0x18000e27a  mov     rcx, r15
0x18000e27d  mov     rdx, rsi
0x18000e280  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000e285  mov     ebx, eax
0x18000e287  test    eax, eax
0x18000e289  js      loc_18000E35D
0x18000e28f  mov     rbx, [rsi+10h]
0x18000e293  lea     rcx, [rbp+210h+var_270]
0x18000e297  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000e29d  lea     r8, [rsp+310h+var_2D8]; struct ABO_NODE **
0x18000e2a2  mov     rcx, rbx; this
0x18000e2a5  mov     rdx, rax; unsigned __int16 *
0x18000e2a8  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000e2ad  mov     ebx, eax
0x18000e2af  test    eax, eax
0x18000e2b1  js      loc_18000E358
0x18000e2b7  mov     edx, [rsp+310h+var_2E0]
0x18000e2bb  mov     ecx, [rsp+310h+var_2C8]
0x18000e2bf  call    ?IsReadAccessAllowed@PROPERTY_ENTRY@@SAHKW4ACCESS_GRANTED@@@Z; PROPERTY_ENTRY::IsReadAccessAllowed(ulong,ACCESS_GRANTED)
0x18000e2c4  mov     rdi, [rsp+310h+var_2D8]
0x18000e2c9  test    eax, eax
0x18000e2cb  jnz     short loc_18000E2D7
0x18000e2cd  mov     ebx, 80070005h
0x18000e2d2  jmp     loc_18000E35D
0x18000e2d7  mov     r8d, [rbp+210h+arg_20]; unsigned int
0x18000e2de  lea     r9, [rsp+310h+var_2A8]; struct MULTISZ *
0x18000e2e3  mov     edx, ecx; unsigned int
0x18000e2e5  mov     [rsp+310h+var_2F0], r12; unsigned __int16 *
0x18000e2ea  mov     rcx, rdi; this
0x18000e2ed  call    ?GetDataPathsInternal@ABO_NODE@@AEAAJKKPEAVMULTISZ@@PEBG@Z; ABO_NODE::GetDataPathsInternal(ulong,ulong,MULTISZ *,ushort const *)
0x18000e2f2  mov     ebx, eax
0x18000e2f4  test    eax, eax
0x18000e2f6  js      short loc_18000E35D
0x18000e2f8  lea     rcx, [rsp+310h+var_2A8]
0x18000e2fd  call    cs:__imp_?QueryCCH@MULTISZ@@QEBAIXZ; MULTISZ::QueryCCH(void)
0x18000e303  cmp     eax, [rbp+210h+arg_28]
0x18000e309  jbe     short loc_18000E326
0x18000e30b  test    r13, r13
0x18000e30e  jz      short loc_18000E31F
0x18000e310  lea     rcx, [rsp+310h+var_2A8]
0x18000e315  call    cs:__imp_?QueryCCH@MULTISZ@@QEBAIXZ; MULTISZ::QueryCCH(void)
0x18000e31b  mov     [r13+0], eax
0x18000e31f  mov     ebx, 8007007Ah
0x18000e324  jmp     short loc_18000E35D
0x18000e326  mov     rdx, [rsp+310h+var_2B0]
0x18000e32b  lea     r8, [rbp+210h+arg_28]
0x18000e332  lea     rcx, [rsp+310h+var_2A8]
0x18000e337  call    cs:__imp_?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z; MULTISZ::CopyToBuffer(ushort *,ulong *)
0x18000e33d  test    eax, eax
0x18000e33f  jnz     short loc_18000E35D
0x18000e341  call    cs:__imp_GetLastError
0x18000e347  mov     ebx, eax
0x18000e349  test    eax, eax
0x18000e34b  jle     short loc_18000E35D
0x18000e34d  movzx   ebx, ax
0x18000e350  or      ebx, 80070000h
0x18000e356  jmp     short loc_18000E35D
0x18000e358  mov     rdi, [rsp+310h+var_2D8]
0x18000e35d  lea     rcx, [r15+20h]
0x18000e361  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000e367  cmp     [rsp+310h+var_2D0], 0
0x18000e36d  jz      short loc_18000E379
0x18000e36f  mov     rcx, [rsp+310h+var_2D0]; this
0x18000e374  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e379  test    rdi, rdi
0x18000e37c  jz      short loc_18000E386
0x18000e37e  mov     rcx, rdi; this
0x18000e381  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000e386  test    rsi, rsi
0x18000e389  jz      short loc_18000E393
0x18000e38b  mov     rcx, rsi; this
0x18000e38e  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000e393  mov     eax, 800CC801h
0x18000e398  lea     rcx, [rsp+310h+var_2A8]
0x18000e39d  cmp     ebx, 80070002h
0x18000e3a3  cmovz   ebx, eax
0x18000e3a6  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000e3ac  lea     rcx, [rbp+210h+var_270]
0x18000e3b0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e3b6  mov     eax, ebx
0x18000e3b8  mov     rcx, [rbp+210h+var_40]
0x18000e3bf  xor     rcx, rsp; StackCookie
0x18000e3c2  call    __security_check_cookie
0x18000e3c7  add     rsp, 2E0h
0x18000e3ce  pop     r15
0x18000e3d0  pop     r13
0x18000e3d2  pop     r12
0x18000e3d4  pop     rdi
0x18000e3d5  pop     rsi
0x18000e3d6  pop     rbx
0x18000e3d7  pop     rbp
0x18000e3d8  retn
```

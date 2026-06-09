# ABO_WRAPPER::GetChildPaths(ulong,ushort const *,ulong,ushort *,ulong *)

- ea: `0x18000db80`
- end: `0x18000ddd7`
- name: `?GetChildPaths@ABO_WRAPPER@@UEAAJKPEBGKPEAGPEAK@Z`
- size: `599`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000db80`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd47`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x18000dd3d`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x18000dd3d`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000dd0c`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000dd1b`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000dd0c`
- `iisutil!?QueryCCH@MULTISZ@@QEBAIXZ` at `0x18000dd1b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000dce3`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000dce3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd5f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dd5f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dc52`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000dc52`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000dbf1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000dbf1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ddae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ddae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dc78`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dcab`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dc78`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dcab`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000dc01`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000dc01`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000dcf1`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18000dcf1`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000dda4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18000dda4`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::GetChildPaths(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  struct ABO_TREE *v8; // r14
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v12; // rbx
  const unsigned __int16 *v13; // rax
  HANDLE_ENTRY *v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_NODE *v17; // [rsp+48h] [rbp-B8h] BYREF
  struct ABO_TREE *v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[56]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v21[248]; // [rsp+D0h] [rbp-30h] BYREF

  v18[1] = (struct ABO_TREE *)a5;
  v17 = 0;
  memset_0(v21, 0, 0x1EAu);
  STRU::STRU((STRU *)v20, v21, 0xF5u);
  v15 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v19);
  v8 = 0;
  v16 = 3;
  v18[0] = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v15);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v15, a3, (struct STRU *)v20);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, v18);
      v8 = v18[0];
      HandleEntry = CurrentAboTree;
      if ( CurrentAboTree >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v20);
        HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, v8, Str, 0, (enum ACCESS_GRANTED *)&v16);
        if ( HandleEntry >= 0 )
        {
          v12 = (ABO_NODE *)*((_QWORD *)v8 + 2);
          v13 = STRU::QueryStr((STRU *)v20);
          ABO_NODE::FindNode(v12, v13, &v17);
        }
      }
      CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    }
  }
  if ( v15 )
    HANDLE_ENTRY::DereferenceHandleEntry(v15);
  if ( v8 )
    HANDLE_ENTRY::DereferenceHandleEntry(v8);
  if ( HandleEntry == -2147024894 )
    HandleEntry = -2146646015;
  MULTISZ::~MULTISZ((MULTISZ *)v19);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000db80  push    rbp
0x18000db82  push    rbx
0x18000db83  push    rsi
0x18000db84  push    rdi
0x18000db85  push    r12
0x18000db87  push    r13
0x18000db89  push    r14
0x18000db8b  lea     rbp, [rsp-1D0h]
0x18000db93  sub     rsp, 2D0h
0x18000db9a  mov     rax, cs:__security_cookie
0x18000dba1  xor     rax, rsp
0x18000dba4  mov     [rbp+200h+var_40], rax
0x18000dbab  mov     rax, [rbp+200h+arg_20]
0x18000dbb2  mov     r12, r8
0x18000dbb5  mov     r13, [rbp+200h+arg_28]
0x18000dbbc  mov     ebx, edx
0x18000dbbe  mov     rsi, rcx
0x18000dbc1  mov     [rsp+300h+var_2A8], rax
0x18000dbc6  xor     edi, edi
0x18000dbc8  mov     [rsp+300h+var_2D0], r9d
0x18000dbcd  xor     edx, edx; Val
0x18000dbcf  mov     [rsp+300h+var_2B8], rdi
0x18000dbd4  mov     r8d, 1EAh; Size
0x18000dbda  lea     rcx, [rbp+200h+var_230]; void *
0x18000dbde  call    memset_0
0x18000dbe3  mov     r8d, 0F5h
0x18000dbe9  lea     rdx, [rbp+200h+var_230]
0x18000dbed  lea     rcx, [rbp+200h+var_268]
0x18000dbf1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000dbf7  lea     rcx, [rsp+300h+var_2A0]
0x18000dbfc  mov     [rsp+300h+var_2C8], rdi
0x18000dc01  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000dc07  xor     r14d, r14d
0x18000dc0a  mov     [rsp+300h+var_2C0], 3
0x18000dc12  lea     r8, [rsp+300h+var_2C8]; struct HANDLE_ENTRY **
0x18000dc17  mov     [rsp+300h+var_2B0], r14
0x18000dc1c  mov     edx, ebx; unsigned int
0x18000dc1e  mov     rcx, rsi; this
0x18000dc21  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000dc26  mov     ebx, eax
0x18000dc28  test    eax, eax
0x18000dc2a  js      loc_18000DD65
0x18000dc30  mov     rcx, [rsp+300h+var_2C8]; this
0x18000dc35  lea     r8, [rbp+200h+var_268]; struct STRU *
0x18000dc39  mov     rdx, r12; unsigned __int16 *
0x18000dc3c  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000dc41  mov     ebx, eax
0x18000dc43  test    eax, eax
0x18000dc45  js      loc_18000DD65
0x18000dc4b  lea     r12, [rsi+20h]
0x18000dc4f  mov     rcx, r12
0x18000dc52  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000dc58  lea     rdx, [rsp+300h+var_2B0]; struct ABO_TREE **
0x18000dc5d  mov     rcx, rsi; this
0x18000dc60  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000dc65  mov     r14, [rsp+300h+var_2B0]
0x18000dc6a  mov     ebx, eax
0x18000dc6c  test    eax, eax
0x18000dc6e  js      loc_18000DD5C
0x18000dc74  lea     rcx, [rbp+200h+var_268]
0x18000dc78  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000dc7e  lea     rcx, [rsp+300h+var_2C0]
0x18000dc83  xor     r9d, r9d
0x18000dc86  mov     [rsp+300h+var_2E0], rcx
0x18000dc8b  mov     r8, rax
0x18000dc8e  mov     rcx, rsi
0x18000dc91  mov     rdx, r14
0x18000dc94  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000dc99  mov     ebx, eax
0x18000dc9b  test    eax, eax
0x18000dc9d  js      loc_18000DD5C
0x18000dca3  mov     rbx, [r14+10h]
0x18000dca7  lea     rcx, [rbp+200h+var_268]
0x18000dcab  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000dcb1  lea     r8, [rsp+300h+var_2B8]; struct ABO_NODE **
0x18000dcb6  mov     rcx, rbx; this
0x18000dcb9  mov     rdx, rax; unsigned __int16 *
0x18000dcbc  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000dcc1  mov     rdi, [rsp+300h+var_2B8]
0x18000dcc6  mov     ebx, eax
0x18000dcc8  test    eax, eax
0x18000dcca  js      loc_18000DD5C
0x18000dcd0  xor     esi, esi
0x18000dcd2  cmp     [rdi+28h], esi
0x18000dcd5  jbe     short loc_18000DD02
0x18000dcd7  mov     rax, [rdi+20h]
0x18000dcdb  mov     rcx, [rax+rsi*8]
0x18000dcdf  add     rcx, 38h ; '8'
0x18000dce3  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000dce9  mov     rdx, rax
0x18000dcec  lea     rcx, [rsp+300h+var_2A0]
0x18000dcf1  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18000dcf7  test    eax, eax
0x18000dcf9  jz      short loc_18000DD47
0x18000dcfb  inc     esi
0x18000dcfd  cmp     esi, [rdi+28h]
0x18000dd00  jb      short loc_18000DCD7
0x18000dd02  test    r13, r13
0x18000dd05  jz      short loc_18000DD16
0x18000dd07  lea     rcx, [rsp+300h+var_2A0]
0x18000dd0c  call    cs:__imp_?QueryCCH@MULTISZ@@QEBAIXZ; MULTISZ::QueryCCH(void)
0x18000dd12  mov     [r13+0], eax
0x18000dd16  lea     rcx, [rsp+300h+var_2A0]
0x18000dd1b  call    cs:__imp_?QueryCCH@MULTISZ@@QEBAIXZ; MULTISZ::QueryCCH(void)
0x18000dd21  cmp     eax, [rsp+300h+var_2D0]
0x18000dd25  jbe     short loc_18000DD2E
0x18000dd27  mov     ebx, 8007007Ah
0x18000dd2c  jmp     short loc_18000DD5C
0x18000dd2e  mov     rdx, [rsp+300h+var_2A8]
0x18000dd33  lea     r8, [rsp+300h+var_2D0]
0x18000dd38  lea     rcx, [rsp+300h+var_2A0]
0x18000dd3d  call    cs:__imp_?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z; MULTISZ::CopyToBuffer(ushort *,ulong *)
0x18000dd43  test    eax, eax
0x18000dd45  jnz     short loc_18000DD5C
0x18000dd47  call    cs:__imp_GetLastError
0x18000dd4d  mov     ebx, eax
0x18000dd4f  test    eax, eax
0x18000dd51  jle     short loc_18000DD5C
0x18000dd53  movzx   ebx, ax
0x18000dd56  or      ebx, 80070000h
0x18000dd5c  mov     rcx, r12
0x18000dd5f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000dd65  cmp     [rsp+300h+var_2C8], 0
0x18000dd6b  jz      short loc_18000DD77
0x18000dd6d  mov     rcx, [rsp+300h+var_2C8]; this
0x18000dd72  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000dd77  test    rdi, rdi
0x18000dd7a  jz      short loc_18000DD84
0x18000dd7c  mov     rcx, rdi; this
0x18000dd7f  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000dd84  test    r14, r14
0x18000dd87  jz      short loc_18000DD91
0x18000dd89  mov     rcx, r14; this
0x18000dd8c  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000dd91  mov     eax, 800CC801h
0x18000dd96  lea     rcx, [rsp+300h+var_2A0]
0x18000dd9b  cmp     ebx, 80070002h
0x18000dda1  cmovz   ebx, eax
0x18000dda4  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000ddaa  lea     rcx, [rbp+200h+var_268]
0x18000ddae  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ddb4  mov     eax, ebx
0x18000ddb6  mov     rcx, [rbp+200h+var_40]
0x18000ddbd  xor     rcx, rsp; StackCookie
0x18000ddc0  call    __security_check_cookie
0x18000ddc5  add     rsp, 2D0h
0x18000ddcc  pop     r14
0x18000ddce  pop     r13
0x18000ddd0  pop     r12
0x18000ddd2  pop     rdi
0x18000ddd3  pop     rsi
0x18000ddd4  pop     rbx
0x18000ddd5  pop     rbp
0x18000ddd6  retn
```

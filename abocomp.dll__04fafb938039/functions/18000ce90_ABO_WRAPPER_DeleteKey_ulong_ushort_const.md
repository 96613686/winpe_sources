# ABO_WRAPPER::DeleteKey(ulong,ushort const *)

- ea: `0x18000ce90`
- end: `0x18000d039`
- name: `?DeleteKey@ABO_WRAPPER@@UEAAJKPEBG@Z`
- size: `425`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007530`
- `0x180007ac8`
- `0x18000b68c`
- `0x18000ce90`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfc6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfc6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cf36`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cf36`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ceeb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ceeb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d00b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d00b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cf59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cf85`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cf59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cf85`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::DeleteKey(ABO_WRAPPER *this, unsigned int a2, const unsigned __int16 *a3)
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
  if ( HandleEntry == -2147024894 )
    HandleEntry = -2146646015;
  STRU::~STRU((STRU *)v16);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000ce90  mov     [rsp-8+arg_18], rbx
0x18000ce95  push    rbp
0x18000ce96  push    rsi
0x18000ce97  push    rdi
0x18000ce98  push    r12
0x18000ce9a  push    r15
0x18000ce9c  lea     rbp, [rsp-180h]
0x18000cea4  sub     rsp, 280h
0x18000ceab  mov     rax, cs:__security_cookie
0x18000ceb2  xor     rax, rsp
0x18000ceb5  mov     [rbp+1A0h+var_30], rax
0x18000cebc  mov     r12, r8
0x18000cebf  mov     ebx, edx
0x18000cec1  mov     r15, rcx
0x18000cec4  xor     edi, edi
0x18000cec6  xor     edx, edx; Val
0x18000cec8  mov     [rsp+2A0h+var_268], rdi
0x18000cecd  mov     r8d, 1EAh; Size
0x18000ced3  lea     rcx, [rbp+1A0h+var_220]; void *
0x18000ced7  call    memset_0
0x18000cedc  mov     r8d, 0F5h
0x18000cee2  lea     rdx, [rbp+1A0h+var_220]
0x18000cee6  lea     rcx, [rsp+2A0h+var_258]
0x18000ceeb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000cef1  xor     esi, esi
0x18000cef3  mov     [rsp+2A0h+var_270], rdi
0x18000cef8  lea     r8, [rsp+2A0h+var_270]; struct HANDLE_ENTRY **
0x18000cefd  mov     [rsp+2A0h+var_260], rsi
0x18000cf02  mov     edx, ebx; unsigned int
0x18000cf04  mov     rcx, r15; this
0x18000cf07  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000cf0c  mov     ebx, eax
0x18000cf0e  test    eax, eax
0x18000cf10  js      loc_18000CFCC
0x18000cf16  mov     rcx, [rsp+2A0h+var_270]; this
0x18000cf1b  lea     r8, [rsp+2A0h+var_258]; struct STRU *
0x18000cf20  mov     rdx, r12; unsigned __int16 *
0x18000cf23  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000cf28  mov     ebx, eax
0x18000cf2a  test    eax, eax
0x18000cf2c  js      loc_18000CFCC
0x18000cf32  lea     rcx, [r15+20h]
0x18000cf36  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000cf3c  lea     rdx, [rsp+2A0h+var_260]; struct ABO_TREE **
0x18000cf41  mov     rcx, r15; this
0x18000cf44  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000cf49  mov     rsi, [rsp+2A0h+var_260]
0x18000cf4e  mov     ebx, eax
0x18000cf50  test    eax, eax
0x18000cf52  js      short loc_18000CFC2
0x18000cf54  lea     rcx, [rsp+2A0h+var_258]
0x18000cf59  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cf5f  lea     r9d, [rdi+1]
0x18000cf63  mov     [rsp+2A0h+var_280], rdi
0x18000cf68  mov     r8, rax
0x18000cf6b  mov     rdx, rsi
0x18000cf6e  mov     rcx, r15
0x18000cf71  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000cf76  mov     ebx, eax
0x18000cf78  test    eax, eax
0x18000cf7a  js      short loc_18000CFC2
0x18000cf7c  mov     rbx, [rsi+10h]
0x18000cf80  lea     rcx, [rsp+2A0h+var_258]
0x18000cf85  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cf8b  lea     r8, [rsp+2A0h+var_268]; struct ABO_NODE **
0x18000cf90  mov     rcx, rbx; this
0x18000cf93  mov     rdx, rax; unsigned __int16 *
0x18000cf96  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000cf9b  mov     rdi, [rsp+2A0h+var_268]
0x18000cfa0  mov     ebx, eax
0x18000cfa2  test    eax, eax
0x18000cfa4  js      short loc_18000CFC2
0x18000cfa6  mov     rcx, [rdi+10h]; this
0x18000cfaa  mov     rdx, rdi; struct ABO_NODE *
0x18000cfad  call    ?DeleteChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::DeleteChildNode(ABO_NODE *)
0x18000cfb2  mov     ebx, eax
0x18000cfb4  test    eax, eax
0x18000cfb6  js      short loc_18000CFC2
0x18000cfb8  mov     rcx, [rsp+2A0h+var_270]; this
0x18000cfbd  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000cfc2  lea     rcx, [r15+20h]
0x18000cfc6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000cfcc  cmp     [rsp+2A0h+var_270], 0
0x18000cfd2  jz      short loc_18000CFDE
0x18000cfd4  mov     rcx, [rsp+2A0h+var_270]; this
0x18000cfd9  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cfde  test    rdi, rdi
0x18000cfe1  jz      short loc_18000CFEB
0x18000cfe3  mov     rcx, rdi; this
0x18000cfe6  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000cfeb  test    rsi, rsi
0x18000cfee  jz      short loc_18000CFF8
0x18000cff0  mov     rcx, rsi; this
0x18000cff3  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000cff8  cmp     ebx, 80070002h
0x18000cffe  lea     rcx, [rsp+2A0h+var_258]
0x18000d003  mov     eax, 800CC801h
0x18000d008  cmovz   ebx, eax
0x18000d00b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d011  mov     eax, ebx
0x18000d013  mov     rcx, [rbp+1A0h+var_30]
0x18000d01a  xor     rcx, rsp; StackCookie
0x18000d01d  call    __security_check_cookie
0x18000d022  mov     rbx, [rsp+2A0h+arg_18]
0x18000d02a  add     rsp, 280h
0x18000d031  pop     r15
0x18000d033  pop     r12
0x18000d035  pop     rdi
0x18000d036  pop     rsi
0x18000d037  pop     rbp
0x18000d038  retn
```

# ABO_WRAPPER::AddKey(ulong,ushort const *)

- ea: `0x18000b3c0`
- end: `0x18000b546`
- name: `?AddKey@ABO_WRAPPER@@UEAAJKPEBG@Z`
- size: `390`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x180007148`
- `0x18000b3c0`
- `0x18000b68c`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b4f6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b4f6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b46e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b46e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b410`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b410`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b520`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b520`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b491`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b4c3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b491`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b4c3`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::AddKey(ABO_WRAPPER *this, unsigned int a2, const unsigned __int16 *a3)
{
  struct ABO_TREE *v6; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  struct ABO_TREE **v10; // rbx
  const unsigned __int16 *v11; // rax
  int v12; // edx
  HANDLE_ENTRY *v14; // [rsp+30h] [rbp-D0h] BYREF
  struct ABO_TREE *v15; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v17[248]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v17, 0, 0x1EAu);
  STRU::STRU((STRU *)v16, v17, 0xF5u);
  v6 = 0;
  v14 = 0;
  v15 = 0;
  if ( a3 )
  {
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v14);
    if ( HandleEntry >= 0 )
    {
      HandleEntry = HANDLE_ENTRY::GetFullPath(v14, a3, (struct STRU *)v16);
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
            v10 = (struct ABO_TREE **)*((_QWORD *)v6 + 2);
            v11 = STRU::QueryStr((STRU *)v16);
            HandleEntry = ABO_NODE::CreateNode(v10, v11, 0, 0, 1);
            if ( HandleEntry >= 0 )
              HANDLE_ENTRY::SetDirty(v14, v12);
          }
        }
        CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
      }
    }
    if ( v14 )
      HANDLE_ENTRY::DereferenceHandleEntry(v14);
    if ( v6 )
      HANDLE_ENTRY::DereferenceHandleEntry(v6);
  }
  else
  {
    HandleEntry = -2147024809;
  }
  STRU::~STRU((STRU *)v16);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000b3c0  push    rbp
0x18000b3c2  push    rbx
0x18000b3c3  push    rsi
0x18000b3c4  push    r14
0x18000b3c6  push    r15
0x18000b3c8  lea     rbp, [rsp-180h]
0x18000b3d0  sub     rsp, 280h
0x18000b3d7  mov     rax, cs:__security_cookie
0x18000b3de  xor     rax, rsp
0x18000b3e1  mov     [rbp+1A0h+var_30], rax
0x18000b3e8  mov     r15, r8
0x18000b3eb  mov     ebx, edx
0x18000b3ed  mov     r14, rcx
0x18000b3f0  xor     edx, edx; Val
0x18000b3f2  mov     r8d, 1EAh; Size
0x18000b3f8  lea     rcx, [rbp+1A0h+var_220]; void *
0x18000b3fc  call    memset_0
0x18000b401  mov     r8d, 0F5h
0x18000b407  lea     rdx, [rbp+1A0h+var_220]
0x18000b40b  lea     rcx, [rsp+2A0h+var_260]
0x18000b410  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000b416  xor     esi, esi
0x18000b418  mov     [rsp+2A0h+var_270], 0
0x18000b421  mov     [rsp+2A0h+var_268], rsi
0x18000b426  test    r15, r15
0x18000b429  jnz     short loc_18000B435
0x18000b42b  mov     ebx, 80070057h
0x18000b430  jmp     loc_18000B51B
0x18000b435  lea     r8, [rsp+2A0h+var_270]; struct HANDLE_ENTRY **
0x18000b43a  mov     edx, ebx; unsigned int
0x18000b43c  mov     rcx, r14; this
0x18000b43f  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000b444  mov     ebx, eax
0x18000b446  test    eax, eax
0x18000b448  js      loc_18000B4FC
0x18000b44e  mov     rcx, [rsp+2A0h+var_270]; this
0x18000b453  lea     r8, [rsp+2A0h+var_260]; struct STRU *
0x18000b458  mov     rdx, r15; unsigned __int16 *
0x18000b45b  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000b460  mov     ebx, eax
0x18000b462  test    eax, eax
0x18000b464  js      loc_18000B4FC
0x18000b46a  lea     rcx, [r14+20h]
0x18000b46e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b474  lea     rdx, [rsp+2A0h+var_268]; struct ABO_TREE **
0x18000b479  mov     rcx, r14; this
0x18000b47c  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000b481  mov     rsi, [rsp+2A0h+var_268]
0x18000b486  mov     ebx, eax
0x18000b488  test    eax, eax
0x18000b48a  js      short loc_18000B4F2
0x18000b48c  lea     rcx, [rsp+2A0h+var_260]
0x18000b491  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b497  mov     r9d, 1
0x18000b49d  mov     qword ptr [rsp+2A0h+var_280], 0
0x18000b4a6  mov     r8, rax
0x18000b4a9  mov     rdx, rsi
0x18000b4ac  mov     rcx, r14
0x18000b4af  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000b4b4  mov     ebx, eax
0x18000b4b6  test    eax, eax
0x18000b4b8  js      short loc_18000B4F2
0x18000b4ba  mov     rbx, [rsi+10h]
0x18000b4be  lea     rcx, [rsp+2A0h+var_260]
0x18000b4c3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b4c9  xor     r9d, r9d; struct ABO_NODE **
0x18000b4cc  mov     [rsp+2A0h+var_280], 1; int
0x18000b4d4  mov     rdx, rax; unsigned __int16 *
0x18000b4d7  xor     r8d, r8d; int
0x18000b4da  mov     rcx, rbx; this
0x18000b4dd  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x18000b4e2  mov     ebx, eax
0x18000b4e4  test    eax, eax
0x18000b4e6  js      short loc_18000B4F2
0x18000b4e8  mov     rcx, [rsp+2A0h+var_270]; this
0x18000b4ed  call    ?SetDirty@HANDLE_ENTRY@@QEAAXH@Z; HANDLE_ENTRY::SetDirty(int)
0x18000b4f2  lea     rcx, [r14+20h]
0x18000b4f6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b4fc  cmp     [rsp+2A0h+var_270], 0
0x18000b502  jz      short loc_18000B50E
0x18000b504  mov     rcx, [rsp+2A0h+var_270]; this
0x18000b509  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000b50e  test    rsi, rsi
0x18000b511  jz      short loc_18000B51B
0x18000b513  mov     rcx, rsi; this
0x18000b516  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000b51b  lea     rcx, [rsp+2A0h+var_260]
0x18000b520  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b526  mov     eax, ebx
0x18000b528  mov     rcx, [rbp+1A0h+var_30]
0x18000b52f  xor     rcx, rsp; StackCookie
0x18000b532  call    __security_check_cookie
0x18000b537  add     rsp, 280h
0x18000b53e  pop     r15
0x18000b540  pop     r14
0x18000b542  pop     rsi
0x18000b543  pop     rbx
0x18000b544  pop     rbp
0x18000b545  retn
```

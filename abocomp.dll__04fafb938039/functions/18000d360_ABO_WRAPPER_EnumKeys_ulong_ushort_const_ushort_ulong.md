# ABO_WRAPPER::EnumKeys(ulong,ushort const *,ushort *,ulong)

- ea: `0x18000d360`
- end: `0x18000d53b`
- name: `?EnumKeys@ABO_WRAPPER@@UEAAJKPEBGPEAGK@Z`
- size: `475`
- prototype: `__int64 __usercall@<rax>(ABO_WRAPPER *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int)`
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
- `0x18000d360`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000d4c8`
- `msvcrt!wcsncpy_s` at `0x18000d4c8`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000d4ad`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000d4ad`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d4db`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d4db`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d41c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d41c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d3c6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d3c6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d512`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d512`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d443`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d473`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d443`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d473`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::EnumKeys(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct ABO_TREE *a4)
{
  struct ABO_TREE *v7; // rsi
  int HandleEntry; // ebx
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v11; // rbx
  const unsigned __int16 *v12; // rax
  HANDLE_ENTRY *v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  struct ABO_NODE *v16; // [rsp+40h] [rbp-C0h] BYREF
  struct ABO_TREE *v17[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[248]; // [rsp+90h] [rbp-70h] BYREF

  v17[1] = a4;
  v16 = 0;
  memset_0(v19, 0, 0x1EAu);
  STRU::STRU((STRU *)v18, v19, 0xF5u);
  v7 = 0;
  v14 = 0;
  v17[0] = 0;
  v15 = 3;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v14);
  if ( HandleEntry >= 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v14, a3, (struct STRU *)v18);
    if ( HandleEntry >= 0 )
    {
      CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
      CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, v17);
      v7 = v17[0];
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
0x18000d360  push    rbp
0x18000d362  push    rbx
0x18000d363  push    rsi
0x18000d364  push    rdi
0x18000d365  push    r12
0x18000d367  push    r13
0x18000d369  push    r15
0x18000d36b  lea     rbp, [rsp-190h]
0x18000d373  sub     rsp, 290h
0x18000d37a  mov     rax, cs:__security_cookie
0x18000d381  xor     rax, rsp
0x18000d384  mov     [rbp+1C0h+var_40], rax
0x18000d38b  mov     r13d, [rbp+1C0h+arg_20]
0x18000d392  mov     r12, r8
0x18000d395  mov     ebx, edx
0x18000d397  mov     [rsp+2C0h+Destination], r9
0x18000d39c  mov     r15, rcx
0x18000d39f  xor     edi, edi
0x18000d3a1  xor     edx, edx; Val
0x18000d3a3  mov     [rsp+2C0h+var_280], rdi
0x18000d3a8  mov     r8d, 1EAh; Size
0x18000d3ae  lea     rcx, [rbp+1C0h+var_230]; void *
0x18000d3b2  call    memset_0
0x18000d3b7  mov     r8d, 0F5h
0x18000d3bd  lea     rdx, [rbp+1C0h+var_230]
0x18000d3c1  lea     rcx, [rsp+2C0h+var_268]
0x18000d3c6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d3cc  xor     esi, esi
0x18000d3ce  mov     [rsp+2C0h+var_290], rdi
0x18000d3d3  lea     r8, [rsp+2C0h+var_290]; struct HANDLE_ENTRY **
0x18000d3d8  mov     [rsp+2C0h+var_278], rsi
0x18000d3dd  mov     edx, ebx; unsigned int
0x18000d3df  mov     [rsp+2C0h+var_288], 3
0x18000d3e7  mov     rcx, r15; this
0x18000d3ea  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000d3ef  mov     ebx, eax
0x18000d3f1  test    eax, eax
0x18000d3f3  js      loc_18000D4E1
0x18000d3f9  mov     rcx, [rsp+2C0h+var_290]; this
0x18000d3fe  lea     r8, [rsp+2C0h+var_268]; struct STRU *
0x18000d403  mov     rdx, r12; unsigned __int16 *
0x18000d406  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000d40b  mov     ebx, eax
0x18000d40d  test    eax, eax
0x18000d40f  js      loc_18000D4E1
0x18000d415  lea     r12, [r15+20h]
0x18000d419  mov     rcx, r12
0x18000d41c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d422  lea     rdx, [rsp+2C0h+var_278]; struct ABO_TREE **
0x18000d427  mov     rcx, r15; this
0x18000d42a  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000d42f  mov     rsi, [rsp+2C0h+var_278]
0x18000d434  mov     ebx, eax
0x18000d436  test    eax, eax
0x18000d438  js      loc_18000D4D8
0x18000d43e  lea     rcx, [rsp+2C0h+var_268]
0x18000d443  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d449  lea     rcx, [rsp+2C0h+var_288]
0x18000d44e  xor     r9d, r9d
0x18000d451  mov     [rsp+2C0h+var_2A0], rcx
0x18000d456  mov     r8, rax
0x18000d459  mov     rcx, r15
0x18000d45c  mov     rdx, rsi
0x18000d45f  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000d464  mov     ebx, eax
0x18000d466  test    eax, eax
0x18000d468  js      short loc_18000D4D8
0x18000d46a  mov     rbx, [rsi+10h]
0x18000d46e  lea     rcx, [rsp+2C0h+var_268]
0x18000d473  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d479  lea     r8, [rsp+2C0h+var_280]; struct ABO_NODE **
0x18000d47e  mov     rcx, rbx; this
0x18000d481  mov     rdx, rax; unsigned __int16 *
0x18000d484  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000d489  mov     rdi, [rsp+2C0h+var_280]
0x18000d48e  mov     ebx, eax
0x18000d490  test    eax, eax
0x18000d492  js      short loc_18000D4D8
0x18000d494  cmp     r13d, [rdi+28h]
0x18000d498  jb      short loc_18000D4A1
0x18000d49a  mov     ebx, 80070103h
0x18000d49f  jmp     short loc_18000D4D8
0x18000d4a1  mov     rax, [rdi+20h]
0x18000d4a5  mov     rcx, [rax+r13*8]
0x18000d4a9  add     rcx, 38h ; '8'
0x18000d4ad  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000d4b3  mov     r15, [rsp+2C0h+Destination]
0x18000d4b8  mov     r9d, 0FFh; MaxCount
0x18000d4be  mov     r8, rax; Source
0x18000d4c1  mov     rcx, r15; Destination
0x18000d4c4  lea     edx, [r9+1]; SizeInWords
0x18000d4c8  call    cs:__imp_wcsncpy_s
0x18000d4ce  xor     eax, eax
0x18000d4d0  mov     [r15+1FEh], ax
0x18000d4d8  mov     rcx, r12
0x18000d4db  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d4e1  cmp     [rsp+2C0h+var_290], 0
0x18000d4e7  jz      short loc_18000D4F3
0x18000d4e9  mov     rcx, [rsp+2C0h+var_290]; this
0x18000d4ee  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d4f3  test    rdi, rdi
0x18000d4f6  jz      short loc_18000D500
0x18000d4f8  mov     rcx, rdi; this
0x18000d4fb  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000d500  test    rsi, rsi
0x18000d503  jz      short loc_18000D50D
0x18000d505  mov     rcx, rsi; this
0x18000d508  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000d50d  lea     rcx, [rsp+2C0h+var_268]
0x18000d512  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d518  mov     eax, ebx
0x18000d51a  mov     rcx, [rbp+1C0h+var_40]
0x18000d521  xor     rcx, rsp; StackCookie
0x18000d524  call    __security_check_cookie
0x18000d529  add     rsp, 290h
0x18000d530  pop     r15
0x18000d532  pop     r13
0x18000d534  pop     r12
0x18000d536  pop     rdi
0x18000d537  pop     rsi
0x18000d538  pop     rbx
0x18000d539  pop     rbp
0x18000d53a  retn
```

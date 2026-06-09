# ABO_WRAPPER::OpenKey(ulong,ushort const *,ulong,ulong,ulong *)

- ea: `0x18000ed00`
- end: `0x18000ef18`
- name: `?OpenKey@ABO_WRAPPER@@UEAAJKPEBGKKPEAK@Z`
- size: `536`
- prototype: `__int64 __fastcall(ABO_WRAPPER *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x180007ac8`
- `0x18000b0b4`
- `0x18000c944`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000ed00`
- `0x18000f6dc`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000edcb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000edcb`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000ee52`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000ee52`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ee71`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000eea3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ee71`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000eea3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ee2c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ee2c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ed6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000ed6b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000eeed`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000eeed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ee0a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ee0a`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000ee81`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000ee81`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::OpenKey(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  HANDLE_ENTRY *v9; // rsi
  HANDLE_ENTRY *v11; // r15
  HANDLE_ENTRY *v12; // rdi
  int HandleEntry; // eax
  int FullPath; // ebx
  HANDLE_ENTRY *v15; // rax
  const unsigned __int16 *Str; // rax
  int CurrentAboTree; // eax
  ABO_NODE *v18; // rbx
  const unsigned __int16 *v19; // rax
  HANDLE_ENTRY *v21; // [rsp+20h] [rbp-E0h] BYREF
  struct ABO_TREE *v22; // [rsp+28h] [rbp-D8h] BYREF
  ABO_NODE *v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v25[256]; // [rsp+80h] [rbp-80h] BYREF

  v23[1] = (ABO_NODE *)a6;
  v9 = 0;
  v21 = 0;
  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v24, v25, 0x100u);
  v11 = 0;
  v23[0] = 0;
  v22 = 0;
  if ( a2 )
  {
    v12 = 0;
    HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a2, &v21);
    v9 = v21;
    FullPath = HandleEntry;
    if ( HandleEntry < 0 )
      goto LABEL_16;
    FullPath = HANDLE_ENTRY::GetFullPath(v21, a3, (struct STRU *)v24);
    if ( FullPath < 0 )
      goto LABEL_16;
  }
  else if ( a3 )
  {
    FullPath = STRU::Copy((STRU *)v24, a3);
    if ( FullPath < 0 )
      goto LABEL_22;
  }
  v15 = (HANDLE_ENTRY *)operator new(0x50u);
  if ( v15 )
  {
    v12 = HANDLE_ENTRY::HANDLE_ENTRY(v15, a4);
    if ( v12 )
    {
      Str = STRU::QueryStr((STRU *)v24);
      FullPath = HANDLE_ENTRY::Create(v12, Str);
      if ( FullPath >= 0 )
      {
        CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
        CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v22);
        v11 = v22;
        FullPath = CurrentAboTree;
        if ( CurrentAboTree >= 0 )
        {
          v18 = (ABO_NODE *)*((_QWORD *)v22 + 2);
          v19 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v12 + 16));
          ABO_NODE::FindNode(v18, v19, v23);
        }
        CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
        if ( v23[0] )
          ABO_NODE::DereferenceAboNode(v23[0]);
      }
      goto LABEL_16;
    }
  }
  else
  {
    v12 = 0;
  }
  FullPath = -2147024888;
LABEL_16:
  if ( v9 )
    HANDLE_ENTRY::DereferenceHandleEntry(v9);
  if ( v12 )
    HANDLE_ENTRY::DereferenceHandleEntry(v12);
  if ( v11 )
    HANDLE_ENTRY::DereferenceHandleEntry(v11);
LABEL_22:
  STRU::~STRU((STRU *)v24);
  return (unsigned int)FullPath;
}

```

## disassembly

```asm
0x18000ed00  push    rbp
0x18000ed02  push    rbx
0x18000ed03  push    rsi
0x18000ed04  push    rdi
0x18000ed05  push    r12
0x18000ed07  push    r13
0x18000ed09  push    r14
0x18000ed0b  push    r15
0x18000ed0d  lea     rbp, [rsp-198h]
0x18000ed15  sub     rsp, 298h
0x18000ed1c  mov     rax, cs:__security_cookie
0x18000ed23  xor     rax, rsp
0x18000ed26  mov     [rbp+1D0h+var_50], rax
0x18000ed2d  mov     rax, [rbp+1D0h+arg_28]
0x18000ed34  mov     r14, r8
0x18000ed37  mov     ebx, edx
0x18000ed39  mov     [rsp+2D0h+var_298], rax
0x18000ed3e  mov     r13, rcx
0x18000ed41  xor     esi, esi
0x18000ed43  xor     edx, edx; Val
0x18000ed45  mov     [rsp+2D0h+var_2B0], rsi
0x18000ed4a  mov     r8d, 200h; Size
0x18000ed50  lea     rcx, [rbp+1D0h+var_250]; void *
0x18000ed54  mov     r12d, r9d
0x18000ed57  call    memset_0
0x18000ed5c  mov     r8d, 100h
0x18000ed62  lea     rdx, [rbp+1D0h+var_250]
0x18000ed66  lea     rcx, [rsp+2D0h+var_290]
0x18000ed6b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000ed71  xor     r15d, r15d
0x18000ed74  mov     [rsp+2D0h+var_2A0], rsi
0x18000ed79  mov     [rsp+2D0h+var_2A8], r15
0x18000ed7e  test    ebx, ebx
0x18000ed80  jz      short loc_18000EDBE
0x18000ed82  lea     r8, [rsp+2D0h+var_2B0]; struct HANDLE_ENTRY **
0x18000ed87  mov     edx, ebx; unsigned int
0x18000ed89  mov     rcx, r13; this
0x18000ed8c  xor     edi, edi
0x18000ed8e  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000ed93  mov     rsi, [rsp+2D0h+var_2B0]
0x18000ed98  mov     ebx, eax
0x18000ed9a  test    eax, eax
0x18000ed9c  js      loc_18000EEC1
0x18000eda2  lea     r8, [rsp+2D0h+var_290]; struct STRU *
0x18000eda7  mov     rdx, r14; unsigned __int16 *
0x18000edaa  mov     rcx, rsi; this
0x18000edad  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000edb2  mov     ebx, eax
0x18000edb4  test    eax, eax
0x18000edb6  js      loc_18000EEC1
0x18000edbc  jmp     short loc_18000EDDB
0x18000edbe  test    r14, r14
0x18000edc1  jz      short loc_18000EDDB
0x18000edc3  mov     rdx, r14
0x18000edc6  lea     rcx, [rsp+2D0h+var_290]
0x18000edcb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000edd1  mov     ebx, eax
0x18000edd3  test    eax, eax
0x18000edd5  js      loc_18000EEE8
0x18000eddb  mov     ecx, 50h ; 'P'; Size
0x18000ede0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ede5  test    rax, rax
0x18000ede8  jz      loc_18000EEBA
0x18000edee  mov     edx, r12d; unsigned int
0x18000edf1  mov     rcx, rax; this
0x18000edf4  call    ??0HANDLE_ENTRY@@QEAA@K@Z; HANDLE_ENTRY::HANDLE_ENTRY(ulong)
0x18000edf9  mov     rdi, rax
0x18000edfc  test    rax, rax
0x18000edff  jz      loc_18000EEBC
0x18000ee05  lea     rcx, [rsp+2D0h+var_290]
0x18000ee0a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ee10  mov     rdx, rax; unsigned __int16 *
0x18000ee13  mov     rcx, rdi; this
0x18000ee16  call    ?Create@HANDLE_ENTRY@@QEAAJPEBG@Z; HANDLE_ENTRY::Create(ushort const *)
0x18000ee1b  mov     ebx, eax
0x18000ee1d  test    eax, eax
0x18000ee1f  js      loc_18000EEC1
0x18000ee25  lea     r14, [r13+20h]
0x18000ee29  mov     rcx, r14
0x18000ee2c  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ee32  lea     rdx, [rsp+2D0h+var_2A8]; struct ABO_TREE **
0x18000ee37  mov     rcx, r13; this
0x18000ee3a  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000ee3f  mov     r15, [rsp+2D0h+var_2A8]
0x18000ee44  mov     ebx, eax
0x18000ee46  test    eax, eax
0x18000ee48  js      short loc_18000EEA0
0x18000ee4a  mov     rbx, [r15+10h]
0x18000ee4e  lea     rcx, [rdi+10h]
0x18000ee52  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18000ee58  lea     r8, [rsp+2D0h+var_2A0]; struct ABO_NODE **
0x18000ee5d  mov     rcx, rbx; this
0x18000ee60  mov     rdx, rax; unsigned __int16 *
0x18000ee63  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000ee68  mov     ebx, eax
0x18000ee6a  test    eax, eax
0x18000ee6c  js      short loc_18000EEA0
0x18000ee6e  mov     rcx, r14
0x18000ee71  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ee77  lea     rcx, [r13+30h]
0x18000ee7b  xor     r8d, r8d
0x18000ee7e  mov     rdx, rdi
0x18000ee81  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000ee87  test    eax, eax
0x18000ee89  jz      short loc_18000EE92
0x18000ee8b  mov     ebx, 800700B7h
0x18000ee90  jmp     short loc_18000EEA9
0x18000ee92  mov     rcx, [rsp+2D0h+var_298]
0x18000ee97  xor     ebx, ebx
0x18000ee99  mov     eax, [rdi+0Ch]
0x18000ee9c  mov     [rcx], eax
0x18000ee9e  jmp     short loc_18000EEA9
0x18000eea0  mov     rcx, r14
0x18000eea3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000eea9  mov     rcx, [rsp+2D0h+var_2A0]; this
0x18000eeae  test    rcx, rcx
0x18000eeb1  jz      short loc_18000EEC1
0x18000eeb3  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000eeb8  jmp     short loc_18000EEC1
0x18000eeba  xor     edi, edi
0x18000eebc  mov     ebx, 80070008h
0x18000eec1  test    rsi, rsi
0x18000eec4  jz      short loc_18000EECE
0x18000eec6  mov     rcx, rsi; this
0x18000eec9  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000eece  test    rdi, rdi
0x18000eed1  jz      short loc_18000EEDB
0x18000eed3  mov     rcx, rdi; this
0x18000eed6  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000eedb  test    r15, r15
0x18000eede  jz      short loc_18000EEE8
0x18000eee0  mov     rcx, r15; this
0x18000eee3  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000eee8  lea     rcx, [rsp+2D0h+var_290]
0x18000eeed  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000eef3  mov     eax, ebx
0x18000eef5  mov     rcx, [rbp+1D0h+var_50]
0x18000eefc  xor     rcx, rsp; StackCookie
0x18000eeff  call    __security_check_cookie
0x18000ef04  add     rsp, 298h
0x18000ef0b  pop     r15
0x18000ef0d  pop     r14
0x18000ef0f  pop     r13
0x18000ef11  pop     r12
0x18000ef13  pop     rdi
0x18000ef14  pop     rsi
0x18000ef15  pop     rbx
0x18000ef16  pop     rbp
0x18000ef17  retn
```

# ABO_WRAPPER::CopyData(ulong,ushort const *,ulong,ushort const *,ulong,ulong,ulong,int)

- ea: `0x18000bf00`
- end: `0x18000c553`
- name: `?CopyData@ABO_WRAPPER@@UEAAJKPEBGK0KKKH@Z`
- size: `1619`
- prototype: `__int64 __fastcall(ABO_WRAPPER *this, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x18000473c`
- `0x18000672c`
- `0x180007148`
- `0x180007ac8`
- `0x18000a6fc`
- `0x18000b0b4`
- `0x18000b68c`
- `0x18000bf00`
- `0x18000c944`
- `0x18000cd68`
- `0x18000d8f0`
- `0x18000dde0`
- `0x18000e5d4`
- `0x18000f6dc`
- `0x18000f820`
- `0x18000fab8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2ce`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000c2c4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000c2c4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000c28c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000c2fd`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000c28c`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000c2fd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c27f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c2f0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c346`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c463`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c27f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c2f0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c346`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c463`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1d3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c1d3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c104`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c104`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bf7b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bfa0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bfc5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bf7b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bfa0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bfc5`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c50a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c50a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c514`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c51e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c528`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c514`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c51e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c528`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c128`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c37d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c405`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c434`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c128`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c37d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c405`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000c434`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000c1b6`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000c1b6`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bfcf`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000bfcf`

## string_xrefs

- `0x18000c0ad`: `Failed to Close dummy key used during CopyData\n`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CopyData(
        ABO_WRAPPER *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  HANDLE_ENTRY *v11; // r12
  ABO_NODE **v13; // r14
  unsigned int *v14; // rdi
  int HandleEntry; // ebx
  HANDLE_ENTRY *v16; // r15
  int CurrentAboTree; // eax
  const unsigned __int16 *Str; // rax
  HANDLE_ENTRY *v19; // rax
  HANDLE_ENTRY *v20; // rax
  unsigned __int8 *Ptr; // rbx
  unsigned int Size; // eax
  signed int LastError; // eax
  unsigned __int8 *v24; // rbx
  unsigned int v25; // eax
  HANDLE_ENTRY *v26; // rcx
  ABO_NODE *v27; // rbx
  const unsigned __int16 *v28; // rax
  ABO_NODE *v29; // rbx
  const unsigned __int16 *v30; // rax
  HANDLE_ENTRY *v32; // [rsp+50h] [rbp-B0h] BYREF
  ABO_NODE *v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v34; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v35; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h]
  struct HANDLE_ENTRY *v37; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+78h] [rbp-88h]
  unsigned int v39; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 *v40; // [rsp+80h] [rbp-80h]
  struct ABO_TREE *v41; // [rsp+88h] [rbp-78h] BYREF
  void **v42; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v43[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _METADATA_RECORD v44; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v45[48]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v46[56]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v47[56]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v48[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v49[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v50[256]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v51[256]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v38 = a2;
  v11 = 0;
  v40 = a5;
  v37 = 0;
  v32 = 0;
  memset_0(v49, 0, sizeof(v49));
  STRU::STRU((STRU *)v46, v49, 0x100u);
  memset_0(v50, 0, sizeof(v50));
  STRU::STRU((STRU *)v48, v50, 0x100u);
  memset_0(v51, 0, sizeof(v51));
  STRU::STRU((STRU *)v47, v51, 0x100u);
  BUFFER::BUFFER((BUFFER *)v45);
  v42 = &PROPERTY_BAG::`vftable';
  v34 = 0;
  v39 = 0;
  v35 = 0;
  v13 = 0;
  v43[0] = 0;
  v43[1] = 0;
  v33 = 0;
  v41 = 0;
  memset(&v44, 0, sizeof(v44));
  if ( !a4 || (a6 & 1) != 0 && !a9 )
  {
    HandleEntry = -2147024809;
    goto LABEL_43;
  }
  v14 = 0;
  v36 = 0;
  HandleEntry = ABO_WRAPPER::GetHandleEntry(this, a4, &v32);
  if ( HandleEntry < 0 )
    goto LABEL_7;
  if ( (*((_BYTE *)v32 + 76) & 2) != 0 )
  {
    HandleEntry = HANDLE_ENTRY::GetFullPath(v32, v40, (struct STRU *)v46);
    if ( HandleEntry < 0 )
      goto LABEL_7;
    CReaderWriterLock3::WriteLock((ABO_WRAPPER *)((char *)this + 32));
    CurrentAboTree = ABO_WRAPPER::GetCurrentAboTree(this, &v41);
    v13 = (ABO_NODE **)v41;
    HandleEntry = CurrentAboTree;
    if ( CurrentAboTree >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v46);
      HandleEntry = ABO_WRAPPER::CheckAccessAndPermissions(this, (ABO_TREE *)v13, Str, 1, 0);
      if ( HandleEntry >= 0 )
      {
        if ( v38 )
        {
          HandleEntry = ABO_WRAPPER::GetHandleEntry(this, v38, &v37);
          if ( HandleEntry >= 0 )
          {
            HandleEntry = ABO_WRAPPER::GetAllDataInternal(
                            this,
                            v37,
                            a3,
                            (struct ABO_TREE *)v13,
                            a6,
                            a7,
                            a8,
                            &v39,
                            (struct PROPERTY_BAG *)&v42);
            if ( HandleEntry >= 0 )
            {
              Ptr = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v45);
              Size = BUFFER::QuerySize((BUFFER *)v45);
              if ( (unsigned int)PROPERTY_BAG::CopyAllToBuffer((PROPERTY_BAG *)&v42, a6, &v34, Size, Ptr, &v35) != -2147024774 )
                goto LABEL_36;
              if ( !BUFFER::Resize((BUFFER *)v45, v35) )
              {
                LastError = GetLastError();
                HandleEntry = LastError;
                if ( LastError > 0 )
                  HandleEntry = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_27;
              }
              v24 = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v45);
              v25 = BUFFER::QuerySize((BUFFER *)v45);
              HandleEntry = PROPERTY_BAG::CopyAllToBuffer((PROPERTY_BAG *)&v42, a6, &v34, v25, v24, &v35);
              if ( HandleEntry >= 0 )
              {
LABEL_36:
                if ( a9 )
                {
                  v29 = v13[2];
                  v30 = STRU::QueryStr((STRU *)v46);
                  ABO_NODE::FindNode(v29, v30, &v33);
                }
                v40 = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v45);
                v26 = 0;
                if ( !v36 )
                  v26 = v37;
                HandleEntry = HANDLE_ENTRY::GetFullPath(v26, a3, (struct STRU *)v47);
                if ( HandleEntry >= 0 )
                {
                  v27 = v13[2];
                  v28 = STRU::QueryStr((STRU *)v47);
                  ABO_NODE::FindNode(v27, v28, &v33);
                }
              }
            }
          }
        }
        else
        {
          v19 = (HANDLE_ENTRY *)operator new(0x50u);
          if ( v19 && (v20 = HANDLE_ENTRY::HANDLE_ENTRY(v19, 1u), (v14 = (unsigned int *)v20) != 0) )
          {
            HandleEntry = HANDLE_ENTRY::Create(v20, a3);
            if ( HandleEntry >= 0 )
              ABO_NODE::FindNode(v13[2], a3, &v33);
          }
          else
          {
            HandleEntry = -2147024888;
          }
        }
      }
    }
LABEL_27:
    v16 = v32;
    CReaderWriterLock3::WriteUnlock((ABO_WRAPPER *)((char *)this + 32));
    v11 = v37;
    goto LABEL_8;
  }
  HandleEntry = -2147024891;
LABEL_7:
  v16 = v32;
LABEL_8:
  if ( v16 )
    HANDLE_ENTRY::DereferenceHandleEntry(v16);
  if ( v11 )
    HANDLE_ENTRY::DereferenceHandleEntry(v11);
  if ( v14 )
  {
    if ( v36 )
    {
      HandleEntry = (*(__int64 (__fastcall **)(ABO_WRAPPER *, _QWORD))(*(_QWORD *)this + 32LL))(this, v14[3]);
      if ( HandleEntry < 0 )
      {
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to Close dummy key used during CopyData\n");
        HandleEntry = 0;
      }
    }
    HANDLE_ENTRY::DereferenceHandleEntry((HANDLE_ENTRY *)v14);
  }
  if ( v13 )
    HANDLE_ENTRY::DereferenceHandleEntry((HANDLE_ENTRY *)v13);
LABEL_43:
  v42 = &PROPERTY_BAG::`vftable';
  ARRAY_LIST::~ARRAY_LIST((ARRAY_LIST *)v43);
  BUFFER::~BUFFER((BUFFER *)v45);
  STRU::~STRU((STRU *)v47);
  STRU::~STRU((STRU *)v48);
  STRU::~STRU((STRU *)v46);
  return (unsigned int)HandleEntry;
}

```

## disassembly

```asm
0x18000bf00  push    rbp
0x18000bf02  push    rbx
0x18000bf03  push    rsi
0x18000bf04  push    rdi
0x18000bf05  push    r12
0x18000bf07  push    r13
0x18000bf09  push    r14
0x18000bf0b  push    r15
0x18000bf0d  lea     rbp, [rsp-6C8h]
0x18000bf15  sub     rsp, 7C8h
0x18000bf1c  mov     rax, cs:__security_cookie
0x18000bf23  xor     rax, rsp
0x18000bf26  mov     [rbp+700h+var_50], rax
0x18000bf2d  mov     rax, [rbp+700h+arg_20]
0x18000bf34  mov     r15, r8
0x18000bf37  mov     [rsp+800h+var_788], edx
0x18000bf3b  mov     r13, rcx
0x18000bf3e  xor     r12d, r12d
0x18000bf41  mov     [rbp+700h+var_780], rax
0x18000bf45  mov     esi, 200h
0x18000bf4a  mov     [rsp+800h+var_790], r12
0x18000bf4f  mov     r8d, esi; Size
0x18000bf52  mov     [rsp+800h+var_7B0], r12
0x18000bf57  xor     edx, edx; Val
0x18000bf59  lea     rcx, [rbp+700h+var_650]; void *
0x18000bf60  mov     ebx, r9d
0x18000bf63  call    memset_0
0x18000bf68  mov     edi, 100h
0x18000bf6d  lea     rdx, [rbp+700h+var_650]
0x18000bf74  mov     r8d, edi
0x18000bf77  lea     rcx, [rbp+700h+var_700]
0x18000bf7b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bf81  mov     r8d, esi; Size
0x18000bf84  lea     rcx, [rbp+700h+var_450]; void *
0x18000bf8b  xor     edx, edx; Val
0x18000bf8d  call    memset_0
0x18000bf92  mov     r8d, edi
0x18000bf95  lea     rdx, [rbp+700h+var_450]
0x18000bf9c  lea     rcx, [rbp+700h+var_690]
0x18000bfa0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bfa6  mov     r8d, esi; Size
0x18000bfa9  lea     rcx, [rbp+700h+var_250]; void *
0x18000bfb0  xor     edx, edx; Val
0x18000bfb2  call    memset_0
0x18000bfb7  mov     r8d, edi
0x18000bfba  lea     rdx, [rbp+700h+var_250]
0x18000bfc1  lea     rcx, [rbp+700h+var_6C8]
0x18000bfc5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bfcb  lea     rcx, [rbp+700h+var_730]
0x18000bfcf  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000bfd5  xor     ecx, ecx
0x18000bfd7  lea     rsi, ??_7PROPERTY_BAG@@6B@; const PROPERTY_BAG::`vftable'
0x18000bfde  xor     eax, eax
0x18000bfe0  mov     [rbp+700h+var_770], rsi
0x18000bfe4  mov     [rsp+800h+var_7A0], ecx
0x18000bfe8  xorps   xmm0, xmm0
0x18000bfeb  mov     [rsp+800h+var_784], ecx
0x18000bfef  mov     esi, ecx
0x18000bff1  mov     [rsp+800h+var_79C], ecx
0x18000bff5  mov     r14d, ecx
0x18000bff8  mov     qword ptr [rbp+700h+var_758.dwMDDataTag], rax
0x18000bffc  mov     [rbp+700h+var_768], rcx
0x18000c000  mov     [rbp+700h+var_760], rcx
0x18000c004  mov     [rsp+800h+var_7A8], rcx
0x18000c009  mov     [rbp+700h+var_778], rcx
0x18000c00d  movups  xmmword ptr [rbp+700h+var_758.dwMDIdentifier], xmm0
0x18000c011  movups  xmmword ptr [rbp+700h+var_758.dwMDDataLen], xmm0
0x18000c015  test    ebx, ebx
0x18000c017  jz      loc_18000C4ED
0x18000c01d  test    byte ptr [rbp+700h+arg_28], 1
0x18000c024  jz      short loc_18000C032
0x18000c026  cmp     [rbp+700h+arg_40], ecx
0x18000c02c  jz      loc_18000C4ED
0x18000c032  mov     rdi, rcx
0x18000c035  mov     [rsp+800h+var_798], ecx
0x18000c039  mov     rcx, r13; this
0x18000c03c  lea     r8, [rsp+800h+var_7B0]; struct HANDLE_ENTRY **
0x18000c041  mov     edx, ebx; unsigned int
0x18000c043  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000c048  mov     ebx, eax
0x18000c04a  test    eax, eax
0x18000c04c  js      short loc_18000C062
0x18000c04e  mov     rbx, [rsp+800h+var_7B0]
0x18000c053  test    byte ptr [rbx+4Ch], 2
0x18000c057  jnz     loc_18000C0E6
0x18000c05d  mov     ebx, 80070005h
0x18000c062  mov     r15, [rsp+800h+var_7B0]
0x18000c067  test    r15, r15
0x18000c06a  jz      short loc_18000C074
0x18000c06c  mov     rcx, r15; this
0x18000c06f  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c074  test    r12, r12
0x18000c077  jz      short loc_18000C081
0x18000c079  mov     rcx, r12; this
0x18000c07c  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c081  test    rdi, rdi
0x18000c084  jz      short loc_18000C0C3
0x18000c086  cmp     [rsp+800h+var_798], 0
0x18000c08b  jz      short loc_18000C0BB
0x18000c08d  mov     rax, [r13+0]
0x18000c091  mov     rcx, r13
0x18000c094  mov     edx, [rdi+0Ch]
0x18000c097  mov     rax, [rax+20h]
0x18000c09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0a0  mov     ebx, eax
0x18000c0a2  test    eax, eax
0x18000c0a4  jns     short loc_18000C0BB
0x18000c0a6  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000c0ad  lea     rdx, aFailedToCloseD; "Failed to Close dummy key used during C"...
0x18000c0b4  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000c0b9  xor     ebx, ebx
0x18000c0bb  mov     rcx, rdi; this
0x18000c0be  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c0c3  test    rsi, rsi
0x18000c0c6  jz      short loc_18000C0D0
0x18000c0c8  mov     rcx, rsi; this
0x18000c0cb  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000c0d0  test    r14, r14
0x18000c0d3  jz      loc_18000C4F2
0x18000c0d9  mov     rcx, r14; this
0x18000c0dc  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18000c0e1  jmp     loc_18000C4F2
0x18000c0e6  mov     rdx, [rbp+700h+var_780]; unsigned __int16 *
0x18000c0ea  lea     r8, [rbp+700h+var_700]; struct STRU *
0x18000c0ee  mov     rcx, rbx; this
0x18000c0f1  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000c0f6  mov     ebx, eax
0x18000c0f8  test    eax, eax
0x18000c0fa  js      loc_18000C062
0x18000c100  lea     rcx, [r13+20h]
0x18000c104  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c10a  lea     rdx, [rbp+700h+var_778]; struct ABO_TREE **
0x18000c10e  mov     rcx, r13; this
0x18000c111  call    ?GetCurrentAboTree@ABO_WRAPPER@@AEAAJPEAPEAVABO_TREE@@@Z; ABO_WRAPPER::GetCurrentAboTree(ABO_TREE * *)
0x18000c116  mov     r14, [rbp+700h+var_778]
0x18000c11a  mov     ebx, eax
0x18000c11c  test    eax, eax
0x18000c11e  js      loc_18000C1CA
0x18000c124  lea     rcx, [rbp+700h+var_700]
0x18000c128  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c12e  mov     r12d, 1
0x18000c134  mov     [rsp+800h+var_7E0], rsi
0x18000c139  mov     r9d, r12d
0x18000c13c  mov     r8, rax
0x18000c13f  mov     rdx, r14
0x18000c142  mov     rcx, r13
0x18000c145  call    ?CheckAccessAndPermissions@ABO_WRAPPER@@AEAAJPEAVABO_TREE@@PEBGW4ACCESS_REQUESTED@@PEAW4ACCESS_GRANTED@@@Z; ABO_WRAPPER::CheckAccessAndPermissions(ABO_TREE *,ushort const *,ACCESS_REQUESTED,ACCESS_GRANTED *)
0x18000c14a  mov     ebx, eax
0x18000c14c  test    eax, eax
0x18000c14e  js      short loc_18000C1CA
0x18000c150  mov     eax, [rsp+800h+var_788]
0x18000c154  test    eax, eax
0x18000c156  jnz     loc_18000C216
0x18000c15c  lea     ecx, [rax+50h]; Size
0x18000c15f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c164  test    rax, rax
0x18000c167  jz      loc_18000C20F
0x18000c16d  mov     edx, r12d; unsigned int
0x18000c170  mov     rcx, rax; this
0x18000c173  call    ??0HANDLE_ENTRY@@QEAA@K@Z; HANDLE_ENTRY::HANDLE_ENTRY(ulong)
0x18000c178  mov     rdi, rax
0x18000c17b  test    rax, rax
0x18000c17e  jz      loc_18000C20F
0x18000c184  mov     rdx, r15; unsigned __int16 *
0x18000c187  mov     rcx, rax; this
0x18000c18a  call    ?Create@HANDLE_ENTRY@@QEAAJPEBG@Z; HANDLE_ENTRY::Create(ushort const *)
0x18000c18f  mov     ebx, eax
0x18000c191  test    eax, eax
0x18000c193  js      short loc_18000C1CA
0x18000c195  mov     rcx, [r14+10h]; this
0x18000c199  lea     r8, [rsp+800h+var_7A8]; struct ABO_NODE **
0x18000c19e  mov     rdx, r15; unsigned __int16 *
0x18000c1a1  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000c1a6  mov     ebx, eax
0x18000c1a8  test    eax, eax
0x18000c1aa  js      short loc_18000C208
0x18000c1ac  lea     rcx, [r13+30h]
0x18000c1b0  xor     r8d, r8d
0x18000c1b3  mov     rdx, rdi
0x18000c1b6  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000c1bc  mov     rsi, [rsp+800h+var_7A8]
0x18000c1c1  test    eax, eax
0x18000c1c3  jz      short loc_18000C1E3
0x18000c1c5  mov     ebx, 800700B7h
0x18000c1ca  mov     r15, [rsp+800h+var_7B0]
0x18000c1cf  lea     rcx, [r13+20h]
0x18000c1d3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c1d9  mov     r12, [rsp+800h+var_790]
0x18000c1de  jmp     loc_18000C067
0x18000c1e3  mov     [rsp+800h+var_798], r12d
0x18000c1e8  lea     r15, word_18002E968
0x18000c1ef  test    rsi, rsi
0x18000c1f2  jz      short loc_18000C203
0x18000c1f4  mov     rcx, rsi; this
0x18000c1f7  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000c1fc  xor     esi, esi
0x18000c1fe  mov     [rsp+800h+var_7A8], rsi
0x18000c203  mov     rdx, rdi
0x18000c206  jmp     short loc_18000C230
0x18000c208  mov     rsi, [rsp+800h+var_7A8]
0x18000c20d  jmp     short loc_18000C1CA
0x18000c20f  mov     ebx, 80070008h
0x18000c214  jmp     short loc_18000C1CA
0x18000c216  lea     r8, [rsp+800h+var_790]; struct HANDLE_ENTRY **
0x18000c21b  mov     edx, eax; unsigned int
0x18000c21d  mov     rcx, r13; this
0x18000c220  call    ?GetHandleEntry@ABO_WRAPPER@@AEAAJKPEAPEAVHANDLE_ENTRY@@@Z; ABO_WRAPPER::GetHandleEntry(ulong,HANDLE_ENTRY * *)
0x18000c225  mov     ebx, eax
0x18000c227  test    eax, eax
0x18000c229  js      short loc_18000C1CA
0x18000c22b  mov     rdx, [rsp+800h+var_790]; struct HANDLE_ENTRY *
0x18000c230  mov     r12d, [rbp+700h+arg_28]
0x18000c237  lea     rax, [rbp+700h+var_770]
0x18000c23b  mov     [rsp+800h+var_7C0], rax; struct PROPERTY_BAG *
0x18000c240  mov     r9, r14; struct ABO_TREE *
0x18000c243  lea     rax, [rsp+800h+var_784]
0x18000c248  mov     r8, r15; unsigned __int16 *
0x18000c24b  mov     [rsp+800h+var_7C8], rax; unsigned int *
0x18000c250  mov     rcx, r13; this
0x18000c253  mov     eax, [rbp+700h+arg_38]
0x18000c259  mov     [rsp+800h+var_7D0], eax; unsigned int
0x18000c25d  mov     eax, [rbp+700h+arg_30]
0x18000c263  mov     dword ptr [rsp+800h+var_7D8], eax; unsigned int
0x18000c267  mov     dword ptr [rsp+800h+var_7E0], r12d; unsigned int
0x18000c26c  call    ?GetAllDataInternal@ABO_WRAPPER@@AEAAJPEAVHANDLE_ENTRY@@PEBGPEAVABO_TREE@@KKKPEAKPEAVPROPERTY_BAG@@@Z; ABO_WRAPPER::GetAllDataInternal(HANDLE_ENTRY *,ushort const *,ABO_TREE *,ulong,ulong,ulong,ulong *,PROPERTY_BAG *)
0x18000c271  mov     ebx, eax
0x18000c273  test    eax, eax
0x18000c275  js      loc_18000C1CA
0x18000c27b  lea     rcx, [rbp+700h+var_730]
0x18000c27f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c285  lea     rcx, [rbp+700h+var_730]
0x18000c289  mov     rbx, rax
0x18000c28c  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000c292  lea     rcx, [rsp+800h+var_79C]
0x18000c297  mov     edx, r12d; unsigned int
0x18000c29a  mov     [rsp+800h+var_7D8], rcx; unsigned int *
0x18000c29f  lea     r8, [rsp+800h+var_7A0]; unsigned int *
0x18000c2a4  lea     rcx, [rbp+700h+var_770]; this
0x18000c2a8  mov     [rsp+800h+var_7E0], rbx; unsigned __int8 *
0x18000c2ad  mov     r9d, eax; unsigned int
0x18000c2b0  call    ?CopyAllToBuffer@PROPERTY_BAG@@QEAAJKPEAKKPEAE0@Z; PROPERTY_BAG::CopyAllToBuffer(ulong,ulong *,ulong,uchar *,ulong *)
0x18000c2b5  cmp     eax, 8007007Ah
0x18000c2ba  jnz     short loc_18000C330
0x18000c2bc  mov     edx, [rsp+800h+var_79C]
0x18000c2c0  lea     rcx, [rbp+700h+var_730]
0x18000c2c4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000c2ca  test    al, al
0x18000c2cc  jnz     short loc_18000C2EC
0x18000c2ce  call    cs:__imp_GetLastError
0x18000c2d4  mov     ebx, eax
0x18000c2d6  test    eax, eax
0x18000c2d8  jle     loc_18000C1CA
0x18000c2de  movzx   ebx, ax
0x18000c2e1  or      ebx, 80070000h
0x18000c2e7  jmp     loc_18000C1CA
0x18000c2ec  lea     rcx, [rbp+700h+var_730]
0x18000c2f0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c2f6  lea     rcx, [rbp+700h+var_730]
0x18000c2fa  mov     rbx, rax
0x18000c2fd  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000c303  lea     rcx, [rsp+800h+var_79C]
0x18000c308  mov     edx, r12d; unsigned int
0x18000c30b  mov     [rsp+800h+var_7D8], rcx; unsigned int *
0x18000c310  lea     r8, [rsp+800h+var_7A0]; unsigned int *
0x18000c315  lea     rcx, [rbp+700h+var_770]; this
0x18000c319  mov     [rsp+800h+var_7E0], rbx; unsigned __int8 *
0x18000c31e  mov     r9d, eax; unsigned int
0x18000c321  call    ?CopyAllToBuffer@PROPERTY_BAG@@QEAAJKPEAKKPEAE0@Z; PROPERTY_BAG::CopyAllToBuffer(ulong,ulong *,ulong,uchar *,ulong *)
0x18000c326  mov     ebx, eax
0x18000c328  test    eax, eax
0x18000c32a  js      loc_18000C1CA
0x18000c330  cmp     [rbp+700h+arg_40], 0
0x18000c337  mov     r12d, [rsp+800h+var_7A0]
0x18000c33c  jnz     loc_18000C3FD
0x18000c342  lea     rcx, [rbp+700h+var_730]
0x18000c346  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c34c  cmp     [rsp+800h+var_798], 0
0x18000c351  lea     r8, [rbp+700h+var_6C8]; struct STRU *
0x18000c355  mov     [rbp+700h+var_780], rax
0x18000c359  mov     rdx, r15; unsigned __int16 *
0x18000c35c  mov     rcx, rdi
0x18000c35f  jnz     short loc_18000C366
0x18000c361  mov     rcx, [rsp+800h+var_790]; this
0x18000c366  call    ?GetFullPath@HANDLE_ENTRY@@QEAAJPEBGPEAVSTRU@@@Z; HANDLE_ENTRY::GetFullPath(ushort const *,STRU *)
0x18000c36b  mov     ebx, eax
0x18000c36d  test    eax, eax
0x18000c36f  js      loc_18000C1CA
0x18000c375  mov     rbx, [r14+10h]
0x18000c379  lea     rcx, [rbp+700h+var_6C8]
0x18000c37d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000c383  lea     r8, [rsp+800h+var_7A8]; struct ABO_NODE **
0x18000c388  mov     rcx, rbx; this
0x18000c38b  mov     rdx, rax; unsigned __int16 *
0x18000c38e  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x18000c393  mov     ebx, eax
0x18000c395  test    eax, eax
0x18000c397  js      loc_18000C208
0x18000c39d  mov     rsi, [rsp+800h+var_7A8]
0x18000c3a2  xor     r15d, r15d
0x18000c3a5  test    r12d, r12d
  ... truncated ...
```

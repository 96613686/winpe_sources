# CRepubReadWriteBaseTask::AllocateFile(unsigned __int64,unsigned __int64 *,bool *)

- ea: `0x18007c658`
- end: `0x18007cc0a`
- name: `?AllocateFile@CRepubReadWriteBaseTask@@IEAAK_KPEA_KPEA_N@Z`
- size: `1458`
- prototype: `__int64 __fastcall(CRepubReadWriteBaseTask *this, unsigned __int64, LPCWSTR *, bool *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18007d374`
- `0x180080570`

## callees

- `0x1800024f0`
- `0x180008290`
- `0x1800082d0`
- `0x180008310`
- `0x18000cf48`
- `0x18000cfc0`
- `0x18006116c`
- `0x180065f44`
- `0x18006a110`
- `0x180073e44`
- `0x18007c658`
- `0x18007cd00`
- `0x18007ddb4`
- `0x180080038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca48`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007ca3a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007ca3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubReadWriteBaseTask::AllocateFile(
        CRepubReadWriteBaseTask *this,
        unsigned __int64 a2,
        LPCWSTR *a3,
        bool *a4)
{
  WCHAR *v8; // rbx
  WCHAR *v9; // rdi
  LPCWSTR v10; // r12
  bool v11; // r13
  unsigned int inserted; // esi
  CHostedCacheMsgEncoding *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CHostedCacheMsgEncoding *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  unsigned int v19; // edx
  unsigned int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  __int64 v23; // rax
  unsigned __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpNewFileName; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR v28; // [rsp+58h] [rbp-18h]
  LPCWSTR v29; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids);
  }
  v8 = 0;
  v28 = 0;
  v9 = 0;
  v29 = 0;
  v25 = 0;
  lpNewFileName = 0;
  *a3 = 0;
  *a4 = 0;
  v10 = 0;
  lpExistingFileName = 0;
  v11 = 0;
  if ( CRepubReadWriteBaseTask::CheckFileAllocation(this, a2) != 1168 )
  {
    inserted = ConstructRepubFilePath(
                 a2,
                 *(_DWORD *)(*((_QWORD *)this + 76) + 224LL),
                 *(_DWORD *)(*((_QWORD *)this + 76) + 228LL),
                 (const unsigned __int16 *)(*((_QWORD *)this + 75) + 20LL),
                 0,
                 *(_QWORD *)(*((_QWORD *)this + 75) + 624LL),
                 (unsigned __int16 **)&lpNewFileName,
                 &v25);
    if ( inserted )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_78;
      }
      v17 = 32;
      goto LABEL_18;
    }
    operator delete(0);
    v8 = (WCHAR *)lpNewFileName;
    v28 = lpNewFileName;
    goto LABEL_70;
  }
  inserted = CRepubCatalogLRUTask::CommitRecords(this, 1);
  if ( inserted )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v14 = 22;
LABEL_11:
      v15 = inserted;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v13 + 12), v14, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v15);
      goto LABEL_78;
    }
    goto LABEL_78;
  }
  inserted = ConstructRepubFilePath(
               a2,
               *(_DWORD *)(*((_QWORD *)this + 76) + 224LL),
               *(_DWORD *)(*((_QWORD *)this + 76) + 228LL),
               (const unsigned __int16 *)(*((_QWORD *)this + 75) + 20LL),
               1,
               *(_QWORD *)(*((_QWORD *)this + 75) + 624LL),
               (unsigned __int16 **)&lpNewFileName,
               &v25);
  if ( inserted )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_78;
    }
    v17 = 23;
LABEL_18:
    v18 = a2;
    goto LABEL_19;
  }
  operator delete(0);
  v8 = (WCHAR *)lpNewFileName;
  v28 = lpNewFileName;
  *(_QWORD *)(*((_QWORD *)this + 75) + 624LL) = v25;
  inserted = CRepubEvictSegmentsTask::ReserveFile(this, v19, v20);
  v15 = 112;
  if ( inserted != 112 )
  {
LABEL_37:
    inserted = CRepubReadWriteBaseTask::InsertFileTableEntry(this, a2);
    if ( inserted )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_78;
      }
      v17 = 27;
      goto LABEL_18;
    }
    inserted = CRepubCatalogLRUTask::CommitRecords(this, 1);
    if ( inserted )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v14 = 28;
        goto LABEL_11;
      }
      goto LABEL_78;
    }
    if ( v11 )
    {
      lpExistingFileName = 0;
      inserted = ConstructRepubFilePath(
                   (unsigned __int64)v10,
                   *(_DWORD *)(*((_QWORD *)this + 76) + 224LL),
                   *(_DWORD *)(*((_QWORD *)this + 76) + 228LL),
                   (const unsigned __int16 *)(*((_QWORD *)this + 75) + 20LL),
                   0,
                   *(_QWORD *)(*((_QWORD *)this + 75) + 624LL),
                   (unsigned __int16 **)&lpExistingFileName,
                   &v25);
      if ( inserted )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_78;
        }
        v17 = 29;
        v18 = (unsigned __int64)v10;
        goto LABEL_19;
      }
      operator delete(0);
      v9 = (WCHAR *)lpExistingFileName;
      v29 = lpExistingFileName;
      if ( !MoveFileExW(lpExistingFileName, v8, 1u) )
      {
        inserted = GetLastError();
        if ( inserted - 2 > 1 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              31,
              (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
              (_DWORD)v9,
              (__int64)v8,
              inserted);
          }
          goto LABEL_78;
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            30,
            (unsigned int)WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
            (_DWORD)v9,
            inserted);
        }
        inserted = 0;
      }
    }
LABEL_70:
    v23 = *((_QWORD *)this + 81);
    if ( v23 && *(_QWORD *)(v23 + 24) == a2 || (inserted = CRepubReadWriteBaseTask::OpenFileForWrite(this, a2, v8)) == 0 )
    {
      *a3 = v10;
      *a4 = v11;
      goto LABEL_78;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_78;
    }
    v17 = 33;
    v18 = *((_QWORD *)this + 78);
LABEL_19:
    WPP_SF_qD(*((_QWORD *)v16 + 12), v17, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v18, inserted);
    goto LABEL_78;
  }
  if ( *(_BYTE *)(*((_QWORD *)this + 1) + 172LL) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v14 = 24;
      goto LABEL_12;
    }
    goto LABEL_78;
  }
  inserted = CRepubCatalogLRUTask::GetNextLRUFileId(this, (unsigned __int64 *)&lpExistingFileName, 1);
  if ( !inserted )
  {
    inserted = CRepubEvictSegmentsTask::ReserveFile(this, v21, v22);
    if ( inserted )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_78;
      }
      v17 = 26;
      goto LABEL_18;
    }
    v11 = 1;
    v10 = lpExistingFileName;
    goto LABEL_37;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v14 = 25;
    goto LABEL_11;
  }
LABEL_78:
  operator delete(v9);
  operator delete(v8);
  return inserted;
}

```

## disassembly

```asm
0x18007c658  mov     [rsp-38h+arg_0], rbx
0x18007c65d  mov     [rsp-38h+arg_18], r9
0x18007c662  mov     [rsp-38h+arg_10], r8
0x18007c667  push    rbp
0x18007c668  push    rsi
0x18007c669  push    rdi
0x18007c66a  push    r12
0x18007c66c  push    r13
0x18007c66e  push    r14
0x18007c670  push    r15
0x18007c672  mov     rbp, rsp
0x18007c675  sub     rsp, 70h
0x18007c679  mov     rsi, r9
0x18007c67c  mov     r12, r8
0x18007c67f  mov     r15, rdx
0x18007c682  mov     r14, rcx
0x18007c685  lea     rax, WPP_GLOBAL_Control
0x18007c68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c693  cmp     rcx, rax
0x18007c696  jz      short loc_18007C6BC
0x18007c698  test    byte ptr [rcx+6Ch], 4
0x18007c69c  jz      short loc_18007C6BC
0x18007c69e  cmp     byte ptr [rcx+69h], 4
0x18007c6a2  jb      short loc_18007C6BC
0x18007c6a4  mov     edx, 15h
0x18007c6a9  mov     r9, r15
0x18007c6ac  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007c6b3  mov     rcx, [rcx+60h]
0x18007c6b7  call    WPP_SF_q
0x18007c6bc  xor     eax, eax
0x18007c6be  mov     ebx, eax
0x18007c6c0  mov     [rbp+var_18], rax
0x18007c6c4  mov     edi, eax
0x18007c6c6  mov     [rbp+var_10], rax
0x18007c6ca  mov     [rbp+var_30], rax
0x18007c6ce  mov     [rbp+lpNewFileName], rax
0x18007c6d2  mov     [r12], rax
0x18007c6d6  mov     [rsi], al
0x18007c6d8  mov     r12d, eax
0x18007c6db  mov     [rbp+lpExistingFileName], rax
0x18007c6df  mov     r13b, al
0x18007c6e2  mov     rdx, r15; unsigned __int64
0x18007c6e5  mov     rcx, r14; this
0x18007c6e8  call    ?CheckFileAllocation@CRepubReadWriteBaseTask@@IEAAK_K@Z; CRepubReadWriteBaseTask::CheckFileAllocation(unsigned __int64)
0x18007c6ed  cmp     eax, 490h
0x18007c6f2  jnz     loc_18007CAEB
0x18007c6f8  mov     dl, 1; bool
0x18007c6fa  mov     rcx, r14; this
0x18007c6fd  call    ?CommitRecords@CRepubCatalogLRUTask@@IEAAK_N@Z; CRepubCatalogLRUTask::CommitRecords(bool)
0x18007c702  mov     esi, eax
0x18007c704  test    eax, eax
0x18007c706  jz      short loc_18007C750
0x18007c708  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c70f  lea     rax, WPP_GLOBAL_Control
0x18007c716  cmp     rcx, rax
0x18007c719  jz      loc_18007CBDF
0x18007c71f  test    byte ptr [rcx+6Ch], 4
0x18007c723  jz      loc_18007CBDF
0x18007c729  cmp     byte ptr [rcx+69h], 1
0x18007c72d  jb      loc_18007CBDF
0x18007c733  lea     edx, [r12+16h]
0x18007c738  mov     r9d, esi
0x18007c73b  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007c742  mov     rcx, [rcx+60h]
0x18007c746  call    WPP_SF_d
0x18007c74b  jmp     loc_18007CBDF
0x18007c750  mov     rax, [r14+258h]
0x18007c757  mov     rdx, [r14+260h]
0x18007c75e  lea     r9, [rax+14h]; unsigned __int16 *
0x18007c762  lea     rcx, [rbp+var_30]
0x18007c766  mov     [rsp+70h+var_38], rcx; unsigned __int64 *
0x18007c76b  lea     rcx, [rbp+lpNewFileName]
0x18007c76f  mov     [rsp+70h+var_40], rcx; unsigned __int16 **
0x18007c774  mov     rax, [rax+270h]
0x18007c77b  mov     [rsp+70h+var_48], rax; unsigned __int64
0x18007c780  mov     [rsp+70h+var_50], 1; bool
0x18007c785  mov     r8d, [rdx+0E4h]; unsigned int
0x18007c78c  mov     edx, [rdx+0E0h]; unsigned int
0x18007c792  mov     rcx, r15; unsigned __int64
0x18007c795  call    ?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z; ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)
0x18007c79a  mov     esi, eax
0x18007c79c  test    eax, eax
0x18007c79e  jz      short loc_18007C7EC
0x18007c7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c7a7  lea     rax, WPP_GLOBAL_Control
0x18007c7ae  cmp     rcx, rax
0x18007c7b1  jz      loc_18007CBDF
0x18007c7b7  test    byte ptr [rcx+6Ch], 4
0x18007c7bb  jz      loc_18007CBDF
0x18007c7c1  cmp     byte ptr [rcx+69h], 1
0x18007c7c5  jb      loc_18007CBDF
0x18007c7cb  mov     edx, 17h
0x18007c7d0  mov     r9, r15
0x18007c7d3  mov     dword ptr [rsp+70h+var_50], esi
0x18007c7d7  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007c7de  mov     rcx, [rcx+60h]
0x18007c7e2  call    WPP_SF_qD
0x18007c7e7  jmp     loc_18007CBDF
0x18007c7ec  xor     ecx, ecx; Block
0x18007c7ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c7f3  mov     rbx, [rbp+lpNewFileName]
0x18007c7f7  mov     [rbp+var_18], rbx
0x18007c7fb  mov     rcx, [r14+258h]
0x18007c802  mov     rax, [rbp+var_30]
0x18007c806  mov     [rcx+270h], rax
0x18007c80d  mov     rcx, r14; this
0x18007c810  call    ?ReserveFile@CRepubEvictSegmentsTask@@IEAAKKK@Z; CRepubEvictSegmentsTask::ReserveFile(ulong,ulong)
0x18007c815  mov     esi, eax
0x18007c817  mov     r9d, 70h ; 'p'
0x18007c81d  cmp     eax, r9d
0x18007c820  jnz     loc_18007C8FB
0x18007c826  mov     rax, [r14+8]
0x18007c82a  cmp     [rax+0ACh], r12b
0x18007c831  jz      short loc_18007C867
0x18007c833  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c83a  lea     rax, WPP_GLOBAL_Control
0x18007c841  cmp     rcx, rax
0x18007c844  jz      loc_18007CBDF
0x18007c84a  test    byte ptr [rcx+6Ch], 4
0x18007c84e  jz      loc_18007CBDF
0x18007c854  cmp     byte ptr [rcx+69h], 1
0x18007c858  jb      loc_18007CBDF
0x18007c85e  lea     edx, [r9-58h]
0x18007c862  jmp     loc_18007C73B
0x18007c867  mov     r8b, 1; bool
0x18007c86a  lea     rdx, [rbp+lpExistingFileName]; unsigned __int64 *
0x18007c86e  mov     rcx, r14; this
0x18007c871  call    ?GetNextLRUFileId@CRepubCatalogLRUTask@@IEAAKPEA_K_N@Z; CRepubCatalogLRUTask::GetNextLRUFileId(unsigned __int64 *,bool)
0x18007c876  mov     esi, eax
0x18007c878  test    eax, eax
0x18007c87a  jz      short loc_18007C8B1
0x18007c87c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c883  lea     rax, WPP_GLOBAL_Control
0x18007c88a  cmp     rcx, rax
0x18007c88d  jz      loc_18007CBDF
0x18007c893  test    byte ptr [rcx+6Ch], 4
0x18007c897  jz      loc_18007CBDF
0x18007c89d  cmp     byte ptr [rcx+69h], 1
0x18007c8a1  jb      loc_18007CBDF
0x18007c8a7  mov     edx, 19h
0x18007c8ac  jmp     loc_18007C738
0x18007c8b1  mov     rcx, r14; this
0x18007c8b4  call    ?ReserveFile@CRepubEvictSegmentsTask@@IEAAKKK@Z; CRepubEvictSegmentsTask::ReserveFile(ulong,ulong)
0x18007c8b9  mov     esi, eax
0x18007c8bb  test    eax, eax
0x18007c8bd  jz      short loc_18007C8F4
0x18007c8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c8c6  lea     rax, WPP_GLOBAL_Control
0x18007c8cd  cmp     rcx, rax
0x18007c8d0  jz      loc_18007CBDF
0x18007c8d6  test    byte ptr [rcx+6Ch], 4
0x18007c8da  jz      loc_18007CBDF
0x18007c8e0  cmp     byte ptr [rcx+69h], 1
0x18007c8e4  jb      loc_18007CBDF
0x18007c8ea  mov     edx, 1Ah
0x18007c8ef  jmp     loc_18007C7D0
0x18007c8f4  mov     r13b, 1
0x18007c8f7  mov     r12, [rbp+lpExistingFileName]
0x18007c8fb  mov     rdx, r15; unsigned __int64
0x18007c8fe  mov     rcx, r14; this
0x18007c901  call    ?InsertFileTableEntry@CRepubReadWriteBaseTask@@IEAAK_K@Z; CRepubReadWriteBaseTask::InsertFileTableEntry(unsigned __int64)
0x18007c906  mov     esi, eax
0x18007c908  test    eax, eax
0x18007c90a  jz      short loc_18007C941
0x18007c90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c913  lea     rax, WPP_GLOBAL_Control
0x18007c91a  cmp     rcx, rax
0x18007c91d  jz      loc_18007CBDF
0x18007c923  test    byte ptr [rcx+6Ch], 4
0x18007c927  jz      loc_18007CBDF
0x18007c92d  cmp     byte ptr [rcx+69h], 1
0x18007c931  jb      loc_18007CBDF
0x18007c937  mov     edx, 1Bh
0x18007c93c  jmp     loc_18007C7D0
0x18007c941  mov     dl, 1; bool
0x18007c943  mov     rcx, r14; this
0x18007c946  call    ?CommitRecords@CRepubCatalogLRUTask@@IEAAK_N@Z; CRepubCatalogLRUTask::CommitRecords(bool)
0x18007c94b  mov     esi, eax
0x18007c94d  test    eax, eax
0x18007c94f  jz      short loc_18007C986
0x18007c951  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c958  lea     rax, WPP_GLOBAL_Control
0x18007c95f  cmp     rcx, rax
0x18007c962  jz      loc_18007CBDF
0x18007c968  test    byte ptr [rcx+6Ch], 4
0x18007c96c  jz      loc_18007CBDF
0x18007c972  cmp     byte ptr [rcx+69h], 1
0x18007c976  jb      loc_18007CBDF
0x18007c97c  mov     edx, 1Ch
0x18007c981  jmp     loc_18007C738
0x18007c986  test    r13b, r13b
0x18007c989  jz      loc_18007CB7B
0x18007c98f  mov     [rbp+lpExistingFileName], 0
0x18007c997  mov     rax, [r14+258h]
0x18007c99e  mov     rdx, [r14+260h]
0x18007c9a5  lea     r9, [rax+14h]; unsigned __int16 *
0x18007c9a9  lea     rcx, [rbp+var_30]
0x18007c9ad  mov     [rsp+70h+var_38], rcx; unsigned __int64 *
0x18007c9b2  lea     rcx, [rbp+lpExistingFileName]
0x18007c9b6  mov     [rsp+70h+var_40], rcx; unsigned __int16 **
0x18007c9bb  mov     rax, [rax+270h]
0x18007c9c2  mov     [rsp+70h+var_48], rax; unsigned __int64
0x18007c9c7  mov     [rsp+70h+var_50], 0; bool
0x18007c9cc  mov     r8d, [rdx+0E4h]; unsigned int
0x18007c9d3  mov     edx, [rdx+0E0h]; unsigned int
0x18007c9d9  mov     rcx, r12; unsigned __int64
0x18007c9dc  call    ?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z; ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)
0x18007c9e1  mov     esi, eax
0x18007c9e3  test    eax, eax
0x18007c9e5  jz      short loc_18007CA1F
0x18007c9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c9ee  lea     rax, WPP_GLOBAL_Control
0x18007c9f5  cmp     rcx, rax
0x18007c9f8  jz      loc_18007CBDF
0x18007c9fe  test    byte ptr [rcx+6Ch], 4
0x18007ca02  jz      loc_18007CBDF
0x18007ca08  cmp     byte ptr [rcx+69h], 1
0x18007ca0c  jb      loc_18007CBDF
0x18007ca12  mov     edx, 1Dh
0x18007ca17  mov     r9, r12
0x18007ca1a  jmp     loc_18007C7D3
0x18007ca1f  xor     ecx, ecx; Block
0x18007ca21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ca26  mov     rdi, [rbp+lpExistingFileName]
0x18007ca2a  mov     [rbp+var_10], rdi
0x18007ca2e  mov     r8d, 1; dwFlags
0x18007ca34  mov     rdx, rbx; lpNewFileName
0x18007ca37  mov     rcx, rdi; lpExistingFileName
0x18007ca3a  call    cs:__imp_MoveFileExW
0x18007ca40  test    eax, eax
0x18007ca42  jnz     loc_18007CB7B
0x18007ca48  call    cs:__imp_GetLastError
0x18007ca4e  mov     esi, eax
0x18007ca50  add     eax, 0FFFFFFFEh
0x18007ca53  cmp     eax, 1
0x18007ca56  jbe     short loc_18007CAA9
0x18007ca58  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ca5f  lea     rax, WPP_GLOBAL_Control
0x18007ca66  cmp     rcx, rax
0x18007ca69  jz      loc_18007CBDF
0x18007ca6f  test    byte ptr [rcx+6Ch], 4
0x18007ca73  jz      loc_18007CBDF
0x18007ca79  cmp     byte ptr [rcx+69h], 1
0x18007ca7d  jb      loc_18007CBDF
0x18007ca83  mov     edx, 1Fh
0x18007ca88  mov     dword ptr [rsp+70h+var_48], esi
0x18007ca8c  mov     qword ptr [rsp+70h+var_50], rbx
0x18007ca91  mov     r9, rdi
0x18007ca94  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007ca9b  mov     rcx, [rcx+60h]
0x18007ca9f  call    WPP_SF_SSD
0x18007caa4  jmp     loc_18007CBDF
0x18007caa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cab0  lea     rax, WPP_GLOBAL_Control
0x18007cab7  cmp     rcx, rax
0x18007caba  jz      short loc_18007CAE4
0x18007cabc  test    byte ptr [rcx+6Ch], 4
0x18007cac0  jz      short loc_18007CAE4
0x18007cac2  cmp     byte ptr [rcx+69h], 4
0x18007cac6  jb      short loc_18007CAE4
0x18007cac8  mov     edx, 1Eh
0x18007cacd  mov     dword ptr [rsp+70h+var_50], esi
0x18007cad1  mov     r9, rdi
0x18007cad4  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007cadb  mov     rcx, [rcx+60h]
0x18007cadf  call    WPP_SF_Sd
0x18007cae4  xor     esi, esi
0x18007cae6  jmp     loc_18007CB7B
0x18007caeb  mov     rax, [r14+258h]
0x18007caf2  mov     rdx, [r14+260h]
0x18007caf9  lea     r9, [rax+14h]; unsigned __int16 *
0x18007cafd  lea     rcx, [rbp+var_30]
0x18007cb01  mov     [rsp+70h+var_38], rcx; unsigned __int64 *
0x18007cb06  lea     rcx, [rbp+lpNewFileName]
0x18007cb0a  mov     [rsp+70h+var_40], rcx; unsigned __int16 **
0x18007cb0f  mov     rax, [rax+270h]
0x18007cb16  mov     [rsp+70h+var_48], rax; unsigned __int64
0x18007cb1b  mov     [rsp+70h+var_50], r12b; bool
0x18007cb20  mov     r8d, [rdx+0E4h]; unsigned int
0x18007cb27  mov     edx, [rdx+0E0h]; unsigned int
0x18007cb2d  mov     rcx, r15; unsigned __int64
0x18007cb30  call    ?ConstructRepubFilePath@@YAK_KKKPEBG_N0PEAPEAGPEA_K@Z; ConstructRepubFilePath(unsigned __int64,ulong,ulong,ushort const *,bool,unsigned __int64,ushort * *,unsigned __int64 *)
0x18007cb35  mov     esi, eax
0x18007cb37  test    eax, eax
0x18007cb39  jz      short loc_18007CB6C
0x18007cb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb42  lea     rax, WPP_GLOBAL_Control
0x18007cb49  cmp     rcx, rax
0x18007cb4c  jz      loc_18007CBDF
0x18007cb52  test    byte ptr [rcx+6Ch], 4
0x18007cb56  jz      loc_18007CBDF
0x18007cb5c  cmp     byte ptr [rcx+69h], 1
0x18007cb60  jb      short loc_18007CBDF
0x18007cb62  mov     edx, 20h ; ' '
0x18007cb67  jmp     loc_18007C7D0
0x18007cb6c  xor     ecx, ecx; Block
0x18007cb6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007cb73  mov     rbx, [rbp+lpNewFileName]
0x18007cb77  mov     [rbp+var_18], rbx
0x18007cb7b  mov     rax, [r14+288h]
  ... truncated ...
```

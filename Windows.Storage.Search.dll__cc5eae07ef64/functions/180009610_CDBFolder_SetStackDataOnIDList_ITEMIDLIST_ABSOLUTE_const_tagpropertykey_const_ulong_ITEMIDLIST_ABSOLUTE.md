# CDBFolder::_SetStackDataOnIDList(_ITEMIDLIST_ABSOLUTE const *,_tagpropertykey const &,ulong,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180009610`
- end: `0x180009a4a`
- name: `?_SetStackDataOnIDList@CDBFolder@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@AEBU_tagpropertykey@@KPEAPEAU2@@Z`
- size: `1082`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, const struct _tagpropertykey *, unsigned int, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180058af0`
- `0x180084650`
- `0x180085d60`

## callees

- `0x180009610`
- `0x18000b650`
- `0x18000b6d0`
- `0x180072cdc`
- `0x180072cf4`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x18000967c`
- `Windows.Storage!ILFindLastID` at `0x1800096bb`
- `Windows.Storage!ILFindLastID` at `0x180009745`
- `Windows.Storage!ILFindLastID` at `0x1800097e4`
- `Windows.Storage!ILFindLastID` at `0x180009822`
- `Windows.Storage!ILFindLastID` at `0x18000967c`
- `Windows.Storage!ILFindLastID` at `0x1800096bb`
- `Windows.Storage!ILFindLastID` at `0x180009745`
- `Windows.Storage!ILFindLastID` at `0x1800097e4`
- `Windows.Storage!ILFindLastID` at `0x180009822`
- `Windows.Storage!ILFree` at `0x1800097ca`
- `Windows.Storage!ILFree` at `0x1800098dd`
- `Windows.Storage!ILFree` at `0x1800097ca`
- `Windows.Storage!ILFree` at `0x1800098dd`
- `Windows.Storage!ILClone` at `0x180009643`
- `Windows.Storage!ILClone` at `0x180009643`
- `Windows.Storage!ILGetSize` at `0x180009700`
- `Windows.Storage!ILGetSize` at `0x180009700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000970d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000970d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097b1`

## pseudocode

```c
__int64 __fastcall CDBFolder::_SetStackDataOnIDList(
        CDBFolder *this,
        const ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        int a4,
        struct _ITEMIDLIST_ABSOLUTE **a5)
{
  int v5; // r13d
  LPITEMIDLIST v7; // rbx
  int v8; // esi
  LPITEMIDLIST ID; // rax
  LPITEMIDLIST v11; // rdx
  int v12; // r12d
  unsigned __int64 v13; // rax
  const struct _ITEMIDLIST_RELATIVE *v14; // rbp
  const struct _HIDDENITEMID *v15; // rdx
  unsigned __int64 v16; // rbp
  ITEMIDLIST *v17; // rbp
  UINT v18; // r13d
  ITEMIDLIST *v19; // rax
  size_t v20; // rax
  const struct _ITEMIDLIST_RELATIVE *v21; // rdi
  const struct _ITEMIDLIST_RELATIVE *v22; // rax
  unsigned __int16 v23; // r8
  unsigned __int16 *v24; // rdx
  LPITEMIDLIST v25; // rax
  unsigned __int64 cb; // rcx
  BYTE *abID; // rdi
  const struct _ITEMIDLIST_RELATIVE *v28; // rbp
  const struct _HIDDENITEMID *HiddenID; // rdx
  unsigned __int64 v30; // rbp
  unsigned __int16 *v31; // rcx
  DWORD pid; // ecx
  __m128i v33; // xmm0
  int v34; // eax
  unsigned int v35; // ecx
  int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // ecx
  int v39; // eax
  unsigned __int64 v40; // rax
  const struct _HIDDENITEMID *v41; // r8
  unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  const struct _HIDDENITEMID *v44; // r8
  unsigned __int16 *v45; // r9

  v5 = a4;
  *a5 = 0;
  if ( a2 )
  {
    v7 = ILClone(a2);
    v8 = -2147024882;
    if ( !v7 )
      return 2147942414LL;
    ID = ILFindLastID(v7);
    v11 = ID;
    v12 = 1;
    if ( !ID
      || (v13 = ID->mkid.cb, (unsigned int)v13 < 0x2E)
      || *(_DWORD *)&v11[2].mkid.cb != 269752705
      || v13 < (unsigned __int64)*(unsigned __int16 *)((char *)&v11[3].mkid.cb + 1) + 46
      || (abID = v11[4].mkid.abID, v11 == (LPITEMIDLIST)-14LL) )
    {
      if ( !v7->mkid.cb
        || (v14 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v7),
            v15 = ILFindFirstHiddenID(v14),
            v16 = (unsigned __int64)v14 + *(unsigned __int16 *)v14,
            !v15) )
      {
LABEL_10:
        v17 = v7;
        if ( v7->mkid.cb )
        {
          v18 = ILGetSize(v7);
          v19 = (ITEMIDLIST *)CoTaskMemAlloc(v18 + 42);
          v17 = v19;
          if ( v19 )
          {
            v20 = CTCoAllocPolicy::_CoTaskMemSize(v19);
            memset_0(v17, 0, v20);
            memcpy_0(v17, v7, v18);
            v21 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v17);
            if ( ILFindFirstHiddenID(v21) )
              v22 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v21 + *(unsigned __int16 *)v21 - 2);
            else
              v22 = v21;
            v23 = *(_WORD *)v22;
            v24 = (unsigned __int16 *)((char *)v17 + v18 - 2);
            *(_DWORD *)v24 = 40;
            *((_DWORD *)v24 + 1) = -1091633133;
            *((_DWORD *)v24 + 2) = 0x20000000;
            *(PROPERTYKEY *)(v24 + 6) = PKEY_Null;
            *((_DWORD *)v24 + 8) = 0;
            *((_DWORD *)v24 + 9) = 1;
            *v24 = 42;
            if ( (unsigned __int16)(*(_WORD *)v21 + 42) >= *(_WORD *)v21 )
            {
              *(_WORD *)v21 += 42;
              *(unsigned __int16 *)((char *)v24 + *v24 - 2) = v23;
            }
            else
            {
              CoTaskMemFree(v17);
              v17 = 0;
            }
          }
          ILFree(v7);
          v5 = a4;
        }
        v7 = v17;
        if ( !v17 )
          goto LABEL_43;
        v25 = ILFindLastID(v17);
        if ( v25
          && (cb = v25->mkid.cb, (unsigned int)cb >= 0x2E)
          && *(_DWORD *)&v25[2].mkid.cb == 269752705
          && cb >= (unsigned __int64)*(unsigned __int16 *)((char *)&v25[3].mkid.cb + 1) + 46 )
        {
          abID = v25[4].mkid.abID;
          if ( v25 != (LPITEMIDLIST)-14LL )
            goto LABEL_28;
        }
        else
        {
          abID = 0;
        }
        v8 = -2147024809;
        if ( !v17->mkid.cb
          || (v28 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v17),
              HiddenID = ILFindFirstHiddenID(v28),
              v30 = (unsigned __int64)v28 + *(unsigned __int16 *)v28,
              !HiddenID) )
        {
LABEL_29:
          if ( v8 < 0 )
          {
LABEL_43:
            ILFree(v7);
            return (unsigned int)v8;
          }
LABEL_30:
          pid = a3->pid;
          v33 = *(__m128i *)(abID + 4);
          if ( *((_DWORD *)abID + 5) != pid )
            goto LABEL_62;
          v40 = v33.m128i_i64[0] - *(_QWORD *)&a3->fmtid.Data1;
          if ( v33.m128i_i64[0] == *(_QWORD *)&a3->fmtid.Data1 )
            v40 = _mm_srli_si128(v33, 8).m128i_u64[0] - *(_QWORD *)a3->fmtid.Data4;
          if ( v40 )
          {
LABEL_62:
            if ( pid )
              goto LABEL_32;
            v43 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Null.fmtid.Data1;
            if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Null.fmtid.Data1 )
              v43 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Null.fmtid.Data4;
            if ( v43 )
LABEL_32:
              v12 = 0;
            v34 = *((_DWORD *)abID + 7);
            v35 = v34 & 0xFFFFEFFF;
            v36 = v34 | 0x1000;
            if ( !v12 )
              v35 = v36;
            v37 = v35;
            v38 = v35 & 0xFFFFDFFF;
            v39 = v37 | 0x2000;
            if ( v5 == -1 )
              v38 = v39;
            *((_DWORD *)abID + 7) = v38;
            *(GUID *)(abID + 4) = a3->fmtid;
            *((_DWORD *)abID + 5) = a3->pid;
            *((_DWORD *)abID + 6) = v5;
          }
          *a5 = (struct _ITEMIDLIST_ABSOLUTE *)v7;
          v7 = 0;
          goto LABEL_43;
        }
        while ( 1 )
        {
          v31 = (unsigned __int16 *)((char *)HiddenID + 8);
          if ( *((_DWORD *)HiddenID + 1) == -1091633133 )
            break;
          v44 = 0;
          if ( (unsigned __int64)v31 <= v30 )
          {
            v45 = (unsigned __int16 *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
            if ( v45 == (unsigned __int16 *)v30 )
              goto LABEL_29;
            if ( (unsigned __int64)v45 <= v30 )
            {
              if ( (unsigned __int64)(v45 + 4) > v30
                || HIWORD(*((_DWORD *)v45 + 1)) != 0xBEEF
                || (unsigned __int64)v45 + *v45 > v30
                || v45 < v31 )
              {
                goto LABEL_29;
              }
              v44 = (const struct _HIDDENITEMID *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
            }
          }
          HiddenID = v44;
          if ( !v44 )
            goto LABEL_29;
        }
        abID = (BYTE *)HiddenID + 8;
LABEL_28:
        v8 = 0;
        goto LABEL_29;
      }
      while ( 1 )
      {
        abID = (BYTE *)v15 + 8;
        if ( *((_DWORD *)v15 + 1) == -1091633133 )
          break;
        v41 = 0;
        if ( (unsigned __int64)abID <= v16 )
        {
          v42 = (unsigned __int16 *)((char *)v15 + *(unsigned __int16 *)v15);
          if ( v42 == (unsigned __int16 *)v16 )
            goto LABEL_10;
          if ( (unsigned __int64)v42 <= v16 )
          {
            if ( (unsigned __int64)(v42 + 4) > v16
              || HIWORD(*((_DWORD *)v42 + 1)) != 0xBEEF
              || (unsigned __int64)v42 + *v42 > v16
              || v42 < (unsigned __int16 *)abID )
            {
              goto LABEL_10;
            }
            v41 = (const struct _HIDDENITEMID *)((char *)v15 + *(unsigned __int16 *)v15);
          }
        }
        v15 = v41;
        if ( !v41 )
          goto LABEL_10;
      }
    }
    v8 = 0;
    goto LABEL_30;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009610  push    rbx
0x180009612  push    rsi
0x180009613  push    r13
0x180009615  push    r14
0x180009617  push    r15
0x180009619  sub     rsp, 40h
0x18000961d  mov     r14, [rsp+68h+arg_20]
0x180009625  mov     r13d, r9d
0x180009628  mov     [rsp+68h+var_44], r9d
0x18000962d  mov     r15, r8
0x180009630  mov     qword ptr [r14], 0
0x180009637  test    rdx, rdx
0x18000963a  jz      loc_180009A40
0x180009640  mov     rcx, rdx; pidl
0x180009643  call    cs:__imp_ILClone
0x180009649  mov     rbx, rax
0x18000964c  mov     esi, 8007000Eh
0x180009651  xor     eax, eax
0x180009653  test    rbx, rbx
0x180009656  cmovz   eax, esi
0x180009659  jz      loc_1800098FF
0x18000965f  mov     [rsp+68h+arg_18], r12
0x180009667  mov     rcx, rbx; pidl
0x18000966a  mov     [rsp+68h+arg_0], rbp
0x18000966f  mov     [rsp+68h+arg_10], rdi
0x180009677  movaps  [rsp+68h+var_38], xmm6
0x18000967c  call    cs:__imp_ILFindLastID
0x180009682  mov     rdx, rax
0x180009685  mov     r12d, 1
0x18000968b  test    rax, rax
0x18000968e  jz      short loc_1800096B2
0x180009690  movzx   eax, word ptr [rax]
0x180009693  cmp     eax, 2Eh ; '.'
0x180009696  jb      short loc_1800096B2
0x180009698  cmp     dword ptr [rdx+6], 10141981h
0x18000969f  jnz     short loc_1800096B2
0x1800096a1  movzx   ecx, word ptr [rdx+0Ah]
0x1800096a5  add     rcx, 2Eh ; '.'
0x1800096a9  cmp     rax, rcx
0x1800096ac  jnb     loc_18000990C
0x1800096b2  cmp     word ptr [rbx], 0
0x1800096b6  jz      short loc_1800096DF
0x1800096b8  mov     rcx, rbx; pidl
0x1800096bb  call    cs:__imp_ILFindLastID
0x1800096c1  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x1800096c4  mov     rbp, rax
0x1800096c7  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x1800096cc  movzx   ecx, word ptr [rbp+0]
0x1800096d0  mov     rdx, rax
0x1800096d3  add     rbp, rcx
0x1800096d6  test    rax, rax
0x1800096d9  jnz     loc_180009A35
0x1800096df  cmp     word ptr [rbx], 0
0x1800096e3  mov     rbp, rbx
0x1800096e6  mov     eax, cs:PKEY_Null.pid
0x1800096ec  movups  xmm6, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x1800096f3  mov     [rsp+68h+var_48], eax
0x1800096f7  jz      loc_1800097D5
0x1800096fd  mov     rcx, rbx; pidl
0x180009700  call    cs:__imp_ILGetSize
0x180009706  mov     r13d, eax
0x180009709  lea     ecx, [r13+2Ah]; cb
0x18000970d  call    cs:__imp_CoTaskMemAlloc
0x180009713  mov     rbp, rax
0x180009716  test    rax, rax
0x180009719  jz      loc_1800097C7
0x18000971f  mov     rcx, rax; void *
0x180009722  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180009727  mov     r8, rax; Size
0x18000972a  xor     edx, edx; Val
0x18000972c  mov     rcx, rbp; void *
0x18000972f  call    memset_0
0x180009734  mov     r8d, r13d; Size
0x180009737  mov     rdx, rbx; Src
0x18000973a  mov     rcx, rbp; void *
0x18000973d  call    memcpy_0
0x180009742  mov     rcx, rbp; pidl
0x180009745  call    cs:__imp_ILFindLastID
0x18000974b  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000974e  mov     rdi, rax
0x180009751  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180009756  test    rax, rax
0x180009759  jz      loc_1800098B0
0x18000975f  movzx   eax, word ptr [rdi]
0x180009762  add     rax, 0FFFFFFFFFFFFFFFEh
0x180009766  add     rax, rdi
0x180009769  movzx   r8d, word ptr [rax]
0x18000976d  lea     edx, [r13-2]
0x180009771  mov     eax, [rsp+68h+var_48]
0x180009775  add     rdx, rbp
0x180009778  mov     dword ptr [rdx], 28h ; '('
0x18000977e  mov     dword ptr [rdx+4], 0BEEF0013h
0x180009785  mov     dword ptr [rdx+8], 20000000h
0x18000978c  movups  xmmword ptr [rdx+0Ch], xmm6
0x180009790  mov     [rdx+1Ch], eax
0x180009793  mov     dword ptr [rdx+20h], 0
0x18000979a  mov     [rdx+24h], r12d
0x18000979e  mov     word ptr [rdx], 2Ah ; '*'
0x1800097a3  movzx   eax, word ptr [rdi]
0x1800097a6  lea     ecx, [rax+2Ah]
0x1800097a9  cmp     cx, ax
0x1800097ac  jnb     short loc_1800097BB
0x1800097ae  mov     rcx, rbp; pv
0x1800097b1  call    cs:__imp_CoTaskMemFree
0x1800097b7  xor     ebp, ebp
0x1800097b9  jmp     short loc_1800097C7
0x1800097bb  mov     [rdi], cx
0x1800097be  movzx   eax, word ptr [rdx]
0x1800097c1  mov     [rax+rdx-2], r8w
0x1800097c7  mov     rcx, rbx; pidl
0x1800097ca  call    cs:__imp_ILFree
0x1800097d0  mov     r13d, [rsp+68h+var_44]
0x1800097d5  mov     rbx, rbp
0x1800097d8  test    rbp, rbp
0x1800097db  jz      loc_1800098DA
0x1800097e1  mov     rcx, rbp; pidl
0x1800097e4  call    cs:__imp_ILFindLastID
0x1800097ea  test    rax, rax
0x1800097ed  jz      short loc_180009811
0x1800097ef  movzx   ecx, word ptr [rax]
0x1800097f2  cmp     ecx, 2Eh ; '.'
0x1800097f5  jb      short loc_180009811
0x1800097f7  cmp     dword ptr [rax+6], 10141981h
0x1800097fe  jnz     short loc_180009811
0x180009800  movzx   edx, word ptr [rax+0Ah]
0x180009804  add     rdx, 2Eh ; '.'
0x180009808  cmp     rcx, rdx
0x18000980b  jnb     loc_180009994
0x180009811  xor     edi, edi
0x180009813  cmp     word ptr [rbp+0], 0
0x180009818  mov     esi, 80070057h
0x18000981d  jz      short loc_180009858
0x18000981f  mov     rcx, rbp; pidl
0x180009822  call    cs:__imp_ILFindLastID
0x180009828  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000982b  mov     rbp, rax
0x18000982e  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180009833  movzx   ecx, word ptr [rbp+0]
0x180009837  mov     rdx, rax
0x18000983a  add     rbp, rcx
0x18000983d  test    rax, rax
0x180009840  jz      short loc_180009858
0x180009842  cmp     dword ptr [rdx+4], 0BEEF0013h
0x180009849  lea     rcx, [rdx+8]
0x18000984d  jnz     loc_1800099CB
0x180009853  mov     rdi, rcx
0x180009856  xor     esi, esi
0x180009858  test    esi, esi
0x18000985a  js      short loc_1800098DA
0x18000985c  mov     ecx, [r15+10h]
0x180009860  movups  xmm0, xmmword ptr [rdi+4]
0x180009864  cmp     [rdi+14h], ecx
0x180009867  jz      short loc_1800098B8
0x180009869  test    ecx, ecx
0x18000986b  jz      loc_1800099A6
0x180009871  xor     r12d, r12d
0x180009874  mov     ecx, [rdi+1Ch]
0x180009877  mov     eax, ecx
0x180009879  btr     ecx, 0Ch
0x18000987d  bts     eax, 0Ch
0x180009881  test    r12d, r12d
0x180009884  cmovz   ecx, eax
0x180009887  mov     eax, ecx
0x180009889  btr     ecx, 0Dh
0x18000988d  bts     eax, 0Dh
0x180009891  cmp     r13d, 0FFFFFFFFh
0x180009895  cmovz   ecx, eax
0x180009898  mov     [rdi+1Ch], ecx
0x18000989b  movups  xmm0, xmmword ptr [r15]
0x18000989f  movups  xmmword ptr [rdi+4], xmm0
0x1800098a3  mov     ecx, [r15+10h]
0x1800098a7  mov     [rdi+14h], ecx
0x1800098aa  mov     [rdi+18h], r13d
0x1800098ae  jmp     short loc_1800098D5
0x1800098b0  mov     rax, rdi
0x1800098b3  jmp     loc_180009769
0x1800098b8  movq    rax, xmm0
0x1800098bd  sub     rax, [r15]
0x1800098c0  jnz     short loc_1800098D0
0x1800098c2  psrldq  xmm0, 8
0x1800098c7  movq    rax, xmm0
0x1800098cc  sub     rax, [r15+8]
0x1800098d0  test    rax, rax
0x1800098d3  jnz     short loc_180009869
0x1800098d5  mov     [r14], rbx
0x1800098d8  xor     ebx, ebx
0x1800098da  mov     rcx, rbx; pidl
0x1800098dd  call    cs:__imp_ILFree
0x1800098e3  movaps  xmm6, [rsp+68h+var_38]
0x1800098e8  mov     eax, esi
0x1800098ea  mov     r12, [rsp+68h+arg_18]
0x1800098f2  mov     rdi, [rsp+68h+arg_10]
0x1800098fa  mov     rbp, [rsp+68h+arg_0]
0x1800098ff  add     rsp, 40h
0x180009903  pop     r15
0x180009905  pop     r14
0x180009907  pop     r13
0x180009909  pop     rsi
0x18000990a  pop     rbx
0x18000990b  retn
0x18000990c  lea     rdi, [rdx+0Eh]
0x180009910  test    rdi, rdi
0x180009913  jnz     short loc_18000992D
0x180009915  jmp     loc_1800096B2
0x180009920  cmp     dword ptr [rdx+4], 0BEEF0013h
0x180009927  lea     rdi, [rdx+8]
0x18000992b  jnz     short loc_180009934
0x18000992d  xor     esi, esi
0x18000992f  jmp     loc_18000985C
0x180009934  xor     r8d, r8d
0x180009937  cmp     rdi, rbp
0x18000993a  ja      short loc_180009986
0x18000993c  movzx   ecx, word ptr [rdx]
0x18000993f  add     rcx, rdx
0x180009942  cmp     rcx, rbp
0x180009945  jz      loc_1800096DF
0x18000994b  ja      short loc_180009986
0x18000994d  lea     rax, [rcx+8]
0x180009951  cmp     rax, rbp
0x180009954  ja      loc_1800096DF
0x18000995a  mov     eax, [rcx+4]
0x18000995d  shr     rax, 10h
0x180009961  cmp     ax, r9w
0x180009965  jnz     loc_1800096DF
0x18000996b  movzx   eax, word ptr [rcx]
0x18000996e  add     rax, rcx
0x180009971  cmp     rax, rbp
0x180009974  ja      loc_1800096DF
0x18000997a  cmp     rcx, rdi
0x18000997d  jb      loc_1800096DF
0x180009983  mov     r8, rcx
0x180009986  mov     rdx, r8
0x180009989  test    r8, r8
0x18000998c  jz      loc_1800096DF
0x180009992  jmp     short loc_180009920
0x180009994  lea     rdi, [rax+0Eh]
0x180009998  test    rdi, rdi
0x18000999b  jz      loc_180009813
0x1800099a1  jmp     loc_180009856
0x1800099a6  mov     rax, [r15]
0x1800099a9  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data1
0x1800099b0  jnz     short loc_1800099BD
0x1800099b2  mov     rax, [r15+8]
0x1800099b6  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data4
0x1800099bd  test    rax, rax
0x1800099c0  jz      loc_180009874
0x1800099c6  jmp     loc_180009871
0x1800099cb  xor     r8d, r8d
0x1800099ce  cmp     rcx, rbp
0x1800099d1  ja      short loc_180009A24
0x1800099d3  movzx   r9d, word ptr [rdx]
0x1800099d7  add     r9, rdx
0x1800099da  cmp     r9, rbp
0x1800099dd  jz      loc_180009858
0x1800099e3  ja      short loc_180009A24
0x1800099e5  lea     rax, [r9+8]
0x1800099e9  cmp     rax, rbp
0x1800099ec  ja      loc_180009858
0x1800099f2  mov     eax, [r9+4]
0x1800099f6  mov     edx, 0BEEFh
0x1800099fb  shr     rax, 10h
0x1800099ff  cmp     ax, dx
0x180009a02  jnz     loc_180009858
0x180009a08  movzx   eax, word ptr [r9]
0x180009a0c  add     rax, r9
0x180009a0f  cmp     rax, rbp
0x180009a12  ja      loc_180009858
0x180009a18  cmp     r9, rcx
0x180009a1b  jb      loc_180009858
0x180009a21  mov     r8, r9
0x180009a24  mov     rdx, r8
0x180009a27  test    r8, r8
0x180009a2a  jz      loc_180009858
0x180009a30  jmp     loc_180009842
0x180009a35  mov     r9d, 0BEEFh
0x180009a3b  jmp     loc_180009920
0x180009a40  mov     eax, 80070057h
0x180009a45  jmp     loc_1800098FF
```

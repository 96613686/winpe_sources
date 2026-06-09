# CRepubEvictSegmentsTask::DeleteStagedContentRecord(void)

- ea: `0x1800688d0`
- end: `0x180068ad9`
- name: `?DeleteStagedContentRecord@CRepubEvictSegmentsTask@@AEAAKXZ`
- size: `521`
- prototype: `unsigned int __fastcall(CRepubEvictSegmentsTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x1800693e0`

## callees

- `0x180004374`
- `0x180008290`
- `0x18002b67c`
- `0x1800688d0`
- `0x18006b49c`
- `0x1800749f4`
- `0x180159010`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x180068986`
- `ESENT!JetRetrieveColumns` at `0x180068986`
- `ESENT!JetDelete` at `0x180068a24`
- `ESENT!JetDelete` at `0x180068a24`

## pseudocode

```c
__int64 __fastcall CRepubEvictSegmentsTask::DeleteStagedContentRecord(CRepubEvictSegmentsTask *this)
{
  unsigned int Columns; // edi
  CHostedCacheMsgEncoding *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  unsigned int updated; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  unsigned __int64 v9; // [rsp+40h] [rbp-10h] BYREF
  __int16 v10; // [rsp+80h] [rbp+30h] BYREF
  unsigned int cretrievecolumn; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v12; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v13; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 296, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  v9 = 0;
  v10 = 0;
  v12 = 0;
  cretrievecolumn = *((_DWORD *)this + 96);
  v13 = 0;
  CRepubEvictSegmentsTask::InitializeStagedContentTableRetrieveColumns(
    this,
    &v9,
    &v10,
    &v13,
    &v12,
    *((struct JET_RETRIEVECOLUMN **)this + 49),
    &cretrievecolumn);
  Columns = JetRetrieveColumns(
              *((_QWORD *)this + 47),
              *((_QWORD *)this + 66),
              *((JET_RETRIEVECOLUMN **)this + 49),
              cretrievecolumn);
  if ( Columns )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 297;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v3 + 12), v4, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, Columns);
LABEL_11:
    v5 = (*(__int64 (__fastcall **)(CRepubEvictSegmentsTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, Columns);
LABEL_26:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 12), 298, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v9, v10, v13);
  }
  Columns = JetDelete(*((_QWORD *)this + 47), *((_QWORD *)this + 66));
  if ( Columns )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 299;
    goto LABEL_10;
  }
  updated = CRepubEvictSegmentsTask::UpdateActualSpace(this, v10, v12, 0);
  v5 = updated;
  if ( !updated )
    goto LABEL_26;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 300, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, updated);
    goto LABEL_26;
  }
LABEL_27:
  if ( v7 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 108) & 4) != 0
    && *((_BYTE *)v7 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v7 + 12), 301, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1800688d0  push    rbp
0x1800688d2  push    rbx
0x1800688d3  push    rdi
0x1800688d4  push    r14
0x1800688d6  push    r15
0x1800688d8  mov     rbp, rsp
0x1800688db  sub     rsp, 50h
0x1800688df  mov     rbx, rcx
0x1800688e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800688e9  lea     r14, WPP_GLOBAL_Control
0x1800688f0  lea     r15, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800688f7  cmp     rcx, r14
0x1800688fa  jz      short loc_180068919
0x1800688fc  test    byte ptr [rcx+6Ch], 4
0x180068900  jz      short loc_180068919
0x180068902  cmp     byte ptr [rcx+69h], 4
0x180068906  jb      short loc_180068919
0x180068908  mov     rcx, [rcx+60h]
0x18006890c  mov     edx, 128h
0x180068911  mov     r8, r15
0x180068914  call    WPP_SF_
0x180068919  xor     eax, eax
0x18006891b  mov     [rbp+var_10], 0
0x180068923  mov     [rbp+arg_0], ax
0x180068927  lea     r9, [rbp+arg_18]; unsigned __int64 *
0x18006892b  mov     [rbp+arg_10], eax
0x18006892e  lea     r8, [rbp+arg_0]; __int16 *
0x180068932  mov     eax, [rbx+180h]
0x180068938  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x18006893c  mov     [rbp+cretrievecolumn], eax
0x18006893f  mov     rcx, rbx; this
0x180068942  lea     rax, [rbp+cretrievecolumn]
0x180068946  mov     [rbp+arg_18], 0
0x18006894e  mov     [rsp+50h+var_20], rax; unsigned int *
0x180068953  mov     rax, [rbx+188h]
0x18006895a  mov     [rsp+50h+var_28], rax; struct JET_RETRIEVECOLUMN *
0x18006895f  lea     rax, [rbp+arg_10]
0x180068963  mov     [rsp+50h+var_30], rax; unsigned int *
0x180068968  call    ?InitializeStagedContentTableRetrieveColumns@CRepubEvictSegmentsTask@@AEAAXPEA_KPEAF0PEAKPEAUJET_RETRIEVECOLUMN@@2@Z; CRepubEvictSegmentsTask::InitializeStagedContentTableRetrieveColumns(unsigned __int64 *,short *,unsigned __int64 *,ulong *,JET_RETRIEVECOLUMN *,ulong *)
0x18006896d  mov     rdx, [rbx+210h]; tableid
0x180068974  mov     rcx, [rbx+178h]; sesid
0x18006897b  mov     r9d, [rbp+cretrievecolumn]; cretrievecolumn
0x18006897f  mov     r8, [rbx+188h]; pretrievecolumn
0x180068986  call    cs:__imp_JetRetrieveColumns
0x18006898c  mov     edi, eax
0x18006898e  test    eax, eax
0x180068990  jz      short loc_1800689D6
0x180068992  mov     rcx, cs:WPP_GLOBAL_Control
0x180068999  cmp     rcx, r14
0x18006899c  jz      short loc_1800689BE
0x18006899e  test    byte ptr [rcx+6Ch], 4
0x1800689a2  jz      short loc_1800689BE
0x1800689a4  cmp     byte ptr [rcx+69h], 1
0x1800689a8  jb      short loc_1800689BE
0x1800689aa  mov     edx, 129h
0x1800689af  mov     rcx, [rcx+60h]
0x1800689b3  mov     r9d, edi
0x1800689b6  mov     r8, r15
0x1800689b9  call    WPP_SF_d
0x1800689be  mov     rax, [rbx]
0x1800689c1  mov     edx, edi
0x1800689c3  mov     rcx, rbx
0x1800689c6  mov     rax, [rax+30h]
0x1800689ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689cf  mov     ebx, eax
0x1800689d1  jmp     loc_180068A9F
0x1800689d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800689dd  cmp     rcx, r14
0x1800689e0  jz      short loc_180068A16
0x1800689e2  test    byte ptr [rcx+6Ch], 4
0x1800689e6  jz      short loc_180068A16
0x1800689e8  cmp     byte ptr [rcx+69h], 3
0x1800689ec  jb      short loc_180068A16
0x1800689ee  movsx   r8d, [rbp+arg_0]
0x1800689f3  mov     edx, 12Ah
0x1800689f8  mov     rax, [rbp+arg_18]
0x1800689fc  mov     r9, [rbp+var_10]
0x180068a00  mov     rcx, [rcx+60h]
0x180068a04  mov     [rsp+50h+var_28], rax
0x180068a09  mov     dword ptr [rsp+50h+var_30], r8d
0x180068a0e  mov     r8, r15
0x180068a11  call    WPP_SF_qDq
0x180068a16  mov     rdx, [rbx+210h]; tableid
0x180068a1d  mov     rcx, [rbx+178h]; sesid
0x180068a24  call    cs:__imp_JetDelete
0x180068a2a  mov     edi, eax
0x180068a2c  test    eax, eax
0x180068a2e  jz      short loc_180068A5A
0x180068a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a37  cmp     rcx, r14
0x180068a3a  jz      short loc_1800689BE
0x180068a3c  test    byte ptr [rcx+6Ch], 4
0x180068a40  jz      loc_1800689BE
0x180068a46  cmp     byte ptr [rcx+69h], 1
0x180068a4a  jb      loc_1800689BE
0x180068a50  mov     edx, 12Bh
0x180068a55  jmp     loc_1800689AF
0x180068a5a  mov     r8d, [rbp+arg_10]; unsigned __int64
0x180068a5e  xor     r9d, r9d; bool
0x180068a61  movzx   edx, [rbp+arg_0]; __int16
0x180068a65  mov     rcx, rbx; this
0x180068a68  call    ?UpdateActualSpace@CRepubEvictSegmentsTask@@IEAAKF_K_N@Z; CRepubEvictSegmentsTask::UpdateActualSpace(short,unsigned __int64,bool)
0x180068a6d  mov     ebx, eax
0x180068a6f  test    eax, eax
0x180068a71  jz      short loc_180068A9F
0x180068a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a7a  cmp     rcx, r14
0x180068a7d  jz      short loc_180068ACB
0x180068a7f  test    byte ptr [rcx+6Ch], 4
0x180068a83  jz      short loc_180068AA6
0x180068a85  cmp     byte ptr [rcx+69h], 4
0x180068a89  jb      short loc_180068AA6
0x180068a8b  mov     rcx, [rcx+60h]
0x180068a8f  mov     edx, 12Ch
0x180068a94  mov     r9d, eax
0x180068a97  mov     r8, r15
0x180068a9a  call    WPP_SF_d
0x180068a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180068aa6  cmp     rcx, r14
0x180068aa9  jz      short loc_180068ACB
0x180068aab  test    byte ptr [rcx+6Ch], 4
0x180068aaf  jz      short loc_180068ACB
0x180068ab1  cmp     byte ptr [rcx+69h], 4
0x180068ab5  jb      short loc_180068ACB
0x180068ab7  mov     rcx, [rcx+60h]
0x180068abb  mov     edx, 12Dh
0x180068ac0  mov     r9d, ebx
0x180068ac3  mov     r8, r15
0x180068ac6  call    WPP_SF_d
0x180068acb  mov     eax, ebx
0x180068acd  add     rsp, 50h
0x180068ad1  pop     r15
0x180068ad3  pop     r14
0x180068ad5  pop     rdi
0x180068ad6  pop     rbx
0x180068ad7  pop     rbp
0x180068ad8  retn
```

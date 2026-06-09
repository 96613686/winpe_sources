# ESESession::OpenTable(_INDEXTABLE_ID)

- ea: `0x180017b04`
- end: `0x180017d19`
- name: `?OpenTable@ESESession@@QEAAJW4_INDEXTABLE_ID@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x180016b68`
- `0x1800173c4`
- `0x180017638`
- `0x180017f74`
- `0x1800180c4`
- `0x18001bce0`
- `0x18001cf00`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x18000c618`
- `0x180010638`
- `0x1800178b0`
- `0x1800179c8`
- `0x180017b04`
- `0x18002120a`
- `0x180021240`

## import_xrefs

- `ESENT!JetGetTableColumnInfoA` at `0x180017c8f`
- `ESENT!JetGetTableColumnInfoA` at `0x180017c8f`
- `ESENT!JetOpenTableA` at `0x180017b8f`
- `ESENT!JetOpenTableA` at `0x180017b8f`

## string_xrefs

- `0x180017b4a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017c1d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180017cb5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::OpenTable(__int64 a1, int a2)
{
  __int64 v2; // r14
  __int64 v4; // rsi
  JET_TABLEID *ptableid; // r12
  JET_PCSTR *IndexDataFromTableId; // rax
  JET_ERR v7; // eax
  __int64 v8; // rcx
  int v9; // ebp
  __int64 v10; // rdi
  __int64 TableDefinitionFromTableId; // rax
  __int64 v12; // r14
  __int64 v13; // r13
  __int64 v14; // rcx
  void **v15; // r15
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rbp
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 i; // rsi
  __int64 v23; // r8
  JET_TABLEID v24; // rdx
  JET_SESID v25; // rcx
  JET_ERR TableColumnInfoA; // eax
  unsigned int HresultFromJetError; // eax
  _DWORD pvResult[8]; // [rsp+40h] [rbp-68h] BYREF

  v2 = a2;
  v4 = 48LL * a2;
  ptableid = (JET_TABLEID *)(v4 + a1 + 112);
  if ( *ptableid != -1 )
    return 0;
  if ( *(_DWORD *)(a1 + 352) )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1077);
  IndexDataFromTableId = (JET_PCSTR *)GetIndexDataFromTableId((unsigned int)v2);
  v7 = JetOpenTableA(*(_QWORD *)(a1 + 56), *(_DWORD *)(a1 + 24), *IndexDataFromTableId, 0, 0, 0x10000u, ptableid);
  v9 = v7;
  if ( v7 == -1305 )
  {
    Log_AssertionEvent(
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1093);
LABEL_22:
    HresultFromJetError = MakeHresultFromJetError(v9);
    v21 = 1094;
LABEL_23:
    v19 = HresultFromJetError;
    v20 = HresultFromJetError;
    goto LABEL_24;
  }
  if ( v7 < 0 )
    goto LABEL_22;
  if ( *ptableid == -1 )
    Log_AssertionEvent(
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      1095);
  v10 = 6 * (v2 + 3);
  if ( *(_DWORD *)(a1 + 48 * (v2 + 3)) )
    return 0;
  TableDefinitionFromTableId = GetTableDefinitionFromTableId((unsigned int)v2);
  v12 = v4 + a1;
  v13 = TableDefinitionFromTableId;
  v14 = *(_QWORD *)(v4 + a1 + 120);
  v15 = (void **)(v4 + a1 + 128);
  v16 = *(unsigned int *)(TableDefinitionFromTableId + 24);
  v17 = ((__int64)*v15 - v14) >> 2;
  if ( v16 <= v17 )
  {
    v18 = v14 + 4 * v16;
    goto LABEL_14;
  }
  if ( (unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::reserve(
                          v12 + 120,
                          *(unsigned int *)(TableDefinitionFromTableId + 24)) )
  {
    memset_0(*v15, 0, 4 * (v16 - v17));
    v18 = *(_QWORD *)(v12 + 120) + 4 * v16;
LABEL_14:
    *v15 = (void *)v18;
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v13 + 24); i = (unsigned int)(i + 1) )
    {
      v23 = *(_QWORD *)(v13 + 16);
      v24 = *ptableid;
      v25 = *(_QWORD *)(a1 + 56);
      memset(pvResult, 0, 28);
      TableColumnInfoA = JetGetTableColumnInfoA(
                           v25,
                           v24,
                           *(JET_PCSTR *)(32LL * (unsigned int)i + v23 + 8),
                           pvResult,
                           0x1Cu,
                           0);
      if ( TableColumnInfoA < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(TableColumnInfoA);
        v21 = 1115;
        goto LABEL_23;
      }
      *(_DWORD *)(*(_QWORD *)(v12 + 120) + 4 * i) = pvResult[1];
    }
    *(_DWORD *)(a1 + 8 * v10) = 1;
    return 0;
  }
  v19 = -2147024882;
  v20 = 2147942414LL;
  v21 = 1102;
LABEL_24:
  Log_HREvent(
    v20,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
    v21);
  return v19;
}

```

## disassembly

```asm
0x180017b04  mov     [rsp+arg_10], rbx
0x180017b09  push    rbp
0x180017b0a  push    rsi
0x180017b0b  push    rdi
0x180017b0c  push    r12
0x180017b0e  push    r13
0x180017b10  push    r14
0x180017b12  push    r15
0x180017b14  sub     rsp, 70h
0x180017b18  mov     rax, cs:__security_cookie
0x180017b1f  xor     rax, rsp
0x180017b22  mov     [rsp+0A8h+var_48], rax
0x180017b27  movsxd  r14, edx
0x180017b2a  lea     r12, [rcx+70h]
0x180017b2e  mov     rbx, rcx
0x180017b31  lea     rsi, [r14+r14*2]
0x180017b35  shl     rsi, 4
0x180017b39  add     r12, rsi
0x180017b3c  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180017b41  jnz     loc_180017CC5
0x180017b47  xor     r13d, r13d
0x180017b4a  lea     r15, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017b51  cmp     [rcx+160h], r13d
0x180017b58  jz      short loc_180017B68
0x180017b5a  mov     r8d, 435h
0x180017b60  mov     rdx, r15
0x180017b63  call    Log_AssertionEvent
0x180017b68  mov     ecx, r14d
0x180017b6b  call    ?GetIndexDataFromTableId@@YAPEBU_IndexSourceData@IndexedFiltering@@W4_INDEXTABLE_ID@@@Z; GetIndexDataFromTableId(_INDEXTABLE_ID)
0x180017b70  mov     edx, [rbx+18h]; dbid
0x180017b73  xor     r9d, r9d; pvParameters
0x180017b76  mov     rcx, [rbx+38h]; sesid
0x180017b7a  mov     [rsp+0A8h+ptableid], r12; ptableid
0x180017b7f  mov     r8, [rax]; szTableName
0x180017b82  mov     [rsp+0A8h+grbit], 10000h; grbit
0x180017b8a  mov     [rsp+0A8h+cbParameters], r13d; cbParameters
0x180017b8f  call    cs:__imp_JetOpenTableA
0x180017b95  mov     ebp, eax
0x180017b97  cmp     eax, 0FFFFFAE7h
0x180017b9c  jz      loc_180017CEC
0x180017ba2  test    eax, eax
0x180017ba4  js      loc_180017CFA
0x180017baa  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180017baf  jnz     short loc_180017BBF
0x180017bb1  mov     r8d, 447h
0x180017bb7  mov     rdx, r15
0x180017bba  call    Log_AssertionEvent
0x180017bbf  lea     rdi, [r14+3]
0x180017bc3  lea     rdi, [rdi+rdi*2]
0x180017bc7  add     rdi, rdi
0x180017bca  cmp     [rbx+rdi*8], r13d
0x180017bce  jnz     loc_180017CC5
0x180017bd4  mov     ecx, r14d
0x180017bd7  call    ?GetTableDefinitionFromTableId@@YAPEBUDatabaseTableDefinition@@W4_INDEXTABLE_ID@@@Z; GetTableDefinitionFromTableId(_INDEXTABLE_ID)
0x180017bdc  lea     r14, [rsi+rbx]
0x180017be0  mov     r13, rax
0x180017be3  mov     rcx, [r14+78h]
0x180017be7  lea     r15, [r14+80h]
0x180017bee  mov     rbp, [r15]
0x180017bf1  mov     esi, [rax+18h]
0x180017bf4  sub     rbp, rcx
0x180017bf7  sar     rbp, 2
0x180017bfb  cmp     rsi, rbp
0x180017bfe  ja      short loc_180017C06
0x180017c00  lea     rcx, [rcx+rsi*4]
0x180017c04  jmp     short loc_180017C4B
0x180017c06  mov     rdx, rsi
0x180017c09  lea     rcx, [r14+78h]
0x180017c0d  call    ?reserve@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::reserve(unsigned __int64)
0x180017c12  xor     edx, edx; Val
0x180017c14  test    al, al
0x180017c16  jnz     short loc_180017C31
0x180017c18  mov     ebx, 8007000Eh
0x180017c1d  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017c24  mov     ecx, ebx
0x180017c26  mov     r9d, 44Eh
0x180017c2c  jmp     loc_180017D10
0x180017c31  mov     rcx, [r15]; void *
0x180017c34  mov     r8, rsi
0x180017c37  sub     r8, rbp
0x180017c3a  shl     r8, 2; Size
0x180017c3e  call    memset_0
0x180017c43  mov     rax, [r14+78h]
0x180017c47  lea     rcx, [rax+rsi*4]
0x180017c4b  mov     [r15], rcx
0x180017c4e  xor     esi, esi
0x180017c50  cmp     esi, [r13+18h]
0x180017c54  jnb     short loc_180017CBE
0x180017c56  mov     r8, [r13+10h]
0x180017c5a  lea     r9, [rsp+0A8h+pvResult]; pvResult
0x180017c5f  mov     rdx, [r12]; tableid
0x180017c63  xorps   xmm0, xmm0
0x180017c66  mov     rcx, [rbx+38h]; sesid
0x180017c6a  movups  xmmword ptr [rsp+0A8h+pvResult], xmm0
0x180017c6f  mov     eax, esi
0x180017c71  shl     rax, 5
0x180017c75  movups  xmmword ptr [rsp+0A8h+pvResult+0Ch], xmm0
0x180017c7a  mov     [rsp+0A8h+grbit], 0; InfoLevel
0x180017c82  mov     [rsp+0A8h+cbParameters], 1Ch; cbMax
0x180017c8a  mov     r8, [rax+r8+8]; szColumnName
0x180017c8f  call    cs:__imp_JetGetTableColumnInfoA
0x180017c95  test    eax, eax
0x180017c97  js      short loc_180017CA8
0x180017c99  mov     rcx, [r14+78h]
0x180017c9d  mov     eax, [rsp+0A8h+pvResult+4]
0x180017ca1  mov     [rcx+rsi*4], eax
0x180017ca4  inc     esi
0x180017ca6  jmp     short loc_180017C50
0x180017ca8  mov     ecx, eax; int
0x180017caa  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017caf  mov     r9d, 45Bh
0x180017cb5  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017cbc  jmp     short loc_180017D0A
0x180017cbe  mov     dword ptr [rbx+rdi*8], 1
0x180017cc5  xor     eax, eax
0x180017cc7  mov     rcx, [rsp+0A8h+var_48]
0x180017ccc  xor     rcx, rsp; StackCookie
0x180017ccf  call    __security_check_cookie
0x180017cd4  mov     rbx, [rsp+0A8h+arg_10]
0x180017cdc  add     rsp, 70h
0x180017ce0  pop     r15
0x180017ce2  pop     r14
0x180017ce4  pop     r13
0x180017ce6  pop     r12
0x180017ce8  pop     rdi
0x180017ce9  pop     rsi
0x180017cea  pop     rbp
0x180017ceb  retn
0x180017cec  mov     r8d, 445h
0x180017cf2  mov     rdx, r15
0x180017cf5  call    Log_AssertionEvent
0x180017cfa  mov     ecx, ebp; int
0x180017cfc  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180017d01  mov     r9d, 446h
0x180017d07  mov     r8, r15
0x180017d0a  mov     ebx, eax
0x180017d0c  xor     edx, edx
0x180017d0e  mov     ecx, eax
0x180017d10  call    Log_HREvent
0x180017d15  mov     eax, ebx
0x180017d17  jmp     short loc_180017CC7
```

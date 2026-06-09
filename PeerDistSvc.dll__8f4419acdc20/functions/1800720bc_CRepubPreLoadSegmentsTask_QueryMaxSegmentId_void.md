# CRepubPreLoadSegmentsTask::QueryMaxSegmentId(void)

- ea: `0x1800720bc`
- end: `0x1800722a0`
- name: `?QueryMaxSegmentId@CRepubPreLoadSegmentsTask@@IEAAKXZ`
- size: `484`
- prototype: `unsigned int __fastcall(CRepubPreLoadSegmentsTask *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18006e290`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800720bc`
- `0x180159010`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800721f3`
- `ESENT!JetRetrieveColumns` at `0x1800721f3`
- `ESENT!JetMove` at `0x180072170`
- `ESENT!JetMove` at `0x180072247`
- `ESENT!JetMove` at `0x180072170`
- `ESENT!JetMove` at `0x180072247`
- `ESENT!JetSetCurrentIndexW` at `0x180072117`
- `ESENT!JetSetCurrentIndexW` at `0x180072117`

## pseudocode

```c
__int64 __fastcall CRepubPreLoadSegmentsTask::QueryMaxSegmentId(CRepubPreLoadSegmentsTask *this)
{
  unsigned int Columns; // esi
  CHostedCacheMsgEncoding *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  int v7; // ecx
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // ebp

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 575, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  Columns = JetSetCurrentIndexW(*((_QWORD *)this + 47), *((_QWORD *)this + 54), L"SegmentIdIndex");
  if ( Columns )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 576;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v3 + 12), v4, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, Columns);
LABEL_11:
    v5 = Columns;
    return (*(unsigned int (__fastcall **)(CRepubPreLoadSegmentsTask *, __int64))(*(_QWORD *)this + 48LL))(this, v5);
  }
  Columns = JetMove(*((_QWORD *)this + 47), *((_QWORD *)this + 54), 0x7FFFFFFF, 1u);
  if ( Columns )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 577;
    goto LABEL_10;
  }
  v6 = *((_QWORD *)this + 49);
  v7 = *(_DWORD *)(*((_QWORD *)this + 52) + 812LL);
  *(_OWORD *)v6 = 0;
  *(_OWORD *)(v6 + 16) = 0;
  *(_OWORD *)(v6 + 32) = 0;
  *(_DWORD *)v6 = v7;
  *(_DWORD *)(v6 + 16) = 8;
  *(_QWORD *)(v6 + 8) = (char *)this + 472;
  *(_DWORD *)(v6 + 32) = 1;
  Columns = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 54), *((JET_RETRIEVECOLUMN **)this + 49), 1u);
  if ( Columns )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v4 = 578;
    goto LABEL_10;
  }
  v8 = 0;
  v9 = JetMove(*((_QWORD *)this + 47), *((_QWORD *)this + 54), 0x80000000, 1u);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 579, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v9);
    }
    v5 = v10;
    return (*(unsigned int (__fastcall **)(CRepubPreLoadSegmentsTask *, __int64))(*(_QWORD *)this + 48LL))(this, v5);
  }
  return v8;
}

```

## disassembly

```asm
0x1800720bc  push    rbx
0x1800720be  push    rbp
0x1800720bf  push    rsi
0x1800720c0  push    r12
0x1800720c2  push    r15
0x1800720c4  sub     rsp, 20h
0x1800720c8  mov     rbx, rcx
0x1800720cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800720d2  lea     r15, WPP_GLOBAL_Control
0x1800720d9  lea     r12, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800720e0  cmp     rcx, r15
0x1800720e3  jz      short loc_180072102
0x1800720e5  test    byte ptr [rcx+6Ch], 4
0x1800720e9  jz      short loc_180072102
0x1800720eb  cmp     byte ptr [rcx+69h], 4
0x1800720ef  jb      short loc_180072102
0x1800720f1  mov     rcx, [rcx+60h]
0x1800720f5  mov     edx, 23Fh
0x1800720fa  mov     r8, r12
0x1800720fd  call    WPP_SF_
0x180072102  mov     r8, cs:off_1801612C8; szIndexName
0x180072109  mov     rdx, [rbx+1B0h]; tableid
0x180072110  mov     rcx, [rbx+178h]; sesid
0x180072117  call    cs:__imp_JetSetCurrentIndexW
0x18007211d  mov     esi, eax
0x18007211f  test    eax, eax
0x180072121  jz      short loc_180072156
0x180072123  mov     rcx, cs:WPP_GLOBAL_Control
0x18007212a  cmp     rcx, r15
0x18007212d  jz      short loc_18007214F
0x18007212f  test    byte ptr [rcx+6Ch], 4
0x180072133  jz      short loc_18007214F
0x180072135  cmp     byte ptr [rcx+69h], 1
0x180072139  jb      short loc_18007214F
0x18007213b  mov     edx, 240h
0x180072140  mov     rcx, [rcx+60h]
0x180072144  mov     r9d, esi
0x180072147  mov     r8, r12
0x18007214a  call    WPP_SF_d
0x18007214f  mov     edx, esi
0x180072151  jmp     loc_180072281
0x180072156  mov     rdx, [rbx+1B0h]; tableid
0x18007215d  mov     r9d, 1; grbit
0x180072163  mov     rcx, [rbx+178h]; sesid
0x18007216a  mov     r8d, 7FFFFFFFh; cRow
0x180072170  call    cs:__imp_JetMove
0x180072176  mov     esi, eax
0x180072178  test    eax, eax
0x18007217a  jz      short loc_18007219B
0x18007217c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072183  cmp     rcx, r15
0x180072186  jz      short loc_18007214F
0x180072188  test    byte ptr [rcx+6Ch], 4
0x18007218c  jz      short loc_18007214F
0x18007218e  cmp     byte ptr [rcx+69h], 1
0x180072192  jb      short loc_18007214F
0x180072194  mov     edx, 241h
0x180072199  jmp     short loc_180072140
0x18007219b  mov     rax, [rbx+1A0h]
0x1800721a2  xorps   xmm0, xmm0
0x1800721a5  mov     rdx, [rbx+188h]
0x1800721ac  mov     r9d, 1; cretrievecolumn
0x1800721b2  mov     ecx, [rax+32Ch]
0x1800721b8  lea     rax, [rbx+1D8h]
0x1800721bf  movups  xmmword ptr [rdx], xmm0
0x1800721c2  movups  xmmword ptr [rdx+10h], xmm0
0x1800721c6  movups  xmmword ptr [rdx+20h], xmm0
0x1800721ca  mov     [rdx], ecx
0x1800721cc  mov     dword ptr [rdx+10h], 8
0x1800721d3  mov     [rdx+8], rax
0x1800721d7  mov     dword ptr [rdx+20h], 1
0x1800721de  mov     r8, [rbx+188h]; pretrievecolumn
0x1800721e5  mov     rdx, [rbx+1B0h]; tableid
0x1800721ec  mov     rcx, [rbx+178h]; sesid
0x1800721f3  call    cs:__imp_JetRetrieveColumns
0x1800721f9  mov     esi, eax
0x1800721fb  test    eax, eax
0x1800721fd  jz      short loc_18007222D
0x1800721ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180072206  cmp     rcx, r15
0x180072209  jz      loc_18007214F
0x18007220f  test    byte ptr [rcx+6Ch], 4
0x180072213  jz      loc_18007214F
0x180072219  cmp     byte ptr [rcx+69h], 1
0x18007221d  jb      loc_18007214F
0x180072223  mov     edx, 242h
0x180072228  jmp     loc_180072140
0x18007222d  mov     rdx, [rbx+1B0h]; tableid
0x180072234  xor     esi, esi
0x180072236  mov     rcx, [rbx+178h]; sesid
0x18007223d  mov     r8d, 80000000h; cRow
0x180072243  lea     r9d, [rsi+1]; grbit
0x180072247  call    cs:__imp_JetMove
0x18007224d  mov     ebp, eax
0x18007224f  test    eax, eax
0x180072251  jz      short loc_180072292
0x180072253  mov     rcx, cs:WPP_GLOBAL_Control
0x18007225a  cmp     rcx, r15
0x18007225d  jz      short loc_18007227F
0x18007225f  test    byte ptr [rcx+6Ch], 4
0x180072263  jz      short loc_18007227F
0x180072265  cmp     byte ptr [rcx+69h], 1
0x180072269  jb      short loc_18007227F
0x18007226b  mov     rcx, [rcx+60h]
0x18007226f  mov     edx, 243h
0x180072274  mov     r9d, eax
0x180072277  mov     r8, r12
0x18007227a  call    WPP_SF_d
0x18007227f  mov     edx, ebp
0x180072281  mov     rax, [rbx]
0x180072284  mov     rcx, rbx
0x180072287  mov     rax, [rax+30h]
0x18007228b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072290  mov     esi, eax
0x180072292  mov     eax, esi
0x180072294  add     rsp, 20h
0x180072298  pop     r15
0x18007229a  pop     r12
0x18007229c  pop     rsi
0x18007229d  pop     rbp
0x18007229e  pop     rbx
0x18007229f  retn
```

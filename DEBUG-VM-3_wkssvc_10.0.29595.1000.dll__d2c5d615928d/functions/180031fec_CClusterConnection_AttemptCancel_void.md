# CClusterConnection::AttemptCancel(void)

- ea: `0x180031fec`
- end: `0x180032098`
- name: `?AttemptCancel@CClusterConnection@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(CClusterConnection *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c82c`
- `0x18001cf24`

## callees

- `0x180023694`
- `0x180031ba0`
- `0x180031fec`

## import_xrefs

- `RPCRT4!RpcAsyncCancelCall` at `0x180032014`
- `RPCRT4!RpcAsyncCancelCall` at `0x180032014`

## pseudocode

```c
void __fastcall CClusterConnection::AttemptCancel(CClusterConnection *this)
{
  RPC_STATUS v2; // eax

  if ( *((_DWORD *)this + 53) )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_q(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 21, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids, this);
    }
  }
  else
  {
    *((_DWORD *)this + 53) = 1;
    v2 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 280), 1);
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        20,
        &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids,
        this,
        v2);
    }
  }
}

```

## disassembly

```asm
0x180031fec  push    rbx
0x180031fee  sub     rsp, 30h
0x180031ff2  cmp     dword ptr [rcx+0D4h], 0
0x180031ff9  mov     rbx, rcx
0x180031ffc  jnz     short loc_18003205B
0x180031ffe  mov     dword ptr [rcx+0D4h], 1
0x180032008  mov     edx, 1; fAbort
0x18003200d  add     rcx, 118h; pAsync
0x180032014  call    cs:__imp_RpcAsyncCancelCall
0x18003201a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180032021  lea     rdx, WPP_witness_GLOBAL_Control
0x180032028  cmp     rcx, rdx
0x18003202b  jz      short loc_180032092
0x18003202d  test    byte ptr [rcx+1Ch], 1
0x180032031  jz      short loc_180032092
0x180032033  cmp     byte ptr [rcx+19h], 3
0x180032037  jb      short loc_180032092
0x180032039  mov     rcx, [rcx+10h]
0x18003203d  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x180032044  mov     edx, 14h
0x180032049  mov     [rsp+38h+var_18], eax
0x18003204d  mov     r9, rbx
0x180032050  call    WPP_SF_qd
0x180032055  add     rsp, 30h
0x180032059  pop     rbx
0x18003205a  retn
0x18003205b  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180032062  lea     rdx, WPP_witness_GLOBAL_Control
0x180032069  cmp     rcx, rdx
0x18003206c  jz      short loc_180032092
0x18003206e  test    byte ptr [rcx+1Ch], 1
0x180032072  jz      short loc_180032092
0x180032074  cmp     byte ptr [rcx+19h], 3
0x180032078  jb      short loc_180032092
0x18003207a  mov     rcx, [rcx+10h]
0x18003207e  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x180032085  mov     edx, 15h
0x18003208a  mov     r9, rbx
0x18003208d  call    WPP_SF_q
0x180032092  add     rsp, 30h
0x180032096  pop     rbx
0x180032097  retn
```

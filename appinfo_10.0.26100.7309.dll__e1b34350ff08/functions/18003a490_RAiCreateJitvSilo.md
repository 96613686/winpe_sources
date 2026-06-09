# RAiCreateJitvSilo

- ea: `0x18003a490`
- end: `0x18003a54e`
- name: `RAiCreateJitvSilo`
- size: `190`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002cc58`
- `0x18003a490`
- `0x18003c20c`
- `0x18003c274`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a52e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a52e`

## pseudocode

```c
RPC_STATUS __fastcall RAiCreateJitvSilo(PRPC_ASYNC_STATE pAsync, void *a2, unsigned __int16 *a3, unsigned int *a4)
{
  int DesktopJitvSilo; // eax
  int v9; // r8d
  int v10; // ebx
  int v11; // eax
  int Reply; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids, a3);
  DesktopJitvSilo = CreateDesktopJitvSilo(a2, a3, a4);
  v10 = DesktopJitvSilo;
  if ( DesktopJitvSilo < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v9, (_DWORD)a3, DesktopJitvSilo);
  }
  v11 = (unsigned __int16)v10;
  if ( v10 >= 0 )
    v11 = 0;
  Reply = v11;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x18003a490  mov     [rsp+arg_0], rbx
0x18003a495  mov     [rsp+arg_8], rbp
0x18003a49a  push    rsi
0x18003a49b  push    rdi
0x18003a49c  push    r14
0x18003a49e  sub     rsp, 30h
0x18003a4a2  mov     rbx, r9
0x18003a4a5  mov     rdi, r8
0x18003a4a8  mov     rsi, rdx
0x18003a4ab  mov     rbp, rcx
0x18003a4ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4b5  lea     r14, WPP_GLOBAL_Control
0x18003a4bc  cmp     rcx, r14
0x18003a4bf  jz      short loc_18003A4DF
0x18003a4c1  test    byte ptr [rcx+1Ch], 1
0x18003a4c5  jz      short loc_18003A4DF
0x18003a4c7  mov     rcx, [rcx+10h]
0x18003a4cb  mov     r9, r8
0x18003a4ce  lea     r8, WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids
0x18003a4d5  mov     edx, 24h ; '$'
0x18003a4da  call    WPP_SF_S
0x18003a4df  mov     r8, rbx; unsigned int *
0x18003a4e2  mov     rdx, rdi; unsigned __int16 *
0x18003a4e5  mov     rcx, rsi; void *
0x18003a4e8  call    ?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z; CreateDesktopJitvSilo(void *,ushort const *,ulong *)
0x18003a4ed  xor     esi, esi
0x18003a4ef  mov     ebx, eax
0x18003a4f1  test    eax, eax
0x18003a4f3  jns     short loc_18003A51A
0x18003a4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4fc  cmp     rcx, r14
0x18003a4ff  jz      short loc_18003A51A
0x18003a501  test    byte ptr [rcx+1Ch], 1
0x18003a505  jz      short loc_18003A51A
0x18003a507  mov     rcx, [rcx+10h]
0x18003a50b  lea     edx, [rsi+25h]
0x18003a50e  mov     r9, rdi
0x18003a511  mov     [rsp+48h+var_28], eax
0x18003a515  call    WPP_SF_SD
0x18003a51a  test    ebx, ebx
0x18003a51c  movzx   eax, bx
0x18003a51f  lea     rdx, [rsp+48h+Reply]; Reply
0x18003a524  mov     rcx, rbp; pAsync
0x18003a527  cmovns  eax, esi
0x18003a52a  mov     [rsp+48h+Reply], eax
0x18003a52e  call    cs:__imp_RpcAsyncCompleteCall
0x18003a535  nop     dword ptr [rax+rax+00h]
0x18003a53a  mov     rbx, [rsp+48h+arg_0]
0x18003a53f  mov     rbp, [rsp+48h+arg_8]
0x18003a544  add     rsp, 30h
0x18003a548  pop     r14
0x18003a54a  pop     rdi
0x18003a54b  pop     rsi
0x18003a54c  retn
```

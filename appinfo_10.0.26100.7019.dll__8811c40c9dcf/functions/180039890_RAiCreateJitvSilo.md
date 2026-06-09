# RAiCreateJitvSilo

- ea: `0x180039890`
- end: `0x18003994e`
- name: `RAiCreateJitvSilo`
- size: `190`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002e278`
- `0x180039890`
- `0x18003b5cc`
- `0x18003b634`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003992e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003992e`

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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids, a3);
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
0x180039890  mov     [rsp+arg_0], rbx
0x180039895  mov     [rsp+arg_8], rbp
0x18003989a  push    rsi
0x18003989b  push    rdi
0x18003989c  push    r14
0x18003989e  sub     rsp, 30h
0x1800398a2  mov     rbx, r9
0x1800398a5  mov     rdi, r8
0x1800398a8  mov     rsi, rdx
0x1800398ab  mov     rbp, rcx
0x1800398ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398b5  lea     r14, WPP_GLOBAL_Control
0x1800398bc  cmp     rcx, r14
0x1800398bf  jz      short loc_1800398DF
0x1800398c1  test    byte ptr [rcx+1Ch], 1
0x1800398c5  jz      short loc_1800398DF
0x1800398c7  mov     rcx, [rcx+10h]
0x1800398cb  mov     r9, r8
0x1800398ce  lea     r8, WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids
0x1800398d5  mov     edx, 24h ; '$'
0x1800398da  call    WPP_SF_S
0x1800398df  mov     r8, rbx; unsigned int *
0x1800398e2  mov     rdx, rdi; unsigned __int16 *
0x1800398e5  mov     rcx, rsi; void *
0x1800398e8  call    ?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z; CreateDesktopJitvSilo(void *,ushort const *,ulong *)
0x1800398ed  xor     esi, esi
0x1800398ef  mov     ebx, eax
0x1800398f1  test    eax, eax
0x1800398f3  jns     short loc_18003991A
0x1800398f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800398fc  cmp     rcx, r14
0x1800398ff  jz      short loc_18003991A
0x180039901  test    byte ptr [rcx+1Ch], 1
0x180039905  jz      short loc_18003991A
0x180039907  mov     rcx, [rcx+10h]
0x18003990b  lea     edx, [rsi+25h]
0x18003990e  mov     r9, rdi
0x180039911  mov     [rsp+48h+var_28], eax
0x180039915  call    WPP_SF_SD
0x18003991a  test    ebx, ebx
0x18003991c  movzx   eax, bx
0x18003991f  lea     rdx, [rsp+48h+Reply]; Reply
0x180039924  mov     rcx, rbp; pAsync
0x180039927  cmovns  eax, esi
0x18003992a  mov     [rsp+48h+Reply], eax
0x18003992e  call    cs:__imp_RpcAsyncCompleteCall
0x180039935  nop     dword ptr [rax+rax+00h]
0x18003993a  mov     rbx, [rsp+48h+arg_0]
0x18003993f  mov     rbp, [rsp+48h+arg_8]
0x180039944  add     rsp, 30h
0x180039948  pop     r14
0x18003994a  pop     rdi
0x18003994b  pop     rsi
0x18003994c  retn
```

# RAiCreateJitvSilo

- ea: `0x18003a810`
- end: `0x18003a8ce`
- name: `RAiCreateJitvSilo`
- size: `190`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002cd28`
- `0x18003a810`
- `0x18003c74c`
- `0x18003c7b4`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a8ae`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a8ae`

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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids, a3);
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
0x18003a810  mov     [rsp+arg_0], rbx
0x18003a815  mov     [rsp+arg_8], rbp
0x18003a81a  push    rsi
0x18003a81b  push    rdi
0x18003a81c  push    r14
0x18003a81e  sub     rsp, 30h
0x18003a822  mov     rbx, r9
0x18003a825  mov     rdi, r8
0x18003a828  mov     rsi, rdx
0x18003a82b  mov     rbp, rcx
0x18003a82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a835  lea     r14, WPP_GLOBAL_Control
0x18003a83c  cmp     rcx, r14
0x18003a83f  jz      short loc_18003A85F
0x18003a841  test    byte ptr [rcx+1Ch], 1
0x18003a845  jz      short loc_18003A85F
0x18003a847  mov     rcx, [rcx+10h]
0x18003a84b  mov     r9, r8
0x18003a84e  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x18003a855  mov     edx, 24h ; '$'
0x18003a85a  call    WPP_SF_S
0x18003a85f  mov     r8, rbx; unsigned int *
0x18003a862  mov     rdx, rdi; unsigned __int16 *
0x18003a865  mov     rcx, rsi; void *
0x18003a868  call    ?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z; CreateDesktopJitvSilo(void *,ushort const *,ulong *)
0x18003a86d  xor     esi, esi
0x18003a86f  mov     ebx, eax
0x18003a871  test    eax, eax
0x18003a873  jns     short loc_18003A89A
0x18003a875  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a87c  cmp     rcx, r14
0x18003a87f  jz      short loc_18003A89A
0x18003a881  test    byte ptr [rcx+1Ch], 1
0x18003a885  jz      short loc_18003A89A
0x18003a887  mov     rcx, [rcx+10h]
0x18003a88b  lea     edx, [rsi+25h]
0x18003a88e  mov     r9, rdi
0x18003a891  mov     [rsp+48h+var_28], eax
0x18003a895  call    WPP_SF_SD
0x18003a89a  test    ebx, ebx
0x18003a89c  movzx   eax, bx
0x18003a89f  lea     rdx, [rsp+48h+Reply]; Reply
0x18003a8a4  mov     rcx, rbp; pAsync
0x18003a8a7  cmovns  eax, esi
0x18003a8aa  mov     [rsp+48h+Reply], eax
0x18003a8ae  call    cs:__imp_RpcAsyncCompleteCall
0x18003a8b5  nop     dword ptr [rax+rax+00h]
0x18003a8ba  mov     rbx, [rsp+48h+arg_0]
0x18003a8bf  mov     rbp, [rsp+48h+arg_8]
0x18003a8c4  add     rsp, 30h
0x18003a8c8  pop     r14
0x18003a8ca  pop     rdi
0x18003a8cb  pop     rsi
0x18003a8cc  retn
```

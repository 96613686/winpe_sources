# RAiCloseJitvSilo

- ea: `0x18003a750`
- end: `0x18003a80a`
- name: `RAiCloseJitvSilo`
- size: `186`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800234a0`
- `0x1800241b4`
- `0x18002c7fc`
- `0x18003a750`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a7ea`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a7ea`

## pseudocode

```c
RPC_STATUS __fastcall RAiCloseJitvSilo(PRPC_ASYNC_STATE pAsync, void *a2, unsigned int *a3)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids);
  v6 = CloseDesktopJitvSilo(a2, *a3);
  v7 = v6;
  if ( v6 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids,
      (unsigned int)v6);
  v8 = (unsigned __int16)v7;
  *(_QWORD *)a3 = 0;
  if ( v7 >= 0 )
    v8 = 0;
  Reply = v8;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x18003a750  mov     [rsp+arg_0], rbx
0x18003a755  mov     [rsp+arg_8], rbp
0x18003a75a  push    rsi
0x18003a75b  push    rdi
0x18003a75c  push    r14
0x18003a75e  sub     rsp, 20h
0x18003a762  mov     rdi, r8
0x18003a765  mov     rbx, rdx
0x18003a768  mov     rsi, rcx
0x18003a76b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a772  lea     r14, WPP_GLOBAL_Control
0x18003a779  cmp     rcx, r14
0x18003a77c  jz      short loc_18003A799
0x18003a77e  test    byte ptr [rcx+1Ch], 1
0x18003a782  jz      short loc_18003A799
0x18003a784  mov     rcx, [rcx+10h]
0x18003a788  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x18003a78f  mov     edx, 26h ; '&'
0x18003a794  call    WPP_SF_
0x18003a799  mov     edx, [rdi]; unsigned int
0x18003a79b  mov     rcx, rbx; void *
0x18003a79e  call    ?CloseDesktopJitvSilo@@YAJPEAXK@Z; CloseDesktopJitvSilo(void *,ulong)
0x18003a7a3  xor     ebp, ebp
0x18003a7a5  mov     ebx, eax
0x18003a7a7  test    eax, eax
0x18003a7a9  jns     short loc_18003A7D3
0x18003a7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7b2  cmp     rcx, r14
0x18003a7b5  jz      short loc_18003A7D3
0x18003a7b7  test    byte ptr [rcx+1Ch], 1
0x18003a7bb  jz      short loc_18003A7D3
0x18003a7bd  mov     rcx, [rcx+10h]
0x18003a7c1  lea     edx, [rbp+27h]
0x18003a7c4  mov     r9d, eax
0x18003a7c7  lea     r8, WPP_5a99e4d32d543c5ccd81a78831f70868_Traceguids
0x18003a7ce  call    WPP_SF_D
0x18003a7d3  test    ebx, ebx
0x18003a7d5  movzx   eax, bx
0x18003a7d8  lea     rdx, [rsp+38h+Reply]; Reply
0x18003a7dd  mov     [rdi], rbp
0x18003a7e0  cmovns  eax, ebp
0x18003a7e3  mov     rcx, rsi; pAsync
0x18003a7e6  mov     [rsp+38h+Reply], eax
0x18003a7ea  call    cs:__imp_RpcAsyncCompleteCall
0x18003a7f1  nop     dword ptr [rax+rax+00h]
0x18003a7f6  mov     rbx, [rsp+38h+arg_0]
0x18003a7fb  mov     rbp, [rsp+38h+arg_8]
0x18003a800  add     rsp, 20h
0x18003a804  pop     r14
0x18003a806  pop     rdi
0x18003a807  pop     rsi
0x18003a808  retn
```

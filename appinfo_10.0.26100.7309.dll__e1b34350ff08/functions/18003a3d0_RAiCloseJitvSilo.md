# RAiCloseJitvSilo

- ea: `0x18003a3d0`
- end: `0x18003a48a`
- name: `RAiCloseJitvSilo`
- size: `186`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800234a0`
- `0x1800241b4`
- `0x18002c72c`
- `0x18003a3d0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a46a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a46a`

## pseudocode

```c
RPC_STATUS __fastcall RAiCloseJitvSilo(PRPC_ASYNC_STATE pAsync, void *a2, unsigned int *a3)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids);
  v6 = CloseDesktopJitvSilo(a2, *a3);
  v7 = v6;
  if ( v6 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids,
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
0x18003a3d0  mov     [rsp+arg_0], rbx
0x18003a3d5  mov     [rsp+arg_8], rbp
0x18003a3da  push    rsi
0x18003a3db  push    rdi
0x18003a3dc  push    r14
0x18003a3de  sub     rsp, 20h
0x18003a3e2  mov     rdi, r8
0x18003a3e5  mov     rbx, rdx
0x18003a3e8  mov     rsi, rcx
0x18003a3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3f2  lea     r14, WPP_GLOBAL_Control
0x18003a3f9  cmp     rcx, r14
0x18003a3fc  jz      short loc_18003A419
0x18003a3fe  test    byte ptr [rcx+1Ch], 1
0x18003a402  jz      short loc_18003A419
0x18003a404  mov     rcx, [rcx+10h]
0x18003a408  lea     r8, WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids
0x18003a40f  mov     edx, 26h ; '&'
0x18003a414  call    WPP_SF_
0x18003a419  mov     edx, [rdi]; unsigned int
0x18003a41b  mov     rcx, rbx; void *
0x18003a41e  call    ?CloseDesktopJitvSilo@@YAJPEAXK@Z; CloseDesktopJitvSilo(void *,ulong)
0x18003a423  xor     ebp, ebp
0x18003a425  mov     ebx, eax
0x18003a427  test    eax, eax
0x18003a429  jns     short loc_18003A453
0x18003a42b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a432  cmp     rcx, r14
0x18003a435  jz      short loc_18003A453
0x18003a437  test    byte ptr [rcx+1Ch], 1
0x18003a43b  jz      short loc_18003A453
0x18003a43d  mov     rcx, [rcx+10h]
0x18003a441  lea     edx, [rbp+27h]
0x18003a444  mov     r9d, eax
0x18003a447  lea     r8, WPP_063934a2c6ca383cf9bd298d4f16efdb_Traceguids
0x18003a44e  call    WPP_SF_D
0x18003a453  test    ebx, ebx
0x18003a455  movzx   eax, bx
0x18003a458  lea     rdx, [rsp+38h+Reply]; Reply
0x18003a45d  mov     [rdi], rbp
0x18003a460  cmovns  eax, ebp
0x18003a463  mov     rcx, rsi; pAsync
0x18003a466  mov     [rsp+38h+Reply], eax
0x18003a46a  call    cs:__imp_RpcAsyncCompleteCall
0x18003a471  nop     dword ptr [rax+rax+00h]
0x18003a476  mov     rbx, [rsp+38h+arg_0]
0x18003a47b  mov     rbp, [rsp+38h+arg_8]
0x18003a480  add     rsp, 20h
0x18003a484  pop     r14
0x18003a486  pop     rdi
0x18003a487  pop     rsi
0x18003a488  retn
```

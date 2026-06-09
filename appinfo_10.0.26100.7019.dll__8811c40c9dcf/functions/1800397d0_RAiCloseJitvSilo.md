# RAiCloseJitvSilo

- ea: `0x1800397d0`
- end: `0x18003988a`
- name: `RAiCloseJitvSilo`
- size: `186`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180024db0`
- `0x180025ac4`
- `0x18002dd4c`
- `0x1800397d0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003986a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003986a`

## pseudocode

```c
RPC_STATUS __fastcall RAiCloseJitvSilo(PRPC_ASYNC_STATE pAsync, void *a2, unsigned int *a3)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids);
  v6 = CloseDesktopJitvSilo(a2, *a3);
  v7 = v6;
  if ( v6 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids,
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
0x1800397d0  mov     [rsp+arg_0], rbx
0x1800397d5  mov     [rsp+arg_8], rbp
0x1800397da  push    rsi
0x1800397db  push    rdi
0x1800397dc  push    r14
0x1800397de  sub     rsp, 20h
0x1800397e2  mov     rdi, r8
0x1800397e5  mov     rbx, rdx
0x1800397e8  mov     rsi, rcx
0x1800397eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800397f2  lea     r14, WPP_GLOBAL_Control
0x1800397f9  cmp     rcx, r14
0x1800397fc  jz      short loc_180039819
0x1800397fe  test    byte ptr [rcx+1Ch], 1
0x180039802  jz      short loc_180039819
0x180039804  mov     rcx, [rcx+10h]
0x180039808  lea     r8, WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids
0x18003980f  mov     edx, 26h ; '&'
0x180039814  call    WPP_SF_
0x180039819  mov     edx, [rdi]; unsigned int
0x18003981b  mov     rcx, rbx; void *
0x18003981e  call    ?CloseDesktopJitvSilo@@YAJPEAXK@Z; CloseDesktopJitvSilo(void *,ulong)
0x180039823  xor     ebp, ebp
0x180039825  mov     ebx, eax
0x180039827  test    eax, eax
0x180039829  jns     short loc_180039853
0x18003982b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039832  cmp     rcx, r14
0x180039835  jz      short loc_180039853
0x180039837  test    byte ptr [rcx+1Ch], 1
0x18003983b  jz      short loc_180039853
0x18003983d  mov     rcx, [rcx+10h]
0x180039841  lea     edx, [rbp+27h]
0x180039844  mov     r9d, eax
0x180039847  lea     r8, WPP_e8c8bde4cfdd31ad7ca53050940b7a3e_Traceguids
0x18003984e  call    WPP_SF_D
0x180039853  test    ebx, ebx
0x180039855  movzx   eax, bx
0x180039858  lea     rdx, [rsp+38h+Reply]; Reply
0x18003985d  mov     [rdi], rbp
0x180039860  cmovns  eax, ebp
0x180039863  mov     rcx, rsi; pAsync
0x180039866  mov     [rsp+38h+Reply], eax
0x18003986a  call    cs:__imp_RpcAsyncCompleteCall
0x180039871  nop     dword ptr [rax+rax+00h]
0x180039876  mov     rbx, [rsp+38h+arg_0]
0x18003987b  mov     rbp, [rsp+38h+arg_8]
0x180039880  add     rsp, 20h
0x180039884  pop     r14
0x180039886  pop     rdi
0x180039887  pop     rsi
0x180039888  retn
```

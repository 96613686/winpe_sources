# RAiEnsurePackageShutdown

- ea: `0x18003aa60`
- end: `0x18003ab2a`
- name: `RAiEnsurePackageShutdown`
- size: `202`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002d054`
- `0x18003aa60`
- `0x18003c7b4`
- `0x18003c838`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ab04`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ab04`

## pseudocode

```c
RPC_STATUS __fastcall RAiEnsurePackageShutdown(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // ebx
  int v12; // eax
  _DWORD Reply[10]; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, (_DWORD)a3, (_DWORD)a3, a4);
  v8 = EnsurePackageShutdown(a2, a3, a4);
  v11 = v8;
  if ( v8 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (_DWORD)a3, a4, v8);
  v12 = (unsigned __int16)v11;
  if ( v11 >= 0 )
    v12 = 0;
  Reply[0] = v12;
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x18003aa60  mov     rax, rsp
0x18003aa63  mov     [rax+8], rbx
0x18003aa67  mov     [rax+10h], rbp
0x18003aa6b  mov     [rax+18h], rsi
0x18003aa6f  push    rdi
0x18003aa70  push    r14
0x18003aa72  push    r15
0x18003aa74  sub     rsp, 40h
0x18003aa78  mov     edi, r9d
0x18003aa7b  mov     rsi, r8
0x18003aa7e  mov     rbx, rdx
0x18003aa81  mov     rbp, rcx
0x18003aa84  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa8b  lea     r15, WPP_GLOBAL_Control
0x18003aa92  cmp     rcx, r15
0x18003aa95  jz      short loc_18003AAB2
0x18003aa97  test    byte ptr [rcx+1Ch], 1
0x18003aa9b  jz      short loc_18003AAB2
0x18003aa9d  mov     rcx, [rcx+10h]
0x18003aaa1  mov     edx, 3Fh ; '?'
0x18003aaa6  mov     [rax-38h], r9d
0x18003aaaa  mov     r9, r8
0x18003aaad  call    WPP_SF_SD
0x18003aab2  mov     r8d, edi; unsigned int
0x18003aab5  mov     rdx, rsi; unsigned __int16 *
0x18003aab8  mov     rcx, rbx; void *
0x18003aabb  call    ?EnsurePackageShutdown@@YAJPEAXPEBGK@Z; EnsurePackageShutdown(void *,ushort const *,ulong)
0x18003aac0  xor     r14d, r14d
0x18003aac3  mov     ebx, eax
0x18003aac5  test    eax, eax
0x18003aac7  jns     short loc_18003AAEF
0x18003aac9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aad0  cmp     rcx, r15
0x18003aad3  jz      short loc_18003AAEF
0x18003aad5  test    byte ptr [rcx+1Ch], 1
0x18003aad9  jz      short loc_18003AAEF
0x18003aadb  mov     rcx, [rcx+10h]
0x18003aadf  mov     r9, rsi
0x18003aae2  mov     [rsp+58h+var_30], eax
0x18003aae6  mov     [rsp+58h+var_38], edi
0x18003aaea  call    WPP_SF_SDD
0x18003aaef  test    ebx, ebx
0x18003aaf1  movzx   eax, bx
0x18003aaf4  lea     rdx, [rsp+58h+Reply]; Reply
0x18003aaf9  mov     rcx, rbp; pAsync
0x18003aafc  cmovns  eax, r14d
0x18003ab00  mov     [rsp+58h+Reply], eax
0x18003ab04  call    cs:__imp_RpcAsyncCompleteCall
0x18003ab0b  nop     dword ptr [rax+rax+00h]
0x18003ab10  mov     rbx, [rsp+58h+arg_0]
0x18003ab15  mov     rbp, [rsp+58h+arg_8]
0x18003ab1a  mov     rsi, [rsp+58h+arg_10]
0x18003ab1f  add     rsp, 40h
0x18003ab23  pop     r15
0x18003ab25  pop     r14
0x18003ab27  pop     rdi
0x18003ab28  retn
```

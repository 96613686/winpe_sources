# RAiEnsurePackageShutdown

- ea: `0x18003a6e0`
- end: `0x18003a7aa`
- name: `RAiEnsurePackageShutdown`
- size: `202`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002cf84`
- `0x18003a6e0`
- `0x18003c274`
- `0x18003c2f8`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a784`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a784`

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
0x18003a6e0  mov     rax, rsp
0x18003a6e3  mov     [rax+8], rbx
0x18003a6e7  mov     [rax+10h], rbp
0x18003a6eb  mov     [rax+18h], rsi
0x18003a6ef  push    rdi
0x18003a6f0  push    r14
0x18003a6f2  push    r15
0x18003a6f4  sub     rsp, 40h
0x18003a6f8  mov     edi, r9d
0x18003a6fb  mov     rsi, r8
0x18003a6fe  mov     rbx, rdx
0x18003a701  mov     rbp, rcx
0x18003a704  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a70b  lea     r15, WPP_GLOBAL_Control
0x18003a712  cmp     rcx, r15
0x18003a715  jz      short loc_18003A732
0x18003a717  test    byte ptr [rcx+1Ch], 1
0x18003a71b  jz      short loc_18003A732
0x18003a71d  mov     rcx, [rcx+10h]
0x18003a721  mov     edx, 3Fh ; '?'
0x18003a726  mov     [rax-38h], r9d
0x18003a72a  mov     r9, r8
0x18003a72d  call    WPP_SF_SD
0x18003a732  mov     r8d, edi; unsigned int
0x18003a735  mov     rdx, rsi; unsigned __int16 *
0x18003a738  mov     rcx, rbx; void *
0x18003a73b  call    ?EnsurePackageShutdown@@YAJPEAXPEBGK@Z; EnsurePackageShutdown(void *,ushort const *,ulong)
0x18003a740  xor     r14d, r14d
0x18003a743  mov     ebx, eax
0x18003a745  test    eax, eax
0x18003a747  jns     short loc_18003A76F
0x18003a749  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a750  cmp     rcx, r15
0x18003a753  jz      short loc_18003A76F
0x18003a755  test    byte ptr [rcx+1Ch], 1
0x18003a759  jz      short loc_18003A76F
0x18003a75b  mov     rcx, [rcx+10h]
0x18003a75f  mov     r9, rsi
0x18003a762  mov     [rsp+58h+var_30], eax
0x18003a766  mov     [rsp+58h+var_38], edi
0x18003a76a  call    WPP_SF_SDD
0x18003a76f  test    ebx, ebx
0x18003a771  movzx   eax, bx
0x18003a774  lea     rdx, [rsp+58h+Reply]; Reply
0x18003a779  mov     rcx, rbp; pAsync
0x18003a77c  cmovns  eax, r14d
0x18003a780  mov     [rsp+58h+Reply], eax
0x18003a784  call    cs:__imp_RpcAsyncCompleteCall
0x18003a78b  nop     dword ptr [rax+rax+00h]
0x18003a790  mov     rbx, [rsp+58h+arg_0]
0x18003a795  mov     rbp, [rsp+58h+arg_8]
0x18003a79a  mov     rsi, [rsp+58h+arg_10]
0x18003a79f  add     rsp, 40h
0x18003a7a3  pop     r15
0x18003a7a5  pop     r14
0x18003a7a7  pop     rdi
0x18003a7a8  retn
```

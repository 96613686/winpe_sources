# RAiEnsurePackageShutdown

- ea: `0x180039ae0`
- end: `0x180039baa`
- name: `RAiEnsurePackageShutdown`
- size: `202`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002e5a4`
- `0x180039ae0`
- `0x18003b634`
- `0x18003b6b8`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180039b84`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180039b84`

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
0x180039ae0  mov     rax, rsp
0x180039ae3  mov     [rax+8], rbx
0x180039ae7  mov     [rax+10h], rbp
0x180039aeb  mov     [rax+18h], rsi
0x180039aef  push    rdi
0x180039af0  push    r14
0x180039af2  push    r15
0x180039af4  sub     rsp, 40h
0x180039af8  mov     edi, r9d
0x180039afb  mov     rsi, r8
0x180039afe  mov     rbx, rdx
0x180039b01  mov     rbp, rcx
0x180039b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b0b  lea     r15, WPP_GLOBAL_Control
0x180039b12  cmp     rcx, r15
0x180039b15  jz      short loc_180039B32
0x180039b17  test    byte ptr [rcx+1Ch], 1
0x180039b1b  jz      short loc_180039B32
0x180039b1d  mov     rcx, [rcx+10h]
0x180039b21  mov     edx, 3Fh ; '?'
0x180039b26  mov     [rax-38h], r9d
0x180039b2a  mov     r9, r8
0x180039b2d  call    WPP_SF_SD
0x180039b32  mov     r8d, edi; unsigned int
0x180039b35  mov     rdx, rsi; unsigned __int16 *
0x180039b38  mov     rcx, rbx; void *
0x180039b3b  call    ?EnsurePackageShutdown@@YAJPEAXPEBGK@Z; EnsurePackageShutdown(void *,ushort const *,ulong)
0x180039b40  xor     r14d, r14d
0x180039b43  mov     ebx, eax
0x180039b45  test    eax, eax
0x180039b47  jns     short loc_180039B6F
0x180039b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b50  cmp     rcx, r15
0x180039b53  jz      short loc_180039B6F
0x180039b55  test    byte ptr [rcx+1Ch], 1
0x180039b59  jz      short loc_180039B6F
0x180039b5b  mov     rcx, [rcx+10h]
0x180039b5f  mov     r9, rsi
0x180039b62  mov     [rsp+58h+var_30], eax
0x180039b66  mov     [rsp+58h+var_38], edi
0x180039b6a  call    WPP_SF_SDD
0x180039b6f  test    ebx, ebx
0x180039b71  movzx   eax, bx
0x180039b74  lea     rdx, [rsp+58h+Reply]; Reply
0x180039b79  mov     rcx, rbp; pAsync
0x180039b7c  cmovns  eax, r14d
0x180039b80  mov     [rsp+58h+Reply], eax
0x180039b84  call    cs:__imp_RpcAsyncCompleteCall
0x180039b8b  nop     dword ptr [rax+rax+00h]
0x180039b90  mov     rbx, [rsp+58h+arg_0]
0x180039b95  mov     rbp, [rsp+58h+arg_8]
0x180039b9a  mov     rsi, [rsp+58h+arg_10]
0x180039b9f  add     rsp, 40h
0x180039ba3  pop     r15
0x180039ba5  pop     r14
0x180039ba7  pop     rdi
0x180039ba8  retn
```

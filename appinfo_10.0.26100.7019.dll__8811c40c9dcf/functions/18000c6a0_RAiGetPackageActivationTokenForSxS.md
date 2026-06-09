# RAiGetPackageActivationTokenForSxS

- ea: `0x18000c6a0`
- end: `0x18000c787`
- name: `RAiGetPackageActivationTokenForSxS`
- size: `231`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c6a0`
- `0x1800327a0`
- `0x18003b634`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c71c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c71c`

## pseudocode

```c
RPC_STATUS __fastcall RAiGetPackageActivationTokenForSxS(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        const unsigned __int16 *a3,
        void *a4,
        int a5,
        struct _ACTIVATION_TOKEN_INFO *a6)
{
  int PackageActivationTokenForSxS; // eax
  int v11; // r8d
  int v12; // ebx
  int v13; // eax
  _DWORD Reply[6]; // [rsp+30h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, (_DWORD)a3, (_DWORD)a3, (char)a4);
  PackageActivationTokenForSxS = GetPackageActivationTokenForSxS(a2, a3, a4, a5, a6);
  v12 = PackageActivationTokenForSxS;
  if ( PackageActivationTokenForSxS < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v11, (_DWORD)a3, PackageActivationTokenForSxS);
  }
  v13 = (unsigned __int16)v12;
  if ( v12 >= 0 )
    v13 = 0;
  Reply[0] = v13;
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x18000c6a0  mov     [rsp+arg_0], rbx
0x18000c6a5  mov     [rsp+arg_8], rbp
0x18000c6aa  mov     [rsp+arg_10], rsi
0x18000c6af  mov     [rsp+arg_18], rdi
0x18000c6b4  push    r14
0x18000c6b6  sub     rsp, 40h
0x18000c6ba  mov     rbx, r9
0x18000c6bd  mov     rbp, r8
0x18000c6c0  mov     rsi, rdx
0x18000c6c3  mov     rdi, rcx
0x18000c6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6cd  lea     r14, WPP_GLOBAL_Control
0x18000c6d4  cmp     rcx, r14
0x18000c6d7  jz      short loc_18000C6E3
0x18000c6d9  test    byte ptr [rcx+1Ch], 1
0x18000c6dd  jnz     loc_18000C76D
0x18000c6e3  mov     rax, [rsp+48h+arg_28]
0x18000c6e8  mov     r8, rbx; void *
0x18000c6eb  mov     r9d, [rsp+48h+arg_20]; int
0x18000c6f0  mov     rdx, rbp; unsigned __int16 *
0x18000c6f3  mov     rcx, rsi; void *
0x18000c6f6  mov     [rsp+48h+var_28], rax; struct _ACTIVATION_TOKEN_INFO *
0x18000c6fb  call    ?GetPackageActivationTokenForSxS@@YAJPEAXPEBG0HPEAU_ACTIVATION_TOKEN_INFO@@@Z; GetPackageActivationTokenForSxS(void *,ushort const *,void *,int,_ACTIVATION_TOKEN_INFO *)
0x18000c700  mov     ebx, eax
0x18000c702  test    eax, eax
0x18000c704  js      short loc_18000C744
0x18000c706  xor     ecx, ecx
0x18000c708  movzx   eax, bx
0x18000c70b  test    ebx, ebx
0x18000c70d  lea     rdx, [rsp+48h+Reply]; Reply
0x18000c712  cmovns  eax, ecx
0x18000c715  mov     rcx, rdi; pAsync
0x18000c718  mov     [rsp+48h+Reply], eax
0x18000c71c  call    cs:__imp_RpcAsyncCompleteCall
0x18000c723  nop     dword ptr [rax+rax+00h]
0x18000c728  mov     rbx, [rsp+48h+arg_0]
0x18000c72d  mov     rbp, [rsp+48h+arg_8]
0x18000c732  mov     rsi, [rsp+48h+arg_10]
0x18000c737  mov     rdi, [rsp+48h+arg_18]
0x18000c73c  add     rsp, 40h
0x18000c740  pop     r14
0x18000c742  retn
0x18000c744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c74b  cmp     rcx, r14
0x18000c74e  jz      short loc_18000C706
0x18000c750  test    byte ptr [rcx+1Ch], 1
0x18000c754  jz      short loc_18000C706
0x18000c756  mov     rcx, [rcx+10h]
0x18000c75a  mov     edx, 23h ; '#'
0x18000c75f  mov     r9, rbp
0x18000c762  mov     dword ptr [rsp+48h+var_28], ebx
0x18000c766  call    WPP_SF_SD
0x18000c76b  jmp     short loc_18000C706
0x18000c76d  mov     rcx, [rcx+10h]
0x18000c771  mov     edx, 22h ; '"'
0x18000c776  mov     r9, rbp
0x18000c779  mov     dword ptr [rsp+48h+var_28], ebx
0x18000c77d  call    WPP_SF_SD
0x18000c782  jmp     loc_18000C6E3
```

# RAiGetPackageActivationTokenForFilePath

- ea: `0x18003a7b0`
- end: `0x18003a89d`
- name: `RAiGetPackageActivationTokenForFilePath`
- size: `237`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, void *, struct _ACTIVATION_TOKEN_INFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a1f0`
- `0x180032730`
- `0x18003a7b0`
- `0x18003c274`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a875`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003a875`

## pseudocode

```c
RPC_STATUS __fastcall RAiGetPackageActivationTokenForFilePath(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        void *a4,
        struct _ACTIVATION_TOKEN_INFO *a5)
{
  unsigned int v9; // eax
  int v10; // r8d
  int PackageActivationTokenForFilePath; // ebx
  unsigned int v12; // eax
  int v13; // r8d
  int v14; // eax
  _DWORD Reply[6]; // [rsp+30h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = (unsigned int)AipJustFileName(a3);
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v10, v9, (char)a4);
  }
  PackageActivationTokenForFilePath = GetPackageActivationTokenForFilePath(a2, a3, a4, a5);
  if ( PackageActivationTokenForFilePath < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = (unsigned int)AipJustFileName(a3);
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v13, v12, PackageActivationTokenForFilePath);
  }
  v14 = (unsigned __int16)PackageActivationTokenForFilePath;
  if ( PackageActivationTokenForFilePath >= 0 )
    v14 = 0;
  Reply[0] = v14;
  return RpcAsyncCompleteCall(pAsync, Reply);
}

```

## disassembly

```asm
0x18003a7b0  mov     rax, rsp
0x18003a7b3  mov     [rax+8], rbx
0x18003a7b7  mov     [rax+10h], rbp
0x18003a7bb  mov     [rax+18h], rsi
0x18003a7bf  mov     [rax+20h], rdi
0x18003a7c3  push    r14
0x18003a7c5  sub     rsp, 40h
0x18003a7c9  mov     rbx, r9
0x18003a7cc  mov     rdi, r8
0x18003a7cf  mov     rsi, rdx
0x18003a7d2  mov     rbp, rcx
0x18003a7d5  mov     rax, cs:WPP_GLOBAL_Control
0x18003a7dc  lea     r14, WPP_GLOBAL_Control
0x18003a7e3  cmp     rax, r14
0x18003a7e6  jz      short loc_18003A812
0x18003a7e8  test    byte ptr [rax+1Ch], 1
0x18003a7ec  jz      short loc_18003A812
0x18003a7ee  mov     rcx, r8; unsigned __int16 *
0x18003a7f1  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003a7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7fd  mov     edx, 1Ch
0x18003a802  mov     r9, rax
0x18003a805  mov     [rsp+48h+var_28], ebx
0x18003a809  mov     rcx, [rcx+10h]
0x18003a80d  call    WPP_SF_SD
0x18003a812  mov     r9, [rsp+48h+arg_20]; struct _ACTIVATION_TOKEN_INFO *
0x18003a817  mov     r8, rbx; void *
0x18003a81a  mov     rdx, rdi; unsigned __int16 *
0x18003a81d  mov     rcx, rsi; void *
0x18003a820  call    ?GetPackageActivationTokenForFilePath@@YAJPEAXPEBG0PEAU_ACTIVATION_TOKEN_INFO@@@Z; GetPackageActivationTokenForFilePath(void *,ushort const *,void *,_ACTIVATION_TOKEN_INFO *)
0x18003a825  xor     esi, esi
0x18003a827  mov     ebx, eax
0x18003a829  test    eax, eax
0x18003a82b  jns     short loc_18003A861
0x18003a82d  mov     rax, cs:WPP_GLOBAL_Control
0x18003a834  cmp     rax, r14
0x18003a837  jz      short loc_18003A861
0x18003a839  test    byte ptr [rax+1Ch], 1
0x18003a83d  jz      short loc_18003A861
0x18003a83f  mov     rcx, rdi; unsigned __int16 *
0x18003a842  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003a847  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a84e  lea     edx, [rsi+1Dh]
0x18003a851  mov     r9, rax
0x18003a854  mov     [rsp+48h+var_28], ebx
0x18003a858  mov     rcx, [rcx+10h]
0x18003a85c  call    WPP_SF_SD
0x18003a861  test    ebx, ebx
0x18003a863  movzx   eax, bx
0x18003a866  lea     rdx, [rsp+48h+Reply]; Reply
0x18003a86b  mov     rcx, rbp; pAsync
0x18003a86e  cmovns  eax, esi
0x18003a871  mov     [rsp+48h+Reply], eax
0x18003a875  call    cs:__imp_RpcAsyncCompleteCall
0x18003a87c  nop     dword ptr [rax+rax+00h]
0x18003a881  mov     rbx, [rsp+48h+arg_0]
0x18003a886  mov     rbp, [rsp+48h+arg_8]
0x18003a88b  mov     rsi, [rsp+48h+arg_10]
0x18003a890  mov     rdi, [rsp+48h+arg_18]
0x18003a895  add     rsp, 40h
0x18003a899  pop     r14
0x18003a89b  retn
```

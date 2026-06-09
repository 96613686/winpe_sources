# RAiGetPackageActivationTokenForFilePath

- ea: `0x180039bb0`
- end: `0x180039c9d`
- name: `RAiGetPackageActivationTokenForFilePath`
- size: `237`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, void *, struct _ACTIVATION_TOKEN_INFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a1f0`
- `0x1800326c0`
- `0x180039bb0`
- `0x18003b634`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180039c75`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180039c75`

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
0x180039bb0  mov     rax, rsp
0x180039bb3  mov     [rax+8], rbx
0x180039bb7  mov     [rax+10h], rbp
0x180039bbb  mov     [rax+18h], rsi
0x180039bbf  mov     [rax+20h], rdi
0x180039bc3  push    r14
0x180039bc5  sub     rsp, 40h
0x180039bc9  mov     rbx, r9
0x180039bcc  mov     rdi, r8
0x180039bcf  mov     rsi, rdx
0x180039bd2  mov     rbp, rcx
0x180039bd5  mov     rax, cs:WPP_GLOBAL_Control
0x180039bdc  lea     r14, WPP_GLOBAL_Control
0x180039be3  cmp     rax, r14
0x180039be6  jz      short loc_180039C12
0x180039be8  test    byte ptr [rax+1Ch], 1
0x180039bec  jz      short loc_180039C12
0x180039bee  mov     rcx, r8; unsigned __int16 *
0x180039bf1  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x180039bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180039bfd  mov     edx, 1Ch
0x180039c02  mov     r9, rax
0x180039c05  mov     [rsp+48h+var_28], ebx
0x180039c09  mov     rcx, [rcx+10h]
0x180039c0d  call    WPP_SF_SD
0x180039c12  mov     r9, [rsp+48h+arg_20]; struct _ACTIVATION_TOKEN_INFO *
0x180039c17  mov     r8, rbx; void *
0x180039c1a  mov     rdx, rdi; unsigned __int16 *
0x180039c1d  mov     rcx, rsi; void *
0x180039c20  call    ?GetPackageActivationTokenForFilePath@@YAJPEAXPEBG0PEAU_ACTIVATION_TOKEN_INFO@@@Z; GetPackageActivationTokenForFilePath(void *,ushort const *,void *,_ACTIVATION_TOKEN_INFO *)
0x180039c25  xor     esi, esi
0x180039c27  mov     ebx, eax
0x180039c29  test    eax, eax
0x180039c2b  jns     short loc_180039C61
0x180039c2d  mov     rax, cs:WPP_GLOBAL_Control
0x180039c34  cmp     rax, r14
0x180039c37  jz      short loc_180039C61
0x180039c39  test    byte ptr [rax+1Ch], 1
0x180039c3d  jz      short loc_180039C61
0x180039c3f  mov     rcx, rdi; unsigned __int16 *
0x180039c42  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x180039c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c4e  lea     edx, [rsi+1Dh]
0x180039c51  mov     r9, rax
0x180039c54  mov     [rsp+48h+var_28], ebx
0x180039c58  mov     rcx, [rcx+10h]
0x180039c5c  call    WPP_SF_SD
0x180039c61  test    ebx, ebx
0x180039c63  movzx   eax, bx
0x180039c66  lea     rdx, [rsp+48h+Reply]; Reply
0x180039c6b  mov     rcx, rbp; pAsync
0x180039c6e  cmovns  eax, esi
0x180039c71  mov     [rsp+48h+Reply], eax
0x180039c75  call    cs:__imp_RpcAsyncCompleteCall
0x180039c7c  nop     dword ptr [rax+rax+00h]
0x180039c81  mov     rbx, [rsp+48h+arg_0]
0x180039c86  mov     rbp, [rsp+48h+arg_8]
0x180039c8b  mov     rsi, [rsp+48h+arg_10]
0x180039c90  mov     rdi, [rsp+48h+arg_18]
0x180039c95  add     rsp, 40h
0x180039c99  pop     r14
0x180039c9b  retn
```

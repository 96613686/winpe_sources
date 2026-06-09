# RAiGetPackageActivationTokenForFilePath

- ea: `0x18003ab30`
- end: `0x18003ac1d`
- name: `RAiGetPackageActivationTokenForFilePath`
- size: `237`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, void *, struct _ACTIVATION_TOKEN_INFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a1f0`
- `0x1800329f0`
- `0x18003ab30`
- `0x18003c7b4`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003abf5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003abf5`

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
0x18003ab30  mov     rax, rsp
0x18003ab33  mov     [rax+8], rbx
0x18003ab37  mov     [rax+10h], rbp
0x18003ab3b  mov     [rax+18h], rsi
0x18003ab3f  mov     [rax+20h], rdi
0x18003ab43  push    r14
0x18003ab45  sub     rsp, 40h
0x18003ab49  mov     rbx, r9
0x18003ab4c  mov     rdi, r8
0x18003ab4f  mov     rsi, rdx
0x18003ab52  mov     rbp, rcx
0x18003ab55  mov     rax, cs:WPP_GLOBAL_Control
0x18003ab5c  lea     r14, WPP_GLOBAL_Control
0x18003ab63  cmp     rax, r14
0x18003ab66  jz      short loc_18003AB92
0x18003ab68  test    byte ptr [rax+1Ch], 1
0x18003ab6c  jz      short loc_18003AB92
0x18003ab6e  mov     rcx, r8; unsigned __int16 *
0x18003ab71  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003ab76  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab7d  mov     edx, 1Ch
0x18003ab82  mov     r9, rax
0x18003ab85  mov     [rsp+48h+var_28], ebx
0x18003ab89  mov     rcx, [rcx+10h]
0x18003ab8d  call    WPP_SF_SD
0x18003ab92  mov     r9, [rsp+48h+arg_20]; struct _ACTIVATION_TOKEN_INFO *
0x18003ab97  mov     r8, rbx; void *
0x18003ab9a  mov     rdx, rdi; unsigned __int16 *
0x18003ab9d  mov     rcx, rsi; void *
0x18003aba0  call    ?GetPackageActivationTokenForFilePath@@YAJPEAXPEBG0PEAU_ACTIVATION_TOKEN_INFO@@@Z; GetPackageActivationTokenForFilePath(void *,ushort const *,void *,_ACTIVATION_TOKEN_INFO *)
0x18003aba5  xor     esi, esi
0x18003aba7  mov     ebx, eax
0x18003aba9  test    eax, eax
0x18003abab  jns     short loc_18003ABE1
0x18003abad  mov     rax, cs:WPP_GLOBAL_Control
0x18003abb4  cmp     rax, r14
0x18003abb7  jz      short loc_18003ABE1
0x18003abb9  test    byte ptr [rax+1Ch], 1
0x18003abbd  jz      short loc_18003ABE1
0x18003abbf  mov     rcx, rdi; unsigned __int16 *
0x18003abc2  call    ?AipJustFileName@@YAPEBGPEBG@Z; AipJustFileName(ushort const *)
0x18003abc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003abce  lea     edx, [rsi+1Dh]
0x18003abd1  mov     r9, rax
0x18003abd4  mov     [rsp+48h+var_28], ebx
0x18003abd8  mov     rcx, [rcx+10h]
0x18003abdc  call    WPP_SF_SD
0x18003abe1  test    ebx, ebx
0x18003abe3  movzx   eax, bx
0x18003abe6  lea     rdx, [rsp+48h+Reply]; Reply
0x18003abeb  mov     rcx, rbp; pAsync
0x18003abee  cmovns  eax, esi
0x18003abf1  mov     [rsp+48h+Reply], eax
0x18003abf5  call    cs:__imp_RpcAsyncCompleteCall
0x18003abfc  nop     dword ptr [rax+rax+00h]
0x18003ac01  mov     rbx, [rsp+48h+arg_0]
0x18003ac06  mov     rbp, [rsp+48h+arg_8]
0x18003ac0b  mov     rsi, [rsp+48h+arg_10]
0x18003ac10  mov     rdi, [rsp+48h+arg_18]
0x18003ac15  add     rsp, 40h
0x18003ac19  pop     r14
0x18003ac1b  retn
```

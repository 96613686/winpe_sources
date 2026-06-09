# RAiCreatePackagedProcessByLaunchContract

- ea: `0x18003cca0`
- end: `0x18003cd73`
- name: `RAiCreatePackagedProcessByLaunchContract`
- size: `211`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, void *, void *, unsigned __int16 *, unsigned __int16 *, PCWSTR applicationUserModelId, __int64 Reply, unsigned __int16 *, struct _APPINFO_STARTUPINFO *, struct _APPINFO_STARTUPINFO_STDHANDLES *, unsigned __int16 *, struct _APPINFO_PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002e8bc`
- `0x18003cca0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18003cd64`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003cd64`

## pseudocode

```c
RPC_STATUS __fastcall RAiCreatePackagedProcessByLaunchContract(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        void *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        PCWSTR applicationUserModelId,
        __int64 Reply,
        unsigned __int16 *a8,
        struct _APPINFO_STARTUPINFO *a9,
        struct _APPINFO_STARTUPINFO_STDHANDLES *a10,
        unsigned __int16 *a11,
        struct _APPINFO_PROCESS_INFORMATION *a12)
{
  int PackagedProcessByLaunchContract_AppExtension; // eax
  int v14; // edx
  const unsigned __int16 *v16; // [rsp+40h] [rbp-58h]

  if ( *(_DWORD *)Reply == 1 )
    PackagedProcessByLaunchContract_AppExtension = AipCreatePackagedProcessByLaunchContract_AppExtension(
                                                     a2,
                                                     a3,
                                                     a4,
                                                     a5,
                                                     applicationUserModelId,
                                                     *(LPCWCH *)(Reply + 8),
                                                     *(const unsigned __int16 **)(Reply + 16),
                                                     *(_DWORD *)(Reply + 24),
                                                     v16,
                                                     a8,
                                                     a9,
                                                     a10,
                                                     a11,
                                                     a12);
  else
    PackagedProcessByLaunchContract_AppExtension = -2147024846;
  v14 = (unsigned __int16)PackagedProcessByLaunchContract_AppExtension;
  if ( PackagedProcessByLaunchContract_AppExtension >= 0 )
    v14 = 0;
  LODWORD(Reply) = v14;
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x18003cca0  push    rbx
0x18003cca2  push    rbp
0x18003cca3  push    rsi
0x18003cca4  push    rdi
0x18003cca5  sub     rsp, 78h
0x18003cca9  mov     r11, [rsp+98h+Reply]
0x18003ccb1  mov     rdi, r9
0x18003ccb4  mov     rsi, r8
0x18003ccb7  mov     rbp, rdx
0x18003ccba  mov     rbx, rcx
0x18003ccbd  cmp     dword ptr [r11], 1
0x18003ccc1  jz      short loc_18003CCCA
0x18003ccc3  mov     eax, 80070032h
0x18003ccc8  jmp     short loc_18003CD48
0x18003ccca  mov     rax, [rsp+98h+arg_58]
0x18003ccd2  mov     r8, rdi; unsigned __int16 *
0x18003ccd5  mov     r9, [rsp+98h+arg_20]; unsigned __int16 *
0x18003ccdd  mov     rdx, rsi; void *
0x18003cce0  mov     [rsp+98h+var_30], rax; struct _APPINFO_PROCESS_INFORMATION *
0x18003cce5  mov     rcx, rbp; void *
0x18003cce8  mov     rax, [rsp+98h+arg_50]
0x18003ccf0  mov     [rsp+98h+var_38], rax; unsigned __int16 *
0x18003ccf5  mov     rax, [rsp+98h+arg_48]
0x18003ccfd  mov     [rsp+98h+var_40], rax; struct _APPINFO_STARTUPINFO_STDHANDLES *
0x18003cd02  mov     rax, [rsp+98h+arg_40]
0x18003cd0a  mov     [rsp+98h+var_48], rax; struct _APPINFO_STARTUPINFO *
0x18003cd0f  mov     rax, [rsp+98h+arg_38]
0x18003cd17  mov     [rsp+98h+var_50], rax; unsigned __int16 *
0x18003cd1c  mov     eax, [r11+18h]
0x18003cd20  mov     [rsp+98h+var_60], eax; unsigned int
0x18003cd24  mov     rax, [r11+10h]
0x18003cd28  mov     [rsp+98h+var_68], rax; unsigned __int16 *
0x18003cd2d  mov     rax, [r11+8]
0x18003cd31  mov     [rsp+98h+lpString1], rax; lpString1
0x18003cd36  mov     rax, [rsp+98h+arg_28]
0x18003cd3e  mov     [rsp+98h+applicationUserModelId], rax; applicationUserModelId
0x18003cd43  call    ?AipCreatePackagedProcessByLaunchContract_AppExtension@@YAJPEAX0PEBGPEAG111K11PEAU_APPINFO_STARTUPINFO@@PEAU_APPINFO_STARTUPINFO_STDHANDLES@@1PEAU_APPINFO_PROCESS_INFORMATION@@@Z; AipCreatePackagedProcessByLaunchContract_AppExtension(void *,void *,ushort const *,ushort *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,_APPINFO_STARTUPINFO *,_APPINFO_STARTUPINFO_STDHANDLES *,ushort const *,_APPINFO_PROCESS_INFORMATION *)
0x18003cd48  xor     ecx, ecx
0x18003cd4a  movzx   edx, ax
0x18003cd4d  test    eax, eax
0x18003cd4f  cmovns  edx, ecx
0x18003cd52  mov     rcx, rbx; pAsync
0x18003cd55  mov     dword ptr [rsp+98h+Reply], edx
0x18003cd5c  lea     rdx, [rsp+98h+Reply]; Reply
0x18003cd64  call    cs:__imp_RpcAsyncCompleteCall
0x18003cd6a  add     rsp, 78h
0x18003cd6e  pop     rdi
0x18003cd6f  pop     rsi
0x18003cd70  pop     rbp
0x18003cd71  pop     rbx
0x18003cd72  retn
```

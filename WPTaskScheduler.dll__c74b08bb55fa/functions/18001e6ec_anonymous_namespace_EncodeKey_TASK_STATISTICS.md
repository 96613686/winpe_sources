# _anonymous_namespace_::EncodeKey__TASK_STATISTICS_

- ea: `0x18001e6ec`
- end: `0x18001e80f`
- name: `_anonymous_namespace_::EncodeKey__TASK_STATISTICS_`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001f3ec`
- `0x18001f87c`

## callees

- `0x18000ea40`
- `0x18001e6ec`
- `0x18001e8e8`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001e7ae`
- `msvcrt!free` at `0x18001e7ae`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e73a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e73a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e77b`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e77b`
- `RPCRT4!MesHandleFree` at `0x18001e7eb`
- `RPCRT4!MesHandleFree` at `0x18001e7eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e7a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e7a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::EncodeKey__TASK_STATISTICS_(HKEY *a1, __int64 a2, const void *a3)
{
  handle_t *v5; // rax
  RPC_STATUS v6; // eax
  LSTATUS v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int pEncodedSize; // [rsp+30h] [rbp-30h] BYREF
  handle_t Handle; // [rsp+38h] [rbp-28h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-18h] BYREF

  pEncodedSize = 0;
  pBuffer = 0;
  Handle = 0;
  v5 = (handle_t *)tlx::replace<void *,long (*)(void *),&long MesHandleFree(void *),0>(&Handle);
  v6 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, v5);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
      goto LABEL_9;
    v7 = (unsigned __int16)v6;
    goto LABEL_8;
  }
  NdrMesTypeEncode3(Handle, &stru_1800282E0, &pProxyInfo, (const unsigned int **)&off_180030000, 1u, a3);
  v7 = RegSetValueExW(*a1, L"Statistics", 0, 3u, (const BYTE *)pBuffer, pEncodedSize);
  free(pBuffer);
  if ( (byte_180030D06 & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, RegistryWrite, v9, 1, v14);
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7;
LABEL_8:
    v7 |= 0x80070000;
  }
LABEL_9:
  if ( Handle )
    MesHandleFree(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e6ec  mov     [rsp-18h+arg_8], rbx
0x18001e6f1  push    rbp
0x18001e6f2  push    rsi
0x18001e6f3  push    rdi
0x18001e6f4  mov     rbp, rsp
0x18001e6f7  sub     rsp, 60h
0x18001e6fb  mov     rax, cs:__security_cookie
0x18001e702  xor     rax, rsp
0x18001e705  mov     [rbp+var_8], rax
0x18001e709  mov     rsi, r8
0x18001e70c  mov     rdi, rcx
0x18001e70f  mov     [rbp+pEncodedSize], 0
0x18001e716  mov     [rbp+pBuffer], 0
0x18001e71e  mov     [rbp+Handle], 0
0x18001e726  lea     rcx, [rbp+Handle]
0x18001e72a  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e72f  mov     r8, rax; pHandle
0x18001e732  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18001e736  lea     rcx, [rbp+pBuffer]; pBuffer
0x18001e73a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001e740  mov     ebx, eax
0x18001e742  test    eax, eax
0x18001e744  jz      short loc_18001E754
0x18001e746  jle     loc_18001E7E2
0x18001e74c  movzx   ebx, ax
0x18001e74f  jmp     loc_18001E7DC
0x18001e754  mov     [rsp+60h+pObject], rsi; pObject
0x18001e759  mov     esi, 1
0x18001e75e  mov     [rsp+60h+nTypeIndex], esi; nTypeIndex
0x18001e762  lea     r9, off_180030000; ArrTypeOffset
0x18001e769  lea     r8, pProxyInfo; pProxyInfo
0x18001e770  lea     rdx, stru_1800282E0; pPicklingInfo
0x18001e777  mov     rcx, [rbp+Handle]; Handle
0x18001e77b  call    cs:__imp_NdrMesTypeEncode3
0x18001e781  mov     eax, [rbp+pEncodedSize]
0x18001e784  mov     rdx, [rbp+pBuffer]
0x18001e788  mov     dword ptr [rsp+60h+pObject], eax; cbData
0x18001e78c  mov     qword ptr [rsp+60h+nTypeIndex], rdx; lpData
0x18001e791  lea     r9d, [rsi+2]; dwType
0x18001e795  xor     r8d, r8d; Reserved
0x18001e798  lea     rdx, aStatistics; "Statistics"
0x18001e79f  mov     rcx, [rdi]; hKey
0x18001e7a2  call    cs:__imp_RegSetValueExW
0x18001e7a8  mov     ebx, eax
0x18001e7aa  mov     rcx, [rbp+pBuffer]; Block
0x18001e7ae  call    cs:__imp_free
0x18001e7b4  test    cs:byte_180030D06, 2
0x18001e7bb  jz      short loc_18001E7D5
0x18001e7bd  lea     rax, [rbp+var_18]
0x18001e7c1  mov     qword ptr [rsp+60h+nTypeIndex], rax
0x18001e7c6  mov     r9d, esi
0x18001e7c9  lea     rdx, RegistryWrite
0x18001e7d0  call    McGenEventWrite_EventWriteTransfer
0x18001e7d5  test    ebx, ebx
0x18001e7d7  jle     short loc_18001E7E2
0x18001e7d9  movzx   ebx, bx
0x18001e7dc  or      ebx, 80070000h
0x18001e7e2  mov     rcx, [rbp+Handle]; Handle
0x18001e7e6  test    rcx, rcx
0x18001e7e9  jz      short loc_18001E7F1
0x18001e7eb  call    cs:__imp_MesHandleFree
0x18001e7f1  mov     eax, ebx
0x18001e7f3  mov     rcx, [rbp+var_8]
0x18001e7f7  xor     rcx, rsp; StackCookie
0x18001e7fa  call    __security_check_cookie
0x18001e7ff  mov     rbx, [rsp+60h+arg_8]
0x18001e807  add     rsp, 60h
0x18001e80b  pop     rdi
0x18001e80c  pop     rsi
0x18001e80d  pop     rbp
0x18001e80e  retn
```

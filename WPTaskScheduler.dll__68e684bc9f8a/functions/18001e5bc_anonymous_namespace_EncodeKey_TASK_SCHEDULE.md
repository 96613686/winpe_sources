# _anonymous_namespace_::EncodeKey__TASK_SCHEDULE_

- ea: `0x18001e5bc`
- end: `0x18001e6e3`
- name: `_anonymous_namespace_::EncodeKey__TASK_SCHEDULE_`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001f3ec`
- `0x18001f7e0`

## callees

- `0x18000ea40`
- `0x18001e5bc`
- `0x18001e8e8`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001e67f`
- `msvcrt!free` at `0x18001e67f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e60a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e60a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e64a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e64a`
- `RPCRT4!MesHandleFree` at `0x18001e6bf`
- `RPCRT4!MesHandleFree` at `0x18001e6bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e673`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e673`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::EncodeKey__TASK_SCHEDULE_(HKEY *a1, __int64 a2, const void *a3)
{
  void **v5; // rax
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
  v5 = tlx::replace<void *,long (*)(void *),&long MesHandleFree(void *),0>(&Handle);
  v6 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, v5);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
      goto LABEL_9;
    v7 = (unsigned __int16)v6;
    goto LABEL_8;
  }
  NdrMesTypeEncode3(Handle, &stru_1800282E0, &pProxyInfo, (const unsigned int **)&off_180030000, 0, a3);
  v7 = RegSetValueExW(*a1, L"Schedule", 0, 3u, (const BYTE *)pBuffer, pEncodedSize);
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
0x18001e5bc  mov     [rsp-18h+arg_8], rbx
0x18001e5c1  push    rbp
0x18001e5c2  push    rsi
0x18001e5c3  push    rdi
0x18001e5c4  mov     rbp, rsp
0x18001e5c7  sub     rsp, 60h
0x18001e5cb  mov     rax, cs:__security_cookie
0x18001e5d2  xor     rax, rsp
0x18001e5d5  mov     [rbp+var_8], rax
0x18001e5d9  mov     rsi, r8
0x18001e5dc  mov     rdi, rcx
0x18001e5df  mov     [rbp+pEncodedSize], 0
0x18001e5e6  mov     [rbp+pBuffer], 0
0x18001e5ee  mov     [rbp+Handle], 0
0x18001e5f6  lea     rcx, [rbp+Handle]
0x18001e5fa  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e5ff  mov     r8, rax; pHandle
0x18001e602  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18001e606  lea     rcx, [rbp+pBuffer]; pBuffer
0x18001e60a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001e610  mov     ebx, eax
0x18001e612  test    eax, eax
0x18001e614  jz      short loc_18001E624
0x18001e616  jle     loc_18001E6B6
0x18001e61c  movzx   ebx, ax
0x18001e61f  jmp     loc_18001E6B0
0x18001e624  mov     [rsp+60h+pObject], rsi; pObject
0x18001e629  mov     [rsp+60h+nTypeIndex], 0; nTypeIndex
0x18001e631  lea     r9, off_180030000; ArrTypeOffset
0x18001e638  lea     r8, pProxyInfo; pProxyInfo
0x18001e63f  lea     rdx, stru_1800282E0; pPicklingInfo
0x18001e646  mov     rcx, [rbp+Handle]; Handle
0x18001e64a  call    cs:__imp_NdrMesTypeEncode3
0x18001e650  mov     eax, [rbp+pEncodedSize]
0x18001e653  mov     rdx, [rbp+pBuffer]
0x18001e657  mov     dword ptr [rsp+60h+pObject], eax; cbData
0x18001e65b  mov     qword ptr [rsp+60h+nTypeIndex], rdx; lpData
0x18001e660  mov     r9d, 3; dwType
0x18001e666  xor     r8d, r8d; Reserved
0x18001e669  lea     rdx, aSchedule; "Schedule"
0x18001e670  mov     rcx, [rdi]; hKey
0x18001e673  call    cs:__imp_RegSetValueExW
0x18001e679  mov     ebx, eax
0x18001e67b  mov     rcx, [rbp+pBuffer]; Block
0x18001e67f  call    cs:__imp_free
0x18001e685  test    cs:byte_180030D06, 2
0x18001e68c  jz      short loc_18001E6A9
0x18001e68e  lea     rax, [rbp+var_18]
0x18001e692  mov     qword ptr [rsp+60h+nTypeIndex], rax
0x18001e697  mov     r9d, 1
0x18001e69d  lea     rdx, RegistryWrite
0x18001e6a4  call    McGenEventWrite_EventWriteTransfer
0x18001e6a9  test    ebx, ebx
0x18001e6ab  jle     short loc_18001E6B6
0x18001e6ad  movzx   ebx, bx
0x18001e6b0  or      ebx, 80070000h
0x18001e6b6  mov     rcx, [rbp+Handle]; Handle
0x18001e6ba  test    rcx, rcx
0x18001e6bd  jz      short loc_18001E6C5
0x18001e6bf  call    cs:__imp_MesHandleFree
0x18001e6c5  mov     eax, ebx
0x18001e6c7  mov     rcx, [rbp+var_8]
0x18001e6cb  xor     rcx, rsp; StackCookie
0x18001e6ce  call    __security_check_cookie
0x18001e6d3  mov     rbx, [rsp+60h+arg_8]
0x18001e6db  add     rsp, 60h
0x18001e6df  pop     rdi
0x18001e6e0  pop     rsi
0x18001e6e1  pop     rbp
0x18001e6e2  retn
```

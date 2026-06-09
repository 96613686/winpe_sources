# _anonymous_namespace_::EncodeKey__TASK_RUNTIME_DATA_

- ea: `0x18001e48c`
- end: `0x18001e5b3`
- name: `_anonymous_namespace_::EncodeKey__TASK_RUNTIME_DATA_`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001f3ec`
- `0x18001f65c`

## callees

- `0x18000ea40`
- `0x18001e48c`
- `0x18001e8e8`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x18001e54f`
- `msvcrt!free` at `0x18001e54f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e4da`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001e4da`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e51a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001e51a`
- `RPCRT4!MesHandleFree` at `0x18001e58f`
- `RPCRT4!MesHandleFree` at `0x18001e58f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e543`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e543`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::EncodeKey__TASK_RUNTIME_DATA_(HKEY *a1, __int64 a2, const void *a3)
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
  NdrMesTypeEncode3(Handle, &stru_1800282E0, &pProxyInfo, (const unsigned int **)&off_180030000, 2u, a3);
  v7 = RegSetValueExW(*a1, L"RuntimeData", 0, 3u, (const BYTE *)pBuffer, pEncodedSize);
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
0x18001e48c  mov     [rsp-18h+arg_8], rbx
0x18001e491  push    rbp
0x18001e492  push    rsi
0x18001e493  push    rdi
0x18001e494  mov     rbp, rsp
0x18001e497  sub     rsp, 60h
0x18001e49b  mov     rax, cs:__security_cookie
0x18001e4a2  xor     rax, rsp
0x18001e4a5  mov     [rbp+var_8], rax
0x18001e4a9  mov     rsi, r8
0x18001e4ac  mov     rdi, rcx
0x18001e4af  mov     [rbp+pEncodedSize], 0
0x18001e4b6  mov     [rbp+pBuffer], 0
0x18001e4be  mov     [rbp+Handle], 0
0x18001e4c6  lea     rcx, [rbp+Handle]
0x18001e4ca  call    ??$replace@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AJPEAX@Z$1?MesHandleFree@@YAJ0@Z$0A@@0@@Z; tlx::replace<void *,long (*)(void *),&MesHandleFree(void *),0>(tlx::auto_xxx<void *,long (*)(void *),&MesHandleFree(void *),0> &)
0x18001e4cf  mov     r8, rax; pHandle
0x18001e4d2  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18001e4d6  lea     rcx, [rbp+pBuffer]; pBuffer
0x18001e4da  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001e4e0  mov     ebx, eax
0x18001e4e2  test    eax, eax
0x18001e4e4  jz      short loc_18001E4F4
0x18001e4e6  jle     loc_18001E586
0x18001e4ec  movzx   ebx, ax
0x18001e4ef  jmp     loc_18001E580
0x18001e4f4  mov     [rsp+60h+pObject], rsi; pObject
0x18001e4f9  mov     [rsp+60h+nTypeIndex], 2; nTypeIndex
0x18001e501  lea     r9, off_180030000; ArrTypeOffset
0x18001e508  lea     r8, pProxyInfo; pProxyInfo
0x18001e50f  lea     rdx, stru_1800282E0; pPicklingInfo
0x18001e516  mov     rcx, [rbp+Handle]; Handle
0x18001e51a  call    cs:__imp_NdrMesTypeEncode3
0x18001e520  mov     eax, [rbp+pEncodedSize]
0x18001e523  mov     rdx, [rbp+pBuffer]
0x18001e527  mov     dword ptr [rsp+60h+pObject], eax; cbData
0x18001e52b  mov     qword ptr [rsp+60h+nTypeIndex], rdx; lpData
0x18001e530  mov     r9d, 3; dwType
0x18001e536  xor     r8d, r8d; Reserved
0x18001e539  lea     rdx, aRuntimedata; "RuntimeData"
0x18001e540  mov     rcx, [rdi]; hKey
0x18001e543  call    cs:__imp_RegSetValueExW
0x18001e549  mov     ebx, eax
0x18001e54b  mov     rcx, [rbp+pBuffer]; Block
0x18001e54f  call    cs:__imp_free
0x18001e555  test    cs:byte_180030D06, 2
0x18001e55c  jz      short loc_18001E579
0x18001e55e  lea     rax, [rbp+var_18]
0x18001e562  mov     qword ptr [rsp+60h+nTypeIndex], rax
0x18001e567  mov     r9d, 1
0x18001e56d  lea     rdx, RegistryWrite
0x18001e574  call    McGenEventWrite_EventWriteTransfer
0x18001e579  test    ebx, ebx
0x18001e57b  jle     short loc_18001E586
0x18001e57d  movzx   ebx, bx
0x18001e580  or      ebx, 80070000h
0x18001e586  mov     rcx, [rbp+Handle]; Handle
0x18001e58a  test    rcx, rcx
0x18001e58d  jz      short loc_18001E595
0x18001e58f  call    cs:__imp_MesHandleFree
0x18001e595  mov     eax, ebx
0x18001e597  mov     rcx, [rbp+var_8]
0x18001e59b  xor     rcx, rsp; StackCookie
0x18001e59e  call    __security_check_cookie
0x18001e5a3  mov     rbx, [rsp+60h+arg_8]
0x18001e5ab  add     rsp, 60h
0x18001e5af  pop     rdi
0x18001e5b0  pop     rsi
0x18001e5b1  pop     rbp
0x18001e5b2  retn
```

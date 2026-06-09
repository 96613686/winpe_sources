# PAC_DecodeS4UDelegationInformation(uchar *,ulong,_S4U_DELEGATION_INFO * *)

- ea: `0x18006f2d0`
- end: `0x18006f374`
- name: `?PAC_DecodeS4UDelegationInformation@@YAJPEAEKPEAPEAU_S4U_DELEGATION_INFO@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _S4U_DELEGATION_INFO **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a000`
- `0x1800837f8`

## callees

- `0x18006f2d0`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18006f348`
- `RPCRT4!NdrMesTypeDecode3` at `0x18006f348`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f302`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f302`
- `RPCRT4!MesHandleFree` at `0x18006f362`
- `RPCRT4!MesHandleFree` at `0x18006f362`

## pseudocode

```c
__int64 __fastcall PAC_DecodeS4UDelegationInformation(unsigned __int8 *a1, int a2, struct _S4U_DELEGATION_INFO **a3)
{
  unsigned int v6; // ebx
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+20h] BYREF

  Handle = 0;
  v8 = 0;
  if ( MesDecodeIncrementalHandleCreate(&v8, PacReadFcn, &Handle) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v8) = a2;
    *(_QWORD *)&v8 = a1;
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 3u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x18006f2d0  mov     rax, rsp
0x18006f2d3  push    rbx
0x18006f2d4  push    rsi
0x18006f2d5  push    rdi
0x18006f2d6  push    r14
0x18006f2d8  sub     rsp, 48h
0x18006f2dc  mov     r14, r8
0x18006f2df  mov     edi, edx
0x18006f2e1  mov     rsi, rcx
0x18006f2e4  mov     qword ptr [rax+20h], 0
0x18006f2ec  xorps   xmm0, xmm0
0x18006f2ef  movups  xmmword ptr [rax-38h], xmm0
0x18006f2f3  lea     r8, [rax+20h]; pHandle
0x18006f2f7  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18006f2fe  lea     rcx, [rax-38h]; UserState
0x18006f302  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x18006f308  test    eax, eax
0x18006f30a  jz      short loc_18006F313
0x18006f30c  mov     ebx, 0C000009Ah
0x18006f311  jmp     short loc_18006F355
0x18006f313  xor     ebx, ebx
0x18006f315  mov     [rsp+68h+var_30], edi
0x18006f319  mov     [rsp+68h+var_38], rsi
0x18006f31e  mov     [rsp+68h+pObject], r14; pObject
0x18006f323  mov     [rsp+68h+nTypeIndex], 3; nTypeIndex
0x18006f32b  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f332  lea     r8, pProxyInfo; pProxyInfo
0x18006f339  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f340  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f348  call    cs:__imp_NdrMesTypeDecode3
0x18006f34e  jmp     short loc_18006F355
0x18006f350  mov     ebx, 0C000000Dh
0x18006f355  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f35d  test    rcx, rcx
0x18006f360  jz      short loc_18006F368
0x18006f362  call    cs:__imp_MesHandleFree
0x18006f368  mov     eax, ebx
0x18006f36a  add     rsp, 48h
0x18006f36e  pop     r14
0x18006f370  pop     rdi
0x18006f371  pop     rsi
0x18006f372  pop     rbx
0x18006f373  retn
```

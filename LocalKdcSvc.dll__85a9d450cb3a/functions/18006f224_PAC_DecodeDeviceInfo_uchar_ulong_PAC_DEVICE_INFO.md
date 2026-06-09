# PAC_DecodeDeviceInfo(uchar *,ulong,_PAC_DEVICE_INFO * *)

- ea: `0x18006f224`
- end: `0x18006f2c8`
- name: `?PAC_DecodeDeviceInfo@@YAJPEAEKPEAPEAU_PAC_DEVICE_INFO@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _PAC_DEVICE_INFO **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180070fdc`

## callees

- `0x18006f224`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18006f29c`
- `RPCRT4!NdrMesTypeDecode3` at `0x18006f29c`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f256`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f256`
- `RPCRT4!MesHandleFree` at `0x18006f2b6`
- `RPCRT4!MesHandleFree` at `0x18006f2b6`

## pseudocode

```c
__int64 __fastcall PAC_DecodeDeviceInfo(unsigned __int8 *a1, int a2, struct _PAC_DEVICE_INFO **a3)
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
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 5u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x18006f224  mov     rax, rsp
0x18006f227  push    rbx
0x18006f228  push    rsi
0x18006f229  push    rdi
0x18006f22a  push    r14
0x18006f22c  sub     rsp, 48h
0x18006f230  mov     r14, r8
0x18006f233  mov     edi, edx
0x18006f235  mov     rsi, rcx
0x18006f238  mov     qword ptr [rax+20h], 0
0x18006f240  xorps   xmm0, xmm0
0x18006f243  movups  xmmword ptr [rax-38h], xmm0
0x18006f247  lea     r8, [rax+20h]; pHandle
0x18006f24b  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18006f252  lea     rcx, [rax-38h]; UserState
0x18006f256  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x18006f25c  test    eax, eax
0x18006f25e  jz      short loc_18006F267
0x18006f260  mov     ebx, 0C000009Ah
0x18006f265  jmp     short loc_18006F2A9
0x18006f267  xor     ebx, ebx
0x18006f269  mov     [rsp+68h+var_30], edi
0x18006f26d  mov     [rsp+68h+var_38], rsi
0x18006f272  mov     [rsp+68h+pObject], r14; pObject
0x18006f277  mov     [rsp+68h+nTypeIndex], 5; nTypeIndex
0x18006f27f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f286  lea     r8, pProxyInfo; pProxyInfo
0x18006f28d  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f294  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f29c  call    cs:__imp_NdrMesTypeDecode3
0x18006f2a2  jmp     short loc_18006F2A9
0x18006f2a4  mov     ebx, 0C000000Dh
0x18006f2a9  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f2b1  test    rcx, rcx
0x18006f2b4  jz      short loc_18006F2BC
0x18006f2b6  call    cs:__imp_MesHandleFree
0x18006f2bc  mov     eax, ebx
0x18006f2be  add     rsp, 48h
0x18006f2c2  pop     r14
0x18006f2c4  pop     rdi
0x18006f2c5  pop     rsi
0x18006f2c6  pop     rbx
0x18006f2c7  retn
```

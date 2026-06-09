# PAC_DecodeValidationInformation(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO3 * *)

- ea: `0x18006f37c`
- end: `0x18006f420`
- name: `?PAC_DecodeValidationInformation@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `164`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO3 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800710d8`

## callees

- `0x18006f37c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18006f3f4`
- `RPCRT4!NdrMesTypeDecode3` at `0x18006f3f4`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f3ae`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f3ae`
- `RPCRT4!MesHandleFree` at `0x18006f40e`
- `RPCRT4!MesHandleFree` at `0x18006f40e`

## pseudocode

```c
__int64 __fastcall PAC_DecodeValidationInformation(
        unsigned __int8 *a1,
        int a2,
        struct _NETLOGON_VALIDATION_SAM_INFO3 **a3)
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
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x18006f37c  mov     rax, rsp
0x18006f37f  push    rbx
0x18006f380  push    rsi
0x18006f381  push    rdi
0x18006f382  push    r14
0x18006f384  sub     rsp, 48h
0x18006f388  mov     r14, r8
0x18006f38b  mov     edi, edx
0x18006f38d  mov     rsi, rcx
0x18006f390  mov     qword ptr [rax+20h], 0
0x18006f398  xorps   xmm0, xmm0
0x18006f39b  movups  xmmword ptr [rax-38h], xmm0
0x18006f39f  lea     r8, [rax+20h]; pHandle
0x18006f3a3  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18006f3aa  lea     rcx, [rax-38h]; UserState
0x18006f3ae  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x18006f3b4  test    eax, eax
0x18006f3b6  jz      short loc_18006F3BF
0x18006f3b8  mov     ebx, 0C000009Ah
0x18006f3bd  jmp     short loc_18006F401
0x18006f3bf  xor     ebx, ebx
0x18006f3c1  mov     [rsp+68h+var_30], edi
0x18006f3c5  mov     [rsp+68h+var_38], rsi
0x18006f3ca  mov     [rsp+68h+pObject], r14; pObject
0x18006f3cf  mov     [rsp+68h+nTypeIndex], 1; nTypeIndex
0x18006f3d7  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f3de  lea     r8, pProxyInfo; pProxyInfo
0x18006f3e5  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f3ec  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f3f4  call    cs:__imp_NdrMesTypeDecode3
0x18006f3fa  jmp     short loc_18006F401
0x18006f3fc  mov     ebx, 0C000000Dh
0x18006f401  mov     rcx, [rsp+68h+Handle]; Handle
0x18006f409  test    rcx, rcx
0x18006f40c  jz      short loc_18006F414
0x18006f40e  call    cs:__imp_MesHandleFree
0x18006f414  mov     eax, ebx
0x18006f416  add     rsp, 48h
0x18006f41a  pop     r14
0x18006f41c  pop     rdi
0x18006f41d  pop     rsi
0x18006f41e  pop     rbx
0x18006f41f  retn
```

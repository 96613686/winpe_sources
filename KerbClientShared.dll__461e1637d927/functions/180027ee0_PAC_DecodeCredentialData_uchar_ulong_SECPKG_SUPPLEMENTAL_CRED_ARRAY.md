# PAC_DecodeCredentialData(uchar *,ulong,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180027ee0`
- end: `0x180027f95`
- name: `?PAC_DecodeCredentialData@@YAJPEAEKPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `181`
- prototype: `int(unsigned __int8 *, unsigned int, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016190`

## callees

- `0x180027ee0`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x180027f7f`
- `RPCRT4!MesHandleFree` at `0x180027f7f`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180027f19`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x180027f19`
- `RPCRT4!NdrMesTypeDecode3` at `0x180027f5c`
- `RPCRT4!NdrMesTypeDecode3` at `0x180027f5c`

## pseudocode

```c
__int64 __fastcall PAC_DecodeCredentialData(unsigned __int8 *a1, int a2, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a3)
{
  unsigned int v6; // ebx
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  handle_t Handle; // [rsp+78h] [rbp+20h] BYREF

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
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 2u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180027ee0  mov     rax, rsp
0x180027ee3  mov     [rax+8], rbx
0x180027ee7  mov     [rax+18h], r8
0x180027eeb  push    rsi
0x180027eec  push    rdi
0x180027eed  push    r14
0x180027eef  sub     rsp, 40h
0x180027ef3  mov     rdi, r8
0x180027ef6  mov     esi, edx
0x180027ef8  mov     r14, rcx
0x180027efb  mov     qword ptr [rax+20h], 0
0x180027f03  xorps   xmm0, xmm0
0x180027f06  movups  xmmword ptr [rax-28h], xmm0
0x180027f0a  lea     r8, [rax+20h]; pHandle
0x180027f0e  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x180027f15  lea     rcx, [rax-28h]; UserState
0x180027f19  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x180027f1f  test    eax, eax
0x180027f21  jz      short loc_180027F2A
0x180027f23  mov     ebx, 0C000009Ah
0x180027f28  jmp     short loc_180027F75
0x180027f2a  xor     ebx, ebx
0x180027f2c  mov     [rsp+58h+var_20], esi
0x180027f30  mov     [rsp+58h+var_28], r14
0x180027f35  mov     [rsp+58h+pObject], rdi; pObject
0x180027f3a  mov     [rsp+58h+nTypeIndex], 2; nTypeIndex
0x180027f42  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180027f49  lea     r8, pProxyInfo; pProxyInfo
0x180027f50  lea     rdx, pPicklingInfo; pPicklingInfo
0x180027f57  mov     rcx, [rsp+58h+Handle]; Handle
0x180027f5c  call    cs:__imp_NdrMesTypeDecode3
0x180027f62  jmp     short loc_180027F75
0x180027f64  mov     rax, [rsp+58h+arg_10]
0x180027f69  mov     qword ptr [rax], 0
0x180027f70  mov     ebx, 0C000000Dh
0x180027f75  mov     rcx, [rsp+58h+Handle]; Handle
0x180027f7a  test    rcx, rcx
0x180027f7d  jz      short loc_180027F85
0x180027f7f  call    cs:__imp_MesHandleFree
0x180027f85  mov     eax, ebx
0x180027f87  mov     rbx, [rsp+58h+arg_0]
0x180027f8c  add     rsp, 40h
0x180027f90  pop     r14
0x180027f92  pop     rdi
0x180027f93  pop     rsi
0x180027f94  retn
```

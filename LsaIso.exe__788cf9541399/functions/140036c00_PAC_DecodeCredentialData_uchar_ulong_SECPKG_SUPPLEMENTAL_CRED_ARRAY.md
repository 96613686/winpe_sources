# PAC_DecodeCredentialData(uchar *,ulong,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x140036c00`
- end: `0x140036cb5`
- name: `?PAC_DecodeCredentialData@@YAJPEAEKPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `181`
- prototype: `int(unsigned __int8 *, unsigned int, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400145ac`

## callees

- `0x140036c00`

## import_xrefs

- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x140036c39`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x140036c39`
- `RPCRT4!MesHandleFree` at `0x140036c9f`
- `RPCRT4!MesHandleFree` at `0x140036c9f`
- `RPCRT4!NdrMesTypeDecode3` at `0x140036c7c`
- `RPCRT4!NdrMesTypeDecode3` at `0x140036c7c`

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
    NdrMesTypeDecode3(Handle, &stru_14004BE00, &pProxyInfo, (const unsigned int **)&off_1400521D8, 2u, a3);
  }
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x140036c00  mov     rax, rsp
0x140036c03  mov     [rax+8], rbx
0x140036c07  mov     [rax+18h], r8
0x140036c0b  push    rsi
0x140036c0c  push    rdi
0x140036c0d  push    r14
0x140036c0f  sub     rsp, 40h
0x140036c13  mov     rdi, r8
0x140036c16  mov     esi, edx
0x140036c18  mov     r14, rcx
0x140036c1b  mov     qword ptr [rax+20h], 0
0x140036c23  xorps   xmm0, xmm0
0x140036c26  movups  xmmword ptr [rax-28h], xmm0
0x140036c2a  lea     r8, [rax+20h]; pHandle
0x140036c2e  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x140036c35  lea     rcx, [rax-28h]; UserState
0x140036c39  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x140036c3f  test    eax, eax
0x140036c41  jz      short loc_140036C4A
0x140036c43  mov     ebx, 0C000009Ah
0x140036c48  jmp     short loc_140036C95
0x140036c4a  xor     ebx, ebx
0x140036c4c  mov     [rsp+58h+var_20], esi
0x140036c50  mov     [rsp+58h+var_28], r14
0x140036c55  mov     [rsp+58h+pObject], rdi; pObject
0x140036c5a  mov     [rsp+58h+nTypeIndex], 2; nTypeIndex
0x140036c62  lea     r9, off_1400521D8; ArrTypeOffset
0x140036c69  lea     r8, pProxyInfo; pProxyInfo
0x140036c70  lea     rdx, stru_14004BE00; pPicklingInfo
0x140036c77  mov     rcx, [rsp+58h+Handle]; Handle
0x140036c7c  call    cs:__imp_NdrMesTypeDecode3
0x140036c82  jmp     short loc_140036C95
0x140036c84  mov     rax, [rsp+58h+arg_10]
0x140036c89  mov     qword ptr [rax], 0
0x140036c90  mov     ebx, 0C000000Dh
0x140036c95  mov     rcx, [rsp+58h+Handle]; Handle
0x140036c9a  test    rcx, rcx
0x140036c9d  jz      short loc_140036CA5
0x140036c9f  call    cs:__imp_MesHandleFree
0x140036ca5  mov     eax, ebx
0x140036ca7  mov     rbx, [rsp+58h+arg_0]
0x140036cac  add     rsp, 40h
0x140036cb0  pop     r14
0x140036cb2  pop     rdi
0x140036cb3  pop     rsi
0x140036cb4  retn
```

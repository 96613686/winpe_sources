# PAC_DecodeValidationInformationEx(uchar *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 * *)

- ea: `0x18006f428`
- end: `0x18006f4ec`
- name: `?PAC_DecodeValidationInformationEx@@YAJPEAEKPEAPEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z`
- size: `196`
- prototype: `int(unsigned __int8 *, unsigned int, struct _NETLOGON_VALIDATION_SAM_INFO4 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180070918`

## callees

- `0x18005a090`
- `0x18006f428`
- `0x1800716bc`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18006f49f`
- `RPCRT4!NdrMesTypeDecode3` at `0x18006f49f`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f45e`
- `RPCRT4!MesDecodeIncrementalHandleCreate` at `0x18006f45e`
- `RPCRT4!MesHandleFree` at `0x18006f4d4`
- `RPCRT4!MesHandleFree` at `0x18006f4d4`

## pseudocode

```c
__int64 __fastcall PAC_DecodeValidationInformationEx(
        unsigned __int8 *a1,
        int a2,
        struct _NETLOGON_VALIDATION_SAM_INFO4 **a3)
{
  int v6; // ebx
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF
  handle_t Handle; // [rsp+68h] [rbp+20h] BYREF

  Handle = 0;
  v8 = 0;
  if ( MesDecodeIncrementalHandleCreate(&v8, PacReadFcn, &Handle) )
  {
    v6 = -1073741670;
  }
  else
  {
    DWORD2(v8) = a2;
    *(_QWORD *)&v8 = a1;
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, a3);
    v6 = PacValidateInfo4(*a3);
    if ( v6 < 0 )
    {
      MIDL_user_free(*a3);
      *a3 = 0;
    }
  }
  if ( Handle )
    MesHandleFree(Handle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006f428  mov     rax, rsp
0x18006f42b  mov     [rax+8], rbx
0x18006f42f  mov     [rax+10h], rsi
0x18006f433  push    rdi
0x18006f434  sub     rsp, 40h
0x18006f438  mov     rdi, r8
0x18006f43b  mov     ebx, edx
0x18006f43d  mov     rsi, rcx
0x18006f440  mov     qword ptr [rax+20h], 0
0x18006f448  xorps   xmm0, xmm0
0x18006f44b  movups  xmmword ptr [rax-18h], xmm0
0x18006f44f  lea     r8, [rax+20h]; pHandle
0x18006f453  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; ReadFn
0x18006f45a  lea     rcx, [rax-18h]; UserState
0x18006f45e  call    cs:__imp_MesDecodeIncrementalHandleCreate
0x18006f464  test    eax, eax
0x18006f466  jz      short loc_18006F46F
0x18006f468  mov     ebx, 0C000009Ah
0x18006f46d  jmp     short loc_18006F4CA
0x18006f46f  mov     [rsp+48h+var_10], ebx
0x18006f473  mov     [rsp+48h+var_18], rsi
0x18006f478  mov     [rsp+48h+pObject], rdi; pObject
0x18006f47d  mov     [rsp+48h+nTypeIndex], 4; nTypeIndex
0x18006f485  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18006f48c  lea     r8, pProxyInfo; pProxyInfo
0x18006f493  lea     rdx, pPicklingInfo; pPicklingInfo
0x18006f49a  mov     rcx, [rsp+48h+Handle]; Handle
0x18006f49f  call    cs:__imp_NdrMesTypeDecode3
0x18006f4a5  nop
0x18006f4a6  mov     rcx, [rdi]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x18006f4a9  call    ?PacValidateInfo4@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO4@@@Z; PacValidateInfo4(_NETLOGON_VALIDATION_SAM_INFO4 * const)
0x18006f4ae  mov     ebx, eax
0x18006f4b0  test    eax, eax
0x18006f4b2  jns     short loc_18006F4CA
0x18006f4b4  mov     rcx, [rdi]; void *
0x18006f4b7  call    MIDL_user_free
0x18006f4bc  mov     qword ptr [rdi], 0
0x18006f4c3  jmp     short loc_18006F4CA
0x18006f4c5  mov     ebx, 0C000000Dh
0x18006f4ca  mov     rcx, [rsp+48h+Handle]; Handle
0x18006f4cf  test    rcx, rcx
0x18006f4d2  jz      short loc_18006F4DA
0x18006f4d4  call    cs:__imp_MesHandleFree
0x18006f4da  mov     eax, ebx
0x18006f4dc  mov     rbx, [rsp+48h+arg_0]
0x18006f4e1  mov     rsi, [rsp+48h+arg_8]
0x18006f4e6  add     rsp, 40h
0x18006f4ea  pop     rdi
0x18006f4eb  retn
```

# DeserializeObject<AadCredentialBagSerializer,_AadCredentialBag>(AadCredentialBagSerializer &,uchar *,ulong,_AadCredentialBag *)

- ea: `0x180071308`
- end: `0x18007148f`
- name: `??$DeserializeObject@VAadCredentialBagSerializer@@U_AadCredentialBag@@@@YAJAEAVAadCredentialBagSerializer@@PEAEKPEAU_AadCredentialBag@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180071854`

## callees

- `0x1800049d0`
- `0x180071308`
- `0x1800719c4`
- `0x1800719f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180071462`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180071462`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071374`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071374`
- `RPCRT4!MesHandleFree` at `0x180071472`
- `RPCRT4!MesHandleFree` at `0x180071472`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800713ca`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800713ca`
- `RPCRT4!NdrMesTypeDecode3` at `0x18007140a`
- `RPCRT4!NdrMesTypeDecode3` at `0x18007140a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeserializeObject<AadCredentialBagSerializer,_AadCredentialBag>(
        __int64 a1,
        void *a2,
        unsigned int a3,
        _OWORD *a4)
{
  rsize_t v5; // r14
  void *v6; // r15
  unsigned int v7; // esi
  _BYTE *v8; // rdi
  _BYTE *v9; // rax
  unsigned int v10; // ebx
  void *v11; // rbx
  RPC_STATUS v12; // eax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  handle_t pHandle; // [rsp+78h] [rbp+10h] BYREF

  v5 = a3;
  v6 = a2;
  pHandle = 0;
  v7 = 0;
  v8 = 0;
  if ( !a2 || !a3 || !a4 )
    goto LABEL_13;
  if ( (void *)(((unsigned __int64)a2 + 7) & 0xFFFFFFFFFFFFFFF8uLL) != a2 )
  {
    v7 = a3 + 16;
    if ( a3 + 16 >= a3 )
    {
      v9 = malloc(v7);
      v8 = v9;
      if ( !v9 )
      {
        v10 = -2147024882;
        goto LABEL_14;
      }
      v11 = (void *)((unsigned __int64)(v9 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      memcpy_s(v11, v5, v6, v5);
      v6 = v11;
      goto LABEL_10;
    }
    v7 = -1;
LABEL_13:
    v10 = -2147024809;
    goto LABEL_14;
  }
LABEL_10:
  *a4 = 0;
  v12 = MesDecodeBufferHandleCreate((char *)v6, v5, &pHandle);
  if ( v12 )
  {
    v10 = HandleRpcError(v12);
  }
  else
  {
    NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, a4);
    v10 = 0;
  }
LABEL_14:
  if ( v8 )
  {
    v13 = v7;
    v14 = v8;
    if ( v7 )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    free(v8);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return v10;
}

```

## disassembly

```asm
0x180071308  mov     [rsp+arg_10], rbx
0x18007130d  mov     [rsp+arg_0], rcx
0x180071312  push    rsi
0x180071313  push    rdi
0x180071314  push    r12
0x180071316  push    r14
0x180071318  push    r15
0x18007131a  sub     rsp, 40h
0x18007131e  mov     r12, r9
0x180071321  mov     r14d, r8d
0x180071324  mov     r15, rdx
0x180071327  mov     [rsp+68h+pHandle], 0
0x180071330  xor     esi, esi
0x180071332  mov     dword ptr [rsp+68h+arg_0], esi
0x180071336  xor     edi, edi
0x180071338  mov     [rsp+68h+var_30], rdi
0x18007133d  test    rdx, rdx
0x180071340  jz      loc_180071440
0x180071346  test    r8d, r8d
0x180071349  jz      loc_180071440
0x18007134f  test    r9, r9
0x180071352  jz      loc_180071440
0x180071358  lea     rax, [rdx+7]
0x18007135c  and     rax, 0FFFFFFFFFFFFFFF8h
0x180071360  cmp     rax, rdx
0x180071363  jz      short loc_1800713B7
0x180071365  lea     esi, [r14+10h]
0x180071369  cmp     esi, r14d
0x18007136c  jb      short loc_1800713AF
0x18007136e  mov     dword ptr [rsp+68h+arg_0], esi
0x180071372  mov     ecx, esi; Size
0x180071374  call    cs:__imp_malloc
0x18007137a  mov     rdi, rax
0x18007137d  mov     [rsp+68h+var_30], rax
0x180071382  test    rax, rax
0x180071385  jnz     short loc_180071391
0x180071387  mov     ebx, 8007000Eh
0x18007138c  jmp     loc_180071445
0x180071391  lea     rbx, [rax+7]
0x180071395  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180071399  mov     rdx, r14; DestinationSize
0x18007139c  mov     r9, r14; SourceSize
0x18007139f  mov     r8, r15; Source
0x1800713a2  mov     rcx, rbx; Destination
0x1800713a5  call    memcpy_s
0x1800713aa  mov     r15, rbx
0x1800713ad  jmp     short loc_1800713B7
0x1800713af  or      esi, 0FFFFFFFFh
0x1800713b2  jmp     loc_180071440
0x1800713b7  xorps   xmm0, xmm0
0x1800713ba  movups  xmmword ptr [r12], xmm0
0x1800713bf  lea     r8, [rsp+68h+pHandle]; pHandle
0x1800713c4  mov     edx, r14d; BufferSize
0x1800713c7  mov     rcx, r15; Buffer
0x1800713ca  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800713d0  test    eax, eax
0x1800713d2  jz      short loc_1800713E3
0x1800713d4  mov     ecx, eax; int
0x1800713d6  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x1800713db  mov     ebx, eax
0x1800713dd  mov     [rsp+68h+var_38], eax
0x1800713e1  jmp     short loc_180071445
0x1800713e3  mov     [rsp+68h+pObject], r12; pObject
0x1800713e8  mov     [rsp+68h+nTypeIndex], 0; nTypeIndex
0x1800713f0  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800713f7  lea     r8, pProxyInfo; pProxyInfo
0x1800713fe  lea     rdx, pPicklingInfo; pPicklingInfo
0x180071405  mov     rcx, [rsp+68h+pHandle]; Handle
0x18007140a  call    cs:__imp_NdrMesTypeDecode3
0x180071410  xor     ebx, ebx
0x180071412  jmp     short loc_180071445
0x180071414  mov     ebx, eax
0x180071416  test    eax, eax
0x180071418  jle     short loc_180071423
0x18007141a  movzx   ebx, ax
0x18007141d  or      ebx, 80070000h
0x180071423  mov     [rsp+68h+var_38], ebx
0x180071427  mov     eax, 8000FFFFh
0x18007142c  test    ebx, ebx
0x18007142e  cmovns  ebx, eax
0x180071431  mov     [rsp+68h+var_38], ebx
0x180071435  mov     esi, dword ptr [rsp+68h+arg_0]
0x180071439  mov     rdi, [rsp+68h+var_30]
0x18007143e  jmp     short loc_180071445
0x180071440  mov     ebx, 80070057h
0x180071445  test    rdi, rdi
0x180071448  jz      short loc_180071468
0x18007144a  mov     eax, esi
0x18007144c  mov     rcx, rdi
0x18007144f  test    esi, esi
0x180071451  jz      short loc_18007145F
0x180071453  mov     byte ptr [rcx], 0
0x180071456  inc     rcx
0x180071459  sub     rax, 1
0x18007145d  jnz     short loc_180071453
0x18007145f  mov     rcx, rdi; Block
0x180071462  call    cs:__imp_free
0x180071468  mov     rcx, [rsp+68h+pHandle]; Handle
0x18007146d  test    rcx, rcx
0x180071470  jz      short loc_180071478
0x180071472  call    cs:__imp_MesHandleFree
0x180071478  mov     eax, ebx
0x18007147a  mov     rbx, [rsp+68h+arg_10]
0x180071482  add     rsp, 40h
0x180071486  pop     r15
0x180071488  pop     r14
0x18007148a  pop     r12
0x18007148c  pop     rdi
0x18007148d  pop     rsi
0x18007148e  retn
0x1800a602b  push    rbp
0x1800a602d  sub     rsp, 30h
0x1800a6031  mov     rbp, rdx
0x1800a6034  mov     rcx, [rcx]
0x1800a6037  mov     ecx, [rcx]; unsigned int
0x1800a6039  call    ?SerializationExceptionFilter@@YAHK@Z; SerializationExceptionFilter(ulong)
0x1800a603e  nop
0x1800a603f  add     rsp, 30h
0x1800a6043  pop     rbp
0x1800a6044  retn
```

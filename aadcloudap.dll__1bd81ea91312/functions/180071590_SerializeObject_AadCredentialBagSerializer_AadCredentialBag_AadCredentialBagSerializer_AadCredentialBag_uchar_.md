# SerializeObject<AadCredentialBagSerializer,_AadCredentialBag>(AadCredentialBagSerializer &,_AadCredentialBag &,uchar * *,ulong *)

- ea: `0x180071590`
- end: `0x180071816`
- name: `??$SerializeObject@VAadCredentialBagSerializer@@U_AadCredentialBag@@@@YAJAEAVAadCredentialBagSerializer@@AEAU_AadCredentialBag@@PEAPEAEPEAK@Z`
- size: `646`
- prototype: `__int64 __fastcall(__int64, const void *, char **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180071a28`

## callees

- `0x180003c20`
- `0x1800049d0`
- `0x180071590`
- `0x1800719c4`
- `0x1800719f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800717e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800717e8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071697`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071743`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071697`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180071743`
- `RPCRT4!MesHandleFree` at `0x1800717c3`
- `RPCRT4!MesHandleFree` at `0x1800717c3`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18007161b`
- `RPCRT4!MesEncodeFixedBufferHandleCreate` at `0x18007161b`
- `RPCRT4!NdrMesTypeEncode3` at `0x18007172e`
- `RPCRT4!NdrMesTypeEncode3` at `0x18007172e`
- `RPCRT4!MesBufferHandleReset` at `0x1800716eb`
- `RPCRT4!MesBufferHandleReset` at `0x1800716eb`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18007165e`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x18007165e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SerializeObject<AadCredentialBagSerializer,_AadCredentialBag>(
        __int64 a1,
        const void *a2,
        char **a3,
        unsigned int *a4)
{
  char *v7; // rsi
  unsigned int v8; // r15d
  RPC_STATUS v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ecx
  char *v13; // rax
  char *v14; // r14
  char *v15; // rax
  __int64 v16; // rdx
  char *v17; // rax
  unsigned int pEncodedSize; // [rsp+34h] [rbp-74h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-70h]
  char *pBuffer; // [rsp+40h] [rbp-68h] BYREF
  handle_t Handle; // [rsp+48h] [rbp-60h] BYREF
  char *v23; // [rsp+50h] [rbp-58h]
  __int128 v24; // [rsp+58h] [rbp-50h] BYREF
  __int64 v25; // [rsp+68h] [rbp-40h]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h] BYREF

  pBuffer = 0;
  v7 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  pEncodedSize = 0;
  v8 = 0;
  v20 = 0;
  Handle = 0;
  if ( a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    v9 = MesEncodeFixedBufferHandleCreate(
           (char *)&v24,
           ((unsigned int)&retaddr - 56 - (unsigned int)&v24) & 0xFFFFFFF8,
           &pEncodedSize,
           &Handle);
    if ( v9 )
    {
LABEL_4:
      v10 = HandleRpcError(v9);
      goto LABEL_19;
    }
    v11 = NdrMesTypeAlignSize3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, a2);
    v12 = v11 + 16;
    v8 = -1;
    if ( v11 + 16 >= v11 )
      v8 = v11 + 16;
    v20 = v8;
    v10 = v12 < v11 ? 0x80070216 : 0;
    if ( v12 < v11 )
    {
      v10 = -2147024809;
      goto LABEL_19;
    }
    v13 = (char *)malloc(v8);
    v7 = v13;
    v23 = v13;
    if ( !v13 )
    {
      v10 = -2147024882;
      goto LABEL_19;
    }
    pBuffer = (char *)((unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    v9 = MesBufferHandleReset(Handle, 1u, MES_ENCODE, &pBuffer, v8 + (_DWORD)v13 - (_DWORD)pBuffer, &pEncodedSize);
    if ( v9 )
      goto LABEL_4;
    NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, a2);
    v14 = pBuffer;
    if ( pBuffer == v7 )
    {
      v7 = 0;
    }
    else
    {
      v15 = (char *)malloc(pEncodedSize);
      v14 = v15;
      if ( !v15 )
      {
        v10 = -2147024882;
        goto LABEL_19;
      }
      memcpy_s(v15, pEncodedSize, pBuffer, pEncodedSize);
    }
    *a3 = v14;
    *a4 = pEncodedSize;
    pBuffer = 0;
  }
  else
  {
    v10 = -2147024809;
  }
LABEL_19:
  if ( Handle )
    MesHandleFree(Handle);
  if ( v7 )
  {
    v16 = v8;
    v17 = v7;
    if ( v8 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    free(v7);
  }
  return v10;
}

```

## disassembly

```asm
0x180071590  mov     r11, rsp
0x180071593  mov     [r11+8], rbx
0x180071597  push    rsi
0x180071598  push    r12
0x18007159a  push    r13
0x18007159c  push    r14
0x18007159e  push    r15
0x1800715a0  sub     rsp, 80h
0x1800715a7  mov     rax, cs:__security_cookie
0x1800715ae  xor     rax, rsp
0x1800715b1  mov     [rsp+0A8h+var_38], rax
0x1800715b6  mov     r12, r9
0x1800715b9  mov     r13, r8
0x1800715bc  mov     r14, rdx
0x1800715bf  mov     qword ptr [r11-68h], 0
0x1800715c7  xor     esi, esi
0x1800715c9  mov     [r11-58h], rsi
0x1800715cd  xorps   xmm0, xmm0
0x1800715d0  xor     eax, eax
0x1800715d2  movups  [rsp+0A8h+var_50], xmm0
0x1800715d7  mov     [r11-40h], rax
0x1800715db  mov     [rsp+0A8h+pEncodedSize], eax
0x1800715df  xor     r15d, r15d
0x1800715e2  mov     [r11-70h], r15d
0x1800715e6  mov     [r11-60h], rax
0x1800715ea  test    r8, r8
0x1800715ed  jz      loc_1800717B4
0x1800715f3  test    r9, r9
0x1800715f6  jz      loc_1800717B4
0x1800715fc  mov     [r8], rax
0x1800715ff  mov     [r9], eax
0x180071602  lea     rcx, [r11-49h]
0x180071606  and     rcx, 0FFFFFFFFFFFFFFF8h; pBuffer
0x18007160a  lea     rdx, [r11-38h]
0x18007160e  sub     edx, ecx
0x180071610  and     edx, 0FFFFFFF8h; BufferSize
0x180071613  lea     r9, [r11-60h]; pHandle
0x180071617  lea     r8, [r11-74h]; pEncodedSize
0x18007161b  call    cs:__imp_MesEncodeFixedBufferHandleCreate
0x180071621  test    eax, eax
0x180071623  jz      short loc_180071637
0x180071625  mov     ecx, eax; int
0x180071627  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x18007162c  mov     ebx, eax
0x18007162e  mov     [rsp+0A8h+var_78], eax
0x180071632  jmp     loc_1800717B9
0x180071637  mov     [rsp+0A8h+pObject], r14; pObject
0x18007163c  mov     [rsp+0A8h+nTypeIndex], 0; nTypeIndex
0x180071644  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18007164b  lea     r8, pProxyInfo; pProxyInfo
0x180071652  lea     rdx, pPicklingInfo; pPicklingInfo
0x180071659  mov     rcx, [rsp+0A8h+Handle]; Handle
0x18007165e  call    cs:__imp_NdrMesTypeAlignSize3
0x180071664  lea     ecx, [rax+10h]
0x180071667  or      r15d, 0FFFFFFFFh
0x18007166b  cmp     ecx, eax
0x18007166d  cmovnb  r15d, ecx
0x180071671  mov     [rsp+0A8h+var_70], r15d
0x180071676  sbb     ebx, ebx
0x180071678  and     ebx, 80070216h
0x18007167e  mov     [rsp+0A8h+var_78], ebx
0x180071682  cmp     ecx, eax
0x180071684  jnb     short loc_180071694
0x180071686  mov     ebx, 80070057h
0x18007168b  mov     [rsp+0A8h+var_78], ebx
0x18007168f  jmp     loc_1800717B9
0x180071694  mov     ecx, r15d; Size
0x180071697  call    cs:__imp_malloc
0x18007169d  mov     rsi, rax
0x1800716a0  mov     [rsp+0A8h+var_58], rax
0x1800716a5  test    rax, rax
0x1800716a8  jnz     short loc_1800716B8
0x1800716aa  mov     ebx, 8007000Eh
0x1800716af  mov     [rsp+0A8h+var_78], ebx
0x1800716b3  jmp     loc_1800717B9
0x1800716b8  add     rax, 7
0x1800716bc  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800716c0  mov     [rsp+0A8h+pBuffer], rax
0x1800716c5  mov     ecx, esi
0x1800716c7  sub     ecx, eax
0x1800716c9  add     ecx, r15d
0x1800716cc  lea     rax, [rsp+0A8h+pEncodedSize]
0x1800716d1  mov     [rsp+0A8h+pObject], rax; pEncodedSize
0x1800716d6  mov     [rsp+0A8h+nTypeIndex], ecx; BufferSize
0x1800716da  lea     r9, [rsp+0A8h+pBuffer]; pBuffer
0x1800716df  xor     r8d, r8d; Operation
0x1800716e2  lea     edx, [r8+1]; HandleStyle
0x1800716e6  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1800716eb  call    cs:__imp_MesBufferHandleReset
0x1800716f1  test    eax, eax
0x1800716f3  jz      short loc_180071707
0x1800716f5  mov     ecx, eax; int
0x1800716f7  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x1800716fc  mov     ebx, eax
0x1800716fe  mov     [rsp+0A8h+var_78], eax
0x180071702  jmp     loc_1800717B9
0x180071707  mov     [rsp+0A8h+pObject], r14; pObject
0x18007170c  mov     [rsp+0A8h+nTypeIndex], 0; nTypeIndex
0x180071714  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18007171b  lea     r8, pProxyInfo; pProxyInfo
0x180071722  lea     rdx, pPicklingInfo; pPicklingInfo
0x180071729  mov     rcx, [rsp+0A8h+Handle]; Handle
0x18007172e  call    cs:__imp_NdrMesTypeEncode3
0x180071734  nop
0x180071735  mov     r14, [rsp+0A8h+pBuffer]
0x18007173a  cmp     r14, rsi
0x18007173d  jz      short loc_18007176E
0x18007173f  mov     ecx, [rsp+0A8h+pEncodedSize]; Size
0x180071743  call    cs:__imp_malloc
0x180071749  mov     r14, rax
0x18007174c  test    rax, rax
0x18007174f  jnz     short loc_180071758
0x180071751  mov     ebx, 8007000Eh
0x180071756  jmp     short loc_1800717B9
0x180071758  mov     edx, [rsp+0A8h+pEncodedSize]; DestinationSize
0x18007175c  mov     r9d, edx; SourceSize
0x18007175f  mov     r8, [rsp+0A8h+pBuffer]; Source
0x180071764  mov     rcx, rax; Destination
0x180071767  call    memcpy_s
0x18007176c  jmp     short loc_180071770
0x18007176e  xor     esi, esi
0x180071770  mov     [r13+0], r14
0x180071774  mov     eax, [rsp+0A8h+pEncodedSize]
0x180071778  mov     [r12], eax
0x18007177c  mov     [rsp+0A8h+pBuffer], 0
0x180071785  jmp     short loc_1800717B9
0x180071787  mov     ebx, eax
0x180071789  test    eax, eax
0x18007178b  jle     short loc_180071796
0x18007178d  movzx   ebx, ax
0x180071790  or      ebx, 80070000h
0x180071796  mov     [rsp+0A8h+var_78], ebx
0x18007179a  mov     eax, 8000FFFFh
0x18007179f  test    ebx, ebx
0x1800717a1  cmovns  ebx, eax
0x1800717a4  mov     [rsp+0A8h+var_78], ebx
0x1800717a8  mov     rsi, [rsp+0A8h+var_58]
0x1800717ad  mov     r15d, [rsp+0A8h+var_70]
0x1800717b2  jmp     short loc_1800717B9
0x1800717b4  mov     ebx, 80070057h
0x1800717b9  mov     rcx, [rsp+0A8h+Handle]; Handle
0x1800717be  test    rcx, rcx
0x1800717c1  jz      short loc_1800717C9
0x1800717c3  call    cs:__imp_MesHandleFree
0x1800717c9  test    rsi, rsi
0x1800717cc  jz      short loc_1800717EE
0x1800717ce  mov     edx, r15d
0x1800717d1  mov     rax, rsi
0x1800717d4  test    r15d, r15d
0x1800717d7  jz      short loc_1800717E5
0x1800717d9  mov     byte ptr [rax], 0
0x1800717dc  inc     rax
0x1800717df  sub     rdx, 1
0x1800717e3  jnz     short loc_1800717D9
0x1800717e5  mov     rcx, rsi; Block
0x1800717e8  call    cs:__imp_free
0x1800717ee  mov     eax, ebx
0x1800717f0  mov     rcx, [rsp+0A8h+var_38]
0x1800717f5  xor     rcx, rsp; StackCookie
0x1800717f8  call    __security_check_cookie
0x1800717fd  mov     rbx, [rsp+0A8h+arg_0]
0x180071805  add     rsp, 80h
0x18007180c  pop     r15
0x18007180e  pop     r14
0x180071810  pop     r13
0x180071812  pop     r12
0x180071814  pop     rsi
0x180071815  retn
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

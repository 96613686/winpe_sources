# LsaIsoDecryptAsymmetricKeyBlob(void const *,ulong,_LSA_ISO_ASYMMETRIC_KEY_BLOB * *,void * *,ulong *)

- ea: `0x140005280`
- end: `0x140005530`
- name: `?LsaIsoDecryptAsymmetricKeyBlob@@YAJPEBXKPEAPEAU_LSA_ISO_ASYMMETRIC_KEY_BLOB@@PEAPEAXPEAK@Z`
- size: `688`
- prototype: `__int64 __usercall@<rax>(const void *@<rcx>, unsigned int@<edx>, struct _LSA_ISO_ASYMMETRIC_KEY_BLOB **@<r8>, void **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140003e58`
- `0x1400041d0`

## callees

- `0x140004ca8`
- `0x140005280`
- `0x140005ad4`
- `0x140005df0`
- `0x14000639c`
- `0x140006720`

## import_xrefs

- `RPCRT4!MesHandleFree` at `0x140005505`
- `RPCRT4!MesHandleFree` at `0x140005505`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x140005444`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x140005444`
- `RPCRT4!NdrMesTypeDecode3` at `0x14000549b`
- `RPCRT4!NdrMesTypeDecode3` at `0x14000549b`
- `RPCRT4!RpcExceptionFilter` at `0x140038ece`
- `RPCRT4!RpcExceptionFilter` at `0x140038ece`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400054f3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400054f3`

## pseudocode

```c
__int64 __fastcall LsaIsoDecryptAsymmetricKeyBlob(
        const void *a1,
        int a2,
        struct _LSA_ISO_ASYMMETRIC_KEY_BLOB **a3,
        void **a4,
        unsigned int *a5)
{
  char *v8; // r14
  unsigned int *v9; // r9
  int v10; // edi
  __int16 v11; // cx
  unsigned int *v12; // r9
  void **v13; // r10
  unsigned int v14; // r11d
  int v15; // eax
  RPC_STATUS v16; // esi
  void (*pObject)(void *); // [rsp+28h] [rbp-50h]
  handle_t pHandle; // [rsp+50h] [rbp-28h] BYREF
  unsigned int BufferSize; // [rsp+90h] [rbp+18h] BYREF
  void *v21; // [rsp+98h] [rbp+20h] BYREF

  pHandle = 0;
  *a3 = 0;
  v8 = 0;
  v21 = 0;
  BufferSize = 0;
  if ( a4 )
    *a4 = 0;
  v9 = a5;
  if ( a5 )
    *a5 = 0;
  if ( a1 )
  {
    if ( a2 )
      goto LABEL_11;
  }
  else if ( a2 )
  {
    v10 = -1073741584;
    goto LABEL_28;
  }
  if ( a1 )
  {
    v10 = -1073741583;
    goto LABEL_28;
  }
LABEL_11:
  if ( a4 )
  {
    if ( !v9 )
    {
      v10 = -1073741577;
      goto LABEL_28;
    }
  }
  else if ( v9 )
  {
    v10 = -1073741578;
    goto LABEL_28;
  }
  LOWORD(a5) = 0;
  v10 = RtlUIntPtrToUShort(0x17u, (unsigned __int16 *)&a5);
  if ( v10 >= 0 )
  {
    if ( (unsigned __int16)(v11 - 15) > (unsigned __int16)a5 || (unsigned __int16)a5 > 0x20u )
    {
      v10 = -1073741585;
    }
    else if ( a1 || v14 )
    {
      if ( dword_140052C5C )
        v15 = LsaIsoIumDecrypt(
                "LsaIsoAsymmetricKeyBlob",
                (unsigned __int16)a5,
                a1,
                v14,
                MIDLAllocWrapper,
                MIDLFreeWrapper,
                &v21,
                &BufferSize,
                v13,
                v12);
      else
        v15 = LsaIsoFakeDecrypt(
                "LsaIsoAsymmetricKeyBlob",
                (unsigned __int16)a5,
                a1,
                v14,
                MIDLAllocWrapper,
                pObject,
                &v21,
                &BufferSize,
                v13,
                v12);
      v8 = (char *)v21;
      v10 = v15;
    }
    else
    {
      v10 = 0;
    }
  }
LABEL_28:
  LODWORD(a5) = v10;
  if ( v10 >= 0 )
  {
    v16 = MesDecodeBufferHandleCreate(v8, BufferSize, &pHandle);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids,
          (unsigned int)"LsaIsoDecryptAsymmetricKeyBlob",
          v16);
      v10 = I_RpcMapWin32Status(v16);
    }
    else
    {
      NdrMesTypeDecode3(
        pHandle,
        &pPicklingInfo,
        &ProvIum::ProvIum_ProxyInfo,
        (const unsigned int **)&ArrTypeOffset,
        0,
        a3);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids,
      (unsigned int)"LsaIsoDecryptAsymmetricKeyBlob",
      v10);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  if ( v8 )
    SafeAllocaFreeToHeap(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005280  mov     rax, rsp
0x140005283  mov     [rax+8], rbx
0x140005287  mov     [rax+10h], rsi
0x14000528b  push    rdi
0x14000528c  push    r14
0x14000528e  push    r15
0x140005290  sub     rsp, 60h
0x140005294  mov     r10, r9
0x140005297  mov     r15, r8
0x14000529a  mov     r11d, edx
0x14000529d  mov     rsi, rcx
0x1400052a0  xor     ebx, ebx
0x1400052a2  mov     [rax-28h], rbx
0x1400052a6  mov     [r8], rbx
0x1400052a9  mov     r14d, ebx
0x1400052ac  mov     [rax+20h], rbx
0x1400052b0  mov     [rax+18h], ebx
0x1400052b3  test    r9, r9
0x1400052b6  jz      short loc_1400052BB
0x1400052b8  mov     [r9], rbx
0x1400052bb  mov     r9, [rsp+78h+arg_20]
0x1400052c3  test    r9, r9
0x1400052c6  jz      short loc_1400052CB
0x1400052c8  mov     [r9], ebx
0x1400052cb  test    rsi, rsi
0x1400052ce  jnz     short loc_1400052DF
0x1400052d0  test    r11d, r11d
0x1400052d3  jz      short loc_1400052E4
0x1400052d5  mov     edi, 0C00000F0h
0x1400052da  jmp     loc_1400053E4
0x1400052df  test    r11d, r11d
0x1400052e2  jnz     short loc_1400052F3
0x1400052e4  test    rsi, rsi
0x1400052e7  jz      short loc_1400052F3
0x1400052e9  mov     edi, 0C00000F1h
0x1400052ee  jmp     loc_1400053E4
0x1400052f3  test    r10, r10
0x1400052f6  jnz     short loc_14000530C
0x1400052f8  test    r9, r9
0x1400052fb  jz      short loc_140005307
0x1400052fd  mov     edi, 0C00000F6h
0x140005302  jmp     loc_1400053E4
0x140005307  test    r10, r10
0x14000530a  jz      short loc_14000531B
0x14000530c  test    r9, r9
0x14000530f  jnz     short loc_14000531B
0x140005311  mov     edi, 0C00000F7h
0x140005316  jmp     loc_1400053E4
0x14000531b  mov     word ptr [rsp+78h+arg_20], bx
0x140005323  lea     rdx, [rsp+78h+arg_20]; unsigned __int16 *
0x14000532b  mov     ecx, 17h; unsigned __int64
0x140005330  call    ?RtlUIntPtrToUShort@@YAJ_KPEAG@Z; RtlUIntPtrToUShort(unsigned __int64,ushort *)
0x140005335  mov     edi, eax
0x140005337  test    eax, eax
0x140005339  js      loc_1400053E4
0x14000533f  lea     eax, [rcx-0Fh]
0x140005342  movzx   edx, word ptr [rsp+78h+arg_20]; unsigned __int16
0x14000534a  cmp     ax, dx
0x14000534d  jbe     short loc_140005359
0x14000534f  mov     edi, 0C00000EFh
0x140005354  jmp     loc_1400053E4
0x140005359  mov     eax, 20h ; ' '
0x14000535e  cmp     ax, dx
0x140005361  jb      short loc_14000534F
0x140005363  test    rsi, rsi
0x140005366  jnz     short loc_140005371
0x140005368  test    r11d, r11d
0x14000536b  jnz     short loc_140005371
0x14000536d  mov     edi, ebx
0x14000536f  jmp     short loc_1400053E4
0x140005371  mov     [rsp+78h+var_30], r9; unsigned int *
0x140005376  lea     rax, [rsp+78h+BufferSize]
0x14000537e  mov     r8, rsi; void *
0x140005381  lea     rcx, aLsaisoasymmetr; "LsaIsoAsymmetricKeyBlob"
0x140005388  mov     [rsp+78h+var_38], r10; void **
0x14000538d  mov     r9d, r11d; unsigned int
0x140005390  mov     [rsp+78h+var_40], rax; unsigned int *
0x140005395  lea     rax, [rsp+78h+arg_18]
0x14000539d  mov     [rsp+78h+var_48], rax; void **
0x1400053a2  cmp     cs:dword_140052C5C, ebx
0x1400053a8  jz      short loc_1400053C9
0x1400053aa  lea     rax, MIDLFreeWrapper
0x1400053b1  mov     [rsp+78h+pObject], rax; void (*)(void *)
0x1400053b6  lea     rax, MIDLAllocWrapper
0x1400053bd  mov     qword ptr [rsp+78h+nTypeIndex], rax; void *(*)(unsigned __int64)
0x1400053c2  call    ?LsaIsoIumDecrypt@@YAJPEBDGPEBXKP6APEAX_K@ZP6AXPEAX@ZPEAPEAXPEAK67@Z; LsaIsoIumDecrypt(char const *,ushort,void const *,ulong,void * (*)(unsigned __int64),void (*)(void *),void * *,ulong *,void * *,ulong *)
0x1400053c7  jmp     short loc_1400053DA
0x1400053c9  lea     rax, MIDLAllocWrapper
0x1400053d0  mov     qword ptr [rsp+78h+nTypeIndex], rax; void *(*)(unsigned __int64)
0x1400053d5  call    ?LsaIsoFakeDecrypt@@YAJPEBDGPEBXKP6APEAX_K@ZP6AXPEAX@ZPEAPEAXPEAK67@Z; LsaIsoFakeDecrypt(char const *,ushort,void const *,ulong,void * (*)(unsigned __int64),void (*)(void *),void * *,ulong *,void * *,ulong *)
0x1400053da  mov     r14, [rsp+78h+arg_18]
0x1400053e2  mov     edi, eax
0x1400053e4  mov     dword ptr [rsp+78h+arg_20], edi
0x1400053eb  test    edi, edi
0x1400053ed  jns     short loc_140005435
0x1400053ef  lea     rax, WPP_GLOBAL_Control
0x1400053f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053fd  cmp     rcx, rax
0x140005400  jz      loc_1400054FB
0x140005406  test    byte ptr [rcx+1Ch], 1
0x14000540a  jz      loc_1400054FB
0x140005410  mov     edx, 14h
0x140005415  mov     [rsp+78h+nTypeIndex], edi
0x140005419  lea     r9, aLsaisodecrypta; "LsaIsoDecryptAsymmetricKeyBlob"
0x140005420  lea     r8, WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids
0x140005427  mov     rcx, [rcx+10h]
0x14000542b  call    WPP_SF_sd
0x140005430  jmp     loc_1400054FB
0x140005435  lea     r8, [rsp+78h+pHandle]; pHandle
0x14000543a  mov     edx, [rsp+78h+BufferSize]; BufferSize
0x140005441  mov     rcx, r14; Buffer
0x140005444  call    cs:__imp_MesDecodeBufferHandleCreate
0x14000544a  mov     esi, eax
0x14000544c  test    eax, eax
0x14000544e  jz      short loc_140005478
0x140005450  lea     rax, WPP_GLOBAL_Control
0x140005457  mov     rcx, cs:WPP_GLOBAL_Control
0x14000545e  cmp     rcx, rax
0x140005461  jz      loc_1400054F1
0x140005467  test    byte ptr [rcx+1Ch], 1
0x14000546b  jz      loc_1400054F1
0x140005471  mov     edx, 15h
0x140005476  jmp     short loc_1400054D6
0x140005478  mov     [rsp+78h+pObject], r15; pObject
0x14000547d  mov     [rsp+78h+nTypeIndex], ebx; nTypeIndex
0x140005481  lea     r9, ArrTypeOffset; ArrTypeOffset
0x140005488  lea     r8, ?ProvIum_ProxyInfo@ProvIum@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x14000548f  lea     rdx, pPicklingInfo; pPicklingInfo
0x140005496  mov     rcx, [rsp+78h+pHandle]; Handle
0x14000549b  call    cs:__imp_NdrMesTypeDecode3
0x1400054a1  jmp     short loc_1400054B4
0x1400054a3  mov     esi, eax
0x1400054a5  mov     edi, dword ptr [rsp+78h+arg_20]
0x1400054ac  mov     r14, [rsp+78h+arg_18]
0x1400054b4  test    esi, esi
0x1400054b6  jz      short loc_1400054FB
0x1400054b8  lea     rax, WPP_GLOBAL_Control
0x1400054bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054c6  cmp     rcx, rax
0x1400054c9  jz      short loc_1400054F1
0x1400054cb  test    byte ptr [rcx+1Ch], 1
0x1400054cf  jz      short loc_1400054F1
0x1400054d1  mov     edx, 16h
0x1400054d6  mov     [rsp+78h+nTypeIndex], esi
0x1400054da  lea     r9, aLsaisodecrypta; "LsaIsoDecryptAsymmetricKeyBlob"
0x1400054e1  lea     r8, WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids
0x1400054e8  mov     rcx, [rcx+10h]
0x1400054ec  call    WPP_SF_sd
0x1400054f1  mov     ecx, esi; Status
0x1400054f3  call    cs:__imp_I_RpcMapWin32Status
0x1400054f9  mov     edi, eax
0x1400054fb  mov     rcx, [rsp+78h+pHandle]; Handle
0x140005500  test    rcx, rcx
0x140005503  jz      short loc_14000550B
0x140005505  call    cs:__imp_MesHandleFree
0x14000550b  test    r14, r14
0x14000550e  jz      short loc_140005518
0x140005510  mov     rcx, r14; void *
0x140005513  call    SafeAllocaFreeToHeap
0x140005518  mov     eax, edi
0x14000551a  lea     r11, [rsp+78h+var_18]
0x14000551f  mov     rbx, [r11+20h]
0x140005523  mov     rsi, [r11+28h]
0x140005527  mov     rsp, r11
0x14000552a  pop     r15
0x14000552c  pop     r14
0x14000552e  pop     rdi
0x14000552f  retn
0x140038ec0  push    rbp
0x140038ec2  sub     rsp, 50h
0x140038ec6  mov     rbp, rdx
0x140038ec9  mov     rcx, [rcx]
0x140038ecc  mov     ecx, [rcx]; ExceptionCode
0x140038ece  call    cs:__imp_RpcExceptionFilter
0x140038ed4  nop
0x140038ed5  add     rsp, 50h
0x140038ed9  pop     rbp
0x140038eda  retn
```

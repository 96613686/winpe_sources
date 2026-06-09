# I_SCardReadCache(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong *,int)

- ea: `0x18002bd60`
- end: `0x18002c156`
- name: `?I_SCardReadCache@@YAJ_KPEAU_GUID@@KPEAE2PEAKH@Z`
- size: `1014`
- prototype: `__int64 __fastcall(struct _REDIR_LOCAL_SCARDCONTEXT *, struct _GUID *, int, unsigned __int8 *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000dbf0`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`
- `0x18002bd60`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002c015`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002c015`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002beda`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002bf65`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002beda`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002bf65`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c078`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c078`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002be1b`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002be1b`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bfd2`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002bfd2`

## pseudocode

```c
__int64 __fastcall I_SCardReadCache(
        struct _REDIR_LOCAL_SCARDCONTEXT *a1,
        struct _GUID *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        int a7)
{
  unsigned int *v11; // r15
  struct _RTL_CRITICAL_SECTION *v12; // r12
  unsigned int SCardError; // ebx
  unsigned __int8 *v15; // rsi
  unsigned int v16; // eax
  int v17; // edi
  int v18; // eax
  handle_t pHandle; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-C0h]
  char *pBuffer; // [rsp+50h] [rbp-B8h] BYREF
  struct _BUFFER_LIST_STRUCT *v22; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int8 *v23[2]; // [rsp+60h] [rbp-A8h] BYREF
  _OWORD pObject[2]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v25; // [rsp+90h] [rbp-78h]
  _QWORD v26[4]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v27; // [rsp+C0h] [rbp-48h]
  unsigned int pEncodedSize; // [rsp+110h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v22 = 0;
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  memset(pObject, 0, sizeof(pObject));
  v25 = 0;
  *(_OWORD *)v23 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !a2 )
    return 2148532228LL;
  if ( !a4 )
    return 2148532228LL;
  v11 = a6;
  if ( !a6 )
    return 2148532228LL;
  v12 = *(struct _RTL_CRITICAL_SECTION **)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 68LL) < 2u )
    return 2148532336LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    *(_OWORD *)((char *)pObject + 8) = *(_OWORD *)((char *)a1 + 8);
    *(_OWORD *)&v26[1] = *(_OWORD *)((char *)pObject + 8);
    *((_QWORD *)&pObject[1] + 1) = a2;
    v26[3] = a2;
    LODWORD(v25) = a3;
    LODWORD(v27) = a3;
    v15 = a5;
    if ( a5 )
      v16 = *v11;
    else
      v16 = -1;
    DWORD2(v25) = v16;
    DWORD2(v27) = v16;
    DWORD1(v25) = 0;
    DWORD1(v27) = 0;
    v17 = a7;
    if ( a7 )
    {
      *(_QWORD *)&pObject[0] = a4;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x28u, pObject);
    }
    else
    {
      v26[0] = a4;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x27u, v26);
    }
    v18 = _SendSCardIOCTL(v17 != 0 ? 590068 : 590064, pBuffer, pEncodedSize, &v22, v12, 0xFFFFFFFF, 0x800u);
    if ( v18 )
    {
      SCardError = _MakeSCardError(v18);
      goto LABEL_21;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v22 + 2), *((_DWORD *)v22 + 7), &pHandle) )
    {
      *(_OWORD *)v23 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x29u, v23);
      SCardError = (unsigned int)v23[0];
      v20 = (unsigned int)v23[0];
      if ( !LODWORD(v23[0]) )
      {
        SCardError = _CopyReturnToCallerBuffer(a1, v23[1], HIDWORD(v23[0]), v15, v11, 1u);
        v20 = SCardError;
      }
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x29u, v23);
      goto LABEL_21;
    }
  }
  SCardError = -2146435041;
LABEL_21:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v22 )
    *((_DWORD *)v22 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002bd60  mov     rax, rsp
0x18002bd63  push    rbx
0x18002bd64  push    rsi
0x18002bd65  push    rdi
0x18002bd66  push    r12
0x18002bd68  push    r14
0x18002bd6a  push    r15
0x18002bd6c  sub     rsp, 0D8h
0x18002bd73  mov     rbx, r9
0x18002bd76  mov     esi, r8d
0x18002bd79  mov     rdi, rdx
0x18002bd7c  mov     r14, rcx
0x18002bd7f  mov     [rsp+108h+pBuffer], 0
0x18002bd88  mov     dword ptr [rax+8], 0
0x18002bd8f  mov     [rsp+108h+pHandle], 0
0x18002bd98  mov     [rsp+108h+var_B0], 0
0x18002bda1  xorps   xmm0, xmm0
0x18002bda4  movups  xmmword ptr [rax-68h], xmm0
0x18002bda8  movups  xmmword ptr [rax-58h], xmm0
0x18002bdac  movups  xmmword ptr [rax-48h], xmm0
0x18002bdb0  xorps   xmm1, xmm1
0x18002bdb3  movups  [rsp+108h+var_98], xmm1
0x18002bdb8  movups  xmmword ptr [rax-88h], xmm1
0x18002bdbf  movups  xmmword ptr [rax-78h], xmm1
0x18002bdc3  movups  xmmword ptr [rsp+108h+var_A8], xmm0
0x18002bdc8  test    rcx, rcx
0x18002bdcb  jz      loc_18002C140
0x18002bdd1  test    rdx, rdx
0x18002bdd4  jz      loc_18002C140
0x18002bdda  test    rbx, rbx
0x18002bddd  jz      loc_18002C140
0x18002bde3  mov     r15, [rsp+108h+arg_28]
0x18002bdeb  test    r15, r15
0x18002bdee  jz      loc_18002C140
0x18002bdf4  mov     r12, [rcx]
0x18002bdf7  cmp     dword ptr [r12+44h], 2
0x18002bdfd  jnb     short loc_18002BE09
0x18002bdff  mov     eax, 80100070h
0x18002be04  jmp     loc_18002C145
0x18002be09  lea     r8, [rsp+108h+pHandle]; pHandle
0x18002be0e  lea     rdx, [rsp+108h+pEncodedSize]; pEncodedSize
0x18002be16  lea     rcx, [rsp+108h+pBuffer]; pBuffer
0x18002be1b  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002be21  test    eax, eax
0x18002be23  jz      short loc_18002BE2F
0x18002be25  mov     ebx, 8010001Fh
0x18002be2a  jmp     loc_18002C117
0x18002be2f  movups  xmm0, xmmword ptr [r14+8]
0x18002be34  movdqu  [rsp+108h+var_98+8], xmm0
0x18002be3a  movdqu  [rsp+108h+var_60], xmm0
0x18002be43  mov     [rsp+108h+var_80], rdi
0x18002be4b  mov     [rsp+108h+var_50], rdi
0x18002be53  mov     [rsp+108h+var_78], esi
0x18002be5a  mov     [rsp+108h+var_48], esi
0x18002be61  mov     rsi, [rsp+108h+arg_20]
0x18002be69  test    rsi, rsi
0x18002be6c  jnz     short loc_18002BE73
0x18002be6e  or      eax, 0FFFFFFFFh
0x18002be71  jmp     short loc_18002BE76
0x18002be73  mov     eax, [r15]
0x18002be76  mov     [rsp+108h+var_70], eax
0x18002be7d  mov     [rsp+108h+var_40], eax
0x18002be84  mov     [rsp+108h+var_74], 0
0x18002be8f  mov     [rsp+108h+var_44], 0
0x18002be9a  mov     edi, [rsp+108h+arg_30]
0x18002bea1  test    edi, edi
0x18002bea3  jz      loc_18002BF2E
0x18002bea9  mov     qword ptr [rsp+108h+var_98], rbx
0x18002beae  lea     rax, [rsp+108h+var_98]
0x18002beb3  mov     [rsp+108h+pObject], rax; pObject
0x18002beb8  mov     [rsp+108h+nTypeIndex], 28h ; '('; nTypeIndex
0x18002bec0  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002bec7  lea     r8, pProxyInfo; pProxyInfo
0x18002bece  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002bed5  mov     rcx, [rsp+108h+pHandle]; Handle
0x18002beda  call    cs:__imp_NdrMesTypeEncode3
0x18002bee0  jmp     loc_18002BF6C
0x18002bee5  mov     ebx, eax
0x18002bee7  mov     edx, 2
0x18002beec  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002bef1  lea     rax, WPP_GLOBAL_Control
0x18002bef8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002beff  cmp     rcx, rax
0x18002bf02  jz      short loc_18002BF29
0x18002bf04  test    byte ptr [rcx+1Ch], 8
0x18002bf08  jz      short loc_18002BF29
0x18002bf0a  cmp     byte ptr [rcx+19h], 2
0x18002bf0e  jb      short loc_18002BF29
0x18002bf10  mov     edx, 51h ; 'Q'
0x18002bf15  mov     [rsp+108h+nTypeIndex], ebx
0x18002bf19  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002bf20  mov     rcx, [rcx+10h]
0x18002bf24  call    WPP_SF_sd
0x18002bf29  jmp     loc_18002C117
0x18002bf2e  mov     [rsp+108h+var_68], rbx
0x18002bf36  lea     rax, [rsp+108h+var_68]
0x18002bf3e  mov     [rsp+108h+pObject], rax; pObject
0x18002bf43  mov     [rsp+108h+nTypeIndex], 27h ; '''; nTypeIndex
0x18002bf4b  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002bf52  lea     r8, pProxyInfo; pProxyInfo
0x18002bf59  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002bf60  mov     rcx, [rsp+108h+pHandle]; Handle
0x18002bf65  call    cs:__imp_NdrMesTypeEncode3
0x18002bf6b  nop
0x18002bf6c  neg     edi
0x18002bf6e  sbb     ecx, ecx
0x18002bf70  and     ecx, 4
0x18002bf73  add     ecx, 900F0h; IoControlCode
0x18002bf79  mov     [rsp+108h+var_D8], 800h; unsigned int
0x18002bf81  mov     dword ptr [rsp+108h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002bf89  mov     qword ptr [rsp+108h+nTypeIndex], r12; lpCriticalSection
0x18002bf8e  lea     r9, [rsp+108h+var_B0]; struct _BUFFER_LIST_STRUCT **
0x18002bf93  mov     r8d, [rsp+108h+pEncodedSize]; InputBufferLength
0x18002bf9b  mov     rdx, [rsp+108h+pBuffer]; InputBuffer
0x18002bfa0  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002bfa5  test    eax, eax
0x18002bfa7  jz      short loc_18002BFB7
0x18002bfa9  mov     ecx, eax; int
0x18002bfab  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002bfb0  mov     ebx, eax
0x18002bfb2  jmp     loc_18002C117
0x18002bfb7  lea     rcx, [rsp+108h+pHandle]; void **
0x18002bfbc  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002bfc1  lea     r8, [rsp+108h+pHandle]; pHandle
0x18002bfc6  mov     rcx, [rsp+108h+var_B0]
0x18002bfcb  mov     edx, [rcx+1Ch]; BufferSize
0x18002bfce  mov     rcx, [rcx+10h]; Buffer
0x18002bfd2  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002bfd8  test    eax, eax
0x18002bfda  jnz     loc_18002BE25
0x18002bfe0  xorps   xmm0, xmm0
0x18002bfe3  movups  xmmword ptr [rsp+108h+var_A8], xmm0
0x18002bfe8  lea     rax, [rsp+108h+var_A8]
0x18002bfed  mov     [rsp+108h+pObject], rax; pObject
0x18002bff2  mov     edi, 29h ; ')'
0x18002bff7  mov     [rsp+108h+nTypeIndex], edi; nTypeIndex
0x18002bffb  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c002  lea     r8, pProxyInfo; pProxyInfo
0x18002c009  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c010  mov     rcx, [rsp+108h+pHandle]; Handle
0x18002c015  call    cs:__imp_NdrMesTypeDecode3
0x18002c01b  nop
0x18002c01c  mov     ebx, dword ptr [rsp+108h+var_A8]
0x18002c020  mov     [rsp+108h+var_C0], ebx
0x18002c024  test    ebx, ebx
0x18002c026  jnz     short loc_18002C050
0x18002c028  mov     dword ptr [rsp+108h+pObject], 1; unsigned int
0x18002c030  mov     qword ptr [rsp+108h+nTypeIndex], r15; unsigned int *
0x18002c035  mov     r9, rsi; unsigned __int8 *
0x18002c038  mov     r8d, dword ptr [rsp+108h+var_A8+4]; unsigned int
0x18002c03d  mov     rdx, [rsp+108h+var_A8+8]; unsigned __int8 *
0x18002c042  mov     rcx, r14; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18002c045  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x18002c04a  mov     ebx, eax
0x18002c04c  mov     [rsp+108h+var_C0], eax
0x18002c050  lea     rax, [rsp+108h+var_A8]
0x18002c055  mov     [rsp+108h+pObject], rax; pObject
0x18002c05a  mov     [rsp+108h+nTypeIndex], edi; nTypeIndex
0x18002c05e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c065  lea     r8, pProxyInfo; pProxyInfo
0x18002c06c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c073  mov     rcx, [rsp+108h+pHandle]; Handle
0x18002c078  call    cs:__imp_NdrMesTypeFree3
0x18002c07e  jmp     loc_18002C117
0x18002c083  mov     ebx, [rsp+108h+var_C0]
0x18002c087  jmp     loc_18002C117
0x18002c08c  mov     ebx, eax
0x18002c08e  mov     edx, 2
0x18002c093  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c098  lea     rax, WPP_GLOBAL_Control
0x18002c09f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0a6  cmp     rcx, rax
0x18002c0a9  jz      short loc_18002C0D0
0x18002c0ab  test    byte ptr [rcx+1Ch], 8
0x18002c0af  jz      short loc_18002C0D0
0x18002c0b1  cmp     byte ptr [rcx+19h], 2
0x18002c0b5  jb      short loc_18002C0D0
0x18002c0b7  mov     edx, 53h ; 'S'
0x18002c0bc  mov     [rsp+108h+nTypeIndex], ebx
0x18002c0c0  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c0c7  mov     rcx, [rcx+10h]
0x18002c0cb  call    WPP_SF_sd
0x18002c0d0  jmp     short loc_18002C117
0x18002c0d2  mov     ebx, eax
0x18002c0d4  mov     edx, 2
0x18002c0d9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c0de  lea     rax, WPP_GLOBAL_Control
0x18002c0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0ec  cmp     rcx, rax
0x18002c0ef  jz      short loc_18002C117
0x18002c0f1  test    byte ptr [rcx+1Ch], 8
0x18002c0f5  jz      short loc_18002C117
0x18002c0f7  cmp     byte ptr [rcx+19h], 2
0x18002c0fb  jb      short loc_18002C117
0x18002c0fd  mov     edx, 52h ; 'R'
0x18002c102  mov     [rsp+108h+nTypeIndex], ebx
0x18002c106  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c10d  mov     rcx, [rcx+10h]
0x18002c111  call    WPP_SF_sd
0x18002c116  nop
0x18002c117  lea     rcx, [rsp+108h+pHandle]; void **
0x18002c11c  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c121  mov     rcx, [rsp+108h+pBuffer]; void *
0x18002c126  call    MIDL_user_free
0x18002c12b  mov     rax, [rsp+108h+var_B0]
0x18002c130  test    rax, rax
0x18002c133  jz      short loc_18002C13C
0x18002c135  mov     dword ptr [rax+8], 0
0x18002c13c  mov     eax, ebx
0x18002c13e  jmp     short loc_18002C145
0x18002c140  mov     eax, 80100004h
0x18002c145  add     rsp, 0D8h
0x18002c14c  pop     r15
0x18002c14e  pop     r14
0x18002c150  pop     r12
0x18002c152  pop     rdi
0x18002c153  pop     rsi
0x18002c154  pop     rbx
0x18002c155  retn
```

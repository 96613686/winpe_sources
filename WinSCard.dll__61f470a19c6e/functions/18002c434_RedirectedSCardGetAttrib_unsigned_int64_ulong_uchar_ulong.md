# RedirectedSCardGetAttrib(unsigned __int64,ulong,uchar *,ulong *)

- ea: `0x18002c434`
- end: `0x18002c6fc`
- name: `?RedirectedSCardGetAttrib@@YAJ_KKPEAEPEAK@Z`
- size: `712`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180022f20`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`
- `0x18002c434`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002c5c2`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002c5c2`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c515`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c515`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c629`
- `RPCRT4!NdrMesTypeFree3` at `0x18002c629`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c4a1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c4a1`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002c580`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002c580`

## pseudocode

```c
__int64 __fastcall RedirectedSCardGetAttrib(__int64 a1, int a2, unsigned __int8 *a3, unsigned int *a4)
{
  unsigned int SCardError; // ebx
  int v10; // eax
  handle_t pHandle; // [rsp+48h] [rbp-80h] BYREF
  char *pBuffer; // [rsp+50h] [rbp-78h] BYREF
  struct _BUFFER_LIST_STRUCT *v13; // [rsp+58h] [rbp-70h] BYREF
  unsigned __int8 *v14[2]; // [rsp+60h] [rbp-68h] BYREF
  __int128 pObject; // [rsp+70h] [rbp-58h] BYREF
  __int128 v16; // [rsp+80h] [rbp-48h]
  __int128 v17; // [rsp+90h] [rbp-38h]
  unsigned int pEncodedSize; // [rsp+D0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v13 = 0;
  pObject = 0;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)v14 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    v16 = *(_OWORD *)(a1 + 24);
    LODWORD(v17) = a2;
    DWORD1(v17) = a3 == 0;
    DWORD2(v17) = *a4;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x24u, &pObject);
    v10 = _SendSCardIOCTL(590040, pBuffer, pEncodedSize, &v13, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v10 )
    {
      SCardError = _MakeSCardError(v10);
      goto LABEL_11;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v13 + 2), *((_DWORD *)v13 + 7), &pHandle) )
    {
      *(_OWORD *)v14 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x25u, v14);
      SCardError = (unsigned int)v14[0];
      if ( !LODWORD(v14[0]) )
        SCardError = _CopyReturnToCallerBuffer(
                       *(struct _REDIR_LOCAL_SCARDCONTEXT **)a1,
                       v14[1],
                       HIDWORD(v14[0]),
                       a3,
                       a4,
                       1u);
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x25u, v14);
      goto LABEL_11;
    }
  }
  SCardError = -2146435041;
LABEL_11:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v13 )
    *((_DWORD *)v13 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002c434  mov     rax, rsp
0x18002c437  push    rbx
0x18002c438  push    rsi
0x18002c439  push    rdi
0x18002c43a  push    r14
0x18002c43c  sub     rsp, 0A8h
0x18002c443  mov     rsi, r9
0x18002c446  mov     r14, r8
0x18002c449  mov     ebx, edx
0x18002c44b  mov     rdi, rcx
0x18002c44e  mov     qword ptr [rax-78h], 0
0x18002c456  mov     dword ptr [rax+8], 0
0x18002c45d  mov     qword ptr [rax-80h], 0
0x18002c465  mov     qword ptr [rax-70h], 0
0x18002c46d  xorps   xmm0, xmm0
0x18002c470  movups  xmmword ptr [rax-58h], xmm0
0x18002c474  movups  xmmword ptr [rax-48h], xmm0
0x18002c478  movups  xmmword ptr [rax-38h], xmm0
0x18002c47c  movups  xmmword ptr [rax-68h], xmm0
0x18002c480  test    rcx, rcx
0x18002c483  jnz     short loc_18002C48F
0x18002c485  mov     eax, 80100004h
0x18002c48a  jmp     loc_18002C6EF
0x18002c48f  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002c494  lea     rdx, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x18002c49c  lea     rcx, [rsp+0C8h+pBuffer]; pBuffer
0x18002c4a1  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002c4a7  test    eax, eax
0x18002c4a9  jz      short loc_18002C4B5
0x18002c4ab  mov     ebx, 8010001Fh
0x18002c4b0  jmp     loc_18002C6C8
0x18002c4b5  movups  xmm0, xmmword ptr [rdi+8]
0x18002c4b9  movups  [rsp+0C8h+var_58], xmm0
0x18002c4be  movups  xmm1, xmmword ptr [rdi+18h]
0x18002c4c2  movups  [rsp+0C8h+var_48], xmm1
0x18002c4ca  mov     [rsp+0C8h+var_38], ebx
0x18002c4d1  xor     eax, eax
0x18002c4d3  test    r14, r14
0x18002c4d6  setz    al
0x18002c4d9  mov     [rsp+0C8h+var_34], eax
0x18002c4e0  mov     eax, [rsi]
0x18002c4e2  mov     [rsp+0C8h+var_30], eax
0x18002c4e9  lea     rax, [rsp+0C8h+var_58]
0x18002c4ee  mov     [rsp+0C8h+pObject], rax; pObject
0x18002c4f3  mov     [rsp+0C8h+nTypeIndex], 24h ; '$'; nTypeIndex
0x18002c4fb  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c502  lea     r8, pProxyInfo; pProxyInfo
0x18002c509  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c510  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002c515  call    cs:__imp_NdrMesTypeEncode3
0x18002c51b  nop
0x18002c51c  mov     rax, [rdi]
0x18002c51f  mov     [rsp+0C8h+var_98], 800h; unsigned int
0x18002c527  mov     dword ptr [rsp+0C8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002c52f  mov     rax, [rax]
0x18002c532  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; lpCriticalSection
0x18002c537  lea     r9, [rsp+0C8h+var_70]; struct _BUFFER_LIST_STRUCT **
0x18002c53c  mov     r8d, [rsp+0C8h+pEncodedSize]; InputBufferLength
0x18002c544  mov     rdx, [rsp+0C8h+pBuffer]; InputBuffer
0x18002c549  mov     ecx, 900D8h; IoControlCode
0x18002c54e  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002c553  test    eax, eax
0x18002c555  jz      short loc_18002C565
0x18002c557  mov     ecx, eax; int
0x18002c559  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002c55e  mov     ebx, eax
0x18002c560  jmp     loc_18002C6C8
0x18002c565  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002c56a  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c56f  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002c574  mov     rcx, [rsp+0C8h+var_70]
0x18002c579  mov     edx, [rcx+1Ch]; BufferSize
0x18002c57c  mov     rcx, [rcx+10h]; Buffer
0x18002c580  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002c586  test    eax, eax
0x18002c588  jnz     loc_18002C4AB
0x18002c58e  xorps   xmm0, xmm0
0x18002c591  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x18002c596  lea     rax, [rsp+0C8h+var_68]
0x18002c59b  mov     [rsp+0C8h+pObject], rax; pObject
0x18002c5a0  mov     [rsp+0C8h+nTypeIndex], 25h ; '%'; nTypeIndex
0x18002c5a8  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c5af  lea     r8, pProxyInfo; pProxyInfo
0x18002c5b6  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c5bd  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002c5c2  call    cs:__imp_NdrMesTypeDecode3
0x18002c5c8  nop
0x18002c5c9  mov     ebx, dword ptr [rsp+0C8h+var_68]
0x18002c5cd  mov     [rsp+0C8h+var_88], ebx
0x18002c5d1  test    ebx, ebx
0x18002c5d3  jnz     short loc_18002C5FD
0x18002c5d5  mov     dword ptr [rsp+0C8h+pObject], 1; unsigned int
0x18002c5dd  mov     qword ptr [rsp+0C8h+nTypeIndex], rsi; unsigned int *
0x18002c5e2  mov     r9, r14; unsigned __int8 *
0x18002c5e5  mov     r8d, dword ptr [rsp+0C8h+var_68+4]; unsigned int
0x18002c5ea  mov     rdx, [rsp+0C8h+var_68+8]; unsigned __int8 *
0x18002c5ef  mov     rcx, [rdi]; struct _REDIR_LOCAL_SCARDCONTEXT *
0x18002c5f2  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x18002c5f7  mov     ebx, eax
0x18002c5f9  mov     [rsp+0C8h+var_88], eax
0x18002c5fd  lea     rax, [rsp+0C8h+var_68]
0x18002c602  mov     [rsp+0C8h+pObject], rax; pObject
0x18002c607  mov     [rsp+0C8h+nTypeIndex], 25h ; '%'; nTypeIndex
0x18002c60f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c616  lea     r8, pProxyInfo; pProxyInfo
0x18002c61d  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c624  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002c629  call    cs:__imp_NdrMesTypeFree3
0x18002c62f  jmp     loc_18002C6C8
0x18002c634  mov     ebx, [rsp+0C8h+var_88]
0x18002c638  jmp     loc_18002C6C8
0x18002c63d  mov     ebx, eax
0x18002c63f  mov     edx, 2
0x18002c644  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c649  lea     rax, WPP_GLOBAL_Control
0x18002c650  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c657  cmp     rcx, rax
0x18002c65a  jz      short loc_18002C681
0x18002c65c  test    byte ptr [rcx+1Ch], 8
0x18002c660  jz      short loc_18002C681
0x18002c662  cmp     byte ptr [rcx+19h], 2
0x18002c666  jb      short loc_18002C681
0x18002c668  mov     edx, 4Fh ; 'O'
0x18002c66d  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002c671  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c678  mov     rcx, [rcx+10h]
0x18002c67c  call    WPP_SF_sd
0x18002c681  jmp     short loc_18002C6C8
0x18002c683  mov     ebx, eax
0x18002c685  mov     edx, 2
0x18002c68a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c68f  lea     rax, WPP_GLOBAL_Control
0x18002c696  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c69d  cmp     rcx, rax
0x18002c6a0  jz      short loc_18002C6C8
0x18002c6a2  test    byte ptr [rcx+1Ch], 8
0x18002c6a6  jz      short loc_18002C6C8
0x18002c6a8  cmp     byte ptr [rcx+19h], 2
0x18002c6ac  jb      short loc_18002C6C8
0x18002c6ae  mov     edx, 4Eh ; 'N'
0x18002c6b3  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002c6b7  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c6be  mov     rcx, [rcx+10h]
0x18002c6c2  call    WPP_SF_sd
0x18002c6c7  nop
0x18002c6c8  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002c6cd  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c6d2  mov     rcx, [rsp+0C8h+pBuffer]; void *
0x18002c6d7  call    MIDL_user_free
0x18002c6dc  mov     rax, [rsp+0C8h+var_70]
0x18002c6e1  test    rax, rax
0x18002c6e4  jz      short loc_18002C6ED
0x18002c6e6  mov     dword ptr [rax+8], 0
0x18002c6ed  mov     eax, ebx
0x18002c6ef  add     rsp, 0A8h
0x18002c6f6  pop     r14
0x18002c6f8  pop     rdi
0x18002c6f9  pop     rsi
0x18002c6fa  pop     rbx
0x18002c6fb  retn
```

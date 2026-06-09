# RedirectedSCardLocateCardsByATRW(unsigned __int64,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEW *,ulong)

- ea: `0x18002d290`
- end: `0x18002d5b4`
- name: `?RedirectedSCardLocateCardsByATRW@@YAJ_KPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEW@@K@Z`
- size: `804`
- prototype: `int(unsigned __int64, struct _SCARD_ATRMASK *, unsigned int, struct SCARD_READERSTATEW *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180028160`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800127cc`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002d290`
- `0x18002e13c`
- `0x18002e29c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002d470`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002d470`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d3c9`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d3c9`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d4c1`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d4c1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d317`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002d317`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d431`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d431`

## pseudocode

```c
__int64 __fastcall RedirectedSCardLocateCardsByATRW(
        __int64 a1,
        struct _SCARD_ATRMASK *a2,
        unsigned int a3,
        struct SCARD_READERSTATEW *a4,
        unsigned int a5)
{
  unsigned int SCardError; // ebx
  unsigned int v11; // edi
  int v12; // eax
  handle_t pHandle; // [rsp+40h] [rbp-88h] BYREF
  int v14; // [rsp+48h] [rbp-80h]
  char *pBuffer; // [rsp+50h] [rbp-78h] BYREF
  struct _LocateCards_ATRMask *v16; // [rsp+58h] [rbp-70h] BYREF
  struct _ReaderStateW *v17; // [rsp+60h] [rbp-68h] BYREF
  struct _BUFFER_LIST_STRUCT *v18; // [rsp+68h] [rbp-60h] BYREF
  struct _ReaderState_Return *v19[2]; // [rsp+70h] [rbp-58h] BYREF
  __int128 pObject; // [rsp+80h] [rbp-48h] BYREF
  __int128 v21; // [rsp+90h] [rbp-38h]
  __int128 v22; // [rsp+A0h] [rbp-28h]
  unsigned int pEncodedSize; // [rsp+D0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  pObject = 0;
  v21 = 0;
  v22 = 0;
  v16 = 0;
  *(_OWORD *)v19 = 0;
  v17 = 0;
  v18 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 8);
    LODWORD(v21) = a3;
    v11 = a5;
    LODWORD(v22) = a5;
    if ( (unsigned int)_AllocAndCopyATRMasksForCall(a3, &v16, a2)
      || (*((_QWORD *)&v21 + 1) = v16, (unsigned int)_AllocAndCopyReaderStateWStructsForCall(v11, &v17, a4)) )
    {
      SCardError = -2146435066;
      goto LABEL_15;
    }
    *((_QWORD *)&v22 + 1) = v17;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xFu, &pObject);
    v12 = _SendSCardIOCTL(590060, pBuffer, pEncodedSize, &v18, *(LPCRITICAL_SECTION *)a1, 0xFFFFFFFF, 0x800u);
    if ( v12 )
    {
      SCardError = _MakeSCardError(v12);
      goto LABEL_15;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v18 + 2), *((_DWORD *)v18 + 7), &pHandle) )
    {
      *(_OWORD *)v19 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v19);
      SCardError = (unsigned int)v19[0];
      v14 = (int)v19[0];
      if ( LODWORD(v19[0]) )
      {
LABEL_14:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x10u, v19);
        goto LABEL_15;
      }
      if ( v11 == HIDWORD(v19[0]) )
      {
        _CopyReaderStateWStructsForReturn(v11, a4, v19[1]);
        goto LABEL_14;
      }
    }
  }
  SCardError = -2146435041;
LABEL_15:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  MIDL_user_free(v16);
  MIDL_user_free(v17);
  if ( v18 )
    *((_DWORD *)v18 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18002d290  mov     rax, rsp
0x18002d293  mov     [rax+10h], rbx
0x18002d297  mov     [rax+18h], rsi
0x18002d29b  push    rdi
0x18002d29c  push    r14
0x18002d29e  push    r15
0x18002d2a0  sub     rsp, 0B0h
0x18002d2a7  mov     r15, r9
0x18002d2aa  mov     ebx, r8d
0x18002d2ad  mov     r14, rdx
0x18002d2b0  mov     rsi, rcx
0x18002d2b3  mov     qword ptr [rax-78h], 0
0x18002d2bb  mov     dword ptr [rax+8], 0
0x18002d2c2  mov     [rsp+0C8h+pHandle], 0
0x18002d2cb  xorps   xmm0, xmm0
0x18002d2ce  movups  xmmword ptr [rax-48h], xmm0
0x18002d2d2  movups  xmmword ptr [rax-38h], xmm0
0x18002d2d6  movups  xmmword ptr [rax-28h], xmm0
0x18002d2da  mov     qword ptr [rax-70h], 0
0x18002d2e2  movups  xmmword ptr [rax-58h], xmm0
0x18002d2e6  mov     qword ptr [rax-68h], 0
0x18002d2ee  mov     qword ptr [rax-60h], 0
0x18002d2f6  test    rcx, rcx
0x18002d2f9  jnz     short loc_18002D305
0x18002d2fb  mov     eax, 80100004h
0x18002d300  jmp     loc_18002D59B
0x18002d305  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002d30a  lea     rdx, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x18002d312  lea     rcx, [rsp+0C8h+pBuffer]; pBuffer
0x18002d317  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002d31d  test    eax, eax
0x18002d31f  jz      short loc_18002D32B
0x18002d321  mov     ebx, 8010001Fh
0x18002d326  jmp     loc_18002D560
0x18002d32b  movups  xmm0, xmmword ptr [rsi+8]
0x18002d32f  movdqu  [rsp+0C8h+var_48], xmm0
0x18002d338  mov     [rsp+0C8h+var_38], ebx
0x18002d33f  mov     edi, [rsp+0C8h+arg_20]
0x18002d346  mov     [rsp+0C8h+var_28], edi
0x18002d34d  mov     r8, r14; struct _SCARD_ATRMASK *
0x18002d350  lea     rdx, [rsp+0C8h+var_70]; struct _LocateCards_ATRMask **
0x18002d355  mov     ecx, ebx; unsigned int
0x18002d357  call    ?_AllocAndCopyATRMasksForCall@@YAJKPEAPEAU_LocateCards_ATRMask@@PEAU_SCARD_ATRMASK@@@Z; _AllocAndCopyATRMasksForCall(ulong,_LocateCards_ATRMask * *,_SCARD_ATRMASK *)
0x18002d35c  test    eax, eax
0x18002d35e  jz      short loc_18002D36A
0x18002d360  mov     ebx, 80100006h
0x18002d365  jmp     loc_18002D560
0x18002d36a  mov     rax, [rsp+0C8h+var_70]
0x18002d36f  mov     [rsp+0C8h+var_30], rax
0x18002d377  mov     r8, r15; struct SCARD_READERSTATEW *
0x18002d37a  lea     rdx, [rsp+0C8h+var_68]; struct _ReaderStateW **
0x18002d37f  mov     ecx, edi; unsigned int
0x18002d381  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x18002d386  test    eax, eax
0x18002d388  jnz     short loc_18002D360
0x18002d38a  mov     rax, [rsp+0C8h+var_68]
0x18002d38f  mov     [rsp+0C8h+var_20], rax
0x18002d397  lea     rax, [rsp+0C8h+var_48]
0x18002d39f  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d3a4  mov     [rsp+0C8h+nTypeIndex], 0Fh; nTypeIndex
0x18002d3ac  lea     r14, ArrTypeOffset
0x18002d3b3  mov     r9, r14; ArrTypeOffset
0x18002d3b6  lea     r8, pProxyInfo; pProxyInfo
0x18002d3bd  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d3c4  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d3c9  call    cs:__imp_NdrMesTypeEncode3
0x18002d3cf  nop
0x18002d3d0  mov     [rsp+0C8h+var_98], 800h; unsigned int
0x18002d3d8  mov     dword ptr [rsp+0C8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002d3e0  mov     rax, [rsi]
0x18002d3e3  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; lpCriticalSection
0x18002d3e8  lea     r9, [rsp+0C8h+var_60]; struct _BUFFER_LIST_STRUCT **
0x18002d3ed  mov     r8d, [rsp+0C8h+pEncodedSize]; InputBufferLength
0x18002d3f5  mov     rdx, [rsp+0C8h+pBuffer]; InputBuffer
0x18002d3fa  mov     ecx, 900ECh; IoControlCode
0x18002d3ff  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002d404  test    eax, eax
0x18002d406  jz      short loc_18002D416
0x18002d408  mov     ecx, eax; int
0x18002d40a  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002d40f  mov     ebx, eax
0x18002d411  jmp     loc_18002D560
0x18002d416  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002d41b  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d420  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002d425  mov     rcx, [rsp+0C8h+var_60]
0x18002d42a  mov     edx, [rcx+1Ch]; BufferSize
0x18002d42d  mov     rcx, [rcx+10h]; Buffer
0x18002d431  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002d437  test    eax, eax
0x18002d439  jnz     loc_18002D321
0x18002d43f  xorps   xmm0, xmm0
0x18002d442  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x18002d447  lea     rax, [rsp+0C8h+var_58]
0x18002d44c  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d451  mov     esi, 10h
0x18002d456  mov     [rsp+0C8h+nTypeIndex], esi; nTypeIndex
0x18002d45a  mov     r9, r14; ArrTypeOffset
0x18002d45d  lea     r8, pProxyInfo; pProxyInfo
0x18002d464  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d46b  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d470  call    cs:__imp_NdrMesTypeDecode3
0x18002d476  nop
0x18002d477  mov     ebx, dword ptr [rsp+0C8h+var_58]
0x18002d47b  mov     [rsp+0C8h+var_80], ebx
0x18002d47f  test    ebx, ebx
0x18002d481  jnz     short loc_18002D49D
0x18002d483  cmp     edi, dword ptr [rsp+0C8h+var_58+4]
0x18002d487  jnz     loc_18002D321
0x18002d48d  mov     r8, [rsp+0C8h+var_58+8]; struct _ReaderState_Return *
0x18002d492  mov     rdx, r15; struct SCARD_READERSTATEW *
0x18002d495  mov     ecx, edi; unsigned int
0x18002d497  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x18002d49c  nop
0x18002d49d  lea     rax, [rsp+0C8h+var_58]
0x18002d4a2  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d4a7  mov     [rsp+0C8h+nTypeIndex], esi; nTypeIndex
0x18002d4ab  mov     r9, r14; ArrTypeOffset
0x18002d4ae  lea     r8, pProxyInfo; pProxyInfo
0x18002d4b5  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d4bc  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d4c1  call    cs:__imp_NdrMesTypeFree3
0x18002d4c7  jmp     loc_18002D560
0x18002d4cc  mov     ebx, [rsp+0C8h+var_80]
0x18002d4d0  jmp     loc_18002D560
0x18002d4d5  mov     ebx, eax
0x18002d4d7  mov     edx, 2
0x18002d4dc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d4e1  lea     rax, WPP_GLOBAL_Control
0x18002d4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4ef  cmp     rcx, rax
0x18002d4f2  jz      short loc_18002D519
0x18002d4f4  test    byte ptr [rcx+1Ch], 8
0x18002d4f8  jz      short loc_18002D519
0x18002d4fa  cmp     byte ptr [rcx+19h], 2
0x18002d4fe  jb      short loc_18002D519
0x18002d500  mov     edx, 37h ; '7'
0x18002d505  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002d509  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d510  mov     rcx, [rcx+10h]
0x18002d514  call    WPP_SF_sd
0x18002d519  jmp     short loc_18002D560
0x18002d51b  mov     ebx, eax
0x18002d51d  mov     edx, 2
0x18002d522  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d527  lea     rax, WPP_GLOBAL_Control
0x18002d52e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d535  cmp     rcx, rax
0x18002d538  jz      short loc_18002D560
0x18002d53a  test    byte ptr [rcx+1Ch], 8
0x18002d53e  jz      short loc_18002D560
0x18002d540  cmp     byte ptr [rcx+19h], 2
0x18002d544  jb      short loc_18002D560
0x18002d546  mov     edx, 36h ; '6'
0x18002d54b  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002d54f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d556  mov     rcx, [rcx+10h]
0x18002d55a  call    WPP_SF_sd
0x18002d55f  nop
0x18002d560  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002d565  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d56a  mov     rcx, [rsp+0C8h+pBuffer]; void *
0x18002d56f  call    MIDL_user_free
0x18002d574  mov     rcx, [rsp+0C8h+var_70]; void *
0x18002d579  call    MIDL_user_free
0x18002d57e  mov     rcx, [rsp+0C8h+var_68]; void *
0x18002d583  call    MIDL_user_free
0x18002d588  mov     rax, [rsp+0C8h+var_60]
0x18002d58d  test    rax, rax
0x18002d590  jz      short loc_18002D599
0x18002d592  mov     dword ptr [rax+8], 0
0x18002d599  mov     eax, ebx
0x18002d59b  lea     r11, [rsp+0C8h+var_18]
0x18002d5a3  mov     rbx, [r11+28h]
0x18002d5a7  mov     rsi, [r11+30h]
0x18002d5ab  mov     rsp, r11
0x18002d5ae  pop     r15
0x18002d5b0  pop     r14
0x18002d5b2  pop     rdi
0x18002d5b3  retn
```

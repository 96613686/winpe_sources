# RedirectedSCardLocateCardsByATRA(unsigned __int64,_SCARD_ATRMASK *,ulong,SCARD_READERSTATEA *,ulong)

- ea: `0x18002cf64`
- end: `0x18002d288`
- name: `?RedirectedSCardLocateCardsByATRA@@YAJ_KPEAU_SCARD_ATRMASK@@KPEAUSCARD_READERSTATEA@@K@Z`
- size: `804`
- prototype: `int(unsigned __int64, struct _SCARD_ATRMASK *, unsigned int, struct SCARD_READERSTATEA *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180026bb0`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800127cc`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002cf64`
- `0x18002e13c`
- `0x18002e29c`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18002d144`
- `RPCRT4!NdrMesTypeDecode3` at `0x18002d144`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d09d`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002d09d`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d195`
- `RPCRT4!NdrMesTypeFree3` at `0x18002d195`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002cfeb`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002cfeb`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d105`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18002d105`

## pseudocode

```c
__int64 __fastcall RedirectedSCardLocateCardsByATRA(
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
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xEu, &pObject);
    v12 = _SendSCardIOCTL(590056, pBuffer, pEncodedSize, &v18, *(LPCRITICAL_SECTION *)a1, 0xFFFFFFFF, 0x800u);
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
0x18002cf64  mov     rax, rsp
0x18002cf67  mov     [rax+10h], rbx
0x18002cf6b  mov     [rax+18h], rsi
0x18002cf6f  push    rdi
0x18002cf70  push    r14
0x18002cf72  push    r15
0x18002cf74  sub     rsp, 0B0h
0x18002cf7b  mov     r15, r9
0x18002cf7e  mov     ebx, r8d
0x18002cf81  mov     r14, rdx
0x18002cf84  mov     rsi, rcx
0x18002cf87  mov     qword ptr [rax-78h], 0
0x18002cf8f  mov     dword ptr [rax+8], 0
0x18002cf96  mov     [rsp+0C8h+pHandle], 0
0x18002cf9f  xorps   xmm0, xmm0
0x18002cfa2  movups  xmmword ptr [rax-48h], xmm0
0x18002cfa6  movups  xmmword ptr [rax-38h], xmm0
0x18002cfaa  movups  xmmword ptr [rax-28h], xmm0
0x18002cfae  mov     qword ptr [rax-70h], 0
0x18002cfb6  movups  xmmword ptr [rax-58h], xmm0
0x18002cfba  mov     qword ptr [rax-68h], 0
0x18002cfc2  mov     qword ptr [rax-60h], 0
0x18002cfca  test    rcx, rcx
0x18002cfcd  jnz     short loc_18002CFD9
0x18002cfcf  mov     eax, 80100004h
0x18002cfd4  jmp     loc_18002D26F
0x18002cfd9  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002cfde  lea     rdx, [rsp+0C8h+pEncodedSize]; pEncodedSize
0x18002cfe6  lea     rcx, [rsp+0C8h+pBuffer]; pBuffer
0x18002cfeb  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002cff1  test    eax, eax
0x18002cff3  jz      short loc_18002CFFF
0x18002cff5  mov     ebx, 8010001Fh
0x18002cffa  jmp     loc_18002D234
0x18002cfff  movups  xmm0, xmmword ptr [rsi+8]
0x18002d003  movdqu  [rsp+0C8h+var_48], xmm0
0x18002d00c  mov     [rsp+0C8h+var_38], ebx
0x18002d013  mov     edi, [rsp+0C8h+arg_20]
0x18002d01a  mov     [rsp+0C8h+var_28], edi
0x18002d021  mov     r8, r14; struct _SCARD_ATRMASK *
0x18002d024  lea     rdx, [rsp+0C8h+var_70]; struct _LocateCards_ATRMask **
0x18002d029  mov     ecx, ebx; unsigned int
0x18002d02b  call    ?_AllocAndCopyATRMasksForCall@@YAJKPEAPEAU_LocateCards_ATRMask@@PEAU_SCARD_ATRMASK@@@Z; _AllocAndCopyATRMasksForCall(ulong,_LocateCards_ATRMask * *,_SCARD_ATRMASK *)
0x18002d030  test    eax, eax
0x18002d032  jz      short loc_18002D03E
0x18002d034  mov     ebx, 80100006h
0x18002d039  jmp     loc_18002D234
0x18002d03e  mov     rax, [rsp+0C8h+var_70]
0x18002d043  mov     [rsp+0C8h+var_30], rax
0x18002d04b  mov     r8, r15; struct SCARD_READERSTATEW *
0x18002d04e  lea     rdx, [rsp+0C8h+var_68]; struct _ReaderStateW **
0x18002d053  mov     ecx, edi; unsigned int
0x18002d055  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x18002d05a  test    eax, eax
0x18002d05c  jnz     short loc_18002D034
0x18002d05e  mov     rax, [rsp+0C8h+var_68]
0x18002d063  mov     [rsp+0C8h+var_20], rax
0x18002d06b  lea     rax, [rsp+0C8h+var_48]
0x18002d073  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d078  mov     [rsp+0C8h+nTypeIndex], 0Eh; nTypeIndex
0x18002d080  lea     r14, ArrTypeOffset
0x18002d087  mov     r9, r14; ArrTypeOffset
0x18002d08a  lea     r8, pProxyInfo; pProxyInfo
0x18002d091  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d098  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d09d  call    cs:__imp_NdrMesTypeEncode3
0x18002d0a3  nop
0x18002d0a4  mov     [rsp+0C8h+var_98], 800h; unsigned int
0x18002d0ac  mov     dword ptr [rsp+0C8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002d0b4  mov     rax, [rsi]
0x18002d0b7  mov     qword ptr [rsp+0C8h+nTypeIndex], rax; lpCriticalSection
0x18002d0bc  lea     r9, [rsp+0C8h+var_60]; struct _BUFFER_LIST_STRUCT **
0x18002d0c1  mov     r8d, [rsp+0C8h+pEncodedSize]; InputBufferLength
0x18002d0c9  mov     rdx, [rsp+0C8h+pBuffer]; InputBuffer
0x18002d0ce  mov     ecx, 900E8h; IoControlCode
0x18002d0d3  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002d0d8  test    eax, eax
0x18002d0da  jz      short loc_18002D0EA
0x18002d0dc  mov     ecx, eax; int
0x18002d0de  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002d0e3  mov     ebx, eax
0x18002d0e5  jmp     loc_18002D234
0x18002d0ea  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002d0ef  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d0f4  lea     r8, [rsp+0C8h+pHandle]; pHandle
0x18002d0f9  mov     rcx, [rsp+0C8h+var_60]
0x18002d0fe  mov     edx, [rcx+1Ch]; BufferSize
0x18002d101  mov     rcx, [rcx+10h]; Buffer
0x18002d105  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002d10b  test    eax, eax
0x18002d10d  jnz     loc_18002CFF5
0x18002d113  xorps   xmm0, xmm0
0x18002d116  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x18002d11b  lea     rax, [rsp+0C8h+var_58]
0x18002d120  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d125  mov     esi, 10h
0x18002d12a  mov     [rsp+0C8h+nTypeIndex], esi; nTypeIndex
0x18002d12e  mov     r9, r14; ArrTypeOffset
0x18002d131  lea     r8, pProxyInfo; pProxyInfo
0x18002d138  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d13f  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d144  call    cs:__imp_NdrMesTypeDecode3
0x18002d14a  nop
0x18002d14b  mov     ebx, dword ptr [rsp+0C8h+var_58]
0x18002d14f  mov     [rsp+0C8h+var_80], ebx
0x18002d153  test    ebx, ebx
0x18002d155  jnz     short loc_18002D171
0x18002d157  cmp     edi, dword ptr [rsp+0C8h+var_58+4]
0x18002d15b  jnz     loc_18002CFF5
0x18002d161  mov     r8, [rsp+0C8h+var_58+8]; struct _ReaderState_Return *
0x18002d166  mov     rdx, r15; struct SCARD_READERSTATEW *
0x18002d169  mov     ecx, edi; unsigned int
0x18002d16b  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x18002d170  nop
0x18002d171  lea     rax, [rsp+0C8h+var_58]
0x18002d176  mov     [rsp+0C8h+pObject], rax; pObject
0x18002d17b  mov     [rsp+0C8h+nTypeIndex], esi; nTypeIndex
0x18002d17f  mov     r9, r14; ArrTypeOffset
0x18002d182  lea     r8, pProxyInfo; pProxyInfo
0x18002d189  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002d190  mov     rcx, [rsp+0C8h+pHandle]; Handle
0x18002d195  call    cs:__imp_NdrMesTypeFree3
0x18002d19b  jmp     loc_18002D234
0x18002d1a0  mov     ebx, [rsp+0C8h+var_80]
0x18002d1a4  jmp     loc_18002D234
0x18002d1a9  mov     ebx, eax
0x18002d1ab  mov     edx, 2
0x18002d1b0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d1b5  lea     rax, WPP_GLOBAL_Control
0x18002d1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1c3  cmp     rcx, rax
0x18002d1c6  jz      short loc_18002D1ED
0x18002d1c8  test    byte ptr [rcx+1Ch], 8
0x18002d1cc  jz      short loc_18002D1ED
0x18002d1ce  cmp     byte ptr [rcx+19h], 2
0x18002d1d2  jb      short loc_18002D1ED
0x18002d1d4  mov     edx, 35h ; '5'
0x18002d1d9  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002d1dd  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d1e4  mov     rcx, [rcx+10h]
0x18002d1e8  call    WPP_SF_sd
0x18002d1ed  jmp     short loc_18002D234
0x18002d1ef  mov     ebx, eax
0x18002d1f1  mov     edx, 2
0x18002d1f6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d1fb  lea     rax, WPP_GLOBAL_Control
0x18002d202  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d209  cmp     rcx, rax
0x18002d20c  jz      short loc_18002D234
0x18002d20e  test    byte ptr [rcx+1Ch], 8
0x18002d212  jz      short loc_18002D234
0x18002d214  cmp     byte ptr [rcx+19h], 2
0x18002d218  jb      short loc_18002D234
0x18002d21a  mov     edx, 34h ; '4'
0x18002d21f  mov     [rsp+0C8h+nTypeIndex], ebx
0x18002d223  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002d22a  mov     rcx, [rcx+10h]
0x18002d22e  call    WPP_SF_sd
0x18002d233  nop
0x18002d234  lea     rcx, [rsp+0C8h+pHandle]; void **
0x18002d239  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002d23e  mov     rcx, [rsp+0C8h+pBuffer]; void *
0x18002d243  call    MIDL_user_free
0x18002d248  mov     rcx, [rsp+0C8h+var_70]; void *
0x18002d24d  call    MIDL_user_free
0x18002d252  mov     rcx, [rsp+0C8h+var_68]; void *
0x18002d257  call    MIDL_user_free
0x18002d25c  mov     rax, [rsp+0C8h+var_60]
0x18002d261  test    rax, rax
0x18002d264  jz      short loc_18002D26D
0x18002d266  mov     dword ptr [rax+8], 0
0x18002d26d  mov     eax, ebx
0x18002d26f  lea     r11, [rsp+0C8h+var_18]
0x18002d277  mov     rbx, [r11+28h]
0x18002d27b  mov     rsi, [r11+30h]
0x18002d27f  mov     rsp, r11
0x18002d282  pop     r15
0x18002d284  pop     r14
0x18002d286  pop     rdi
0x18002d287  retn
```

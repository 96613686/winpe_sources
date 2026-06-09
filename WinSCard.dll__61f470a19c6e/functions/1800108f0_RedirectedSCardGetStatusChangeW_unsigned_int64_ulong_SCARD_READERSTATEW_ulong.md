# RedirectedSCardGetStatusChangeW(unsigned __int64,ulong,SCARD_READERSTATEW *,ulong)

- ea: `0x1800108f0`
- end: `0x180010c57`
- name: `?RedirectedSCardGetStatusChangeW@@YAJ_KKPEAUSCARD_READERSTATEW@@K@Z`
- size: `871`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, struct SCARD_READERSTATEW *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005de0`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800108f0`
- `0x1800127cc`
- `0x180016d20`
- `0x18001991c`
- `0x180019a14`
- `0x18002e29c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010b28`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010b28`
- `RPCRT4!NdrMesTypeDecode3` at `0x180010aa5`
- `RPCRT4!NdrMesTypeDecode3` at `0x180010aa5`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800109ee`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800109ee`
- `RPCRT4!NdrMesTypeFree3` at `0x180010b5f`
- `RPCRT4!NdrMesTypeFree3` at `0x180010b5f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001096c`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001096c`
- `RPCRT4!MesHandleFree` at `0x180010a42`
- `RPCRT4!MesHandleFree` at `0x180010c08`
- `RPCRT4!MesHandleFree` at `0x180010a42`
- `RPCRT4!MesHandleFree` at `0x180010c08`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180010a62`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180010a62`

## pseudocode

```c
__int64 __fastcall RedirectedSCardGetStatusChangeW(
        __int64 *a1,
        unsigned int a2,
        struct SCARD_READERSTATEW *a3,
        unsigned int a4)
{
  __int64 v9; // r14
  unsigned int SCardError; // ebx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r9d
  handle_t pHandle; // [rsp+48h] [rbp-70h] BYREF
  char *pBuffer; // [rsp+50h] [rbp-68h] BYREF
  struct _ReaderStateW *v16; // [rsp+58h] [rbp-60h] BYREF
  struct _BUFFER_LIST_STRUCT *v17; // [rsp+60h] [rbp-58h] BYREF
  struct _ReaderState_Return *v18[2]; // [rsp+68h] [rbp-50h] BYREF
  __int128 pObject; // [rsp+78h] [rbp-40h] BYREF
  __int128 v20; // [rsp+88h] [rbp-30h]
  unsigned int pEncodedSize; // [rsp+C0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  pObject = 0;
  v20 = 0;
  *(_OWORD *)v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( !a1 )
    return 2148532228LL;
  v9 = *a1;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)(a1 + 1);
    *(_QWORD *)&v20 = __PAIR64__(a4, a2);
    if ( (unsigned int)_AllocAndCopyReaderStateWStructsForCall(a4, &v16, a3) )
    {
      SCardError = -2146435066;
      goto LABEL_22;
    }
    *((_QWORD *)&v20 + 1) = v16;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x12u, &pObject);
    v11 = _SendSCardIOCTL(589988, pBuffer, pEncodedSize, &v17, (LPCRITICAL_SECTION)v9, 0xFFFFFFFF, 0x800u);
    if ( v11 )
    {
      SCardError = _MakeSCardError(v11);
      goto LABEL_22;
    }
    if ( pHandle )
    {
      MesHandleFree(pHandle);
      pHandle = 0;
    }
    if ( !MesDecodeBufferHandleCreate(*((char **)v17 + 2), *((_DWORD *)v17 + 7), &pHandle) )
    {
      *(_OWORD *)v18 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x13u, v18);
      SCardError = (unsigned int)v18[0];
      if ( LODWORD(v18[0]) )
      {
        if ( LODWORD(v18[0]) == -2146435054 )
        {
          WppTraceIndent(v12, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              61,
              (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
              v13,
              *(_DWORD *)(v9 + 72));
          }
          ResetEvent(*(HANDLE *)(v9 + 128));
          _SetStartedEventToCorrectState((struct _REDIRECTION_CONTEXT *)v9);
        }
        goto LABEL_21;
      }
      if ( a4 == HIDWORD(v18[0]) )
      {
        _CopyReaderStateWStructsForReturn(a4, a3, v18[1]);
LABEL_21:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x13u, v18);
        goto LABEL_22;
      }
    }
  }
  SCardError = -2146435041;
LABEL_22:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  MIDL_user_free(pBuffer);
  MIDL_user_free(v16);
  if ( v17 )
    *((_DWORD *)v17 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x1800108f0  mov     rax, rsp
0x1800108f3  mov     [rax+10h], rbx
0x1800108f7  mov     [rax+18h], rsi
0x1800108fb  push    rdi
0x1800108fc  push    r14
0x1800108fe  push    r15
0x180010900  sub     rsp, 0A0h
0x180010907  mov     esi, r9d
0x18001090a  mov     r15, r8
0x18001090d  mov     edi, edx
0x18001090f  mov     rbx, rcx
0x180010912  mov     qword ptr [rax-68h], 0
0x18001091a  mov     dword ptr [rax+8], 0
0x180010921  mov     qword ptr [rax-70h], 0
0x180010929  xorps   xmm0, xmm0
0x18001092c  movups  xmmword ptr [rax-40h], xmm0
0x180010930  movups  xmmword ptr [rax-30h], xmm0
0x180010934  movups  xmmword ptr [rax-50h], xmm0
0x180010938  mov     qword ptr [rax-60h], 0
0x180010940  mov     qword ptr [rax-58h], 0
0x180010948  test    rcx, rcx
0x18001094b  jnz     short loc_180010957
0x18001094d  mov     eax, 80100004h
0x180010952  jmp     loc_180010C3E
0x180010957  mov     r14, [rcx]
0x18001095a  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x18001095f  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x180010967  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x18001096c  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180010972  test    eax, eax
0x180010974  jz      short loc_180010980
0x180010976  mov     ebx, 8010001Fh
0x18001097b  jmp     loc_180010BFE
0x180010980  movups  xmm0, xmmword ptr [rbx+8]
0x180010984  movdqu  [rsp+0B8h+var_40], xmm0
0x18001098a  mov     [rsp+0B8h+var_30], edi
0x180010991  mov     [rsp+0B8h+var_2C], esi
0x180010998  mov     r8, r15; struct SCARD_READERSTATEW *
0x18001099b  lea     rdx, [rsp+0B8h+var_60]; struct _ReaderStateW **
0x1800109a0  mov     ecx, esi; unsigned int
0x1800109a2  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x1800109a7  test    eax, eax
0x1800109a9  jz      short loc_1800109B5
0x1800109ab  mov     ebx, 80100006h
0x1800109b0  jmp     loc_180010BFE
0x1800109b5  mov     rax, [rsp+0B8h+var_60]
0x1800109ba  mov     [rsp+0B8h+var_28], rax
0x1800109c2  lea     rax, [rsp+0B8h+var_40]
0x1800109c7  mov     [rsp+0B8h+pObject], rax; pObject
0x1800109cc  mov     [rsp+0B8h+nTypeIndex], 12h; nTypeIndex
0x1800109d4  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800109db  lea     r8, pProxyInfo; pProxyInfo
0x1800109e2  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800109e9  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x1800109ee  call    cs:__imp_NdrMesTypeEncode3
0x1800109f4  nop
0x1800109f5  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x1800109fd  mov     dword ptr [rsp+0B8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180010a05  mov     qword ptr [rsp+0B8h+nTypeIndex], r14; lpCriticalSection
0x180010a0a  lea     r9, [rsp+0B8h+var_58]; struct _BUFFER_LIST_STRUCT **
0x180010a0f  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x180010a17  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x180010a1c  mov     ecx, 900A4h; IoControlCode
0x180010a21  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180010a26  test    eax, eax
0x180010a28  jz      short loc_180010A38
0x180010a2a  mov     ecx, eax; int
0x180010a2c  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180010a31  mov     ebx, eax
0x180010a33  jmp     loc_180010BFE
0x180010a38  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180010a3d  test    rcx, rcx
0x180010a40  jz      short loc_180010A51
0x180010a42  call    cs:__imp_MesHandleFree
0x180010a48  mov     [rsp+0B8h+pHandle], 0
0x180010a51  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x180010a56  mov     rcx, [rsp+0B8h+var_58]
0x180010a5b  mov     edx, [rcx+1Ch]; BufferSize
0x180010a5e  mov     rcx, [rcx+10h]; Buffer
0x180010a62  call    cs:__imp_MesDecodeBufferHandleCreate
0x180010a68  test    eax, eax
0x180010a6a  jnz     loc_180010976
0x180010a70  xorps   xmm0, xmm0
0x180010a73  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x180010a78  lea     rax, [rsp+0B8h+var_50]
0x180010a7d  mov     [rsp+0B8h+pObject], rax; pObject
0x180010a82  mov     edi, 13h
0x180010a87  mov     [rsp+0B8h+nTypeIndex], edi; nTypeIndex
0x180010a8b  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180010a92  lea     r8, pProxyInfo; pProxyInfo
0x180010a99  lea     rdx, pPicklingInfo; pPicklingInfo
0x180010aa0  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180010aa5  call    cs:__imp_NdrMesTypeDecode3
0x180010aab  nop
0x180010aac  mov     ebx, dword ptr [rsp+0B8h+var_50]
0x180010ab0  mov     [rsp+0B8h+var_78], ebx
0x180010ab4  test    ebx, ebx
0x180010ab6  jnz     short loc_180010AD3
0x180010ab8  cmp     esi, dword ptr [rsp+0B8h+var_50+4]
0x180010abc  jnz     loc_180010976
0x180010ac2  mov     r8, [rsp+0B8h+var_50+8]; struct _ReaderState_Return *
0x180010ac7  mov     rdx, r15; struct SCARD_READERSTATEW *
0x180010aca  mov     ecx, esi; unsigned int
0x180010acc  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x180010ad1  jmp     short loc_180010B37
0x180010ad3  cmp     ebx, 80100012h
0x180010ad9  jnz     short loc_180010B37
0x180010adb  mov     edx, 2
0x180010ae0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010ae5  lea     rax, WPP_GLOBAL_Control
0x180010aec  mov     rcx, cs:WPP_GLOBAL_Control
0x180010af3  cmp     rcx, rax
0x180010af6  jz      short loc_180010B21
0x180010af8  test    byte ptr [rcx+1Ch], 1
0x180010afc  jz      short loc_180010B21
0x180010afe  cmp     byte ptr [rcx+19h], 4
0x180010b02  jb      short loc_180010B21
0x180010b04  mov     edx, 3Dh ; '='
0x180010b09  mov     eax, [r14+48h]
0x180010b0d  mov     [rsp+0B8h+nTypeIndex], eax
0x180010b11  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180010b18  mov     rcx, [rcx+10h]
0x180010b1c  call    WPP_SF_sd
0x180010b21  mov     rcx, [r14+80h]; hEvent
0x180010b28  call    cs:__imp_ResetEvent
0x180010b2e  mov     rcx, r14; struct _REDIRECTION_CONTEXT *
0x180010b31  call    ?_SetStartedEventToCorrectState@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; _SetStartedEventToCorrectState(_REDIRECTION_CONTEXT *)
0x180010b36  nop
0x180010b37  lea     rax, [rsp+0B8h+var_50]
0x180010b3c  mov     [rsp+0B8h+pObject], rax; pObject
0x180010b41  mov     [rsp+0B8h+nTypeIndex], edi; nTypeIndex
0x180010b45  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180010b4c  lea     r8, pProxyInfo; pProxyInfo
0x180010b53  lea     rdx, pPicklingInfo; pPicklingInfo
0x180010b5a  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180010b5f  call    cs:__imp_NdrMesTypeFree3
0x180010b65  jmp     loc_180010BFE
0x180010b6a  mov     ebx, [rsp+0B8h+var_78]
0x180010b6e  jmp     loc_180010BFE
0x180010b73  mov     ebx, eax
0x180010b75  mov     edx, 2
0x180010b7a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010b7f  lea     rax, WPP_GLOBAL_Control
0x180010b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b8d  cmp     rcx, rax
0x180010b90  jz      short loc_180010BB7
0x180010b92  test    byte ptr [rcx+1Ch], 8
0x180010b96  jz      short loc_180010BB7
0x180010b98  cmp     byte ptr [rcx+19h], 2
0x180010b9c  jb      short loc_180010BB7
0x180010b9e  mov     edx, 3Ch ; '<'
0x180010ba3  mov     [rsp+0B8h+nTypeIndex], ebx
0x180010ba7  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180010bae  mov     rcx, [rcx+10h]
0x180010bb2  call    WPP_SF_sd
0x180010bb7  jmp     short loc_180010BFE
0x180010bb9  mov     ebx, eax
0x180010bbb  mov     edx, 2
0x180010bc0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180010bc5  lea     rax, WPP_GLOBAL_Control
0x180010bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bd3  cmp     rcx, rax
0x180010bd6  jz      short loc_180010BFE
0x180010bd8  test    byte ptr [rcx+1Ch], 8
0x180010bdc  jz      short loc_180010BFE
0x180010bde  cmp     byte ptr [rcx+19h], 2
0x180010be2  jb      short loc_180010BFE
0x180010be4  mov     edx, 3Bh ; ';'
0x180010be9  mov     [rsp+0B8h+nTypeIndex], ebx
0x180010bed  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180010bf4  mov     rcx, [rcx+10h]
0x180010bf8  call    WPP_SF_sd
0x180010bfd  nop
0x180010bfe  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180010c03  test    rcx, rcx
0x180010c06  jz      short loc_180010C17
0x180010c08  call    cs:__imp_MesHandleFree
0x180010c0e  mov     [rsp+0B8h+pHandle], 0
0x180010c17  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x180010c1c  call    MIDL_user_free
0x180010c21  mov     rcx, [rsp+0B8h+var_60]; void *
0x180010c26  call    MIDL_user_free
0x180010c2b  mov     rax, [rsp+0B8h+var_58]
0x180010c30  test    rax, rax
0x180010c33  jz      short loc_180010C3C
0x180010c35  mov     dword ptr [rax+8], 0
0x180010c3c  mov     eax, ebx
0x180010c3e  lea     r11, [rsp+0B8h+var_18]
0x180010c46  mov     rbx, [r11+28h]
0x180010c4a  mov     rsi, [r11+30h]
0x180010c4e  mov     rsp, r11
0x180010c51  pop     r15
0x180010c53  pop     r14
0x180010c55  pop     rdi
0x180010c56  retn
```

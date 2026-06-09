# RedirectedSCardGetStatusChangeA(unsigned __int64,ulong,SCARD_READERSTATEA *,ulong)

- ea: `0x180019f1c`
- end: `0x18001a265`
- name: `?RedirectedSCardGetStatusChangeA@@YAJ_KKPEAUSCARD_READERSTATEA@@K@Z`
- size: `841`
- prototype: `int(unsigned __int64, unsigned int, struct SCARD_READERSTATEA *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800046a0`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x1800127cc`
- `0x180016ca4`
- `0x180016d20`
- `0x18001991c`
- `0x180019a14`
- `0x180019f1c`
- `0x18002e29c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001a145`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001a145`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001a0c2`
- `RPCRT4!NdrMesTypeDecode3` at `0x18001a0c2`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001a01a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18001a01a`
- `RPCRT4!NdrMesTypeFree3` at `0x18001a17c`
- `RPCRT4!NdrMesTypeFree3` at `0x18001a17c`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019f98`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019f98`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001a07f`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18001a07f`

## pseudocode

```c
__int64 __fastcall RedirectedSCardGetStatusChangeA(
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
      goto LABEL_20;
    }
    *((_QWORD *)&v20 + 1) = v16;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x11u, &pObject);
    v11 = _SendSCardIOCTL(589984, pBuffer, pEncodedSize, &v17, (LPCRITICAL_SECTION)v9, 0xFFFFFFFF, 0x800u);
    if ( v11 )
    {
      SCardError = _MakeSCardError(v11);
      goto LABEL_20;
    }
    SafeMesHandleFree(&pHandle);
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
              58,
              (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
              v13,
              *(_DWORD *)(v9 + 72));
          }
          ResetEvent(*(HANDLE *)(v9 + 128));
          _SetStartedEventToCorrectState((struct _REDIRECTION_CONTEXT *)v9);
        }
        goto LABEL_19;
      }
      if ( a4 == HIDWORD(v18[0]) )
      {
        _CopyReaderStateWStructsForReturn(a4, a3, v18[1]);
LABEL_19:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x13u, v18);
        goto LABEL_20;
      }
    }
  }
  SCardError = -2146435041;
LABEL_20:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  MIDL_user_free(v16);
  if ( v17 )
    *((_DWORD *)v17 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x180019f1c  mov     rax, rsp
0x180019f1f  mov     [rax+10h], rbx
0x180019f23  mov     [rax+18h], rsi
0x180019f27  push    rdi
0x180019f28  push    r14
0x180019f2a  push    r15
0x180019f2c  sub     rsp, 0A0h
0x180019f33  mov     edi, r9d
0x180019f36  mov     r15, r8
0x180019f39  mov     esi, edx
0x180019f3b  mov     rbx, rcx
0x180019f3e  mov     qword ptr [rax-68h], 0
0x180019f46  mov     dword ptr [rax+8], 0
0x180019f4d  mov     qword ptr [rax-70h], 0
0x180019f55  xorps   xmm0, xmm0
0x180019f58  movups  xmmword ptr [rax-40h], xmm0
0x180019f5c  movups  xmmword ptr [rax-30h], xmm0
0x180019f60  movups  xmmword ptr [rax-50h], xmm0
0x180019f64  mov     qword ptr [rax-60h], 0
0x180019f6c  mov     qword ptr [rax-58h], 0
0x180019f74  test    rcx, rcx
0x180019f77  jnz     short loc_180019F83
0x180019f79  mov     eax, 80100004h
0x180019f7e  jmp     loc_18001A24C
0x180019f83  mov     r14, [rcx]
0x180019f86  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x180019f8b  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x180019f93  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x180019f98  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180019f9e  test    eax, eax
0x180019fa0  jz      short loc_180019FAC
0x180019fa2  mov     ebx, 8010001Fh
0x180019fa7  jmp     loc_18001A21B
0x180019fac  movups  xmm0, xmmword ptr [rbx+8]
0x180019fb0  movdqu  [rsp+0B8h+var_40], xmm0
0x180019fb6  mov     [rsp+0B8h+var_30], esi
0x180019fbd  mov     [rsp+0B8h+var_2C], edi
0x180019fc4  mov     r8, r15; struct SCARD_READERSTATEW *
0x180019fc7  lea     rdx, [rsp+0B8h+var_60]; struct _ReaderStateW **
0x180019fcc  mov     ecx, edi; unsigned int
0x180019fce  call    ?_AllocAndCopyReaderStateWStructsForCall@@YAJKPEAPEAU_ReaderStateW@@PEAUSCARD_READERSTATEW@@@Z; _AllocAndCopyReaderStateWStructsForCall(ulong,_ReaderStateW * *,SCARD_READERSTATEW *)
0x180019fd3  test    eax, eax
0x180019fd5  jz      short loc_180019FE1
0x180019fd7  mov     ebx, 80100006h
0x180019fdc  jmp     loc_18001A21B
0x180019fe1  mov     rax, [rsp+0B8h+var_60]
0x180019fe6  mov     [rsp+0B8h+var_28], rax
0x180019fee  lea     rax, [rsp+0B8h+var_40]
0x180019ff3  mov     [rsp+0B8h+pObject], rax; pObject
0x180019ff8  mov     [rsp+0B8h+nTypeIndex], 11h; nTypeIndex
0x18001a000  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001a007  lea     r8, pProxyInfo; pProxyInfo
0x18001a00e  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001a015  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18001a01a  call    cs:__imp_NdrMesTypeEncode3
0x18001a020  nop
0x18001a021  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x18001a029  mov     dword ptr [rsp+0B8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18001a031  mov     qword ptr [rsp+0B8h+nTypeIndex], r14; lpCriticalSection
0x18001a036  lea     r9, [rsp+0B8h+var_58]; struct _BUFFER_LIST_STRUCT **
0x18001a03b  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x18001a043  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x18001a048  mov     ecx, 900A0h; IoControlCode
0x18001a04d  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18001a052  test    eax, eax
0x18001a054  jz      short loc_18001A064
0x18001a056  mov     ecx, eax; int
0x18001a058  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18001a05d  mov     ebx, eax
0x18001a05f  jmp     loc_18001A21B
0x18001a064  lea     rcx, [rsp+0B8h+pHandle]; void **
0x18001a069  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18001a06e  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x18001a073  mov     rcx, [rsp+0B8h+var_58]
0x18001a078  mov     edx, [rcx+1Ch]; BufferSize
0x18001a07b  mov     rcx, [rcx+10h]; Buffer
0x18001a07f  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001a085  test    eax, eax
0x18001a087  jnz     loc_180019FA2
0x18001a08d  xorps   xmm0, xmm0
0x18001a090  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x18001a095  lea     rax, [rsp+0B8h+var_50]
0x18001a09a  mov     [rsp+0B8h+pObject], rax; pObject
0x18001a09f  mov     esi, 13h
0x18001a0a4  mov     [rsp+0B8h+nTypeIndex], esi; nTypeIndex
0x18001a0a8  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001a0af  lea     r8, pProxyInfo; pProxyInfo
0x18001a0b6  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001a0bd  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18001a0c2  call    cs:__imp_NdrMesTypeDecode3
0x18001a0c8  nop
0x18001a0c9  mov     ebx, dword ptr [rsp+0B8h+var_50]
0x18001a0cd  mov     [rsp+0B8h+var_78], ebx
0x18001a0d1  test    ebx, ebx
0x18001a0d3  jnz     short loc_18001A0F0
0x18001a0d5  cmp     edi, dword ptr [rsp+0B8h+var_50+4]
0x18001a0d9  jnz     loc_180019FA2
0x18001a0df  mov     r8, [rsp+0B8h+var_50+8]; struct _ReaderState_Return *
0x18001a0e4  mov     rdx, r15; struct SCARD_READERSTATEW *
0x18001a0e7  mov     ecx, edi; unsigned int
0x18001a0e9  call    ?_CopyReaderStateWStructsForReturn@@YAXKPEAUSCARD_READERSTATEW@@PEAU_ReaderState_Return@@@Z; _CopyReaderStateWStructsForReturn(ulong,SCARD_READERSTATEW *,_ReaderState_Return *)
0x18001a0ee  jmp     short loc_18001A154
0x18001a0f0  cmp     ebx, 80100012h
0x18001a0f6  jnz     short loc_18001A154
0x18001a0f8  mov     edx, 2
0x18001a0fd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001a102  lea     rax, WPP_GLOBAL_Control
0x18001a109  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a110  cmp     rcx, rax
0x18001a113  jz      short loc_18001A13E
0x18001a115  test    byte ptr [rcx+1Ch], 1
0x18001a119  jz      short loc_18001A13E
0x18001a11b  cmp     byte ptr [rcx+19h], 4
0x18001a11f  jb      short loc_18001A13E
0x18001a121  mov     edx, 3Ah ; ':'
0x18001a126  mov     eax, [r14+48h]
0x18001a12a  mov     [rsp+0B8h+nTypeIndex], eax
0x18001a12e  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001a135  mov     rcx, [rcx+10h]
0x18001a139  call    WPP_SF_sd
0x18001a13e  mov     rcx, [r14+80h]; hEvent
0x18001a145  call    cs:__imp_ResetEvent
0x18001a14b  mov     rcx, r14; struct _REDIRECTION_CONTEXT *
0x18001a14e  call    ?_SetStartedEventToCorrectState@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; _SetStartedEventToCorrectState(_REDIRECTION_CONTEXT *)
0x18001a153  nop
0x18001a154  lea     rax, [rsp+0B8h+var_50]
0x18001a159  mov     [rsp+0B8h+pObject], rax; pObject
0x18001a15e  mov     [rsp+0B8h+nTypeIndex], esi; nTypeIndex
0x18001a162  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001a169  lea     r8, pProxyInfo; pProxyInfo
0x18001a170  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001a177  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18001a17c  call    cs:__imp_NdrMesTypeFree3
0x18001a182  jmp     loc_18001A21B
0x18001a187  mov     ebx, [rsp+0B8h+var_78]
0x18001a18b  jmp     loc_18001A21B
0x18001a190  mov     ebx, eax
0x18001a192  mov     edx, 2
0x18001a197  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001a19c  lea     rax, WPP_GLOBAL_Control
0x18001a1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1aa  cmp     rcx, rax
0x18001a1ad  jz      short loc_18001A1D4
0x18001a1af  test    byte ptr [rcx+1Ch], 8
0x18001a1b3  jz      short loc_18001A1D4
0x18001a1b5  cmp     byte ptr [rcx+19h], 2
0x18001a1b9  jb      short loc_18001A1D4
0x18001a1bb  mov     edx, 39h ; '9'
0x18001a1c0  mov     [rsp+0B8h+nTypeIndex], ebx
0x18001a1c4  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001a1cb  mov     rcx, [rcx+10h]
0x18001a1cf  call    WPP_SF_sd
0x18001a1d4  jmp     short loc_18001A21B
0x18001a1d6  mov     ebx, eax
0x18001a1d8  mov     edx, 2
0x18001a1dd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001a1e2  lea     rax, WPP_GLOBAL_Control
0x18001a1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1f0  cmp     rcx, rax
0x18001a1f3  jz      short loc_18001A21B
0x18001a1f5  test    byte ptr [rcx+1Ch], 8
0x18001a1f9  jz      short loc_18001A21B
0x18001a1fb  cmp     byte ptr [rcx+19h], 2
0x18001a1ff  jb      short loc_18001A21B
0x18001a201  mov     edx, 38h ; '8'
0x18001a206  mov     [rsp+0B8h+nTypeIndex], ebx
0x18001a20a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001a211  mov     rcx, [rcx+10h]
0x18001a215  call    WPP_SF_sd
0x18001a21a  nop
0x18001a21b  lea     rcx, [rsp+0B8h+pHandle]; void **
0x18001a220  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18001a225  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x18001a22a  call    MIDL_user_free
0x18001a22f  mov     rcx, [rsp+0B8h+var_60]; void *
0x18001a234  call    MIDL_user_free
0x18001a239  mov     rax, [rsp+0B8h+var_58]
0x18001a23e  test    rax, rax
0x18001a241  jz      short loc_18001A24A
0x18001a243  mov     dword ptr [rax+8], 0
0x18001a24a  mov     eax, ebx
0x18001a24c  lea     r11, [rsp+0B8h+var_18]
0x18001a254  mov     rbx, [r11+28h]
0x18001a258  mov     rsi, [r11+30h]
0x18001a25c  mov     rsp, r11
0x18001a25f  pop     r15
0x18001a261  pop     r14
0x18001a263  pop     rdi
0x18001a264  retn
```

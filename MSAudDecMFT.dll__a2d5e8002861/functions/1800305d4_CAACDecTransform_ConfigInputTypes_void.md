# CAACDecTransform::_ConfigInputTypes(void)

- ea: `0x1800305d4`
- end: `0x18003091c`
- name: `?_ConfigInputTypes@CAACDecTransform@@AEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(CAACDecTransform *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180030114`

## callees

- `0x180003af0`
- `0x1800305d4`
- `0x180030f18`
- `0x180031154`
- `0x18003120c`
- `0x18004d320`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1800306cc`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18003075c`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1800307cd`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1800306cc`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18003075c`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x1800307cd`
- `MFPlat!MFCreateMediaType` at `0x1800306a9`
- `MFPlat!MFCreateMediaType` at `0x180030734`
- `MFPlat!MFCreateMediaType` at `0x1800307aa`
- `MFPlat!MFCreateMediaType` at `0x1800306a9`
- `MFPlat!MFCreateMediaType` at `0x180030734`
- `MFPlat!MFCreateMediaType` at `0x1800307aa`

## string_xrefs

- `0x180030611`: `CAACDecTransform::_ConfigInputTypes`
- `0x1800308d2`: `CAACDecTransform::_ConfigInputTypes`
- `0x180030601`: `CAACDecTransform::_ConfigInputTypes()`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::_ConfigInputTypes(CAACDecTransform *this)
{
  int v2; // eax
  HRESULT inited; // ebx
  struct tWAVEFORMATEX *v4; // rdx
  unsigned int v5; // r8d
  IMFMediaType *ppMFType; // [rsp+40h] [rbp-39h] BYREF
  TraceLoggingHelperBase *v8; // [rsp+48h] [rbp-31h]
  _BYTE pWaveFormat[30]; // [rsp+50h] [rbp-29h] BYREF
  WAVEFORMATEX v10; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v11[22]; // [rsp+82h] [rbp+9h] BYREF

  v8 = (CAACDecTransform *)((char *)this + 246664);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246664),
    5u,
    "CAACDecTransform::_ConfigInputTypes",
    0x75Au,
    "CAACDecTransform::_ConfigInputTypes()");
  memset(v11, 0, sizeof(v11));
  memset(&v10, 0, sizeof(v10));
  memset(pWaveFormat, 0, sizeof(pWaveFormat));
  v2 = *((_DWORD *)this + 64038);
  if ( !v2 )
  {
    inited = CMFTSimpleBase::_InitAvailableInputTypeArray((CAACDecTransform *)((char *)this + 24), 5u);
    if ( inited < 0 )
      goto LABEL_27;
    *(_DWORD *)pWaveFormat = 398864;
    *(_WORD *)&pWaveFormat[24] = 0;
    *(_DWORD *)&pWaveFormat[26] = 0;
    ppMFType = 0;
    *(_DWORD *)&pWaveFormat[4] = 48000;
    *(_DWORD *)&pWaveFormat[8] = 1152000;
    *(_DWORD *)&pWaveFormat[12] = 2097176;
    *(_QWORD *)&pWaveFormat[16] = 12;
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = MFInitMediaTypeFromWaveFormatEx(
                 ppMFType,
                 (const WAVEFORMATEX *)pWaveFormat,
                 *(unsigned __int16 *)&pWaveFormat[16] + 18);
      if ( inited >= 0 )
        CMFTSimpleBase::_SetAvailableInputType((CAACDecTransform *)((char *)this + 24), 0, ppMFType);
    }
    if ( ppMFType )
      ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    if ( inited < 0 )
      goto LABEL_28;
    *(_DWORD *)&v10.wFormatTag = 393471;
    v10.cbSize = 0;
    ppMFType = 0;
    v10.nSamplesPerSec = 48000;
    v10.nAvgBytesPerSec = 1152000;
    *(_DWORD *)&v10.nBlockAlign = 2097176;
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = MFInitMediaTypeFromWaveFormatEx(ppMFType, &v10, v10.cbSize + 18);
      if ( inited >= 0 )
        CMFTSimpleBase::_SetAvailableInputType((CAACDecTransform *)((char *)this + 24), 1u, ppMFType);
    }
    if ( ppMFType )
      ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    if ( inited < 0 )
      goto LABEL_28;
    *(_WORD *)&pWaveFormat[18] = 1;
    ppMFType = 0;
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = MFInitMediaTypeFromWaveFormatEx(
                 ppMFType,
                 (const WAVEFORMATEX *)pWaveFormat,
                 *(unsigned __int16 *)&pWaveFormat[16] + 18);
      if ( inited >= 0 )
        CMFTSimpleBase::_SetAvailableInputType((CAACDecTransform *)((char *)this + 24), 2u, ppMFType);
    }
    if ( ppMFType )
      ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    if ( inited < 0 )
      goto LABEL_28;
    *(_WORD *)&pWaveFormat[18] = 3;
    inited = CAACDecTransform::_AddTypes(this, (struct tWAVEFORMATEX *)pWaveFormat, 3u, 1);
    if ( inited < 0 )
      goto LABEL_27;
    *(_DWORD *)&v10.wFormatTag = 398848;
    v10.nSamplesPerSec = 48000;
    v4 = &v10;
    v10.nAvgBytesPerSec = 1152000;
    *(_DWORD *)&v10.nBlockAlign = 2097176;
    v5 = 4;
    v10.cbSize = 0;
    goto LABEL_26;
  }
  inited = 0;
  if ( v2 != 1 )
    return (unsigned int)inited;
  inited = CMFTSimpleBase::_InitAvailableInputTypeArray((CAACDecTransform *)((char *)this + 24), 1u);
  if ( inited >= 0 )
  {
    *(_DWORD *)pWaveFormat = 398864;
    *(_WORD *)&pWaveFormat[24] = 0;
    v4 = (struct tWAVEFORMATEX *)pWaveFormat;
    *(_DWORD *)&pWaveFormat[26] = 0;
    v5 = 0;
    *(_DWORD *)&pWaveFormat[4] = 48000;
    *(_DWORD *)&pWaveFormat[8] = 1152000;
    *(_DWORD *)&pWaveFormat[12] = 2097176;
    *(_QWORD *)&pWaveFormat[16] = 65548;
LABEL_26:
    inited = CAACDecTransform::_AddTypes(this, v4, v5, 1);
  }
LABEL_27:
  if ( inited )
LABEL_28:
    TraceLoggingHelperBase::TraceVA(
      v8,
      2u,
      "CAACDecTransform::_ConfigInputTypes",
      0x7C4u,
      "Error %08X returned: File: %s, Line: %d",
      inited,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
      1988);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800305d4  push    rbp
0x1800305d6  push    rbx
0x1800305d7  push    rsi
0x1800305d8  push    rdi
0x1800305d9  push    r13
0x1800305db  push    r14
0x1800305dd  lea     rbp, [rsp-2Fh]
0x1800305e2  sub     rsp, 0A8h
0x1800305e9  mov     rax, cs:__security_cookie
0x1800305f0  xor     rax, rsp
0x1800305f3  mov     [rbp+57h+var_38], rax
0x1800305f7  lea     rax, [rcx+3C388h]
0x1800305fe  mov     rsi, rcx
0x180030601  lea     rcx, aCaacdectransfo_60; "CAACDecTransform::_ConfigInputTypes()"
0x180030608  mov     [rbp+57h+var_88], rax
0x18003060c  mov     [rsp+0D0h+Format], rcx; Format
0x180030611  lea     r8, aCaacdectransfo_13; "CAACDecTransform::_ConfigInputTypes"
0x180030618  mov     ebx, 5
0x18003061d  mov     rcx, rax; this
0x180030620  mov     r9d, 75Ah; unsigned int
0x180030626  mov     edx, ebx; unsigned __int8
0x180030628  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003062d  xor     eax, eax
0x18003062f  xorps   xmm0, xmm0
0x180030632  movups  xmmword ptr [rbp+57h+var_4E], xmm0
0x180030636  mov     qword ptr [rbp+57h+var_4E+0Eh], rax
0x18003063a  mov     [rbp+57h+var_60.wFormatTag], ax
0x18003063e  mov     [rbp+57h+pWaveFormat.wFormatTag], ax
0x180030642  mov     eax, [rsi+3E898h]
0x180030648  movups  xmmword ptr [rbp+57h+pWaveFormat.nChannels], xmm0
0x18003064c  movups  xmmword ptr [rbp+57h+var_60.nChannels], xmm0
0x180030650  movups  xmmword ptr [rbp+57h+pWaveFormat.wBitsPerSample], xmm0
0x180030654  test    eax, eax
0x180030656  jnz     loc_18003085E
0x18003065c  lea     r14, [rsi+18h]
0x180030660  mov     edx, ebx; unsigned int
0x180030662  mov     rcx, r14; this
0x180030665  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x18003066a  mov     ebx, eax
0x18003066c  test    eax, eax
0x18003066e  js      loc_1800308BD
0x180030674  xor     eax, eax
0x180030676  mov     dword ptr [rbp+57h+pWaveFormat.wFormatTag], 61610h
0x18003067d  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180030681  mov     [rbp+57h+var_68], ax
0x180030685  mov     [rbp+57h+var_66], eax
0x180030688  mov     [rbp+57h+ppMFType], rax
0x18003068c  mov     [rbp+57h+pWaveFormat.nSamplesPerSec], 0BB80h
0x180030693  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], 119400h
0x18003069a  mov     dword ptr [rbp+57h+pWaveFormat.nBlockAlign], 200018h
0x1800306a1  mov     qword ptr [rbp+57h+pWaveFormat.cbSize], 0Ch
0x1800306a9  call    cs:__imp_MFCreateMediaType
0x1800306b0  nop     dword ptr [rax+rax+00h]
0x1800306b5  mov     ebx, eax
0x1800306b7  test    eax, eax
0x1800306b9  js      short loc_1800306EC
0x1800306bb  movzx   r8d, [rbp+57h+pWaveFormat.cbSize]
0x1800306c0  lea     rdx, [rbp+57h+pWaveFormat]; pWaveFormat
0x1800306c4  mov     rcx, [rbp+57h+ppMFType]; pMFType
0x1800306c8  add     r8d, 12h; cbBufSize
0x1800306cc  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x1800306d3  nop     dword ptr [rax+rax+00h]
0x1800306d8  mov     ebx, eax
0x1800306da  test    eax, eax
0x1800306dc  js      short loc_1800306EC
0x1800306de  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x1800306e2  xor     edx, edx; unsigned int
0x1800306e4  mov     rcx, r14; this
0x1800306e7  call    ?_SetAvailableInputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableInputType(ulong,IMFMediaType *)
0x1800306ec  mov     rcx, [rbp+57h+ppMFType]
0x1800306f0  test    rcx, rcx
0x1800306f3  jz      short loc_180030702
0x1800306f5  mov     rax, [rcx]
0x1800306f8  mov     rax, [rax+10h]
0x1800306fc  call    cs:__guard_dispatch_icall_fptr
0x180030702  test    ebx, ebx
0x180030704  js      loc_1800308C1
0x18003070a  xor     eax, eax
0x18003070c  mov     dword ptr [rbp+57h+var_60.wFormatTag], 600FFh
0x180030713  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180030717  mov     [rbp+57h+var_60.cbSize], ax
0x18003071b  mov     [rbp+57h+ppMFType], rax
0x18003071f  mov     [rbp+57h+var_60.nSamplesPerSec], 0BB80h
0x180030726  mov     [rbp+57h+var_60.nAvgBytesPerSec], 119400h
0x18003072d  mov     dword ptr [rbp+57h+var_60.nBlockAlign], 200018h
0x180030734  call    cs:__imp_MFCreateMediaType
0x18003073b  nop     dword ptr [rax+rax+00h]
0x180030740  mov     ebx, eax
0x180030742  mov     edi, 1
0x180030747  test    eax, eax
0x180030749  js      short loc_18003077C
0x18003074b  movzx   r8d, [rbp+57h+var_60.cbSize]
0x180030750  lea     rdx, [rbp+57h+var_60]; pWaveFormat
0x180030754  mov     rcx, [rbp+57h+ppMFType]; pMFType
0x180030758  add     r8d, 12h; cbBufSize
0x18003075c  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x180030763  nop     dword ptr [rax+rax+00h]
0x180030768  mov     ebx, eax
0x18003076a  test    eax, eax
0x18003076c  js      short loc_18003077C
0x18003076e  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x180030772  mov     edx, edi; unsigned int
0x180030774  mov     rcx, r14; this
0x180030777  call    ?_SetAvailableInputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableInputType(ulong,IMFMediaType *)
0x18003077c  mov     rcx, [rbp+57h+ppMFType]
0x180030780  test    rcx, rcx
0x180030783  jz      short loc_180030792
0x180030785  mov     rax, [rcx]
0x180030788  mov     rax, [rax+10h]
0x18003078c  call    cs:__guard_dispatch_icall_fptr
0x180030792  test    ebx, ebx
0x180030794  js      loc_1800308C1
0x18003079a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18003079e  mov     [rbp-17h], di
0x1800307a2  mov     [rbp+57h+ppMFType], 0
0x1800307aa  call    cs:__imp_MFCreateMediaType
0x1800307b1  nop     dword ptr [rax+rax+00h]
0x1800307b6  mov     ebx, eax
0x1800307b8  test    eax, eax
0x1800307ba  js      short loc_1800307F0
0x1800307bc  movzx   r8d, [rbp+57h+pWaveFormat.cbSize]
0x1800307c1  lea     rdx, [rbp+57h+pWaveFormat]; pWaveFormat
0x1800307c5  mov     rcx, [rbp+57h+ppMFType]; pMFType
0x1800307c9  add     r8d, 12h; cbBufSize
0x1800307cd  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x1800307d4  nop     dword ptr [rax+rax+00h]
0x1800307d9  mov     ebx, eax
0x1800307db  test    eax, eax
0x1800307dd  js      short loc_1800307F0
0x1800307df  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x1800307e3  mov     edx, 2; unsigned int
0x1800307e8  mov     rcx, r14; this
0x1800307eb  call    ?_SetAvailableInputType@CMFTSimpleBase@@IEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleBase::_SetAvailableInputType(ulong,IMFMediaType *)
0x1800307f0  mov     rcx, [rbp+57h+ppMFType]
0x1800307f4  test    rcx, rcx
0x1800307f7  jz      short loc_180030806
0x1800307f9  mov     rax, [rcx]
0x1800307fc  mov     rax, [rax+10h]
0x180030800  call    cs:__guard_dispatch_icall_fptr
0x180030806  test    ebx, ebx
0x180030808  js      loc_1800308C1
0x18003080e  mov     r8d, 3; unsigned int
0x180030814  lea     rdx, [rbp+57h+pWaveFormat]; struct tWAVEFORMATEX *
0x180030818  mov     r9d, edi; int
0x18003081b  mov     [rbp-17h], r8w
0x180030820  mov     rcx, rsi; this
0x180030823  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x180030828  mov     ebx, eax
0x18003082a  test    eax, eax
0x18003082c  js      loc_1800308BD
0x180030832  xor     eax, eax
0x180030834  mov     dword ptr [rbp+57h+var_60.wFormatTag], 61600h
0x18003083b  mov     [rbp+57h+var_60.nSamplesPerSec], 0BB80h
0x180030842  lea     rdx, [rbp+57h+var_60]
0x180030846  mov     [rbp+57h+var_60.nAvgBytesPerSec], 119400h
0x18003084d  mov     dword ptr [rbp+57h+var_60.nBlockAlign], 200018h
0x180030854  lea     r8d, [rax+4]
0x180030858  mov     [rbp+57h+var_60.cbSize], ax
0x18003085c  jmp     short loc_1800308B0
0x18003085e  xor     ebx, ebx
0x180030860  lea     edi, [rbx+1]
0x180030863  cmp     eax, edi
0x180030865  jnz     loc_1800308FD
0x18003086b  lea     rcx, [rsi+18h]; this
0x18003086f  mov     edx, edi; unsigned int
0x180030871  call    ?_InitAvailableInputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableInputTypeArray(ulong)
0x180030876  mov     ebx, eax
0x180030878  test    eax, eax
0x18003087a  js      short loc_1800308BD
0x18003087c  xor     eax, eax
0x18003087e  mov     dword ptr [rbp+57h+pWaveFormat.wFormatTag], 61610h
0x180030885  mov     [rbp+57h+var_68], ax
0x180030889  lea     rdx, [rbp+57h+pWaveFormat]; struct tWAVEFORMATEX *
0x18003088d  mov     [rbp+57h+var_66], eax
0x180030890  xor     r8d, r8d; unsigned int
0x180030893  mov     [rbp+57h+pWaveFormat.nSamplesPerSec], 0BB80h
0x18003089a  mov     [rbp+57h+pWaveFormat.nAvgBytesPerSec], 119400h
0x1800308a1  mov     dword ptr [rbp+57h+pWaveFormat.nBlockAlign], 200018h
0x1800308a8  mov     qword ptr [rbp+57h+pWaveFormat.cbSize], 1000Ch
0x1800308b0  mov     r9d, edi; int
0x1800308b3  mov     rcx, rsi; this
0x1800308b6  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x1800308bb  mov     ebx, eax
0x1800308bd  test    ebx, ebx
0x1800308bf  jz      short loc_1800308FD
0x1800308c1  mov     rcx, [rbp+57h+var_88]; this
0x1800308c5  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x1800308cc  mov     r9d, 7C4h; unsigned int
0x1800308d2  lea     r8, aCaacdectransfo_13; "CAACDecTransform::_ConfigInputTypes"
0x1800308d9  mov     [rsp+0D0h+var_98], r9d
0x1800308de  mov     edx, 2; unsigned __int8
0x1800308e3  mov     [rsp+0D0h+var_A0], rax
0x1800308e8  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x1800308ef  mov     [rsp+0D0h+var_A8], ebx
0x1800308f3  mov     [rsp+0D0h+Format], rax; Format
0x1800308f8  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800308fd  mov     eax, ebx
0x1800308ff  mov     rcx, [rbp+57h+var_38]
0x180030903  xor     rcx, rsp; StackCookie
0x180030906  call    __security_check_cookie
0x18003090b  add     rsp, 0A8h
0x180030912  pop     r14
0x180030914  pop     r13
0x180030916  pop     rdi
0x180030917  pop     rsi
0x180030918  pop     rbx
0x180030919  pop     rbp
0x18003091a  retn
```

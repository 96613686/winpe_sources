# RedirectedSCardGetReaderIcon(unsigned __int64,ushort const *,uchar *,ulong *)

- ea: `0x1800190cc`
- end: `0x1800193b2`
- name: `?RedirectedSCardGetReaderIcon@@YAJ_KPEBGPEAEPEAK@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct _REDIR_LOCAL_SCARDCONTEXT *, const unsigned __int16 *, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180012e40`
- `0x180025980`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x180017c48`
- `0x1800180b4`
- `0x1800190cc`
- `0x18001991c`
- `0x180019a14`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180019269`
- `RPCRT4!NdrMesTypeDecode3` at `0x180019269`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800191ab`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800191ab`
- `RPCRT4!NdrMesTypeFree3` at `0x1800192cc`
- `RPCRT4!NdrMesTypeFree3` at `0x1800192cc`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019159`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019159`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180019226`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180019226`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RedirectedSCardGetReaderIcon(
        struct _REDIR_LOCAL_SCARDCONTEXT *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  unsigned int SCardError; // ebx
  DWORD RedirectionTimeoutMs; // eax
  int v12; // eax
  handle_t pHandle; // [rsp+48h] [rbp-60h] BYREF
  char *pBuffer; // [rsp+50h] [rbp-58h] BYREF
  struct _BUFFER_LIST_STRUCT *v15; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int8 *v16[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 pObject; // [rsp+70h] [rbp-38h] BYREF
  const unsigned __int16 *v18; // [rsp+80h] [rbp-28h]
  unsigned int pEncodedSize; // [rsp+B0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v15 = 0;
  pObject = 0;
  v18 = 0;
  *(_OWORD *)v16 = 0;
  if ( !a1 || !a4 )
    return 2148532228LL;
  v8 = *(struct _RTL_CRITICAL_SECTION **)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 68LL) < 3u )
    return 120;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    pObject = *(_OWORD *)((char *)a1 + 8);
    v18 = a2;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Cu, &pObject);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      RedirectionTimeoutMs = _GetRedirectionTimeoutMs();
    else
      RedirectionTimeoutMs = -1;
    v12 = _SendSCardIOCTL(590084, pBuffer, pEncodedSize, &v15, v8, RedirectionTimeoutMs, 0x20800u);
    if ( v12 )
    {
      SCardError = _MakeSCardError(v12);
      goto LABEL_16;
    }
    SafeMesHandleFree(&pHandle);
    if ( !MesDecodeBufferHandleCreate(*((char **)v15 + 2), *((_DWORD *)v15 + 7), &pHandle) )
    {
      *(_OWORD *)v16 = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Du, v16);
      SCardError = (unsigned int)v16[0];
      if ( !LODWORD(v16[0]) )
        SCardError = _CopyReturnToCallerBuffer(a1, v16[1], HIDWORD(v16[0]), a3, a4, 1u);
      NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Du, v16);
      goto LABEL_16;
    }
  }
  SCardError = -2146435041;
LABEL_16:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v15 )
    *((_DWORD *)v15 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x1800190cc  mov     r11, rsp
0x1800190cf  mov     [r11+10h], rbx
0x1800190d3  mov     [r11+18h], rsi
0x1800190d7  push    rdi
0x1800190d8  push    r14
0x1800190da  push    r15
0x1800190dc  sub     rsp, 90h
0x1800190e3  mov     r14, r9
0x1800190e6  mov     r15, r8
0x1800190e9  mov     rbx, rdx
0x1800190ec  mov     rdi, rcx
0x1800190ef  mov     qword ptr [r11-58h], 0
0x1800190f7  mov     dword ptr [r11+8], 0
0x1800190ff  mov     qword ptr [r11-60h], 0
0x180019107  mov     qword ptr [r11-50h], 0
0x18001910f  xorps   xmm0, xmm0
0x180019112  xor     eax, eax
0x180019114  movups  [rsp+0A8h+var_38], xmm0
0x180019119  mov     [r11-28h], rax
0x18001911d  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180019122  test    rcx, rcx
0x180019125  jz      loc_180019394
0x18001912b  test    r9, r9
0x18001912e  jz      loc_180019394
0x180019134  mov     rsi, [rcx]
0x180019137  cmp     dword ptr [rsi+44h], 3
0x18001913b  jnb     short loc_180019147
0x18001913d  mov     eax, 78h ; 'x'
0x180019142  jmp     loc_180019399
0x180019147  lea     r8, [rsp+0A8h+pHandle]; pHandle
0x18001914c  lea     rdx, [rsp+0A8h+pEncodedSize]; pEncodedSize
0x180019154  lea     rcx, [rsp+0A8h+pBuffer]; pBuffer
0x180019159  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001915f  test    eax, eax
0x180019161  jz      short loc_18001916D
0x180019163  mov     ebx, 8010001Fh
0x180019168  jmp     loc_18001936B
0x18001916d  movups  xmm0, xmmword ptr [rdi+8]
0x180019171  movdqu  [rsp+0A8h+var_38], xmm0
0x180019177  mov     [rsp+0A8h+var_28], rbx
0x18001917f  lea     rax, [rsp+0A8h+var_38]
0x180019184  mov     [rsp+0A8h+pObject], rax; pObject
0x180019189  mov     [rsp+0A8h+nTypeIndex], 2Ch ; ','; nTypeIndex
0x180019191  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180019198  lea     r8, pProxyInfo; pProxyInfo
0x18001919f  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800191a6  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x1800191ab  call    cs:__imp_NdrMesTypeEncode3
0x1800191b1  nop
0x1800191b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x1800191b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x1800191be  test    al, al
0x1800191c0  jz      short loc_1800191C9
0x1800191c2  call    ?_GetRedirectionTimeoutMs@@YAKXZ; _GetRedirectionTimeoutMs(void)
0x1800191c7  jmp     short loc_1800191CC
0x1800191c9  or      eax, 0FFFFFFFFh
0x1800191cc  mov     [rsp+0A8h+var_78], 20800h; unsigned int
0x1800191d4  mov     dword ptr [rsp+0A8h+pObject], eax; dwMilliseconds
0x1800191d8  mov     qword ptr [rsp+0A8h+nTypeIndex], rsi; lpCriticalSection
0x1800191dd  lea     r9, [rsp+0A8h+var_50]; struct _BUFFER_LIST_STRUCT **
0x1800191e2  mov     r8d, [rsp+0A8h+pEncodedSize]; InputBufferLength
0x1800191ea  mov     rdx, [rsp+0A8h+pBuffer]; InputBuffer
0x1800191ef  mov     ecx, 90104h; IoControlCode
0x1800191f4  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x1800191f9  test    eax, eax
0x1800191fb  jz      short loc_18001920B
0x1800191fd  mov     ecx, eax; int
0x1800191ff  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180019204  mov     ebx, eax
0x180019206  jmp     loc_18001936B
0x18001920b  lea     rcx, [rsp+0A8h+pHandle]; void **
0x180019210  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180019215  lea     r8, [rsp+0A8h+pHandle]; pHandle
0x18001921a  mov     rcx, [rsp+0A8h+var_50]
0x18001921f  mov     edx, [rcx+1Ch]; BufferSize
0x180019222  mov     rcx, [rcx+10h]; Buffer
0x180019226  call    cs:__imp_MesDecodeBufferHandleCreate
0x18001922c  test    eax, eax
0x18001922e  jnz     loc_180019163
0x180019234  xorps   xmm0, xmm0
0x180019237  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x18001923c  lea     rax, [rsp+0A8h+var_48]
0x180019241  mov     [rsp+0A8h+pObject], rax; pObject
0x180019246  mov     esi, 2Dh ; '-'
0x18001924b  mov     [rsp+0A8h+nTypeIndex], esi; nTypeIndex
0x18001924f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180019256  lea     r8, pProxyInfo; pProxyInfo
0x18001925d  lea     rdx, pPicklingInfo; pPicklingInfo
0x180019264  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x180019269  call    cs:__imp_NdrMesTypeDecode3
0x18001926f  nop
0x180019270  mov     ebx, dword ptr [rsp+0A8h+var_48]
0x180019274  mov     [rsp+0A8h+var_68], ebx
0x180019278  test    ebx, ebx
0x18001927a  jnz     short loc_1800192A4
0x18001927c  mov     dword ptr [rsp+0A8h+pObject], 1; unsigned int
0x180019284  mov     qword ptr [rsp+0A8h+nTypeIndex], r14; unsigned int *
0x180019289  mov     r9, r15; unsigned __int8 *
0x18001928c  mov     r8d, dword ptr [rsp+0A8h+var_48+4]; unsigned int
0x180019291  mov     rdx, [rsp+0A8h+var_48+8]; unsigned __int8 *
0x180019296  mov     rcx, rdi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180019299  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x18001929e  mov     ebx, eax
0x1800192a0  mov     [rsp+0A8h+var_68], eax
0x1800192a4  lea     rax, [rsp+0A8h+var_48]
0x1800192a9  mov     [rsp+0A8h+pObject], rax; pObject
0x1800192ae  mov     [rsp+0A8h+nTypeIndex], esi; nTypeIndex
0x1800192b2  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800192b9  lea     r8, pProxyInfo; pProxyInfo
0x1800192c0  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800192c7  mov     rcx, [rsp+0A8h+pHandle]; Handle
0x1800192cc  call    cs:__imp_NdrMesTypeFree3
0x1800192d2  jmp     loc_18001936B
0x1800192d7  mov     ebx, [rsp+0A8h+var_68]
0x1800192db  jmp     loc_18001936B
0x1800192e0  mov     ebx, eax
0x1800192e2  mov     edx, 2
0x1800192e7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800192ec  lea     rax, WPP_GLOBAL_Control
0x1800192f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192fa  cmp     rcx, rax
0x1800192fd  jz      short loc_180019324
0x1800192ff  test    byte ptr [rcx+1Ch], 8
0x180019303  jz      short loc_180019324
0x180019305  cmp     byte ptr [rcx+19h], 2
0x180019309  jb      short loc_180019324
0x18001930b  mov     edx, 57h ; 'W'
0x180019310  mov     [rsp+0A8h+nTypeIndex], ebx
0x180019314  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001931b  mov     rcx, [rcx+10h]
0x18001931f  call    WPP_SF_sd
0x180019324  jmp     short loc_18001936B
0x180019326  mov     ebx, eax
0x180019328  mov     edx, 2
0x18001932d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019332  lea     rax, WPP_GLOBAL_Control
0x180019339  mov     rcx, cs:WPP_GLOBAL_Control
0x180019340  cmp     rcx, rax
0x180019343  jz      short loc_18001936B
0x180019345  test    byte ptr [rcx+1Ch], 8
0x180019349  jz      short loc_18001936B
0x18001934b  cmp     byte ptr [rcx+19h], 2
0x18001934f  jb      short loc_18001936B
0x180019351  mov     edx, 56h ; 'V'
0x180019356  mov     [rsp+0A8h+nTypeIndex], ebx
0x18001935a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180019361  mov     rcx, [rcx+10h]
0x180019365  call    WPP_SF_sd
0x18001936a  nop
0x18001936b  lea     rcx, [rsp+0A8h+pHandle]; void **
0x180019370  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180019375  mov     rcx, [rsp+0A8h+pBuffer]; void *
0x18001937a  call    MIDL_user_free
0x18001937f  mov     rax, [rsp+0A8h+var_50]
0x180019384  test    rax, rax
0x180019387  jz      short loc_180019390
0x180019389  mov     dword ptr [rax+8], 0
0x180019390  mov     eax, ebx
0x180019392  jmp     short loc_180019399
0x180019394  mov     eax, 80100004h
0x180019399  lea     r11, [rsp+0A8h+var_18]
0x1800193a1  mov     rbx, [r11+28h]
0x1800193a5  mov     rsi, [r11+30h]
0x1800193a9  mov     rsp, r11
0x1800193ac  pop     r15
0x1800193ae  pop     r14
0x1800193b0  pop     rdi
0x1800193b1  retn
```

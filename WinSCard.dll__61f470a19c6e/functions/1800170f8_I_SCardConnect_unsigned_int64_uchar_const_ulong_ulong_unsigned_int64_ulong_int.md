# I_SCardConnect(unsigned __int64,uchar const *,ulong,ulong,unsigned __int64 *,ulong *,int)

- ea: `0x1800170f8`
- end: `0x180017524`
- name: `?I_SCardConnect@@YAJ_KPEBEKKPEA_KPEAKH@Z`
- size: `1068`
- prototype: `__int64 __fastcall(__int64, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int64 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180011b70`
- `0x180012000`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180011760`
- `0x1800170f8`
- `0x18001991c`
- `0x180019a14`
- `0x18002ef38`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180017382`
- `RPCRT4!NdrMesTypeDecode3` at `0x180017382`
- `RPCRT4!NdrMesTypeEncode3` at `0x180017228`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800172b3`
- `RPCRT4!NdrMesTypeEncode3` at `0x180017228`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800172b3`
- `RPCRT4!NdrMesTypeFree3` at `0x18001742f`
- `RPCRT4!NdrMesTypeFree3` at `0x18001742f`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001719b`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001719b`
- `RPCRT4!MesHandleFree` at `0x180017312`
- `RPCRT4!MesHandleFree` at `0x1800174d8`
- `RPCRT4!MesHandleFree` at `0x180017312`
- `RPCRT4!MesHandleFree` at `0x1800174d8`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180017332`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180017332`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall I_SCardConnect(
        __int64 a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 *a5,
        unsigned int *a6,
        int a7)
{
  unsigned __int64 *v11; // r15
  unsigned int SCardError; // ebx
  int v14; // edi
  int v15; // eax
  char *v16; // rax
  unsigned __int64 v17; // rdi
  handle_t pHandle; // [rsp+40h] [rbp-A8h] BYREF
  int v19; // [rsp+48h] [rbp-A0h]
  char *pBuffer; // [rsp+50h] [rbp-98h] BYREF
  struct _BUFFER_LIST_STRUCT *v21; // [rsp+58h] [rbp-90h] BYREF
  __int128 v22; // [rsp+60h] [rbp-88h] BYREF
  size_t Size[2]; // [rsp+70h] [rbp-78h]
  void *Src[2]; // [rsp+80h] [rbp-68h]
  _QWORD pObject[4]; // [rsp+90h] [rbp-58h] BYREF
  _QWORD v26[4]; // [rsp+B0h] [rbp-38h] BYREF
  unsigned int pEncodedSize; // [rsp+F0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v21 = 0;
  memset(v26, 0, sizeof(v26));
  memset(pObject, 0, sizeof(pObject));
  v22 = 0;
  *(_OWORD *)Size = 0;
  *(_OWORD *)Src = 0;
  if ( !a1 )
    return 2148532228LL;
  v11 = a5;
  if ( !a5 )
    return 2148532228LL;
  if ( !a2 )
    return 2148532233LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    *(_OWORD *)&pObject[1] = *(_OWORD *)(a1 + 8);
    *(_OWORD *)&v26[1] = *(_OWORD *)&pObject[1];
    pObject[3] = __PAIR64__(a4, a3);
    v26[3] = __PAIR64__(a4, a3);
    v14 = a7;
    if ( a7 )
    {
      pObject[0] = a2;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x15u, pObject);
    }
    else
    {
      v26[0] = a2;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x14u, v26);
    }
    v15 = _SendSCardIOCTL(
            v14 != 0 ? 590000 : 589996,
            pBuffer,
            pEncodedSize,
            &v21,
            *(LPCRITICAL_SECTION *)a1,
            0xFFFFFFFF,
            0x800u);
    if ( v15 )
    {
      SCardError = _MakeSCardError(v15);
      goto LABEL_22;
    }
    if ( pHandle )
    {
      MesHandleFree(pHandle);
      pHandle = 0;
    }
    if ( !MesDecodeBufferHandleCreate(*((char **)v21 + 2), *((_DWORD *)v21 + 7), &pHandle) )
    {
      v22 = 0;
      *(_OWORD *)Size = 0;
      *(_OWORD *)Src = 0;
      NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x16u, &v22);
      SCardError = v22;
      v19 = v22;
      if ( (_DWORD)v22 )
      {
LABEL_21:
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x16u, &v22);
        goto LABEL_22;
      }
      if ( LODWORD(Size[1]) <= 0x20 )
      {
        v16 = (char *)MIDL_user_allocate(LODWORD(Size[1]) + 40LL);
        v17 = (unsigned __int64)v16;
        if ( v16 )
        {
          *(_QWORD *)v16 = a1;
          *(_OWORD *)(v16 + 8) = *(_OWORD *)(a1 + 8);
          *((_DWORD *)v16 + 6) = Size[1];
          *((_QWORD *)v16 + 4) = v16 + 40;
          memcpy_0(v16 + 40, Src[0], LODWORD(Size[1]));
          *v11 = v17;
          if ( a6 )
            *a6 = (unsigned int)Src[1];
        }
        else
        {
          SCardError = -2146435066;
          v19 = -2146435066;
        }
        goto LABEL_21;
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
  if ( v21 )
    *((_DWORD *)v21 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x1800170f8  mov     rax, rsp
0x1800170fb  mov     [rax+10h], rbx
0x1800170ff  mov     [rax+18h], rsi
0x180017103  push    rdi
0x180017104  push    r14
0x180017106  push    r15
0x180017108  sub     rsp, 0D0h
0x18001710f  mov     edi, r9d
0x180017112  mov     esi, r8d
0x180017115  mov     rbx, rdx
0x180017118  mov     r14, rcx
0x18001711b  mov     [rsp+0E8h+pBuffer], 0
0x180017124  mov     dword ptr [rax+8], 0
0x18001712b  mov     [rsp+0E8h+pHandle], 0
0x180017134  mov     [rsp+0E8h+var_90], 0
0x18001713d  xorps   xmm0, xmm0
0x180017140  movups  xmmword ptr [rax-38h], xmm0
0x180017144  movups  xmmword ptr [rax-28h], xmm0
0x180017148  xorps   xmm1, xmm1
0x18001714b  movups  xmmword ptr [rax-58h], xmm1
0x18001714f  movups  xmmword ptr [rax-48h], xmm1
0x180017153  movups  [rsp+0E8h+var_88], xmm0
0x180017158  movups  xmmword ptr [rax-78h], xmm0
0x18001715c  movups  xmmword ptr [rax-68h], xmm0
0x180017160  test    rcx, rcx
0x180017163  jz      loc_180017506
0x180017169  mov     r15, [rsp+0E8h+arg_20]
0x180017171  test    r15, r15
0x180017174  jz      loc_180017506
0x18001717a  test    rdx, rdx
0x18001717d  jnz     short loc_180017189
0x18001717f  mov     eax, 80100009h
0x180017184  jmp     loc_18001750B
0x180017189  lea     r8, [rsp+0E8h+pHandle]; pHandle
0x18001718e  lea     rdx, [rsp+0E8h+pEncodedSize]; pEncodedSize
0x180017196  lea     rcx, [rsp+0E8h+pBuffer]; pBuffer
0x18001719b  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800171a1  test    eax, eax
0x1800171a3  jz      short loc_1800171AF
0x1800171a5  mov     ebx, 8010001Fh
0x1800171aa  jmp     loc_1800174CE
0x1800171af  movups  xmm0, xmmword ptr [r14+8]
0x1800171b4  movdqu  [rsp+0E8h+var_50], xmm0
0x1800171bd  movdqu  [rsp+0E8h+var_30], xmm0
0x1800171c6  mov     [rsp+0E8h+var_40], esi
0x1800171cd  mov     [rsp+0E8h+var_20], esi
0x1800171d4  mov     [rsp+0E8h+var_3C], edi
0x1800171db  mov     [rsp+0E8h+var_1C], edi
0x1800171e2  mov     edi, [rsp+0E8h+arg_30]
0x1800171e9  test    edi, edi
0x1800171eb  jz      loc_18001727C
0x1800171f1  mov     [rsp+0E8h+var_58], rbx
0x1800171f9  lea     rax, [rsp+0E8h+var_58]
0x180017201  mov     [rsp+0E8h+pObject], rax; pObject
0x180017206  mov     [rsp+0E8h+nTypeIndex], 15h; nTypeIndex
0x18001720e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180017215  lea     r8, pProxyInfo; pProxyInfo
0x18001721c  lea     rdx, pPicklingInfo; pPicklingInfo
0x180017223  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180017228  call    cs:__imp_NdrMesTypeEncode3
0x18001722e  jmp     loc_1800172BA
0x180017233  mov     ebx, eax
0x180017235  mov     edx, 2
0x18001723a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001723f  lea     rax, WPP_GLOBAL_Control
0x180017246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001724d  cmp     rcx, rax
0x180017250  jz      short loc_180017277
0x180017252  test    byte ptr [rcx+1Ch], 8
0x180017256  jz      short loc_180017277
0x180017258  cmp     byte ptr [rcx+19h], 2
0x18001725c  jb      short loc_180017277
0x18001725e  mov     edx, 3Eh ; '>'
0x180017263  mov     [rsp+0E8h+nTypeIndex], ebx
0x180017267  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001726e  mov     rcx, [rcx+10h]
0x180017272  call    WPP_SF_sd
0x180017277  jmp     loc_1800174CE
0x18001727c  mov     [rsp+0E8h+var_38], rbx
0x180017284  lea     rax, [rsp+0E8h+var_38]
0x18001728c  mov     [rsp+0E8h+pObject], rax; pObject
0x180017291  mov     [rsp+0E8h+nTypeIndex], 14h; nTypeIndex
0x180017299  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800172a0  lea     r8, pProxyInfo; pProxyInfo
0x1800172a7  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800172ae  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x1800172b3  call    cs:__imp_NdrMesTypeEncode3
0x1800172b9  nop
0x1800172ba  neg     edi
0x1800172bc  sbb     ecx, ecx
0x1800172be  and     ecx, 4
0x1800172c1  add     ecx, 900ACh; IoControlCode
0x1800172c7  mov     [rsp+0E8h+var_B8], 800h; unsigned int
0x1800172cf  mov     dword ptr [rsp+0E8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x1800172d7  mov     rax, [r14]
0x1800172da  mov     qword ptr [rsp+0E8h+nTypeIndex], rax; lpCriticalSection
0x1800172df  lea     r9, [rsp+0E8h+var_90]; struct _BUFFER_LIST_STRUCT **
0x1800172e4  mov     r8d, [rsp+0E8h+pEncodedSize]; InputBufferLength
0x1800172ec  mov     rdx, [rsp+0E8h+pBuffer]; InputBuffer
0x1800172f1  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x1800172f6  test    eax, eax
0x1800172f8  jz      short loc_180017308
0x1800172fa  mov     ecx, eax; int
0x1800172fc  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180017301  mov     ebx, eax
0x180017303  jmp     loc_1800174CE
0x180017308  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x18001730d  test    rcx, rcx
0x180017310  jz      short loc_180017321
0x180017312  call    cs:__imp_MesHandleFree
0x180017318  mov     [rsp+0E8h+pHandle], 0
0x180017321  lea     r8, [rsp+0E8h+pHandle]; pHandle
0x180017326  mov     rcx, [rsp+0E8h+var_90]
0x18001732b  mov     edx, [rcx+1Ch]; BufferSize
0x18001732e  mov     rcx, [rcx+10h]; Buffer
0x180017332  call    cs:__imp_MesDecodeBufferHandleCreate
0x180017338  test    eax, eax
0x18001733a  jnz     loc_1800171A5
0x180017340  xorps   xmm0, xmm0
0x180017343  movups  [rsp+0E8h+var_88], xmm0
0x180017348  movups  xmmword ptr [rsp+0E8h+Size], xmm0
0x18001734d  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x180017355  lea     rax, [rsp+0E8h+var_88]
0x18001735a  mov     [rsp+0E8h+pObject], rax; pObject
0x18001735f  mov     esi, 16h
0x180017364  mov     [rsp+0E8h+nTypeIndex], esi; nTypeIndex
0x180017368  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001736f  lea     r8, pProxyInfo; pProxyInfo
0x180017376  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001737d  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180017382  call    cs:__imp_NdrMesTypeDecode3
0x180017388  nop
0x180017389  mov     ebx, dword ptr [rsp+0E8h+var_88]
0x18001738d  mov     [rsp+0E8h+var_A0], ebx
0x180017391  test    ebx, ebx
0x180017393  jnz     short loc_180017407
0x180017395  cmp     dword ptr [rsp+0E8h+Size+8], 20h ; ' '
0x18001739a  ja      loc_1800171A5
0x1800173a0  mov     ecx, dword ptr [rsp+0E8h+Size+8]
0x1800173a4  add     rcx, 28h ; '('; size
0x1800173a8  call    MIDL_user_allocate
0x1800173ad  mov     rdi, rax
0x1800173b0  test    rax, rax
0x1800173b3  jz      short loc_1800173FE
0x1800173b5  mov     [rax], r14
0x1800173b8  movups  xmm0, xmmword ptr [r14+8]
0x1800173bd  movdqu  xmmword ptr [rax+8], xmm0
0x1800173c2  mov     ecx, dword ptr [rsp+0E8h+Size+8]
0x1800173c6  mov     [rax+18h], ecx
0x1800173c9  lea     rcx, [rax+28h]; void *
0x1800173cd  mov     [rax+20h], rcx
0x1800173d1  mov     r8d, dword ptr [rsp+0E8h+Size+8]; Size
0x1800173d6  mov     rdx, [rsp+0E8h+Src]; Src
0x1800173de  call    memcpy_0
0x1800173e3  mov     [r15], rdi
0x1800173e6  mov     rcx, [rsp+0E8h+arg_28]
0x1800173ee  test    rcx, rcx
0x1800173f1  jz      short loc_180017407
0x1800173f3  mov     eax, dword ptr [rsp+0E8h+Src+8]
0x1800173fa  mov     [rcx], eax
0x1800173fc  jmp     short loc_180017407
0x1800173fe  mov     ebx, 80100006h
0x180017403  mov     [rsp+0E8h+var_A0], ebx
0x180017407  lea     rax, [rsp+0E8h+var_88]
0x18001740c  mov     [rsp+0E8h+pObject], rax; pObject
0x180017411  mov     [rsp+0E8h+nTypeIndex], esi; nTypeIndex
0x180017415  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18001741c  lea     r8, pProxyInfo; pProxyInfo
0x180017423  lea     rdx, pPicklingInfo; pPicklingInfo
0x18001742a  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x18001742f  call    cs:__imp_NdrMesTypeFree3
0x180017435  jmp     loc_1800174CE
0x18001743a  mov     ebx, [rsp+0E8h+var_A0]
0x18001743e  jmp     loc_1800174CE
0x180017443  mov     ebx, eax
0x180017445  mov     edx, 2
0x18001744a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001744f  lea     rax, WPP_GLOBAL_Control
0x180017456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001745d  cmp     rcx, rax
0x180017460  jz      short loc_180017487
0x180017462  test    byte ptr [rcx+1Ch], 8
0x180017466  jz      short loc_180017487
0x180017468  cmp     byte ptr [rcx+19h], 2
0x18001746c  jb      short loc_180017487
0x18001746e  mov     edx, 40h ; '@'
0x180017473  mov     [rsp+0E8h+nTypeIndex], ebx
0x180017477  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001747e  mov     rcx, [rcx+10h]
0x180017482  call    WPP_SF_sd
0x180017487  jmp     short loc_1800174CE
0x180017489  mov     ebx, eax
0x18001748b  mov     edx, 2
0x180017490  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017495  lea     rax, WPP_GLOBAL_Control
0x18001749c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174a3  cmp     rcx, rax
0x1800174a6  jz      short loc_1800174CE
0x1800174a8  test    byte ptr [rcx+1Ch], 8
0x1800174ac  jz      short loc_1800174CE
0x1800174ae  cmp     byte ptr [rcx+19h], 2
0x1800174b2  jb      short loc_1800174CE
0x1800174b4  mov     edx, 3Fh ; '?'
0x1800174b9  mov     [rsp+0E8h+nTypeIndex], ebx
0x1800174bd  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x1800174c4  mov     rcx, [rcx+10h]
0x1800174c8  call    WPP_SF_sd
0x1800174cd  nop
0x1800174ce  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x1800174d3  test    rcx, rcx
0x1800174d6  jz      short loc_1800174E7
0x1800174d8  call    cs:__imp_MesHandleFree
0x1800174de  mov     [rsp+0E8h+pHandle], 0
0x1800174e7  mov     rcx, [rsp+0E8h+pBuffer]; void *
0x1800174ec  call    MIDL_user_free
0x1800174f1  mov     rax, [rsp+0E8h+var_90]
0x1800174f6  test    rax, rax
0x1800174f9  jz      short loc_180017502
0x1800174fb  mov     dword ptr [rax+8], 0
0x180017502  mov     eax, ebx
0x180017504  jmp     short loc_18001750B
0x180017506  mov     eax, 80100004h
0x18001750b  lea     r11, [rsp+0E8h+var_18]
0x180017513  mov     rbx, [r11+28h]
0x180017517  mov     rsi, [r11+30h]
0x18001751b  mov     rsp, r11
0x18001751e  pop     r15
0x180017520  pop     r14
0x180017522  pop     rdi
0x180017523  retn
```

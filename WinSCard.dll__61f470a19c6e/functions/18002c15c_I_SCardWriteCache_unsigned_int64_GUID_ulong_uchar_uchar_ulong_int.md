# I_SCardWriteCache(unsigned __int64,_GUID *,ulong,uchar *,uchar *,ulong,int)

- ea: `0x18002c15c`
- end: `0x18002c42b`
- name: `?I_SCardWriteCache@@YAJ_KPEAU_GUID@@KPEAE2KH@Z`
- size: `719`
- prototype: `__int64 __fastcall(unsigned __int64, struct _GUID *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011880`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180012878`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002c15c`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x18002c2a8`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c333`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c2a8`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002c333`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c1fd`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002c1fd`

## pseudocode

```c
__int64 __fastcall I_SCardWriteCache(
        __int64 a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v11; // r14
  unsigned int v13; // ebx
  int v14; // edi
  int v15; // eax
  unsigned int SCardError; // eax
  handle_t pHandle; // [rsp+40h] [rbp-98h] BYREF
  char *pBuffer; // [rsp+48h] [rbp-90h] BYREF
  struct _BUFFER_LIST_STRUCT *v19; // [rsp+50h] [rbp-88h] BYREF
  _QWORD pObject[4]; // [rsp+58h] [rbp-80h] BYREF
  __int128 v21; // [rsp+78h] [rbp-60h]
  _QWORD v22[4]; // [rsp+88h] [rbp-50h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-30h]
  unsigned int pEncodedSize; // [rsp+E0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v19 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  memset(pObject, 0, sizeof(pObject));
  v21 = 0;
  if ( !a1 || !a2 || !a4 )
    return 2148532228LL;
  v11 = *(struct _RTL_CRITICAL_SECTION **)a1;
  if ( *(_DWORD *)(*(_QWORD *)a1 + 68LL) < 2u )
    return 0;
  if ( MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    v13 = -2146435041;
  }
  else
  {
    *(_OWORD *)&pObject[1] = *(_OWORD *)(a1 + 8);
    *(_OWORD *)&v22[1] = *(_OWORD *)&pObject[1];
    pObject[3] = a2;
    v22[3] = a2;
    *(_QWORD *)&v21 = __PAIR64__(a6, a3);
    *(_QWORD *)&v23 = __PAIR64__(a6, a3);
    *((_QWORD *)&v21 + 1) = a5;
    *((_QWORD *)&v23 + 1) = a5;
    v14 = a7;
    if ( a7 )
    {
      pObject[0] = a4;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Bu, pObject);
    }
    else
    {
      v22[0] = a4;
      NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x2Au, v22);
    }
    v15 = _SendSCardIOCTL(v14 != 0 ? 590076 : 590072, pBuffer, pEncodedSize, &v19, v11, 0xFFFFFFFF, 0x800u);
    if ( v15 )
    {
      SCardError = _MakeSCardError(v15);
    }
    else
    {
      SafeMesHandleFree(&pHandle);
      SCardError = I_DecodeLongReturn(*((char **)v19 + 2), *((_DWORD *)v19 + 7));
    }
    v13 = SCardError;
  }
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v19 )
    *((_DWORD *)v19 + 2) = 0;
  return v13;
}

```

## disassembly

```asm
0x18002c15c  mov     rax, rsp
0x18002c15f  mov     [rax+10h], rbx
0x18002c163  mov     [rax+18h], rsi
0x18002c167  push    rdi
0x18002c168  push    r14
0x18002c16a  push    r15
0x18002c16c  sub     rsp, 0C0h
0x18002c173  mov     rbx, r9
0x18002c176  mov     r15d, r8d
0x18002c179  mov     rsi, rdx
0x18002c17c  mov     rdi, rcx
0x18002c17f  mov     [rsp+0D8h+pBuffer], 0
0x18002c188  mov     dword ptr [rax+8], 0
0x18002c18f  mov     [rsp+0D8h+pHandle], 0
0x18002c198  mov     [rsp+0D8h+var_88], 0
0x18002c1a1  xorps   xmm0, xmm0
0x18002c1a4  movups  xmmword ptr [rax-50h], xmm0
0x18002c1a8  movups  xmmword ptr [rax-40h], xmm0
0x18002c1ac  movups  xmmword ptr [rax-30h], xmm0
0x18002c1b0  xorps   xmm1, xmm1
0x18002c1b3  movups  xmmword ptr [rax-80h], xmm1
0x18002c1b7  movups  xmmword ptr [rax-70h], xmm1
0x18002c1bb  movups  xmmword ptr [rax-60h], xmm1
0x18002c1bf  test    rcx, rcx
0x18002c1c2  jz      loc_18002C40D
0x18002c1c8  test    rdx, rdx
0x18002c1cb  jz      loc_18002C40D
0x18002c1d1  test    rbx, rbx
0x18002c1d4  jz      loc_18002C40D
0x18002c1da  mov     r14, [rcx]
0x18002c1dd  cmp     dword ptr [r14+44h], 2
0x18002c1e2  jnb     short loc_18002C1EB
0x18002c1e4  xor     eax, eax
0x18002c1e6  jmp     loc_18002C412
0x18002c1eb  lea     r8, [rsp+0D8h+pHandle]; pHandle
0x18002c1f0  lea     rdx, [rsp+0D8h+pEncodedSize]; pEncodedSize
0x18002c1f8  lea     rcx, [rsp+0D8h+pBuffer]; pBuffer
0x18002c1fd  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002c203  test    eax, eax
0x18002c205  jz      short loc_18002C211
0x18002c207  mov     ebx, 8010001Fh
0x18002c20c  jmp     loc_18002C3E4
0x18002c211  movups  xmm0, xmmword ptr [rdi+8]
0x18002c215  movdqu  [rsp+0D8h+var_78], xmm0
0x18002c21b  movdqu  [rsp+0D8h+var_48], xmm0
0x18002c224  mov     [rsp+0D8h+var_68], rsi
0x18002c229  mov     [rsp+0D8h+var_38], rsi
0x18002c231  mov     [rsp+0D8h+var_60], r15d
0x18002c236  mov     [rsp+0D8h+var_30], r15d
0x18002c23e  mov     eax, [rsp+0D8h+arg_28]
0x18002c245  mov     [rsp+0D8h+var_5C], eax
0x18002c249  mov     [rsp+0D8h+var_2C], eax
0x18002c250  mov     rax, [rsp+0D8h+arg_20]
0x18002c258  mov     [rsp+0D8h+var_58], rax
0x18002c260  mov     [rsp+0D8h+var_28], rax
0x18002c268  mov     edi, [rsp+0D8h+arg_30]
0x18002c26f  test    edi, edi
0x18002c271  jz      loc_18002C2FC
0x18002c277  mov     [rsp+0D8h+var_80], rbx
0x18002c27c  lea     rax, [rsp+0D8h+var_80]
0x18002c281  mov     [rsp+0D8h+pObject], rax; pObject
0x18002c286  mov     [rsp+0D8h+nTypeIndex], 2Bh ; '+'; nTypeIndex
0x18002c28e  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c295  lea     r8, pProxyInfo; pProxyInfo
0x18002c29c  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c2a3  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002c2a8  call    cs:__imp_NdrMesTypeEncode3
0x18002c2ae  jmp     loc_18002C33A
0x18002c2b3  mov     ebx, eax
0x18002c2b5  mov     edx, 2
0x18002c2ba  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c2bf  lea     rax, WPP_GLOBAL_Control
0x18002c2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2cd  cmp     rcx, rax
0x18002c2d0  jz      short loc_18002C2F7
0x18002c2d2  test    byte ptr [rcx+1Ch], 8
0x18002c2d6  jz      short loc_18002C2F7
0x18002c2d8  cmp     byte ptr [rcx+19h], 2
0x18002c2dc  jb      short loc_18002C2F7
0x18002c2de  mov     edx, 54h ; 'T'
0x18002c2e3  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002c2e7  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c2ee  mov     rcx, [rcx+10h]
0x18002c2f2  call    WPP_SF_sd
0x18002c2f7  jmp     loc_18002C3E4
0x18002c2fc  mov     [rsp+0D8h+var_50], rbx
0x18002c304  lea     rax, [rsp+0D8h+var_50]
0x18002c30c  mov     [rsp+0D8h+pObject], rax; pObject
0x18002c311  mov     [rsp+0D8h+nTypeIndex], 2Ah ; '*'; nTypeIndex
0x18002c319  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002c320  lea     r8, pProxyInfo; pProxyInfo
0x18002c327  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002c32e  mov     rcx, [rsp+0D8h+pHandle]; Handle
0x18002c333  call    cs:__imp_NdrMesTypeEncode3
0x18002c339  nop
0x18002c33a  neg     edi
0x18002c33c  sbb     ecx, ecx
0x18002c33e  and     ecx, 4
0x18002c341  add     ecx, 900F8h; IoControlCode
0x18002c347  mov     [rsp+0D8h+var_A8], 800h; unsigned int
0x18002c34f  mov     dword ptr [rsp+0D8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002c357  mov     qword ptr [rsp+0D8h+nTypeIndex], r14; lpCriticalSection
0x18002c35c  lea     r9, [rsp+0D8h+var_88]; struct _BUFFER_LIST_STRUCT **
0x18002c361  mov     r8d, [rsp+0D8h+pEncodedSize]; InputBufferLength
0x18002c369  mov     rdx, [rsp+0D8h+pBuffer]; InputBuffer
0x18002c36e  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002c373  test    eax, eax
0x18002c375  jz      short loc_18002C382
0x18002c377  mov     ecx, eax; int
0x18002c379  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002c37e  mov     ebx, eax
0x18002c380  jmp     short loc_18002C3E4
0x18002c382  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002c387  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c38c  mov     rcx, [rsp+0D8h+var_88]
0x18002c391  mov     edx, [rcx+1Ch]; unsigned int
0x18002c394  mov     rcx, [rcx+10h]; unsigned __int8 *
0x18002c398  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x18002c39d  jmp     short loc_18002C37E
0x18002c39f  mov     ebx, eax
0x18002c3a1  mov     edx, 2
0x18002c3a6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c3ab  lea     rax, WPP_GLOBAL_Control
0x18002c3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c3b9  cmp     rcx, rax
0x18002c3bc  jz      short loc_18002C3E4
0x18002c3be  test    byte ptr [rcx+1Ch], 8
0x18002c3c2  jz      short loc_18002C3E4
0x18002c3c4  cmp     byte ptr [rcx+19h], 2
0x18002c3c8  jb      short loc_18002C3E4
0x18002c3ca  mov     edx, 55h ; 'U'
0x18002c3cf  mov     [rsp+0D8h+nTypeIndex], ebx
0x18002c3d3  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002c3da  mov     rcx, [rcx+10h]
0x18002c3de  call    WPP_SF_sd
0x18002c3e3  nop
0x18002c3e4  lea     rcx, [rsp+0D8h+pHandle]; void **
0x18002c3e9  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002c3ee  mov     rcx, [rsp+0D8h+pBuffer]; void *
0x18002c3f3  call    MIDL_user_free
0x18002c3f8  mov     rax, [rsp+0D8h+var_88]
0x18002c3fd  test    rax, rax
0x18002c400  jz      short loc_18002C409
0x18002c402  mov     dword ptr [rax+8], 0
0x18002c409  mov     eax, ebx
0x18002c40b  jmp     short loc_18002C412
0x18002c40d  mov     eax, 80100004h
0x18002c412  lea     r11, [rsp+0D8h+var_18]
0x18002c41a  mov     rbx, [r11+28h]
0x18002c41e  mov     rsi, [r11+30h]
0x18002c422  mov     rsp, r11
0x18002c425  pop     r15
0x18002c427  pop     r14
0x18002c429  pop     rdi
0x18002c42a  retn
```

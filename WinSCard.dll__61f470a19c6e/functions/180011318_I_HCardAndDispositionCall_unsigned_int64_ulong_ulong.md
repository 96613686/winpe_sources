# I_HCardAndDispositionCall(unsigned __int64,ulong,ulong)

- ea: `0x180011318`
- end: `0x1800114d9`
- name: `?I_HCardAndDispositionCall@@YAJ_KKK@Z`
- size: `449`
- prototype: `int(unsigned __int64, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180001210`
- `0x180006910`
- `0x180010c60`
- `0x180010f50`
- `0x180011040`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180011318`
- `0x180012878`
- `0x18001991c`
- `0x180019a14`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x1800113e4`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800113e4`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001138b`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18001138b`
- `RPCRT4!MesHandleFree` at `0x180011494`
- `RPCRT4!MesHandleFree` at `0x180011494`

## pseudocode

```c
__int64 __fastcall I_HCardAndDispositionCall(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v7; // edi
  int v8; // eax
  unsigned int SCardError; // eax
  char *pBuffer; // [rsp+40h] [rbp-48h] BYREF
  struct _BUFFER_LIST_STRUCT *v11; // [rsp+48h] [rbp-40h] BYREF
  __int128 pObject; // [rsp+50h] [rbp-38h] BYREF
  __int128 v13; // [rsp+60h] [rbp-28h]
  __int64 v14; // [rsp+70h] [rbp-18h]
  unsigned int pEncodedSize; // [rsp+90h] [rbp+8h] BYREF
  handle_t pHandle; // [rsp+A8h] [rbp+20h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v11 = 0;
  pObject = 0;
  v13 = 0;
  v14 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    v7 = -2146435041;
  }
  else
  {
    pObject = *(_OWORD *)(a1 + 8);
    v13 = *(_OWORD *)(a1 + 24);
    LODWORD(v14) = a2;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x19u, &pObject);
    v8 = _SendSCardIOCTL(a3, pBuffer, pEncodedSize, &v11, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v8 )
      SCardError = _MakeSCardError(v8);
    else
      SCardError = I_DecodeLongReturn(*((char **)v11 + 2), *((_DWORD *)v11 + 7));
    v7 = SCardError;
  }
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  MIDL_user_free(pBuffer);
  if ( v11 )
    *((_DWORD *)v11 + 2) = 0;
  return v7;
}

```

## disassembly

```asm
0x180011318  mov     rax, rsp
0x18001131b  mov     [rax+10h], rsi
0x18001131f  mov     [rax+18h], rdi
0x180011323  push    r14
0x180011325  sub     rsp, 80h
0x18001132c  mov     r14d, r8d
0x18001132f  mov     esi, edx
0x180011331  mov     rdi, rcx
0x180011334  mov     qword ptr [rax-48h], 0
0x18001133c  mov     dword ptr [rax+8], 0
0x180011343  mov     qword ptr [rax+20h], 0
0x18001134b  mov     qword ptr [rax-40h], 0
0x180011353  xorps   xmm0, xmm0
0x180011356  xor     eax, eax
0x180011358  movups  [rsp+88h+var_38], xmm0
0x18001135d  movups  [rsp+88h+var_28], xmm0
0x180011362  mov     [rsp+88h+var_18], rax
0x180011367  test    rcx, rcx
0x18001136a  jnz     short loc_180011376
0x18001136c  mov     eax, 80100004h
0x180011371  jmp     loc_1800114C3
0x180011376  lea     r8, [rsp+88h+pHandle]; pHandle
0x18001137e  lea     rdx, [rsp+88h+pEncodedSize]; pEncodedSize
0x180011386  lea     rcx, [rsp+88h+pBuffer]; pBuffer
0x18001138b  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180011391  test    eax, eax
0x180011393  jz      short loc_18001139F
0x180011395  mov     edi, 8010001Fh
0x18001139a  jmp     loc_180011487
0x18001139f  movups  xmm0, xmmword ptr [rdi+8]
0x1800113a3  movups  [rsp+88h+var_38], xmm0
0x1800113a8  movups  xmm1, xmmword ptr [rdi+18h]
0x1800113ac  movups  [rsp+88h+var_28], xmm1
0x1800113b1  mov     dword ptr [rsp+88h+var_18], esi
0x1800113b5  lea     rax, [rsp+88h+var_38]
0x1800113ba  mov     [rsp+88h+pObject], rax; pObject
0x1800113bf  mov     [rsp+88h+nTypeIndex], 19h; nTypeIndex
0x1800113c7  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800113ce  lea     r8, pProxyInfo; pProxyInfo
0x1800113d5  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800113dc  mov     rcx, [rsp+88h+pHandle]; Handle
0x1800113e4  call    cs:__imp_NdrMesTypeEncode3
0x1800113ea  nop
0x1800113eb  mov     rax, [rdi]
0x1800113ee  mov     [rsp+88h+var_58], 800h; unsigned int
0x1800113f6  mov     dword ptr [rsp+88h+pObject], 0FFFFFFFFh; dwMilliseconds
0x1800113fe  mov     rax, [rax]
0x180011401  mov     qword ptr [rsp+88h+nTypeIndex], rax; lpCriticalSection
0x180011406  lea     r9, [rsp+88h+var_40]; struct _BUFFER_LIST_STRUCT **
0x18001140b  mov     r8d, [rsp+88h+pEncodedSize]; InputBufferLength
0x180011413  mov     rdx, [rsp+88h+pBuffer]; InputBuffer
0x180011418  mov     ecx, r14d; IoControlCode
0x18001141b  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180011420  test    eax, eax
0x180011422  jz      short loc_18001142F
0x180011424  mov     ecx, eax; int
0x180011426  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18001142b  mov     edi, eax
0x18001142d  jmp     short loc_180011487
0x18001142f  mov     rcx, [rsp+88h+var_40]
0x180011434  mov     edx, [rcx+1Ch]; unsigned int
0x180011437  mov     rcx, [rcx+10h]; unsigned __int8 *
0x18001143b  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x180011440  jmp     short loc_18001142B
0x180011442  mov     edi, eax
0x180011444  mov     edx, 2
0x180011449  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001144e  lea     rax, WPP_GLOBAL_Control
0x180011455  mov     rcx, cs:WPP_GLOBAL_Control
0x18001145c  cmp     rcx, rax
0x18001145f  jz      short loc_180011487
0x180011461  test    byte ptr [rcx+1Ch], 8
0x180011465  jz      short loc_180011487
0x180011467  cmp     byte ptr [rcx+19h], 2
0x18001146b  jb      short loc_180011487
0x18001146d  mov     edx, 43h ; 'C'
0x180011472  mov     [rsp+88h+nTypeIndex], edi
0x180011476  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18001147d  mov     rcx, [rcx+10h]
0x180011481  call    WPP_SF_sd
0x180011486  nop
0x180011487  mov     rcx, [rsp+88h+pHandle]; Handle
0x18001148f  test    rcx, rcx
0x180011492  jz      short loc_1800114A6
0x180011494  call    cs:__imp_MesHandleFree
0x18001149a  mov     [rsp+88h+pHandle], 0
0x1800114a6  mov     rcx, [rsp+88h+pBuffer]; void *
0x1800114ab  call    MIDL_user_free
0x1800114b0  mov     rax, [rsp+88h+var_40]
0x1800114b5  test    rax, rax
0x1800114b8  jz      short loc_1800114C1
0x1800114ba  mov     dword ptr [rax+8], 0
0x1800114c1  mov     eax, edi
0x1800114c3  lea     r11, [rsp+88h+var_8]
0x1800114cb  mov     rsi, [r11+18h]
0x1800114cf  mov     rdi, [r11+20h]
0x1800114d3  mov     rsp, r11
0x1800114d6  pop     r14
0x1800114d8  retn
```

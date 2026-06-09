# RedirectedSCardSetAttrib(unsigned __int64,ulong,uchar const *,ulong)

- ea: `0x18002db5c`
- end: `0x18002dd04`
- name: `?RedirectedSCardSetAttrib@@YAJ_KKPEBEK@Z`
- size: `424`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023740`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180012878`
- `0x180016ca4`
- `0x18001991c`
- `0x180019a14`
- `0x18002db5c`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x18002dc2a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18002dc2a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002dbc7`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18002dbc7`

## pseudocode

```c
__int64 __fastcall RedirectedSCardSetAttrib(__int64 a1, unsigned int a2, const unsigned __int8 *a3, unsigned int a4)
{
  unsigned int v9; // edi
  int v10; // eax
  unsigned int SCardError; // eax
  handle_t pHandle; // [rsp+40h] [rbp-78h] BYREF
  char *pBuffer; // [rsp+48h] [rbp-70h] BYREF
  struct _BUFFER_LIST_STRUCT *v14; // [rsp+50h] [rbp-68h] BYREF
  __int128 pObject; // [rsp+58h] [rbp-60h] BYREF
  __int128 v16; // [rsp+68h] [rbp-50h]
  __int128 v17; // [rsp+78h] [rbp-40h]
  unsigned int pEncodedSize; // [rsp+C0h] [rbp+8h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v14 = 0;
  pObject = 0;
  v16 = 0;
  v17 = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    v9 = -2146435041;
  }
  else
  {
    pObject = *(_OWORD *)(a1 + 8);
    v16 = *(_OWORD *)(a1 + 24);
    *(_QWORD *)&v17 = __PAIR64__(a4, a2);
    *((_QWORD *)&v17 + 1) = a3;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0x26u, &pObject);
    v10 = _SendSCardIOCTL(590044, pBuffer, pEncodedSize, &v14, **(LPCRITICAL_SECTION **)a1, 0xFFFFFFFF, 0x800u);
    if ( v10 )
      SCardError = _MakeSCardError(v10);
    else
      SCardError = I_DecodeLongReturn(*((char **)v14 + 2), *((_DWORD *)v14 + 7));
    v9 = SCardError;
  }
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v14 )
    *((_DWORD *)v14 + 2) = 0;
  return v9;
}

```

## disassembly

```asm
0x18002db5c  mov     rax, rsp
0x18002db5f  push    rsi
0x18002db60  push    rdi
0x18002db61  push    r14
0x18002db63  push    r15
0x18002db65  sub     rsp, 98h
0x18002db6c  mov     esi, r9d
0x18002db6f  mov     r14, r8
0x18002db72  mov     r15d, edx
0x18002db75  mov     rdi, rcx
0x18002db78  mov     qword ptr [rax-70h], 0
0x18002db80  mov     dword ptr [rax+8], 0
0x18002db87  mov     qword ptr [rax-78h], 0
0x18002db8f  mov     qword ptr [rax-68h], 0
0x18002db97  xorps   xmm0, xmm0
0x18002db9a  movups  xmmword ptr [rax-60h], xmm0
0x18002db9e  movups  xmmword ptr [rax-50h], xmm0
0x18002dba2  movups  xmmword ptr [rax-40h], xmm0
0x18002dba6  test    rcx, rcx
0x18002dba9  jnz     short loc_18002DBB5
0x18002dbab  mov     eax, 80100004h
0x18002dbb0  jmp     loc_18002DCF6
0x18002dbb5  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x18002dbba  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x18002dbc2  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x18002dbc7  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18002dbcd  test    eax, eax
0x18002dbcf  jz      short loc_18002DBDB
0x18002dbd1  mov     edi, 8010001Fh
0x18002dbd6  jmp     loc_18002DCCF
0x18002dbdb  movups  xmm0, xmmword ptr [rdi+8]
0x18002dbdf  movups  [rsp+0B8h+var_60], xmm0
0x18002dbe4  movups  xmm1, xmmword ptr [rdi+18h]
0x18002dbe8  movups  [rsp+0B8h+var_50], xmm1
0x18002dbed  mov     [rsp+0B8h+var_40], r15d
0x18002dbf2  mov     [rsp+0B8h+var_38], r14
0x18002dbfa  mov     [rsp+0B8h+var_3C], esi
0x18002dbfe  lea     rax, [rsp+0B8h+var_60]
0x18002dc03  mov     [rsp+0B8h+pObject], rax; pObject
0x18002dc08  mov     [rsp+0B8h+nTypeIndex], 26h ; '&'; nTypeIndex
0x18002dc10  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18002dc17  lea     r8, pProxyInfo; pProxyInfo
0x18002dc1e  lea     rdx, pPicklingInfo; pPicklingInfo
0x18002dc25  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x18002dc2a  call    cs:__imp_NdrMesTypeEncode3
0x18002dc30  nop
0x18002dc31  mov     rax, [rdi]
0x18002dc34  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x18002dc3c  mov     dword ptr [rsp+0B8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x18002dc44  mov     rax, [rax]
0x18002dc47  mov     qword ptr [rsp+0B8h+nTypeIndex], rax; lpCriticalSection
0x18002dc4c  lea     r9, [rsp+0B8h+var_68]; struct _BUFFER_LIST_STRUCT **
0x18002dc51  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x18002dc59  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x18002dc5e  mov     ecx, 900DCh; IoControlCode
0x18002dc63  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18002dc68  test    eax, eax
0x18002dc6a  jz      short loc_18002DC77
0x18002dc6c  mov     ecx, eax; int
0x18002dc6e  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18002dc73  mov     edi, eax
0x18002dc75  jmp     short loc_18002DCCF
0x18002dc77  mov     rcx, [rsp+0B8h+var_68]
0x18002dc7c  mov     edx, [rcx+1Ch]; unsigned int
0x18002dc7f  mov     rcx, [rcx+10h]; unsigned __int8 *
0x18002dc83  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x18002dc88  jmp     short loc_18002DC73
0x18002dc8a  mov     edi, eax
0x18002dc8c  mov     edx, 2
0x18002dc91  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002dc96  lea     rax, WPP_GLOBAL_Control
0x18002dc9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dca4  cmp     rcx, rax
0x18002dca7  jz      short loc_18002DCCF
0x18002dca9  test    byte ptr [rcx+1Ch], 8
0x18002dcad  jz      short loc_18002DCCF
0x18002dcaf  cmp     byte ptr [rcx+19h], 2
0x18002dcb3  jb      short loc_18002DCCF
0x18002dcb5  mov     edx, 50h ; 'P'
0x18002dcba  mov     [rsp+0B8h+nTypeIndex], edi
0x18002dcbe  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18002dcc5  mov     rcx, [rcx+10h]
0x18002dcc9  call    WPP_SF_sd
0x18002dcce  nop
0x18002dccf  lea     rcx, [rsp+0B8h+pHandle]; void **
0x18002dcd4  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18002dcd9  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x18002dcde  call    MIDL_user_free
0x18002dce3  mov     rax, [rsp+0B8h+var_68]
0x18002dce8  test    rax, rax
0x18002dceb  jz      short loc_18002DCF4
0x18002dced  mov     dword ptr [rax+8], 0
0x18002dcf4  mov     eax, edi
0x18002dcf6  add     rsp, 98h
0x18002dcfd  pop     r15
0x18002dcff  pop     r14
0x18002dd01  pop     rdi
0x18002dd02  pop     rsi
0x18002dd03  retn
```

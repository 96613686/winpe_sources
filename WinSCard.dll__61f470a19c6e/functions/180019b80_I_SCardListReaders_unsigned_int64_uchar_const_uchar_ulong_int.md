# I_SCardListReaders(unsigned __int64,uchar const *,uchar *,ulong *,int)

- ea: `0x180019b80`
- end: `0x180019efb`
- name: `?I_SCardListReaders@@YAJ_KPEBEPEAEPEAKH@Z`
- size: `891`
- prototype: `__int64 __fastcall(struct _REDIR_LOCAL_SCARDCONTEXT *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x18000e110`
- `0x18000e980`

## callees

- `0x18000605c`
- `0x180006c80`
- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180016ca4`
- `0x180016ef0`
- `0x18001991c`
- `0x180019a14`
- `0x180019b80`
- `0x18002e1e4`
- `0x18002e234`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x180019d89`
- `RPCRT4!NdrMesTypeDecode3` at `0x180019d89`
- `RPCRT4!NdrMesTypeEncode3` at `0x180019cdd`
- `RPCRT4!NdrMesTypeEncode3` at `0x180019cdd`
- `RPCRT4!NdrMesTypeFree3` at `0x180019df1`
- `RPCRT4!NdrMesTypeFree3` at `0x180019df1`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019c04`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180019c04`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180019d47`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180019d47`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_SCardListReaders(
        struct _REDIR_LOCAL_SCARDCONTEXT *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        int a5)
{
  unsigned int SCardError; // ebx
  int v11; // esi
  unsigned int v12; // eax
  int v13; // eax
  handle_t pHandle; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-70h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-68h] BYREF
  char *pBuffer; // [rsp+58h] [rbp-60h] BYREF
  struct _BUFFER_LIST_STRUCT *v18; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int8 *v19[2]; // [rsp+68h] [rbp-50h] BYREF
  __int128 pObject; // [rsp+78h] [rbp-40h] BYREF
  __int128 v21; // [rsp+88h] [rbp-30h]
  __int64 v22; // [rsp+98h] [rbp-20h]
  unsigned int pEncodedSize; // [rsp+D8h] [rbp+20h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v18 = 0;
  pObject = 0;
  v21 = 0;
  v22 = 0;
  *(_OWORD *)v19 = 0;
  lpCriticalSection = 0;
  if ( !a4 )
    return 2148532228LL;
  if ( !MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    if ( a1 )
    {
      pObject = *(_OWORD *)((char *)a1 + 8);
      lpCriticalSection = *(LPCRITICAL_SECTION *)a1;
    }
    else
    {
      *((_QWORD *)&pObject + 1) = 0;
      LODWORD(pObject) = 0;
      v13 = RedirectionContextLookup((struct _REDIRECTION_CONTEXT **)&lpCriticalSection);
      if ( v13 )
        goto LABEL_10;
    }
    v11 = a5;
    if ( a5 )
      v12 = _CalculateNumBytesInMultiStringW(a2);
    else
      v12 = _CalculateNumBytesInMultiStringA((const char *)a2);
    LODWORD(v21) = v12;
    *((_QWORD *)&v21 + 1) = a2;
    LODWORD(v22) = a3 == 0;
    HIDWORD(v22) = *a4;
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0xBu, &pObject);
    v13 = _SendSCardIOCTL(
            v11 != 0 ? 589868 : 589864,
            pBuffer,
            pEncodedSize,
            &v18,
            lpCriticalSection,
            0xFFFFFFFF,
            0x800u);
    if ( !v13 )
    {
      SafeMesHandleFree(&pHandle);
      if ( !MesDecodeBufferHandleCreate(*((char **)v18 + 2), *((_DWORD *)v18 + 7), &pHandle) )
      {
        *(_OWORD *)v19 = 0;
        NdrMesTypeDecode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 2u, v19);
        SCardError = (unsigned int)v19[0];
        if ( !LODWORD(v19[0]) )
          SCardError = _CopyReturnToCallerBuffer(a1, v19[1], HIDWORD(v19[0]), a3, a4, (unsigned int)(v11 != 0) + 2);
        v15 = SCardError;
        NdrMesTypeFree3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 2u, v19);
        goto LABEL_17;
      }
      goto LABEL_4;
    }
LABEL_10:
    SCardError = _MakeSCardError(v13);
    goto LABEL_17;
  }
LABEL_4:
  SCardError = -2146435041;
LABEL_17:
  SafeMesHandleFree(&pHandle);
  MIDL_user_free(pBuffer);
  if ( v18 )
    *((_DWORD *)v18 + 2) = 0;
  if ( !a1 )
  {
    if ( lpCriticalSection )
      RedirectionContextRelease((struct _REDIRECTION_CONTEXT *)lpCriticalSection);
  }
  return SCardError;
}

```

## disassembly

```asm
0x180019b80  mov     r11, rsp
0x180019b83  mov     [r11+10h], rbx
0x180019b87  mov     [r11+18h], rsi
0x180019b8b  mov     [r11+8], rcx
0x180019b8f  push    rdi
0x180019b90  push    r14
0x180019b92  push    r15
0x180019b94  sub     rsp, 0A0h
0x180019b9b  mov     r14, r9
0x180019b9e  mov     r15, r8
0x180019ba1  mov     rbx, rdx
0x180019ba4  mov     rdi, rcx
0x180019ba7  mov     qword ptr [r11-60h], 0
0x180019baf  mov     dword ptr [r11+20h], 0
0x180019bb7  mov     qword ptr [r11-78h], 0
0x180019bbf  mov     qword ptr [r11-58h], 0
0x180019bc7  xorps   xmm0, xmm0
0x180019bca  xor     eax, eax
0x180019bcc  movups  [rsp+0B8h+var_40], xmm0
0x180019bd1  movups  xmmword ptr [r11-30h], xmm0
0x180019bd6  mov     [r11-20h], rax
0x180019bda  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x180019bdf  mov     [r11-68h], rax
0x180019be3  test    r9, r9
0x180019be6  jnz     short loc_180019BF2
0x180019be8  mov     eax, 80100004h
0x180019bed  jmp     loc_180019EE2
0x180019bf2  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x180019bf7  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x180019bff  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x180019c04  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180019c0a  test    eax, eax
0x180019c0c  jz      short loc_180019C18
0x180019c0e  mov     ebx, 8010001Fh
0x180019c13  jmp     loc_180019EA7
0x180019c18  test    rdi, rdi
0x180019c1b  jz      short loc_180019C54
0x180019c1d  mov     eax, [rdi+8]
0x180019c20  mov     dword ptr [rsp+0B8h+var_40], eax
0x180019c24  mov     eax, [rdi+0Ch]
0x180019c27  mov     dword ptr [rsp+0B8h+var_40+4], eax
0x180019c2b  mov     rax, [rdi+10h]
0x180019c2f  mov     qword ptr [rsp+0B8h+var_40+8], rax
0x180019c37  mov     rax, [rdi]
0x180019c3a  mov     [rsp+0B8h+lpCriticalSection], rax
0x180019c3f  mov     esi, [rsp+0B8h+arg_20]
0x180019c46  mov     rcx, rbx; char *
0x180019c49  test    esi, esi
0x180019c4b  jz      short loc_180019C84
0x180019c4d  call    ?_CalculateNumBytesInMultiStringW@@YAKPEBG@Z; _CalculateNumBytesInMultiStringW(ushort const *)
0x180019c52  jmp     short loc_180019C89
0x180019c54  mov     qword ptr [rsp+0B8h+var_40+8], 0
0x180019c60  mov     dword ptr [rsp+0B8h+var_40], 0
0x180019c68  lea     rcx, [rsp+0B8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT **
0x180019c6d  call    ?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextLookup(_REDIRECTION_CONTEXT * *)
0x180019c72  test    eax, eax
0x180019c74  jz      short loc_180019C3F
0x180019c76  mov     ecx, eax; int
0x180019c78  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180019c7d  mov     ebx, eax
0x180019c7f  jmp     loc_180019EA7
0x180019c84  call    ?_CalculateNumBytesInMultiStringA@@YAKPEBD@Z; _CalculateNumBytesInMultiStringA(char const *)
0x180019c89  mov     [rsp+0B8h+var_30], eax
0x180019c90  mov     [rsp+0B8h+var_28], rbx
0x180019c98  xor     eax, eax
0x180019c9a  test    r15, r15
0x180019c9d  setz    al
0x180019ca0  mov     [rsp+0B8h+var_20], eax
0x180019ca7  mov     eax, [r14]
0x180019caa  mov     [rsp+0B8h+var_1C], eax
0x180019cb1  lea     rax, [rsp+0B8h+var_40]
0x180019cb6  mov     [rsp+0B8h+pObject], rax; pObject
0x180019cbb  mov     [rsp+0B8h+nTypeIndex], 0Bh; nTypeIndex
0x180019cc3  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180019cca  lea     r8, pProxyInfo; pProxyInfo
0x180019cd1  lea     rdx, pPicklingInfo; pPicklingInfo
0x180019cd8  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180019cdd  call    cs:__imp_NdrMesTypeEncode3
0x180019ce3  nop
0x180019ce4  mov     eax, esi
0x180019ce6  neg     eax
0x180019ce8  sbb     ecx, ecx
0x180019cea  and     ecx, 4
0x180019ced  add     ecx, 90028h; IoControlCode
0x180019cf3  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x180019cfb  mov     dword ptr [rsp+0B8h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180019d03  mov     rax, [rsp+0B8h+lpCriticalSection]
0x180019d08  mov     qword ptr [rsp+0B8h+nTypeIndex], rax; lpCriticalSection
0x180019d0d  lea     r9, [rsp+0B8h+var_58]; struct _BUFFER_LIST_STRUCT **
0x180019d12  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x180019d1a  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x180019d1f  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180019d24  test    eax, eax
0x180019d26  jnz     loc_180019C76
0x180019d2c  lea     rcx, [rsp+0B8h+pHandle]; void **
0x180019d31  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180019d36  lea     r8, [rsp+0B8h+pHandle]; pHandle
0x180019d3b  mov     rcx, [rsp+0B8h+var_58]
0x180019d40  mov     edx, [rcx+1Ch]; BufferSize
0x180019d43  mov     rcx, [rcx+10h]; Buffer
0x180019d47  call    cs:__imp_MesDecodeBufferHandleCreate
0x180019d4d  test    eax, eax
0x180019d4f  jnz     loc_180019C0E
0x180019d55  xorps   xmm0, xmm0
0x180019d58  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x180019d5d  lea     rax, [rsp+0B8h+var_50]
0x180019d62  mov     [rsp+0B8h+pObject], rax; pObject
0x180019d67  mov     [rsp+0B8h+nTypeIndex], 2; nTypeIndex
0x180019d6f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180019d76  lea     r8, pProxyInfo; pProxyInfo
0x180019d7d  lea     rdx, pPicklingInfo; pPicklingInfo
0x180019d84  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180019d89  call    cs:__imp_NdrMesTypeDecode3
0x180019d8f  nop
0x180019d90  mov     ebx, dword ptr [rsp+0B8h+var_50]
0x180019d94  test    ebx, ebx
0x180019d96  jnz     short loc_180019DC1
0x180019d98  neg     esi
0x180019d9a  sbb     eax, eax
0x180019d9c  neg     eax
0x180019d9e  add     eax, 2
0x180019da1  mov     dword ptr [rsp+0B8h+pObject], eax; unsigned int
0x180019da5  mov     qword ptr [rsp+0B8h+nTypeIndex], r14; unsigned int *
0x180019daa  mov     r9, r15; unsigned __int8 *
0x180019dad  mov     r8d, dword ptr [rsp+0B8h+var_50+4]; unsigned int
0x180019db2  mov     rdx, [rsp+0B8h+var_50+8]; unsigned __int8 *
0x180019db7  mov     rcx, rdi; struct _REDIR_LOCAL_SCARDCONTEXT *
0x180019dba  call    ?_CopyReturnToCallerBuffer@@YAJPEAU_REDIR_LOCAL_SCARDCONTEXT@@PEAEK1PEAKK@Z; _CopyReturnToCallerBuffer(_REDIR_LOCAL_SCARDCONTEXT *,uchar *,ulong,uchar *,ulong *,ulong)
0x180019dbf  mov     ebx, eax
0x180019dc1  mov     [rsp+0B8h+var_70], ebx
0x180019dc5  lea     rax, [rsp+0B8h+var_50]
0x180019dca  mov     [rsp+0B8h+pObject], rax; pObject
0x180019dcf  mov     [rsp+0B8h+nTypeIndex], 2; nTypeIndex
0x180019dd7  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180019dde  lea     r8, pProxyInfo; pProxyInfo
0x180019de5  lea     rdx, pPicklingInfo; pPicklingInfo
0x180019dec  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x180019df1  call    cs:__imp_NdrMesTypeFree3
0x180019df7  jmp     loc_180019EA7
0x180019dfc  mov     rdi, [rsp+0B8h+arg_0]
0x180019e04  mov     ebx, [rsp+0B8h+var_70]
0x180019e08  jmp     loc_180019EA7
0x180019e0d  mov     ebx, eax
0x180019e0f  mov     edx, 2
0x180019e14  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019e19  lea     rax, WPP_GLOBAL_Control
0x180019e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e27  cmp     rcx, rax
0x180019e2a  jz      short loc_180019E51
0x180019e2c  test    byte ptr [rcx+1Ch], 8
0x180019e30  jz      short loc_180019E51
0x180019e32  cmp     byte ptr [rcx+19h], 2
0x180019e36  jb      short loc_180019E51
0x180019e38  mov     edx, 2Bh ; '+'
0x180019e3d  mov     [rsp+0B8h+nTypeIndex], ebx
0x180019e41  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180019e48  mov     rcx, [rcx+10h]
0x180019e4c  call    WPP_SF_sd
0x180019e51  mov     rdi, [rsp+0B8h+arg_0]
0x180019e59  jmp     short loc_180019EA7
0x180019e5b  mov     ebx, eax
0x180019e5d  mov     edx, 2
0x180019e62  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019e67  lea     rax, WPP_GLOBAL_Control
0x180019e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e75  cmp     rcx, rax
0x180019e78  jz      short loc_180019E9F
0x180019e7a  test    byte ptr [rcx+1Ch], 8
0x180019e7e  jz      short loc_180019E9F
0x180019e80  cmp     byte ptr [rcx+19h], 2
0x180019e84  jb      short loc_180019E9F
0x180019e86  mov     edx, 2Ah ; '*'
0x180019e8b  mov     [rsp+0B8h+nTypeIndex], ebx
0x180019e8f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180019e96  mov     rcx, [rcx+10h]
0x180019e9a  call    WPP_SF_sd
0x180019e9f  mov     rdi, [rsp+0B8h+arg_0]
0x180019ea7  lea     rcx, [rsp+0B8h+pHandle]; void **
0x180019eac  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x180019eb1  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x180019eb6  call    MIDL_user_free
0x180019ebb  mov     rax, [rsp+0B8h+var_58]
0x180019ec0  test    rax, rax
0x180019ec3  jz      short loc_180019ECC
0x180019ec5  mov     dword ptr [rax+8], 0
0x180019ecc  test    rdi, rdi
0x180019ecf  jnz     short loc_180019EE0
0x180019ed1  mov     rcx, [rsp+0B8h+lpCriticalSection]; struct _REDIRECTION_CONTEXT *
0x180019ed6  test    rcx, rcx
0x180019ed9  jz      short loc_180019EE0
0x180019edb  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x180019ee0  mov     eax, ebx
0x180019ee2  lea     r11, [rsp+0B8h+var_18]
0x180019eea  mov     rbx, [r11+28h]
0x180019eee  mov     rsi, [r11+30h]
0x180019ef2  mov     rsp, r11
0x180019ef5  pop     r15
0x180019ef7  pop     r14
0x180019ef9  pop     rdi
0x180019efa  retn
```

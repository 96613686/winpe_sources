# I_ContextCallWithLongReturn(unsigned __int64,ulong)

- ea: `0x180012a78`
- end: `0x180012c09`
- name: `?I_ContextCallWithLongReturn@@YAJ_KK@Z`
- size: `401`
- prototype: `int(unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180012990`
- `0x180015540`
- `0x180019acc`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000ff10`
- `0x180012878`
- `0x180012a78`
- `0x18001991c`
- `0x180019a14`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x180012b20`
- `RPCRT4!NdrMesTypeEncode3` at `0x180012b20`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180012ad3`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180012ad3`
- `RPCRT4!MesHandleFree` at `0x180012bcc`
- `RPCRT4!MesHandleFree` at `0x180012bcc`

## pseudocode

```c
__int64 __fastcall I_ContextCallWithLongReturn(__int64 a1, unsigned int a2)
{
  unsigned int v5; // edi
  int v6; // eax
  unsigned int SCardError; // eax
  struct _BUFFER_LIST_STRUCT *v8; // [rsp+40h] [rbp-28h] BYREF
  __int128 pObject; // [rsp+48h] [rbp-20h] BYREF
  unsigned int pEncodedSize; // [rsp+70h] [rbp+8h] BYREF
  handle_t pHandle; // [rsp+80h] [rbp+18h] BYREF
  char *pBuffer; // [rsp+88h] [rbp+20h] BYREF

  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  v8 = 0;
  pObject = 0;
  if ( !a1 )
    return 2148532228LL;
  if ( MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle) )
  {
    v5 = -2146435041;
  }
  else
  {
    pObject = *(_OWORD *)(a1 + 8);
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 3u, &pObject);
    v6 = _SendSCardIOCTL(a2, pBuffer, pEncodedSize, &v8, *(LPCRITICAL_SECTION *)a1, 0xFFFFFFFF, 0x800u);
    if ( v6 )
      SCardError = _MakeSCardError(v6);
    else
      SCardError = I_DecodeLongReturn(*((char **)v8 + 2), *((_DWORD *)v8 + 7));
    v5 = SCardError;
  }
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  MIDL_user_free(pBuffer);
  if ( v8 )
    *((_DWORD *)v8 + 2) = 0;
  return v5;
}

```

## disassembly

```asm
0x180012a78  mov     rax, rsp
0x180012a7b  mov     [rax+10h], rsi
0x180012a7f  push    rdi
0x180012a80  sub     rsp, 60h
0x180012a84  mov     esi, edx
0x180012a86  mov     rdi, rcx
0x180012a89  mov     qword ptr [rax+20h], 0
0x180012a91  mov     dword ptr [rax+8], 0
0x180012a98  mov     qword ptr [rax+18h], 0
0x180012aa0  mov     qword ptr [rax-28h], 0
0x180012aa8  xorps   xmm0, xmm0
0x180012aab  movups  xmmword ptr [rax-20h], xmm0
0x180012aaf  test    rcx, rcx
0x180012ab2  jnz     short loc_180012ABE
0x180012ab4  mov     eax, 80100004h
0x180012ab9  jmp     loc_180012BFE
0x180012abe  lea     r8, [rsp+68h+pHandle]; pHandle
0x180012ac6  lea     rdx, [rsp+68h+pEncodedSize]; pEncodedSize
0x180012acb  lea     rcx, [rsp+68h+pBuffer]; pBuffer
0x180012ad3  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180012ad9  test    eax, eax
0x180012adb  jz      short loc_180012AE7
0x180012add  mov     edi, 8010001Fh
0x180012ae2  jmp     loc_180012BBF
0x180012ae7  movups  xmm0, xmmword ptr [rdi+8]
0x180012aeb  movdqu  [rsp+68h+var_20], xmm0
0x180012af1  lea     rax, [rsp+68h+var_20]
0x180012af6  mov     [rsp+68h+pObject], rax; pObject
0x180012afb  mov     [rsp+68h+nTypeIndex], 3; nTypeIndex
0x180012b03  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180012b0a  lea     r8, pProxyInfo; pProxyInfo
0x180012b11  lea     rdx, pPicklingInfo; pPicklingInfo
0x180012b18  mov     rcx, [rsp+68h+pHandle]; Handle
0x180012b20  call    cs:__imp_NdrMesTypeEncode3
0x180012b26  nop
0x180012b27  mov     [rsp+68h+var_38], 800h; unsigned int
0x180012b2f  mov     dword ptr [rsp+68h+pObject], 0FFFFFFFFh; dwMilliseconds
0x180012b37  mov     rax, [rdi]
0x180012b3a  mov     qword ptr [rsp+68h+nTypeIndex], rax; lpCriticalSection
0x180012b3f  lea     r9, [rsp+68h+var_28]; struct _BUFFER_LIST_STRUCT **
0x180012b44  mov     r8d, [rsp+68h+pEncodedSize]; InputBufferLength
0x180012b49  mov     rdx, [rsp+68h+pBuffer]; InputBuffer
0x180012b51  mov     ecx, esi; IoControlCode
0x180012b53  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x180012b58  test    eax, eax
0x180012b5a  jz      short loc_180012B67
0x180012b5c  mov     ecx, eax; int
0x180012b5e  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x180012b63  mov     edi, eax
0x180012b65  jmp     short loc_180012BBF
0x180012b67  mov     rcx, [rsp+68h+var_28]
0x180012b6c  mov     edx, [rcx+1Ch]; unsigned int
0x180012b6f  mov     rcx, [rcx+10h]; unsigned __int8 *
0x180012b73  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x180012b78  jmp     short loc_180012B63
0x180012b7a  mov     edi, eax
0x180012b7c  mov     edx, 2
0x180012b81  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012b86  lea     rax, WPP_GLOBAL_Control
0x180012b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b94  cmp     rcx, rax
0x180012b97  jz      short loc_180012BBF
0x180012b99  test    byte ptr [rcx+1Ch], 8
0x180012b9d  jz      short loc_180012BBF
0x180012b9f  cmp     byte ptr [rcx+19h], 2
0x180012ba3  jb      short loc_180012BBF
0x180012ba5  mov     edx, 27h ; '''
0x180012baa  mov     [rsp+68h+nTypeIndex], edi
0x180012bae  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180012bb5  mov     rcx, [rcx+10h]
0x180012bb9  call    WPP_SF_sd
0x180012bbe  nop
0x180012bbf  mov     rcx, [rsp+68h+pHandle]; Handle
0x180012bc7  test    rcx, rcx
0x180012bca  jz      short loc_180012BDE
0x180012bcc  call    cs:__imp_MesHandleFree
0x180012bd2  mov     [rsp+68h+pHandle], 0
0x180012bde  mov     rcx, [rsp+68h+pBuffer]; void *
0x180012be6  call    MIDL_user_free
0x180012beb  mov     rax, [rsp+68h+var_28]
0x180012bf0  test    rax, rax
0x180012bf3  jz      short loc_180012BFC
0x180012bf5  mov     dword ptr [rax+8], 0
0x180012bfc  mov     eax, edi
0x180012bfe  mov     rsi, [rsp+68h+arg_8]
0x180012c03  add     rsp, 60h
0x180012c07  pop     rdi
0x180012c08  retn
```

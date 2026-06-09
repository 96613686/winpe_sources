# LsaIsoEncryptAsymmetricKeyBlob(_LSA_ISO_ASYMMETRIC_KEY_BLOB *,void * *,ulong *)

- ea: `0x140005820`
- end: `0x1400059d3`
- name: `?LsaIsoEncryptAsymmetricKeyBlob@@YAJPEAU_LSA_ISO_ASYMMETRIC_KEY_BLOB@@PEAPEAXPEAK@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004810`

## callees

- `0x140004ca8`
- `0x1400056f0`
- `0x140005820`
- `0x140006720`

## import_xrefs

- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x14000586e`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x14000586e`
- `RPCRT4!NdrMesTypeEncode3` at `0x1400058ee`
- `RPCRT4!NdrMesTypeEncode3` at `0x1400058ee`
- `RPCRT4!MesHandleFree` at `0x1400059c2`
- `RPCRT4!MesHandleFree` at `0x1400059c2`
- `RPCRT4!RpcExceptionFilter` at `0x140038ef0`
- `RPCRT4!RpcExceptionFilter` at `0x140038ef0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400058b5`
- `RPCRT4!I_RpcMapWin32Status` at `0x1400058b5`

## pseudocode

```c
__int64 __fastcall LsaIsoEncryptAsymmetricKeyBlob(struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *a1, void **a2, unsigned int *a3)
{
  RPC_STATUS v5; // edi
  unsigned int v6; // edi
  int v7; // eax
  void *v9; // [rsp+40h] [rbp-28h] BYREF
  handle_t Handle; // [rsp+48h] [rbp-20h] BYREF
  struct _LSA_ISO_ASYMMETRIC_KEY_BLOB *pObject; // [rsp+70h] [rbp+8h] BYREF
  void **v12; // [rsp+78h] [rbp+10h]
  unsigned int *v13; // [rsp+80h] [rbp+18h]
  unsigned int v14; // [rsp+88h] [rbp+20h] BYREF

  v13 = a3;
  v12 = a2;
  pObject = a1;
  Handle = 0;
  v9 = 0;
  v14 = 0;
  *a2 = 0;
  *a3 = 0;
  v5 = MesEncodeDynBufferHandleCreate((char **)&v9, &v14, &Handle);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids,
        (unsigned int)"LsaIsoEncryptAsymmetricKeyBlob",
        v5);
    v6 = I_RpcMapWin32Status(v5);
  }
  else
  {
    NdrMesTypeEncode3(
      Handle,
      &pPicklingInfo,
      &ProvIum::ProvIum_ProxyInfo,
      (const unsigned int **)&ArrTypeOffset,
      0,
      &pObject);
    v7 = LsaIsoEncrypt("LsaIsoAsymmetricKeyBlob", v9, v14, MIDLAllocWrapper, MIDLFreeWrapper, 1, a2, a3);
    v6 = v7;
    if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids,
        (unsigned int)"LsaIsoEncryptAsymmetricKeyBlob",
        v7);
  }
  if ( v9 )
    SafeAllocaFreeToHeap(v9);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x140005820  mov     rax, rsp
0x140005823  mov     [rax+18h], r8
0x140005827  mov     [rax+10h], rdx
0x14000582b  mov     [rax+8], rcx
0x14000582f  push    rsi
0x140005830  push    rdi
0x140005831  push    r14
0x140005833  sub     rsp, 50h
0x140005837  mov     rsi, r8
0x14000583a  mov     r14, rdx
0x14000583d  mov     qword ptr [rax-20h], 0
0x140005845  mov     qword ptr [rax-28h], 0
0x14000584d  mov     dword ptr [rax+20h], 0
0x140005854  mov     qword ptr [rdx], 0
0x14000585b  mov     dword ptr [r8], 0
0x140005862  lea     r8, [rax-20h]; pHandle
0x140005866  lea     rdx, [rax+20h]; pEncodedSize
0x14000586a  lea     rcx, [rax-28h]; pBuffer
0x14000586e  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x140005874  mov     edi, eax
0x140005876  test    eax, eax
0x140005878  jz      short loc_1400058C2
0x14000587a  lea     rdx, WPP_GLOBAL_Control
0x140005881  mov     rcx, cs:WPP_GLOBAL_Control
0x140005888  cmp     rcx, rdx
0x14000588b  jz      short loc_1400058B3
0x14000588d  test    byte ptr [rcx+1Ch], 1
0x140005891  jz      short loc_1400058B3
0x140005893  mov     edx, 11h
0x140005898  mov     [rsp+68h+nTypeIndex], edi
0x14000589c  lea     r9, aLsaisoencrypta; "LsaIsoEncryptAsymmetricKeyBlob"
0x1400058a3  lea     r8, WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids
0x1400058aa  mov     rcx, [rcx+10h]
0x1400058ae  call    WPP_SF_sd
0x1400058b3  mov     ecx, edi; Status
0x1400058b5  call    cs:__imp_I_RpcMapWin32Status
0x1400058bb  mov     edi, eax
0x1400058bd  jmp     loc_1400059A9
0x1400058c2  lea     rax, [rsp+68h+arg_0]
0x1400058c7  mov     [rsp+68h+pObject], rax; pObject
0x1400058cc  mov     [rsp+68h+nTypeIndex], 0; nTypeIndex
0x1400058d4  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1400058db  lea     r8, ?ProvIum_ProxyInfo@ProvIum@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1400058e2  lea     rdx, pPicklingInfo; pPicklingInfo
0x1400058e9  mov     rcx, [rsp+68h+Handle]; Handle
0x1400058ee  call    cs:__imp_NdrMesTypeEncode3
0x1400058f4  jmp     short loc_140005905
0x1400058f6  mov     edi, eax
0x1400058f8  mov     rsi, [rsp+68h+arg_10]
0x140005900  mov     r14, [rsp+68h+arg_8]
0x140005905  test    edi, edi
0x140005907  jz      short loc_14000592C
0x140005909  lea     rdx, WPP_GLOBAL_Control
0x140005910  mov     rcx, cs:WPP_GLOBAL_Control
0x140005917  cmp     rcx, rdx
0x14000591a  jz      short loc_1400058B3
0x14000591c  test    byte ptr [rcx+1Ch], 1
0x140005920  jz      short loc_1400058B3
0x140005922  mov     edx, 12h
0x140005927  jmp     loc_140005898
0x14000592c  mov     [rsp+68h+var_30], rsi
0x140005931  mov     [rsp+68h+var_38], r14
0x140005936  mov     dword ptr [rsp+68h+pObject], 1
0x14000593e  lea     rax, MIDLFreeWrapper
0x140005945  mov     qword ptr [rsp+68h+nTypeIndex], rax
0x14000594a  lea     r9, MIDLAllocWrapper
0x140005951  mov     r8d, [rsp+68h+arg_18]
0x140005959  mov     rdx, [rsp+68h+var_28]
0x14000595e  lea     rcx, aLsaisoasymmetr; "LsaIsoAsymmetricKeyBlob"
0x140005965  call    ?LsaIsoEncrypt@@YAJPEBDPEBXKP6APEAX_K@ZP6AXPEAX@ZW4LsaIsoCryptoPersistenceMode@@PEAPEAXPEAK@Z; LsaIsoEncrypt(char const *,void const *,ulong,void * (*)(unsigned __int64),void (*)(void *),LsaIsoCryptoPersistenceMode,void * *,ulong *)
0x14000596a  mov     edi, eax
0x14000596c  test    eax, eax
0x14000596e  jns     short loc_1400059A9
0x140005970  lea     rdx, WPP_GLOBAL_Control
0x140005977  mov     rcx, cs:WPP_GLOBAL_Control
0x14000597e  cmp     rcx, rdx
0x140005981  jz      short loc_1400059A9
0x140005983  test    byte ptr [rcx+1Ch], 1
0x140005987  jz      short loc_1400059A9
0x140005989  mov     edx, 13h
0x14000598e  mov     [rsp+68h+nTypeIndex], eax
0x140005992  lea     r9, aLsaisoencrypta; "LsaIsoEncryptAsymmetricKeyBlob"
0x140005999  lea     r8, WPP_217719c1ce6136db9a8b7dc58bf99136_Traceguids
0x1400059a0  mov     rcx, [rcx+10h]
0x1400059a4  call    WPP_SF_sd
0x1400059a9  mov     rcx, [rsp+68h+var_28]; void *
0x1400059ae  test    rcx, rcx
0x1400059b1  jz      short loc_1400059B8
0x1400059b3  call    SafeAllocaFreeToHeap
0x1400059b8  mov     rcx, [rsp+68h+Handle]; Handle
0x1400059bd  test    rcx, rcx
0x1400059c0  jz      short loc_1400059C8
0x1400059c2  call    cs:__imp_MesHandleFree
0x1400059c8  mov     eax, edi
0x1400059ca  add     rsp, 50h
0x1400059ce  pop     r14
0x1400059d0  pop     rdi
0x1400059d1  pop     rsi
0x1400059d2  retn
0x140038ee2  push    rbp
0x140038ee4  sub     rsp, 40h
0x140038ee8  mov     rbp, rdx
0x140038eeb  mov     rcx, [rcx]
0x140038eee  mov     ecx, [rcx]; ExceptionCode
0x140038ef0  call    cs:__imp_RpcExceptionFilter
0x140038ef6  nop
0x140038ef7  add     rsp, 40h
0x140038efb  pop     rbp
0x140038efc  retn
```

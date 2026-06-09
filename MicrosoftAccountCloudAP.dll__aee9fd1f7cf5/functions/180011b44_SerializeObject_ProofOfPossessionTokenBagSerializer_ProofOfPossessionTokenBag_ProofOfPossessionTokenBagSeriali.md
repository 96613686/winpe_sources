# SerializeObject<ProofOfPossessionTokenBagSerializer,_ProofOfPossessionTokenBag>(ProofOfPossessionTokenBagSerializer &,_ProofOfPossessionTokenBag &,uchar * *,ulong *)

- ea: `0x180011b44`
- end: `0x180011f20`
- name: `??$SerializeObject@VProofOfPossessionTokenBagSerializer@@U_ProofOfPossessionTokenBag@@@@YAJAEAVProofOfPossessionTokenBagSerializer@@AEAU_ProofOfPossessionTokenBag@@PEAPEAEPEAK@Z`
- size: `988`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *, void *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013478`

## callees

- `0x180003160`
- `0x180007eb8`
- `0x18000f408`
- `0x18000fa14`
- `0x18000fcf4`
- `0x180010040`
- `0x180011b44`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x180011d89`
- `RPCRT4!NdrMesTypeEncode3` at `0x180011d89`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180011c5e`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180011c5e`

## string_xrefs

- `0x180011ee6`: `SerializeObject() completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SerializeObject<ProofOfPossessionTokenBagSerializer,_ProofOfPossessionTokenBag>(
        WlidPropertyBagSerializer *a1,
        void *a2,
        _QWORD *a3,
        _DWORD *a4)
{
  _BYTE *v5; // r15
  void *v6; // r14
  unsigned int v7; // r12d
  struct IRPCFunctions *RPCFunctions; // rax
  int v9; // eax
  signed int v10; // edi
  unsigned __int8 v11; // bl
  unsigned int v12; // eax
  unsigned int v13; // ecx
  _BYTE *v14; // rax
  struct IRPCFunctions *v15; // rax
  void *v16; // rax
  errno_t v17; // eax
  __int64 v18; // rax
  __int64 v19; // rcx
  _BYTE *v20; // rax
  unsigned int v21; // r8d
  void **nTypeIndex; // [rsp+20h] [rbp-C8h]
  _DWORD SourceSize[3]; // [rsp+44h] [rbp-A4h] BYREF
  handle_t Handle; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-90h]
  void *Source; // [rsp+60h] [rbp-88h] BYREF
  void *pObject; // [rsp+68h] [rbp-80h]
  void *v29; // [rsp+70h] [rbp-78h]
  _QWORD *v30; // [rsp+78h] [rbp-70h]
  __int64 v31; // [rsp+80h] [rbp-68h]
  WlidPropertyBagSerializer *v32; // [rsp+88h] [rbp-60h]
  __int128 v33; // [rsp+90h] [rbp-58h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+E8h] [rbp+0h] BYREF

  v30 = a3;
  pObject = a2;
  *(_QWORD *)&SourceSize[1] = a1;
  v32 = a1;
  Source = 0;
  v5 = 0;
  v29 = 0;
  v6 = 0;
  v31 = 0;
  v33 = 0;
  v34 = 0;
  SourceSize[0] = 0;
  v7 = 0;
  v26 = 0;
  Handle = 0;
  if ( !a3 || !a4 )
  {
    v10 = -2147024809;
    goto LABEL_21;
  }
  *a3 = 0;
  *a4 = 0;
  RPCFunctions = WlidPropertyBagSerializer::GetRPCFunctions(a1);
  v9 = (*(__int64 (__fastcall **)(struct IRPCFunctions *, __int128 *, _QWORD, _DWORD *, handle_t *))(*(_QWORD *)RPCFunctions + 8LL))(
         RPCFunctions,
         &v33,
         ((unsigned int)&retaddr - 64 - (unsigned int)&v33) & 0xFFFFFFF8,
         SourceSize,
         &Handle);
  if ( v9 )
  {
LABEL_4:
    v10 = HandleRpcError(v9);
    v11 = 2;
    a1 = *(WlidPropertyBagSerializer **)&SourceSize[1];
    goto LABEL_22;
  }
  v12 = NdrMesTypeAlignSize3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, pObject);
  v13 = v12 + 16;
  v7 = -1;
  if ( v12 + 16 >= v12 )
    v7 = v12 + 16;
  v26 = v7;
  v10 = v13 < v12 ? 0x80070216 : 0;
  if ( v13 < v12 )
  {
    LODWORD(nTypeIndex) = v13 < v12 ? 0x80070216 : 0;
    v11 = 2;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
      0x9Bu,
      L"ULongAdd hr = 0x%x.",
      nTypeIndex);
    v10 = -2147024809;
    a1 = *(WlidPropertyBagSerializer **)&SourceSize[1];
    goto LABEL_22;
  }
  v14 = LiveAllocate(v7);
  v5 = v14;
  v29 = v14;
  if ( !v14 )
  {
    v10 = -2147024882;
    v11 = 2;
    a1 = *(WlidPropertyBagSerializer **)&SourceSize[1];
    goto LABEL_22;
  }
  Source = (void *)((unsigned __int64)(v14 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  v15 = WlidPropertyBagSerializer::GetRPCFunctions(*(WlidPropertyBagSerializer **)&SourceSize[1]);
  nTypeIndex = &Source;
  v9 = (*(__int64 (__fastcall **)(struct IRPCFunctions *, handle_t, __int64))(*(_QWORD *)v15 + 16LL))(v15, Handle, 1);
  if ( v9 )
    goto LABEL_4;
  NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, pObject);
  v6 = Source;
  if ( Source == v5 )
  {
    v5 = 0;
LABEL_19:
    *v30 = v6;
    *a4 = SourceSize[0];
    Source = 0;
    v6 = 0;
    goto LABEL_15;
  }
  v16 = LiveAllocate(SourceSize[0]);
  v6 = v16;
  if ( v16 )
  {
    v17 = memcpy_s_0(v16, SourceSize[0], Source, SourceSize[0]);
    v10 = v17 != 0 ? 0x8000FFFF : 0;
    if ( v17 )
      goto LABEL_15;
    goto LABEL_19;
  }
  v10 = -2147024882;
LABEL_15:
  a1 = *(WlidPropertyBagSerializer **)&SourceSize[1];
LABEL_21:
  v11 = 2;
LABEL_22:
  if ( Handle )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 16LL))(*(_QWORD *)a1);
    (*(void (__fastcall **)(__int64, handle_t))(*(_QWORD *)v18 + 24LL))(v18, Handle);
  }
  if ( v5 )
  {
    v19 = v7;
    v20 = v5;
    if ( v7 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LiveFree(v5);
  }
  if ( v6 )
    LiveFree(v6);
  if ( v10 >= 0 )
  {
    v11 = 5;
    v21 = 242;
  }
  else
  {
    v21 = 238;
  }
  LODWORD(nTypeIndex) = v10;
  TracePrintW(
    v11,
    "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
    v21,
    L"SerializeObject() completed with hr = 0x%x.",
    nTypeIndex);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011b44  mov     r11, rsp
0x180011b47  push    rbx
0x180011b48  push    rdi
0x180011b49  push    r12
0x180011b4b  push    r13
0x180011b4d  push    r14
0x180011b4f  push    r15
0x180011b51  sub     rsp, 0B8h
0x180011b58  mov     rax, cs:__security_cookie
0x180011b5f  xor     rax, rsp
0x180011b62  mov     [rsp+0E8h+var_40], rax
0x180011b6a  mov     r13, r9
0x180011b6d  mov     [rsp+0E8h+var_70], r8
0x180011b72  mov     [rsp+0E8h+var_80], rdx
0x180011b77  mov     qword ptr [rsp+0E8h+SourceSize+4], rcx
0x180011b7c  mov     [rsp+0E8h+var_60], rcx
0x180011b84  mov     [rsp+0E8h+Source], 0
0x180011b8d  xor     r15d, r15d
0x180011b90  mov     [r11-78h], r15
0x180011b94  xor     r14d, r14d
0x180011b97  mov     [rsp+0E8h+var_68], r14
0x180011b9f  xorps   xmm0, xmm0
0x180011ba2  xor     edx, edx
0x180011ba4  movups  xmmword ptr [r11-58h], xmm0
0x180011ba9  mov     [r11-48h], rdx
0x180011bad  mov     dword ptr [rsp+0E8h+SourceSize], edx
0x180011bb1  xor     r12d, r12d
0x180011bb4  mov     [rsp+0E8h+var_90], r12d
0x180011bb9  mov     [rsp+0E8h+Handle], rdx
0x180011bbe  test    r8, r8
0x180011bc1  jz      loc_180011E65
0x180011bc7  test    r9, r9
0x180011bca  jz      loc_180011E65
0x180011bd0  mov     [r8], rdx
0x180011bd3  mov     [r9], edx
0x180011bd6  lea     rdi, [r11-51h]
0x180011bda  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180011bde  lea     rbx, [r11-40h]
0x180011be2  sub     ebx, edi
0x180011be4  and     ebx, 0FFFFFFF8h
0x180011be7  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180011bec  mov     r10, rax
0x180011bef  mov     rcx, [rax]
0x180011bf2  mov     rax, [rcx+8]
0x180011bf6  lea     rcx, [rsp+0E8h+Handle]
0x180011bfb  mov     qword ptr [rsp+0E8h+nTypeIndex], rcx
0x180011c00  lea     r9, [rsp+0E8h+SourceSize]
0x180011c05  mov     r8d, ebx
0x180011c08  mov     rdx, rdi
0x180011c0b  mov     rcx, r10
0x180011c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c13  test    eax, eax
0x180011c15  jz      short loc_180011C32
0x180011c17  mov     ecx, eax; int
0x180011c19  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180011c1e  mov     edi, eax
0x180011c20  mov     [rsp+0E8h+var_A8], eax
0x180011c24  lea     ebx, [r15+2]
0x180011c28  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180011c2d  jmp     loc_180011E6F
0x180011c32  mov     rax, [rsp+0E8h+var_80]
0x180011c37  mov     [rsp+0E8h+pObject], rax; pObject
0x180011c3c  mov     [rsp+0E8h+nTypeIndex], 1; nTypeIndex
0x180011c44  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180011c4b  lea     r8, pProxyInfo; pProxyInfo
0x180011c52  lea     rdx, pPicklingInfo; pPicklingInfo
0x180011c59  mov     rcx, [rsp+0E8h+Handle]; Handle
0x180011c5e  call    cs:__imp_NdrMesTypeAlignSize3
0x180011c64  lea     ecx, [rax+10h]
0x180011c67  or      r12d, 0FFFFFFFFh
0x180011c6b  cmp     ecx, eax
0x180011c6d  cmovnb  r12d, ecx
0x180011c71  mov     [rsp+0E8h+var_90], r12d
0x180011c76  sbb     edi, edi
0x180011c78  and     edi, 80070216h
0x180011c7e  mov     [rsp+0E8h+var_A8], edi
0x180011c82  cmp     ecx, eax
0x180011c84  jnb     short loc_180011CBD
0x180011c86  mov     [rsp+0E8h+nTypeIndex], edi
0x180011c8a  lea     r9, aUlongaddHr0xX; "ULongAdd hr = 0x%x."
0x180011c91  mov     r8d, 9Bh; unsigned int
0x180011c97  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011c9e  mov     ebx, 2
0x180011ca3  mov     ecx, ebx; unsigned __int8
0x180011ca5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011caa  mov     edi, 80070057h
0x180011caf  mov     [rsp+0E8h+var_A8], edi
0x180011cb3  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180011cb8  jmp     loc_180011E6F
0x180011cbd  mov     ecx, r12d; unsigned __int64
0x180011cc0  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x180011cc5  mov     r15, rax
0x180011cc8  mov     [rsp+0E8h+var_78], rax
0x180011ccd  test    rax, rax
0x180011cd0  jnz     short loc_180011CE8
0x180011cd2  mov     edi, 8007000Eh
0x180011cd7  mov     [rsp+0E8h+var_A8], edi
0x180011cdb  lea     ebx, [rax+2]
0x180011cde  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180011ce3  jmp     loc_180011E6F
0x180011ce8  lea     rcx, [rax+7]
0x180011cec  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180011cf0  mov     [rsp+0E8h+Source], rcx
0x180011cf5  mov     ebx, r15d
0x180011cf8  sub     ebx, ecx
0x180011cfa  add     ebx, r12d
0x180011cfd  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]; this
0x180011d02  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180011d07  mov     r10, rax
0x180011d0a  mov     rcx, [rax]
0x180011d0d  mov     rax, [rcx+10h]
0x180011d11  lea     rcx, [rsp+0E8h+SourceSize]
0x180011d16  mov     [rsp+0E8h+var_B8], rcx
0x180011d1b  mov     dword ptr [rsp+0E8h+pObject], ebx
0x180011d1f  lea     rcx, [rsp+0E8h+Source]
0x180011d24  mov     qword ptr [rsp+0E8h+nTypeIndex], rcx
0x180011d29  xor     r9d, r9d
0x180011d2c  lea     r8d, [r9+1]
0x180011d30  mov     rdx, [rsp+0E8h+Handle]
0x180011d35  mov     rcx, r10
0x180011d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3d  test    eax, eax
0x180011d3f  jz      short loc_180011D5D
0x180011d41  mov     ecx, eax; int
0x180011d43  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180011d48  mov     edi, eax
0x180011d4a  mov     [rsp+0E8h+var_A8], eax
0x180011d4e  mov     ebx, 2
0x180011d53  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180011d58  jmp     loc_180011E6F
0x180011d5d  mov     rax, [rsp+0E8h+var_80]
0x180011d62  mov     [rsp+0E8h+pObject], rax; pObject
0x180011d67  mov     [rsp+0E8h+nTypeIndex], 1; nTypeIndex
0x180011d6f  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180011d76  lea     r8, pProxyInfo; pProxyInfo
0x180011d7d  lea     rdx, pPicklingInfo; pPicklingInfo
0x180011d84  mov     rcx, [rsp+0E8h+Handle]; Handle
0x180011d89  call    cs:__imp_NdrMesTypeEncode3
0x180011d8f  nop
0x180011d90  mov     r14, [rsp+0E8h+Source]
0x180011d95  cmp     r14, r15
0x180011d98  jz      short loc_180011DE0
0x180011d9a  mov     ecx, dword ptr [rsp+0E8h+SourceSize]; unsigned __int64
0x180011d9e  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x180011da3  mov     r14, rax
0x180011da6  test    rax, rax
0x180011da9  jnz     short loc_180011DBA
0x180011dab  mov     edi, 8007000Eh
0x180011db0  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180011db5  jmp     loc_180011E6A
0x180011dba  mov     edx, dword ptr [rsp+0E8h+SourceSize]; DestinationSize
0x180011dbe  mov     r9d, edx; SourceSize
0x180011dc1  mov     r8, [rsp+0E8h+Source]; Source
0x180011dc6  mov     rcx, rax; Destination
0x180011dc9  call    memcpy_s_0
0x180011dce  mov     ecx, eax
0x180011dd0  neg     ecx
0x180011dd2  sbb     edi, edi
0x180011dd4  and     edi, 8000FFFFh
0x180011dda  test    eax, eax
0x180011ddc  jz      short loc_180011DE3
0x180011dde  jmp     short loc_180011DB0
0x180011de0  xor     r15d, r15d
0x180011de3  mov     rax, [rsp+0E8h+var_70]
0x180011de8  mov     [rax], r14
0x180011deb  mov     eax, dword ptr [rsp+0E8h+SourceSize]
0x180011def  mov     [r13+0], eax
0x180011df3  mov     [rsp+0E8h+Source], 0
0x180011dfc  xor     r14d, r14d
0x180011dff  jmp     short loc_180011DB0
0x180011e01  mov     edi, eax
0x180011e03  test    eax, eax
0x180011e05  jle     short loc_180011E10
0x180011e07  movzx   edi, ax
0x180011e0a  or      edi, 80070000h
0x180011e10  mov     [rsp+0E8h+var_A8], edi
0x180011e14  mov     [rsp+0E8h+nTypeIndex], edi
0x180011e18  lea     r9, aRpcexceptionco; "RpcExceptionCode hr = 0x%x."
0x180011e1f  mov     r8d, 0BBh; unsigned int
0x180011e25  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011e2c  mov     ecx, 2; unsigned __int8
0x180011e31  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011e36  mov     eax, 8000FFFFh
0x180011e3b  test    edi, edi
0x180011e3d  cmovns  edi, eax
0x180011e40  mov     [rsp+0E8h+var_A8], edi
0x180011e44  mov     ebx, 2
0x180011e49  mov     r15, [rsp+0E8h+var_78]
0x180011e4e  mov     r14, [rsp+0E8h+var_68]
0x180011e56  mov     r12d, [rsp+0E8h+var_90]
0x180011e5b  mov     rcx, [rsp+0E8h+var_60]
0x180011e63  jmp     short loc_180011E6F
0x180011e65  mov     edi, 80070057h
0x180011e6a  mov     ebx, 2
0x180011e6f  cmp     [rsp+0E8h+Handle], 0
0x180011e75  jz      short loc_180011E9D
0x180011e77  mov     rcx, [rcx]
0x180011e7a  mov     rax, [rcx]
0x180011e7d  mov     rax, [rax+10h]
0x180011e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e86  mov     r8, rax
0x180011e89  mov     rcx, [rax]
0x180011e8c  mov     rax, [rcx+18h]
0x180011e90  mov     rdx, [rsp+0E8h+Handle]
0x180011e95  mov     rcx, r8
0x180011e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e9d  test    r15, r15
0x180011ea0  jz      short loc_180011EC1
0x180011ea2  mov     ecx, r12d
0x180011ea5  mov     rax, r15
0x180011ea8  test    r12d, r12d
0x180011eab  jz      short loc_180011EB9
0x180011ead  mov     byte ptr [rax], 0
0x180011eb0  inc     rax
0x180011eb3  sub     rcx, 1
0x180011eb7  jnz     short loc_180011EAD
0x180011eb9  mov     rcx, r15; void *
0x180011ebc  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180011ec1  test    r14, r14
0x180011ec4  jz      short loc_180011ECE
0x180011ec6  mov     rcx, r14; void *
0x180011ec9  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180011ece  test    edi, edi
0x180011ed0  jns     short loc_180011EDA
0x180011ed2  mov     r8d, 0EEh
0x180011ed8  jmp     short loc_180011EE2
0x180011eda  mov     bl, 5
0x180011edc  mov     r8d, 0F2h; unsigned int
0x180011ee2  mov     [rsp+0E8h+nTypeIndex], edi
0x180011ee6  lea     r9, aSerializeobjec; "SerializeObject() completed with hr = 0"...
0x180011eed  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011ef4  movzx   ecx, bl; unsigned __int8
0x180011ef7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011efc  mov     eax, edi
0x180011efe  mov     rcx, [rsp+0E8h+var_40]
0x180011f06  xor     rcx, rsp; StackCookie
0x180011f09  call    __security_check_cookie
0x180011f0e  add     rsp, 0B8h
0x180011f15  pop     r15
0x180011f17  pop     r14
0x180011f19  pop     r13
0x180011f1b  pop     r12
0x180011f1d  pop     rdi
0x180011f1e  pop     rbx
0x180011f1f  retn
0x180030a74  push    rbp
0x180030a76  sub     rsp, 40h
0x180030a7a  mov     rbp, rdx
0x180030a7d  mov     rcx, [rcx]
0x180030a80  mov     ecx, [rcx]; unsigned int
0x180030a82  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x180030a87  nop
0x180030a88  add     rsp, 40h
0x180030a8c  pop     rbp
0x180030a8d  retn
```

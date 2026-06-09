# SerializeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(WLIDCredentialBagSerializer &,_WLIDCredentialBag &,uchar * *,ulong *)

- ea: `0x180023778`
- end: `0x180023b54`
- name: `??$SerializeObject@VWLIDCredentialBagSerializer@@U_WLIDCredentialBag@@@@YAJAEAVWLIDCredentialBagSerializer@@AEAU_WLIDCredentialBag@@PEAPEAEPEAK@Z`
- size: `988`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *, void *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800244b0`

## callees

- `0x180003160`
- `0x180007eb8`
- `0x18000f408`
- `0x18000fa14`
- `0x18000fcf4`
- `0x180010040`
- `0x180023778`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x1800239bd`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800239bd`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180023892`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180023892`

## string_xrefs

- `0x180023b1a`: `SerializeObject() completed with hr = 0x%x.`

## pseudocode

```c
__int64 __fastcall SerializeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(
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
  v12 = NdrMesTypeAlignSize3(
          Handle,
          &stru_18003F728,
          &stru_180037AE0,
          (const unsigned int **)&off_18004D0D8,
          0,
          pObject);
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
  NdrMesTypeEncode3(Handle, &stru_18003F728, &stru_180037AE0, (const unsigned int **)&off_18004D0D8, 0, pObject);
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
0x180023778  mov     r11, rsp
0x18002377b  push    rbx
0x18002377c  push    rdi
0x18002377d  push    r12
0x18002377f  push    r13
0x180023781  push    r14
0x180023783  push    r15
0x180023785  sub     rsp, 0B8h
0x18002378c  mov     rax, cs:__security_cookie
0x180023793  xor     rax, rsp
0x180023796  mov     [rsp+0E8h+var_40], rax
0x18002379e  mov     r13, r9
0x1800237a1  mov     [rsp+0E8h+var_70], r8
0x1800237a6  mov     [rsp+0E8h+var_80], rdx
0x1800237ab  mov     qword ptr [rsp+0E8h+SourceSize+4], rcx
0x1800237b0  mov     [rsp+0E8h+var_60], rcx
0x1800237b8  mov     [rsp+0E8h+Source], 0
0x1800237c1  xor     r15d, r15d
0x1800237c4  mov     [r11-78h], r15
0x1800237c8  xor     r14d, r14d
0x1800237cb  mov     [rsp+0E8h+var_68], r14
0x1800237d3  xorps   xmm0, xmm0
0x1800237d6  xor     edx, edx
0x1800237d8  movups  xmmword ptr [r11-58h], xmm0
0x1800237dd  mov     [r11-48h], rdx
0x1800237e1  mov     dword ptr [rsp+0E8h+SourceSize], edx
0x1800237e5  xor     r12d, r12d
0x1800237e8  mov     [rsp+0E8h+var_90], r12d
0x1800237ed  mov     [rsp+0E8h+Handle], rdx
0x1800237f2  test    r8, r8
0x1800237f5  jz      loc_180023A99
0x1800237fb  test    r9, r9
0x1800237fe  jz      loc_180023A99
0x180023804  mov     [r8], rdx
0x180023807  mov     [r9], edx
0x18002380a  lea     rdi, [r11-51h]
0x18002380e  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180023812  lea     rbx, [r11-40h]
0x180023816  sub     ebx, edi
0x180023818  and     ebx, 0FFFFFFF8h
0x18002381b  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180023820  mov     r10, rax
0x180023823  mov     rcx, [rax]
0x180023826  mov     rax, [rcx+8]
0x18002382a  lea     rcx, [rsp+0E8h+Handle]
0x18002382f  mov     qword ptr [rsp+0E8h+nTypeIndex], rcx
0x180023834  lea     r9, [rsp+0E8h+SourceSize]
0x180023839  mov     r8d, ebx
0x18002383c  mov     rdx, rdi
0x18002383f  mov     rcx, r10
0x180023842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023847  test    eax, eax
0x180023849  jz      short loc_180023866
0x18002384b  mov     ecx, eax; int
0x18002384d  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180023852  mov     edi, eax
0x180023854  mov     [rsp+0E8h+var_A8], eax
0x180023858  lea     ebx, [r15+2]
0x18002385c  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180023861  jmp     loc_180023AA3
0x180023866  mov     rax, [rsp+0E8h+var_80]
0x18002386b  mov     [rsp+0E8h+pObject], rax; pObject
0x180023870  mov     [rsp+0E8h+nTypeIndex], 0; nTypeIndex
0x180023878  lea     r9, off_18004D0D8; ArrTypeOffset
0x18002387f  lea     r8, stru_180037AE0; pProxyInfo
0x180023886  lea     rdx, stru_18003F728; pPicklingInfo
0x18002388d  mov     rcx, [rsp+0E8h+Handle]; Handle
0x180023892  call    cs:__imp_NdrMesTypeAlignSize3
0x180023898  lea     ecx, [rax+10h]
0x18002389b  or      r12d, 0FFFFFFFFh
0x18002389f  cmp     ecx, eax
0x1800238a1  cmovnb  r12d, ecx
0x1800238a5  mov     [rsp+0E8h+var_90], r12d
0x1800238aa  sbb     edi, edi
0x1800238ac  and     edi, 80070216h
0x1800238b2  mov     [rsp+0E8h+var_A8], edi
0x1800238b6  cmp     ecx, eax
0x1800238b8  jnb     short loc_1800238F1
0x1800238ba  mov     [rsp+0E8h+nTypeIndex], edi
0x1800238be  lea     r9, aUlongaddHr0xX; "ULongAdd hr = 0x%x."
0x1800238c5  mov     r8d, 9Bh; unsigned int
0x1800238cb  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800238d2  mov     ebx, 2
0x1800238d7  mov     ecx, ebx; unsigned __int8
0x1800238d9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800238de  mov     edi, 80070057h
0x1800238e3  mov     [rsp+0E8h+var_A8], edi
0x1800238e7  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x1800238ec  jmp     loc_180023AA3
0x1800238f1  mov     ecx, r12d; unsigned __int64
0x1800238f4  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x1800238f9  mov     r15, rax
0x1800238fc  mov     [rsp+0E8h+var_78], rax
0x180023901  test    rax, rax
0x180023904  jnz     short loc_18002391C
0x180023906  mov     edi, 8007000Eh
0x18002390b  mov     [rsp+0E8h+var_A8], edi
0x18002390f  lea     ebx, [rax+2]
0x180023912  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x180023917  jmp     loc_180023AA3
0x18002391c  lea     rcx, [rax+7]
0x180023920  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180023924  mov     [rsp+0E8h+Source], rcx
0x180023929  mov     ebx, r15d
0x18002392c  sub     ebx, ecx
0x18002392e  add     ebx, r12d
0x180023931  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]; this
0x180023936  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x18002393b  mov     r10, rax
0x18002393e  mov     rcx, [rax]
0x180023941  mov     rax, [rcx+10h]
0x180023945  lea     rcx, [rsp+0E8h+SourceSize]
0x18002394a  mov     [rsp+0E8h+var_B8], rcx
0x18002394f  mov     dword ptr [rsp+0E8h+pObject], ebx
0x180023953  lea     rcx, [rsp+0E8h+Source]
0x180023958  mov     qword ptr [rsp+0E8h+nTypeIndex], rcx
0x18002395d  xor     r9d, r9d
0x180023960  lea     r8d, [r9+1]
0x180023964  mov     rdx, [rsp+0E8h+Handle]
0x180023969  mov     rcx, r10
0x18002396c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023971  test    eax, eax
0x180023973  jz      short loc_180023991
0x180023975  mov     ecx, eax; int
0x180023977  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x18002397c  mov     edi, eax
0x18002397e  mov     [rsp+0E8h+var_A8], eax
0x180023982  mov     ebx, 2
0x180023987  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x18002398c  jmp     loc_180023AA3
0x180023991  mov     rax, [rsp+0E8h+var_80]
0x180023996  mov     [rsp+0E8h+pObject], rax; pObject
0x18002399b  mov     [rsp+0E8h+nTypeIndex], 0; nTypeIndex
0x1800239a3  lea     r9, off_18004D0D8; ArrTypeOffset
0x1800239aa  lea     r8, stru_180037AE0; pProxyInfo
0x1800239b1  lea     rdx, stru_18003F728; pPicklingInfo
0x1800239b8  mov     rcx, [rsp+0E8h+Handle]; Handle
0x1800239bd  call    cs:__imp_NdrMesTypeEncode3
0x1800239c3  nop
0x1800239c4  mov     r14, [rsp+0E8h+Source]
0x1800239c9  cmp     r14, r15
0x1800239cc  jz      short loc_180023A14
0x1800239ce  mov     ecx, dword ptr [rsp+0E8h+SourceSize]; unsigned __int64
0x1800239d2  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x1800239d7  mov     r14, rax
0x1800239da  test    rax, rax
0x1800239dd  jnz     short loc_1800239EE
0x1800239df  mov     edi, 8007000Eh
0x1800239e4  mov     rcx, qword ptr [rsp+0E8h+SourceSize+4]
0x1800239e9  jmp     loc_180023A9E
0x1800239ee  mov     edx, dword ptr [rsp+0E8h+SourceSize]; DestinationSize
0x1800239f2  mov     r9d, edx; SourceSize
0x1800239f5  mov     r8, [rsp+0E8h+Source]; Source
0x1800239fa  mov     rcx, rax; Destination
0x1800239fd  call    memcpy_s_0
0x180023a02  mov     ecx, eax
0x180023a04  neg     ecx
0x180023a06  sbb     edi, edi
0x180023a08  and     edi, 8000FFFFh
0x180023a0e  test    eax, eax
0x180023a10  jz      short loc_180023A17
0x180023a12  jmp     short loc_1800239E4
0x180023a14  xor     r15d, r15d
0x180023a17  mov     rax, [rsp+0E8h+var_70]
0x180023a1c  mov     [rax], r14
0x180023a1f  mov     eax, dword ptr [rsp+0E8h+SourceSize]
0x180023a23  mov     [r13+0], eax
0x180023a27  mov     [rsp+0E8h+Source], 0
0x180023a30  xor     r14d, r14d
0x180023a33  jmp     short loc_1800239E4
0x180023a35  mov     edi, eax
0x180023a37  test    eax, eax
0x180023a39  jle     short loc_180023A44
0x180023a3b  movzx   edi, ax
0x180023a3e  or      edi, 80070000h
0x180023a44  mov     [rsp+0E8h+var_A8], edi
0x180023a48  mov     [rsp+0E8h+nTypeIndex], edi
0x180023a4c  lea     r9, aRpcexceptionco; "RpcExceptionCode hr = 0x%x."
0x180023a53  mov     r8d, 0BBh; unsigned int
0x180023a59  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180023a60  mov     ecx, 2; unsigned __int8
0x180023a65  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023a6a  mov     eax, 8000FFFFh
0x180023a6f  test    edi, edi
0x180023a71  cmovns  edi, eax
0x180023a74  mov     [rsp+0E8h+var_A8], edi
0x180023a78  mov     ebx, 2
0x180023a7d  mov     r15, [rsp+0E8h+var_78]
0x180023a82  mov     r14, [rsp+0E8h+var_68]
0x180023a8a  mov     r12d, [rsp+0E8h+var_90]
0x180023a8f  mov     rcx, [rsp+0E8h+var_60]
0x180023a97  jmp     short loc_180023AA3
0x180023a99  mov     edi, 80070057h
0x180023a9e  mov     ebx, 2
0x180023aa3  cmp     [rsp+0E8h+Handle], 0
0x180023aa9  jz      short loc_180023AD1
0x180023aab  mov     rcx, [rcx]
0x180023aae  mov     rax, [rcx]
0x180023ab1  mov     rax, [rax+10h]
0x180023ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023aba  mov     r8, rax
0x180023abd  mov     rcx, [rax]
0x180023ac0  mov     rax, [rcx+18h]
0x180023ac4  mov     rdx, [rsp+0E8h+Handle]
0x180023ac9  mov     rcx, r8
0x180023acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ad1  test    r15, r15
0x180023ad4  jz      short loc_180023AF5
0x180023ad6  mov     ecx, r12d
0x180023ad9  mov     rax, r15
0x180023adc  test    r12d, r12d
0x180023adf  jz      short loc_180023AED
0x180023ae1  mov     byte ptr [rax], 0
0x180023ae4  inc     rax
0x180023ae7  sub     rcx, 1
0x180023aeb  jnz     short loc_180023AE1
0x180023aed  mov     rcx, r15; void *
0x180023af0  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180023af5  test    r14, r14
0x180023af8  jz      short loc_180023B02
0x180023afa  mov     rcx, r14; void *
0x180023afd  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180023b02  test    edi, edi
0x180023b04  jns     short loc_180023B0E
0x180023b06  mov     r8d, 0EEh
0x180023b0c  jmp     short loc_180023B16
0x180023b0e  mov     bl, 5
0x180023b10  mov     r8d, 0F2h; unsigned int
0x180023b16  mov     [rsp+0E8h+nTypeIndex], edi
0x180023b1a  lea     r9, aSerializeobjec; "SerializeObject() completed with hr = 0"...
0x180023b21  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180023b28  movzx   ecx, bl; unsigned __int8
0x180023b2b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023b30  mov     eax, edi
0x180023b32  mov     rcx, [rsp+0E8h+var_40]
0x180023b3a  xor     rcx, rsp; StackCookie
0x180023b3d  call    __security_check_cookie
0x180023b42  add     rsp, 0B8h
0x180023b49  pop     r15
0x180023b4b  pop     r14
0x180023b4d  pop     r13
0x180023b4f  pop     r12
0x180023b51  pop     rdi
0x180023b52  pop     rbx
0x180023b53  retn
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

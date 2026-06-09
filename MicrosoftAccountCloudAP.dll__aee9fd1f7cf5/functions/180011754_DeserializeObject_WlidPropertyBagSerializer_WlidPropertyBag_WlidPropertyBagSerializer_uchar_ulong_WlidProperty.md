# DeserializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(WlidPropertyBagSerializer &,uchar *,ulong,_WlidPropertyBag *)

- ea: `0x180011754`
- end: `0x1800119a4`
- name: `??$DeserializeObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@YAJAEAVWlidPropertyBagSerializer@@PEAEKPEAU_WlidPropertyBag@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *this, void *Source, rsize_t DestinationSize, _OWORD *pObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013478`

## callees

- `0x180007eb8`
- `0x18000f408`
- `0x18000fa14`
- `0x18000fcf4`
- `0x180010040`
- `0x180011754`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x1800118a1`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800118a1`

## string_xrefs

- `0x180011972`: `DeserializeObject() completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeserializeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(
        WlidPropertyBagSerializer *this,
        void *Source,
        rsize_t DestinationSize,
        _OWORD *pObject)
{
  rsize_t v5; // r15
  const void *v6; // r14
  WlidPropertyBagSerializer *v7; // r13
  unsigned int v8; // esi
  _BYTE *v9; // rdi
  signed int v10; // ebx
  _BYTE *v11; // rax
  void *v12; // r13
  errno_t v13; // eax
  struct IRPCFunctions *RPCFunctions; // rax
  int v15; // eax
  __int64 v16; // rax
  _BYTE *v17; // rcx
  __int64 v18; // rax
  unsigned __int8 v19; // al
  unsigned int v20; // r8d
  __int64 nTypeIndex; // [rsp+20h] [rbp-58h]
  handle_t Handle; // [rsp+38h] [rbp-40h] BYREF
  void *v24; // [rsp+40h] [rbp-38h]

  v5 = (unsigned int)DestinationSize;
  v6 = Source;
  v7 = this;
  Handle = 0;
  v8 = 0;
  v9 = 0;
  v24 = 0;
  if ( !Source || !(_DWORD)DestinationSize || !pObject )
    goto LABEL_15;
  v10 = 0;
  if ( (void *)(((unsigned __int64)Source + 7) & 0xFFFFFFFFFFFFFFF8uLL) != Source )
  {
    v8 = DestinationSize + 16;
    if ( (int)DestinationSize + 16 >= (unsigned int)DestinationSize )
    {
      v11 = LiveAllocate(v8);
      v9 = v11;
      v24 = v11;
      if ( !v11 )
      {
        v10 = -2147024882;
        goto LABEL_16;
      }
      v12 = (void *)((unsigned __int64)(v11 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      v13 = memcpy_s_0(v12, v5, v6, v5);
      v10 = v13 != 0 ? 0x8000FFFF : 0;
      if ( v13 )
      {
        v7 = this;
        goto LABEL_16;
      }
      v6 = v12;
      v7 = this;
      goto LABEL_12;
    }
    v8 = -1;
LABEL_15:
    v10 = -2147024809;
    goto LABEL_16;
  }
LABEL_12:
  *pObject = 0;
  RPCFunctions = WlidPropertyBagSerializer::GetRPCFunctions(v7);
  v15 = (*(__int64 (__fastcall **)(struct IRPCFunctions *, const void *, _QWORD, handle_t *))(*(_QWORD *)RPCFunctions
                                                                                            + 32LL))(
          RPCFunctions,
          v6,
          (unsigned int)v5,
          &Handle);
  if ( v15 )
    v10 = HandleRpcError(v15);
  else
    NdrMesTypeDecode3(Handle, &stru_18003F630, &stru_180037860, (const unsigned int **)&off_18004D0C8, 0, pObject);
LABEL_16:
  if ( v9 )
  {
    v16 = v8;
    v17 = v9;
    if ( v8 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    LiveFree(v9);
  }
  if ( Handle )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 16LL))(*(_QWORD *)v7);
    (*(void (__fastcall **)(__int64, handle_t))(*(_QWORD *)v18 + 24LL))(v18, Handle);
  }
  if ( v10 >= 0 )
  {
    v19 = 5;
    v20 = 461;
  }
  else
  {
    v19 = 2;
    v20 = 457;
  }
  LODWORD(nTypeIndex) = v10;
  TracePrintW(
    v19,
    "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
    v20,
    L"DeserializeObject() completed with hr = 0x%x.",
    nTypeIndex);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011754  mov     rax, rsp
0x180011757  mov     [rax+18h], rbx
0x18001175b  mov     [rax+20h], rsi
0x18001175f  mov     [rax+8], rcx
0x180011763  push    rdi
0x180011764  push    r12
0x180011766  push    r13
0x180011768  push    r14
0x18001176a  push    r15
0x18001176c  sub     rsp, 50h
0x180011770  mov     r12, r9
0x180011773  mov     r15d, r8d
0x180011776  mov     r14, rdx
0x180011779  mov     r13, rcx
0x18001177c  mov     qword ptr [rax-40h], 0
0x180011784  xor     esi, esi
0x180011786  mov     [rsp+78h+arg_8], esi
0x18001178d  xor     edi, edi
0x18001178f  mov     [rsp+78h+var_38], rdi
0x180011794  test    rdx, rdx
0x180011797  jz      loc_180011902
0x18001179d  test    r8d, r8d
0x1800117a0  jz      loc_180011902
0x1800117a6  test    r9, r9
0x1800117a9  jz      loc_180011902
0x1800117af  xor     ebx, ebx
0x1800117b1  lea     rax, [rdx+7]
0x1800117b5  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800117b9  cmp     rax, rdx
0x1800117bc  jz      short loc_180011837
0x1800117be  lea     esi, [r15+10h]
0x1800117c2  cmp     esi, r15d
0x1800117c5  jb      short loc_18001182F
0x1800117c7  mov     [rsp+78h+arg_8], esi
0x1800117ce  mov     ecx, esi; unsigned __int64
0x1800117d0  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x1800117d5  mov     rdi, rax
0x1800117d8  mov     [rsp+78h+var_38], rax
0x1800117dd  test    rax, rax
0x1800117e0  jnz     short loc_1800117EC
0x1800117e2  mov     ebx, 8007000Eh
0x1800117e7  jmp     loc_180011907
0x1800117ec  lea     r13, [rax+7]
0x1800117f0  and     r13, 0FFFFFFFFFFFFFFF8h
0x1800117f4  mov     rdx, r15; DestinationSize
0x1800117f7  mov     r9, r15; SourceSize
0x1800117fa  mov     r8, r14; Source
0x1800117fd  mov     rcx, r13; Destination
0x180011800  call    memcpy_s_0
0x180011805  mov     ecx, eax
0x180011807  neg     ecx
0x180011809  sbb     ebx, ebx
0x18001180b  and     ebx, 8000FFFFh
0x180011811  test    eax, eax
0x180011813  jnz     short loc_180011822
0x180011815  mov     r14, r13
0x180011818  mov     r13, [rsp+78h+arg_0]
0x180011820  jmp     short loc_180011837
0x180011822  mov     r13, [rsp+78h+arg_0]
0x18001182a  jmp     loc_180011907
0x18001182f  or      esi, 0FFFFFFFFh
0x180011832  jmp     loc_180011902
0x180011837  xorps   xmm0, xmm0
0x18001183a  movups  xmmword ptr [r12], xmm0
0x18001183f  mov     rcx, r13; this
0x180011842  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180011847  mov     r10, rax
0x18001184a  mov     rcx, [rax]
0x18001184d  mov     rax, [rcx+20h]
0x180011851  lea     r9, [rsp+78h+Handle]
0x180011856  mov     r8d, r15d
0x180011859  mov     rdx, r14
0x18001185c  mov     rcx, r10
0x18001185f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011864  test    eax, eax
0x180011866  jz      short loc_18001187A
0x180011868  mov     ecx, eax; int
0x18001186a  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x18001186f  mov     ebx, eax
0x180011871  mov     [rsp+78h+var_48], eax
0x180011875  jmp     loc_180011907
0x18001187a  mov     [rsp+78h+pObject], r12; pObject
0x18001187f  mov     dword ptr [rsp+78h+nTypeIndex], 0; nTypeIndex
0x180011887  lea     r9, off_18004D0C8; ArrTypeOffset
0x18001188e  lea     r8, stru_180037860; pProxyInfo
0x180011895  lea     rdx, stru_18003F630; pPicklingInfo
0x18001189c  mov     rcx, [rsp+78h+Handle]; Handle
0x1800118a1  call    cs:__imp_NdrMesTypeDecode3
0x1800118a7  jmp     short loc_180011907
0x1800118a9  mov     ebx, eax
0x1800118ab  test    eax, eax
0x1800118ad  jle     short loc_1800118B8
0x1800118af  movzx   ebx, ax
0x1800118b2  or      ebx, 80070000h
0x1800118b8  mov     [rsp+78h+var_48], ebx
0x1800118bc  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x1800118c0  lea     r9, aRpcexceptionco; "RpcExceptionCode hr = 0x%x."
0x1800118c7  mov     r8d, 1B1h; unsigned int
0x1800118cd  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800118d4  mov     ecx, 2; unsigned __int8
0x1800118d9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800118de  mov     eax, 8000FFFFh
0x1800118e3  test    ebx, ebx
0x1800118e5  cmovns  ebx, eax
0x1800118e8  mov     [rsp+78h+var_48], ebx
0x1800118ec  mov     esi, [rsp+78h+arg_8]
0x1800118f3  mov     rdi, [rsp+78h+var_38]
0x1800118f8  mov     r13, [rsp+78h+arg_0]
0x180011900  jmp     short loc_180011907
0x180011902  mov     ebx, 80070057h
0x180011907  test    rdi, rdi
0x18001190a  jz      short loc_180011929
0x18001190c  mov     eax, esi
0x18001190e  mov     rcx, rdi
0x180011911  test    esi, esi
0x180011913  jz      short loc_180011921
0x180011915  mov     byte ptr [rcx], 0
0x180011918  inc     rcx
0x18001191b  sub     rax, 1
0x18001191f  jnz     short loc_180011915
0x180011921  mov     rcx, rdi; void *
0x180011924  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180011929  cmp     [rsp+78h+Handle], 0
0x18001192f  jz      short loc_180011958
0x180011931  mov     rcx, [r13+0]
0x180011935  mov     rax, [rcx]
0x180011938  mov     rax, [rax+10h]
0x18001193c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011941  mov     r8, rax
0x180011944  mov     rcx, [rax]
0x180011947  mov     rax, [rcx+18h]
0x18001194b  mov     rdx, [rsp+78h+Handle]
0x180011950  mov     rcx, r8
0x180011953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011958  test    ebx, ebx
0x18001195a  jns     short loc_180011966
0x18001195c  mov     al, 2
0x18001195e  mov     r8d, 1C9h
0x180011964  jmp     short loc_18001196E
0x180011966  mov     al, 5
0x180011968  mov     r8d, 1CDh; unsigned int
0x18001196e  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x180011972  lea     r9, aDeserializeobj; "DeserializeObject() completed with hr ="...
0x180011979  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011980  movzx   ecx, al; unsigned __int8
0x180011983  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011988  mov     eax, ebx
0x18001198a  lea     r11, [rsp+78h+var_28]
0x18001198f  mov     rbx, [r11+40h]
0x180011993  mov     rsi, [r11+48h]
0x180011997  mov     rsp, r11
0x18001199a  pop     r15
0x18001199c  pop     r14
0x18001199e  pop     r13
0x1800119a0  pop     r12
0x1800119a2  pop     rdi
0x1800119a3  retn
0x180030717  push    rbp
0x180030719  sub     rsp, 30h
0x18003071d  mov     rbp, rdx
0x180030720  mov     rcx, [rcx]
0x180030723  mov     ecx, [rcx]; unsigned int
0x180030725  call    ?WLIDpExceptionFilter@@YAHK@Z; WLIDpExceptionFilter(ulong)
0x18003072a  nop
0x18003072b  add     rsp, 30h
0x18003072f  pop     rbp
0x180030730  retn
```

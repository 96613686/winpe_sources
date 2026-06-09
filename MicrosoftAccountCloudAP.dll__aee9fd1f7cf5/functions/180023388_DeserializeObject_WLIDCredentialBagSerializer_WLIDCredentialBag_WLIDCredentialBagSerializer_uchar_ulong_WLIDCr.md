# DeserializeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(WLIDCredentialBagSerializer &,uchar *,ulong,_WLIDCredentialBag *)

- ea: `0x180023388`
- end: `0x1800235d8`
- name: `??$DeserializeObject@VWLIDCredentialBagSerializer@@U_WLIDCredentialBag@@@@YAJAEAVWLIDCredentialBagSerializer@@PEAEKPEAU_WLIDCredentialBag@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *this, void *Source, rsize_t DestinationSize, _OWORD *pObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023d38`

## callees

- `0x180007eb8`
- `0x18000f408`
- `0x18000fa14`
- `0x18000fcf4`
- `0x180010040`
- `0x180023388`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x1800234d5`
- `RPCRT4!NdrMesTypeDecode3` at `0x1800234d5`

## string_xrefs

- `0x1800235a6`: `DeserializeObject() completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeserializeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(
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
    NdrMesTypeDecode3(Handle, &stru_18003F728, &stru_180037AE0, (const unsigned int **)&off_18004D0D8, 0, pObject);
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
0x180023388  mov     rax, rsp
0x18002338b  mov     [rax+18h], rbx
0x18002338f  mov     [rax+20h], rsi
0x180023393  mov     [rax+8], rcx
0x180023397  push    rdi
0x180023398  push    r12
0x18002339a  push    r13
0x18002339c  push    r14
0x18002339e  push    r15
0x1800233a0  sub     rsp, 50h
0x1800233a4  mov     r12, r9
0x1800233a7  mov     r15d, r8d
0x1800233aa  mov     r14, rdx
0x1800233ad  mov     r13, rcx
0x1800233b0  mov     qword ptr [rax-40h], 0
0x1800233b8  xor     esi, esi
0x1800233ba  mov     [rsp+78h+arg_8], esi
0x1800233c1  xor     edi, edi
0x1800233c3  mov     [rsp+78h+var_38], rdi
0x1800233c8  test    rdx, rdx
0x1800233cb  jz      loc_180023536
0x1800233d1  test    r8d, r8d
0x1800233d4  jz      loc_180023536
0x1800233da  test    r9, r9
0x1800233dd  jz      loc_180023536
0x1800233e3  xor     ebx, ebx
0x1800233e5  lea     rax, [rdx+7]
0x1800233e9  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800233ed  cmp     rax, rdx
0x1800233f0  jz      short loc_18002346B
0x1800233f2  lea     esi, [r15+10h]
0x1800233f6  cmp     esi, r15d
0x1800233f9  jb      short loc_180023463
0x1800233fb  mov     [rsp+78h+arg_8], esi
0x180023402  mov     ecx, esi; unsigned __int64
0x180023404  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x180023409  mov     rdi, rax
0x18002340c  mov     [rsp+78h+var_38], rax
0x180023411  test    rax, rax
0x180023414  jnz     short loc_180023420
0x180023416  mov     ebx, 8007000Eh
0x18002341b  jmp     loc_18002353B
0x180023420  lea     r13, [rax+7]
0x180023424  and     r13, 0FFFFFFFFFFFFFFF8h
0x180023428  mov     rdx, r15; DestinationSize
0x18002342b  mov     r9, r15; SourceSize
0x18002342e  mov     r8, r14; Source
0x180023431  mov     rcx, r13; Destination
0x180023434  call    memcpy_s_0
0x180023439  mov     ecx, eax
0x18002343b  neg     ecx
0x18002343d  sbb     ebx, ebx
0x18002343f  and     ebx, 8000FFFFh
0x180023445  test    eax, eax
0x180023447  jnz     short loc_180023456
0x180023449  mov     r14, r13
0x18002344c  mov     r13, [rsp+78h+arg_0]
0x180023454  jmp     short loc_18002346B
0x180023456  mov     r13, [rsp+78h+arg_0]
0x18002345e  jmp     loc_18002353B
0x180023463  or      esi, 0FFFFFFFFh
0x180023466  jmp     loc_180023536
0x18002346b  xorps   xmm0, xmm0
0x18002346e  movups  xmmword ptr [r12], xmm0
0x180023473  mov     rcx, r13; this
0x180023476  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x18002347b  mov     r10, rax
0x18002347e  mov     rcx, [rax]
0x180023481  mov     rax, [rcx+20h]
0x180023485  lea     r9, [rsp+78h+Handle]
0x18002348a  mov     r8d, r15d
0x18002348d  mov     rdx, r14
0x180023490  mov     rcx, r10
0x180023493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023498  test    eax, eax
0x18002349a  jz      short loc_1800234AE
0x18002349c  mov     ecx, eax; int
0x18002349e  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x1800234a3  mov     ebx, eax
0x1800234a5  mov     [rsp+78h+var_48], eax
0x1800234a9  jmp     loc_18002353B
0x1800234ae  mov     [rsp+78h+pObject], r12; pObject
0x1800234b3  mov     dword ptr [rsp+78h+nTypeIndex], 0; nTypeIndex
0x1800234bb  lea     r9, off_18004D0D8; ArrTypeOffset
0x1800234c2  lea     r8, stru_180037AE0; pProxyInfo
0x1800234c9  lea     rdx, stru_18003F728; pPicklingInfo
0x1800234d0  mov     rcx, [rsp+78h+Handle]; Handle
0x1800234d5  call    cs:__imp_NdrMesTypeDecode3
0x1800234db  jmp     short loc_18002353B
0x1800234dd  mov     ebx, eax
0x1800234df  test    eax, eax
0x1800234e1  jle     short loc_1800234EC
0x1800234e3  movzx   ebx, ax
0x1800234e6  or      ebx, 80070000h
0x1800234ec  mov     [rsp+78h+var_48], ebx
0x1800234f0  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x1800234f4  lea     r9, aRpcexceptionco; "RpcExceptionCode hr = 0x%x."
0x1800234fb  mov     r8d, 1B1h; unsigned int
0x180023501  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180023508  mov     ecx, 2; unsigned __int8
0x18002350d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023512  mov     eax, 8000FFFFh
0x180023517  test    ebx, ebx
0x180023519  cmovns  ebx, eax
0x18002351c  mov     [rsp+78h+var_48], ebx
0x180023520  mov     esi, [rsp+78h+arg_8]
0x180023527  mov     rdi, [rsp+78h+var_38]
0x18002352c  mov     r13, [rsp+78h+arg_0]
0x180023534  jmp     short loc_18002353B
0x180023536  mov     ebx, 80070057h
0x18002353b  test    rdi, rdi
0x18002353e  jz      short loc_18002355D
0x180023540  mov     eax, esi
0x180023542  mov     rcx, rdi
0x180023545  test    esi, esi
0x180023547  jz      short loc_180023555
0x180023549  mov     byte ptr [rcx], 0
0x18002354c  inc     rcx
0x18002354f  sub     rax, 1
0x180023553  jnz     short loc_180023549
0x180023555  mov     rcx, rdi; void *
0x180023558  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x18002355d  cmp     [rsp+78h+Handle], 0
0x180023563  jz      short loc_18002358C
0x180023565  mov     rcx, [r13+0]
0x180023569  mov     rax, [rcx]
0x18002356c  mov     rax, [rax+10h]
0x180023570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023575  mov     r8, rax
0x180023578  mov     rcx, [rax]
0x18002357b  mov     rax, [rcx+18h]
0x18002357f  mov     rdx, [rsp+78h+Handle]
0x180023584  mov     rcx, r8
0x180023587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002358c  test    ebx, ebx
0x18002358e  jns     short loc_18002359A
0x180023590  mov     al, 2
0x180023592  mov     r8d, 1C9h
0x180023598  jmp     short loc_1800235A2
0x18002359a  mov     al, 5
0x18002359c  mov     r8d, 1CDh; unsigned int
0x1800235a2  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x1800235a6  lea     r9, aDeserializeobj; "DeserializeObject() completed with hr ="...
0x1800235ad  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800235b4  movzx   ecx, al; unsigned __int8
0x1800235b7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800235bc  mov     eax, ebx
0x1800235be  lea     r11, [rsp+78h+var_28]
0x1800235c3  mov     rbx, [r11+40h]
0x1800235c7  mov     rsi, [r11+48h]
0x1800235cb  mov     rsp, r11
0x1800235ce  pop     r15
0x1800235d0  pop     r14
0x1800235d2  pop     r13
0x1800235d4  pop     r12
0x1800235d6  pop     rdi
0x1800235d7  retn
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

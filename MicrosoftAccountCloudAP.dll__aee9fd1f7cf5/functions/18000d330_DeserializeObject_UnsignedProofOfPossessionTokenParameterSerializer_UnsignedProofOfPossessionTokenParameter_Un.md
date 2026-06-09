# DeserializeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(UnsignedProofOfPossessionTokenParameterSerializer &,uchar *,ulong,_UnsignedProofOfPossessionTokenParameter *)

- ea: `0x18000d330`
- end: `0x18000d587`
- name: `??$DeserializeObject@VUnsignedProofOfPossessionTokenParameterSerializer@@U_UnsignedProofOfPossessionTokenParameter@@@@YAJAEAVUnsignedProofOfPossessionTokenParameterSerializer@@PEAEKPEAU_UnsignedProofOfPossessionTokenParameter@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *this, void *Source, rsize_t DestinationSize, void *pObject)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e75c`

## callees

- `0x180003b14`
- `0x180007eb8`
- `0x18000d330`
- `0x18000f408`
- `0x18000fa14`
- `0x18000fcf4`
- `0x180010040`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeDecode3` at `0x18000d484`
- `RPCRT4!NdrMesTypeDecode3` at `0x18000d484`

## string_xrefs

- `0x18000d555`: `DeserializeObject() completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeserializeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(
        WlidPropertyBagSerializer *this,
        void *Source,
        rsize_t DestinationSize,
        void *pObject)
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
  memset_0(pObject, 0, 0x40u);
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
    NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, pObject);
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
0x18000d330  mov     rax, rsp
0x18000d333  mov     [rax+18h], rbx
0x18000d337  mov     [rax+20h], rsi
0x18000d33b  mov     [rax+8], rcx
0x18000d33f  push    rdi
0x18000d340  push    r12
0x18000d342  push    r13
0x18000d344  push    r14
0x18000d346  push    r15
0x18000d348  sub     rsp, 50h
0x18000d34c  mov     r12, r9
0x18000d34f  mov     r15d, r8d
0x18000d352  mov     r14, rdx
0x18000d355  mov     r13, rcx
0x18000d358  mov     qword ptr [rax-40h], 0
0x18000d360  xor     esi, esi
0x18000d362  mov     [rsp+78h+arg_8], esi
0x18000d369  xor     edi, edi
0x18000d36b  mov     [rsp+78h+var_38], rdi
0x18000d370  test    rdx, rdx
0x18000d373  jz      loc_18000D4E5
0x18000d379  test    r8d, r8d
0x18000d37c  jz      loc_18000D4E5
0x18000d382  test    r9, r9
0x18000d385  jz      loc_18000D4E5
0x18000d38b  xor     ebx, ebx
0x18000d38d  lea     rax, [rdx+7]
0x18000d391  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d395  cmp     rax, rdx
0x18000d398  jz      short loc_18000D413
0x18000d39a  lea     esi, [r15+10h]
0x18000d39e  cmp     esi, r15d
0x18000d3a1  jb      short loc_18000D40B
0x18000d3a3  mov     [rsp+78h+arg_8], esi
0x18000d3aa  mov     ecx, esi; unsigned __int64
0x18000d3ac  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000d3b1  mov     rdi, rax
0x18000d3b4  mov     [rsp+78h+var_38], rax
0x18000d3b9  test    rax, rax
0x18000d3bc  jnz     short loc_18000D3C8
0x18000d3be  mov     ebx, 8007000Eh
0x18000d3c3  jmp     loc_18000D4EA
0x18000d3c8  lea     r13, [rax+7]
0x18000d3cc  and     r13, 0FFFFFFFFFFFFFFF8h
0x18000d3d0  mov     rdx, r15; DestinationSize
0x18000d3d3  mov     r9, r15; SourceSize
0x18000d3d6  mov     r8, r14; Source
0x18000d3d9  mov     rcx, r13; Destination
0x18000d3dc  call    memcpy_s_0
0x18000d3e1  mov     ecx, eax
0x18000d3e3  neg     ecx
0x18000d3e5  sbb     ebx, ebx
0x18000d3e7  and     ebx, 8000FFFFh
0x18000d3ed  test    eax, eax
0x18000d3ef  jnz     short loc_18000D3FE
0x18000d3f1  mov     r14, r13
0x18000d3f4  mov     r13, [rsp+78h+arg_0]
0x18000d3fc  jmp     short loc_18000D413
0x18000d3fe  mov     r13, [rsp+78h+arg_0]
0x18000d406  jmp     loc_18000D4EA
0x18000d40b  or      esi, 0FFFFFFFFh
0x18000d40e  jmp     loc_18000D4E5
0x18000d413  xor     edx, edx; Val
0x18000d415  lea     r8d, [rdx+40h]; Size
0x18000d419  mov     rcx, r12; void *
0x18000d41c  call    memset_0
0x18000d421  nop
0x18000d422  mov     rcx, r13; this
0x18000d425  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x18000d42a  mov     r10, rax
0x18000d42d  mov     rcx, [rax]
0x18000d430  mov     rax, [rcx+20h]
0x18000d434  lea     r9, [rsp+78h+Handle]
0x18000d439  mov     r8d, r15d
0x18000d43c  mov     rdx, r14
0x18000d43f  mov     rcx, r10
0x18000d442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d447  test    eax, eax
0x18000d449  jz      short loc_18000D45D
0x18000d44b  mov     ecx, eax; int
0x18000d44d  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x18000d452  mov     ebx, eax
0x18000d454  mov     [rsp+78h+var_48], eax
0x18000d458  jmp     loc_18000D4EA
0x18000d45d  mov     [rsp+78h+pObject], r12; pObject
0x18000d462  mov     dword ptr [rsp+78h+nTypeIndex], 0; nTypeIndex
0x18000d46a  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18000d471  lea     r8, pProxyInfo; pProxyInfo
0x18000d478  lea     rdx, pPicklingInfo; pPicklingInfo
0x18000d47f  mov     rcx, [rsp+78h+Handle]; Handle
0x18000d484  call    cs:__imp_NdrMesTypeDecode3
0x18000d48a  jmp     short loc_18000D4EA
0x18000d48c  mov     ebx, eax
0x18000d48e  test    eax, eax
0x18000d490  jle     short loc_18000D49B
0x18000d492  movzx   ebx, ax
0x18000d495  or      ebx, 80070000h
0x18000d49b  mov     [rsp+78h+var_48], ebx
0x18000d49f  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x18000d4a3  lea     r9, aRpcexceptionco; "RpcExceptionCode hr = 0x%x."
0x18000d4aa  mov     r8d, 1B1h; unsigned int
0x18000d4b0  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18000d4b7  mov     ecx, 2; unsigned __int8
0x18000d4bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d4c1  mov     eax, 8000FFFFh
0x18000d4c6  test    ebx, ebx
0x18000d4c8  cmovns  ebx, eax
0x18000d4cb  mov     [rsp+78h+var_48], ebx
0x18000d4cf  mov     esi, [rsp+78h+arg_8]
0x18000d4d6  mov     rdi, [rsp+78h+var_38]
0x18000d4db  mov     r13, [rsp+78h+arg_0]
0x18000d4e3  jmp     short loc_18000D4EA
0x18000d4e5  mov     ebx, 80070057h
0x18000d4ea  test    rdi, rdi
0x18000d4ed  jz      short loc_18000D50C
0x18000d4ef  mov     eax, esi
0x18000d4f1  mov     rcx, rdi
0x18000d4f4  test    esi, esi
0x18000d4f6  jz      short loc_18000D504
0x18000d4f8  mov     byte ptr [rcx], 0
0x18000d4fb  inc     rcx
0x18000d4fe  sub     rax, 1
0x18000d502  jnz     short loc_18000D4F8
0x18000d504  mov     rcx, rdi; void *
0x18000d507  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x18000d50c  cmp     [rsp+78h+Handle], 0
0x18000d512  jz      short loc_18000D53B
0x18000d514  mov     rcx, [r13+0]
0x18000d518  mov     rax, [rcx]
0x18000d51b  mov     rax, [rax+10h]
0x18000d51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d524  mov     r8, rax
0x18000d527  mov     rcx, [rax]
0x18000d52a  mov     rax, [rcx+18h]
0x18000d52e  mov     rdx, [rsp+78h+Handle]
0x18000d533  mov     rcx, r8
0x18000d536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53b  test    ebx, ebx
0x18000d53d  jns     short loc_18000D549
0x18000d53f  mov     al, 2
0x18000d541  mov     r8d, 1C9h
0x18000d547  jmp     short loc_18000D551
0x18000d549  mov     al, 5
0x18000d54b  mov     r8d, 1CDh; unsigned int
0x18000d551  mov     dword ptr [rsp+78h+nTypeIndex], ebx
0x18000d555  lea     r9, aDeserializeobj; "DeserializeObject() completed with hr ="...
0x18000d55c  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18000d563  movzx   ecx, al; unsigned __int8
0x18000d566  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d56b  mov     eax, ebx
0x18000d56d  lea     r11, [rsp+78h+var_28]
0x18000d572  mov     rbx, [r11+40h]
0x18000d576  mov     rsi, [r11+48h]
0x18000d57a  mov     rsp, r11
0x18000d57d  pop     r15
0x18000d57f  pop     r14
0x18000d581  pop     r13
0x18000d583  pop     r12
0x18000d585  pop     rdi
0x18000d586  retn
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

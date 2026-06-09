# FreeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(UnsignedProofOfPossessionTokenParameterSerializer &,_UnsignedProofOfPossessionTokenParameter *)

- ea: `0x18000d590`
- end: `0x18000d72a`
- name: `??$FreeObject@VUnsignedProofOfPossessionTokenParameterSerializer@@U_UnsignedProofOfPossessionTokenParameter@@@@YAJAEAVUnsignedProofOfPossessionTokenParameterSerializer@@PEAU_UnsignedProofOfPossessionTokenParameter@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d9e4`

## callees

- `0x180003160`
- `0x180003b14`
- `0x18000d590`
- `0x18000f408`
- `0x18000fa14`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeFree3` at `0x18000d656`
- `RPCRT4!NdrMesTypeFree3` at `0x18000d656`

## string_xrefs

- `0x18000d6e7`: `FreeObject() in SerializationDefinition.h completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FreeObject<UnsignedProofOfPossessionTokenParameterSerializer,_UnsignedProofOfPossessionTokenParameter>(
        WlidPropertyBagSerializer *a1,
        void *a2)
{
  unsigned int v4; // ebx
  int v5; // esp
  unsigned int v6; // r15d
  struct IRPCFunctions *RPCFunctions; // rax
  int v8; // eax
  __int64 v9; // rax
  unsigned int nTypeIndex[2]; // [rsp+20h] [rbp-68h]
  handle_t Handle; // [rsp+38h] [rbp-50h] BYREF
  int v13; // [rsp+40h] [rbp-48h] BYREF
  WlidPropertyBagSerializer *v14; // [rsp+48h] [rbp-40h]
  _BYTE v15[7]; // [rsp+50h] [rbp-38h] BYREF

  v14 = a1;
  Handle = 0;
  v13 = 0;
  if ( a2 )
  {
    v4 = 0;
    v6 = v5 + 104 - (unsigned int)v15;
    RPCFunctions = WlidPropertyBagSerializer::GetRPCFunctions(a1);
    v8 = (*(__int64 (__fastcall **)(struct IRPCFunctions *, _BYTE *, _QWORD, int *, handle_t *))(*(_QWORD *)RPCFunctions
                                                                                               + 8LL))(
           RPCFunctions,
           v15,
           v6,
           &v13,
           &Handle);
    if ( v8 )
    {
      v4 = HandleRpcError(v8);
    }
    else
    {
      NdrMesTypeFree3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, a2);
      memset_0(a2, 0, 0x40u);
    }
  }
  else
  {
    v4 = -2147024809;
  }
  if ( Handle )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 16LL))(*(_QWORD *)a1);
    (*(void (__fastcall **)(__int64, handle_t))(*(_QWORD *)v9 + 24LL))(v9, Handle);
  }
  nTypeIndex[0] = v4;
  TracePrintW(
    4u,
    "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
    0x23Fu,
    L"FreeObject() in SerializationDefinition.h completed with hr = 0x%x.",
    *(_QWORD *)nTypeIndex);
  return v4;
}

```

## disassembly

```asm
0x18000d590  mov     [rsp+arg_10], rbx
0x18000d595  mov     [rsp+arg_18], rsi
0x18000d59a  push    rdi
0x18000d59b  push    r14
0x18000d59d  push    r15
0x18000d59f  sub     rsp, 70h
0x18000d5a3  mov     rax, cs:__security_cookie
0x18000d5aa  xor     rax, rsp
0x18000d5ad  mov     [rsp+88h+var_20], rax
0x18000d5b2  mov     rdi, rdx
0x18000d5b5  mov     r14, rcx
0x18000d5b8  mov     [rsp+88h+var_40], rcx
0x18000d5bd  mov     [rsp+88h+Handle], 0
0x18000d5c6  mov     [rsp+88h+var_48], 0
0x18000d5ce  test    rdx, rdx
0x18000d5d1  jnz     short loc_18000D5DD
0x18000d5d3  mov     ebx, 80070057h
0x18000d5d8  jmp     loc_18000D6B5
0x18000d5dd  xor     ebx, ebx
0x18000d5df  lea     rsi, [rsp+88h+var_31]
0x18000d5e4  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18000d5e8  lea     r15, [rsp+88h+var_20]
0x18000d5ed  sub     r15d, esi
0x18000d5f0  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x18000d5f5  mov     rcx, rax
0x18000d5f8  mov     rax, [rax]
0x18000d5fb  lea     rdx, [rsp+88h+Handle]
0x18000d600  mov     qword ptr [rsp+88h+nTypeIndex], rdx
0x18000d605  lea     r9, [rsp+88h+var_48]
0x18000d60a  mov     r8d, r15d
0x18000d60d  mov     rdx, rsi
0x18000d610  mov     rax, [rax+8]
0x18000d614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d619  test    eax, eax
0x18000d61b  jz      short loc_18000D62F
0x18000d61d  mov     ecx, eax; int
0x18000d61f  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x18000d624  mov     ebx, eax
0x18000d626  mov     [rsp+88h+var_58], eax
0x18000d62a  jmp     loc_18000D6B5
0x18000d62f  mov     [rsp+88h+pObject], rdi; pObject
0x18000d634  mov     [rsp+88h+nTypeIndex], 0; nTypeIndex
0x18000d63c  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18000d643  lea     r8, pProxyInfo; pProxyInfo
0x18000d64a  lea     rdx, pPicklingInfo; pPicklingInfo
0x18000d651  mov     rcx, [rsp+88h+Handle]; Handle
0x18000d656  call    cs:__imp_NdrMesTypeFree3
0x18000d65c  nop
0x18000d65d  xor     edx, edx; Val
0x18000d65f  lea     r8d, [rdx+40h]; Size
0x18000d663  mov     rcx, rdi; void *
0x18000d666  call    memset_0
0x18000d66b  jmp     short loc_18000D6B5
0x18000d66d  mov     ebx, eax
0x18000d66f  test    eax, eax
0x18000d671  jle     short loc_18000D67C
0x18000d673  movzx   ebx, ax
0x18000d676  or      ebx, 80070000h
0x18000d67c  mov     [rsp+88h+var_58], ebx
0x18000d680  mov     [rsp+88h+nTypeIndex], ebx
0x18000d684  lea     r9, aCaughtExceptio; "Caught exception in FreeObject(), hr = "...
0x18000d68b  mov     r8d, 22Fh; unsigned int
0x18000d691  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18000d698  mov     ecx, 2; unsigned __int8
0x18000d69d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d6a2  mov     eax, 8000FFFFh
0x18000d6a7  test    ebx, ebx
0x18000d6a9  cmovns  ebx, eax
0x18000d6ac  mov     [rsp+88h+var_58], ebx
0x18000d6b0  mov     r14, [rsp+88h+var_40]
0x18000d6b5  cmp     [rsp+88h+Handle], 0
0x18000d6bb  jz      short loc_18000D6E3
0x18000d6bd  mov     rcx, [r14]
0x18000d6c0  mov     rax, [rcx]
0x18000d6c3  mov     rax, [rax+10h]
0x18000d6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6cc  mov     r8, rax
0x18000d6cf  mov     rcx, [rax]
0x18000d6d2  mov     rax, [rcx+18h]
0x18000d6d6  mov     rdx, [rsp+88h+Handle]
0x18000d6db  mov     rcx, r8
0x18000d6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6e3  mov     [rsp+88h+nTypeIndex], ebx
0x18000d6e7  lea     r9, aFreeobjectInSe; "FreeObject() in SerializationDefinition"...
0x18000d6ee  mov     r8d, 23Fh; unsigned int
0x18000d6f4  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18000d6fb  mov     ecx, 4; unsigned __int8
0x18000d700  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d705  mov     eax, ebx
0x18000d707  mov     rcx, [rsp+88h+var_20]
0x18000d70c  xor     rcx, rsp; StackCookie
0x18000d70f  call    __security_check_cookie
0x18000d714  lea     r11, [rsp+88h+var_18]
0x18000d719  mov     rbx, [r11+30h]
0x18000d71d  mov     rsi, [r11+38h]
0x18000d721  mov     rsp, r11
0x18000d724  pop     r15
0x18000d726  pop     r14
0x18000d728  pop     rdi
0x18000d729  retn
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

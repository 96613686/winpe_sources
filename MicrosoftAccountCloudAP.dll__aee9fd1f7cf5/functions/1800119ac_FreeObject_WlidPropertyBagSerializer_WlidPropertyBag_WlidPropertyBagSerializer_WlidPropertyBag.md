# FreeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(WlidPropertyBagSerializer &,_WlidPropertyBag *)

- ea: `0x1800119ac`
- end: `0x180011b3b`
- name: `??$FreeObject@VWlidPropertyBagSerializer@@U_WlidPropertyBag@@@@YAJAEAVWlidPropertyBagSerializer@@PEAU_WlidPropertyBag@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012178`

## callees

- `0x180003160`
- `0x18000f408`
- `0x18000fa14`
- `0x1800119ac`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeFree3` at `0x180011a6f`
- `RPCRT4!NdrMesTypeFree3` at `0x180011a6f`

## string_xrefs

- `0x180011af8`: `FreeObject() in SerializationDefinition.h completed with hr = 0x%x.`

## pseudocode

```c
__int64 __fastcall FreeObject<WlidPropertyBagSerializer,_WlidPropertyBag>(WlidPropertyBagSerializer *a1, _OWORD *a2)
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
      NdrMesTypeFree3(Handle, &stru_18003F630, &stru_180037860, (const unsigned int **)&off_18004D0C8, 0, a2);
      *a2 = 0;
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
0x1800119ac  mov     [rsp+arg_10], rbx
0x1800119b1  mov     [rsp+arg_18], rsi
0x1800119b6  push    rdi
0x1800119b7  push    r14
0x1800119b9  push    r15
0x1800119bb  sub     rsp, 70h
0x1800119bf  mov     rax, cs:__security_cookie
0x1800119c6  xor     rax, rsp
0x1800119c9  mov     [rsp+88h+var_20], rax
0x1800119ce  mov     rdi, rdx
0x1800119d1  mov     r14, rcx
0x1800119d4  mov     [rsp+88h+var_40], rcx
0x1800119d9  mov     [rsp+88h+Handle], 0
0x1800119e2  mov     [rsp+88h+var_48], 0
0x1800119ea  test    rdx, rdx
0x1800119ed  jnz     short loc_1800119F9
0x1800119ef  mov     ebx, 80070057h
0x1800119f4  jmp     loc_180011AC6
0x1800119f9  xor     ebx, ebx
0x1800119fb  lea     rsi, [rsp+88h+var_31]
0x180011a00  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180011a04  lea     r15, [rsp+88h+var_20]
0x180011a09  sub     r15d, esi
0x180011a0c  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180011a11  mov     rcx, rax
0x180011a14  mov     rax, [rax]
0x180011a17  lea     rdx, [rsp+88h+Handle]
0x180011a1c  mov     qword ptr [rsp+88h+nTypeIndex], rdx
0x180011a21  lea     r9, [rsp+88h+var_48]
0x180011a26  mov     r8d, r15d
0x180011a29  mov     rdx, rsi
0x180011a2c  mov     rax, [rax+8]
0x180011a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a35  test    eax, eax
0x180011a37  jz      short loc_180011A48
0x180011a39  mov     ecx, eax; int
0x180011a3b  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180011a40  mov     ebx, eax
0x180011a42  mov     [rsp+88h+var_58], eax
0x180011a46  jmp     short loc_180011AC6
0x180011a48  mov     [rsp+88h+pObject], rdi; pObject
0x180011a4d  mov     [rsp+88h+nTypeIndex], 0; nTypeIndex
0x180011a55  lea     r9, off_18004D0C8; ArrTypeOffset
0x180011a5c  lea     r8, stru_180037860; pProxyInfo
0x180011a63  lea     rdx, stru_18003F630; pPicklingInfo
0x180011a6a  mov     rcx, [rsp+88h+Handle]; Handle
0x180011a6f  call    cs:__imp_NdrMesTypeFree3
0x180011a75  nop
0x180011a76  xorps   xmm0, xmm0
0x180011a79  movups  xmmword ptr [rdi], xmm0
0x180011a7c  jmp     short loc_180011AC6
0x180011a7e  mov     ebx, eax
0x180011a80  test    eax, eax
0x180011a82  jle     short loc_180011A8D
0x180011a84  movzx   ebx, ax
0x180011a87  or      ebx, 80070000h
0x180011a8d  mov     [rsp+88h+var_58], ebx
0x180011a91  mov     [rsp+88h+nTypeIndex], ebx
0x180011a95  lea     r9, aCaughtExceptio; "Caught exception in FreeObject(), hr = "...
0x180011a9c  mov     r8d, 22Fh; unsigned int
0x180011aa2  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011aa9  mov     ecx, 2; unsigned __int8
0x180011aae  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011ab3  mov     eax, 8000FFFFh
0x180011ab8  test    ebx, ebx
0x180011aba  cmovns  ebx, eax
0x180011abd  mov     [rsp+88h+var_58], ebx
0x180011ac1  mov     r14, [rsp+88h+var_40]
0x180011ac6  cmp     [rsp+88h+Handle], 0
0x180011acc  jz      short loc_180011AF4
0x180011ace  mov     rcx, [r14]
0x180011ad1  mov     rax, [rcx]
0x180011ad4  mov     rax, [rax+10h]
0x180011ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011add  mov     r8, rax
0x180011ae0  mov     rcx, [rax]
0x180011ae3  mov     rax, [rcx+18h]
0x180011ae7  mov     rdx, [rsp+88h+Handle]
0x180011aec  mov     rcx, r8
0x180011aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af4  mov     [rsp+88h+nTypeIndex], ebx
0x180011af8  lea     r9, aFreeobjectInSe; "FreeObject() in SerializationDefinition"...
0x180011aff  mov     r8d, 23Fh; unsigned int
0x180011b05  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180011b0c  mov     ecx, 4; unsigned __int8
0x180011b11  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180011b16  mov     eax, ebx
0x180011b18  mov     rcx, [rsp+88h+var_20]
0x180011b1d  xor     rcx, rsp; StackCookie
0x180011b20  call    __security_check_cookie
0x180011b25  lea     r11, [rsp+88h+var_18]
0x180011b2a  mov     rbx, [r11+30h]
0x180011b2e  mov     rsi, [r11+38h]
0x180011b32  mov     rsp, r11
0x180011b35  pop     r15
0x180011b37  pop     r14
0x180011b39  pop     rdi
0x180011b3a  retn
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

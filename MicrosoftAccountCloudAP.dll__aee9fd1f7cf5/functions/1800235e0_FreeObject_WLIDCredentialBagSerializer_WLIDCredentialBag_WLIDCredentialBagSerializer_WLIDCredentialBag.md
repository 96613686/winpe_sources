# FreeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(WLIDCredentialBagSerializer &,_WLIDCredentialBag *)

- ea: `0x1800235e0`
- end: `0x18002376f`
- name: `??$FreeObject@VWLIDCredentialBagSerializer@@U_WLIDCredentialBag@@@@YAJAEAVWLIDCredentialBagSerializer@@PEAU_WLIDCredentialBag@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(WlidPropertyBagSerializer *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024258`

## callees

- `0x180003160`
- `0x18000f408`
- `0x18000fa14`
- `0x1800235e0`
- `0x1800267c0`
- `0x180029bec`
- `0x180032010`

## import_xrefs

- `RPCRT4!NdrMesTypeFree3` at `0x1800236a3`
- `RPCRT4!NdrMesTypeFree3` at `0x1800236a3`

## string_xrefs

- `0x18002372c`: `FreeObject() in SerializationDefinition.h completed with hr = 0x%x.`

## pseudocode

```c
__int64 __fastcall FreeObject<WLIDCredentialBagSerializer,_WLIDCredentialBag>(
        WlidPropertyBagSerializer *a1,
        _OWORD *a2)
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
      NdrMesTypeFree3(Handle, &stru_18003F728, &stru_180037AE0, (const unsigned int **)&off_18004D0D8, 0, a2);
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
0x1800235e0  mov     [rsp+arg_10], rbx
0x1800235e5  mov     [rsp+arg_18], rsi
0x1800235ea  push    rdi
0x1800235eb  push    r14
0x1800235ed  push    r15
0x1800235ef  sub     rsp, 70h
0x1800235f3  mov     rax, cs:__security_cookie
0x1800235fa  xor     rax, rsp
0x1800235fd  mov     [rsp+88h+var_20], rax
0x180023602  mov     rdi, rdx
0x180023605  mov     r14, rcx
0x180023608  mov     [rsp+88h+var_40], rcx
0x18002360d  mov     [rsp+88h+Handle], 0
0x180023616  mov     [rsp+88h+var_48], 0
0x18002361e  test    rdx, rdx
0x180023621  jnz     short loc_18002362D
0x180023623  mov     ebx, 80070057h
0x180023628  jmp     loc_1800236FA
0x18002362d  xor     ebx, ebx
0x18002362f  lea     rsi, [rsp+88h+var_31]
0x180023634  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180023638  lea     r15, [rsp+88h+var_20]
0x18002363d  sub     r15d, esi
0x180023640  call    ?GetRPCFunctions@WlidPropertyBagSerializer@@QEAAPEAVIRPCFunctions@@XZ; WlidPropertyBagSerializer::GetRPCFunctions(void)
0x180023645  mov     rcx, rax
0x180023648  mov     rax, [rax]
0x18002364b  lea     rdx, [rsp+88h+Handle]
0x180023650  mov     qword ptr [rsp+88h+nTypeIndex], rdx
0x180023655  lea     r9, [rsp+88h+var_48]
0x18002365a  mov     r8d, r15d
0x18002365d  mov     rdx, rsi
0x180023660  mov     rax, [rax+8]
0x180023664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023669  test    eax, eax
0x18002366b  jz      short loc_18002367C
0x18002366d  mov     ecx, eax; int
0x18002366f  call    ?HandleRpcError@@YAJJ@Z; HandleRpcError(long)
0x180023674  mov     ebx, eax
0x180023676  mov     [rsp+88h+var_58], eax
0x18002367a  jmp     short loc_1800236FA
0x18002367c  mov     [rsp+88h+pObject], rdi; pObject
0x180023681  mov     [rsp+88h+nTypeIndex], 0; nTypeIndex
0x180023689  lea     r9, off_18004D0D8; ArrTypeOffset
0x180023690  lea     r8, stru_180037AE0; pProxyInfo
0x180023697  lea     rdx, stru_18003F728; pPicklingInfo
0x18002369e  mov     rcx, [rsp+88h+Handle]; Handle
0x1800236a3  call    cs:__imp_NdrMesTypeFree3
0x1800236a9  nop
0x1800236aa  xorps   xmm0, xmm0
0x1800236ad  movups  xmmword ptr [rdi], xmm0
0x1800236b0  jmp     short loc_1800236FA
0x1800236b2  mov     ebx, eax
0x1800236b4  test    eax, eax
0x1800236b6  jle     short loc_1800236C1
0x1800236b8  movzx   ebx, ax
0x1800236bb  or      ebx, 80070000h
0x1800236c1  mov     [rsp+88h+var_58], ebx
0x1800236c5  mov     [rsp+88h+nTypeIndex], ebx
0x1800236c9  lea     r9, aCaughtExceptio; "Caught exception in FreeObject(), hr = "...
0x1800236d0  mov     r8d, 22Fh; unsigned int
0x1800236d6  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800236dd  mov     ecx, 2; unsigned __int8
0x1800236e2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800236e7  mov     eax, 8000FFFFh
0x1800236ec  test    ebx, ebx
0x1800236ee  cmovns  ebx, eax
0x1800236f1  mov     [rsp+88h+var_58], ebx
0x1800236f5  mov     r14, [rsp+88h+var_40]
0x1800236fa  cmp     [rsp+88h+Handle], 0
0x180023700  jz      short loc_180023728
0x180023702  mov     rcx, [r14]
0x180023705  mov     rax, [rcx]
0x180023708  mov     rax, [rax+10h]
0x18002370c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023711  mov     r8, rax
0x180023714  mov     rcx, [rax]
0x180023717  mov     rax, [rcx+18h]
0x18002371b  mov     rdx, [rsp+88h+Handle]
0x180023720  mov     rcx, r8
0x180023723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023728  mov     [rsp+88h+nTypeIndex], ebx
0x18002372c  lea     r9, aFreeobjectInSe; "FreeObject() in SerializationDefinition"...
0x180023733  mov     r8d, 23Fh; unsigned int
0x180023739  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x180023740  mov     ecx, 4; unsigned __int8
0x180023745  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002374a  mov     eax, ebx
0x18002374c  mov     rcx, [rsp+88h+var_20]
0x180023751  xor     rcx, rsp; StackCookie
0x180023754  call    __security_check_cookie
0x180023759  lea     r11, [rsp+88h+var_18]
0x18002375e  mov     rbx, [r11+30h]
0x180023762  mov     rsi, [r11+38h]
0x180023766  mov     rsp, r11
0x180023769  pop     r15
0x18002376b  pop     r14
0x18002376d  pop     rdi
0x18002376e  retn
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

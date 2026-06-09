# CFlat::ComMarshaling::ToNativeInterface(System::Object *,IUnknown *,CFlat::ComInterfaceTypeId const *,_GUID const &)

- ea: `0x180020550`
- end: `0x1800207e1`
- name: `?ToNativeInterface@ComMarshaling@CFlat@@SAPEAXPEAVObject@System@@PEAUIUnknown@@PEBUComInterfaceTypeId@2@AEBU_GUID@@@Z`
- size: `657`
- prototype: `static void *(struct System::Object *, struct IUnknown *, const struct CFlat::ComInterfaceTypeId *, const struct _GUID *)`
- caller_count: `11`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800218ac`
- `0x1800218e0`
- `0x180021c28`
- `0x180021c60`
- `0x180032e30`
- `0x180048c10`
- `0x18006d580`
- `0x18006e890`
- `0x180091c54`
- `0x180093a4c`
- `0x1800946cc`

## callees

- `0x1800080a8`
- `0x1800082d0`
- `0x180009750`
- `0x180019c44`
- `0x180020550`
- `0x1800207e8`
- `0x18004a850`
- `0x18008ae1c`
- `0x18008b758`
- `0x1800a6298`
- `0x1800c7ff0`
- `0x1800c8020`
- `0x1800c8460`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002062a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800206f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020734`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002062a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800206f5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020734`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall CFlat::ComMarshaling::ToNativeInterface(
        struct System::Object *a1,
        struct IUnknown *a2,
        const struct CFlat::ComInterfaceTypeId *a3,
        const struct _GUID *a4)
{
  struct System::Object *v6; // rsi
  char v7; // bl
  unsigned __int16 *v8; // r8
  int v9; // edx
  int v10; // r9d
  __int64 v11; // rax
  int i; // edx
  __int64 v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, struct System::Object *, const struct _GUID *, struct System::Object *); // rcx
  struct IUnknown *Native; // rax
  const char16_t *v16; // rcx
  void *Value; // r14
  void *v18; // r15
  __int64 v19; // rax
  __int64 *v22; // rax
  void *v23; // rbx
  void *v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rax
  const char16_t *v27; // rcx
  void *v28; // [rsp+30h] [rbp-30h] BYREF
  void **v29; // [rsp+38h] [rbp-28h] BYREF
  struct IUnknown *v30; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v31[24]; // [rsp+48h] [rbp-18h] BYREF
  void *v32; // [rsp+90h] [rbp+30h] BYREF

  v6 = a1;
  v7 = 0;
  if ( a1 )
  {
    if ( *((_UNKNOWN **)a1 + 1) == &CFlat::ComImportAdapter::TypeId$ )
    {
      Native = (struct IUnknown *)CFlat::ComImportAdapter::GetNativeInterface$(a1, a3);
      if ( !Native )
        CFlat::Abandonment::Fail(v27);
    }
    else
    {
      if ( a2 )
      {
        v28 = 0;
        Value = TlsGetValue(Cn::Context::s_tlsStorage);
        v18 = CFlat::EntryExit::ValidateCall(Value, a2, 0);
        CFlat::EntryExit::OnBeginCallToNative(Value);
        v29 = &v28;
        v30 = a2;
        LODWORD(v32) = 0;
        v19 = lambda_f7e478493cd4c7e6a5c3d3065f952319_::_lambda_f7e478493cd4c7e6a5c3d3065f952319_(v31, &v32, &v30, &v29);
        CFlat::SehSafe::Execute__lambda_f7e478493cd4c7e6a5c3d3065f952319___(Value, v19);
        if ( !(_DWORD)v32 && *((struct System::Object **)v28 + 3) == v6 )
        {
          Cn::Context::NoContext_NotifyReturn((Cn::Context *)Value, v18);
          Native = a2;
          goto LABEL_22;
        }
        Cn::Context::NoContext_NotifyReturn((Cn::Context *)Value, v18);
      }
      v8 = (unsigned __int16 *)*((_QWORD *)v6 + 1);
      v9 = 0;
      v10 = *v8;
      while ( 1 )
      {
        if ( v9 >= v10 )
          goto LABEL_17;
        v11 = *v8;
        a1 = (struct System::Object *)(2 * (v9 - v11));
        if ( &CFlat::IImplementsComInterface::TypeId$ == *(_UNKNOWN **)&v8[8 * (v9 - v11)] )
          break;
        ++v9;
      }
      if ( !*(_QWORD *)&v8[8 * (v9 - v11) + 4] )
LABEL_17:
        CFlat::Abandonment::Fail((const char16_t *)a1);
      for ( i = 0; i < v10; ++i )
      {
        v13 = *v8;
        if ( &CFlat::IImplementsComInterface::TypeId$ == *(_UNKNOWN **)&v8[8 * (i - v13)] )
        {
          v14 = *(__int64 (__fastcall ****)(_QWORD, struct System::Object *, const struct _GUID *, struct System::Object *))&v8[8 * (i - v13) + 4];
          goto LABEL_12;
        }
      }
      v14 = 0;
LABEL_12:
      Native = (struct IUnknown *)(**v14)(v14, v6, a4, v6);
      if ( !Native )
        CFlat::Abandonment::Fail(v16);
      v7 = 1;
    }
  }
  else
  {
    Native = 0;
  }
LABEL_22:
  v28 = Native;
  v32 = a2;
  if ( a2 == Native )
  {
    CFlat::Contracts::Contract::Requires(v7 != 1);
  }
  else if ( Native && !v7 )
  {
    v23 = TlsGetValue(Cn::Context::s_tlsStorage);
    v24 = CFlat::EntryExit::ValidateCall(v23, v28, 1);
    CFlat::EntryExit::OnBeginCallToNative(v23);
    v25 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v30, &v28);
    CFlat::SehSafe::Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___(v23, v25);
    if ( a2 )
    {
      v24 = CFlat::EntryExit::ValidateCall(0, v32, 2);
      v26 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v30, &v32);
      CFlat::SehSafe::Execute__lambda_40503b817a990e38ee10d5ae7d7119b8___(v23, v26);
    }
    Cn::Context::NoContext_NotifyReturn((Cn::Context *)v23, v24);
  }
  else if ( a2 )
  {
    v22 = (__int64 *)TlsGetValue(Cn::Context::s_tlsStorage);
    if ( v32 )
      Cn::Com::DeferredRelease::CommonCreate(v22 + 10, (__int64)v32, 0, 1, 0);
  }
  return v28;
}

```

## disassembly

```asm
0x180020550  mov     [rsp-28h+arg_8], rbx
0x180020555  mov     [rsp-28h+arg_10], rsi
0x18002055a  push    rbp
0x18002055b  push    rdi
0x18002055c  push    r12
0x18002055e  push    r14
0x180020560  push    r15
0x180020562  mov     rbp, rsp
0x180020565  sub     rsp, 60h
0x180020569  mov     r12, r9
0x18002056c  mov     rdi, rdx
0x18002056f  mov     rsi, rcx
0x180020572  xor     bl, bl
0x180020574  test    rcx, rcx
0x180020577  jz      loc_1800206A7
0x18002057d  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x180020584  cmp     [rcx+8], rax
0x180020588  jz      loc_1800207C2
0x18002058e  test    rdx, rdx
0x180020591  jnz     loc_18002061C
0x180020597  mov     r8, [rsi+8]
0x18002059b  xor     edx, edx
0x18002059d  movzx   r9d, word ptr [r8]
0x1800205a1  lea     r10, ?TypeId$@IImplementsComInterface@CFlat@@2U?$InterfaceTypeIdField@VIImplementsComInterface@CFlat@@$0A@$0A@@2@B; CFlat::InterfaceTypeIdField<CFlat::IImplementsComInterface,0,0> const CFlat::IImplementsComInterface::TypeId$
0x1800205a8  cmp     edx, r9d
0x1800205ab  jge     short loc_180020616
0x1800205ad  movzx   eax, word ptr [r8]
0x1800205b1  movsxd  rcx, edx
0x1800205b4  sub     rcx, rax
0x1800205b7  add     rcx, rcx
0x1800205ba  cmp     r10, [r8+rcx*8]
0x1800205be  jnz     short loc_18002060A
0x1800205c0  cmp     qword ptr [r8+rcx*8+8], 0
0x1800205c6  jz      short loc_180020616
0x1800205c8  xor     edx, edx
0x1800205ca  cmp     edx, r9d
0x1800205cd  jge     short loc_180020612
0x1800205cf  movzx   eax, word ptr [r8]
0x1800205d3  movsxd  rcx, edx
0x1800205d6  sub     rcx, rax
0x1800205d9  add     rcx, rcx
0x1800205dc  cmp     r10, [r8+rcx*8]
0x1800205e0  jnz     short loc_18002060E
0x1800205e2  mov     rcx, [r8+rcx*8+8]
0x1800205e7  mov     rax, [rcx]
0x1800205ea  mov     r9, rsi
0x1800205ed  mov     r8, r12
0x1800205f0  mov     rdx, rsi
0x1800205f3  mov     rax, [rax]
0x1800205f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205fb  test    rax, rax
0x1800205fe  jnz     loc_1800207D9
0x180020604  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002060a  inc     edx
0x18002060c  jmp     short loc_1800205A8
0x18002060e  inc     edx
0x180020610  jmp     short loc_1800205CA
0x180020612  xor     ecx, ecx; char16_t *
0x180020614  jmp     short loc_1800205E7
0x180020616  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002061c  mov     [rbp+var_30], 0
0x180020624  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002062a  call    cs:__imp_TlsGetValue
0x180020630  mov     r14, rax
0x180020633  xor     r8d, r8d; int
0x180020636  mov     rdx, rdi; void *
0x180020639  mov     rcx, rax; void *
0x18002063c  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x180020641  mov     r15, rax
0x180020644  mov     rcx, r14; void *
0x180020647  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18002064c  lea     rax, [rbp+var_30]
0x180020650  mov     [rbp+var_28], rax
0x180020654  mov     [rbp+var_20], rdi
0x180020658  mov     dword ptr [rbp+arg_0], 0
0x18002065f  lea     r9, [rbp+var_28]
0x180020663  lea     r8, [rbp+var_20]
0x180020667  lea     rdx, [rbp+arg_0]
0x18002066b  lea     rcx, [rbp+var_18]
0x18002066f  call    _lambda_f7e478493cd4c7e6a5c3d3065f952319____lambda_f7e478493cd4c7e6a5c3d3065f952319_
0x180020674  mov     rdx, rax
0x180020677  mov     rcx, r14
0x18002067a  call    CFlat__SehSafe__Execute__lambda_f7e478493cd4c7e6a5c3d3065f952319___
0x18002067f  cmp     dword ptr [rbp+arg_0], 0
0x180020683  jnz     loc_18002071E
0x180020689  mov     rax, [rbp+var_30]
0x18002068d  cmp     [rax+18h], rsi
0x180020691  jnz     loc_18002071E
0x180020697  mov     rdx, r15; void *
0x18002069a  mov     rcx, r14; this
0x18002069d  call    ?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z; Cn::Context::NoContext_NotifyReturn(void *)
0x1800206a2  mov     rax, rdi
0x1800206a5  jmp     short loc_1800206A9
0x1800206a7  xor     eax, eax
0x1800206a9  mov     [rbp+var_30], rax
0x1800206ad  mov     [rbp+arg_0], rdi
0x1800206b1  cmp     rdi, rax
0x1800206b4  jz      loc_1800207B3
0x1800206ba  test    rax, rax
0x1800206bd  jz      short loc_1800206EB
0x1800206bf  test    bl, bl
0x1800206c1  jnz     short loc_1800206EB
0x1800206c3  mov     al, 1
0x1800206c5  test    al, al
0x1800206c7  jnz     short loc_18002072E
0x1800206c9  test    rdi, rdi
0x1800206cc  jnz     short loc_1800206EF
0x1800206ce  mov     rax, [rbp+var_30]
0x1800206d2  lea     r11, [rsp+60h+var_s0]
0x1800206d7  mov     rbx, [r11+38h]
0x1800206db  mov     rsi, [r11+40h]
0x1800206df  mov     rsp, r11
0x1800206e2  pop     r15
0x1800206e4  pop     r14
0x1800206e6  pop     r12
0x1800206e8  pop     rdi
0x1800206e9  pop     rbp
0x1800206ea  retn
0x1800206eb  xor     al, al
0x1800206ed  jmp     short loc_1800206C5
0x1800206ef  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800206f5  call    cs:__imp_TlsGetValue
0x1800206fb  mov     rdx, [rbp+arg_0]
0x1800206ff  test    rdx, rdx
0x180020702  jz      short loc_1800206CE
0x180020704  lea     rcx, [rax+50h]
0x180020708  mov     [rsp+60h+var_40], 0
0x180020711  mov     r9b, 1
0x180020714  xor     r8d, r8d
0x180020717  call    ?CommonCreate@DeferredRelease@Com@Cn@@AEAAXPEAUIUnknown@@P6AXPEAX@ZUDeferredAction@123@1@Z; Cn::Com::DeferredRelease::CommonCreate(IUnknown *,void (*)(void *),Cn::Com::DeferredRelease::DeferredAction,void *)
0x18002071c  jmp     short loc_1800206CE
0x18002071e  mov     rdx, r15; void *
0x180020721  mov     rcx, r14; this
0x180020724  call    ?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z; Cn::Context::NoContext_NotifyReturn(void *)
0x180020729  jmp     loc_180020597
0x18002072e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180020734  call    cs:__imp_TlsGetValue
0x18002073a  mov     rbx, rax
0x18002073d  mov     r8d, 1; int
0x180020743  mov     rdx, [rbp+var_30]; void *
0x180020747  mov     rcx, rax; void *
0x18002074a  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18002074f  mov     rsi, rax
0x180020752  mov     rcx, rbx; void *
0x180020755  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18002075a  lea     rdx, [rbp+var_30]
0x18002075e  lea     rcx, [rbp+var_20]
0x180020762  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180020767  mov     rdx, rax
0x18002076a  mov     rcx, rbx
0x18002076d  call    CFlat__SehSafe__Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___
0x180020772  test    rdi, rdi
0x180020775  jz      short loc_1800207A3
0x180020777  mov     r8d, 2; int
0x18002077d  mov     rdx, [rbp+arg_0]; void *
0x180020781  xor     ecx, ecx; void *
0x180020783  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x180020788  mov     rsi, rax
0x18002078b  lea     rdx, [rbp+arg_0]
0x18002078f  lea     rcx, [rbp+var_20]
0x180020793  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180020798  mov     rdx, rax
0x18002079b  mov     rcx, rbx
0x18002079e  call    CFlat__SehSafe__Execute__lambda_40503b817a990e38ee10d5ae7d7119b8___
0x1800207a3  mov     rdx, rsi; void *
0x1800207a6  mov     rcx, rbx; this
0x1800207a9  call    ?NoContext_NotifyReturn@Context@Cn@@QEAAXPEAX@Z; Cn::Context::NoContext_NotifyReturn(void *)
0x1800207ae  jmp     loc_1800206CE
0x1800207b3  xor     bl, 1
0x1800207b6  mov     cl, bl; bool
0x1800207b8  call    ?Requires@Contract@Contracts@CFlat@@SAX_N@Z; CFlat::Contracts::Contract::Requires(bool)
0x1800207bd  jmp     loc_1800206CE
0x1800207c2  mov     rdx, r8; struct CFlat::ComInterfaceTypeId *
0x1800207c5  call    ?GetNativeInterface$@ComImportAdapter@CFlat@@QEAAPEAXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetNativeInterface$(CFlat::ComInterfaceTypeId const *)
0x1800207ca  test    rax, rax
0x1800207cd  jnz     loc_1800206A9
0x1800207d3  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800207d9  mov     bl, 1
0x1800207db  jmp     loc_1800206A9
```

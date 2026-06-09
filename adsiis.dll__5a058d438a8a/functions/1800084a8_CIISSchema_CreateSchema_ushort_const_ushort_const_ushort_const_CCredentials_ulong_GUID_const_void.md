# CIISSchema::CreateSchema(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x1800084a8`
- end: `0x180008595`
- name: `?CreateSchema@CIISSchema@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CCredentials *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015564`

## callees

- `0x180008144`
- `0x18000816c`
- `0x1800084a8`
- `0x18001364c`
- `0x1800148a0`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x180008500`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180008500`

## pseudocode

```c
__int64 __fastcall CIISSchema::CreateSchema(
        const unsigned __int16 *a1,
        wchar_t *a2,
        wchar_t *a3,
        struct CCredentials *a4,
        unsigned int a5,
        struct _GUID *a6,
        void **a7)
{
  int SchemaObject; // eax
  unsigned int v11; // edx
  struct _GUID *v12; // rbx
  int inited; // edi
  LPWSTR v14; // rax
  const unsigned __int16 *v16; // [rsp+20h] [rbp-48h]

  a6 = 0;
  SchemaObject = CIISSchema::AllocateSchemaObject((struct CIISSchema **)&a6, a4);
  v12 = a6;
  inited = SchemaObject;
  if ( SchemaObject >= 0 )
  {
    inited = InitServerInfo(
               (struct CCredentials *)&a6[8],
               a1,
               (struct IMSAdminBaseW **)&a6[7],
               (struct IIsSchema **)a6[7].Data4);
    if ( inited >= 0 )
    {
      v14 = AllocADsStr(a1);
      *(_QWORD *)v12[6].Data4 = v14;
      if ( v14 )
      {
        inited = CCoreADsObject::InitializeCoreObject(
                   (unsigned __int16 **)v12,
                   a2,
                   a3,
                   (wchar_t *)L"Schema",
                   v16,
                   &CLSID_IISSchema,
                   1u);
        if ( inited >= 0 )
        {
          inited = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))&v12[4].Data1)(
                     (__int64)&v12[4],
                     &IID_IUnknown,
                     a7);
          if ( inited >= 0 )
          {
            (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v12[4].Data1 + 16LL))(v12 + 4);
            return (unsigned int)inited;
          }
        }
      }
      else
      {
        inited = -2147024882;
      }
    }
  }
  if ( v12 )
    CIISSchema::`scalar deleting destructor'((CIISSchema *)v12, v11);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800084a8  mov     rax, rsp
0x1800084ab  push    rbx
0x1800084ac  push    rbp
0x1800084ad  push    rsi
0x1800084ae  push    rdi
0x1800084af  push    r14
0x1800084b1  sub     rsp, 40h
0x1800084b5  mov     r14, rdx
0x1800084b8  mov     qword ptr [rax+30h], 0
0x1800084c0  mov     rsi, rcx
0x1800084c3  mov     rdx, r9; struct CCredentials *
0x1800084c6  lea     rcx, [rax+30h]; struct CIISSchema **
0x1800084ca  mov     rbp, r8
0x1800084cd  call    ?AllocateSchemaObject@CIISSchema@@SAJPEAPEAV1@AEAVCCredentials@@@Z; CIISSchema::AllocateSchemaObject(CIISSchema * *,CCredentials &)
0x1800084d2  mov     rbx, [rsp+68h+arg_28]
0x1800084da  mov     edi, eax
0x1800084dc  test    eax, eax
0x1800084de  js      short loc_180008514
0x1800084e0  lea     r9, [rbx+78h]; struct IIsSchema **
0x1800084e4  mov     rdx, rsi; unsigned __int16 *
0x1800084e7  lea     r8, [rbx+70h]; struct IMSAdminBaseW **
0x1800084eb  lea     rcx, [rbx+80h]; struct CCredentials *
0x1800084f2  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x1800084f7  mov     edi, eax
0x1800084f9  test    eax, eax
0x1800084fb  js      short loc_180008514
0x1800084fd  mov     rcx, rsi; pStr
0x180008500  call    cs:__imp_AllocADsStr
0x180008506  mov     [rbx+68h], rax
0x18000850a  test    rax, rax
0x18000850d  jnz     short loc_18000852E
0x18000850f  mov     edi, 8007000Eh
0x180008514  test    rbx, rbx
0x180008517  jz      short loc_180008521
0x180008519  mov     rcx, rbx; this
0x18000851c  call    ??_GCIISSchema@@QEAAPEAXI@Z; CIISSchema::`scalar deleting destructor'(uint)
0x180008521  mov     eax, edi
0x180008523  add     rsp, 40h
0x180008527  pop     r14
0x180008529  pop     rdi
0x18000852a  pop     rsi
0x18000852b  pop     rbp
0x18000852c  pop     rbx
0x18000852d  retn
0x18000852e  lea     rax, CLSID_IISSchema
0x180008535  mov     [rsp+68h+var_38], 1; unsigned int
0x18000853d  lea     r9, aSchema_1; "Schema"
0x180008544  mov     [rsp+68h+var_40], rax; struct _GUID *
0x180008549  mov     r8, rbp; unsigned __int16 *
0x18000854c  mov     rdx, r14; unsigned __int16 *
0x18000854f  mov     rcx, rbx; this
0x180008552  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x180008557  mov     edi, eax
0x180008559  test    eax, eax
0x18000855b  js      short loc_180008514
0x18000855d  mov     r8, [rsp+68h+arg_30]
0x180008565  lea     rsi, [rbx+40h]
0x180008569  mov     rax, [rsi]
0x18000856c  lea     rdx, IID_IUnknown
0x180008573  mov     rcx, rsi
0x180008576  mov     rax, [rax]
0x180008579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857e  mov     edi, eax
0x180008580  test    eax, eax
0x180008582  js      short loc_180008514
0x180008584  mov     rax, [rsi]
0x180008587  mov     rcx, rsi
0x18000858a  mov     rax, [rax+10h]
0x18000858e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008593  jmp     short loc_180008521
```

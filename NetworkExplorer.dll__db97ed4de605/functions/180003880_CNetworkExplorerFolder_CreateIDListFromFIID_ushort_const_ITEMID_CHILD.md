# CNetworkExplorerFolder::_CreateIDListFromFIID(ushort const *,_ITEMID_CHILD * *)

- ea: `0x180003880`
- end: `0x180003946`
- name: `?_CreateIDListFromFIID@CNetworkExplorerFolder@@AEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const unsigned __int16 *, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800037e4`

## callees

- `0x180003880`
- `0x180010010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180003934`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180003934`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_CreateIDListFromFIID(
        CNetworkExplorerFolder *this,
        const unsigned __int16 *a2,
        struct _ITEMID_CHILD **a3)
{
  void **ppv; // rdi
  void *v6; // rdi
  HRESULT Instance; // ebx
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  ppv = (void **)((char *)this + 112);
  *a3 = 0;
  if ( *((_QWORD *)this + 14)
    || (Instance = SHCoCreateInstance(0, &CLSID_NetworkItemFactory, 0, &GUID_72400b6a_d4d1_4318_99f8_5201c05db416, ppv),
        Instance >= 0) )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)*ppv + 8LL))(*ppv);
    v6 = *ppv;
    v9 = 0;
    Instance = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v6 + 72LL))(
                 v6,
                 a2,
                 &v9);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(void *, __int64, struct _ITEMID_CHILD **))(*(_QWORD *)v6 + 104LL))(
                   v6,
                   v9,
                   a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003880  push    rbx
0x180003882  push    rbp
0x180003883  push    rsi
0x180003884  push    rdi
0x180003885  sub     rsp, 38h
0x180003889  lea     rdi, [rcx+70h]
0x18000388d  mov     qword ptr [r8], 0
0x180003894  cmp     qword ptr [rdi], 0
0x180003898  mov     rsi, r8
0x18000389b  mov     rbp, rdx
0x18000389e  jz      short loc_18000391C
0x1800038a0  mov     rcx, [rdi]
0x1800038a3  mov     rax, [rcx]
0x1800038a6  mov     rax, [rax+8]
0x1800038aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038af  mov     rdi, [rdi]
0x1800038b2  lea     r8, [rsp+58h+arg_0]
0x1800038b7  mov     rdx, rbp
0x1800038ba  mov     [rsp+58h+arg_0], 0
0x1800038c3  mov     rcx, rdi
0x1800038c6  mov     rax, [rdi]
0x1800038c9  mov     rax, [rax+48h]
0x1800038cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d2  mov     ebx, eax
0x1800038d4  test    eax, eax
0x1800038d6  js      short loc_180003902
0x1800038d8  mov     rax, [rdi]
0x1800038db  mov     r8, rsi
0x1800038de  mov     rdx, [rsp+58h+arg_0]
0x1800038e3  mov     rcx, rdi
0x1800038e6  mov     rax, [rax+68h]
0x1800038ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ef  mov     rcx, [rsp+58h+arg_0]
0x1800038f4  mov     ebx, eax
0x1800038f6  mov     rax, [rcx]
0x1800038f9  mov     rax, [rax+10h]
0x1800038fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003902  mov     rax, [rdi]
0x180003905  mov     rcx, rdi
0x180003908  mov     rax, [rax+10h]
0x18000390c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003911  mov     eax, ebx
0x180003913  add     rsp, 38h
0x180003917  pop     rdi
0x180003918  pop     rsi
0x180003919  pop     rbp
0x18000391a  pop     rbx
0x18000391b  retn
0x18000391c  lea     r9, _GUID_72400b6a_d4d1_4318_99f8_5201c05db416; riid
0x180003923  mov     [rsp+58h+ppv], rdi; ppv
0x180003928  xor     r8d, r8d; pUnkOuter
0x18000392b  lea     rdx, CLSID_NetworkItemFactory; pclsid
0x180003932  xor     ecx, ecx; pszCLSID
0x180003934  call    cs:__imp_SHCoCreateInstance
0x18000393a  mov     ebx, eax
0x18000393c  test    eax, eax
0x18000393e  jns     loc_1800038A0
0x180003944  jmp     short loc_180003911
```

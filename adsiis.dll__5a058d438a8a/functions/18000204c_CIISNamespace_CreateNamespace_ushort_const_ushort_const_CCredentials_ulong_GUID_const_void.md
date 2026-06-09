# CIISNamespace::CreateNamespace(ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x18000204c`
- end: `0x180002108`
- name: `?CreateNamespace@CIISNamespace@@SAJPEBG0AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `188`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, struct CCredentials *, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cc0`
- `0x180015664`

## callees

- `0x180001e78`
- `0x180001ed0`
- `0x18000204c`
- `0x1800148a0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISNamespace::CreateNamespace(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct CCredentials *a3,
        __int64 a4,
        const struct _GUID *a5,
        void **a6)
{
  int v6; // eax
  unsigned int v7; // edx
  CCoreADsObject *v8; // rdi
  int v9; // ebx
  const unsigned __int16 *v11; // [rsp+20h] [rbp-28h]
  CCoreADsObject *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  v6 = CIISNamespace::AllocateNamespaceObject(a3, &v12);
  v8 = v12;
  v9 = v6;
  if ( v6 < 0
    || (v9 = CCoreADsObject::InitializeCoreObject(
               (unsigned __int16 **)v12,
               (wchar_t *)L"ADs:",
               (wchar_t *)L"IIS:",
               (wchar_t *)L"Namespace",
               v11,
               &CLSID_IISNamespace,
               1u),
        v9 < 0)
    || (v9 = (**((__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v8 + 8))((__int64)v8 + 64, a5, a6),
        v9 < 0) )
  {
    if ( v8 )
      CIISNamespace::`scalar deleting destructor'(v8, v7);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v8 + 8) + 16LL))((__int64)v8 + 64);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000204c  mov     rax, rsp
0x18000204f  mov     [rax+8], rbx
0x180002053  mov     [rax+18h], rsi
0x180002057  mov     [rax+10h], rdx
0x18000205b  push    rdi
0x18000205c  sub     rsp, 40h
0x180002060  lea     rdx, [rax+10h]; struct CIISNamespace **
0x180002064  mov     qword ptr [rax+10h], 0
0x18000206c  mov     rcx, r8; struct CCredentials *
0x18000206f  call    ?AllocateNamespaceObject@CIISNamespace@@SAJAEAVCCredentials@@PEAPEAV1@@Z; CIISNamespace::AllocateNamespaceObject(CCredentials &,CIISNamespace * *)
0x180002074  mov     rdi, [rsp+48h+arg_8]
0x180002079  mov     ebx, eax
0x18000207b  test    eax, eax
0x18000207d  js      short loc_1800020E9
0x18000207f  lea     rax, CLSID_IISNamespace
0x180002086  mov     [rsp+48h+var_18], 1; unsigned int
0x18000208e  lea     r9, aNamespace; "Namespace"
0x180002095  mov     [rsp+48h+var_20], rax; struct _GUID *
0x18000209a  lea     r8, aIis_0; "IIS:"
0x1800020a1  mov     rcx, rdi; this
0x1800020a4  lea     rdx, aAds; "ADs:"
0x1800020ab  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x1800020b0  mov     ebx, eax
0x1800020b2  test    eax, eax
0x1800020b4  js      short loc_1800020E9
0x1800020b6  mov     r8, [rsp+48h+arg_28]
0x1800020bb  lea     rsi, [rdi+40h]
0x1800020bf  mov     rax, [rsi]
0x1800020c2  mov     rcx, rsi
0x1800020c5  mov     rdx, [rsp+48h+arg_20]
0x1800020ca  mov     rax, [rax]
0x1800020cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020d2  mov     ebx, eax
0x1800020d4  test    eax, eax
0x1800020d6  js      short loc_1800020E9
0x1800020d8  mov     rax, [rsi]
0x1800020db  mov     rcx, rsi
0x1800020de  mov     rax, [rax+10h]
0x1800020e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e7  jmp     short loc_1800020F6
0x1800020e9  test    rdi, rdi
0x1800020ec  jz      short loc_1800020F6
0x1800020ee  mov     rcx, rdi; this
0x1800020f1  call    ??_GCIISNamespace@@QEAAPEAXI@Z; CIISNamespace::`scalar deleting destructor'(uint)
0x1800020f6  mov     rsi, [rsp+48h+arg_10]
0x1800020fb  mov     eax, ebx
0x1800020fd  mov     rbx, [rsp+48h+arg_0]
0x180002102  add     rsp, 40h
0x180002106  pop     rdi
0x180002107  retn
```

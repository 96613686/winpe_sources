# CIISSyntax::CreateSyntax(ushort const *,_SyntaxInfo *,ulong,_GUID const &,void * *)

- ea: `0x18000a0a8`
- end: `0x18000a15d`
- name: `?CreateSyntax@CIISSyntax@@SAJPEBGPEAU_SyntaxInfo@@KAEBU_GUID@@PEAPEAX@Z`
- size: `181`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, struct _SyntaxInfo *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d28c`
- `0x180015d04`

## callees

- `0x1800094d0`
- `0x18000978c`
- `0x18000a0a8`
- `0x1800148a0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIISSyntax::CreateSyntax(wchar_t *a1, wchar_t **a2, __int64 a3, const struct _GUID *a4, void **a5)
{
  int v8; // eax
  unsigned int v9; // edx
  CCoreADsObject *v10; // rbx
  int v11; // edi
  const unsigned __int16 *v13; // [rsp+20h] [rbp-58h]
  CCoreADsObject *v14; // [rsp+40h] [rbp-38h] BYREF

  v14 = 0;
  v8 = CIISSyntax::AllocateSyntaxObject(&v14);
  v10 = v14;
  v11 = v8;
  if ( v8 < 0
    || (v11 = CCoreADsObject::InitializeCoreObject(
                (unsigned __int16 **)v14,
                a1,
                *a2,
                (wchar_t *)L"Syntax",
                v13,
                &CLSID_IISSyntax,
                1u),
        v11 < 0)
    || (*((_DWORD *)v10 + 22) = *((_DWORD *)a2 + 3),
        v11 = (**((__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v10 + 8))((__int64)v10 + 64, a4, a5),
        v11 < 0) )
  {
    if ( v10 )
      CIISSyntax::`scalar deleting destructor'(v10, v9);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v10 + 8) + 16LL))((__int64)v10 + 64);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a0a8  push    rbx
0x18000a0aa  push    rbp
0x18000a0ab  push    rsi
0x18000a0ac  push    rdi
0x18000a0ad  push    r14
0x18000a0af  sub     rsp, 50h
0x18000a0b3  mov     rbp, rcx
0x18000a0b6  mov     [rsp+78h+var_38], 0
0x18000a0bf  lea     rcx, [rsp+78h+var_38]; struct CIISSyntax **
0x18000a0c4  mov     r14, r9
0x18000a0c7  mov     rsi, rdx
0x18000a0ca  call    ?AllocateSyntaxObject@CIISSyntax@@SAJPEAPEAV1@@Z; CIISSyntax::AllocateSyntaxObject(CIISSyntax * *)
0x18000a0cf  mov     rbx, [rsp+78h+var_38]
0x18000a0d4  mov     edi, eax
0x18000a0d6  test    eax, eax
0x18000a0d8  js      short loc_18000A143
0x18000a0da  mov     r8, [rsi]; unsigned __int16 *
0x18000a0dd  lea     rax, CLSID_IISSyntax
0x18000a0e4  mov     [rsp+78h+var_48], 1; unsigned int
0x18000a0ec  lea     r9, aSyntax; "Syntax"
0x18000a0f3  mov     rdx, rbp; unsigned __int16 *
0x18000a0f6  mov     [rsp+78h+var_50], rax; struct _GUID *
0x18000a0fb  mov     rcx, rbx; this
0x18000a0fe  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x18000a103  mov     edi, eax
0x18000a105  test    eax, eax
0x18000a107  js      short loc_18000A143
0x18000a109  mov     eax, [rsi+0Ch]
0x18000a10c  mov     rdx, r14
0x18000a10f  mov     r8, [rsp+78h+arg_20]
0x18000a117  lea     rsi, [rbx+40h]
0x18000a11b  mov     [rbx+58h], eax
0x18000a11e  mov     rcx, rsi
0x18000a121  mov     rax, [rsi]
0x18000a124  mov     rax, [rax]
0x18000a127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12c  mov     edi, eax
0x18000a12e  test    eax, eax
0x18000a130  js      short loc_18000A143
0x18000a132  mov     rax, [rsi]
0x18000a135  mov     rcx, rsi
0x18000a138  mov     rax, [rax+10h]
0x18000a13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a141  jmp     short loc_18000A150
0x18000a143  test    rbx, rbx
0x18000a146  jz      short loc_18000A150
0x18000a148  mov     rcx, rbx; this
0x18000a14b  call    ??_GCIISSyntax@@QEAAPEAXI@Z; CIISSyntax::`scalar deleting destructor'(uint)
0x18000a150  mov     eax, edi
0x18000a152  add     rsp, 50h
0x18000a156  pop     r14
0x18000a158  pop     rdi
0x18000a159  pop     rsi
0x18000a15a  pop     rbp
0x18000a15b  pop     rbx
0x18000a15c  retn
```

# CASFUnknownContainer::RemoveObject(_GUID const &,ulong,IASFUnknown * *)

- ea: `0x18001eff0`
- end: `0x18001f081`
- name: `?RemoveObject@CASFUnknownContainer@@UEAAJAEBU_GUID@@KPEAPEAUIASFUnknown@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(CASFUnknownContainer *__hidden this, const struct _GUID *, unsigned int, struct IASFUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001df5c`
- `0x18001e2d4`
- `0x18001ef88`
- `0x18001eff0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFUnknownContainer::RemoveObject(
        CASFUnknownContainer *this,
        const struct _GUID *a2,
        unsigned int a3,
        struct IASFUnknown **a4)
{
  int Object; // esi
  char *v7; // rbx
  struct IASFUnknown *v8; // rax
  __int64 v9; // rax
  unsigned int v11[6]; // [rsp+20h] [rbp-18h] BYREF

  v11[0] = 0;
  Object = CASFUnknownContainer::FindObject(this, a2, a3, v11);
  if ( Object >= 0 )
  {
    v7 = (char *)this + 16;
    if ( a4 )
    {
      v8 = (struct IASFUnknown *)CTDynArray<IASFUnknown *,20>::operator[](v7, v11[0]);
      *a4 = v8;
      (*(void (__fastcall **)(struct IASFUnknown *))(*(_QWORD *)v8 + 8LL))(v8);
    }
    v9 = CTDynArray<IASFUnknown *,20>::operator[](v7, v11[0]);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    CTDynArray<IASFUnknown *,20>::RemoveAt(v7, v11[0]);
  }
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x18001eff0  mov     rax, rsp
0x18001eff3  mov     [rax+8], rbx
0x18001eff7  mov     [rax+10h], rsi
0x18001effb  push    r14
0x18001effd  sub     rsp, 30h
0x18001f001  mov     r14, r9
0x18001f004  mov     dword ptr [rax-18h], 0
0x18001f00b  lea     r9, [rax-18h]; unsigned int *
0x18001f00f  mov     rbx, rcx
0x18001f012  call    ?FindObject@CASFUnknownContainer@@IEAAJAEBU_GUID@@KPEAK@Z; CASFUnknownContainer::FindObject(_GUID const &,ulong,ulong *)
0x18001f017  mov     esi, eax
0x18001f019  test    eax, eax
0x18001f01b  js      short loc_18001F06E
0x18001f01d  add     rbx, 10h
0x18001f021  test    r14, r14
0x18001f024  jz      short loc_18001F047
0x18001f026  mov     edx, [rsp+38h+var_18]
0x18001f02a  mov     rcx, rbx
0x18001f02d  call    ??A?$CTDynArray@PEAUIASFUnknown@@$0BE@@@QEBAPEAUIASFUnknown@@K@Z; CTDynArray<IASFUnknown *,20>::operator[](ulong)
0x18001f032  mov     [r14], rax
0x18001f035  mov     rdx, rax
0x18001f038  mov     rcx, [rax]
0x18001f03b  mov     rax, [rcx+8]
0x18001f03f  mov     rcx, rdx
0x18001f042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f047  mov     edx, [rsp+38h+var_18]
0x18001f04b  mov     rcx, rbx
0x18001f04e  call    ??A?$CTDynArray@PEAUIASFUnknown@@$0BE@@@QEBAPEAUIASFUnknown@@K@Z; CTDynArray<IASFUnknown *,20>::operator[](ulong)
0x18001f053  mov     rcx, rax
0x18001f056  mov     r8, [rax]
0x18001f059  mov     rax, [r8+10h]
0x18001f05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f062  mov     edx, [rsp+38h+var_18]
0x18001f066  mov     rcx, rbx
0x18001f069  call    ?RemoveAt@?$CTDynArray@PEAUIASFUnknown@@$0BE@@@QEAAHKK@Z; CTDynArray<IASFUnknown *,20>::RemoveAt(ulong,ulong)
0x18001f06e  mov     rbx, [rsp+38h+arg_0]
0x18001f073  mov     eax, esi
0x18001f075  mov     rsi, [rsp+38h+arg_8]
0x18001f07a  add     rsp, 30h
0x18001f07e  pop     r14
0x18001f080  retn
```

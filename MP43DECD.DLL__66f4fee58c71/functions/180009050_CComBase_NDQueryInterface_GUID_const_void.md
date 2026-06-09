# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x180009050`
- end: `0x18000909d`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006b40`

## callees

- `0x180009050`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180009050  sub     rsp, 28h
0x180009054  test    r8, r8
0x180009057  jnz     short loc_180009060
0x180009059  mov     eax, 80004003h
0x18000905e  jmp     short loc_180009098
0x180009060  mov     rax, [rdx]
0x180009063  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000906a  jnz     short loc_18000908C
0x18000906c  mov     rax, [rdx+8]
0x180009070  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009077  jnz     short loc_18000908C
0x180009079  mov     [r8], rcx
0x18000907c  mov     rax, [rcx]
0x18000907f  mov     rax, [rax+8]
0x180009083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009088  xor     eax, eax
0x18000908a  jmp     short loc_180009098
0x18000908c  mov     qword ptr [r8], 0
0x180009093  mov     eax, 80004002h
0x180009098  add     rsp, 28h
0x18000909c  retn
```

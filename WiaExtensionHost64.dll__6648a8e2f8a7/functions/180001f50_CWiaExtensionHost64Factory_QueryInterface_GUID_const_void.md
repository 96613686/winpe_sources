# CWiaExtensionHost64Factory::QueryInterface(_GUID const &,void * *)

- ea: `0x180001f50`
- end: `0x180001fba`
- name: `?QueryInterface@CWiaExtensionHost64Factory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(CWiaExtensionHost64Factory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001f50`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64Factory::QueryInterface(
        CWiaExtensionHost64Factory *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( *(_OWORD *)&IID_IUnknown == *(_OWORD *)a2
      || *(_QWORD *)&IID_IClassFactory.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)IID_IClassFactory.Data4 == *(_QWORD *)a2->Data4 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CWiaExtensionHost64Factory *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x180001f50  push    rbx
0x180001f52  sub     rsp, 20h
0x180001f56  xor     ebx, ebx
0x180001f58  test    r8, r8
0x180001f5b  jnz     short loc_180001F64
0x180001f5d  mov     ebx, 80004003h
0x180001f62  jmp     short loc_180001FB2
0x180001f64  mov     [r8], rbx
0x180001f67  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180001f6e  cmp     rax, [rdx]
0x180001f71  jnz     short loc_180001F80
0x180001f73  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180001f7a  cmp     rax, [rdx+8]
0x180001f7e  jz      short loc_180001F99
0x180001f80  mov     rax, qword ptr cs:IID_IClassFactory.Data1
0x180001f87  cmp     rax, [rdx]
0x180001f8a  jnz     short loc_180001FAD
0x180001f8c  mov     rax, qword ptr cs:IID_IClassFactory.Data4
0x180001f93  cmp     rax, [rdx+8]
0x180001f97  jnz     short loc_180001FAD
0x180001f99  mov     [r8], rcx
0x180001f9c  mov     rax, rcx
0x180001f9f  mov     rax, [rcx]
0x180001fa2  mov     rax, [rax+8]
0x180001fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fab  jmp     short loc_180001FB2
0x180001fad  mov     ebx, 80004002h
0x180001fb2  mov     eax, ebx
0x180001fb4  add     rsp, 20h
0x180001fb8  pop     rbx
0x180001fb9  retn
```

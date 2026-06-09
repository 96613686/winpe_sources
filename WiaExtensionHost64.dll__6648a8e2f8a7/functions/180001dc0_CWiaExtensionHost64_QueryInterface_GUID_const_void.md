# CWiaExtensionHost64::QueryInterface(_GUID const &,void * *)

- ea: `0x180001dc0`
- end: `0x180001e2a`
- name: `?QueryInterface@CWiaExtensionHost64@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(CWiaExtensionHost64 *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001dc0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWiaExtensionHost64::QueryInterface(CWiaExtensionHost64 *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( *(_OWORD *)&IID_IWIAExtensionHost64 == *(_OWORD *)a2
      || *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CWiaExtensionHost64 *))(*(_QWORD *)this + 8LL))(this);
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
0x180001dc0  push    rbx
0x180001dc2  sub     rsp, 20h
0x180001dc6  xor     ebx, ebx
0x180001dc8  test    r8, r8
0x180001dcb  jnz     short loc_180001DD4
0x180001dcd  mov     ebx, 80004003h
0x180001dd2  jmp     short loc_180001E22
0x180001dd4  mov     [r8], rbx
0x180001dd7  mov     rax, qword ptr cs:IID_IWIAExtensionHost64.Data1
0x180001dde  cmp     rax, [rdx]
0x180001de1  jnz     short loc_180001DF0
0x180001de3  mov     rax, qword ptr cs:IID_IWIAExtensionHost64.Data4
0x180001dea  cmp     rax, [rdx+8]
0x180001dee  jz      short loc_180001E09
0x180001df0  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180001df7  cmp     rax, [rdx]
0x180001dfa  jnz     short loc_180001E1D
0x180001dfc  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180001e03  cmp     rax, [rdx+8]
0x180001e07  jnz     short loc_180001E1D
0x180001e09  mov     [r8], rcx
0x180001e0c  mov     rax, rcx
0x180001e0f  mov     rax, [rcx]
0x180001e12  mov     rax, [rax+8]
0x180001e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e1b  jmp     short loc_180001E22
0x180001e1d  mov     ebx, 80004002h
0x180001e22  mov     eax, ebx
0x180001e24  add     rsp, 20h
0x180001e28  pop     rbx
0x180001e29  retn
```

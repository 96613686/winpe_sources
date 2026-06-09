# CMILCOMBase::InternalQueryInterface(_GUID const &,void * *)

- ea: `0x180009f30`
- end: `0x180009fad`
- name: `?InternalQueryInterface@CMILCOMBase@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `125`
- prototype: `__int64 __fastcall(CMILCOMBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008f24`
- `0x180009e04`
- `0x180009f20`
- `0x18000b410`
- `0x18000b420`
- `0x18002be80`

## callees

- `0x180009f30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMILCOMBase::InternalQueryInterface(CMILCOMBase *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 result; // rax
  unsigned int v6; // edi

  if ( !a3 )
    return 2147942487LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v4 )
  {
    *a3 = this;
    v6 = 0;
    goto LABEL_6;
  }
  result = (*(__int64 (__fastcall **)(CMILCOMBase *))(*(_QWORD *)this + 32LL))(this);
  v6 = result;
  if ( (int)result >= 0 )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    return v6;
  }
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180009f30  push    rbx
0x180009f32  sub     rsp, 20h
0x180009f36  mov     rbx, r8
0x180009f39  test    r8, r8
0x180009f3c  jz      short loc_180009FA6
0x180009f3e  mov     rax, [rdx]
0x180009f41  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180009f48  jnz     short loc_180009F55
0x180009f4a  mov     rax, [rdx+8]
0x180009f4e  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180009f55  mov     [rsp+28h+arg_0], rdi
0x180009f5a  test    rax, rax
0x180009f5d  jz      short loc_180009F8D
0x180009f5f  mov     rax, [rcx]
0x180009f62  mov     rax, [rax+20h]
0x180009f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f6b  mov     edi, eax
0x180009f6d  test    eax, eax
0x180009f6f  js      short loc_180009F94
0x180009f71  mov     rcx, [rbx]
0x180009f74  mov     rax, [rcx]
0x180009f77  mov     rax, [rax+8]
0x180009f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f80  mov     eax, edi
0x180009f82  mov     rdi, [rsp+28h+arg_0]
0x180009f87  add     rsp, 20h
0x180009f8b  pop     rbx
0x180009f8c  retn
0x180009f8d  mov     [r8], rcx
0x180009f90  xor     edi, edi
0x180009f92  jmp     short loc_180009F71
0x180009f94  mov     rdi, [rsp+28h+arg_0]
0x180009f99  mov     qword ptr [rbx], 0
0x180009fa0  add     rsp, 20h
0x180009fa4  pop     rbx
0x180009fa5  retn
0x180009fa6  mov     eax, 80070057h
0x180009fab  jmp     short loc_180009F87
```

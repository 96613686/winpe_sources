# Completion::QueryInterface(_GUID const &,void * *)

- ea: `0x140005720`
- end: `0x140005778`
- name: `?QueryInterface@Completion@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `88`
- prototype: `__int64 __fastcall(Completion *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005720`
- `0x140006590`

## pseudocode

```c
__int64 __fastcall Completion::QueryInterface(Completion *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_5b83c260_7386_11d2_b99b_0080c7e8daa5.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_5b83c260_7386_11d2_b99b_0080c7e8daa5.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(Completion *))(*(_QWORD *)this + 8LL))(this);
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
0x140005720  sub     rsp, 28h
0x140005724  mov     rax, [rdx]
0x140005727  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x14000572e  jnz     short loc_14000573D
0x140005730  mov     rax, [rdx+8]
0x140005734  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x14000573b  jz      short loc_140005756
0x14000573d  mov     rax, [rdx]
0x140005740  cmp     rax, qword ptr cs:_GUID_5b83c260_7386_11d2_b99b_0080c7e8daa5.Data1
0x140005747  jnz     short loc_14000576A
0x140005749  mov     rax, [rdx+8]
0x14000574d  cmp     rax, qword ptr cs:_GUID_5b83c260_7386_11d2_b99b_0080c7e8daa5.Data4
0x140005754  jnz     short loc_14000576A
0x140005756  mov     [r8], rcx
0x140005759  mov     rax, [rcx]
0x14000575c  mov     rax, [rax+8]
0x140005760  call    cs:__guard_dispatch_icall_fptr
0x140005766  xor     eax, eax
0x140005768  jmp     short loc_140005773
0x14000576a  and     qword ptr [r8], 0
0x14000576e  mov     eax, 80004002h
0x140005773  add     rsp, 28h
0x140005777  retn
```

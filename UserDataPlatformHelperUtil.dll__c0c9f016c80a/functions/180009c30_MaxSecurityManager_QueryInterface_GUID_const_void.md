# MaxSecurityManager::QueryInterface(_GUID const &,void * *)

- ea: `0x180009c30`
- end: `0x180009c99`
- name: `?QueryInterface@MaxSecurityManager@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(MaxSecurityManager *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009c30`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall MaxSecurityManager::QueryInterface(MaxSecurityManager *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(MaxSecurityManager *))(*(_QWORD *)this + 8LL))(this);
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
0x180009c30  sub     rsp, 28h
0x180009c34  test    r8, r8
0x180009c37  jnz     short loc_180009C40
0x180009c39  mov     eax, 80070057h
0x180009c3e  jmp     short loc_180009C94
0x180009c40  mov     rax, [rdx]
0x180009c43  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009c4a  jnz     short loc_180009C59
0x180009c4c  mov     rax, [rdx+8]
0x180009c50  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009c57  jz      short loc_180009C72
0x180009c59  mov     rax, [rdx]
0x180009c5c  cmp     rax, qword ptr cs:_GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data1
0x180009c63  jnz     short loc_180009C88
0x180009c65  mov     rax, [rdx+8]
0x180009c69  cmp     rax, qword ptr cs:_GUID_f164edf1_cc7c_4f0d_9a94_34222625c393.Data4
0x180009c70  jnz     short loc_180009C88
0x180009c72  mov     [r8], rcx
0x180009c75  mov     rax, rcx
0x180009c78  mov     rax, [rcx]
0x180009c7b  mov     rax, [rax+8]
0x180009c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c84  xor     eax, eax
0x180009c86  jmp     short loc_180009C94
0x180009c88  mov     qword ptr [r8], 0
0x180009c8f  mov     eax, 80004002h
0x180009c94  add     rsp, 28h
0x180009c98  retn
```

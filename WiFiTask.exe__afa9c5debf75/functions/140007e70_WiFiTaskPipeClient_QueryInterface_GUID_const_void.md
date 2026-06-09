# WiFiTaskPipeClient::QueryInterface(_GUID const &,void * *)

- ea: `0x140007e70`
- end: `0x140007eca`
- name: `?QueryInterface@WiFiTaskPipeClient@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140007e70`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::QueryInterface(WiFiTaskPipeClient *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_0396a428_1eae_4ad7_8965_df041c68caa8.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_0396a428_1eae_4ad7_8965_df041c68caa8.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(WiFiTaskPipeClient *))(*(_QWORD *)this + 8LL))(this);
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
0x140007e70  sub     rsp, 28h
0x140007e74  mov     rax, [rdx]
0x140007e77  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x140007e7e  jnz     short loc_140007E8D
0x140007e80  mov     rax, [rdx+8]
0x140007e84  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x140007e8b  jz      short loc_140007EA6
0x140007e8d  mov     rax, [rdx]
0x140007e90  cmp     rax, qword ptr cs:_GUID_0396a428_1eae_4ad7_8965_df041c68caa8.Data1
0x140007e97  jnz     short loc_140007EB9
0x140007e99  mov     rax, [rdx+8]
0x140007e9d  cmp     rax, qword ptr cs:_GUID_0396a428_1eae_4ad7_8965_df041c68caa8.Data4
0x140007ea4  jnz     short loc_140007EB9
0x140007ea6  mov     [r8], rcx
0x140007ea9  mov     rax, [rcx]
0x140007eac  mov     rax, [rax+8]
0x140007eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007eb5  xor     eax, eax
0x140007eb7  jmp     short loc_140007EC5
0x140007eb9  mov     qword ptr [r8], 0
0x140007ec0  mov     eax, 80004002h
0x140007ec5  add     rsp, 28h
0x140007ec9  retn
```

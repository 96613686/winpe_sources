# CloudDataTransformResult::`scalar deleting destructor'(uint)

- ea: `0x1800130f0`
- end: `0x180013147`
- name: `??_GCloudDataTransformResult@@UEAAPEAXI@Z`
- size: `87`
- prototype: `void *__fastcall(CloudDataTransformResult *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800130f0`
- `0x18002ca90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001313f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001313f`

## pseudocode

```c
CloudDataTransformResult *__fastcall CloudDataTransformResult::`scalar deleting destructor'(
        CloudDataTransformResult *this,
        char a2)
{
  void *v4; // rcx
  void *v5; // rcx

  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    CoTaskMemFree(v5);
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800130f0  mov     [rsp+arg_0], rbx
0x1800130f5  push    rdi
0x1800130f6  sub     rsp, 20h
0x1800130fa  mov     rbx, rcx
0x1800130fd  mov     edi, edx
0x1800130ff  mov     rcx, [rcx+20h]; pv
0x180013103  test    rcx, rcx
0x180013106  jz      short loc_18001310E
0x180013108  call    cs:__imp_CoTaskMemFree
0x18001310e  mov     rcx, [rbx+18h]; pv
0x180013112  test    rcx, rcx
0x180013115  jnz     short loc_18001313F
0x180013117  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18001311e  test    dil, 1
0x180013122  jz      short loc_180013131
0x180013124  mov     edx, 28h ; '('
0x180013129  mov     rcx, rbx; Block
0x18001312c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013131  mov     rax, rbx
0x180013134  mov     rbx, [rsp+28h+arg_0]
0x180013139  add     rsp, 20h
0x18001313d  pop     rdi
0x18001313e  retn
0x18001313f  call    cs:__imp_CoTaskMemFree
0x180013145  jmp     short loc_180013117
```

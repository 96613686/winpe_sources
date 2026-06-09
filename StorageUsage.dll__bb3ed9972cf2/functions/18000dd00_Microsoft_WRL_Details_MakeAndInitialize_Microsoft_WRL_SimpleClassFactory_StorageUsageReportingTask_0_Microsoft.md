# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,>(Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0> * *)

- ea: `0x18000dd00`
- end: `0x18000dd90`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@12@@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000db80`

## callees

- `0x180005158`
- `0x18000dd00`
- `0x18000fce4`
- `0x1800100cc`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>,>(
        __int64 *a1)
{
  void *v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    v4 = Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>::SimpleClassFactory<StorageUsageReportingTask,0>(v2);
    v5 = v4;
    v7 = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *a1 = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(&v7);
  return v3;
}

```

## disassembly

```asm
0x18000dd00  mov     [rsp+arg_8], rbx
0x18000dd05  push    rdi
0x18000dd06  sub     rsp, 20h
0x18000dd0a  mov     rdi, rcx
0x18000dd0d  mov     qword ptr [rcx], 0
0x18000dd14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd1b  mov     ecx, 18h; unsigned __int64
0x18000dd20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dd25  mov     [rsp+28h+arg_0], rax
0x18000dd2a  test    rax, rax
0x18000dd2d  jnz     short loc_18000DD36
0x18000dd2f  mov     ebx, 8007000Eh
0x18000dd34  jmp     short loc_18000DD79
0x18000dd36  mov     rcx, rax
0x18000dd39  call    ??0?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>::SimpleClassFactory<StorageUsageReportingTask,0>(void)
0x18000dd3e  mov     rbx, rax
0x18000dd41  mov     [rsp+28h+arg_0], 0
0x18000dd4a  test    rax, rax
0x18000dd4d  jz      short loc_18000DD5F
0x18000dd4f  mov     rcx, [rax]
0x18000dd52  mov     rax, [rcx+8]
0x18000dd56  mov     rcx, rbx
0x18000dd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd5e  nop
0x18000dd5f  mov     [rdi], rbx
0x18000dd62  test    rbx, rbx
0x18000dd65  jz      short loc_18000DD77
0x18000dd67  mov     rax, [rbx]
0x18000dd6a  mov     rcx, rbx
0x18000dd6d  mov     rax, [rax+10h]
0x18000dd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd76  nop
0x18000dd77  xor     ebx, ebx
0x18000dd79  lea     rcx, [rsp+28h+arg_0]
0x18000dd7e  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VStorageUsageReportingTask@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<StorageUsageReportingTask,0>>(void)
0x18000dd83  mov     eax, ebx
0x18000dd85  mov     rbx, [rsp+28h+arg_8]
0x18000dd8a  add     rsp, 20h
0x18000dd8e  pop     rdi
0x18000dd8f  retn
```

# ICMModule::OpenColorProfileW(tagPROFILE *,ulong,ulong,ulong)

- ea: `0x180013390`
- end: `0x1800133d2`
- name: `?OpenColorProfileW@ICMModule@@SAPEAXPEAUtagPROFILE@@KKK@Z`
- size: `66`
- prototype: `void *__fastcall(struct tagPROFILE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002ad70`

## callees

- `0x180007410`
- `0x180013390`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall ICMModule::OpenColorProfileW(struct tagPROFILE *a1)
{
  __int64 v2; // rbx

  v2 = 0;
  if ( ICMModule::EnsureLoaded() )
    return ((__int64 (__fastcall *)(struct tagPROFILE *, __int64, __int64, __int64))ICMModule::s_pfnOpenColorProfileW)(
             a1,
             1,
             1,
             3);
  return v2;
}

```

## disassembly

```asm
0x180013390  mov     [rsp+arg_0], rbx
0x180013395  push    rdi
0x180013396  sub     rsp, 30h
0x18001339a  mov     rdi, rcx
0x18001339d  xor     ebx, ebx
0x18001339f  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x1800133a4  test    eax, eax
0x1800133a6  jz      short loc_1800133C4
0x1800133a8  mov     rax, cs:?s_pfnOpenColorProfileW@ICMModule@@0P6APEAXPEAUtagPROFILE@@KKK@ZEA; void * (*ICMModule::s_pfnOpenColorProfileW)(tagPROFILE *,ulong,ulong,ulong)
0x1800133af  lea     edx, [rbx+1]
0x1800133b2  mov     r8d, edx
0x1800133b5  lea     r9d, [rbx+3]
0x1800133b9  mov     rcx, rdi
0x1800133bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c1  mov     rbx, rax
0x1800133c4  mov     rax, rbx
0x1800133c7  mov     rbx, [rsp+38h+arg_0]
0x1800133cc  add     rsp, 30h
0x1800133d0  pop     rdi
0x1800133d1  retn
```

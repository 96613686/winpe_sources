# CAxisUrlCache::Initialize(void)

- ea: `0x180011fe8`
- end: `0x18001202d`
- name: `?Initialize@CAxisUrlCache@@QEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(CAxisUrlCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006aec`

## callees

- `0x180011fe8`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180012000`
- `ntdll!RtlInitializeResource` at `0x180012000`

## pseudocode

```c
__int64 __fastcall CAxisUrlCache::Initialize(CAxisUrlCache *this)
{
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 32));
  *((_DWORD *)this + 6) = 1;
  return 0;
}

```

## disassembly

```asm
0x180011fe8  mov     [rsp+arg_8], rbx
0x180011fed  mov     [rsp+arg_0], rcx
0x180011ff2  push    rdi
0x180011ff3  sub     rsp, 20h
0x180011ff7  mov     rbx, rcx
0x180011ffa  xor     edi, edi
0x180011ffc  add     rcx, 20h ; ' '; Resource
0x180012000  call    cs:__imp_RtlInitializeResource
0x180012006  mov     dword ptr [rbx+18h], 1
0x18001200d  jmp     short loc_180012020
0x18001200f  mov     rax, [rsp+28h+arg_0]
0x180012014  mov     dword ptr [rax+18h], 0
0x18001201b  mov     edi, 80004005h
0x180012020  mov     eax, edi
0x180012022  mov     rbx, [rsp+28h+arg_8]
0x180012027  add     rsp, 20h
0x18001202b  pop     rdi
0x18001202c  retn
```

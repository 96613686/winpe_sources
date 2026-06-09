# GetResourceManagerProxy(ResourceManagerProxy * *)

- ea: `0x18000e8a0`
- end: `0x18000e8f9`
- name: `?GetResourceManagerProxy@@YAJPEAPEAVResourceManagerProxy@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(struct ResourceManagerProxy **)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e740`
- `0x18000e7a0`
- `0x18000e850`
- `0x180019450`
- `0x180019490`
- `0x180019500`

## callees

- `0x18000e8a0`
- `0x180013314`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000e8b4`
- `ntdll!RtlEnterCriticalSection` at `0x18000e8b4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e8d2`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e8d2`

## pseudocode

```c
__int64 __fastcall GetResourceManagerProxy(struct ResourceManagerProxy **a1)
{
  struct ResourceManagerProxy *v2; // rax
  int ResourceManagerProxy; // ebx

  RtlEnterCriticalSection(&s_csProxy);
  v2 = (struct ResourceManagerProxy *)qword_18002ED78;
  if ( !qword_18002ED78 )
  {
    ResourceManagerProxy = CreateResourceManagerProxy();
    if ( ResourceManagerProxy < 0 )
      goto LABEL_3;
    v2 = (struct ResourceManagerProxy *)qword_18002ED78;
  }
  *a1 = v2;
  ResourceManagerProxy = 0;
LABEL_3:
  RtlLeaveCriticalSection(&s_csProxy);
  return (unsigned int)ResourceManagerProxy;
}

```

## disassembly

```asm
0x18000e8a0  mov     [rsp+arg_0], rbx
0x18000e8a5  push    rdi
0x18000e8a6  sub     rsp, 20h
0x18000e8aa  mov     rdi, rcx
0x18000e8ad  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000e8b4  call    cs:__imp_RtlEnterCriticalSection
0x18000e8ba  mov     rax, cs:qword_18002ED78
0x18000e8c1  test    rax, rax
0x18000e8c4  jz      short loc_18000E8E5
0x18000e8c6  mov     [rdi], rax
0x18000e8c9  xor     ebx, ebx
0x18000e8cb  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000e8d2  call    cs:__imp_RtlLeaveCriticalSection
0x18000e8d8  mov     eax, ebx
0x18000e8da  mov     rbx, [rsp+28h+arg_0]
0x18000e8df  add     rsp, 20h
0x18000e8e3  pop     rdi
0x18000e8e4  retn
0x18000e8e5  call    CreateResourceManagerProxy
0x18000e8ea  mov     ebx, eax
0x18000e8ec  test    eax, eax
0x18000e8ee  js      short loc_18000E8CB
0x18000e8f0  mov     rax, cs:qword_18002ED78
0x18000e8f7  jmp     short loc_18000E8C6
```

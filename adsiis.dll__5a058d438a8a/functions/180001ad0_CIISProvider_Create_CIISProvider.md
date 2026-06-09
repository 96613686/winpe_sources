# CIISProvider::Create(CIISProvider * *)

- ea: `0x180001ad0`
- end: `0x180001b23`
- name: `?Create@CIISProvider@@SAJPEAPEAV1@@Z`
- size: `83`
- prototype: `__int64 __fastcall(struct CIISProvider **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800010b0`
- `0x180001ad0`
- `0x180019504`

## pseudocode

```c
__int64 __fastcall CIISProvider::Create(struct CIISProvider **a1)
{
  struct CIISProvider *v2; // rax
  struct WIN32_CRITSEC *v3; // rdx
  __int64 v4; // rcx
  struct CIISProvider *v5; // rbx

  v2 = (struct CIISProvider *)operator new(0x10u);
  v5 = v2;
  if ( !v2 )
    return 2147942414LL;
  *((_DWORD *)v2 + 2) = 1;
  _InterlockedIncrement(&ModuleCount::m_Count);
  SERVER_CACHE::ReferenceGlobalCache(v4, v3);
  *a1 = v5;
  *(_QWORD *)v5 = &CIISProvider::`vftable';
  return 0;
}

```

## disassembly

```asm
0x180001ad0  mov     [rsp+arg_0], rbx
0x180001ad5  push    rdi
0x180001ad6  sub     rsp, 20h
0x180001ada  mov     rdi, rcx
0x180001add  mov     ecx, 10h; Size
0x180001ae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ae7  mov     rbx, rax
0x180001aea  test    rax, rax
0x180001aed  jz      short loc_180001B13
0x180001aef  mov     dword ptr [rax+8], 1
0x180001af6  lock inc cs:?m_Count@ModuleCount@@0JA; long ModuleCount::m_Count
0x180001afd  call    ?ReferenceGlobalCache@SERVER_CACHE@@SAXXZ; SERVER_CACHE::ReferenceGlobalCache(void)
0x180001b02  lea     rax, ??_7CIISProvider@@6B@; const CIISProvider::`vftable'
0x180001b09  mov     [rdi], rbx
0x180001b0c  mov     [rbx], rax
0x180001b0f  xor     eax, eax
0x180001b11  jmp     short loc_180001B18
0x180001b13  mov     eax, 8007000Eh
0x180001b18  mov     rbx, [rsp+28h+arg_0]
0x180001b1d  add     rsp, 20h
0x180001b21  pop     rdi
0x180001b22  retn
```

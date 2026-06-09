# DllInitClasses(int)

- ea: `0x1800020ac`
- end: `0x1800020f9`
- name: `?DllInitClasses@@YAXH@Z`
- size: `77`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022f0`

## callees

- `0x1800020ac`
- `0x180034010`

## pseudocode

```c
void __fastcall DllInitClasses(unsigned int a1)
{
  __int64 i; // rbx
  void (__fastcall *v3)(_QWORD, _QWORD); // rax

  for ( i = 0; i != 5; ++i )
  {
    v3 = (void (__fastcall *)(_QWORD, _QWORD))*(&g_Templates + 5 * i + 3);
    if ( v3 )
      v3(a1, *(&g_Templates + 5 * i + 1));
  }
}

```

## disassembly

```asm
0x1800020ac  mov     [rsp+arg_0], rbx
0x1800020b1  mov     [rsp+arg_8], rsi
0x1800020b6  push    rdi
0x1800020b7  sub     rsp, 20h
0x1800020bb  mov     edi, ecx
0x1800020bd  lea     rsi, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x1800020c4  xor     ebx, ebx
0x1800020c6  lea     rdx, [rbx+rbx*4]
0x1800020ca  mov     rax, [rsi+rdx*8+18h]
0x1800020cf  test    rax, rax
0x1800020d2  jz      short loc_1800020E0
0x1800020d4  mov     rdx, [rsi+rdx*8+8]
0x1800020d9  mov     ecx, edi
0x1800020db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e0  inc     rbx
0x1800020e3  cmp     rbx, 5
0x1800020e7  jnz     short loc_1800020C6
0x1800020e9  mov     rbx, [rsp+28h+arg_0]
0x1800020ee  mov     rsi, [rsp+28h+arg_8]
0x1800020f3  add     rsp, 20h
0x1800020f7  pop     rdi
0x1800020f8  retn
```

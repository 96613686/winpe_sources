# ??$VectorGetMany@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@Collections@Platform@@YAIAEBV?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@IP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@@Z

- ea: `0x1400284b0`
- end: `0x14002855b`
- name: `??$VectorGetMany@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@Collections@Platform@@YAIAEBV?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@IP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@@Z`
- size: `171`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b230`
- `0x14002b2a4`
- `0x14002b320`
- `0x140030650`

## callees

- `0x1400284b0`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x140028554`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x140028554`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x14002854d`
- `wincorlib!?__abi_WinRTraiseOutOfBoundsException@@YAXXZ` at `0x14002854d`

## pseudocode

```c
__int64 __fastcall Platform::Collections::Details::VectorGetMany<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>(
        _QWORD *a1,
        int a2,
        __int64 a3)
{
  unsigned int v3; // ebp
  __int64 i; // rbx
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rcx

  v3 = *(_DWORD *)(a3 + 40);
  if ( (unsigned int)((__int64)(a1[1] - *a1) >> 3) - a2 <= v3 )
    v3 = ((__int64)(a1[1] - *a1) >> 3) - a2;
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
  {
    v8 = *(_QWORD *)(a3 + 48);
    if ( !v8 )
    {
      __abi_WinRTraiseNullReferenceException();
      JUMPOUT(0x14002855ALL);
    }
    if ( (unsigned int)i >= *(_DWORD *)(a3 + 40) )
    {
      __abi_WinRTraiseOutOfBoundsException();
      __debugbreak();
    }
    v9 = (unsigned int)(i + a2);
    v10 = *(_QWORD *)(*a1 + 8 * v9);
    if ( v10 != *(_QWORD *)(v8 + 8 * i) )
    {
      if ( v10 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(*a1 + 8 * v9));
      v11 = *(_QWORD *)(v8 + 8 * i);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *(_QWORD *)(v8 + 8 * i) = v10;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1400284b0  push    rbx
0x1400284b2  push    rbp
0x1400284b3  push    rsi
0x1400284b4  push    rdi
0x1400284b5  push    r12
0x1400284b7  push    r13
0x1400284b9  push    r14
0x1400284bb  push    r15
0x1400284bd  sub     rsp, 28h
0x1400284c1  mov     ebp, [r8+28h]
0x1400284c5  mov     r15, r8
0x1400284c8  mov     rax, [rcx+8]
0x1400284cc  mov     r13d, edx
0x1400284cf  sub     rax, [rcx]
0x1400284d2  mov     r12, rcx
0x1400284d5  sar     rax, 3
0x1400284d9  sub     eax, edx
0x1400284db  cmp     eax, ebp
0x1400284dd  cmovbe  ebp, eax
0x1400284e0  xor     ebx, ebx
0x1400284e2  test    ebp, ebp
0x1400284e4  jz      short loc_14002853A
0x1400284e6  mov     rsi, [r15+30h]
0x1400284ea  test    rsi, rsi
0x1400284ed  jz      short loc_140028554
0x1400284ef  cmp     ebx, [r15+28h]
0x1400284f3  jnb     short loc_14002854D
0x1400284f5  mov     rax, [r12]
0x1400284f9  lea     ecx, [rbx+r13]
0x1400284fd  mov     rdi, [rax+rcx*8]
0x140028501  cmp     rdi, [rsi+rbx*8]
0x140028505  jz      short loc_140028534
0x140028507  test    rdi, rdi
0x14002850a  jz      short loc_14002851B
0x14002850c  mov     rax, [rdi]
0x14002850f  mov     rcx, rdi
0x140028512  mov     rax, [rax+8]
0x140028516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002851b  mov     rcx, [rsi+rbx*8]
0x14002851f  test    rcx, rcx
0x140028522  jz      short loc_140028530
0x140028524  mov     rax, [rcx]
0x140028527  mov     rax, [rax+10h]
0x14002852b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028530  mov     [rsi+rbx*8], rdi
0x140028534  inc     ebx
0x140028536  cmp     ebx, ebp
0x140028538  jb      short loc_1400284E6
0x14002853a  mov     eax, ebp
0x14002853c  add     rsp, 28h
0x140028540  pop     r15
0x140028542  pop     r14
0x140028544  pop     r13
0x140028546  pop     r12
0x140028548  pop     rdi
0x140028549  pop     rsi
0x14002854a  pop     rbp
0x14002854b  pop     rbx
0x14002854c  retn
0x14002854d  call    cs:__imp_?__abi_WinRTraiseOutOfBoundsException@@YAXXZ; __abi_WinRTraiseOutOfBoundsException(void)
0x140028553  int     3; Trap to Debugger
0x140028554  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
```

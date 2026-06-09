# Platform::Array<Platform::String *,1>::CopyToOrDetach(Platform::String * * *,uint *)

- ea: `0x14002ab34`
- end: `0x14002abf2`
- name: `?CopyToOrDetach@?$Array@PE$AAVString@Platform@@$00@Platform@@AE$AAAXPEAPEAPE$AAVString@2@PEAI@Z`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002dec0`

## callees

- `0x140029ad8`
- `0x14002ab34`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x14002abeb`
- `wincorlib!?__abi_WinRTraiseNullReferenceException@@YAXXZ` at `0x14002abeb`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x14002abe4`
- `wincorlib!?__abi_WinRTraiseFailureException@@YAXXZ` at `0x14002abe4`

## pseudocode

```c
void __fastcall Platform::Array<Platform::String __gc *,1>::CopyToOrDetach(__int64 a1, char **a2, _DWORD *a3)
{
  if ( !a2 || !a3 )
  {
    __abi_WinRTraiseNullReferenceException();
    JUMPOUT(0x14002ABF1LL);
  }
  if ( !*(_DWORD *)(a1 + 72) )
  {
    *a2 = 0;
    *a3 = 0;
    return;
  }
  if ( !*(_QWORD *)(a1 + 80) )
    goto LABEL_14;
  if ( !*(_BYTE *)(a1 + 76) && *(_QWORD *)(a1 + 88) && *(_DWORD *)(*(_QWORD *)(a1 + 88) + 12LL) == 1 )
  {
    *a2 = *(char **)(a1 + 80);
    *a3 = *(_DWORD *)(a1 + 72);
    *(_DWORD *)(a1 + 72) = 0;
    *(_BYTE *)(a1 + 76) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    return;
  }
  if ( !*(_BYTE *)(a1 + 76) && (!*(_QWORD *)(a1 + 88) || *(int *)(*(_QWORD *)(a1 + 88) + 12LL) <= 1) )
  {
LABEL_14:
    __abi_WinRTraiseFailureException();
    __debugbreak();
  }
  *a2 = Platform::WriteOnlyArray<Platform::String __gc *,1>::AllocateAndCopyElements(
          *(_QWORD *)(a1 + 80),
          *(_DWORD *)(a1 + 72));
  *a3 = *(_DWORD *)(a1 + 72);
}

```

## disassembly

```asm
0x14002ab34  mov     [rsp+arg_0], rbx
0x14002ab39  mov     [rsp+arg_8], rsi
0x14002ab3e  push    rdi
0x14002ab3f  sub     rsp, 20h
0x14002ab43  mov     rsi, rdx
0x14002ab46  mov     rdi, r8
0x14002ab49  xor     edx, edx
0x14002ab4b  mov     rbx, rcx
0x14002ab4e  test    rsi, rsi
0x14002ab51  jz      loc_14002ABEB
0x14002ab57  test    r8, r8
0x14002ab5a  jz      loc_14002ABEB
0x14002ab60  cmp     [rcx+48h], edx
0x14002ab63  jnz     short loc_14002AB7B
0x14002ab65  mov     [rsi], rdx
0x14002ab68  mov     [r8], edx
0x14002ab6b  mov     rbx, [rsp+28h+arg_0]
0x14002ab70  mov     rsi, [rsp+28h+arg_8]
0x14002ab75  add     rsp, 20h
0x14002ab79  pop     rdi
0x14002ab7a  retn
0x14002ab7b  cmp     [rcx+50h], rdx
0x14002ab7f  jz      short loc_14002ABE4
0x14002ab81  cmp     [rcx+4Ch], dl
0x14002ab84  jnz     short loc_14002ABB4
0x14002ab86  mov     rax, [rcx+58h]
0x14002ab8a  test    rax, rax
0x14002ab8d  jz      short loc_14002ABB4
0x14002ab8f  mov     rax, [rcx+58h]
0x14002ab93  mov     ecx, [rax+0Ch]
0x14002ab96  cmp     ecx, 1
0x14002ab99  jnz     short loc_14002ABB4
0x14002ab9b  mov     rax, [rbx+50h]
0x14002ab9f  mov     [rsi], rax
0x14002aba2  mov     eax, [rbx+48h]
0x14002aba5  mov     [r8], eax
0x14002aba8  mov     [rbx+48h], edx
0x14002abab  mov     [rbx+4Ch], dl
0x14002abae  mov     [rbx+50h], rdx
0x14002abb2  jmp     short loc_14002AB6B
0x14002abb4  cmp     [rbx+4Ch], dl
0x14002abb7  jnz     short loc_14002ABCE
0x14002abb9  mov     rax, [rbx+58h]
0x14002abbd  test    rax, rax
0x14002abc0  jz      short loc_14002ABE4
0x14002abc2  mov     rax, [rbx+58h]
0x14002abc6  mov     ecx, [rax+0Ch]
0x14002abc9  cmp     ecx, 1
0x14002abcc  jle     short loc_14002ABE4
0x14002abce  mov     edx, [rbx+48h]
0x14002abd1  mov     rcx, [rbx+50h]
0x14002abd5  call    ?AllocateAndCopyElements@?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@KAPEAPE$AAVString@2@PEBQE$AAV32@I@Z; Platform::WriteOnlyArray<Platform::String *,1>::AllocateAndCopyElements(Platform::String * const *,uint)
0x14002abda  mov     [rsi], rax
0x14002abdd  mov     eax, [rbx+48h]
0x14002abe0  mov     [rdi], eax
0x14002abe2  jmp     short loc_14002AB6B
0x14002abe4  call    cs:__imp_?__abi_WinRTraiseFailureException@@YAXXZ; __abi_WinRTraiseFailureException(void)
0x14002abea  int     3; Trap to Debugger
0x14002abeb  call    cs:__imp_?__abi_WinRTraiseNullReferenceException@@YAXXZ; __abi_WinRTraiseNullReferenceException(void)
```

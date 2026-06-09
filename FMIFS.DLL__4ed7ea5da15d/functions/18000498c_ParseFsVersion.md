# ParseFsVersion

- ea: `0x18000498c`
- end: `0x1800049f4`
- name: `ParseFsVersion`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058a0`

## callees

- `0x18000498c`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800049ae`
- `msvcrt!wcstoul` at `0x1800049d3`
- `msvcrt!wcstoul` at `0x1800049ae`
- `msvcrt!wcstoul` at `0x1800049d3`

## pseudocode

```c
bool __fastcall ParseFsVersion(const wchar_t *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v6; // eax
  wchar_t *v7; // rcx
  bool result; // al
  wchar_t *EndPtr; // [rsp+50h] [rbp+8h] BYREF

  EndPtr = 0;
  v6 = wcstoul(a1, &EndPtr, 10);
  v7 = EndPtr;
  *a2 = v6;
  result = 0;
  if ( v7 != a1 && *v7 == 46 )
  {
    *a3 = wcstoul(v7 + 1, &EndPtr, 10);
    if ( !*EndPtr )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000498c  push    rbx
0x18000498e  push    rbp
0x18000498f  push    rsi
0x180004990  push    rdi
0x180004991  sub     rsp, 28h
0x180004995  xor     ebp, ebp
0x180004997  mov     rsi, r8
0x18000499a  mov     rbx, rdx
0x18000499d  mov     [rsp+48h+EndPtr], rbp
0x1800049a2  lea     rdx, [rsp+48h+EndPtr]; EndPtr
0x1800049a7  mov     rdi, rcx
0x1800049aa  lea     r8d, [rbp+0Ah]; Radix
0x1800049ae  call    cs:__imp_wcstoul
0x1800049b4  mov     rcx, [rsp+48h+EndPtr]
0x1800049b9  mov     [rbx], eax
0x1800049bb  cmp     rcx, rdi
0x1800049be  jz      short loc_1800049E9
0x1800049c0  cmp     word ptr [rcx], 2Eh ; '.'
0x1800049c4  jnz     short loc_1800049E9
0x1800049c6  add     rcx, 2; String
0x1800049ca  lea     r8d, [rbp+0Ah]; Radix
0x1800049ce  lea     rdx, [rsp+48h+EndPtr]; EndPtr
0x1800049d3  call    cs:__imp_wcstoul
0x1800049d9  mov     [rsi], eax
0x1800049db  mov     rax, [rsp+48h+EndPtr]
0x1800049e0  cmp     [rax], bp
0x1800049e3  jnz     short loc_1800049E9
0x1800049e5  mov     al, 1
0x1800049e7  jmp     short loc_1800049EB
0x1800049e9  xor     al, al
0x1800049eb  add     rsp, 28h
0x1800049ef  pop     rdi
0x1800049f0  pop     rsi
0x1800049f1  pop     rbp
0x1800049f2  pop     rbx
0x1800049f3  retn
```

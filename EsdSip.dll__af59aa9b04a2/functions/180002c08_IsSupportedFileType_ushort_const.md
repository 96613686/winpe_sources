# IsSupportedFileType(ushort const *)

- ea: `0x180002c08`
- end: `0x180002ce9`
- name: `?IsSupportedFileType@@YA_NPEBG@Z`
- size: `225`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002060`
- `0x180002150`

## callees

- `0x180002c08`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180002c22`
- `msvcrt!wcsrchr` at `0x180002c22`
- `msvcrt!_wcsicmp` at `0x180002cb7`
- `msvcrt!_wcsicmp` at `0x180002cb7`

## pseudocode

```c
char __fastcall IsSupportedFileType(const unsigned __int16 *a1)
{
  wchar_t *v1; // rdi
  const wchar_t **v2; // rbx
  _QWORD v4[11]; // [rsp+20h] [rbp-60h] BYREF
  char v5; // [rsp+78h] [rbp-8h] BYREF

  v1 = wcsrchr(a1, 0x2Eu);
  if ( !v1 )
    return 1;
  v4[0] = L".jar";
  v2 = (const wchar_t **)v4;
  v4[1] = L".hta";
  v4[2] = L".cmd";
  v4[3] = L".bat";
  v4[4] = L".ps1";
  v4[5] = L".wsh";
  v4[6] = L".wsf";
  v4[7] = L".js";
  v4[8] = L".vbs";
  v4[9] = L".vbe";
  v4[10] = L".jse";
  while ( _wcsicmp(*v2, v1) )
  {
    if ( ++v2 == (const wchar_t **)&v5 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002c08  mov     [rsp-8+arg_8], rbx
0x180002c0d  mov     [rsp-8+arg_10], rdi
0x180002c12  push    rbp
0x180002c13  mov     rbp, rsp
0x180002c16  sub     rsp, 80h
0x180002c1d  mov     edx, 2Eh ; '.'; Ch
0x180002c22  call    cs:__imp_wcsrchr
0x180002c28  mov     rdi, rax
0x180002c2b  test    rax, rax
0x180002c2e  jz      loc_180002CCE
0x180002c34  lea     rax, aJar; ".jar"
0x180002c3b  mov     [rbp+var_60], rax
0x180002c3f  lea     rbx, [rbp+var_60]
0x180002c43  lea     rax, aHta; ".hta"
0x180002c4a  mov     [rbp+var_58], rax
0x180002c4e  lea     rax, aCmd; ".cmd"
0x180002c55  mov     [rbp+var_50], rax
0x180002c59  lea     rax, aBat; ".bat"
0x180002c60  mov     [rbp+var_48], rax
0x180002c64  lea     rax, aPs1; ".ps1"
0x180002c6b  mov     [rbp+var_40], rax
0x180002c6f  lea     rax, aWsh; ".wsh"
0x180002c76  mov     [rbp+var_38], rax
0x180002c7a  lea     rax, aWsf; ".wsf"
0x180002c81  mov     [rbp+var_30], rax
0x180002c85  lea     rax, aJs; ".js"
0x180002c8c  mov     [rbp+var_28], rax
0x180002c90  lea     rax, aVbs; ".vbs"
0x180002c97  mov     [rbp+var_20], rax
0x180002c9b  lea     rax, aVbe; ".vbe"
0x180002ca2  mov     [rbp+var_18], rax
0x180002ca6  lea     rax, aJse; ".jse"
0x180002cad  mov     [rbp+var_10], rax
0x180002cb1  mov     rcx, [rbx]; String1
0x180002cb4  mov     rdx, rdi; String2
0x180002cb7  call    cs:__imp__wcsicmp
0x180002cbd  test    eax, eax
0x180002cbf  jz      short loc_180002CE5
0x180002cc1  add     rbx, 8
0x180002cc5  lea     rax, [rbp+var_8]
0x180002cc9  cmp     rbx, rax
0x180002ccc  jnz     short loc_180002CB1
0x180002cce  mov     al, 1
0x180002cd0  lea     r11, [rsp+80h+var_s0]
0x180002cd8  mov     rbx, [r11+18h]
0x180002cdc  mov     rdi, [r11+20h]
0x180002ce0  mov     rsp, r11
0x180002ce3  pop     rbp
0x180002ce4  retn
0x180002ce5  xor     al, al
0x180002ce7  jmp     short loc_180002CD0
```

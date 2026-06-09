# VDeleteSubFonts

- ea: `0x180011268`
- end: `0x180011356`
- name: `VDeleteSubFonts`
- size: `238`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae98`
- `0x18000b9a4`
- `0x18000e4ac`
- `0x18001d5bc`

## callees

- `0x1800028d8`
- `0x180011268`
- `0x180037550`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800112e4`
- `KERNEL32!LocalFree` at `0x180011314`
- `KERNEL32!LocalFree` at `0x180011325`
- `KERNEL32!LocalFree` at `0x1800112e4`
- `KERNEL32!LocalFree` at `0x180011314`
- `KERNEL32!LocalFree` at `0x180011325`

## pseudocode

```c
void *__fastcall VDeleteSubFonts(__int64 a1, __int64 a2)
{
  void *v2; // r14
  _QWORD *v4; // rbx
  __int16 v5; // si
  _QWORD *v6; // rdi
  void *v7; // rcx
  _QWORD *v8; // rdi

  v2 = (void *)(a2 + 200);
  v4 = (_QWORD *)(a2 + 200);
  v5 = 0;
  if ( a2 != -200 )
  {
    do
    {
      v6 = (_QWORD *)v4[18];
      if ( v6 )
      {
        if ( *(_DWORD *)(a2 + 196) == 2 )
        {
          if ( *v6 )
          {
            ((void (*)(void))UFOCleanUp)();
            v4[18] = 0;
          }
          LocalFree(v6);
          goto LABEL_19;
        }
        if ( *(_DWORD *)(a2 + 196) == 3
          || *(_DWORD *)(a2 + 196) == 4
          || *(_DWORD *)(a2 + 196) == 5
          || *(_DWORD *)(a2 + 196) == 6
          || *(_DWORD *)(a2 + 196) == 7 )
        {
          UFOCleanUp(v4[18]);
LABEL_14:
          v4[18] = 0;
          goto LABEL_19;
        }
        if ( (unsigned int)(*(_DWORD *)(a2 + 196) - 9) <= 1 )
        {
          if ( *v6 )
            UFOCleanUp(*v6);
          v7 = (void *)v4[18];
          if ( v7 )
            LocalFree(v7);
          goto LABEL_14;
        }
      }
LABEL_19:
      v8 = (_QWORD *)*v4;
      if ( v5 )
        LocalFree(v4);
      ++v5;
      v4 = v8;
    }
    while ( v8 );
  }
  return memset_0(v2, 0, 0xA8u);
}

```

## disassembly

```asm
0x180011268  push    rbx
0x18001126a  push    rbp
0x18001126b  push    rsi
0x18001126c  push    rdi
0x18001126d  push    r14
0x18001126f  push    r15
0x180011271  sub     rsp, 28h
0x180011275  lea     r14, [rdx+0C8h]
0x18001127c  xor     r15d, r15d
0x18001127f  mov     rbp, rdx
0x180011282  mov     rbx, r14
0x180011285  mov     esi, r15d
0x180011288  test    r14, r14
0x18001128b  jz      loc_18001133A
0x180011291  mov     rdi, [rbx+90h]
0x180011298  test    rdi, rdi
0x18001129b  jz      short loc_18001131A
0x18001129d  mov     ecx, [rbp+0C4h]
0x1800112a3  sub     ecx, 2
0x1800112a6  jz      short loc_1800112FD
0x1800112a8  sub     ecx, 1
0x1800112ab  jz      short loc_1800112F3
0x1800112ad  sub     ecx, 1
0x1800112b0  jz      short loc_1800112F3
0x1800112b2  sub     ecx, 1
0x1800112b5  jz      short loc_1800112F3
0x1800112b7  sub     ecx, 1
0x1800112ba  jz      short loc_1800112F3
0x1800112bc  sub     ecx, 1
0x1800112bf  jz      short loc_1800112F3
0x1800112c1  sub     ecx, 2
0x1800112c4  jz      short loc_1800112CB
0x1800112c6  cmp     ecx, 1
0x1800112c9  jnz     short loc_18001131A
0x1800112cb  mov     rcx, [rdi]
0x1800112ce  test    rcx, rcx
0x1800112d1  jz      short loc_1800112D8
0x1800112d3  call    UFOCleanUp
0x1800112d8  mov     rcx, [rbx+90h]; hMem
0x1800112df  test    rcx, rcx
0x1800112e2  jz      short loc_1800112EA
0x1800112e4  call    cs:__imp_LocalFree
0x1800112ea  mov     [rbx+90h], r15
0x1800112f1  jmp     short loc_18001131A
0x1800112f3  mov     rcx, rdi
0x1800112f6  call    UFOCleanUp
0x1800112fb  jmp     short loc_1800112EA
0x1800112fd  mov     rcx, [rdi]
0x180011300  test    rcx, rcx
0x180011303  jz      short loc_180011311
0x180011305  call    UFOCleanUp
0x18001130a  mov     [rbx+90h], r15
0x180011311  mov     rcx, rdi; hMem
0x180011314  call    cs:__imp_LocalFree
0x18001131a  mov     rdi, [rbx]
0x18001131d  test    si, si
0x180011320  jz      short loc_18001132B
0x180011322  mov     rcx, rbx; hMem
0x180011325  call    cs:__imp_LocalFree
0x18001132b  inc     si
0x18001132e  mov     rbx, rdi
0x180011331  test    rdi, rdi
0x180011334  jnz     loc_180011291
0x18001133a  xor     edx, edx; Val
0x18001133c  mov     r8d, 0A8h; Size
0x180011342  mov     rcx, r14; void *
0x180011345  add     rsp, 28h
0x180011349  pop     r15
0x18001134b  pop     r14
0x18001134d  pop     rdi
0x18001134e  pop     rsi
0x18001134f  pop     rbp
0x180011350  pop     rbx
0x180011351  jmp     memset_0
```

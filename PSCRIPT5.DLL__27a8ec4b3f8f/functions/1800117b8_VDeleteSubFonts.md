# VDeleteSubFonts

- ea: `0x1800117b8`
- end: `0x1800118bc`
- name: `VDeleteSubFonts`
- size: `260`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b26c`
- `0x18000bdac`
- `0x18000e910`
- `0x18001e02c`

## callees

- `0x180002938`
- `0x1800117b8`
- `0x180038dc4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180011838`
- `KERNEL32!LocalFree` at `0x18001186e`
- `KERNEL32!LocalFree` at `0x180011885`
- `KERNEL32!LocalFree` at `0x180011838`
- `KERNEL32!LocalFree` at `0x18001186e`
- `KERNEL32!LocalFree` at `0x180011885`

## pseudocode

```c
void *__fastcall VDeleteSubFonts(__int64 a1, __int64 a2)
{
  void *v2; // r14
  _QWORD *v4; // rbx
  __int16 v5; // si
  __int64 *v6; // rdi
  void *v7; // rcx
  _QWORD *v8; // rdi

  v2 = (void *)(a2 + 200);
  v4 = (_QWORD *)(a2 + 200);
  v5 = 0;
  if ( a2 != -200 )
  {
    do
    {
      v6 = (__int64 *)v4[18];
      if ( v6 )
      {
        if ( *(_DWORD *)(a2 + 196) == 2 )
        {
          if ( *v6 )
          {
            UFOCleanUp(*v6);
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
0x1800117b8  push    rbx
0x1800117ba  push    rbp
0x1800117bb  push    rsi
0x1800117bc  push    rdi
0x1800117bd  push    r14
0x1800117bf  push    r15
0x1800117c1  sub     rsp, 28h
0x1800117c5  lea     r14, [rdx+0C8h]
0x1800117cc  xor     r15d, r15d
0x1800117cf  mov     rbp, rdx
0x1800117d2  mov     rbx, r14
0x1800117d5  mov     esi, r15d
0x1800117d8  test    r14, r14
0x1800117db  jz      loc_1800118A0
0x1800117e1  mov     rdi, [rbx+90h]
0x1800117e8  test    rdi, rdi
0x1800117eb  jz      loc_18001187A
0x1800117f1  mov     ecx, [rbp+0C4h]
0x1800117f7  sub     ecx, 2
0x1800117fa  jz      short loc_180011857
0x1800117fc  sub     ecx, 1
0x1800117ff  jz      short loc_18001184D
0x180011801  sub     ecx, 1
0x180011804  jz      short loc_18001184D
0x180011806  sub     ecx, 1
0x180011809  jz      short loc_18001184D
0x18001180b  sub     ecx, 1
0x18001180e  jz      short loc_18001184D
0x180011810  sub     ecx, 1
0x180011813  jz      short loc_18001184D
0x180011815  sub     ecx, 2
0x180011818  jz      short loc_18001181F
0x18001181a  cmp     ecx, 1
0x18001181d  jnz     short loc_18001187A
0x18001181f  mov     rcx, [rdi]
0x180011822  test    rcx, rcx
0x180011825  jz      short loc_18001182C
0x180011827  call    UFOCleanUp
0x18001182c  mov     rcx, [rbx+90h]; hMem
0x180011833  test    rcx, rcx
0x180011836  jz      short loc_180011844
0x180011838  call    cs:__imp_LocalFree
0x18001183f  nop     dword ptr [rax+rax+00h]
0x180011844  mov     [rbx+90h], r15
0x18001184b  jmp     short loc_18001187A
0x18001184d  mov     rcx, rdi
0x180011850  call    UFOCleanUp
0x180011855  jmp     short loc_180011844
0x180011857  mov     rcx, [rdi]
0x18001185a  test    rcx, rcx
0x18001185d  jz      short loc_18001186B
0x18001185f  call    UFOCleanUp
0x180011864  mov     [rbx+90h], r15
0x18001186b  mov     rcx, rdi; hMem
0x18001186e  call    cs:__imp_LocalFree
0x180011875  nop     dword ptr [rax+rax+00h]
0x18001187a  mov     rdi, [rbx]
0x18001187d  test    si, si
0x180011880  jz      short loc_180011891
0x180011882  mov     rcx, rbx; hMem
0x180011885  call    cs:__imp_LocalFree
0x18001188c  nop     dword ptr [rax+rax+00h]
0x180011891  inc     si
0x180011894  mov     rbx, rdi
0x180011897  test    rdi, rdi
0x18001189a  jnz     loc_1800117E1
0x1800118a0  xor     edx, edx; Val
0x1800118a2  mov     r8d, 0A8h; Size
0x1800118a8  mov     rcx, r14; void *
0x1800118ab  add     rsp, 28h
0x1800118af  pop     r15
0x1800118b1  pop     r14
0x1800118b3  pop     rdi
0x1800118b4  pop     rsi
0x1800118b5  pop     rbp
0x1800118b6  pop     rbx
0x1800118b7  jmp     memset_0
```

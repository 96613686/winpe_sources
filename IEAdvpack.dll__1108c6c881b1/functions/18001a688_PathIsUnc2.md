# PathIsUnc2

- ea: `0x18001a688`
- end: `0x18001a719`
- name: `PathIsUnc2`
- size: `145`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *, unsigned __int8 (__fastcall *)(_QWORD))`
- caller_count: `32`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e40`
- `0x180002d50`
- `0x180003fb8`
- `0x180004880`
- `0x180005a8c`
- `0x1800078d8`
- `0x180008524`
- `0x180008f2c`
- `0x180009c14`
- `0x18000a918`
- `0x18000ae68`
- `0x18000b8f0`
- `0x18000c3b8`
- `0x18000c760`
- `0x18000c99c`
- `0x18000cc80`
- `0x18000ced8`
- `0x18000d184`
- `0x18000e060`
- `0x18000ef90`
- `0x18000f7b0`
- `0x180010050`
- `0x1800115b0`
- `0x180011940`
- `0x180013c98`
- `0x180015ef8`
- `0x180017434`
- `0x180017728`
- `0x180017bcc`
- `0x180019fb8`
- `0x18001b524`
- `0x18001b634`

## callees

- `0x18001a688`
- `0x18001a720`
- `0x18001ac8c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall PathIsUnc2(unsigned __int16 *a1, _QWORD *a2, unsigned __int8 (__fastcall *a3)(_QWORD))
{
  unsigned int v3; // ebx
  bool v7; // al
  __int64 v8; // rax

  v3 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3(*a1) && a3(a1[1]) )
  {
    if ( a1[2] == 63 )
    {
      if ( !StrIsEqualCaseInsensitive(a1 + 3, L"\\UNC\\", 5) )
        return v3;
      v8 = 8;
      v3 = 1;
    }
    else
    {
      v7 = !PathIsVolumeGUIDWorker(a1);
      v3 = v7;
      if ( !v7 )
        return v3;
      v8 = 2LL * v7;
    }
    if ( a2 )
      *a2 = &a1[v8];
  }
  return v3;
}

```

## disassembly

```asm
0x18001a688  push    rbx
0x18001a68a  push    rbp
0x18001a68b  push    rsi
0x18001a68c  push    rdi
0x18001a68d  sub     rsp, 28h
0x18001a691  xor     ebx, ebx
0x18001a693  mov     rbp, r8
0x18001a696  mov     rsi, rdx
0x18001a699  mov     rdi, rcx
0x18001a69c  test    rdx, rdx
0x18001a69f  jz      short loc_18001A6A4
0x18001a6a1  mov     [rdx], rbx
0x18001a6a4  movzx   ecx, word ptr [rcx]
0x18001a6a7  mov     rax, rbp
0x18001a6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6af  test    al, al
0x18001a6b1  jz      short loc_18001A70E
0x18001a6b3  movzx   ecx, word ptr [rdi+2]
0x18001a6b7  mov     rax, rbp
0x18001a6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6bf  test    al, al
0x18001a6c1  jz      short loc_18001A70E
0x18001a6c3  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18001a6c8  jz      short loc_18001A6E0
0x18001a6ca  mov     rcx, rdi; unsigned __int16 *
0x18001a6cd  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x18001a6d2  xor     al, 1
0x18001a6d4  movzx   ebx, al
0x18001a6d7  jz      short loc_18001A70E
0x18001a6d9  mov     eax, ebx
0x18001a6db  add     rax, rax
0x18001a6de  jmp     short loc_18001A702
0x18001a6e0  lea     rcx, [rdi+6]; unsigned __int16 *
0x18001a6e4  mov     r8d, 5; int
0x18001a6ea  lea     rdx, aUnc_0; "\\UNC\\"
0x18001a6f1  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18001a6f6  test    al, al
0x18001a6f8  jz      short loc_18001A70E
0x18001a6fa  mov     eax, 8
0x18001a6ff  lea     ebx, [rax-7]
0x18001a702  test    rsi, rsi
0x18001a705  jz      short loc_18001A70E
0x18001a707  lea     rcx, [rdi+rax*2]
0x18001a70b  mov     [rsi], rcx
0x18001a70e  mov     eax, ebx
0x18001a710  add     rsp, 28h
0x18001a714  pop     rdi
0x18001a715  pop     rsi
0x18001a716  pop     rbp
0x18001a717  pop     rbx
0x18001a718  retn
```

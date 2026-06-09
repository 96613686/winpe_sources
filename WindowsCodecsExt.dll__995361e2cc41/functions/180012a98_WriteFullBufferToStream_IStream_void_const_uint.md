# WriteFullBufferToStream(IStream *,void const *,uint)

- ea: `0x180012a98`
- end: `0x180012af5`
- name: `?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct IStream *, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012840`

## callees

- `0x180012a98`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall WriteFullBufferToStream(struct IStream *a1, const void *a2, __int64 a3)
{
  __int64 v3; // rax
  int v4; // edi
  int v5; // ebx
  int v7; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)a1;
  v4 = a3;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IStream *, const void *, __int64, int *))(v3 + 32))(a1, a2, a3, &v7);
  if ( v5 < 0 )
  {
    if ( !g_doStackCaptures )
      return (unsigned int)v5;
    goto LABEL_6;
  }
  if ( v4 != v7 )
  {
    v5 = -2003292303;
    if ( g_doStackCaptures )
LABEL_6:
      DoStackCapture(v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012a98  mov     [rsp+arg_8], rbx
0x180012a9d  push    rdi
0x180012a9e  sub     rsp, 30h
0x180012aa2  mov     rax, [rcx]
0x180012aa5  lea     r9, [rsp+38h+arg_0]
0x180012aaa  mov     edi, r8d
0x180012aad  mov     [rsp+38h+arg_0], 0
0x180012ab5  mov     rax, [rax+20h]
0x180012ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abe  mov     ebx, eax
0x180012ac0  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180012ac6  test    ebx, ebx
0x180012ac8  jns     short loc_180012AD2
0x180012aca  test    eax, eax
0x180012acc  jnz     short loc_180012AE1
0x180012ace  test    ebx, ebx
0x180012ad0  js      short loc_180012AE8
0x180012ad2  cmp     edi, [rsp+38h+arg_0]
0x180012ad6  jz      short loc_180012AE8
0x180012ad8  mov     ebx, 88982F71h
0x180012add  test    eax, eax
0x180012adf  jz      short loc_180012AE8
0x180012ae1  mov     ecx, ebx; int
0x180012ae3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012ae8  mov     eax, ebx
0x180012aea  mov     rbx, [rsp+38h+arg_8]
0x180012aef  add     rsp, 30h
0x180012af3  pop     rdi
0x180012af4  retn
```

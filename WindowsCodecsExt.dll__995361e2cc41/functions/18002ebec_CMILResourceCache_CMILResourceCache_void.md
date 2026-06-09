# CMILResourceCache::~CMILResourceCache(void)

- ea: `0x18002ebec`
- end: `0x18002ec4c`
- name: `??1CMILResourceCache@@IEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CMILResourceCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002dc48`

## callees

- `0x180009290`
- `0x18002ebec`
- `0x180033010`

## pseudocode

```c
void __fastcall CMILResourceCache::~CMILResourceCache(CMILResourceCache *this)
{
  int v2; // eax
  unsigned int v3; // eax
  char *v4; // rdi
  __int64 v5; // rcx

  *(_QWORD *)this = &CMILResourceCache::`vftable';
  v2 = *((_DWORD *)this + 8);
  if ( v2 )
  {
    do
    {
      v3 = v2 - 1;
      v4 = (char *)this + 8;
      *((_DWORD *)this + 8) = v3;
      v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v3);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
      v2 = *((_DWORD *)this + 8);
    }
    while ( v2 );
  }
  else
  {
    v4 = (char *)this + 8;
  }
  DynArrayImpl<0>::~DynArrayImpl<0>(v4);
}

```

## disassembly

```asm
0x18002ebec  mov     [rsp+arg_0], rbx
0x18002ebf1  push    rdi
0x18002ebf2  sub     rsp, 20h
0x18002ebf6  lea     rax, ??_7CMILResourceCache@@6B@; const CMILResourceCache::`vftable'
0x18002ebfd  mov     rbx, rcx
0x18002ec00  mov     [rcx], rax
0x18002ec03  mov     eax, [rcx+20h]
0x18002ec06  test    eax, eax
0x18002ec08  jz      short loc_18002EC36
0x18002ec0a  dec     eax
0x18002ec0c  lea     rdi, [rbx+8]
0x18002ec10  mov     [rbx+20h], eax
0x18002ec13  mov     ecx, eax
0x18002ec15  mov     rax, [rdi]
0x18002ec18  mov     rcx, [rax+rcx*8]
0x18002ec1c  test    rcx, rcx
0x18002ec1f  jz      short loc_18002EC2D
0x18002ec21  mov     rax, [rcx]
0x18002ec24  mov     rax, [rax+18h]
0x18002ec28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec2d  mov     eax, [rbx+20h]
0x18002ec30  test    eax, eax
0x18002ec32  jnz     short loc_18002EC0A
0x18002ec34  jmp     short loc_18002EC3A
0x18002ec36  lea     rdi, [rcx+8]
0x18002ec3a  mov     rcx, rdi
0x18002ec3d  mov     rbx, [rsp+28h+arg_0]
0x18002ec42  add     rsp, 20h
0x18002ec46  pop     rdi
0x18002ec47  jmp     ??1?$DynArrayImpl@$0A@@@IEAA@XZ; DynArrayImpl<0>::~DynArrayImpl<0>(void)
```

# CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::EnsureSize(uint,int)

- ea: `0x18001fe10`
- end: `0x18001fee2`
- name: `?EnsureSize@?$CPbPreallocArray@USessionDelayHandles@CServiceModule@@$09@@IEAAJIH@Z`
- size: `210`
- prototype: `__int64 __fastcall(unsigned int *Src, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800282a0`

## callees

- `0x18001bc04`
- `0x18001bff0`
- `0x18001fe10`
- `0x18002fb4c`

## pseudocode

```c
__int64 __fastcall CPbPreallocArray<CServiceModule::SessionDelayHandles,10>::EnsureSize(
        unsigned int *Src,
        unsigned int a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebp
  unsigned int v4; // esi
  unsigned int v6; // eax
  void *v7; // rax
  size_t v8; // r8
  void *v9; // rbx
  const struct std::nothrow_t *v10; // rdx

  v2 = Src[42];
  v3 = 0;
  v4 = a2;
  if ( v2 < a2 )
  {
    if ( v2 < 0x7FFFFFFF )
    {
      v6 = 2 * v2;
      if ( v6 > a2 )
        v4 = v6;
      if ( *((unsigned int **)Src + 20) == Src )
      {
        v7 = operator new[](saturated_mul(v4, 0x10u));
        v8 = 16LL * Src[42];
        *((_QWORD *)Src + 20) = v7;
        memcpy_0(v7, Src, v8);
      }
      else
      {
        v9 = operator new[](saturated_mul(v4, 0x10u));
        memcpy_0(v9, *((const void **)Src + 20), 16LL * Src[42]);
        operator delete(*((void **)Src + 20), v10);
        *((_QWORD *)Src + 20) = v9;
      }
      Src[42] = v4;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001fe10  push    rbx
0x18001fe12  push    rbp
0x18001fe13  push    rsi
0x18001fe14  push    rdi
0x18001fe15  sub     rsp, 28h
0x18001fe19  mov     eax, [rcx+0A8h]
0x18001fe1f  xor     ebp, ebp
0x18001fe21  mov     esi, edx
0x18001fe23  mov     rdi, rcx
0x18001fe26  cmp     eax, edx
0x18001fe28  jnb     loc_18001FED7
0x18001fe2e  cmp     eax, 7FFFFFFFh
0x18001fe33  jb      short loc_18001FE3F
0x18001fe35  mov     ebp, 8007000Eh
0x18001fe3a  jmp     loc_18001FED7
0x18001fe3f  add     eax, eax
0x18001fe41  cmp     eax, esi
0x18001fe43  cmova   esi, eax
0x18001fe46  mov     eax, 10h
0x18001fe4b  mov     ecx, esi
0x18001fe4d  cmp     [rdi+0A0h], rdi
0x18001fe54  jnz     short loc_18001FE8B
0x18001fe56  mul     rcx
0x18001fe59  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fe60  cmovb   rax, rcx
0x18001fe64  mov     rcx, rax; unsigned __int64
0x18001fe67  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001fe6c  mov     r8d, [rdi+0A8h]
0x18001fe73  mov     rdx, rdi; Src
0x18001fe76  shl     r8, 4; Size
0x18001fe7a  mov     rcx, rax; void *
0x18001fe7d  mov     [rdi+0A0h], rax
0x18001fe84  call    memcpy_0
0x18001fe89  jmp     short loc_18001FED1
0x18001fe8b  mul     rcx
0x18001fe8e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fe95  cmovb   rax, rcx
0x18001fe99  mov     rcx, rax; unsigned __int64
0x18001fe9c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001fea1  mov     r8d, [rdi+0A8h]
0x18001fea8  mov     rcx, rax; void *
0x18001feab  mov     rdx, [rdi+0A0h]; Src
0x18001feb2  mov     rbx, rax
0x18001feb5  shl     r8, 4; Size
0x18001feb9  call    memcpy_0
0x18001febe  mov     rcx, [rdi+0A0h]; void *
0x18001fec5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001feca  mov     [rdi+0A0h], rbx
0x18001fed1  mov     [rdi+0A8h], esi
0x18001fed7  mov     eax, ebp
0x18001fed9  add     rsp, 28h
0x18001fedd  pop     rdi
0x18001fede  pop     rsi
0x18001fedf  pop     rbp
0x18001fee0  pop     rbx
0x18001fee1  retn
```

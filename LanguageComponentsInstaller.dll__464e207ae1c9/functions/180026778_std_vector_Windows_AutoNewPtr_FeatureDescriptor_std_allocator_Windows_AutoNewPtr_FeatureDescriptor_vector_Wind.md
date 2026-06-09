# std::vector<Windows::AutoNewPtr<FeatureDescriptor>,std::allocator<Windows::AutoNewPtr<FeatureDescriptor>>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>,std::allocator<Windows::AutoNewPtr<FeatureDescriptor>>>(void)

- ea: `0x180026778`
- end: `0x18002682d`
- name: `??1?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800269c0`
- `0x180026f3c`
- `0x180029752`
- `0x1800297a2`
- `0x180029807`

## callees

- `0x180003a34`
- `0x180026778`

## pseudocode

```c
void __fastcall std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::~vector<Windows::AutoNewPtr<FeatureDescriptor>>(
        __int64 a1)
{
  void **v1; // rbx
  void **v3; // rsi
  void *v4; // rcx
  void **v5; // rcx
  void **v6; // rax

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        *v1 = 0;
        operator delete(v4);
      }
      ++v1;
    }
    v5 = *(void ***)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v6 = *(void ***)a1;
    }
    else
    {
      v6 = (void **)*(v5 - 1);
      if ( (unsigned __int64)((char *)v5 - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180026778  mov     [rsp+arg_8], rbx
0x18002677d  mov     [rsp+arg_10], rsi
0x180026782  push    rdi
0x180026783  sub     rsp, 20h
0x180026787  mov     rbx, [rcx]
0x18002678a  mov     rdi, rcx
0x18002678d  test    rbx, rbx
0x180026790  jz      loc_18002681D
0x180026796  mov     rsi, [rcx+8]
0x18002679a  jmp     short loc_1800267B9
0x18002679c  mov     rcx, [rbx]; Block
0x18002679f  test    rcx, rcx
0x1800267a2  jz      short loc_1800267B5
0x1800267a4  mov     edx, 18h
0x1800267a9  mov     qword ptr [rbx], 0
0x1800267b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800267b5  add     rbx, 8
0x1800267b9  cmp     rbx, rsi
0x1800267bc  jnz     short loc_18002679C
0x1800267be  mov     rcx, [rdi]
0x1800267c1  mov     rax, [rdi+10h]
0x1800267c5  sub     rax, rcx
0x1800267c8  sar     rax, 3
0x1800267cc  lea     rdx, ds:0[rax*8]
0x1800267d4  cmp     rdx, 1000h
0x1800267db  jb      short loc_1800267FB
0x1800267dd  mov     rax, [rcx-8]
0x1800267e1  sub     rcx, rax
0x1800267e4  sub     rcx, 8
0x1800267e8  cmp     rcx, 1Fh
0x1800267ec  ja      short loc_1800267F4
0x1800267ee  add     rdx, 27h ; '''
0x1800267f2  jmp     short loc_1800267FE
0x1800267f4  mov     ecx, 5
0x1800267f9  int     29h; Win8: RtlFailFast(ecx)
0x1800267fb  mov     rax, rcx
0x1800267fe  mov     rcx, rax; Block
0x180026801  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026806  mov     qword ptr [rdi], 0
0x18002680d  mov     qword ptr [rdi+8], 0
0x180026815  mov     qword ptr [rdi+10h], 0
0x18002681d  mov     rbx, [rsp+28h+arg_8]
0x180026822  mov     rsi, [rsp+28h+arg_10]
0x180026827  add     rsp, 20h
0x18002682b  pop     rdi
0x18002682c  retn
```

# std::vector<Windows::AutoNewPtr<FeatureDescriptor>,std::allocator<Windows::AutoNewPtr<FeatureDescriptor>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180026834`
- end: `0x1800268cb`
- name: `??1_Reallocation_guard@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800263b4`

## callees

- `0x180003a34`
- `0x180026834`

## pseudocode

```c
void __fastcall std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  void **v2; // rsi
  void **i; // rbx
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rax

  if ( a1[1] )
  {
    v2 = (void **)a1[4];
    for ( i = (void **)a1[3]; i != v2; ++i )
    {
      v4 = *i;
      if ( *i )
      {
        *i = 0;
        operator delete(v4);
      }
    }
    v5 = a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v5 - 8);
      if ( (unsigned __int64)(v5 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x180026834  mov     [rsp+arg_8], rbx
0x180026839  mov     [rsp+arg_10], rsi
0x18002683e  push    rdi
0x18002683f  sub     rsp, 20h
0x180026843  cmp     qword ptr [rcx+8], 0
0x180026848  mov     rdi, rcx
0x18002684b  jz      short loc_1800268BB
0x18002684d  mov     rsi, [rcx+20h]
0x180026851  mov     rbx, [rcx+18h]
0x180026855  jmp     short loc_180026874
0x180026857  mov     rcx, [rbx]; Block
0x18002685a  test    rcx, rcx
0x18002685d  jz      short loc_180026870
0x18002685f  mov     edx, 18h
0x180026864  mov     qword ptr [rbx], 0
0x18002686b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026870  add     rbx, 8
0x180026874  cmp     rbx, rsi
0x180026877  jnz     short loc_180026857
0x180026879  mov     rax, [rdi+10h]
0x18002687d  mov     rcx, [rdi+8]
0x180026881  lea     rdx, ds:0[rax*8]
0x180026889  cmp     rdx, 1000h
0x180026890  jb      short loc_1800268B0
0x180026892  mov     rax, [rcx-8]
0x180026896  sub     rcx, rax
0x180026899  sub     rcx, 8
0x18002689d  cmp     rcx, 1Fh
0x1800268a1  ja      short loc_1800268A9
0x1800268a3  add     rdx, 27h ; '''
0x1800268a7  jmp     short loc_1800268B3
0x1800268a9  mov     ecx, 5
0x1800268ae  int     29h; Win8: RtlFailFast(ecx)
0x1800268b0  mov     rax, rcx
0x1800268b3  mov     rcx, rax; Block
0x1800268b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800268bb  mov     rbx, [rsp+28h+arg_8]
0x1800268c0  mov     rsi, [rsp+28h+arg_10]
0x1800268c5  add     rsp, 20h
0x1800268c9  pop     rdi
0x1800268ca  retn
```

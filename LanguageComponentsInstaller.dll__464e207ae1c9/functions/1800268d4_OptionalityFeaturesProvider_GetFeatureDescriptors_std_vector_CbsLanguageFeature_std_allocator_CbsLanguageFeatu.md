# OptionalityFeaturesProvider::GetFeatureDescriptors(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x1800268d4`
- end: `0x1800269ba`
- name: `?GetFeatureDescriptors@OptionalityFeaturesProvider@@YA?AV?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z`
- size: `230`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800269c0`
- `0x180026f3c`

## callees

- `0x180003544`
- `0x180003a34`
- `0x1800263b4`
- `0x1800268d4`

## pseudocode

```c
_QWORD *__fastcall OptionalityFeaturesProvider::GetFeatureDescriptors(_QWORD *a1, __int64 a2)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  _DWORD *v5; // rdx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  void *v8; // rcx
  void *Block[4]; // [rsp+28h] [rbp-20h] BYREF

  Block[1] = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = *(_QWORD **)a2;
  v4 = *(_QWORD **)(a2 + 8);
  while ( v3 != v4 )
  {
    Block[0] = 0;
    v5 = operator new(0x18u);
    *(_OWORD *)v5 = 0;
    *((_QWORD *)v5 + 2) = 0;
    Block[0] = v5;
    if ( v3[3] <= 7u )
      v6 = v3;
    else
      v6 = (_QWORD *)*v3;
    *(_QWORD *)v5 = v6;
    v5[5] = 64;
    v7 = (_QWORD *)a1[1];
    if ( v7 == (_QWORD *)a1[2] )
    {
      std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Emplace_reallocate<Windows::AutoNewPtr<FeatureDescriptor>>(
        (void ***)a1,
        (void **)a1[1],
        (__int64 *)Block);
      v8 = Block[0];
    }
    else
    {
      v8 = 0;
      *v7 = v5;
      a1[1] += 8LL;
    }
    if ( v8 )
      operator delete(v8);
    v3 += 24;
  }
  return a1;
}

```

## disassembly

```asm
0x1800268d4  mov     rax, rsp
0x1800268d7  mov     [rax+10h], rbx
0x1800268db  mov     [rax+18h], rsi
0x1800268df  push    rdi
0x1800268e0  sub     rsp, 40h
0x1800268e4  mov     rbx, rcx
0x1800268e7  mov     [rax-18h], rcx
0x1800268eb  mov     dword ptr [rax-28h], 0
0x1800268f2  mov     qword ptr [rcx], 0
0x1800268f9  mov     qword ptr [rcx+8], 0
0x180026901  mov     qword ptr [rcx+10h], 0
0x180026909  mov     dword ptr [rax-28h], 1
0x180026910  mov     rdi, [rdx]
0x180026913  mov     rsi, [rdx+8]
0x180026917  jmp     loc_18002699D
0x18002691c  mov     [rsp+48h+Block], 0
0x180026925  mov     ecx, 18h; Size
0x18002692a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002692f  mov     rdx, rax
0x180026932  xorps   xmm0, xmm0
0x180026935  xor     eax, eax
0x180026937  movups  xmmword ptr [rdx], xmm0
0x18002693a  mov     [rdx+10h], rax
0x18002693e  mov     [rsp+48h+Block], rdx
0x180026943  cmp     qword ptr [rdi+18h], 7
0x180026948  jbe     short loc_18002694F
0x18002694a  mov     rax, [rdi]
0x18002694d  jmp     short loc_180026952
0x18002694f  mov     rax, rdi
0x180026952  mov     [rdx], rax
0x180026955  mov     dword ptr [rdx+14h], 40h ; '@'
0x18002695c  mov     rax, [rbx+8]
0x180026960  cmp     rax, [rbx+10h]
0x180026964  jz      short loc_180026972
0x180026966  xor     ecx, ecx
0x180026968  mov     [rax], rdx
0x18002696b  add     qword ptr [rbx+8], 8
0x180026970  jmp     short loc_180026987
0x180026972  lea     r8, [rsp+48h+Block]
0x180026977  mov     rdx, rax
0x18002697a  mov     rcx, rbx
0x18002697d  call    ??$_Emplace_reallocate@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@AEAAPEAV?$AutoNewPtr@UFeatureDescriptor@@@Windows@@QEAV23@$$QEAV23@@Z; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Emplace_reallocate<Windows::AutoNewPtr<FeatureDescriptor>>(Windows::AutoNewPtr<FeatureDescriptor> * const,Windows::AutoNewPtr<FeatureDescriptor> &&)
0x180026982  mov     rcx, [rsp+48h+Block]; Block
0x180026987  test    rcx, rcx
0x18002698a  jz      short loc_180026996
0x18002698c  mov     edx, 18h
0x180026991  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026996  add     rdi, 0C0h
0x18002699d  cmp     rdi, rsi
0x1800269a0  jnz     loc_18002691C
0x1800269a6  mov     rax, rbx
0x1800269a9  mov     rbx, [rsp+48h+arg_8]
0x1800269ae  mov     rsi, [rsp+48h+arg_10]
0x1800269b3  add     rsp, 40h
0x1800269b7  pop     rdi
0x1800269b8  retn
```

# std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *,std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *)

- ea: `0x18000e040`
- end: `0x18000e12c`
- name: `??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@@9@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@PEAX@1@PEAU21@0@Z`
- size: `236`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800057f0`
- `0x18000e040`

## callees

- `0x18000e040`
- `0x1800157c0`
- `0x180035060`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbp
  _QWORD *v7; // rdi
  struct winrt::impl::hstring_header *v8; // rdx
  struct winrt::impl::hstring_header *v9; // rdx
  struct winrt::impl::hstring_header *v10; // rdx

  v6 = *a1;
  if ( *(_BYTE *)(a2 + 25) )
    return (_QWORD *)*a1;
  v7 = operator new(0x40u);
  v7[4] = winrt::impl::duplicate_hstring(*(winrt::impl **)(a2 + 32), v8);
  v7[5] = winrt::impl::duplicate_hstring(*(winrt::impl **)(a2 + 40), v9);
  v7[6] = winrt::impl::duplicate_hstring(*(winrt::impl **)(a2 + 48), v10);
  v7[7] = *(_QWORD *)(a2 + 56);
  *v7 = v6;
  v7[2] = v6;
  *((_WORD *)v7 + 12) = 0;
  v7[1] = a3;
  *((_BYTE *)v7 + 24) = *(_BYTE *)(a2 + 24);
  *v7 = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(
          a1,
          *(_QWORD *)a2,
          v7);
  v7[2] = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(
            a1,
            *(_QWORD *)(a2 + 16),
            v7);
  return v7;
}

```

## disassembly

```asm
0x18000e040  mov     [rsp+arg_10], rbx
0x18000e045  push    rbp
0x18000e046  push    rsi
0x18000e047  push    rdi
0x18000e048  push    r14
0x18000e04a  push    r15
0x18000e04c  sub     rsp, 50h
0x18000e050  mov     r15, r8
0x18000e053  mov     rsi, rdx
0x18000e056  mov     r14, rcx
0x18000e059  mov     rbp, [rcx]
0x18000e05c  cmp     byte ptr [rdx+19h], 0
0x18000e060  jnz     loc_18000E115
0x18000e066  mov     [rsp+78h+var_58], rcx
0x18000e06b  mov     [rsp+78h+var_50], 0
0x18000e074  mov     ecx, 40h ; '@'; Size
0x18000e079  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e07e  mov     rdi, rax
0x18000e081  mov     [rsp+78h+var_50], rax
0x18000e086  lea     rbx, [rax+20h]
0x18000e08a  mov     [rsp+78h+var_40], rbx
0x18000e08f  mov     rcx, [rsi+20h]; this
0x18000e093  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000e098  mov     [rbx], rax
0x18000e09b  add     rbx, 8
0x18000e09f  mov     [rsp+78h+var_38], rbx
0x18000e0a4  mov     rcx, [rsi+28h]; this
0x18000e0a8  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000e0ad  mov     [rbx], rax
0x18000e0b0  mov     rcx, [rsi+30h]; this
0x18000e0b4  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000e0b9  mov     [rbx+8], rax
0x18000e0bd  mov     rax, [rsi+38h]
0x18000e0c1  mov     [rbx+10h], rax
0x18000e0c5  mov     [rdi], rbp
0x18000e0c8  mov     [rdi+10h], rbp
0x18000e0cc  mov     word ptr [rdi+18h], 0
0x18000e0d2  mov     [rdi+8], r15
0x18000e0d6  movzx   eax, byte ptr [rsi+18h]
0x18000e0da  mov     [rdi+18h], al
0x18000e0dd  mov     [rsp+78h+var_58], r14
0x18000e0e2  mov     [rsp+78h+var_50], r14
0x18000e0e7  mov     [rsp+78h+var_48], rdi
0x18000e0ec  mov     r8, rdi
0x18000e0ef  mov     rdx, [rsi]
0x18000e0f2  mov     rcx, r14
0x18000e0f5  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@@9@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *,std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *)
0x18000e0fa  mov     [rdi], rax
0x18000e0fd  mov     r8, rdi
0x18000e100  mov     rdx, [rsi+10h]
0x18000e104  mov     rcx, r14
0x18000e107  call    ??$_Copy_nodes@$0A@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@@9@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@PEAX@1@PEAU21@0@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Copy_nodes<0>(std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *,std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *> *)
0x18000e10c  mov     [rdi+10h], rax
0x18000e110  mov     rax, rdi
0x18000e113  jmp     short loc_18000E118
0x18000e115  mov     rax, rbp
0x18000e118  mov     rbx, [rsp+78h+arg_10]
0x18000e120  add     rsp, 50h
0x18000e124  pop     r15
0x18000e126  pop     r14
0x18000e128  pop     rdi
0x18000e129  pop     rsi
0x18000e12a  pop     rbp
0x18000e12b  retn
```

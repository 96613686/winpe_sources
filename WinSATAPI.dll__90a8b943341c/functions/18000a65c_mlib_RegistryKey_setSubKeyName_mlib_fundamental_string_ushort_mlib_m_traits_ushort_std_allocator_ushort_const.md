# mlib::RegistryKey::setSubKeyName(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000a65c`
- end: `0x18000a731`
- name: `?setSubKeyName@RegistryKey@mlib@@QEAAXAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180001ed0`

## callees

- `0x180004990`
- `0x180008490`
- `0x18000a65c`
- `0x18000aa60`
- `0x18000aa80`
- `0x1800110f8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a6e7`

## pseudocode

```c
_QWORD *__fastcall mlib::RegistryKey::setSubKeyName(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  _QWORD **v3; // rsi
  _QWORD *result; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rdi
  _QWORD **v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax

  v2 = (_QWORD *)*a2;
  v3 = (_QWORD **)(a1 + 16);
  if ( *(_QWORD *)(a1 + 16) )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(a1 + 16);
  *v3 = v2;
  ++v2[2];
  result = mlib::RegistryBaseKey::cleanup(v3);
  v7 = *(_QWORD **)(a1 + 40);
  v8 = (_QWORD **)(a1 + 24);
  if ( *v7 )
  {
    ++v7[2];
    if ( *v8 )
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v8);
    *v8 = v7;
    v10 = v7[2];
    v7[2] = v10;
    if ( !v10 )
    {
      mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::~mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v7);
      operator delete(v7);
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      v8,
      v6,
      92);
    return (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
                       v8,
                       0,
                       **v8,
                       (*v3)[3],
                       **v3);
  }
  else
  {
    v9 = *v3;
    if ( *v8 )
      result = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v8);
    *v8 = v9;
    ++v9[2];
  }
  return result;
}

```

## disassembly

```asm
0x18000a65c  mov     [rsp+arg_0], rbx
0x18000a661  mov     [rsp+arg_8], rsi
0x18000a666  push    rdi
0x18000a667  sub     rsp, 30h
0x18000a66b  mov     rdi, [rdx]
0x18000a66e  lea     rsi, [rcx+10h]
0x18000a672  cmp     qword ptr [rsi], 0
0x18000a676  mov     rbx, rcx
0x18000a679  jz      short loc_18000A683
0x18000a67b  mov     rcx, rsi
0x18000a67e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000a683  mov     [rsi], rdi
0x18000a686  mov     rcx, rsi
0x18000a689  inc     qword ptr [rdi+10h]
0x18000a68d  call    ?cleanup@RegistryBaseKey@mlib@@SAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::RegistryBaseKey::cleanup(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18000a692  mov     rdi, [rbx+28h]
0x18000a696  add     rbx, 18h
0x18000a69a  cmp     qword ptr [rdi], 0
0x18000a69e  jnz     short loc_18000A6BA
0x18000a6a0  cmp     qword ptr [rbx], 0
0x18000a6a4  mov     rdi, [rsi]
0x18000a6a7  jz      short loc_18000A6B1
0x18000a6a9  mov     rcx, rbx
0x18000a6ac  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000a6b1  mov     [rbx], rdi
0x18000a6b4  inc     qword ptr [rdi+10h]
0x18000a6b8  jmp     short loc_18000A720
0x18000a6ba  inc     qword ptr [rdi+10h]
0x18000a6be  cmp     qword ptr [rbx], 0
0x18000a6c2  jz      short loc_18000A6CC
0x18000a6c4  mov     rcx, rbx
0x18000a6c7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000a6cc  mov     [rbx], rdi
0x18000a6cf  mov     rax, [rdi+10h]
0x18000a6d3  mov     [rdi+10h], rax
0x18000a6d7  test    rax, rax
0x18000a6da  jnz     short loc_18000A6F3
0x18000a6dc  mov     rcx, rdi
0x18000a6df  call    ??1?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@XZ; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::~mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x18000a6e4  mov     rcx, rdi
0x18000a6e7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a6ee  nop     dword ptr [rax+rax+00h]
0x18000a6f3  mov     r8d, 5Ch ; '\'
0x18000a6f9  mov     rcx, rbx
0x18000a6fc  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@_KG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(unsigned __int64,ushort)
0x18000a701  mov     r9, [rsi]
0x18000a704  xor     edx, edx
0x18000a706  mov     r8, [rbx]
0x18000a709  mov     rcx, rbx
0x18000a70c  mov     rax, [r9]
0x18000a70f  mov     r9, [r9+18h]
0x18000a713  mov     r8, [r8]
0x18000a716  mov     [rsp+38h+var_18], rax
0x18000a71b  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18000a720  mov     rbx, [rsp+38h+arg_0]
0x18000a725  mov     rsi, [rsp+38h+arg_8]
0x18000a72a  add     rsp, 30h
0x18000a72e  pop     rdi
0x18000a72f  retn
```

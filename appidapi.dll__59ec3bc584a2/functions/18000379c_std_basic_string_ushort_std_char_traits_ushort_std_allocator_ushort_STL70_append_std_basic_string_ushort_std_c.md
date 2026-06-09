# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::append(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000379c`
- end: `0x18000389f`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003210`
- `0x1800038a8`

## callees

- `0x1800016a4`
- `0x180001700`
- `0x1800035a4`
- `0x18000379c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003877`
- `msvcrt!memcpy_s` at `0x180003877`

## pseudocode

```c
__int64 __fastcall std::wstring::append(__int64 a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r14
  unsigned __int64 v8; // rdi
  _QWORD *v9; // rax
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rsi
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx

  v4 = a4;
  if ( a2[3] < a3 )
    std::_String_base::_Xran();
  if ( a2[3] - a3 < a4 )
    v4 = a2[3] - a3;
  if ( ~*(_QWORD *)(a1 + 24) <= v4 )
    std::_String_base::_Xlen();
  if ( v4 )
  {
    v8 = v4 + *(_QWORD *)(a1 + 24);
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( *(_QWORD *)(a1 + 32) < v8 )
    {
      std::wstring::_Copy(a1, v4 + *(_QWORD *)(a1 + 24), *(_QWORD *)(a1 + 24));
      if ( !v8 )
        return a1;
      goto LABEL_12;
    }
    if ( v8 )
    {
LABEL_12:
      v9 = a2 + 1;
      if ( a2[4] >= 8u )
        v9 = (_QWORD *)*v9;
      v10 = *(_QWORD *)(a1 + 32);
      v11 = (_QWORD *)(a1 + 8);
      if ( v10 < 8 )
        v12 = (_QWORD *)(a1 + 8);
      else
        v12 = (_QWORD *)*v11;
      memcpy_s((char *)v12 + 2 * *(_QWORD *)(a1 + 24), 2 * (v10 - *(_QWORD *)(a1 + 24)), (char *)v9 + 2 * a3, 2 * v4);
      if ( *(_QWORD *)(a1 + 32) >= 8u )
        v11 = (_QWORD *)*v11;
      *(_QWORD *)(a1 + 24) = v8;
      *((_WORD *)v11 + v8) = 0;
      return a1;
    }
    v13 = (_QWORD *)(a1 + 8);
    if ( *(_QWORD *)(a1 + 32) >= 8u )
      v13 = (_QWORD *)*v13;
    *(_QWORD *)(a1 + 24) = 0;
    *(_WORD *)v13 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000379c  push    rbx
0x18000379e  push    rbp
0x18000379f  push    rsi
0x1800037a0  push    rdi
0x1800037a1  push    r14
0x1800037a3  sub     rsp, 20h
0x1800037a7  mov     r14, r9
0x1800037aa  mov     rbp, r8
0x1800037ad  mov     rsi, rdx
0x1800037b0  mov     rbx, rcx
0x1800037b3  cmp     [rdx+18h], r8
0x1800037b7  jnb     short loc_1800037BE
0x1800037b9  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800037be  mov     rax, [rsi+18h]
0x1800037c2  sub     rax, rbp
0x1800037c5  cmp     rax, r14
0x1800037c8  cmovb   r14, rax
0x1800037cc  mov     rax, [rbx+18h]
0x1800037d0  not     rax
0x1800037d3  cmp     rax, r14
0x1800037d6  ja      short loc_1800037DD
0x1800037d8  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800037dd  test    r14, r14
0x1800037e0  jz      loc_180003891
0x1800037e6  mov     rdi, [rbx+18h]
0x1800037ea  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800037f4  add     rdi, r14
0x1800037f7  cmp     rdi, rax
0x1800037fa  jbe     short loc_180003801
0x1800037fc  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180003801  cmp     [rbx+20h], rdi
0x180003805  jnb     short loc_180003840
0x180003807  mov     r8, [rbx+18h]
0x18000380b  mov     rdx, rdi
0x18000380e  mov     rcx, rbx
0x180003811  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180003816  test    rdi, rdi
0x180003819  jz      short loc_180003891
0x18000381b  cmp     qword ptr [rsi+20h], 8
0x180003820  lea     rax, [rsi+8]
0x180003824  jb      short loc_180003829
0x180003826  mov     rax, [rax]
0x180003829  mov     rdx, [rbx+20h]
0x18000382d  lea     rsi, [rbx+8]
0x180003831  mov     r10, [rbx+18h]
0x180003835  cmp     rdx, 8
0x180003839  jb      short loc_180003862
0x18000383b  mov     rcx, [rsi]
0x18000383e  jmp     short loc_180003865
0x180003840  test    rdi, rdi
0x180003843  jnz     short loc_18000381B
0x180003845  cmp     qword ptr [rbx+20h], 8
0x18000384a  lea     rcx, [rbx+8]
0x18000384e  jb      short loc_180003853
0x180003850  mov     rcx, [rcx]
0x180003853  xor     eax, eax
0x180003855  mov     qword ptr [rbx+18h], 0
0x18000385d  mov     [rcx], ax
0x180003860  jmp     short loc_180003891
0x180003862  mov     rcx, rsi
0x180003865  sub     rdx, r10
0x180003868  lea     r9, [r14+r14]; SourceSize
0x18000386c  add     rdx, rdx; DestinationSize
0x18000386f  lea     r8, [rax+rbp*2]; Source
0x180003873  lea     rcx, [rcx+r10*2]; Destination
0x180003877  call    cs:__imp_memcpy_s
0x18000387d  cmp     qword ptr [rbx+20h], 8
0x180003882  jb      short loc_180003887
0x180003884  mov     rsi, [rsi]
0x180003887  xor     eax, eax
0x180003889  mov     [rbx+18h], rdi
0x18000388d  mov     [rsi+rdi*2], ax
0x180003891  mov     rax, rbx
0x180003894  add     rsp, 20h
0x180003898  pop     r14
0x18000389a  pop     rdi
0x18000389b  pop     rsi
0x18000389c  pop     rbp
0x18000389d  pop     rbx
0x18000389e  retn
```

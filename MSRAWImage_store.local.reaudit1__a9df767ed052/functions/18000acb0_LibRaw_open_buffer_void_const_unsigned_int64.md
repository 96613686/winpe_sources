# LibRaw::open_buffer(void const *,unsigned __int64)

- ea: `0x18000acb0`
- end: `0x18000ade0`
- name: `?open_buffer@LibRaw@@QEAAHPEBX_K@Z`
- size: `304`
- prototype: `int(LibRaw *__hidden this, const void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800abf54`

## callees

- `0x180003044`
- `0x180006380`
- `0x18000acb0`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LibRaw::open_buffer(LibRaw *this, char *a2, unsigned __int64 a3)
{
  __int64 result; // rax
  LibRaw_buffer_datastream *v7; // rax
  LibRaw_buffer_datastream *v8; // rbx
  LibRaw_buffer_datastream *v9; // rcx
  unsigned int (__fastcall *v10)(LibRaw_buffer_datastream *); // rax
  unsigned int v11; // esi

  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 4294867287LL;
  if ( a3 > 0x7FFFFFFF )
    return 4294867284LL;
  try
  {
    v7 = (LibRaw_buffer_datastream *)operator new(0x20u);
    if ( v7 )
      v8 = LibRaw_buffer_datastream::LibRaw_buffer_datastream(v7, a2, a3);
    else
      v8 = 0;
    v9 = v8;
    v10 = *(unsigned int (__fastcall **)(LibRaw_buffer_datastream *))(*(_QWORD *)v8 + 8LL);
  }
  catch ( std::bad_alloc )
  {
    LibRaw::recycle(this);
    return 4294867289LL;
  }
  if ( !v10(v9) )
  {
    (**(void (__fastcall ***)(LibRaw_buffer_datastream *, __int64))v8)(v8, 1);
    return 4294867287LL;
  }
  *((_DWORD *)this + 95322) = 0;
  result = (**(__int64 (__fastcall ***)(LibRaw *, LibRaw_buffer_datastream *))this)(this, v8);
  v11 = result;
  if ( (_DWORD)result )
  {
    (**(void (__fastcall ***)(LibRaw_buffer_datastream *, __int64))v8)(v8, 1);
    *((_DWORD *)this + 95322) = 0;
    return v11;
  }
  else
  {
    *((_DWORD *)this + 95322) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000acb0  mov     [rsp+arg_0], rcx
0x18000acb5  push    rdi
0x18000acb6  sub     rsp, 30h
0x18000acba  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000acc3  mov     [rsp+38h+arg_10], rbx
0x18000acc8  mov     [rsp+38h+arg_18], rsi
0x18000accd  mov     rbx, r8
0x18000acd0  mov     rsi, rdx
0x18000acd3  mov     rdi, rcx
0x18000acd6  lea     rax, [rdx-1]
0x18000acda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000acde  ja      short loc_18000AD4D
0x18000ace0  cmp     rbx, 7FFFFFFFh
0x18000ace7  jbe     short loc_18000ACFE
0x18000ace9  mov     eax, 0FFFE7954h
0x18000acee  mov     rbx, [rsp+38h+arg_10]
0x18000acf3  mov     rsi, [rsp+38h+arg_18]
0x18000acf8  add     rsp, 30h
0x18000acfc  pop     rdi
0x18000acfd  retn
0x18000acfe  mov     ecx, 20h ; ' '; Size
0x18000ad03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad08  mov     [rsp+38h+arg_8], rax
0x18000ad0d  test    rax, rax
0x18000ad10  jz      short loc_18000AD25
0x18000ad12  mov     r8, rbx; unsigned __int64
0x18000ad15  mov     rdx, rsi; void *
0x18000ad18  mov     rcx, rax; this
0x18000ad1b  call    ??0LibRaw_buffer_datastream@@QEAA@PEBX_K@Z; LibRaw_buffer_datastream::LibRaw_buffer_datastream(void const *,unsigned __int64)
0x18000ad20  mov     rbx, rax
0x18000ad23  jmp     short loc_18000AD27
0x18000ad25  xor     ebx, ebx
0x18000ad27  mov     rax, [rbx]
0x18000ad2a  mov     rcx, rbx
0x18000ad2d  mov     rax, [rax+8]
0x18000ad31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad36  test    eax, eax
0x18000ad38  jnz     short loc_18000AD62
0x18000ad3a  mov     rax, [rbx]
0x18000ad3d  mov     edx, 1
0x18000ad42  mov     rcx, rbx
0x18000ad45  mov     rax, [rax]
0x18000ad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad4d  mov     eax, 0FFFE7957h
0x18000ad52  mov     rbx, [rsp+38h+arg_10]
0x18000ad57  mov     rsi, [rsp+38h+arg_18]
0x18000ad5c  add     rsp, 30h
0x18000ad60  pop     rdi
0x18000ad61  retn
0x18000ad62  mov     dword ptr [rdi+5D168h], 0
0x18000ad6c  mov     rax, [rdi]
0x18000ad6f  mov     rdx, rbx
0x18000ad72  mov     rcx, rdi
0x18000ad75  mov     rax, [rax]
0x18000ad78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7d  mov     esi, eax
0x18000ad7f  test    eax, eax
0x18000ad81  jnz     short loc_18000AD9E
0x18000ad83  mov     ecx, 1
0x18000ad88  mov     [rdi+5D168h], ecx
0x18000ad8e  mov     rbx, [rsp+38h+arg_10]
0x18000ad93  mov     rsi, [rsp+38h+arg_18]
0x18000ad98  add     rsp, 30h
0x18000ad9c  pop     rdi
0x18000ad9d  retn
0x18000ad9e  mov     rax, [rbx]
0x18000ada1  mov     edx, 1
0x18000ada6  mov     rcx, rbx
0x18000ada9  mov     rax, [rax]
0x18000adac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb1  xor     ecx, ecx
0x18000adb3  mov     [rdi+5D168h], ecx
0x18000adb9  mov     eax, esi
0x18000adbb  mov     rbx, [rsp+38h+arg_10]
0x18000adc0  mov     rsi, [rsp+38h+arg_18]
0x18000adc5  add     rsp, 30h
0x18000adc9  pop     rdi
0x18000adca  retn
0x18000adcb  mov     eax, 0FFFE7959h
0x18000add0  mov     rbx, [rsp+38h+arg_10]
0x18000add5  mov     rsi, [rsp+38h+arg_18]
0x18000adda  add     rsp, 30h
0x18000adde  pop     rdi
0x18000addf  retn
```

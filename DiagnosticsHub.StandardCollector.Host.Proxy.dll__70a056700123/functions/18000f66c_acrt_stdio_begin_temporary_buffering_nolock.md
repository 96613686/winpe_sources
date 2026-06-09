# __acrt_stdio_begin_temporary_buffering_nolock

- ea: `0x18000f66c`
- end: `0x18000f733`
- name: `__acrt_stdio_begin_temporary_buffering_nolock`
- size: `199`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180041454`
- `0x180041928`
- `0x180041a4c`
- `0x180041b78`
- `0x180041cb4`
- `0x180041df0`
- `0x180041f50`

## callees

- `0x1800078e0`
- `0x18000f510`
- `0x18000f620`
- `0x18000f66c`
- `0x180011f70`

## pseudocode

```c
char __fastcall _acrt_stdio_begin_temporary_buffering_nolock(__int64 a1)
{
  void **v2; // rdi

  if ( !(unsigned __int8)_acrt_should_use_temporary_buffer((FILE *)a1) )
    return 0;
  if ( (FILE *)a1 == _acrt_iob_func(1u) )
  {
    v2 = &_acrt_stdout_buffer;
  }
  else
  {
    if ( (FILE *)a1 != _acrt_iob_func(2u) )
      return 0;
    v2 = &_acrt_stderr_buffer;
  }
  ++cflush;
  if ( (*(_DWORD *)(a1 + 20) & 0x4C0) != 0 )
    return 0;
  _InterlockedOr((volatile signed __int32 *)(a1 + 20), 0x282u);
  if ( !*v2 )
  {
    *v2 = malloc_base(0x1000u);
    free_base(0);
  }
  if ( *v2 )
  {
    *(_QWORD *)(a1 + 8) = *v2;
    *(_QWORD *)a1 = *v2;
    *(_DWORD *)(a1 + 16) = 4096;
    *(_DWORD *)(a1 + 32) = 4096;
  }
  else
  {
    *(_DWORD *)(a1 + 16) = 2;
    *(_QWORD *)(a1 + 8) = a1 + 28;
    *(_QWORD *)a1 = a1 + 28;
    *(_DWORD *)(a1 + 32) = 2;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f66c  mov     [rsp+arg_0], rbx
0x18000f671  push    rdi
0x18000f672  sub     rsp, 20h
0x18000f676  mov     rbx, rcx
0x18000f679  call    __acrt_should_use_temporary_buffer
0x18000f67e  test    al, al
0x18000f680  jz      loc_18000F726
0x18000f686  mov     ecx, 1; Ix
0x18000f68b  call    __acrt_iob_func
0x18000f690  cmp     rbx, rax
0x18000f693  jnz     short loc_18000F69E
0x18000f695  lea     rdi, __acrt_stdout_buffer
0x18000f69c  jmp     short loc_18000F6B4
0x18000f69e  mov     ecx, 2; Ix
0x18000f6a3  call    __acrt_iob_func
0x18000f6a8  cmp     rbx, rax
0x18000f6ab  jnz     short loc_18000F726
0x18000f6ad  lea     rdi, __acrt_stderr_buffer
0x18000f6b4  inc     cs:_cflush
0x18000f6ba  mov     eax, [rbx+14h]
0x18000f6bd  nop
0x18000f6be  test    eax, 4C0h
0x18000f6c3  jnz     short loc_18000F726
0x18000f6c5  lock or dword ptr [rbx+14h], 282h
0x18000f6cd  cmp     qword ptr [rdi], 0
0x18000f6d1  jnz     short loc_18000F6E7
0x18000f6d3  mov     ecx, 1000h; Size
0x18000f6d8  call    _malloc_base
0x18000f6dd  xor     ecx, ecx; Block
0x18000f6df  mov     [rdi], rax
0x18000f6e2  call    _free_base
0x18000f6e7  mov     rcx, [rdi]
0x18000f6ea  test    rcx, rcx
0x18000f6ed  jnz     short loc_18000F70C
0x18000f6ef  lea     rcx, [rbx+1Ch]
0x18000f6f3  mov     dword ptr [rbx+10h], 2
0x18000f6fa  mov     [rbx+8], rcx
0x18000f6fe  mov     [rbx], rcx
0x18000f701  mov     dword ptr [rbx+20h], 2
0x18000f708  mov     al, 1
0x18000f70a  jmp     short loc_18000F728
0x18000f70c  mov     [rbx+8], rcx
0x18000f710  mov     rax, [rdi]
0x18000f713  mov     [rbx], rax
0x18000f716  mov     dword ptr [rbx+10h], 1000h
0x18000f71d  mov     dword ptr [rbx+20h], 1000h
0x18000f724  jmp     short loc_18000F708
0x18000f726  xor     al, al
0x18000f728  mov     rbx, [rsp+28h+arg_0]
0x18000f72d  add     rsp, 20h
0x18000f731  pop     rdi
0x18000f732  retn
```

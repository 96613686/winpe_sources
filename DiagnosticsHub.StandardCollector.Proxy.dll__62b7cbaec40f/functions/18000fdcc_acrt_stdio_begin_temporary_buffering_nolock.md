# __acrt_stdio_begin_temporary_buffering_nolock

- ea: `0x18000fdcc`
- end: `0x18000fe93`
- name: `__acrt_stdio_begin_temporary_buffering_nolock`
- size: `199`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180041734`
- `0x180041c08`
- `0x180041d2c`
- `0x180041e58`
- `0x180041f94`
- `0x1800420d0`
- `0x180042230`

## callees

- `0x180008040`
- `0x18000fc70`
- `0x18000fd80`
- `0x18000fdcc`
- `0x1800126d0`

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
0x18000fdcc  mov     [rsp+arg_0], rbx
0x18000fdd1  push    rdi
0x18000fdd2  sub     rsp, 20h
0x18000fdd6  mov     rbx, rcx
0x18000fdd9  call    __acrt_should_use_temporary_buffer
0x18000fdde  test    al, al
0x18000fde0  jz      loc_18000FE86
0x18000fde6  mov     ecx, 1; Ix
0x18000fdeb  call    __acrt_iob_func
0x18000fdf0  cmp     rbx, rax
0x18000fdf3  jnz     short loc_18000FDFE
0x18000fdf5  lea     rdi, __acrt_stdout_buffer
0x18000fdfc  jmp     short loc_18000FE14
0x18000fdfe  mov     ecx, 2; Ix
0x18000fe03  call    __acrt_iob_func
0x18000fe08  cmp     rbx, rax
0x18000fe0b  jnz     short loc_18000FE86
0x18000fe0d  lea     rdi, __acrt_stderr_buffer
0x18000fe14  inc     cs:_cflush
0x18000fe1a  mov     eax, [rbx+14h]
0x18000fe1d  nop
0x18000fe1e  test    eax, 4C0h
0x18000fe23  jnz     short loc_18000FE86
0x18000fe25  lock or dword ptr [rbx+14h], 282h
0x18000fe2d  cmp     qword ptr [rdi], 0
0x18000fe31  jnz     short loc_18000FE47
0x18000fe33  mov     ecx, 1000h; Size
0x18000fe38  call    _malloc_base
0x18000fe3d  xor     ecx, ecx; Block
0x18000fe3f  mov     [rdi], rax
0x18000fe42  call    _free_base
0x18000fe47  mov     rcx, [rdi]
0x18000fe4a  test    rcx, rcx
0x18000fe4d  jnz     short loc_18000FE6C
0x18000fe4f  lea     rcx, [rbx+1Ch]
0x18000fe53  mov     dword ptr [rbx+10h], 2
0x18000fe5a  mov     [rbx+8], rcx
0x18000fe5e  mov     [rbx], rcx
0x18000fe61  mov     dword ptr [rbx+20h], 2
0x18000fe68  mov     al, 1
0x18000fe6a  jmp     short loc_18000FE88
0x18000fe6c  mov     [rbx+8], rcx
0x18000fe70  mov     rax, [rdi]
0x18000fe73  mov     [rbx], rax
0x18000fe76  mov     dword ptr [rbx+10h], 1000h
0x18000fe7d  mov     dword ptr [rbx+20h], 1000h
0x18000fe84  jmp     short loc_18000FE68
0x18000fe86  xor     al, al
0x18000fe88  mov     rbx, [rsp+28h+arg_0]
0x18000fe8d  add     rsp, 20h
0x18000fe91  pop     rdi
0x18000fe92  retn
```

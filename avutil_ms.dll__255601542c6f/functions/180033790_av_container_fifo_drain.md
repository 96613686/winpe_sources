# av_container_fifo_drain

- ea: `0x180033790`
- end: `0x180033845`
- name: `av_container_fifo_drain`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180033790`
- `0x180039af0`
- `0x180039d60`
- `0x180042ad0`
- `0x18004e230`
- `0x180078c2c`

## string_xrefs

- `0x180033823`: `nb_elems <= av_fifo_can_read(cf->fifo)`

## pseudocode

```c
unsigned __int64 __fastcall av_container_fifo_drain(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  char v5; // [rsp+40h] [rbp+8h] BYREF

  result = av_fifo_can_read(*a1);
  if ( a2 > result )
  {
    av_log(
      0,
      0,
      "Assertion %s failed at %s:%d\n",
      "nb_elems <= av_fifo_can_read(cf->fifo)",
      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/container_fifo.c",
      153);
    abort();
  }
  while ( a2 )
  {
    --a2;
    if ( (int)av_fifo_read(*a1, &v5, 1) < 0 )
    {
      av_log(
        0,
        0,
        "Assertion %s failed at %s:%d\n",
        "ret >= 0",
        "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/container_fifo.c",
        157);
      abort();
    }
    result = av_refstruct_unref(&v5);
  }
  return result;
}

```

## disassembly

```asm
0x180033790  mov     [rsp+arg_8], rbx
0x180033795  push    rdi
0x180033796  sub     rsp, 30h
0x18003379a  mov     rdi, rcx
0x18003379d  mov     rbx, rdx
0x1800337a0  mov     rcx, [rcx]
0x1800337a3  call    av_fifo_can_read
0x1800337a8  cmp     rbx, rax
0x1800337ab  ja      short loc_180033814
0x1800337ad  jmp     short loc_1800337D3
0x1800337af  mov     rcx, [rdi]
0x1800337b2  lea     rdx, [rsp+38h+arg_0]
0x1800337b7  mov     r8d, 1
0x1800337bd  dec     rbx
0x1800337c0  call    av_fifo_read
0x1800337c5  test    eax, eax
0x1800337c7  js      short loc_1800337E3
0x1800337c9  lea     rcx, [rsp+38h+arg_0]
0x1800337ce  call    av_refstruct_unref
0x1800337d3  test    rbx, rbx
0x1800337d6  jnz     short loc_1800337AF
0x1800337d8  mov     rbx, [rsp+38h+arg_8]
0x1800337dd  add     rsp, 30h
0x1800337e1  pop     rdi
0x1800337e2  retn
0x1800337e3  lea     rax, aCW1SFfmpeginte_2; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x1800337ea  mov     [rsp+38h+var_10], 9Dh
0x1800337f2  lea     r9, aRet0_0; "ret >= 0"
0x1800337f9  mov     [rsp+38h+var_18], rax
0x1800337fe  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x180033805  xor     edx, edx
0x180033807  xor     ecx, ecx
0x180033809  call    av_log
0x18003380e  call    abort
0x180033814  lea     rax, aCW1SFfmpeginte_2; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x18003381b  mov     [rsp+38h+var_10], 99h
0x180033823  lea     r9, aNbElemsAvFifoC; "nb_elems <= av_fifo_can_read(cf->fifo)"
0x18003382a  mov     [rsp+38h+var_18], rax
0x18003382f  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x180033836  xor     edx, edx
0x180033838  xor     ecx, ecx
0x18003383a  call    av_log
0x18003383f  call    abort
```

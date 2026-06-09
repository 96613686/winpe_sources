# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000b2d8`
- end: `0x18000b35c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c450`
- `0x18000c990`
- `0x18000d9e0`
- `0x18000dd50`
- `0x18000df40`
- `0x18000e0f0`
- `0x18000e300`
- `0x18000fcd0`
- `0x1800114d8`

## callees

- `0x18000b2d8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000b317`
- `msvcrt!_vsnwprintf` at `0x18000b317`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000b2d8  mov     [rsp+arg_10], r8
0x18000b2dd  mov     qword ptr [rsp+Args], r9
0x18000b2e2  push    rbx
0x18000b2e3  push    rdi
0x18000b2e4  sub     rsp, 38h
0x18000b2e8  mov     rax, rdx
0x18000b2eb  mov     rdi, rcx
0x18000b2ee  test    rdx, rdx
0x18000b2f1  jz      short loc_18000B344
0x18000b2f3  cmp     rax, 7FFFFFFFh
0x18000b2f9  jbe     short loc_18000B302
0x18000b2fb  mov     edx, 80070057h
0x18000b300  jmp     short loc_18000B34E
0x18000b302  lea     rbx, [rdx-1]
0x18000b306  mov     [rsp+48h+var_28], 0
0x18000b30f  mov     rdx, rbx; BufferCount
0x18000b312  lea     r9, [rsp+48h+Args]; Args
0x18000b317  call    cs:__imp__vsnwprintf
0x18000b31d  test    eax, eax
0x18000b31f  js      short loc_18000B337
0x18000b321  cdqe
0x18000b323  cmp     rax, rbx
0x18000b326  ja      short loc_18000B337
0x18000b328  xor     edx, edx
0x18000b32a  cmp     rax, rbx
0x18000b32d  jnz     short loc_18000B353
0x18000b32f  xor     eax, eax
0x18000b331  mov     [rdi+rbx*2], ax
0x18000b335  jmp     short loc_18000B353
0x18000b337  xor     eax, eax
0x18000b339  mov     edx, 8007007Ah
0x18000b33e  mov     [rdi+rbx*2], ax
0x18000b342  jmp     short loc_18000B353
0x18000b344  mov     edx, 80070057h
0x18000b349  test    rax, rax
0x18000b34c  jz      short loc_18000B353
0x18000b34e  xor     ecx, ecx
0x18000b350  mov     [rdi], cx
0x18000b353  mov     eax, edx
0x18000b355  add     rsp, 38h
0x18000b359  pop     rdi
0x18000b35a  pop     rbx
0x18000b35b  retn
```

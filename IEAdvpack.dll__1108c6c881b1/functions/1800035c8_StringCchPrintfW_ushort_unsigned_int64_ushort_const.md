# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800035c8`
- end: `0x18000364c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180003978`
- `0x1800056d0`
- `0x1800068ac`
- `0x180006928`
- `0x1800079c0`
- `0x180009c14`
- `0x18000ced8`
- `0x18000d184`
- `0x180010050`
- `0x180010d50`
- `0x1800121d8`
- `0x1800126c0`
- `0x1800127bc`
- `0x180013b88`
- `0x180015924`
- `0x180015ef8`
- `0x180016268`
- `0x180018a30`

## callees

- `0x1800035c8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003607`
- `msvcrt!_vsnwprintf` at `0x180003607`

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
0x1800035c8  mov     [rsp+arg_10], r8
0x1800035cd  mov     qword ptr [rsp+Args], r9
0x1800035d2  push    rbx
0x1800035d3  push    rdi
0x1800035d4  sub     rsp, 38h
0x1800035d8  mov     rax, rdx
0x1800035db  mov     rdi, rcx
0x1800035de  test    rdx, rdx
0x1800035e1  jz      short loc_180003634
0x1800035e3  cmp     rax, 7FFFFFFFh
0x1800035e9  jbe     short loc_1800035F2
0x1800035eb  mov     edx, 80070057h
0x1800035f0  jmp     short loc_18000363E
0x1800035f2  lea     rbx, [rdx-1]
0x1800035f6  mov     [rsp+48h+var_28], 0
0x1800035ff  mov     rdx, rbx; BufferCount
0x180003602  lea     r9, [rsp+48h+Args]; Args
0x180003607  call    cs:__imp__vsnwprintf
0x18000360d  test    eax, eax
0x18000360f  js      short loc_180003627
0x180003611  cdqe
0x180003613  cmp     rax, rbx
0x180003616  ja      short loc_180003627
0x180003618  xor     edx, edx
0x18000361a  cmp     rax, rbx
0x18000361d  jnz     short loc_180003643
0x18000361f  xor     eax, eax
0x180003621  mov     [rdi+rbx*2], ax
0x180003625  jmp     short loc_180003643
0x180003627  xor     eax, eax
0x180003629  mov     edx, 8007007Ah
0x18000362e  mov     [rdi+rbx*2], ax
0x180003632  jmp     short loc_180003643
0x180003634  mov     edx, 80070057h
0x180003639  test    rax, rax
0x18000363c  jz      short loc_180003643
0x18000363e  xor     ecx, ecx
0x180003640  mov     [rdi], cx
0x180003643  mov     eax, edx
0x180003645  add     rsp, 38h
0x180003649  pop     rdi
0x18000364a  pop     rbx
0x18000364b  retn
```

# WICCreateIcmColorTransform

- ea: `0x18000be7c`
- end: `0x18000bed5`
- name: `WICCreateIcmColorTransform`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b7b0`
- `0x18001d240`

## callees

- `0x180009590`
- `0x18000be7c`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall WICCreateIcmColorTransform(_QWORD *a1)
{
  __int64 result; // rax
  CIcmColorTransform *v3; // rax
  CIcmColorTransform *v4; // rcx

  result = 2147942487LL;
  if ( a1 )
  {
    v3 = (CIcmColorTransform *)operator new(0x130u);
    if ( v3 )
    {
      v4 = CIcmColorTransform::CIcmColorTransform(v3);
      result = 2147942414LL;
      if ( v4 )
      {
        *a1 = (char *)v4 + 72;
        (*(void (__fastcall **)(CIcmColorTransform *))(*(_QWORD *)v4 + 8LL))(v4);
        return 0;
      }
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000be7c  push    rbx
0x18000be7e  sub     rsp, 20h
0x18000be82  mov     rbx, rcx
0x18000be85  mov     eax, 80070057h
0x18000be8a  test    rcx, rcx
0x18000be8d  jz      short loc_18000BECF
0x18000be8f  mov     ecx, 130h; Size
0x18000be94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000be99  test    rax, rax
0x18000be9c  jz      short loc_18000BECA
0x18000be9e  mov     rcx, rax; this
0x18000bea1  call    ??0CIcmColorTransform@@QEAA@XZ; CIcmColorTransform::CIcmColorTransform(void)
0x18000bea6  mov     rcx, rax
0x18000bea9  mov     eax, 8007000Eh
0x18000beae  test    rcx, rcx
0x18000beb1  jz      short loc_18000BECF
0x18000beb3  lea     rax, [rcx+48h]
0x18000beb7  mov     [rbx], rax
0x18000beba  mov     rax, [rcx]
0x18000bebd  mov     rax, [rax+8]
0x18000bec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec6  xor     eax, eax
0x18000bec8  jmp     short loc_18000BECF
0x18000beca  mov     eax, 8007000Eh
0x18000becf  add     rsp, 20h
0x18000bed3  pop     rbx
0x18000bed4  retn
```

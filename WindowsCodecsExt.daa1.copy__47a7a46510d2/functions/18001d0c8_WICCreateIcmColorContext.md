# WICCreateIcmColorContext

- ea: `0x18001d0c8`
- end: `0x18001d121`
- name: `WICCreateIcmColorContext`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bd40`
- `0x18001883c`

## callees

- `0x180014a58`
- `0x18001d0c8`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall WICCreateIcmColorContext(_QWORD *a1)
{
  __int64 result; // rax
  CIcmColorContext *v3; // rax
  CIcmColorContext *v4; // rcx

  result = 2147942487LL;
  if ( a1 )
  {
    v3 = (CIcmColorContext *)operator new(0xD8u);
    if ( v3 )
    {
      v4 = CIcmColorContext::CIcmColorContext(v3);
      result = 2147942414LL;
      if ( v4 )
      {
        *a1 = (char *)v4 + 72;
        (*(void (__fastcall **)(CIcmColorContext *))(*(_QWORD *)v4 + 8LL))(v4);
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
0x18001d0c8  push    rbx
0x18001d0ca  sub     rsp, 20h
0x18001d0ce  mov     rbx, rcx
0x18001d0d1  mov     eax, 80070057h
0x18001d0d6  test    rcx, rcx
0x18001d0d9  jz      short loc_18001D11B
0x18001d0db  mov     ecx, 0D8h; Size
0x18001d0e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d0e5  test    rax, rax
0x18001d0e8  jz      short loc_18001D116
0x18001d0ea  mov     rcx, rax; this
0x18001d0ed  call    ??0CIcmColorContext@@QEAA@XZ; CIcmColorContext::CIcmColorContext(void)
0x18001d0f2  mov     rcx, rax
0x18001d0f5  mov     eax, 8007000Eh
0x18001d0fa  test    rcx, rcx
0x18001d0fd  jz      short loc_18001D11B
0x18001d0ff  lea     rax, [rcx+48h]
0x18001d103  mov     [rbx], rax
0x18001d106  mov     rax, [rcx]
0x18001d109  mov     rax, [rax+8]
0x18001d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d112  xor     eax, eax
0x18001d114  jmp     short loc_18001D11B
0x18001d116  mov     eax, 8007000Eh
0x18001d11b  add     rsp, 20h
0x18001d11f  pop     rbx
0x18001d120  retn
```

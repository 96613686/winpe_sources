# std::vector<_STORAGE_DEVICE_DATA,std::allocator<_STORAGE_DEVICE_DATA>>::~vector<_STORAGE_DEVICE_DATA,std::allocator<_STORAGE_DEVICE_DATA>>(void)

- ea: `0x180006cd0`
- end: `0x180006d53`
- name: `??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ`
- size: `131`
- prototype: `void __fastcall(char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800071b0`
- `0x180007c90`
- `0x180007da8`
- `0x180008d20`
- `0x18000ed46`
- `0x18000ed8e`
- `0x18000f190`

## callees

- `0x18000207c`
- `0x180006cd0`

## pseudocode

```c
void __fastcall std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(char **a1)
{
  char *v1; // rdx
  char *v3; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(16 * ((a1[2] - v1) >> 4)) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180006cd0  push    rbx
0x180006cd2  sub     rsp, 20h
0x180006cd6  mov     rdx, [rcx]
0x180006cd9  mov     rbx, rcx
0x180006cdc  test    rdx, rdx
0x180006cdf  jz      short loc_180006D4D
0x180006ce1  mov     rax, [rcx+10h]
0x180006ce5  mov     rcx, 0DAB7EC1DD3431B57h
0x180006cef  sub     rax, rdx
0x180006cf2  sar     rax, 4
0x180006cf6  imul    rax, rcx
0x180006cfa  imul    rcx, rax, 670h
0x180006d01  cmp     rcx, 1000h
0x180006d08  jb      short loc_180006D28
0x180006d0a  mov     rax, [rdx-8]
0x180006d0e  sub     rdx, rax
0x180006d11  sub     rdx, 8
0x180006d15  cmp     rdx, 1Fh
0x180006d19  ja      short loc_180006D21
0x180006d1b  add     rcx, 27h ; '''
0x180006d1f  jmp     short loc_180006D2B
0x180006d21  mov     ecx, 5
0x180006d26  int     29h; Win8: RtlFailFast(ecx)
0x180006d28  mov     rax, rdx
0x180006d2b  mov     rdx, rcx
0x180006d2e  mov     rcx, rax; Block
0x180006d31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006d36  mov     qword ptr [rbx], 0
0x180006d3d  mov     qword ptr [rbx+8], 0
0x180006d45  mov     qword ptr [rbx+10h], 0
0x180006d4d  add     rsp, 20h
0x180006d51  pop     rbx
0x180006d52  retn
```

# pfnWrite

- ea: `0x1400234d0`
- end: `0x140023534`
- name: `pfnWrite`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD *pvCallbackState, const BYTE *pbData, ULONG cbData)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140009fb0`
- `0x14000fb30`
- `0x14001e124`
- `0x1400234d0`
- `0x1400c7a8a`

## pseudocode

```c
__int64 __fastcall pfnWrite(_QWORD *pvCallbackState, const BYTE *pbData, ULONG cbData)
{
  size_t v4; // rsi
  int v6; // eax
  unsigned int v7; // ebx

  v4 = cbData;
  v6 = sub_14001E124(pvCallbackState, cbData);
  v7 = v6;
  if ( v6 >= 0 )
  {
    memcpy((void *)(pvCallbackState[1] + *pvCallbackState), pbData, v4);
    pvCallbackState[1] += v4;
  }
  else
  {
    sub_140009FB0((unsigned int)v6);
  }
  sub_14000FB30(v7);
  if ( (v7 & 0x80000000) != 0 )
    sub_140009FB0(v7);
  sub_14000FB30(v7);
  return v7;
}

```

## disassembly

```asm
0x1400234d0  push    rbx
0x1400234d2  push    rbp
0x1400234d3  push    rsi
0x1400234d4  push    rdi
0x1400234d5  sub     rsp, 28h
0x1400234d9  mov     rbp, rdx
0x1400234dc  mov     esi, r8d
0x1400234df  mov     edx, r8d
0x1400234e2  mov     rdi, rcx
0x1400234e5  call    sub_14001E124
0x1400234ea  mov     ebx, eax
0x1400234ec  test    eax, eax
0x1400234ee  jns     short loc_1400234F9
0x1400234f0  mov     ecx, eax
0x1400234f2  call    sub_140009FB0
0x1400234f7  jmp     short loc_14002350F
0x1400234f9  mov     rcx, [rdi]
0x1400234fc  mov     r8, rsi; Size
0x1400234ff  add     rcx, [rdi+8]; void *
0x140023503  mov     rdx, rbp; Src
0x140023506  call    memcpy
0x14002350b  add     [rdi+8], rsi
0x14002350f  mov     ecx, ebx
0x140023511  call    sub_14000FB30
0x140023516  test    ebx, ebx
0x140023518  jns     short loc_140023521
0x14002351a  mov     ecx, ebx
0x14002351c  call    sub_140009FB0
0x140023521  mov     ecx, ebx
0x140023523  call    sub_14000FB30
0x140023528  mov     eax, ebx
0x14002352a  add     rsp, 28h
0x14002352e  pop     rdi
0x14002352f  pop     rsi
0x140023530  pop     rbp
0x140023531  pop     rbx
0x140023532  retn
```

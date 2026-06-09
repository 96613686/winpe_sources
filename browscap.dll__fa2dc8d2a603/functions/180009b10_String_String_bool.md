# String::String(bool)

- ea: `0x180009b10`
- end: `0x180009b61`
- name: `??0String@@QEAA@_N@Z`
- size: `81`
- prototype: `String *__fastcall(String *__hidden this, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007a70`
- `0x180008bc4`
- `0x180008e40`
- `0x18000a750`

## callees

- `0x1800099f8`
- `0x180009b10`
- `0x180009c40`
- `0x180009d8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
String *__fastcall String::String(String *this)
{
  StringBuffer *v2; // rax

  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 1;
  v2 = (StringBuffer *)operator new(0x28u);
  if ( v2 )
    v2 = StringBuffer::StringBuffer(v2, &byte_18000F1B7);
  TRefPtr<StringBuffer>::Set(this, v2);
  return this;
}

```

## disassembly

```asm
0x180009b10  mov     [rsp+arg_0], rcx
0x180009b15  push    rbx
0x180009b16  sub     rsp, 20h
0x180009b1a  mov     rbx, rcx
0x180009b1d  mov     qword ptr [rcx], 0
0x180009b24  mov     byte ptr [rcx+8], 1
0x180009b28  mov     ecx, 28h ; '('; unsigned __int64
0x180009b2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b32  mov     [rsp+28h+arg_10], rax
0x180009b37  test    rax, rax
0x180009b3a  jz      short loc_180009B4C
0x180009b3c  lea     rdx, byte_18000F1B7; char *
0x180009b43  mov     rcx, rax; this
0x180009b46  call    ??0StringBuffer@@QEAA@PEBD@Z; StringBuffer::StringBuffer(char const *)
0x180009b4b  nop
0x180009b4c  mov     rdx, rax
0x180009b4f  mov     rcx, rbx
0x180009b52  call    ?Set@?$TRefPtr@VStringBuffer@@@@QEAAXPEAVStringBuffer@@@Z; TRefPtr<StringBuffer>::Set(StringBuffer *)
0x180009b57  nop
0x180009b58  mov     rax, rbx
0x180009b5b  add     rsp, 20h
0x180009b5f  pop     rbx
0x180009b60  retn
```

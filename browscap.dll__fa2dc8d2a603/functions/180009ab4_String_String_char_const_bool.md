# String::String(char const *,bool)

- ea: `0x180009ab4`
- end: `0x180009b07`
- name: `??0String@@QEAA@PEBD_N@Z`
- size: `83`
- prototype: `String *__fastcall(String *this, const char *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x1800076e8`
- `0x180007a70`
- `0x1800081b0`
- `0x180008940`
- `0x180008bc4`
- `0x180008fa8`
- `0x180009530`
- `0x18000a750`
- `0x18000a920`
- `0x18000ae60`

## callees

- `0x1800099f8`
- `0x180009ab4`
- `0x180009c40`

## pseudocode

```c
String *__fastcall String::String(String *this, const char *a2)
{
  volatile signed __int32 *v4; // rax

  v4 = (volatile signed __int32 *)operator new(0x28u);
  if ( v4 )
    v4 = (volatile signed __int32 *)StringBuffer::StringBuffer((StringBuffer *)v4, a2);
  *(_QWORD *)this = v4;
  if ( v4 )
    _InterlockedIncrement(v4 + 2);
  *((_BYTE *)this + 8) = 1;
  return this;
}

```

## disassembly

```asm
0x180009ab4  mov     [rsp+arg_8], rbx
0x180009ab9  mov     [rsp+arg_0], rcx
0x180009abe  push    rdi
0x180009abf  sub     rsp, 20h
0x180009ac3  mov     rdi, rdx
0x180009ac6  mov     rbx, rcx
0x180009ac9  mov     ecx, 28h ; '('; unsigned __int64
0x180009ace  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ad3  mov     [rsp+28h+arg_0], rax
0x180009ad8  test    rax, rax
0x180009adb  jz      short loc_180009AE9
0x180009add  mov     rdx, rdi; char *
0x180009ae0  mov     rcx, rax; this
0x180009ae3  call    ??0StringBuffer@@QEAA@PEBD@Z; StringBuffer::StringBuffer(char const *)
0x180009ae8  nop
0x180009ae9  mov     [rbx], rax
0x180009aec  test    rax, rax
0x180009aef  jz      short loc_180009AF5
0x180009af1  lock inc dword ptr [rax+8]
0x180009af5  mov     byte ptr [rbx+8], 1
0x180009af9  mov     rax, rbx
0x180009afc  mov     rbx, [rsp+28h+arg_8]
0x180009b01  add     rsp, 20h
0x180009b05  pop     rdi
0x180009b06  retn
```

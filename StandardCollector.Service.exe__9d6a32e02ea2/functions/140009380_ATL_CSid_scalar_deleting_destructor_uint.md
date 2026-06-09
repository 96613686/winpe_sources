# ATL::CSid::`scalar deleting destructor'(uint)

- ea: `0x140009380`
- end: `0x1400093b4`
- name: `??_GCSid@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `ATL::CSid *__fastcall(ATL::CSid *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x140009380`
- `0x1400093b4`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ATL::CSid *__fastcall ATL::CSid::`scalar deleting destructor'(ATL::CSid *this, char a2)
{
  ATL::CSid::~CSid(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009380  mov     [rsp+arg_0], rbx
0x140009385  push    rdi
0x140009386  sub     rsp, 20h
0x14000938a  mov     ebx, edx
0x14000938c  mov     rdi, rcx
0x14000938f  call    ??1CSid@ATL@@UEAA@XZ
0x140009394  test    bl, 1
0x140009397  jz      short loc_1400093A6
0x140009399  mov     edx, 78h ; 'x'
0x14000939e  mov     rcx, rdi; Block
0x1400093a1  call    ??3@YAXPEAX_K@Z
0x1400093a6  mov     rbx, [rsp+28h+arg_0]
0x1400093ab  mov     rax, rdi
0x1400093ae  add     rsp, 20h
0x1400093b2  pop     rdi
0x1400093b3  retn
```

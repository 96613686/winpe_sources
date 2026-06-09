# CEnumSubCommands::Release(void)

- ea: `0x18000b160`
- end: `0x18000b199`
- name: `?Release@CEnumSubCommands@@UEAAKXZ`
- size: `57`
- prototype: `__int64 __fastcall(CEnumSubCommands *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006b74`
- `0x18000a738`
- `0x18000b160`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Release(CEnumSubCommands *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CEnumSubCommands::~CEnumSubCommands(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b160  mov     [rsp+arg_0], rbx
0x18000b165  push    rdi
0x18000b166  sub     rsp, 20h
0x18000b16a  mov     rbx, rcx
0x18000b16d  or      edi, 0FFFFFFFFh
0x18000b170  lock xadd [rcx+8], edi
0x18000b175  sub     edi, 1
0x18000b178  jnz     short loc_18000B18C
0x18000b17a  test    rcx, rcx
0x18000b17d  jz      short loc_18000B18C
0x18000b17f  call    ??1CEnumSubCommands@@QEAA@XZ; CEnumSubCommands::~CEnumSubCommands(void)
0x18000b184  mov     rcx, rbx; Block
0x18000b187  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b18c  mov     rbx, [rsp+28h+arg_0]
0x18000b191  mov     eax, edi
0x18000b193  add     rsp, 20h
0x18000b197  pop     rdi
0x18000b198  retn
```

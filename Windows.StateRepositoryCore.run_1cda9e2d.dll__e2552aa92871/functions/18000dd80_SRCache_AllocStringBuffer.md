# SRCache_AllocStringBuffer

- ea: `0x18000dd80`
- end: `0x18000ddb7`
- name: `SRCache_AllocStringBuffer`
- size: `55`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000bed8`
- `0x18000c928`
- `0x18000dd80`

## pseudocode

```c
__int64 __fastcall SRCache_AllocStringBuffer(unsigned int a1)
{
  __int64 *unique; // rax
  __int64 v3; // rbx
  char v4; // [rsp+38h] [rbp+10h] BYREF

  if ( !a1 )
    return 0;
  unique = (__int64 *)wil::make_unique_nothrow<unsigned short [0]>(&v4, a1);
  v3 = *unique;
  *unique = 0;
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v4);
  return v3;
}

```

## disassembly

```asm
0x18000dd80  push    rbx
0x18000dd82  sub     rsp, 20h
0x18000dd86  test    ecx, ecx
0x18000dd88  jnz     short loc_18000DD8E
0x18000dd8a  xor     eax, eax
0x18000dd8c  jmp     short loc_18000DDB1
0x18000dd8e  mov     edx, ecx
0x18000dd90  lea     rcx, [rsp+28h+arg_8]
0x18000dd95  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18000dd9a  lea     rcx, [rsp+28h+arg_8]
0x18000dd9f  mov     rbx, [rax]
0x18000dda2  mov     qword ptr [rax], 0
0x18000dda9  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000ddae  mov     rax, rbx
0x18000ddb1  add     rsp, 20h
0x18000ddb5  pop     rbx
0x18000ddb6  retn
```

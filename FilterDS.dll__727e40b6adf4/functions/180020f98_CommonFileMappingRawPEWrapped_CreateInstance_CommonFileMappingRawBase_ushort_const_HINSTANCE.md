# CommonFileMappingRawPEWrapped::CreateInstance(CommonFileMappingRawBase * *,ushort const *,HINSTANCE__ *)

- ea: `0x180020f98`
- end: `0x180020fef`
- name: `?CreateInstance@CommonFileMappingRawPEWrapped@@SAJPEAPEAVCommonFileMappingRawBase@@PEBGPEAUHINSTANCE__@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(struct CommonFileMappingRawBase **, unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020810`

## callees

- `0x180001a30`
- `0x180020a34`
- `0x180020f98`

## pseudocode

```c
__int64 __fastcall CommonFileMappingRawPEWrapped::CreateInstance(
        struct CommonFileMappingRawBase **a1,
        unsigned __int16 *a2,
        HINSTANCE a3)
{
  CommonFileMappingRawPEWrapped *v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    v6 = (CommonFileMappingRawPEWrapped *)operator new(0x50u);
    if ( v6 )
      v6 = CommonFileMappingRawPEWrapped::CommonFileMappingRawPEWrapped(v6, a2, a3);
    *a1 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x20,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filemap.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180020f98  mov     [rsp+arg_0], rbx
0x180020f9d  mov     [rsp+arg_8], rsi
0x180020fa2  push    rdi
0x180020fa3  sub     rsp, 20h
0x180020fa7  mov     rdi, r8
0x180020faa  mov     rsi, rdx
0x180020fad  mov     rbx, rcx
0x180020fb0  mov     ecx, 50h ; 'P'; Size
0x180020fb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020fba  mov     [rsp+28h+arg_18], rax
0x180020fbf  test    rax, rax
0x180020fc2  jz      short loc_180020FD3
0x180020fc4  mov     r8, rdi; HINSTANCE
0x180020fc7  mov     rdx, rsi; unsigned __int16 *
0x180020fca  mov     rcx, rax; this
0x180020fcd  call    ??0CommonFileMappingRawPEWrapped@@AEAA@PEBGPEAUHINSTANCE__@@@Z; CommonFileMappingRawPEWrapped::CommonFileMappingRawPEWrapped(ushort const *,HINSTANCE__ *)
0x180020fd2  nop
0x180020fd3  mov     [rbx], rax
0x180020fd6  xor     eax, eax
0x180020fd8  jmp     short loc_180020FDE
0x180020fda  mov     eax, dword ptr [rsp+28h+arg_18]
0x180020fde  mov     rbx, [rsp+28h+arg_0]
0x180020fe3  mov     rsi, [rsp+28h+arg_8]
0x180020fe8  add     rsp, 20h
0x180020fec  pop     rdi
0x180020fed  retn
```

# CreateMappedRegisters(MEMORY_MAPPED_BUFFER *,MEMORY_MAPPED_REGISTERS *)

- ea: `0x18000d748`
- end: `0x18000d7b0`
- name: `?CreateMappedRegisters@@YAJPEAUMEMORY_MAPPED_BUFFER@@PEAUMEMORY_MAPPED_REGISTERS@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(struct MEMORY_MAPPED_BUFFER *, struct MEMORY_MAPPED_REGISTERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012b04`

## callees

- `0x180007e24`
- `0x18000d504`
- `0x18000d748`

## pseudocode

```c
__int64 __fastcall CreateMappedRegisters(HANDLE *a1, struct MEMORY_MAPPED_REGISTERS *a2)
{
  int MappedBuffer; // eax
  unsigned int v5; // ebx
  char *v7; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  MappedBuffer = CreateMappedBuffer(0, 8u, a1);
  v5 = MappedBuffer;
  if ( MappedBuffer >= 0 )
  {
    v7 = (char *)a1[1];
    *((_QWORD *)a2 + 1) = v7;
    *(_QWORD *)a2 = v7 + 4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)(unsigned int)MappedBuffer,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x18000d748  mov     [rsp+arg_0], rbx
0x18000d74d  mov     [rsp+arg_8], rsi
0x18000d752  push    rdi; int
0x18000d753  sub     rsp, 20h
0x18000d757  mov     rdi, rdx
0x18000d75a  mov     rsi, rcx
0x18000d75d  mov     r8, rcx; struct MEMORY_MAPPED_BUFFER *
0x18000d760  mov     edx, 8; unsigned int
0x18000d765  xor     ecx, ecx; int
0x18000d767  call    ?CreateMappedBuffer@@YAJHKPEAUMEMORY_MAPPED_BUFFER@@@Z; CreateMappedBuffer(int,ulong,MEMORY_MAPPED_BUFFER *)
0x18000d76c  mov     ebx, eax
0x18000d76e  test    eax, eax
0x18000d770  jns     short loc_18000D78F
0x18000d772  mov     rcx, [rsp+28h]; this
0x18000d777  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d77e  mov     r9d, eax; char *
0x18000d781  mov     edx, 0A2h; void *
0x18000d786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d78b  mov     eax, ebx
0x18000d78d  jmp     short loc_18000D7A0
0x18000d78f  mov     rax, [rsi+8]
0x18000d793  mov     [rdi+8], rax
0x18000d797  add     rax, 4
0x18000d79b  mov     [rdi], rax
0x18000d79e  xor     eax, eax
0x18000d7a0  mov     rbx, [rsp+28h+arg_0]
0x18000d7a5  mov     rsi, [rsp+28h+arg_8]
0x18000d7aa  add     rsp, 20h
0x18000d7ae  pop     rdi
0x18000d7af  retn
```

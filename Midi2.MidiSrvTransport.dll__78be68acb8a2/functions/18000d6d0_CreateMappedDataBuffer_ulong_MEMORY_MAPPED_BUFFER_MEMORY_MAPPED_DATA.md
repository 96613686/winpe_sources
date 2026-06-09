# CreateMappedDataBuffer(ulong,MEMORY_MAPPED_BUFFER *,MEMORY_MAPPED_DATA *)

- ea: `0x18000d6d0`
- end: `0x18000d742`
- name: `?CreateMappedDataBuffer@@YAJKPEAUMEMORY_MAPPED_BUFFER@@PEAUMEMORY_MAPPED_DATA@@@Z`
- size: `114`
- prototype: `int(unsigned int, struct MEMORY_MAPPED_BUFFER *, struct MEMORY_MAPPED_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012b04`

## callees

- `0x180007e24`
- `0x18000d504`
- `0x18000d6d0`

## pseudocode

```c
__int64 __fastcall CreateMappedDataBuffer(__int64 a1, HANDLE *a2, struct MEMORY_MAPPED_DATA *a3)
{
  DWORD v5; // edx
  int MappedBuffer; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = *((_DWORD *)a3 + 2);
  if ( !v5 )
  {
    MappedBuffer = -2147024809;
    v7 = 139;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)(unsigned int)MappedBuffer,
      v9);
    return (unsigned int)MappedBuffer;
  }
  MappedBuffer = CreateMappedBuffer(1, v5, a2);
  if ( MappedBuffer < 0 )
  {
    v7 = 150;
    goto LABEL_3;
  }
  *(_QWORD *)a3 = a2[1];
  return 0;
}

```

## disassembly

```asm
0x18000d6d0  mov     [rsp+arg_0], rbx
0x18000d6d5  mov     [rsp+arg_8], rsi
0x18000d6da  push    rdi; int
0x18000d6db  sub     rsp, 20h
0x18000d6df  mov     rsi, rdx
0x18000d6e2  mov     rdi, r8
0x18000d6e5  mov     edx, [r8+8]; unsigned int
0x18000d6e9  test    edx, edx
0x18000d6eb  jnz     short loc_18000D70F
0x18000d6ed  mov     ebx, 80070057h
0x18000d6f2  mov     edx, 8Bh; void *
0x18000d6f7  mov     rcx, [rsp+28h]; this
0x18000d6fc  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000d703  mov     r9d, ebx; char *
0x18000d706  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d70b  mov     eax, ebx
0x18000d70d  jmp     short loc_18000D732
0x18000d70f  mov     r8, rsi; struct MEMORY_MAPPED_BUFFER *
0x18000d712  mov     ecx, 1; int
0x18000d717  call    ?CreateMappedBuffer@@YAJHKPEAUMEMORY_MAPPED_BUFFER@@@Z; CreateMappedBuffer(int,ulong,MEMORY_MAPPED_BUFFER *)
0x18000d71c  mov     ebx, eax
0x18000d71e  test    eax, eax
0x18000d720  jns     short loc_18000D729
0x18000d722  mov     edx, 96h
0x18000d727  jmp     short loc_18000D6F7
0x18000d729  mov     rax, [rsi+8]
0x18000d72d  mov     [rdi], rax
0x18000d730  xor     eax, eax
0x18000d732  mov     rbx, [rsp+28h+arg_0]
0x18000d737  mov     rsi, [rsp+28h+arg_8]
0x18000d73c  add     rsp, 20h
0x18000d740  pop     rdi
0x18000d741  retn
```

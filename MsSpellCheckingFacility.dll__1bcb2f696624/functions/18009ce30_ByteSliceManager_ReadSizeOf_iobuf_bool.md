# ByteSliceManager::ReadSizeOf(_iobuf *,bool)

- ea: `0x18009ce30`
- end: `0x18009cebe`
- name: `?ReadSizeOf@ByteSliceManager@@SAKPEAU_iobuf@@_N@Z`
- size: `142`
- prototype: `unsigned int __fastcall(FILE *Stream, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18009cbc0`

## callees

- `0x18009ce30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18009ce86`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18009ce86`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009ce47`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009ce69`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009ce47`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18009ce69`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18009ce54`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18009ce54`

## pseudocode

```c
__int64 __fastcall ByteSliceManager::ReadSizeOf(FILE *Stream, char a2)
{
  int v3; // eax
  int v4; // ebx
  int v5; // eax
  unsigned int Buffer; // [rsp+38h] [rbp+10h] BYREF

  LOBYTE(Buffer) = a2;
  if ( fseek(Stream, 0, 2) )
    return 0;
  v3 = _o_ftell(Stream);
  v4 = v3;
  if ( !v3 )
    return 0;
  if ( fseek(Stream, v3 - 4, 0) )
    return 0;
  Buffer = 0;
  if ( fread(&Buffer, 1u, 4u, Stream) != 4 )
    return 0;
  if ( (Buffer & 0xFF000000) != 0 )
    v5 = HIBYTE(Buffer) - 4;
  else
    v5 = (Buffer & 0xFFFFFF) - 8;
  return (unsigned int)(v4 + v5);
}

```

## disassembly

```asm
0x18009ce30  mov     [rsp+arg_0], rbx
0x18009ce35  mov     byte ptr [rsp+Buffer], dl
0x18009ce39  push    rdi
0x18009ce3a  sub     rsp, 20h
0x18009ce3e  xor     edx, edx; Offset
0x18009ce40  mov     rdi, rcx
0x18009ce43  lea     r8d, [rdx+2]; Origin
0x18009ce47  call    cs:__imp_fseek
0x18009ce4d  test    eax, eax
0x18009ce4f  jnz     short loc_18009CEB1
0x18009ce51  mov     rcx, rdi
0x18009ce54  call    cs:__imp__o_ftell
0x18009ce5a  mov     ebx, eax
0x18009ce5c  test    eax, eax
0x18009ce5e  jz      short loc_18009CEB1
0x18009ce60  lea     edx, [rax-4]; Offset
0x18009ce63  xor     r8d, r8d; Origin
0x18009ce66  mov     rcx, rdi; Stream
0x18009ce69  call    cs:__imp_fseek
0x18009ce6f  test    eax, eax
0x18009ce71  jnz     short loc_18009CEB1
0x18009ce73  mov     r9, rdi; Stream
0x18009ce76  mov     [rsp+28h+Buffer], eax
0x18009ce7a  lea     edx, [rax+1]; ElementSize
0x18009ce7d  lea     r8d, [rax+4]; ElementCount
0x18009ce81  lea     rcx, [rsp+28h+Buffer]; Buffer
0x18009ce86  call    cs:__imp_fread
0x18009ce8c  cmp     rax, 4
0x18009ce90  jnz     short loc_18009CEB1
0x18009ce92  mov     eax, [rsp+28h+Buffer]
0x18009ce96  test    eax, 0FF000000h
0x18009ce9b  jnz     short loc_18009CEA7
0x18009ce9d  and     eax, 0FFFFFFh
0x18009cea2  add     eax, 0FFFFFFF8h
0x18009cea5  jmp     short loc_18009CEAD
0x18009cea7  shr     eax, 18h
0x18009ceaa  add     eax, 0FFFFFFFCh
0x18009cead  add     eax, ebx
0x18009ceaf  jmp     short loc_18009CEB3
0x18009ceb1  xor     eax, eax
0x18009ceb3  mov     rbx, [rsp+28h+arg_0]
0x18009ceb8  add     rsp, 20h
0x18009cebc  pop     rdi
0x18009cebd  retn
```

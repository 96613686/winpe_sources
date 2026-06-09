# ByteSliceManager::ReadSizeOf(_iobuf *,bool)

- ea: `0x18006c268`
- end: `0x18006c2f6`
- name: `?ReadSizeOf@ByteSliceManager@@SAKPEAU_iobuf@@_N@Z`
- size: `142`
- prototype: `unsigned int __fastcall(FILE *Stream, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180035120`

## callees

- `0x18006c268`

## import_xrefs

- `msvcrt!ftell` at `0x18006c28c`
- `msvcrt!ftell` at `0x18006c28c`
- `msvcrt!fseek` at `0x18006c27f`
- `msvcrt!fseek` at `0x18006c2a1`
- `msvcrt!fseek` at `0x18006c27f`
- `msvcrt!fseek` at `0x18006c2a1`
- `msvcrt!fread` at `0x18006c2be`
- `msvcrt!fread` at `0x18006c2be`

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
  v3 = ftell(Stream);
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
0x18006c268  mov     [rsp+arg_0], rbx
0x18006c26d  mov     byte ptr [rsp+Buffer], dl
0x18006c271  push    rdi
0x18006c272  sub     rsp, 20h
0x18006c276  xor     edx, edx; Offset
0x18006c278  mov     rdi, rcx
0x18006c27b  lea     r8d, [rdx+2]; Origin
0x18006c27f  call    cs:__imp_fseek
0x18006c285  test    eax, eax
0x18006c287  jnz     short loc_18006C2E9
0x18006c289  mov     rcx, rdi; Stream
0x18006c28c  call    cs:__imp_ftell
0x18006c292  mov     ebx, eax
0x18006c294  test    eax, eax
0x18006c296  jz      short loc_18006C2E9
0x18006c298  lea     edx, [rax-4]; Offset
0x18006c29b  xor     r8d, r8d; Origin
0x18006c29e  mov     rcx, rdi; Stream
0x18006c2a1  call    cs:__imp_fseek
0x18006c2a7  test    eax, eax
0x18006c2a9  jnz     short loc_18006C2E9
0x18006c2ab  mov     r9, rdi; Stream
0x18006c2ae  mov     [rsp+28h+Buffer], eax
0x18006c2b2  lea     edx, [rax+1]; ElementSize
0x18006c2b5  lea     r8d, [rax+4]; ElementCount
0x18006c2b9  lea     rcx, [rsp+28h+Buffer]; Buffer
0x18006c2be  call    cs:__imp_fread
0x18006c2c4  cmp     rax, 4
0x18006c2c8  jnz     short loc_18006C2E9
0x18006c2ca  mov     eax, [rsp+28h+Buffer]
0x18006c2ce  test    eax, 0FF000000h
0x18006c2d3  jnz     short loc_18006C2DF
0x18006c2d5  and     eax, 0FFFFFFh
0x18006c2da  add     eax, 0FFFFFFF8h
0x18006c2dd  jmp     short loc_18006C2E5
0x18006c2df  shr     eax, 18h
0x18006c2e2  add     eax, 0FFFFFFFCh
0x18006c2e5  add     eax, ebx
0x18006c2e7  jmp     short loc_18006C2EB
0x18006c2e9  xor     eax, eax
0x18006c2eb  mov     rbx, [rsp+28h+arg_0]
0x18006c2f0  add     rsp, 20h
0x18006c2f4  pop     rdi
0x18006c2f5  retn
```

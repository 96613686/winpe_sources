# File::MapInNewWriteChunk(unsigned __int64,unsigned __int64,bool)

- ea: `0x180032a8c`
- end: `0x180032bb0`
- name: `?MapInNewWriteChunk@File@@AEAAK_K0_N@Z`
- size: `292`
- prototype: `unsigned int(File *__hidden this, unsigned __int64, unsigned __int64, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800323a4`
- `0x180032794`
- `0x180032f54`

## callees

- `0x180023548`
- `0x1800254b4`
- `0x180032a8c`
- `0x180033fa8`
- `0x180034ca4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032b39`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032b39`

## pseudocode

```c
__int64 __fastcall File::MapInNewWriteChunk(File *this, unsigned __int64 a2, __int64 a3, char a4)
{
  __int64 v5; // rax
  bool v6; // cf
  __int64 v7; // r8
  unsigned int v8; // edi

  *((_QWORD *)this + 21) = (a3 << 16) + 4096;
  *((_QWORD *)this + 4) = a3;
  if ( a4 )
  {
    v5 = 0;
    if ( a3 + 1 != (unsigned __int64)(*((_QWORD *)this + 7) - 4096LL) >> 16 )
      v5 = a3 + 1;
    *((_QWORD *)this + 3) = v5;
  }
  InitializeChunkHeaderInfo(*((struct ChunkHeader **)this + 20), a2);
  memset_0(*((void **)this + 28), 0, 0x100u);
  memset_0(*((void **)this + 63), 0, 0x80u);
  v6 = ++*((_DWORD *)this + 205) < 0x190u;
  *((_BYTE *)this + 827) = 1;
  *((_DWORD *)this + 203) = 0;
  if ( v6 )
    return 0;
  FlushFileBuffers(*((HANDLE *)this + 84));
  LOBYTE(v7) = 1;
  v8 = WriteFileHeader(*((void **)this + 84), (_DWORD *)this + 4, v7, 1);
  if ( !v8 )
  {
    *((_DWORD *)this + 205) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180032a8c  mov     [rsp+arg_0], rbx
0x180032a91  push    rdi
0x180032a92  sub     rsp, 30h
0x180032a96  mov     rax, r8
0x180032a99  mov     r11d, 1000h
0x180032a9f  shl     rax, 10h
0x180032aa3  mov     r10, rdx
0x180032aa6  add     rax, r11
0x180032aa9  mov     rbx, rcx
0x180032aac  mov     [rcx+0A8h], rax
0x180032ab3  mov     [rcx+20h], r8
0x180032ab7  test    r9b, r9b
0x180032aba  jz      short loc_180032AD8
0x180032abc  mov     rcx, [rcx+38h]
0x180032ac0  lea     rdx, [r8+1]
0x180032ac4  sub     rcx, r11
0x180032ac7  xor     eax, eax
0x180032ac9  shr     rcx, 10h
0x180032acd  cmp     rdx, rcx
0x180032ad0  cmovnz  rax, rdx
0x180032ad4  mov     [rbx+18h], rax
0x180032ad8  mov     rcx, [rbx+0A0h]; struct ChunkHeader *
0x180032adf  mov     rdx, r10; unsigned __int64
0x180032ae2  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180032ae7  mov     rcx, [rbx+0E0h]; void *
0x180032aee  xor     edx, edx; Val
0x180032af0  mov     r8d, 100h; Size
0x180032af6  call    memset_0
0x180032afb  mov     rcx, [rbx+1F8h]; void *
0x180032b02  xor     edx, edx; Val
0x180032b04  mov     r8d, 80h; Size
0x180032b0a  call    memset_0
0x180032b0f  inc     dword ptr [rbx+334h]
0x180032b15  cmp     dword ptr [rbx+334h], 190h
0x180032b1f  mov     byte ptr [rbx+33Bh], 1
0x180032b26  mov     dword ptr [rbx+32Ch], 0
0x180032b30  jb      short loc_180032BA3
0x180032b32  mov     rcx, [rbx+2A0h]; hFile
0x180032b39  call    cs:__imp_FlushFileBuffers
0x180032b3f  mov     rcx, [rbx+2A0h]; void *
0x180032b46  lea     rdx, [rbx+10h]; Buffer
0x180032b4a  mov     r9b, 1
0x180032b4d  mov     r8b, r9b
0x180032b50  call    WriteFileHeader
0x180032b55  mov     edi, eax
0x180032b57  test    eax, eax
0x180032b59  jz      short loc_180032B99
0x180032b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b62  lea     rax, WPP_GLOBAL_Control
0x180032b69  cmp     rcx, rax
0x180032b6c  jz      short loc_180032B95
0x180032b6e  test    dword ptr [rcx+1Ch], 8000h
0x180032b75  jz      short loc_180032B95
0x180032b77  cmp     byte ptr [rcx+19h], 2
0x180032b7b  jb      short loc_180032B95
0x180032b7d  mov     rcx, [rcx+10h]
0x180032b81  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180032b88  mov     edx, 65h ; 'e'
0x180032b8d  mov     r9d, edi
0x180032b90  call    WPP_SF_D
0x180032b95  mov     eax, edi
0x180032b97  jmp     short loc_180032BA5
0x180032b99  mov     dword ptr [rbx+334h], 0
0x180032ba3  xor     eax, eax
0x180032ba5  mov     rbx, [rsp+38h+arg_0]
0x180032baa  add     rsp, 30h
0x180032bae  pop     rdi
0x180032baf  retn
```

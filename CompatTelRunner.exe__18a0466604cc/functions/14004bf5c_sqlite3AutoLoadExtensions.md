# sqlite3AutoLoadExtensions

- ea: `0x14004bf5c`
- end: `0x14004c058`
- name: `sqlite3AutoLoadExtensions`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14003bbec`

## callees

- `0x14004bf5c`
- `0x140056170`
- `0x14008ac90`
- `0x1400a8010`

## string_xrefs

- `0x14004c01e`: `automatic extension loading failed: %s`

## pseudocode

```c
void __fastcall sqlite3AutoLoadExtensions(__int64 a1)
{
  int v2; // ebp
  __int64 v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64, const char **, __int64 (__fastcall **)()); // rsi
  unsigned int v7; // eax
  const char *v8; // [rsp+48h] [rbp+10h] BYREF

  if ( dword_1400C9240 )
  {
    v2 = 1;
    v3 = 0;
    do
    {
      v8 = 0;
      if ( (_BYTE)word_1400C84B4 )
      {
        v5 = ((__int64 (__fastcall *)(__int64))xmmword_1400C8520)(2);
        v4 = v5;
        if ( v5 )
          ((void (__fastcall *)(__int64))xmmword_1400C8530)(v5);
      }
      else
      {
        v4 = 0;
      }
      if ( (unsigned int)v3 < dword_1400C9240 )
      {
        v6 = *(__int64 (__fastcall **)(__int64, const char **, __int64 (__fastcall **)()))(qword_1400C9248 + 8 * v3);
      }
      else
      {
        v6 = 0;
        v2 = 0;
      }
      if ( v4 )
        ((void (__fastcall *)(__int64))xmmword_1400C8540)(v4);
      v8 = 0;
      if ( v6 )
      {
        v7 = v6(a1, &v8, off_1400A9650);
        if ( v7 )
        {
          sqlite3ErrorWithMsg(a1, v7, "automatic extension loading failed: %s", v8);
          v2 = 0;
        }
      }
      sqlite3_free(v8);
      v3 = (unsigned int)(v3 + 1);
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x14004bf5c  mov     [rsp+arg_0], rbx
0x14004bf61  mov     [rsp+arg_10], rbp
0x14004bf66  push    rsi
0x14004bf67  push    rdi
0x14004bf68  push    r14
0x14004bf6a  sub     rsp, 20h
0x14004bf6e  cmp     cs:dword_1400C9240, 0
0x14004bf75  mov     r14, rcx
0x14004bf78  jz      loc_14004C045
0x14004bf7e  mov     ebp, 1
0x14004bf83  xor     edi, edi
0x14004bf85  cmp     byte ptr cs:word_1400C84B4, 0
0x14004bf8c  mov     [rsp+38h+arg_8], 0
0x14004bf95  jnz     short loc_14004BF9B
0x14004bf97  xor     ebx, ebx
0x14004bf99  jmp     short loc_14004BFC3
0x14004bf9b  mov     rax, qword ptr cs:xmmword_1400C8520
0x14004bfa2  mov     ecx, 2
0x14004bfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bfac  mov     rbx, rax
0x14004bfaf  test    rax, rax
0x14004bfb2  jz      short loc_14004BFC3
0x14004bfb4  mov     rcx, rax
0x14004bfb7  mov     rax, qword ptr cs:xmmword_1400C8530
0x14004bfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bfc3  cmp     edi, cs:dword_1400C9240
0x14004bfc9  jb      short loc_14004BFD1
0x14004bfcb  xor     esi, esi
0x14004bfcd  xor     ebp, ebp
0x14004bfcf  jmp     short loc_14004BFDC
0x14004bfd1  mov     rax, cs:qword_1400C9248
0x14004bfd8  mov     rsi, [rax+rdi*8]
0x14004bfdc  test    rbx, rbx
0x14004bfdf  jz      short loc_14004BFF0
0x14004bfe1  mov     rax, qword ptr cs:xmmword_1400C8540
0x14004bfe8  mov     rcx, rbx
0x14004bfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bff0  mov     [rsp+38h+arg_8], 0
0x14004bff9  test    rsi, rsi
0x14004bffc  jz      short loc_14004C031
0x14004bffe  lea     r8, off_1400A9650
0x14004c005  mov     rcx, r14
0x14004c008  lea     rdx, [rsp+38h+arg_8]
0x14004c00d  mov     rax, rsi
0x14004c010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c015  test    eax, eax
0x14004c017  jz      short loc_14004C031
0x14004c019  mov     r9, [rsp+38h+arg_8]
0x14004c01e  lea     r8, aAutomaticExten; "automatic extension loading failed: %s"
0x14004c025  mov     edx, eax
0x14004c027  mov     rcx, r14
0x14004c02a  call    sqlite3ErrorWithMsg
0x14004c02f  xor     ebp, ebp
0x14004c031  mov     rcx, [rsp+38h+arg_8]
0x14004c036  call    sqlite3_free
0x14004c03b  inc     edi
0x14004c03d  test    ebp, ebp
0x14004c03f  jnz     loc_14004BF85
0x14004c045  mov     rbx, [rsp+38h+arg_0]
0x14004c04a  mov     rbp, [rsp+38h+arg_10]
0x14004c04f  add     rsp, 20h
0x14004c053  pop     r14
0x14004c055  pop     rdi
0x14004c056  pop     rsi
0x14004c057  retn
```

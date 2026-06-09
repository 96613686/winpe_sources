# CTransaction::Load(void *)

- ea: `0x1800637b8`
- end: `0x18006386d`
- name: `?Load@CTransaction@@QEAAHPEAX@Z`
- size: `181`
- prototype: `int(CTransaction *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180074154`

## callees

- `0x1800637b8`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x180063840`
- `msvcrt!free` at `0x18006384c`
- `msvcrt!free` at `0x180063840`
- `msvcrt!free` at `0x18006384c`
- `KERNEL32!ReadFile` at `0x1800637e4`
- `KERNEL32!ReadFile` at `0x180063826`
- `KERNEL32!ReadFile` at `0x1800637e4`
- `KERNEL32!ReadFile` at `0x180063826`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTransaction::Load(CTransaction *this, void *a2)
{
  void *v4; // rbx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+8h] BYREF
  void *v7; // [rsp+60h] [rbp+18h]

  NumberOfBytesRead = 0;
  if ( !ReadFile(a2, (char *)this + 16, 0x20u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 32 )
    return 0;
  if ( !*((_WORD *)this + 22) )
  {
    *((_QWORD *)this + 6) = 0;
    return 1;
  }
  v7 = 0;
  v4 = MmAllocate(*((unsigned __int16 *)this + 22));
  v7 = v4;
  if ( !ReadFile(a2, v4, *((unsigned __int16 *)this + 22), &NumberOfBytesRead, 0)
    || *((unsigned __int16 *)this + 22) != NumberOfBytesRead )
  {
    free(v4);
    return 0;
  }
  *((_QWORD *)this + 6) = v4;
  free(0);
  return 1;
}

```

## disassembly

```asm
0x1800637b8  mov     rax, rsp
0x1800637bb  mov     [rax+10h], rbx
0x1800637bf  push    rbp
0x1800637c0  push    rsi
0x1800637c1  push    rdi
0x1800637c2  sub     rsp, 30h
0x1800637c6  mov     rsi, rdx
0x1800637c9  mov     rdi, rcx
0x1800637cc  xor     ebp, ebp
0x1800637ce  mov     [rax+8], ebp
0x1800637d1  lea     rdx, [rcx+10h]; lpBuffer
0x1800637d5  mov     [rax-28h], rbp
0x1800637d9  lea     r9, [rax+8]; lpNumberOfBytesRead
0x1800637dd  lea     r8d, [rbp+20h]; nNumberOfBytesToRead
0x1800637e1  mov     rcx, rsi; hFile
0x1800637e4  call    cs:__imp_ReadFile
0x1800637ea  test    eax, eax
0x1800637ec  jz      short loc_180063853
0x1800637ee  cmp     [rsp+48h+NumberOfBytesRead], 20h ; ' '
0x1800637f3  jnz     short loc_180063853
0x1800637f5  cmp     [rdi+2Ch], bp
0x1800637f9  jz      short loc_180063862
0x1800637fb  mov     [rsp+48h+arg_10], rbp
0x180063800  movzx   ecx, word ptr [rdi+2Ch]; unsigned __int64
0x180063804  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180063809  mov     rbx, rax
0x18006380c  mov     [rsp+48h+arg_10], rax
0x180063811  movzx   r8d, word ptr [rdi+2Ch]; nNumberOfBytesToRead
0x180063816  mov     [rsp+48h+lpOverlapped], rbp; lpOverlapped
0x18006381b  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180063820  mov     rdx, rax; lpBuffer
0x180063823  mov     rcx, rsi; hFile
0x180063826  call    cs:__imp_ReadFile
0x18006382c  test    eax, eax
0x18006382e  jz      short loc_180063849
0x180063830  movzx   eax, word ptr [rdi+2Ch]
0x180063834  cmp     eax, [rsp+48h+NumberOfBytesRead]
0x180063838  jnz     short loc_180063849
0x18006383a  mov     [rdi+30h], rbx
0x18006383e  xor     ecx, ecx; Block
0x180063840  call    cs:__imp_free
0x180063846  nop
0x180063847  jmp     short loc_180063866
0x180063849  mov     rcx, rbx; Block
0x18006384c  call    cs:__imp_free
0x180063852  nop
0x180063853  xor     eax, eax
0x180063855  mov     rbx, [rsp+48h+arg_8]
0x18006385a  add     rsp, 30h
0x18006385e  pop     rdi
0x18006385f  pop     rsi
0x180063860  pop     rbp
0x180063861  retn
0x180063862  mov     [rdi+30h], rbp
0x180063866  mov     eax, 1
0x18006386b  jmp     short loc_180063855
```

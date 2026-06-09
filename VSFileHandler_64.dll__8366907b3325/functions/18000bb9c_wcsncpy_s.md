# wcsncpy_s

- ea: `0x18000bb9c`
- end: `0x18000bc80`
- name: `wcsncpy_s`
- size: `228`
- prototype: `errno_t __cdecl(wchar_t *Destination, rsize_t SizeInWords, const wchar_t *Source, rsize_t MaxCount)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001618`
- `0x180003d1c`
- `0x180004bb4`
- `0x180023e3c`

## callees

- `0x18000bb9c`
- `0x18000be9c`
- `0x18000bfbc`

## pseudocode

```c
errno_t __cdecl wcsncpy_s(wchar_t *Destination, rsize_t SizeInWords, const wchar_t *Source, rsize_t MaxCount)
{
  errno_t v4; // r10d
  int *v6; // rax
  errno_t v7; // ebx
  signed __int64 v9; // rbx
  wchar_t *v10; // rdx
  rsize_t v11; // r8
  rsize_t v12; // rdi
  wchar_t v13; // ax
  wchar_t v14; // ax

  v4 = 0;
  if ( MaxCount )
  {
    if ( !Destination )
      goto LABEL_4;
    goto LABEL_8;
  }
  if ( Destination )
  {
LABEL_8:
    if ( !SizeInWords )
      goto LABEL_4;
    if ( !MaxCount )
    {
      *Destination = 0;
      return v4;
    }
    if ( !Source )
    {
      *Destination = 0;
      goto LABEL_4;
    }
    v9 = (char *)Source - (char *)Destination;
    v10 = Destination;
    v11 = SizeInWords;
    v12 = MaxCount;
    if ( MaxCount == -1 )
    {
      do
      {
        v13 = *(wchar_t *)((char *)v10 + v9);
        *v10++ = v13;
        if ( !v13 )
          break;
        --v11;
      }
      while ( v11 );
    }
    else
    {
      do
      {
        v14 = *(wchar_t *)((char *)v10 + v9);
        *v10++ = v14;
        if ( !v14 )
          break;
        if ( !--v11 )
          break;
        --v12;
      }
      while ( v12 );
      if ( !v12 )
        *v10 = 0;
    }
    if ( !v11 )
    {
      if ( MaxCount == -1 )
      {
        Destination[SizeInWords - 1] = 0;
        return 80;
      }
      *Destination = 0;
      v6 = errno();
      v7 = 34;
      goto LABEL_5;
    }
    return v4;
  }
  if ( SizeInWords )
  {
LABEL_4:
    v6 = errno();
    v7 = 22;
LABEL_5:
    *v6 = v7;
    invalid_parameter_noinfo();
    return v7;
  }
  return v4;
}

```

## disassembly

```asm
0x18000bb9c  mov     [rsp+arg_0], rbx
0x18000bba1  push    rdi
0x18000bba2  sub     rsp, 20h
0x18000bba6  xor     r10d, r10d
0x18000bba9  mov     rbx, r8
0x18000bbac  mov     r11, rdx
0x18000bbaf  test    r9, r9
0x18000bbb2  jnz     short loc_18000BBE0
0x18000bbb4  test    rcx, rcx
0x18000bbb7  jnz     short loc_18000BBE5
0x18000bbb9  test    rdx, rdx
0x18000bbbc  jz      short loc_18000BBD2
0x18000bbbe  call    _errno
0x18000bbc3  mov     ebx, 16h
0x18000bbc8  mov     [rax], ebx
0x18000bbca  call    _invalid_parameter_noinfo
0x18000bbcf  mov     r10d, ebx
0x18000bbd2  mov     rbx, [rsp+28h+arg_0]
0x18000bbd7  mov     eax, r10d
0x18000bbda  add     rsp, 20h
0x18000bbde  pop     rdi
0x18000bbdf  retn
0x18000bbe0  test    rcx, rcx
0x18000bbe3  jz      short loc_18000BBBE
0x18000bbe5  test    r11, r11
0x18000bbe8  jz      short loc_18000BBBE
0x18000bbea  test    r9, r9
0x18000bbed  jnz     short loc_18000BBF5
0x18000bbef  mov     [rcx], r10w
0x18000bbf3  jmp     short loc_18000BBD2
0x18000bbf5  test    rbx, rbx
0x18000bbf8  jnz     short loc_18000BC00
0x18000bbfa  mov     [rcx], r10w
0x18000bbfe  jmp     short loc_18000BBBE
0x18000bc00  sub     rbx, rcx
0x18000bc03  mov     rdx, rcx
0x18000bc06  mov     r8, r11
0x18000bc09  mov     rdi, r9
0x18000bc0c  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000bc10  jnz     short loc_18000BC2A
0x18000bc12  movzx   eax, word ptr [rbx+rdx]
0x18000bc16  mov     [rdx], ax
0x18000bc19  lea     rdx, [rdx+2]
0x18000bc1d  test    ax, ax
0x18000bc20  jz      short loc_18000BC4F
0x18000bc22  sub     r8, 1
0x18000bc26  jnz     short loc_18000BC12
0x18000bc28  jmp     short loc_18000BC4F
0x18000bc2a  movzx   eax, word ptr [rbx+rdx]
0x18000bc2e  mov     [rdx], ax
0x18000bc31  lea     rdx, [rdx+2]
0x18000bc35  test    ax, ax
0x18000bc38  jz      short loc_18000BC46
0x18000bc3a  sub     r8, 1
0x18000bc3e  jz      short loc_18000BC46
0x18000bc40  sub     rdi, 1
0x18000bc44  jnz     short loc_18000BC2A
0x18000bc46  test    rdi, rdi
0x18000bc49  jnz     short loc_18000BC4F
0x18000bc4b  mov     [rdx], r10w
0x18000bc4f  test    r8, r8
0x18000bc52  jnz     loc_18000BBD2
0x18000bc58  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000bc5c  jnz     short loc_18000BC6D
0x18000bc5e  mov     [rcx+r11*2-2], r10w
0x18000bc64  lea     r10d, [r8+50h]
0x18000bc68  jmp     loc_18000BBD2
0x18000bc6d  mov     [rcx], r10w
0x18000bc71  call    _errno
0x18000bc76  mov     ebx, 22h ; '"'
0x18000bc7b  jmp     loc_18000BBC8
```

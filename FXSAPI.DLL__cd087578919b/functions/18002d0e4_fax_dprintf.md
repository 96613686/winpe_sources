# fax_dprintf

- ea: `0x18002d0e4`
- end: `0x18002d21d`
- name: `fax_dprintf`
- size: `313`
- prototype: `__int64(_QWORD, ...)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180009ba0`
- `0x1800251c0`
- `0x18002bab8`
- `0x18002bb9c`
- `0x18002d224`
- `0x18002d4cc`
- `0x18002d770`
- `0x18002d854`
- `0x18002d934`
- `0x180032688`

## callees

- `0x180001a48`
- `0x18002ce3c`
- `0x18002d0e4`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18002d17a`
- `msvcrt!_vsnwprintf` at `0x18002d17a`
- `KERNEL32!OutputDebugStringW` at `0x18002d1f0`
- `KERNEL32!OutputDebugStringW` at `0x18002d1f0`

## pseudocode

```c
void fax_dprintf(const wchar_t *a1, ...)
{
  const wchar_t *v1; // rbx
  int DebugLevel; // eax
  unsigned int v3; // eax
  unsigned __int64 v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  wchar_t Buffer[1024]; // [rsp+38h] [rbp-D0h] BYREF
  va_list Args; // [rsp+870h] [rbp+768h] BYREF

  va_start(Args, a1);
  v1 = a1;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( dword_180051734 )
  {
    DebugLevel = dword_18004E220;
  }
  else
  {
    DebugLevel = GetDebugLevel();
    v1 = a1;
    dword_18004E220 = DebugLevel;
    dword_180051734 = 1;
  }
  if ( DebugLevel > 0 )
  {
    v3 = _vsnwprintf(Buffer, 0x3FFu, v1, Args);
    if ( v3 < 0x400 )
    {
      if ( v3 == 1023 )
        Buffer[1023] = 0;
      v4 = -1;
      do
        ++v4;
      while ( Buffer[v4] );
      v5 = 1021;
      if ( v4 < 0x3FD )
        v5 = (unsigned int)v4;
      if ( Buffer[(unsigned int)(v5 - 1)] != 10 )
      {
        Buffer[v5] = 13;
        Buffer[(unsigned int)(v5 + 1)] = 10;
        v6 = 2LL * (unsigned int)(v5 + 2);
        if ( v6 >= 0x800 )
          _report_rangecheckfailure(v6, v5, 10);
        Buffer[(unsigned int)(v5 + 2)] = 0;
      }
      OutputDebugStringW(Buffer);
    }
  }
}

```

## disassembly

```asm
0x18002d0e4  mov     rax, rsp
0x18002d0e7  mov     [rax+8], rcx
0x18002d0eb  mov     [rax+10h], rdx
0x18002d0ef  mov     [rax+18h], r8
0x18002d0f3  mov     [rax+20h], r9
0x18002d0f7  push    rbp
0x18002d0f8  push    rbx
0x18002d0f9  push    rdi
0x18002d0fa  lea     rbp, [rax-758h]
0x18002d101  sub     rsp, 840h
0x18002d108  mov     rax, cs:__security_cookie
0x18002d10f  xor     rax, rsp
0x18002d112  mov     [rbp+750h+var_20], rax
0x18002d119  mov     rbx, rcx
0x18002d11c  xor     edx, edx; Val
0x18002d11e  lea     rcx, [rsp+850h+Buffer]; void *
0x18002d123  mov     r8d, 800h; Size
0x18002d129  call    memset_0
0x18002d12e  xor     edi, edi
0x18002d130  cmp     cs:dword_180051734, edi
0x18002d136  jnz     short loc_18002D156
0x18002d138  call    ?GetDebugLevel@@YAKXZ; GetDebugLevel(void)
0x18002d13d  mov     rbx, [rbp+750h+Format]
0x18002d144  mov     cs:dword_18004E220, eax
0x18002d14a  mov     cs:dword_180051734, 1
0x18002d154  jmp     short loc_18002D15C
0x18002d156  mov     eax, cs:dword_18004E220
0x18002d15c  test    eax, eax
0x18002d15e  jle     loc_18002D1FC
0x18002d164  mov     r8, rbx; Format
0x18002d167  lea     r9, [rbp+750h+Args]; Args
0x18002d16e  mov     ebx, 3FFh
0x18002d173  lea     rcx, [rsp+850h+Buffer]; Buffer
0x18002d178  mov     edx, ebx; BufferCount
0x18002d17a  call    cs:__imp__vsnwprintf
0x18002d181  nop     dword ptr [rax+rax+00h]
0x18002d186  test    eax, eax
0x18002d188  js      short loc_18002D1FC
0x18002d18a  cmp     eax, ebx
0x18002d18c  ja      short loc_18002D1FC
0x18002d18e  jnz     short loc_18002D197
0x18002d190  mov     [rbp+750h+var_22], di
0x18002d197  lea     rcx, [rsp+850h+Buffer]
0x18002d19c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d1a0  inc     rax
0x18002d1a3  cmp     [rcx+rax*2], di
0x18002d1a7  jnz     short loc_18002D1A0
0x18002d1a9  mov     edx, 3FDh
0x18002d1ae  mov     r8d, 0Ah
0x18002d1b4  cmp     rax, rdx
0x18002d1b7  cmovb   edx, eax
0x18002d1ba  lea     eax, [rdx-1]
0x18002d1bd  cmp     [rsp+rax*2+850h+Buffer], r8w
0x18002d1c3  jz      short loc_18002D1EB
0x18002d1c5  lea     ecx, [r8+3]
0x18002d1c9  mov     [rsp+rdx*2+850h+Buffer], cx
0x18002d1ce  lea     eax, [rdx+1]
0x18002d1d1  lea     ecx, [rdx+2]
0x18002d1d4  mov     [rsp+rax*2+850h+Buffer], r8w
0x18002d1da  add     rcx, rcx
0x18002d1dd  cmp     rcx, 800h
0x18002d1e4  jnb     short loc_18002D217
0x18002d1e6  mov     [rsp+rcx+850h+Buffer], di
0x18002d1eb  lea     rcx, [rsp+850h+Buffer]; lpOutputString
0x18002d1f0  call    cs:__imp_OutputDebugStringW
0x18002d1f7  nop     dword ptr [rax+rax+00h]
0x18002d1fc  mov     rcx, [rbp+750h+var_20]
0x18002d203  xor     rcx, rsp; StackCookie
0x18002d206  call    __security_check_cookie
0x18002d20b  add     rsp, 840h
0x18002d212  pop     rdi
0x18002d213  pop     rbx
0x18002d214  pop     rbp
0x18002d215  retn
0x18002d217  call    __report_rangecheckfailure
```

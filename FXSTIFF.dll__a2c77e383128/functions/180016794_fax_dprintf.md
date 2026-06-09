# fax_dprintf

- ea: `0x180016794`
- end: `0x1800168c0`
- name: `fax_dprintf`
- size: `300`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180009070`
- `0x18000ea18`
- `0x18000eafc`
- `0x18000ed20`
- `0x18000ee14`
- `0x18000efb0`
- `0x18000f0e4`
- `0x18000f1b4`
- `0x18000f290`

## callees

- `0x180001bc8`
- `0x180016520`
- `0x180016794`
- `0x180017bce`
- `0x180017c00`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001682a`
- `msvcrt!_vsnwprintf` at `0x18001682a`
- `KERNEL32!OutputDebugStringW` at `0x18001689a`
- `KERNEL32!OutputDebugStringW` at `0x18001689a`

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
  if ( dword_180070AC8 )
  {
    DebugLevel = dword_180070220;
  }
  else
  {
    DebugLevel = GetDebugLevel();
    v1 = a1;
    dword_180070220 = DebugLevel;
    dword_180070AC8 = 1;
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
0x180016794  mov     rax, rsp
0x180016797  mov     [rax+8], rcx
0x18001679b  mov     [rax+10h], rdx
0x18001679f  mov     [rax+18h], r8
0x1800167a3  mov     [rax+20h], r9
0x1800167a7  push    rbp
0x1800167a8  push    rbx
0x1800167a9  push    rdi
0x1800167aa  lea     rbp, [rax-758h]
0x1800167b1  sub     rsp, 840h
0x1800167b8  mov     rax, cs:__security_cookie
0x1800167bf  xor     rax, rsp
0x1800167c2  mov     [rbp+750h+var_20], rax
0x1800167c9  mov     rbx, rcx
0x1800167cc  xor     edx, edx; Val
0x1800167ce  lea     rcx, [rsp+850h+Buffer]; void *
0x1800167d3  mov     r8d, 800h; Size
0x1800167d9  call    memset_0
0x1800167de  xor     edi, edi
0x1800167e0  cmp     cs:dword_180070AC8, edi
0x1800167e6  jnz     short loc_180016806
0x1800167e8  call    ?GetDebugLevel@@YAKXZ; GetDebugLevel(void)
0x1800167ed  mov     rbx, [rbp+750h+Format]
0x1800167f4  mov     cs:dword_180070220, eax
0x1800167fa  mov     cs:dword_180070AC8, 1
0x180016804  jmp     short loc_18001680C
0x180016806  mov     eax, cs:dword_180070220
0x18001680c  test    eax, eax
0x18001680e  jle     loc_1800168A0
0x180016814  mov     r8, rbx; Format
0x180016817  lea     r9, [rbp+750h+Args]; Args
0x18001681e  mov     ebx, 3FFh
0x180016823  lea     rcx, [rsp+850h+Buffer]; Buffer
0x180016828  mov     edx, ebx; BufferCount
0x18001682a  call    cs:__imp__vsnwprintf
0x180016830  test    eax, eax
0x180016832  js      short loc_1800168A0
0x180016834  cmp     eax, ebx
0x180016836  ja      short loc_1800168A0
0x180016838  jnz     short loc_180016841
0x18001683a  mov     [rbp+750h+var_22], di
0x180016841  lea     rcx, [rsp+850h+Buffer]
0x180016846  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001684a  inc     rax
0x18001684d  cmp     [rcx+rax*2], di
0x180016851  jnz     short loc_18001684A
0x180016853  mov     edx, 3FDh
0x180016858  mov     r8d, 0Ah
0x18001685e  cmp     rax, rdx
0x180016861  cmovb   edx, eax
0x180016864  lea     eax, [rdx-1]
0x180016867  cmp     [rsp+rax*2+850h+Buffer], r8w
0x18001686d  jz      short loc_180016895
0x18001686f  lea     ecx, [r8+3]
0x180016873  mov     [rsp+rdx*2+850h+Buffer], cx
0x180016878  lea     eax, [rdx+1]
0x18001687b  lea     ecx, [rdx+2]
0x18001687e  mov     [rsp+rax*2+850h+Buffer], r8w
0x180016884  add     rcx, rcx
0x180016887  cmp     rcx, 800h
0x18001688e  jnb     short loc_1800168BA
0x180016890  mov     [rsp+rcx+850h+Buffer], di
0x180016895  lea     rcx, [rsp+850h+Buffer]; lpOutputString
0x18001689a  call    cs:__imp_OutputDebugStringW
0x1800168a0  mov     rcx, [rbp+750h+var_20]
0x1800168a7  xor     rcx, rsp; StackCookie
0x1800168aa  call    __security_check_cookie
0x1800168af  add     rsp, 840h
0x1800168b6  pop     rdi
0x1800168b7  pop     rbx
0x1800168b8  pop     rbp
0x1800168b9  retn
0x1800168ba  call    __report_rangecheckfailure
```

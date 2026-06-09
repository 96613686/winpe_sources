# fax_dprintf

- ea: `0x1800174d8`
- end: `0x180017611`
- name: `fax_dprintf`
- size: `313`
- prototype: `__int64(_QWORD, ...)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800094c0`
- `0x18000f128`
- `0x18000f20c`
- `0x18000f454`
- `0x18000f550`
- `0x18000f710`
- `0x18000f85c`
- `0x18000f940`
- `0x18000fa34`

## callees

- `0x180001bc8`
- `0x180017230`
- `0x1800174d8`
- `0x18001899e`
- `0x1800189d0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001756e`
- `msvcrt!_vsnwprintf` at `0x18001756e`
- `KERNEL32!OutputDebugStringW` at `0x1800175e4`
- `KERNEL32!OutputDebugStringW` at `0x1800175e4`

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
  if ( dword_180071AE8 )
  {
    DebugLevel = dword_180071220;
  }
  else
  {
    DebugLevel = GetDebugLevel();
    v1 = a1;
    dword_180071220 = DebugLevel;
    dword_180071AE8 = 1;
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
0x1800174d8  mov     rax, rsp
0x1800174db  mov     [rax+8], rcx
0x1800174df  mov     [rax+10h], rdx
0x1800174e3  mov     [rax+18h], r8
0x1800174e7  mov     [rax+20h], r9
0x1800174eb  push    rbp
0x1800174ec  push    rbx
0x1800174ed  push    rdi
0x1800174ee  lea     rbp, [rax-758h]
0x1800174f5  sub     rsp, 840h
0x1800174fc  mov     rax, cs:__security_cookie
0x180017503  xor     rax, rsp
0x180017506  mov     [rbp+750h+var_20], rax
0x18001750d  mov     rbx, rcx
0x180017510  xor     edx, edx; Val
0x180017512  lea     rcx, [rsp+850h+Buffer]; void *
0x180017517  mov     r8d, 800h; Size
0x18001751d  call    memset_0
0x180017522  xor     edi, edi
0x180017524  cmp     cs:dword_180071AE8, edi
0x18001752a  jnz     short loc_18001754A
0x18001752c  call    ?GetDebugLevel@@YAKXZ; GetDebugLevel(void)
0x180017531  mov     rbx, [rbp+750h+Format]
0x180017538  mov     cs:dword_180071220, eax
0x18001753e  mov     cs:dword_180071AE8, 1
0x180017548  jmp     short loc_180017550
0x18001754a  mov     eax, cs:dword_180071220
0x180017550  test    eax, eax
0x180017552  jle     loc_1800175F0
0x180017558  mov     r8, rbx; Format
0x18001755b  lea     r9, [rbp+750h+Args]; Args
0x180017562  mov     ebx, 3FFh
0x180017567  lea     rcx, [rsp+850h+Buffer]; Buffer
0x18001756c  mov     edx, ebx; BufferCount
0x18001756e  call    cs:__imp__vsnwprintf
0x180017575  nop     dword ptr [rax+rax+00h]
0x18001757a  test    eax, eax
0x18001757c  js      short loc_1800175F0
0x18001757e  cmp     eax, ebx
0x180017580  ja      short loc_1800175F0
0x180017582  jnz     short loc_18001758B
0x180017584  mov     [rbp+750h+var_22], di
0x18001758b  lea     rcx, [rsp+850h+Buffer]
0x180017590  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017594  inc     rax
0x180017597  cmp     [rcx+rax*2], di
0x18001759b  jnz     short loc_180017594
0x18001759d  mov     edx, 3FDh
0x1800175a2  mov     r8d, 0Ah
0x1800175a8  cmp     rax, rdx
0x1800175ab  cmovb   edx, eax
0x1800175ae  lea     eax, [rdx-1]
0x1800175b1  cmp     [rsp+rax*2+850h+Buffer], r8w
0x1800175b7  jz      short loc_1800175DF
0x1800175b9  lea     ecx, [r8+3]
0x1800175bd  mov     [rsp+rdx*2+850h+Buffer], cx
0x1800175c2  lea     eax, [rdx+1]
0x1800175c5  lea     ecx, [rdx+2]
0x1800175c8  mov     [rsp+rax*2+850h+Buffer], r8w
0x1800175ce  add     rcx, rcx
0x1800175d1  cmp     rcx, 800h
0x1800175d8  jnb     short loc_18001760B
0x1800175da  mov     [rsp+rcx+850h+Buffer], di
0x1800175df  lea     rcx, [rsp+850h+Buffer]; lpOutputString
0x1800175e4  call    cs:__imp_OutputDebugStringW
0x1800175eb  nop     dword ptr [rax+rax+00h]
0x1800175f0  mov     rcx, [rbp+750h+var_20]
0x1800175f7  xor     rcx, rsp; StackCookie
0x1800175fa  call    __security_check_cookie
0x1800175ff  add     rsp, 840h
0x180017606  pop     rdi
0x180017607  pop     rbx
0x180017608  pop     rbp
0x180017609  retn
0x18001760b  call    __report_rangecheckfailure
```

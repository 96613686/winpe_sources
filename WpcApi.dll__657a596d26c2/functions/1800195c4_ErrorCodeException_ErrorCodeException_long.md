# ErrorCodeException::ErrorCodeException(long)

- ea: `0x1800195c4`
- end: `0x18001966e`
- name: `??0ErrorCodeException@@QEAA@J@Z`
- size: `170`
- prototype: `ErrorCodeException *__fastcall(ErrorCodeException *__hidden this, int)`
- caller_count: `57`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024d0`
- `0x180002530`
- `0x180002590`
- `0x180002620`
- `0x180002750`
- `0x180006960`
- `0x18000a2c0`
- `0x18000a790`
- `0x18000bf74`
- `0x18000c164`
- `0x18000c414`
- `0x18000cc18`
- `0x1800184e8`
- `0x180019b38`
- `0x18001b19c`
- `0x18001bb28`
- `0x18001c724`
- `0x18001ca00`
- `0x18001cad0`
- `0x1800210e8`
- `0x180021304`
- `0x180021540`
- `0x1800216cc`
- `0x1800220a4`
- `0x1800221cc`
- `0x1800226e8`
- `0x180022a84`
- `0x180022e90`
- `0x1800238ec`
- `0x180023b80`
- `0x1800243b0`
- `0x180024640`
- `0x180025374`
- `0x1800256c0`
- `0x180025b50`
- `0x180025bf0`
- `0x1800260c0`
- `0x180026404`
- `0x1800264e0`
- `0x180026670`
- `0x180026880`
- `0x180026f90`
- `0x180027070`
- `0x180027120`
- `0x1800271f0`
- `0x1800272c0`
- `0x1800273a4`
- `0x18002781c`
- `0x180027878`
- `0x180027b3c`

## callees

- `0x18000b29c`
- `0x1800195c4`

## pseudocode

```c
ErrorCodeException *__fastcall ErrorCodeException::ErrorCodeException(ErrorCodeException *this, int a2)
{
  int v4; // eax

  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &ErrorCodeException::`vftable';
  if ( a2 >= 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      WPP_9ff42e10ab693b57d922b1095aea5eb2_Traceguids,
      (unsigned int)a2);
  }
  *((_BYTE *)this + 28) = 0;
  v4 = a2;
  if ( a2 >= 0 )
    v4 = -2147418113;
  *((_DWORD *)this + 6) = v4;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      11,
      WPP_9ff42e10ab693b57d922b1095aea5eb2_Traceguids,
      (unsigned int)a2);
  return this;
}

```

## disassembly

```asm
0x1800195c4  mov     [rsp+arg_0], rbx
0x1800195c9  mov     [rsp+arg_8], rsi
0x1800195ce  push    rdi
0x1800195cf  sub     rsp, 20h
0x1800195d3  lea     rax, ??_7ErrorCodeException@@6B@; const ErrorCodeException::`vftable'
0x1800195da  xorps   xmm0, xmm0
0x1800195dd  lea     rsi, WPP_GLOBAL_Control
0x1800195e4  mov     edi, edx
0x1800195e6  mov     rbx, rcx
0x1800195e9  movups  xmmword ptr [rcx+8], xmm0
0x1800195ed  mov     [rcx], rax
0x1800195f0  test    edx, edx
0x1800195f2  js      short loc_18001961E
0x1800195f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195fb  cmp     rcx, rsi
0x1800195fe  jz      short loc_18001961E
0x180019600  test    byte ptr [rcx+1Ch], 1
0x180019604  jz      short loc_18001961E
0x180019606  mov     rcx, [rcx+10h]
0x18001960a  lea     r8, WPP_9ff42e10ab693b57d922b1095aea5eb2_Traceguids
0x180019611  mov     edx, 0Ah
0x180019616  mov     r9d, edi
0x180019619  call    WPP_SF_d
0x18001961e  test    edi, edi
0x180019620  mov     byte ptr [rbx+1Ch], 0
0x180019624  mov     eax, edi
0x180019626  mov     ecx, 8000FFFFh
0x18001962b  cmovns  eax, ecx
0x18001962e  mov     [rbx+18h], eax
0x180019631  mov     rcx, cs:WPP_GLOBAL_Control
0x180019638  cmp     rcx, rsi
0x18001963b  jz      short loc_18001965B
0x18001963d  test    byte ptr [rcx+1Ch], 1
0x180019641  jz      short loc_18001965B
0x180019643  mov     rcx, [rcx+10h]
0x180019647  lea     r8, WPP_9ff42e10ab693b57d922b1095aea5eb2_Traceguids
0x18001964e  mov     edx, 0Bh
0x180019653  mov     r9d, edi
0x180019656  call    WPP_SF_d
0x18001965b  mov     rsi, [rsp+28h+arg_8]
0x180019660  mov     rax, rbx
0x180019663  mov     rbx, [rsp+28h+arg_0]
0x180019668  add     rsp, 20h
0x18001966c  pop     rdi
0x18001966d  retn
```

# PCLmWriter::IStreamByteStream::GetLength(void)

- ea: `0x18001a3a0`
- end: `0x18001a42c`
- name: `?GetLength@IStreamByteStream@PCLmWriter@@UEBAIXZ`
- size: `140`
- prototype: `unsigned int __fastcall(PCLmWriter::IStreamByteStream *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x180010050`
- `0x180012cc0`
- `0x18001a3a0`
- `0x18001f010`

## pseudocode

```c
unsigned __int64 __fastcall PCLmWriter::IStreamByteStream::GetLength(PCLmWriter::IStreamByteStream *this)
{
  unsigned int v2; // eax
  unsigned __int64 result; // rax
  unsigned int v4[4]; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v5; // [rsp+30h] [rbp-58h]

  memset_0(v4, 0, 0x50u);
  v2 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64))(**((_QWORD **)this + 9) + 96LL))(
         *((_QWORD *)this + 9),
         v4,
         1);
  PrintCore::ThrowIfError(
    (PrintCore *)v2,
    (int)"Failure getting stream length.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\istreambytestream.cpp",
    (const char *)0x2D,
    v4[0]);
  result = v5;
  if ( v5 > 0xFFFFFFFF )
    PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow();
  return result;
}

```

## disassembly

```asm
0x18001a3a0  push    rbx
0x18001a3a2  sub     rsp, 80h
0x18001a3a9  mov     rax, cs:__security_cookie
0x18001a3b0  xor     rax, rsp
0x18001a3b3  mov     [rsp+88h+var_18], rax
0x18001a3b8  xor     edx, edx; Val
0x18001a3ba  mov     rbx, rcx
0x18001a3bd  lea     rcx, [rsp+88h+var_68]; void *
0x18001a3c2  lea     r8d, [rdx+50h]; Size
0x18001a3c6  call    memset_0
0x18001a3cb  mov     rcx, [rbx+48h]
0x18001a3cf  lea     rdx, [rsp+88h+var_68]
0x18001a3d4  mov     r8d, 1
0x18001a3da  mov     rax, [rcx]
0x18001a3dd  mov     rax, [rax+60h]
0x18001a3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3e6  mov     r9d, 2Dh ; '-'; char *
0x18001a3ec  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001a3f3  lea     rdx, aFailureGetting; "Failure getting stream length."
0x18001a3fa  mov     ecx, eax; this
0x18001a3fc  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18001a401  mov     rax, [rsp+88h+var_58]
0x18001a406  mov     ecx, 0FFFFFFFFh
0x18001a40b  cmp     rax, rcx
0x18001a40e  jbe     short loc_18001A416
0x18001a410  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@PCLmWriter@@@PCLmWriter@@SAXXZ; PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow(void)
0x18001a416  mov     rcx, [rsp+88h+var_18]
0x18001a41b  xor     rcx, rsp; StackCookie
0x18001a41e  call    __security_check_cookie
0x18001a423  add     rsp, 80h
0x18001a42a  pop     rbx
0x18001a42b  retn
```

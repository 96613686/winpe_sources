# XpsToTiffConverter::XpsToTiffConverter::CopyTempFileToOutputStream(void)

- ea: `0x180009f94`
- end: `0x18000a138`
- name: `?CopyTempFileToOutputStream@XpsToTiffConverter@1@AEAAXXZ`
- size: `420`
- prototype: `void __fastcall(XpsToTiffConverter::XpsToTiffConverter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a170`

## callees

- `0x180009494`
- `0x180009d6c`
- `0x180009f94`
- `0x18000b0ac`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XpsToTiffConverter::XpsToTiffConverter::CopyTempFileToOutputStream(
        XpsToTiffConverter::XpsToTiffConverter *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // [rsp+20h] [rbp-30h]
  _QWORD v8[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  unsigned int v10; // [rsp+60h] [rbp+10h] BYREF
  int v11; // [rsp+68h] [rbp+18h] BYREF
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF

  v12 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 10) + 40LL))(
         *((_QWORD *)this + 10),
         0,
         1,
         &v12);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
      (const char *)(unsigned int)v2,
      v7);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 10) + 40LL))(
         *((_QWORD *)this + 10),
         0,
         0,
         0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
      (const char *)(unsigned int)v3,
      v7);
  std::vector<unsigned char>::vector<unsigned char>(v8, 0x100000);
  v10 = 0;
  do
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned int *))(**((_QWORD **)this + 10) + 24LL))(
           *((_QWORD *)this + 10),
           v8[0],
           0x100000,
           &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v4,
        v7);
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 9) + 32LL))(
           *((_QWORD *)this + 9),
           v8[0],
           v10,
           &v11);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)(unsigned int)v5,
        v7);
    if ( v11 != v10 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
        (const char *)0x8000FFFFLL,
        v7);
  }
  while ( v10 == 0x100000 );
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 10) + 40LL))(
         *((_QWORD *)this + 10),
         v12,
         0,
         0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpstotiffconverter.cpp",
      (const char *)(unsigned int)v6,
      v7);
  std::vector<unsigned char>::~vector<unsigned char>(v8);
}

```

## disassembly

```asm
0x180009f94  mov     [rsp-8+arg_18], rbx
0x180009f99  push    rbp
0x180009f9a  mov     rbp, rsp
0x180009f9d  sub     rsp, 50h
0x180009fa1  mov     rbx, rcx
0x180009fa4  mov     [rbp+arg_10], 0
0x180009fac  mov     rcx, [rcx+50h]
0x180009fb0  xor     edx, edx
0x180009fb2  mov     rax, [rcx]
0x180009fb5  lea     r9, [rbp+arg_10]
0x180009fb9  lea     r8d, [rdx+1]
0x180009fbd  mov     rax, [rax+28h]
0x180009fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc6  mov     rcx, [rbp+8]; this
0x180009fca  test    eax, eax
0x180009fcc  js      loc_18000A0DE
0x180009fd2  mov     rcx, [rbx+50h]
0x180009fd6  xor     edx, edx
0x180009fd8  mov     rax, [rcx]
0x180009fdb  xor     r9d, r9d
0x180009fde  xor     r8d, r8d
0x180009fe1  mov     rax, [rax+28h]
0x180009fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fea  mov     rcx, [rbp+8]; this
0x180009fee  test    eax, eax
0x180009ff0  js      loc_18000A0F3
0x180009ff6  mov     edx, 100000h
0x180009ffb  lea     rcx, [rbp+var_20]
0x180009fff  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000a004  nop
0x18000a005  mov     [rbp+arg_0], 0
0x18000a00c  mov     rcx, [rbx+50h]
0x18000a010  mov     rax, [rcx]
0x18000a013  lea     r9, [rbp+arg_0]
0x18000a017  mov     r8d, 100000h
0x18000a01d  mov     rdx, [rbp+var_20]
0x18000a021  mov     rax, [rax+18h]
0x18000a025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a02a  mov     rcx, [rbp+8]; this
0x18000a02e  test    eax, eax
0x18000a030  js      loc_18000A0C9
0x18000a036  mov     [rbp+arg_8], 0
0x18000a03d  mov     rcx, [rbx+48h]
0x18000a041  mov     rax, [rcx]
0x18000a044  lea     r9, [rbp+arg_8]
0x18000a048  mov     r8d, [rbp+arg_0]
0x18000a04c  mov     rdx, [rbp+var_20]
0x18000a050  mov     rax, [rax+20h]
0x18000a054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a059  mov     rcx, [rbp+8]; this
0x18000a05d  test    eax, eax
0x18000a05f  js      short loc_18000A0B4
0x18000a061  mov     ecx, [rbp+arg_0]
0x18000a064  cmp     [rbp+arg_8], ecx
0x18000a067  setnz   al
0x18000a06a  mov     r10, [rbp+8]
0x18000a06e  test    al, al
0x18000a070  jnz     loc_18000A11D
0x18000a076  cmp     ecx, 100000h
0x18000a07c  jz      short loc_18000A00C
0x18000a07e  mov     rcx, [rbx+50h]
0x18000a082  mov     rax, [rcx]
0x18000a085  xor     r9d, r9d
0x18000a088  xor     r8d, r8d
0x18000a08b  mov     rdx, [rbp+arg_10]
0x18000a08f  mov     rax, [rax+28h]
0x18000a093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a098  mov     rcx, [rbp+8]; this
0x18000a09c  test    eax, eax
0x18000a09e  js      short loc_18000A108
0x18000a0a0  lea     rcx, [rbp+var_20]
0x18000a0a4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000a0a9  mov     rbx, [rsp+50h+arg_18]
0x18000a0ae  add     rsp, 50h
0x18000a0b2  pop     rbp
0x18000a0b3  retn
0x18000a0b4  mov     r9d, eax; char *
0x18000a0b7  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a0be  mov     edx, 6Fh ; 'o'; void *
0x18000a0c3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a0c9  mov     r9d, eax; char *
0x18000a0cc  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a0d3  mov     edx, 6Dh ; 'm'; void *
0x18000a0d8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a0de  mov     r9d, eax; char *
0x18000a0e1  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a0e8  mov     edx, 67h ; 'g'; void *
0x18000a0ed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a0f3  mov     r9d, eax; char *
0x18000a0f6  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a0fd  mov     edx, 68h ; 'h'; void *
0x18000a102  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a108  mov     r9d, eax; char *
0x18000a10b  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a112  mov     edx, 73h ; 's'; void *
0x18000a117  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a11d  mov     r9d, 8000FFFFh; char *
0x18000a123  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a12a  mov     edx, 70h ; 'p'; void *
0x18000a12f  mov     rcx, r10; this
0x18000a132  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

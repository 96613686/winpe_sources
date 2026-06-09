# MvPackKeys(std::vector<uchar,std::allocator<uchar>> &,IMVKey * *,ulong)

- ea: `0x18000fadc`
- end: `0x18000fc89`
- name: `?MvPackKeys@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAUIMVKey@@K@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e184`

## callees

- `0x18000a2e4`
- `0x18000fadc`
- `0x18000fd14`
- `0x180012010`

## string_xrefs

- `0x18000fc46`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x18000fc5c`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`
- `0x18000fc77`: `onecoreuap\admin\prov\multivariant\common\src\mvprovisiondatahelper.cpp`

## pseudocode

```c
__int64 __fastcall MvPackKeys(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 i; // r15
  __int64 v8; // rcx
  int v9; // eax
  __int16 *j; // r14
  __int16 v11; // di
  int v12; // eax
  __int16 *k; // r14
  __int16 v14; // di
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  char v17; // [rsp+70h] [rbp+50h] BYREF
  __int16 *v18; // [rsp+78h] [rbp+58h] BYREF

  if ( a3 > 0xFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
      (const char *)0x80070216LL,
      savedregs);
  v17 = a3;
  std::vector<unsigned char>::push_back(a1, &v17);
  v17 = BYTE1(a3);
  result = std::vector<unsigned char>::push_back(a1, &v17);
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    v8 = *(_QWORD *)(a2 + 8 * i);
    v18 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int16 **))(*(_QWORD *)v8 + 40LL))(v8, &v18);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B4,
        (int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
        (const char *)(unsigned int)v9,
        savedregs);
    for ( j = v18; ; ++j )
    {
      v11 = *j;
      if ( !*j )
        break;
      v17 = *j;
      std::vector<unsigned char>::push_back(a1, &v17);
      v17 = HIBYTE(v11);
      std::vector<unsigned char>::push_back(a1, &v17);
    }
    v17 = 61;
    std::vector<unsigned char>::push_back(a1, &v17);
    v17 = 0;
    std::vector<unsigned char>::push_back(a1, &v17);
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int16 **))(**(_QWORD **)(a2 + 8 * i) + 48LL))(
            *(_QWORD *)(a2 + 8 * i),
            &v18);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1BE,
        (int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvprovisiondatahelper.cpp",
        (const char *)(unsigned int)v12,
        savedregs);
    for ( k = v18; ; ++k )
    {
      v14 = *k;
      if ( !*k )
        break;
      v17 = *k;
      std::vector<unsigned char>::push_back(a1, &v17);
      v17 = HIBYTE(v14);
      std::vector<unsigned char>::push_back(a1, &v17);
    }
    v17 = 0;
    std::vector<unsigned char>::push_back(a1, &v17);
    v17 = 0;
    result = std::vector<unsigned char>::push_back(a1, &v17);
  }
  return result;
}

```

## disassembly

```asm
0x18000fadc  mov     [rsp-38h+arg_0], rbx
0x18000fae1  push    rbp
0x18000fae2  push    rsi
0x18000fae3  push    rdi
0x18000fae4  push    r12
0x18000fae6  push    r13
0x18000fae8  push    r14
0x18000faea  push    r15; int
0x18000faec  mov     rbp, rsp
0x18000faef  sub     rsp, 20h
0x18000faf3  mov     esi, r8d
0x18000faf6  mov     r12, rdx
0x18000faf9  mov     rbx, rcx
0x18000fafc  cmp     r8d, 0FFFFh
0x18000fb03  ja      loc_18000FC58
0x18000fb09  lea     rdx, [rbp+arg_10]
0x18000fb0d  mov     [rbp+arg_10], sil
0x18000fb11  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fb16  movzx   eax, si
0x18000fb19  lea     rdx, [rbp+arg_10]
0x18000fb1d  shr     ax, 8
0x18000fb21  mov     rcx, rbx
0x18000fb24  mov     [rbp+arg_10], al
0x18000fb27  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fb2c  xor     r15d, r15d
0x18000fb2f  test    esi, esi
0x18000fb31  jz      loc_18000FC2E
0x18000fb37  mov     rcx, [r12+r15*8]
0x18000fb3b  lea     rdx, [rbp+arg_18]
0x18000fb3f  mov     [rbp+arg_18], 0
0x18000fb47  mov     rax, [rcx]
0x18000fb4a  mov     rax, [rax+28h]
0x18000fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb53  mov     rcx, [rbp+38h]; this
0x18000fb57  test    eax, eax
0x18000fb59  js      loc_18000FC43
0x18000fb5f  mov     r14, [rbp+arg_18]
0x18000fb63  jmp     short loc_18000FB86
0x18000fb65  mov     [rbp+arg_10], dil
0x18000fb69  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fb6e  shr     di, 8
0x18000fb72  lea     rdx, [rbp+arg_10]
0x18000fb76  mov     rcx, rbx
0x18000fb79  mov     [rbp+arg_10], dil
0x18000fb7d  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fb82  lea     r14, [r14+2]
0x18000fb86  movzx   edi, word ptr [r14]
0x18000fb8a  lea     rdx, [rbp+arg_10]
0x18000fb8e  xor     eax, eax
0x18000fb90  mov     rcx, rbx
0x18000fb93  cmp     ax, di
0x18000fb96  jnz     short loc_18000FB65
0x18000fb98  mov     [rbp+arg_10], 3Dh ; '='
0x18000fb9c  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fba1  lea     rdx, [rbp+arg_10]
0x18000fba5  mov     [rbp+arg_10], 0
0x18000fba9  mov     rcx, rbx
0x18000fbac  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fbb1  mov     rcx, [r12+r15*8]
0x18000fbb5  lea     rdx, [rbp+arg_18]
0x18000fbb9  mov     rax, [rcx]
0x18000fbbc  mov     rax, [rax+30h]
0x18000fbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc5  mov     rcx, [rbp+38h]; this
0x18000fbc9  test    eax, eax
0x18000fbcb  js      loc_18000FC74
0x18000fbd1  mov     r14, [rbp+arg_18]
0x18000fbd5  jmp     short loc_18000FBF8
0x18000fbd7  mov     [rbp+arg_10], dil
0x18000fbdb  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fbe0  shr     di, 8
0x18000fbe4  lea     rdx, [rbp+arg_10]
0x18000fbe8  mov     rcx, rbx
0x18000fbeb  mov     [rbp+arg_10], dil
0x18000fbef  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fbf4  lea     r14, [r14+2]
0x18000fbf8  movzx   edi, word ptr [r14]
0x18000fbfc  lea     rdx, [rbp+arg_10]
0x18000fc00  xor     eax, eax
0x18000fc02  mov     rcx, rbx
0x18000fc05  cmp     ax, di
0x18000fc08  jnz     short loc_18000FBD7
0x18000fc0a  mov     [rbp+arg_10], al
0x18000fc0d  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fc12  lea     rdx, [rbp+arg_10]
0x18000fc16  mov     [rbp+arg_10], 0
0x18000fc1a  mov     rcx, rbx
0x18000fc1d  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18000fc22  inc     r15d
0x18000fc25  cmp     r15d, esi
0x18000fc28  jb      loc_18000FB37
0x18000fc2e  mov     rbx, [rsp+20h+arg_0]
0x18000fc33  add     rsp, 20h
0x18000fc37  pop     r15
0x18000fc39  pop     r14
0x18000fc3b  pop     r13
0x18000fc3d  pop     r12
0x18000fc3f  pop     rdi
0x18000fc40  pop     rsi
0x18000fc41  pop     rbp
0x18000fc42  retn
0x18000fc43  mov     r9d, eax; char *
0x18000fc46  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000fc4d  mov     edx, 1B4h; void *
0x18000fc52  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fc58  mov     rcx, [rbp+38h]; this
0x18000fc5c  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000fc63  mov     r9d, 80070216h; char *
0x18000fc69  mov     edx, 1ADh; void *
0x18000fc6e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000fc74  mov     r9d, eax; char *
0x18000fc77  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000fc7e  mov     edx, 1BEh; void *
0x18000fc83  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

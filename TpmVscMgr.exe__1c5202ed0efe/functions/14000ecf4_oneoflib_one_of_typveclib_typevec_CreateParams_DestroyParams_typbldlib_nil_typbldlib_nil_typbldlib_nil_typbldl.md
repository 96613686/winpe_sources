# oneoflib::one_of<typveclib::typevec<CreateParams,DestroyParams,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil>,typbldlib::metavalue<0>,typbldlib::metavalue<2>,typbldlib::metavalue<2>>::reset<CreateParams>(CreateParams &&)

- ea: `0x14000ecf4`
- end: `0x14000eef2`
- name: `??$reset@VCreateParams@@@?$one_of@U?$typevec@VCreateParams@@VDestroyParams@@Unil@typbldlib@@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@U34@@typveclib@@U?$metavalue@$0A@@typbldlib@@U?$metavalue@$01@4@U54@@oneoflib@@QEAAX$$QEAVCreateParams@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f54c`

## callees

- `0x140008530`
- `0x14000dab8`
- `0x14000dbfc`
- `0x14000ecf4`

## pseudocode

```c
__int64 __fastcall oneoflib::one_of<typveclib::typevec<CreateParams,DestroyParams,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil,typbldlib::nil>,typbldlib::metavalue<0>,typbldlib::metavalue<2>,typbldlib::metavalue<2>>::reset<CreateParams>(
        __int64 a1,
        __int64 a2)
{
  _DWORD *v2; // rsi
  _OWORD *v5; // rdx
  _OWORD *v6; // rcx
  _OWORD *v7; // rdx
  _OWORD *v8; // rcx
  _OWORD *v9; // rdx
  _OWORD *v10; // rcx
  __int64 *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 result; // rax

  v2 = (_DWORD *)(a1 + 240);
  if ( *(_DWORD *)(a1 + 240) )
  {
    if ( *v2 == 1 && *(_BYTE *)(a1 + 32) )
    {
      *(_BYTE *)(a1 + 32) = 0;
      ((void (*)(void))std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>)();
    }
  }
  else
  {
    CreateParams::~CreateParams((CreateParams *)a1);
  }
  *v2 = 2;
  *(_BYTE *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = a1;
  if ( *(_BYTE *)(a2 + 32) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)a2;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    if ( *(_BYTE *)(a2 + 32) )
    {
      *(_BYTE *)(a2 + 32) = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(a2);
    }
  }
  v5 = (_OWORD *)(a1 + 48);
  v6 = (_OWORD *)(a2 + 48);
  *(_BYTE *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = a1 + 48;
  if ( *(_BYTE *)(a2 + 80) )
  {
    *v5 = 0;
    *(_QWORD *)(a1 + 64) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *v5 = *v6;
    *(_OWORD *)(a1 + 64) = *(_OWORD *)(a2 + 64);
    *(_QWORD *)(a2 + 64) = 0;
    *(_QWORD *)(a2 + 72) = 7;
    *(_WORD *)v6 = 0;
    *(_BYTE *)(a1 + 80) = 1;
    if ( *(_BYTE *)(a2 + 80) )
    {
      *(_BYTE *)(a2 + 80) = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v6);
    }
  }
  v7 = (_OWORD *)(a1 + 96);
  v8 = (_OWORD *)(a2 + 96);
  *(_BYTE *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = a1 + 96;
  if ( *(_BYTE *)(a2 + 128) )
  {
    *v7 = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_QWORD *)(a1 + 120) = 0;
    *v7 = *v8;
    *(_OWORD *)(a1 + 112) = *(_OWORD *)(a2 + 112);
    *(_QWORD *)(a2 + 112) = 0;
    *(_QWORD *)(a2 + 120) = 7;
    *(_WORD *)v8 = 0;
    *(_BYTE *)(a1 + 128) = 1;
    if ( *(_BYTE *)(a2 + 128) )
    {
      *(_BYTE *)(a2 + 128) = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v8);
    }
  }
  v9 = (_OWORD *)(a1 + 144);
  v10 = (_OWORD *)(a2 + 144);
  *(_BYTE *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = a1 + 144;
  if ( *(_BYTE *)(a2 + 176) )
  {
    *v9 = 0;
    *(_QWORD *)(a1 + 160) = 0;
    *(_QWORD *)(a1 + 168) = 0;
    *v9 = *v10;
    *(_OWORD *)(a1 + 160) = *(_OWORD *)(a2 + 160);
    *(_QWORD *)(a2 + 160) = 0;
    *(_QWORD *)(a2 + 168) = 7;
    *(_WORD *)v10 = 0;
    *(_BYTE *)(a1 + 176) = 1;
    if ( *(_BYTE *)(a2 + 176) )
    {
      *(_BYTE *)(a2 + 176) = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v10);
    }
  }
  v11 = (__int64 *)(a2 + 192);
  *(_BYTE *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = a1 + 192;
  if ( *(_BYTE *)(a2 + 216) )
  {
    v12 = *(_QWORD *)(a2 + 208);
    v13 = *(_QWORD *)(a2 + 200);
    v14 = *v11;
    *(_QWORD *)(a2 + 208) = 0;
    *(_QWORD *)(a2 + 200) = 0;
    *v11 = 0;
    *(_QWORD *)(a1 + 192) = v14;
    *(_QWORD *)(a1 + 200) = v13;
    *(_QWORD *)(a1 + 208) = v12;
    *(_BYTE *)(a1 + 216) = 1;
    if ( *(_BYTE *)(a2 + 216) )
    {
      *(_BYTE *)(a2 + 216) = 0;
      std::vector<unsigned char>::~vector<unsigned char>(v11);
    }
  }
  *(_BYTE *)(a1 + 232) = *(_BYTE *)(a2 + 232);
  result = *(unsigned int *)(a2 + 236);
  *(_DWORD *)(a1 + 236) = result;
  *v2 = 0;
  return result;
}

```

## disassembly

```asm
0x14000ecf4  push    rbx
0x14000ecf6  push    rbp
0x14000ecf7  push    rsi
0x14000ecf8  push    rdi
0x14000ecf9  push    r14
0x14000ecfb  sub     rsp, 20h
0x14000ecff  lea     rsi, [rcx+0F0h]
0x14000ed06  xor     ebp, ebp
0x14000ed08  mov     rdi, rdx
0x14000ed0b  mov     rbx, rcx
0x14000ed0e  cmp     [rsi], ebp
0x14000ed10  jnz     short loc_14000ED19
0x14000ed12  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000ed17  jmp     short loc_14000ED2D
0x14000ed19  cmp     dword ptr [rsi], 1
0x14000ed1c  jnz     short loc_14000ED2D
0x14000ed1e  cmp     [rcx+20h], bpl
0x14000ed22  jz      short loc_14000ED2D
0x14000ed24  mov     [rcx+20h], bpl
0x14000ed28  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000ed2d  mov     eax, 2
0x14000ed32  mov     rcx, rsi
0x14000ed35  mov     [rcx], eax
0x14000ed37  lea     r14d, [rax+5]
0x14000ed3b  mov     [rbx+20h], bpl
0x14000ed3f  mov     [rbx+28h], rbx
0x14000ed43  cmp     [rdi+20h], bpl
0x14000ed47  jz      short loc_14000ED86
0x14000ed49  xorps   xmm0, xmm0
0x14000ed4c  movups  xmmword ptr [rbx], xmm0
0x14000ed4f  mov     [rbx+10h], rbp
0x14000ed53  mov     [rbx+18h], rbp
0x14000ed57  movups  xmm0, xmmword ptr [rdi]
0x14000ed5a  movups  xmmword ptr [rbx], xmm0
0x14000ed5d  movups  xmm1, xmmword ptr [rdi+10h]
0x14000ed61  movups  xmmword ptr [rbx+10h], xmm1
0x14000ed65  mov     [rdi+10h], rbp
0x14000ed69  mov     [rdi+18h], r14
0x14000ed6d  mov     [rdi], bp
0x14000ed70  mov     byte ptr [rbx+20h], 1
0x14000ed74  cmp     [rdi+20h], bpl
0x14000ed78  jz      short loc_14000ED86
0x14000ed7a  mov     rcx, rdi
0x14000ed7d  mov     [rdi+20h], bpl
0x14000ed81  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000ed86  lea     rdx, [rbx+30h]
0x14000ed8a  lea     rcx, [rdi+30h]
0x14000ed8e  mov     [rdx+20h], bpl
0x14000ed92  mov     [rdx+28h], rdx
0x14000ed96  cmp     [rcx+20h], bpl
0x14000ed9a  jz      short loc_14000EDD6
0x14000ed9c  xorps   xmm0, xmm0
0x14000ed9f  movups  xmmword ptr [rdx], xmm0
0x14000eda2  mov     [rdx+10h], rbp
0x14000eda6  mov     [rdx+18h], rbp
0x14000edaa  movups  xmm0, xmmword ptr [rcx]
0x14000edad  movups  xmmword ptr [rdx], xmm0
0x14000edb0  movups  xmm1, xmmword ptr [rcx+10h]
0x14000edb4  movups  xmmword ptr [rdx+10h], xmm1
0x14000edb8  mov     [rcx+10h], rbp
0x14000edbc  mov     [rcx+18h], r14
0x14000edc0  mov     [rcx], bp
0x14000edc3  mov     byte ptr [rdx+20h], 1
0x14000edc7  cmp     [rcx+20h], bpl
0x14000edcb  jz      short loc_14000EDD6
0x14000edcd  mov     [rcx+20h], bpl
0x14000edd1  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000edd6  lea     rdx, [rbx+60h]
0x14000edda  lea     rcx, [rdi+60h]
0x14000edde  mov     [rdx+20h], bpl
0x14000ede2  mov     [rdx+28h], rdx
0x14000ede6  cmp     [rcx+20h], bpl
0x14000edea  jz      short loc_14000EE26
0x14000edec  xorps   xmm0, xmm0
0x14000edef  movups  xmmword ptr [rdx], xmm0
0x14000edf2  mov     [rdx+10h], rbp
0x14000edf6  mov     [rdx+18h], rbp
0x14000edfa  movups  xmm0, xmmword ptr [rcx]
0x14000edfd  movups  xmmword ptr [rdx], xmm0
0x14000ee00  movups  xmm1, xmmword ptr [rcx+10h]
0x14000ee04  movups  xmmword ptr [rdx+10h], xmm1
0x14000ee08  mov     [rcx+10h], rbp
0x14000ee0c  mov     [rcx+18h], r14
0x14000ee10  mov     [rcx], bp
0x14000ee13  mov     byte ptr [rdx+20h], 1
0x14000ee17  cmp     [rcx+20h], bpl
0x14000ee1b  jz      short loc_14000EE26
0x14000ee1d  mov     [rcx+20h], bpl
0x14000ee21  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000ee26  lea     rdx, [rbx+90h]
0x14000ee2d  lea     rcx, [rdi+90h]
0x14000ee34  mov     [rdx+20h], bpl
0x14000ee38  mov     [rdx+28h], rdx
0x14000ee3c  cmp     [rcx+20h], bpl
0x14000ee40  jz      short loc_14000EE7C
0x14000ee42  xorps   xmm0, xmm0
0x14000ee45  movups  xmmword ptr [rdx], xmm0
0x14000ee48  mov     [rdx+10h], rbp
0x14000ee4c  mov     [rdx+18h], rbp
0x14000ee50  movups  xmm0, xmmword ptr [rcx]
0x14000ee53  movups  xmmword ptr [rdx], xmm0
0x14000ee56  movups  xmm1, xmmword ptr [rcx+10h]
0x14000ee5a  movups  xmmword ptr [rdx+10h], xmm1
0x14000ee5e  mov     [rcx+10h], rbp
0x14000ee62  mov     [rcx+18h], r14
0x14000ee66  mov     [rcx], bp
0x14000ee69  mov     byte ptr [rdx+20h], 1
0x14000ee6d  cmp     [rcx+20h], bpl
0x14000ee71  jz      short loc_14000EE7C
0x14000ee73  mov     [rcx+20h], bpl
0x14000ee77  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000ee7c  lea     r9, [rbx+0C0h]
0x14000ee83  lea     rcx, [rdi+0C0h]
0x14000ee8a  mov     [r9+18h], bpl
0x14000ee8e  mov     [r9+20h], r9
0x14000ee92  cmp     [rcx+18h], bpl
0x14000ee96  jz      short loc_14000EECD
0x14000ee98  mov     r8, [rcx+10h]
0x14000ee9c  mov     rdx, [rcx+8]
0x14000eea0  mov     rax, [rcx]
0x14000eea3  mov     [rcx+10h], rbp
0x14000eea7  mov     [rcx+8], rbp
0x14000eeab  mov     [rcx], rbp
0x14000eeae  mov     [r9], rax
0x14000eeb1  mov     [r9+8], rdx
0x14000eeb5  mov     [r9+10h], r8
0x14000eeb9  mov     byte ptr [r9+18h], 1
0x14000eebe  cmp     [rcx+18h], bpl
0x14000eec2  jz      short loc_14000EECD
0x14000eec4  mov     [rcx+18h], bpl
0x14000eec8  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14000eecd  mov     al, [rdi+0E8h]
0x14000eed3  mov     [rbx+0E8h], al
0x14000eed9  mov     eax, [rdi+0ECh]
0x14000eedf  mov     [rbx+0ECh], eax
0x14000eee5  mov     [rsi], ebp
0x14000eee7  add     rsp, 20h
0x14000eeeb  pop     r14
0x14000eeed  pop     rdi
0x14000eeee  pop     rsi
0x14000eeef  pop     rbp
0x14000eef0  pop     rbx
0x14000eef1  retn
```

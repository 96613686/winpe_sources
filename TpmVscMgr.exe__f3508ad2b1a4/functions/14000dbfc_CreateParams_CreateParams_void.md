# CreateParams::~CreateParams(void)

- ea: `0x14000dbfc`
- end: `0x14000dc6f`
- name: `??1CreateParams@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(CreateParams *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dc98`
- `0x14000ded8`
- `0x14000ecf4`
- `0x14000f54c`
- `0x140010a68`
- `0x14001223e`

## callees

- `0x140008530`
- `0x14000dab8`
- `0x14000dbfc`

## pseudocode

```c
void __fastcall CreateParams::~CreateParams(CreateParams *this)
{
  char *v2; // rcx

  v2 = (char *)this + 192;
  if ( v2[24] )
  {
    v2[24] = 0;
    std::vector<unsigned char>::~vector<unsigned char>(v2);
  }
  if ( *((_BYTE *)this + 176) )
  {
    *((_BYTE *)this + 176) = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((char *)this + 144);
  }
  if ( *((_BYTE *)this + 128) )
  {
    *((_BYTE *)this + 128) = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((char *)this + 96);
  }
  if ( *((_BYTE *)this + 80) )
  {
    *((_BYTE *)this + 80) = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((char *)this + 48);
  }
  if ( *((_BYTE *)this + 32) )
  {
    *((_BYTE *)this + 32) = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(this);
  }
}

```

## disassembly

```asm
0x14000dbfc  push    rbx
0x14000dbfe  sub     rsp, 20h
0x14000dc02  mov     rbx, rcx
0x14000dc05  add     rcx, 0C0h
0x14000dc0c  cmp     byte ptr [rcx+18h], 0
0x14000dc10  jz      short loc_14000DC1B
0x14000dc12  mov     byte ptr [rcx+18h], 0
0x14000dc16  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14000dc1b  lea     rcx, [rbx+90h]
0x14000dc22  cmp     byte ptr [rcx+20h], 0
0x14000dc26  jz      short loc_14000DC31
0x14000dc28  mov     byte ptr [rcx+20h], 0
0x14000dc2c  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000dc31  lea     rcx, [rbx+60h]
0x14000dc35  cmp     byte ptr [rcx+20h], 0
0x14000dc39  jz      short loc_14000DC44
0x14000dc3b  mov     byte ptr [rcx+20h], 0
0x14000dc3f  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000dc44  lea     rcx, [rbx+30h]
0x14000dc48  cmp     byte ptr [rcx+20h], 0
0x14000dc4c  jz      short loc_14000DC57
0x14000dc4e  mov     byte ptr [rcx+20h], 0
0x14000dc52  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000dc57  cmp     byte ptr [rbx+20h], 0
0x14000dc5b  jz      short loc_14000DC69
0x14000dc5d  mov     rcx, rbx
0x14000dc60  mov     byte ptr [rbx+20h], 0
0x14000dc64  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000dc69  add     rsp, 20h
0x14000dc6d  pop     rbx
0x14000dc6e  retn
```

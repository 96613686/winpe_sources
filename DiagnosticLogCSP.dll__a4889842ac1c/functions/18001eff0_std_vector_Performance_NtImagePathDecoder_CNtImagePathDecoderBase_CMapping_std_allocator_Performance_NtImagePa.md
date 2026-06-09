# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x18001eff0`
- end: `0x18001f08e`
- name: `??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `158`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001f2ec`
- `0x18001f4d8`
- `0x18002989c`
- `0x1800299c4`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18001eff0`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(
        __int64 a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rax
  unsigned __int64 v5; // rdx
  char **v6; // rcx

  v1 = *(char ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(char ***)(a1 + 8);
    while ( v1 != v3 )
    {
      std::wstring::~wstring(v1 + 4);
      std::wstring::~wstring(v1);
      v1 += 8;
    }
    v4 = *(char ***)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFC0uLL;
    if ( v5 < 0x1000 )
    {
      v6 = *(char ***)a1;
    }
    else
    {
      v6 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001eff0  mov     [rsp+arg_0], rbx
0x18001eff5  mov     [rsp+arg_8], rsi
0x18001effa  push    rdi
0x18001effb  sub     rsp, 20h
0x18001efff  mov     rbx, [rcx]
0x18001f002  mov     rdi, rcx
0x18001f005  test    rbx, rbx
0x18001f008  jz      short loc_18001F07E
0x18001f00a  mov     rsi, [rcx+8]
0x18001f00e  jmp     short loc_18001F025
0x18001f010  lea     rcx, [rbx+20h]
0x18001f014  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f019  mov     rcx, rbx
0x18001f01c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f021  add     rbx, 40h ; '@'
0x18001f025  cmp     rbx, rsi
0x18001f028  jnz     short loc_18001F010
0x18001f02a  mov     rax, [rdi]
0x18001f02d  mov     rdx, [rdi+10h]
0x18001f031  sub     rdx, rax
0x18001f034  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18001f038  cmp     rdx, 1000h
0x18001f03f  jb      short loc_18001F05F
0x18001f041  mov     rcx, [rax-8]
0x18001f045  sub     rax, rcx
0x18001f048  sub     rax, 8
0x18001f04c  cmp     rax, 1Fh
0x18001f050  ja      short loc_18001F058
0x18001f052  add     rdx, 27h ; '''
0x18001f056  jmp     short loc_18001F062
0x18001f058  mov     ecx, 5
0x18001f05d  int     29h; Win8: RtlFailFast(ecx)
0x18001f05f  mov     rcx, rax; void *
0x18001f062  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f067  mov     qword ptr [rdi], 0
0x18001f06e  mov     qword ptr [rdi+8], 0
0x18001f076  mov     qword ptr [rdi+10h], 0
0x18001f07e  mov     rbx, [rsp+28h+arg_0]
0x18001f083  mov     rsi, [rsp+28h+arg_8]
0x18001f088  add     rsp, 20h
0x18001f08c  pop     rdi
0x18001f08d  retn
```

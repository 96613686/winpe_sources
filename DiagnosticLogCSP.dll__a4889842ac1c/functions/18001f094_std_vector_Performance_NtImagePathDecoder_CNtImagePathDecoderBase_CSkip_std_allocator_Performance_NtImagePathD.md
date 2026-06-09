# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(void)

- ea: `0x18001f094`
- end: `0x18001f129`
- name: `??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `149`
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
- `0x18001f094`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
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
      std::wstring::~wstring(v1);
      v1 += 4;
    }
    v4 = *(char ***)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL;
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
0x18001f094  mov     [rsp+arg_0], rbx
0x18001f099  mov     [rsp+arg_8], rsi
0x18001f09e  push    rdi
0x18001f09f  sub     rsp, 20h
0x18001f0a3  mov     rbx, [rcx]
0x18001f0a6  mov     rdi, rcx
0x18001f0a9  test    rbx, rbx
0x18001f0ac  jz      short loc_18001F119
0x18001f0ae  mov     rsi, [rcx+8]
0x18001f0b2  jmp     short loc_18001F0C0
0x18001f0b4  mov     rcx, rbx
0x18001f0b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f0bc  add     rbx, 20h ; ' '
0x18001f0c0  cmp     rbx, rsi
0x18001f0c3  jnz     short loc_18001F0B4
0x18001f0c5  mov     rax, [rdi]
0x18001f0c8  mov     rdx, [rdi+10h]
0x18001f0cc  sub     rdx, rax
0x18001f0cf  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18001f0d3  cmp     rdx, 1000h
0x18001f0da  jb      short loc_18001F0FA
0x18001f0dc  mov     rcx, [rax-8]
0x18001f0e0  sub     rax, rcx
0x18001f0e3  sub     rax, 8
0x18001f0e7  cmp     rax, 1Fh
0x18001f0eb  ja      short loc_18001F0F3
0x18001f0ed  add     rdx, 27h ; '''
0x18001f0f1  jmp     short loc_18001F0FD
0x18001f0f3  mov     ecx, 5
0x18001f0f8  int     29h; Win8: RtlFailFast(ecx)
0x18001f0fa  mov     rcx, rax; void *
0x18001f0fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f102  mov     qword ptr [rdi], 0
0x18001f109  mov     qword ptr [rdi+8], 0
0x18001f111  mov     qword ptr [rdi+10h], 0
0x18001f119  mov     rbx, [rsp+28h+arg_0]
0x18001f11e  mov     rsi, [rsp+28h+arg_8]
0x18001f123  add     rsp, 20h
0x18001f127  pop     rdi
0x18001f128  retn
```

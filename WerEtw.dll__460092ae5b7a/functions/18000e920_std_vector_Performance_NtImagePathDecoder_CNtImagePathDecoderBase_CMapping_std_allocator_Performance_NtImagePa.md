# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000e920`
- end: `0x18000e9a8`
- name: `??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bf98`
- `0x180027ff2`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e920`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  char **v2; // rsi
  char **i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = (char **)a1[4];
    for ( i = (char **)a1[3]; i != v2; i += 8 )
    {
      std::wstring::~wstring(i + 4);
      std::wstring::~wstring(i);
    }
    v4 = a1[1];
    if ( a1[2] << 6 < 0x1000u )
    {
      v5 = (void *)a1[1];
    }
    else
    {
      v5 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
  }
}

```

## disassembly

```asm
0x18000e920  mov     [rsp+arg_0], rbx
0x18000e925  mov     [rsp+arg_8], rsi
0x18000e92a  push    rdi
0x18000e92b  sub     rsp, 20h
0x18000e92f  cmp     qword ptr [rcx+8], 0
0x18000e934  mov     rbx, rcx
0x18000e937  jz      short loc_18000E998
0x18000e939  mov     rsi, [rcx+20h]
0x18000e93d  mov     rdi, [rcx+18h]
0x18000e941  jmp     short loc_18000E958
0x18000e943  lea     rcx, [rdi+20h]
0x18000e947  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e94c  mov     rcx, rdi
0x18000e94f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e954  add     rdi, 40h ; '@'
0x18000e958  cmp     rdi, rsi
0x18000e95b  jnz     short loc_18000E943
0x18000e95d  mov     rdx, [rbx+10h]
0x18000e961  mov     rax, [rbx+8]
0x18000e965  shl     rdx, 6
0x18000e969  cmp     rdx, 1000h
0x18000e970  jb      short loc_18000E990
0x18000e972  mov     rcx, [rax-8]
0x18000e976  sub     rax, rcx
0x18000e979  sub     rax, 8
0x18000e97d  cmp     rax, 1Fh
0x18000e981  ja      short loc_18000E989
0x18000e983  add     rdx, 27h ; '''
0x18000e987  jmp     short loc_18000E993
0x18000e989  mov     ecx, 5
0x18000e98e  int     29h; Win8: RtlFailFast(ecx)
0x18000e990  mov     rcx, rax; Block
0x18000e993  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e998  mov     rbx, [rsp+28h+arg_0]
0x18000e99d  mov     rsi, [rsp+28h+arg_8]
0x18000e9a2  add     rsp, 20h
0x18000e9a6  pop     rdi
0x18000e9a7  retn
```

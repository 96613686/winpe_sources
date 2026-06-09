# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18001f544`
- end: `0x18001f5cc`
- name: `??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `136`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001ceb8`
- `0x180035fdf`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18001f544`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  char **v2; // rsi
  char **i; // rdi
  __int64 v4; // rax
  unsigned __int64 v5; // rdx
  void *v6; // rcx

  if ( a1[1] )
  {
    v2 = (char **)a1[4];
    for ( i = (char **)a1[3]; i != v2; i += 8 )
    {
      std::wstring::~wstring(i + 4);
      std::wstring::~wstring(i);
    }
    v4 = a1[1];
    v5 = a1[2] << 6;
    if ( v5 < 0x1000 )
    {
      v6 = (void *)a1[1];
    }
    else
    {
      v6 = *(void **)(v4 - 8);
      if ( (unsigned __int64)(v4 - (_QWORD)v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
  }
}

```

## disassembly

```asm
0x18001f544  mov     [rsp+arg_0], rbx
0x18001f549  mov     [rsp+arg_8], rsi
0x18001f54e  push    rdi
0x18001f54f  sub     rsp, 20h
0x18001f553  cmp     qword ptr [rcx+8], 0
0x18001f558  mov     rbx, rcx
0x18001f55b  jz      short loc_18001F5BC
0x18001f55d  mov     rsi, [rcx+20h]
0x18001f561  mov     rdi, [rcx+18h]
0x18001f565  jmp     short loc_18001F57C
0x18001f567  lea     rcx, [rdi+20h]
0x18001f56b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f570  mov     rcx, rdi
0x18001f573  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f578  add     rdi, 40h ; '@'
0x18001f57c  cmp     rdi, rsi
0x18001f57f  jnz     short loc_18001F567
0x18001f581  mov     rdx, [rbx+10h]
0x18001f585  mov     rax, [rbx+8]
0x18001f589  shl     rdx, 6; unsigned __int64
0x18001f58d  cmp     rdx, 1000h
0x18001f594  jb      short loc_18001F5B4
0x18001f596  mov     rcx, [rax-8]
0x18001f59a  sub     rax, rcx
0x18001f59d  sub     rax, 8
0x18001f5a1  cmp     rax, 1Fh
0x18001f5a5  ja      short loc_18001F5AD
0x18001f5a7  add     rdx, 27h ; '''
0x18001f5ab  jmp     short loc_18001F5B7
0x18001f5ad  mov     ecx, 5
0x18001f5b2  int     29h; Win8: RtlFailFast(ecx)
0x18001f5b4  mov     rcx, rax; void *
0x18001f5b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f5bc  mov     rbx, [rsp+28h+arg_0]
0x18001f5c1  mov     rsi, [rsp+28h+arg_8]
0x18001f5c6  add     rsp, 20h
0x18001f5ca  pop     rdi
0x18001f5cb  retn
```

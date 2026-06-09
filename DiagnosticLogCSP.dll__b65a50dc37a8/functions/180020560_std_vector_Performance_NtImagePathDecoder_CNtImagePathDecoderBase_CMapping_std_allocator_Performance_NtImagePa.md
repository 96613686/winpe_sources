# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180020560`
- end: `0x1800205e9`
- name: `??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001de4c`
- `0x180037791`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x180020560`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 64 )
    {
      std::wstring::~wstring(i + 32);
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
0x180020560  mov     [rsp+arg_0], rbx
0x180020565  mov     [rsp+arg_8], rsi
0x18002056a  push    rdi
0x18002056b  sub     rsp, 20h
0x18002056f  cmp     qword ptr [rcx+8], 0
0x180020574  mov     rbx, rcx
0x180020577  jz      short loc_1800205D8
0x180020579  mov     rsi, [rcx+20h]
0x18002057d  mov     rdi, [rcx+18h]
0x180020581  jmp     short loc_180020598
0x180020583  lea     rcx, [rdi+20h]
0x180020587  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002058c  mov     rcx, rdi
0x18002058f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180020594  add     rdi, 40h ; '@'
0x180020598  cmp     rdi, rsi
0x18002059b  jnz     short loc_180020583
0x18002059d  mov     rdx, [rbx+10h]
0x1800205a1  mov     rax, [rbx+8]
0x1800205a5  shl     rdx, 6; unsigned __int64
0x1800205a9  cmp     rdx, 1000h
0x1800205b0  jb      short loc_1800205D0
0x1800205b2  mov     rcx, [rax-8]
0x1800205b6  sub     rax, rcx
0x1800205b9  sub     rax, 8
0x1800205bd  cmp     rax, 1Fh
0x1800205c1  ja      short loc_1800205C9
0x1800205c3  add     rdx, 27h ; '''
0x1800205c7  jmp     short loc_1800205D3
0x1800205c9  mov     ecx, 5
0x1800205ce  int     29h; Win8: RtlFailFast(ecx)
0x1800205d0  mov     rcx, rax; void *
0x1800205d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800205d8  mov     rbx, [rsp+28h+arg_0]
0x1800205dd  mov     rsi, [rsp+28h+arg_8]
0x1800205e2  add     rsp, 20h
0x1800205e6  pop     rdi
0x1800205e7  retn
```

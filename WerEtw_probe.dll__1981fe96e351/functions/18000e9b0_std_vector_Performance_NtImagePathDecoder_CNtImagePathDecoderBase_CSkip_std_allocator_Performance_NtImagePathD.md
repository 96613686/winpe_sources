# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000e9b0`
- end: `0x18000ea2f`
- name: `??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c1bc`
- `0x180028016`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e9b0`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 v2; // rsi
  __int64 i; // rdi
  __int64 v4; // rax
  void *v5; // rcx

  if ( a1[1] )
  {
    v2 = a1[4];
    for ( i = a1[3]; i != v2; i += 32 )
      std::wstring::~wstring(i);
    v4 = a1[1];
    if ( (unsigned __int64)(32LL * a1[2]) < 0x1000 )
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
0x18000e9b0  mov     [rsp+arg_0], rbx
0x18000e9b5  mov     [rsp+arg_8], rsi
0x18000e9ba  push    rdi
0x18000e9bb  sub     rsp, 20h
0x18000e9bf  cmp     qword ptr [rcx+8], 0
0x18000e9c4  mov     rbx, rcx
0x18000e9c7  jz      short loc_18000EA1F
0x18000e9c9  mov     rsi, [rcx+20h]
0x18000e9cd  mov     rdi, [rcx+18h]
0x18000e9d1  jmp     short loc_18000E9DF
0x18000e9d3  mov     rcx, rdi
0x18000e9d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e9db  add     rdi, 20h ; ' '
0x18000e9df  cmp     rdi, rsi
0x18000e9e2  jnz     short loc_18000E9D3
0x18000e9e4  mov     rdx, [rbx+10h]
0x18000e9e8  mov     rax, [rbx+8]
0x18000e9ec  shl     rdx, 5
0x18000e9f0  cmp     rdx, 1000h
0x18000e9f7  jb      short loc_18000EA17
0x18000e9f9  mov     rcx, [rax-8]
0x18000e9fd  sub     rax, rcx
0x18000ea00  sub     rax, 8
0x18000ea04  cmp     rax, 1Fh
0x18000ea08  ja      short loc_18000EA10
0x18000ea0a  add     rdx, 27h ; '''
0x18000ea0e  jmp     short loc_18000EA1A
0x18000ea10  mov     ecx, 5
0x18000ea15  int     29h; Win8: RtlFailFast(ecx)
0x18000ea17  mov     rcx, rax; Block
0x18000ea1a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ea1f  mov     rbx, [rsp+28h+arg_0]
0x18000ea24  mov     rsi, [rsp+28h+arg_8]
0x18000ea29  add     rsp, 20h
0x18000ea2d  pop     rdi
0x18000ea2e  retn
```

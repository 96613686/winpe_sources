# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(void)

- ea: `0x18000e474`
- end: `0x18000e509`
- name: `??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e6cc`
- `0x18000e8b4`
- `0x180018a9c`
- `0x180018bc4`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e474`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(
        __int64 a1)
{
  char **v1; // rbx
  char **v3; // rsi
  char **v4; // rax
  char **v5; // rcx

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
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v5 = *(char ***)a1;
    }
    else
    {
      v5 = (char **)*(v4 - 1);
      if ( (unsigned __int64)((char *)v4 - (char *)v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000e474  mov     [rsp+arg_0], rbx
0x18000e479  mov     [rsp+arg_8], rsi
0x18000e47e  push    rdi
0x18000e47f  sub     rsp, 20h
0x18000e483  mov     rbx, [rcx]
0x18000e486  mov     rdi, rcx
0x18000e489  test    rbx, rbx
0x18000e48c  jz      short loc_18000E4F9
0x18000e48e  mov     rsi, [rcx+8]
0x18000e492  jmp     short loc_18000E4A0
0x18000e494  mov     rcx, rbx
0x18000e497  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e49c  add     rbx, 20h ; ' '
0x18000e4a0  cmp     rbx, rsi
0x18000e4a3  jnz     short loc_18000E494
0x18000e4a5  mov     rax, [rdi]
0x18000e4a8  mov     rdx, [rdi+10h]
0x18000e4ac  sub     rdx, rax
0x18000e4af  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18000e4b3  cmp     rdx, 1000h
0x18000e4ba  jb      short loc_18000E4DA
0x18000e4bc  mov     rcx, [rax-8]
0x18000e4c0  sub     rax, rcx
0x18000e4c3  sub     rax, 8
0x18000e4c7  cmp     rax, 1Fh
0x18000e4cb  ja      short loc_18000E4D3
0x18000e4cd  add     rdx, 27h ; '''
0x18000e4d1  jmp     short loc_18000E4DD
0x18000e4d3  mov     ecx, 5
0x18000e4d8  int     29h; Win8: RtlFailFast(ecx)
0x18000e4da  mov     rcx, rax; Block
0x18000e4dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e4e2  mov     qword ptr [rdi], 0
0x18000e4e9  mov     qword ptr [rdi+8], 0
0x18000e4f1  mov     qword ptr [rdi+10h], 0
0x18000e4f9  mov     rbx, [rsp+28h+arg_0]
0x18000e4fe  mov     rsi, [rsp+28h+arg_8]
0x18000e503  add     rsp, 20h
0x18000e507  pop     rdi
0x18000e508  retn
```

# CAudioMediaType::Create(tWAVEFORMATEX const *,uint,IAudioMediaType * *,float,int)

- ea: `0x180016114`
- end: `0x1800161e2`
- name: `?Create@CAudioMediaType@@SAJPEBUtWAVEFORMATEX@@IPEAPEAUIAudioMediaType@@MH@Z`
- size: `206`
- prototype: `__int64 __usercall@<rax>(const struct tWAVEFORMATEX *@<rcx>, unsigned int@<edx>, struct IAudioMediaType **@<r8>, float@<xmm3>, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800168a8`
- `0x1800168c8`

## callees

- `0x1800150c4`
- `0x180015104`
- `0x180016084`
- `0x180016114`
- `0x180016660`
- `0x180016710`

## pseudocode

```c
__int64 __fastcall CAudioMediaType::Create(
        const struct tWAVEFORMATEX *a1,
        unsigned int a2,
        struct IAudioMediaType **a3,
        float a4,
        int a5)
{
  float *v9; // rax
  float *v10; // rbx
  int Interface; // edi

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v9 = (float *)operator new(0x20u);
  v10 = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = 0;
    *(_QWORD *)v9 = &CAudioMediaType::`vftable';
    *((_QWORD *)v9 + 2) = 0;
    v9[6] = 0.0;
    if ( !a1 || (Interface = CAudioMediaType::SetAudioFormat((void **)v9, a1, a2, a5), Interface >= 0) )
    {
      v10[6] = a4;
      Interface = CAudioMediaType::QueryInterface(
                    (CAudioMediaType *)v10,
                    &GUID_4e997f73_b71f_4798_873b_ed7dfcf15b4d,
                    (void **)a3);
      if ( Interface >= 0 )
        return (unsigned int)Interface;
    }
    CAudioMediaType::~CAudioMediaType((CAudioMediaType *)v10);
    operator delete(v10);
  }
  else
  {
    Interface = -2147024882;
  }
  *a3 = 0;
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180016114  push    rbx
0x180016116  push    rbp
0x180016117  push    rsi
0x180016118  push    rdi
0x180016119  sub     rsp, 38h
0x18001611d  movaps  [rsp+58h+var_38], xmm6
0x180016122  movaps  xmm6, xmm3
0x180016125  mov     rsi, r8
0x180016128  mov     ebp, edx
0x18001612a  mov     rdi, rcx
0x18001612d  test    r8, r8
0x180016130  jnz     short loc_18001613C
0x180016132  mov     eax, 80070057h
0x180016137  jmp     loc_1800161D4
0x18001613c  mov     ecx, 20h ; ' '; Size
0x180016141  mov     qword ptr [r8], 0
0x180016148  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001614d  mov     rbx, rax
0x180016150  test    rax, rax
0x180016153  jz      short loc_1800161C6
0x180016155  mov     qword ptr [rbx+8], 0
0x18001615d  lea     rax, ??_7CAudioMediaType@@6B@; const CAudioMediaType::`vftable'
0x180016164  mov     [rbx], rax
0x180016167  mov     qword ptr [rbx+10h], 0
0x18001616f  mov     dword ptr [rbx+18h], 0
0x180016176  test    rdi, rdi
0x180016179  jz      short loc_180016197
0x18001617b  mov     r9d, [rsp+58h+arg_20]; int
0x180016183  mov     r8d, ebp; unsigned int
0x180016186  mov     rdx, rdi; struct tWAVEFORMATEX *
0x180016189  mov     rcx, rbx; this
0x18001618c  call    ?SetAudioFormat@CAudioMediaType@@IEAAJPEBUtWAVEFORMATEX@@IH@Z; CAudioMediaType::SetAudioFormat(tWAVEFORMATEX const *,uint,int)
0x180016191  mov     edi, eax
0x180016193  test    eax, eax
0x180016195  js      short loc_1800161B4
0x180016197  mov     r8, rsi; void **
0x18001619a  movss   dword ptr [rbx+18h], xmm6
0x18001619f  lea     rdx, _GUID_4e997f73_b71f_4798_873b_ed7dfcf15b4d; struct _GUID *
0x1800161a6  mov     rcx, rbx; this
0x1800161a9  call    ?QueryInterface@CAudioMediaType@@UEAAJAEBU_GUID@@PEAPEAX@Z; CAudioMediaType::QueryInterface(_GUID const &,void * *)
0x1800161ae  mov     edi, eax
0x1800161b0  test    eax, eax
0x1800161b2  jns     short loc_1800161D2
0x1800161b4  mov     rcx, rbx; this
0x1800161b7  call    ??1CAudioMediaType@@MEAA@XZ; CAudioMediaType::~CAudioMediaType(void)
0x1800161bc  mov     rcx, rbx; Block
0x1800161bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800161c4  jmp     short loc_1800161CB
0x1800161c6  mov     edi, 8007000Eh
0x1800161cb  mov     qword ptr [rsi], 0
0x1800161d2  mov     eax, edi
0x1800161d4  movaps  xmm6, [rsp+58h+var_38]
0x1800161d9  add     rsp, 38h
0x1800161dd  pop     rdi
0x1800161de  pop     rsi
0x1800161df  pop     rbp
0x1800161e0  pop     rbx
0x1800161e1  retn
```

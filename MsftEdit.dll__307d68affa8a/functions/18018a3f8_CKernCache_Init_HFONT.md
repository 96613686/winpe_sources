# CKernCache::Init(HFONT__ *)

- ea: `0x18018a3f8`
- end: `0x18018a57b`
- name: `?Init@CKernCache@@AEAAXPEAUHFONT__@@@Z`
- size: `387`
- prototype: `void __fastcall(CKernCache *__hidden this, HFONT h)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180128ac8`

## callees

- `0x180050060`
- `0x18007e0f0`
- `0x18013bad0`
- `0x18013bea0`
- `0x18013beac`
- `0x18013c916`
- `0x18014fbac`
- `0x18018a35c`
- `0x18018a3f8`
- `0x1801e7dc4`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18018a456`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18018a456`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018a48e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018a541`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018a48e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18018a541`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18018a476`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x18018a476`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18018a54a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18018a54a`

## pseudocode

```c
void __fastcall CKernCache::Init(CKernCache *this, HFONT h)
{
  HDC ScreenDC; // rax
  HDC v5; // rbp
  HFONT v6; // rax
  HFONT v7; // rsi
  HGDIOBJ v8; // r15
  signed int KerningPairs; // eax
  unsigned __int64 v10; // rdi
  int PrimeLessThan; // ebx
  struct tagKERNINGPAIR *v12; // r14
  unsigned __int64 v13; // rdx
  int v14; // r12d
  __int64 v15; // rbx
  LOGFONTW pv; // [rsp+20h] [rbp-A8h] BYREF

  ScreenDC = CW32System::GetScreenDC();
  *((_DWORD *)this + 8) = 2;
  v5 = ScreenDC;
  memset_0(&pv, 0, sizeof(pv));
  if ( GetObjectW(h, 92, &pv) )
  {
    pv.lfHeight = -2048;
    pv.lfCharSet = 0;
    v6 = CreateFontIndirectW(&pv);
    v7 = v6;
    if ( v6 )
    {
      v8 = SelectObject(v5, v6);
      KerningPairs = CW32System::GetKerningPairs(v5, 0, 0);
      v10 = KerningPairs;
      if ( KerningPairs )
      {
        PrimeLessThan = FindPrimeLessThan(5 * KerningPairs / 2);
        if ( PrimeLessThan )
        {
          v12 = (struct tagKERNINGPAIR *)operator new[](saturated_mul(v10, 8u));
          CW32System::GetKerningPairs(v5, v10, v12);
          CArrayBase::ArAdd(this, PrimeLessThan, 0);
          v14 = 0;
          if ( (int)v10 > 0 )
          {
            v15 = 0;
            do
            {
              CKernCache::Add(this, v12[v15].wFirst, v12[v15].wSecond, v12[v15].iKernAmount);
              ++v14;
              ++v15;
            }
            while ( v14 < (int)v10 );
          }
          operator delete(v12, v13);
          *((_DWORD *)this + 8) = 1;
        }
      }
      if ( v8 )
        SelectObject(v5, v8);
      DeleteObject(v7);
    }
  }
}

```

## disassembly

```asm
0x18018a3f8  mov     [rsp+arg_10], rbx
0x18018a3fd  push    rbp
0x18018a3fe  push    rsi
0x18018a3ff  push    rdi
0x18018a400  push    r12
0x18018a402  push    r13
0x18018a404  push    r14
0x18018a406  push    r15
0x18018a408  sub     rsp, 90h
0x18018a40f  mov     rax, cs:__security_cookie
0x18018a416  xor     rax, rsp
0x18018a419  mov     [rsp+0C8h+var_48], rax
0x18018a421  mov     rbx, rdx
0x18018a424  mov     r13, rcx
0x18018a427  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x18018a42c  mov     r14d, 2
0x18018a432  lea     rcx, [rsp+0C8h+pv]; void *
0x18018a437  xor     edx, edx; Val
0x18018a439  mov     [r13+20h], r14d
0x18018a43d  mov     rbp, rax
0x18018a440  lea     edi, [r14+5Ah]
0x18018a444  mov     r8d, edi; Size
0x18018a447  call    memset_0
0x18018a44c  lea     r8, [rsp+0C8h+pv]; pv
0x18018a451  mov     edx, edi; c
0x18018a453  mov     rcx, rbx; h
0x18018a456  call    cs:__imp_GetObjectW
0x18018a45c  test    eax, eax
0x18018a45e  jz      loc_18018A550
0x18018a464  lea     rcx, [rsp+0C8h+pv]; lplf
0x18018a469  mov     [rsp+0C8h+pv], 0FFFFF800h
0x18018a471  mov     [rsp+0C8h+var_91], 0
0x18018a476  call    cs:__imp_CreateFontIndirectW
0x18018a47c  mov     rsi, rax
0x18018a47f  test    rax, rax
0x18018a482  jz      loc_18018A550
0x18018a488  mov     rdx, rax; h
0x18018a48b  mov     rcx, rbp; hdc
0x18018a48e  call    cs:__imp_SelectObject
0x18018a494  xor     r8d, r8d; struct tagKERNINGPAIR *
0x18018a497  xor     edx, edx; unsigned int
0x18018a499  mov     rcx, rbp; HDC
0x18018a49c  mov     r15, rax
0x18018a49f  call    ?GetKerningPairs@CW32System@@SAKPEAUHDC__@@KPEAUtagKERNINGPAIR@@@Z; CW32System::GetKerningPairs(HDC__ *,ulong,tagKERNINGPAIR *)
0x18018a4a4  movsxd  rdi, eax
0x18018a4a7  test    eax, eax
0x18018a4a9  jz      loc_18018A536
0x18018a4af  lea     eax, [rdi+rdi*4]
0x18018a4b2  cdq
0x18018a4b3  idiv    r14d
0x18018a4b6  mov     ecx, eax; int
0x18018a4b8  call    ?FindPrimeLessThan@@YAHH@Z; FindPrimeLessThan(int)
0x18018a4bd  mov     ebx, eax
0x18018a4bf  test    eax, eax
0x18018a4c1  jz      short loc_18018A536
0x18018a4c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18018a4ca  lea     eax, [r14+6]
0x18018a4ce  mul     rdi
0x18018a4d1  cmovb   rax, rcx
0x18018a4d5  mov     rcx, rax; unsigned __int64
0x18018a4d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18018a4dd  mov     r8, rax; struct tagKERNINGPAIR *
0x18018a4e0  mov     edx, edi; unsigned int
0x18018a4e2  mov     rcx, rbp; HDC
0x18018a4e5  mov     r14, rax
0x18018a4e8  call    ?GetKerningPairs@CW32System@@SAKPEAUHDC__@@KPEAUtagKERNINGPAIR@@@Z; CW32System::GetKerningPairs(HDC__ *,ulong,tagKERNINGPAIR *)
0x18018a4ed  xor     r8d, r8d; int *
0x18018a4f0  mov     edx, ebx; int
0x18018a4f2  mov     rcx, r13; this
0x18018a4f5  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18018a4fa  xor     r12d, r12d
0x18018a4fd  test    edi, edi
0x18018a4ff  jle     short loc_18018A526
0x18018a501  xor     ebx, ebx
0x18018a503  mov     r9d, [r14+rbx*8+4]; int
0x18018a508  mov     rcx, r13; this
0x18018a50b  movzx   r8d, word ptr [r14+rbx*8+2]; unsigned __int16
0x18018a511  movzx   edx, word ptr [r14+rbx*8]; unsigned __int16
0x18018a516  call    ?Add@CKernCache@@AEAAXGGJ@Z; CKernCache::Add(ushort,ushort,long)
0x18018a51b  inc     r12d
0x18018a51e  inc     rbx
0x18018a521  cmp     r12d, edi
0x18018a524  jl      short loc_18018A503
0x18018a526  mov     rcx, r14; void *
0x18018a529  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18018a52e  mov     dword ptr [r13+20h], 1
0x18018a536  test    r15, r15
0x18018a539  jz      short loc_18018A547
0x18018a53b  mov     rdx, r15; h
0x18018a53e  mov     rcx, rbp; hdc
0x18018a541  call    cs:__imp_SelectObject
0x18018a547  mov     rcx, rsi; ho
0x18018a54a  call    cs:__imp_DeleteObject
0x18018a550  mov     rcx, [rsp+0C8h+var_48]
0x18018a558  xor     rcx, rsp; StackCookie
0x18018a55b  call    __security_check_cookie
0x18018a560  mov     rbx, [rsp+0C8h+arg_10]
0x18018a568  add     rsp, 90h
0x18018a56f  pop     r15
0x18018a571  pop     r14
0x18018a573  pop     r13
0x18018a575  pop     r12
0x18018a577  pop     rdi
0x18018a578  pop     rsi
0x18018a579  pop     rbp
0x18018a57a  retn
```

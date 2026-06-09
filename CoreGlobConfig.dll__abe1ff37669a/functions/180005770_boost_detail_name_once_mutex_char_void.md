# boost::detail::name_once_mutex(char *,void *)

- ea: `0x180005770`
- end: `0x180005859`
- name: `?name_once_mutex@detail@boost@@YAXPEADPEAX@Z`
- size: `233`
- prototype: `void __fastcall(boost::detail *__hidden this, char *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180005220`
- `0x180005960`

## callees

- `0x180004370`
- `0x180005770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057b9`

## pseudocode

```c
void __fastcall boost::detail::name_once_mutex(boost::detail *this, char *a2, void *a3)
{
  char *v4; // rbx
  DWORD CurrentProcessId; // r8d
  unsigned int i; // eax
  DWORD v10; // edx

  strcpy((char *)this, "Local\\{C15730E2-145C-4c5e-B005-3BC753F42475}-once-flag");
  boost::detail::int_to_string<__int64>(a2, (char *)this + 54, a3);
  v4 = (char *)this + 70;
  CurrentProcessId = GetCurrentProcessId();
  _XMM4 = _mm_shuffle_epi32(_mm_cvtsi32_si128(CurrentProcessId), 0);
  if ( _isa_available < 5 )
  {
    for ( i = 0; i < 8; ++i )
    {
      v10 = CurrentProcessId >> (4 * i);
      *v4++ = (v10 & 0xF) + 65;
    }
    *v4 = 0;
  }
  else
  {
    __asm { vpsrlvd xmm0, xmm4, cs:__xmm@0000000c000000080000000400000000 }
    *(_DWORD *)v4 = _mm_cvtsi128_si32(
                      _mm_add_epi8(
                        (__m128i)_mm_and_ps((__m128)_mm_shuffle_epi8(_XMM0, (__m128i)_xmm), (__m128)_xmm),
                        (__m128i)_xmm));
    __asm { vpsrlvd xmm0, xmm4, cs:__xmm@0000001c000000180000001400000010 }
    *((_DWORD *)v4 + 1) = _mm_cvtsi128_si32(
                            _mm_add_epi8(
                              (__m128i)_mm_and_ps((__m128)_mm_shuffle_epi8(_XMM0, (__m128i)_xmm), (__m128)_xmm),
                              (__m128i)_xmm));
    v4[8] = 0;
  }
}

```

## disassembly

```asm
0x180005770  push    rbx
0x180005772  sub     rsp, 20h
0x180005776  movups  xmm0, cs:?fixed_mutex_name@?1??name_once_mutex@detail@boost@@YAXPEADPEAX@Z@4QBDB; char const near * const `boost::detail::name_once_mutex(char *,void *)'::`2'::fixed_mutex_name
0x18000577d  mov     rax, rdx
0x180005780  mov     rbx, rcx
0x180005783  lea     rdx, [rcx+36h]
0x180005787  movups  xmmword ptr [rcx], xmm0
0x18000578a  movups  xmm1, cs:xmmword_180027E08
0x180005791  movups  xmmword ptr [rcx+10h], xmm1
0x180005795  movups  xmm0, cs:xmmword_180027E18
0x18000579c  movups  xmmword ptr [rcx+20h], xmm0
0x1800057a0  movsd   xmm1, qword ptr cs:xmmword_180027E18+0Fh
0x1800057a8  movsd   qword ptr [rcx+2Fh], xmm1
0x1800057ad  mov     rcx, rax
0x1800057b0  call    ??$int_to_string@_J@detail@boost@@YAX_JPEAD@Z; boost::detail::int_to_string<__int64>(__int64,char *)
0x1800057b5  add     rbx, 46h ; 'F'
0x1800057b9  call    cs:__imp_GetCurrentProcessId
0x1800057bf  cmp     cs:__isa_available, 5
0x1800057c6  mov     r8d, eax
0x1800057c9  movd    xmm4, eax
0x1800057cd  pshufd  xmm4, xmm4, 0
0x1800057d2  jl      short loc_180005829
0x1800057d4  vpsrlvd xmm0, xmm4, cs:__xmm@0000000c000000080000000400000000
0x1800057dd  pshufb  xmm0, cs:__xmm@000000000c080400000000000c080400
0x1800057e6  andps   xmm0, cs:__xmm@0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f
0x1800057ed  paddb   xmm0, cs:__xmm@41414141414141414141414141414141
0x1800057f5  movd    dword ptr [rbx], xmm0
0x1800057f9  vpsrlvd xmm0, xmm4, cs:__xmm@0000001c000000180000001400000010
0x180005802  pshufb  xmm0, cs:__xmm@000000000c080400000000000c080400
0x18000580b  andps   xmm0, cs:__xmm@0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f
0x180005812  paddb   xmm0, cs:__xmm@41414141414141414141414141414141
0x18000581a  movd    dword ptr [rbx+4], xmm0
0x18000581f  mov     byte ptr [rbx+8], 0
0x180005823  add     rsp, 20h
0x180005827  pop     rbx
0x180005828  retn
0x180005829  xor     eax, eax
0x18000582b  nop     dword ptr [rax+rax+00h]
0x180005830  lea     ecx, ds:0[rax*4]
0x180005837  mov     edx, r8d
0x18000583a  shr     edx, cl
0x18000583c  lea     rbx, [rbx+1]
0x180005840  and     dl, 0Fh
0x180005843  inc     eax
0x180005845  add     dl, 41h ; 'A'
0x180005848  mov     [rbx-1], dl
0x18000584b  cmp     eax, 8
0x18000584e  jb      short loc_180005830
0x180005850  mov     byte ptr [rbx], 0
0x180005853  add     rsp, 20h
0x180005857  pop     rbx
0x180005858  retn
```

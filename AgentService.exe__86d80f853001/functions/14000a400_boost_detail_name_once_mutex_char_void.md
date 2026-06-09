# boost::detail::name_once_mutex(char *,void *)

- ea: `0x14000a400`
- end: `0x14000a4e9`
- name: `?name_once_mutex@detail@boost@@YAXPEADPEAX@Z`
- size: `233`
- prototype: `void __fastcall(boost::detail *__hidden this, char *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000a1b0`
- `0x14000a530`

## callees

- `0x140009ba0`
- `0x14000a400`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000a449`
- `KERNEL32!GetCurrentProcessId` at `0x14000a449`

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
0x14000a400  push    rbx
0x14000a402  sub     rsp, 20h
0x14000a406  movups  xmm0, cs:?fixed_mutex_name@?1??name_once_mutex@detail@boost@@YAXPEADPEAX@Z@4QBDB; char const near * const `boost::detail::name_once_mutex(char *,void *)'::`2'::fixed_mutex_name
0x14000a40d  mov     rax, rdx
0x14000a410  mov     rbx, rcx
0x14000a413  lea     rdx, [rcx+36h]
0x14000a417  movups  xmmword ptr [rcx], xmm0
0x14000a41a  movups  xmm1, cs:xmmword_14009FF70
0x14000a421  movups  xmmword ptr [rcx+10h], xmm1
0x14000a425  movups  xmm0, cs:xmmword_14009FF80
0x14000a42c  movups  xmmword ptr [rcx+20h], xmm0
0x14000a430  movsd   xmm1, qword ptr cs:xmmword_14009FF80+0Fh
0x14000a438  movsd   qword ptr [rcx+2Fh], xmm1
0x14000a43d  mov     rcx, rax
0x14000a440  call    ??$int_to_string@_J@detail@boost@@YAX_JPEAD@Z; boost::detail::int_to_string<__int64>(__int64,char *)
0x14000a445  add     rbx, 46h ; 'F'
0x14000a449  call    cs:__imp_GetCurrentProcessId
0x14000a44f  cmp     cs:__isa_available, 5
0x14000a456  mov     r8d, eax
0x14000a459  movd    xmm4, eax
0x14000a45d  pshufd  xmm4, xmm4, 0
0x14000a462  jl      short loc_14000A4B9
0x14000a464  vpsrlvd xmm0, xmm4, cs:__xmm@0000000c000000080000000400000000
0x14000a46d  pshufb  xmm0, cs:__xmm@000000000c080400000000000c080400
0x14000a476  andps   xmm0, cs:__xmm@0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f
0x14000a47d  paddb   xmm0, cs:__xmm@41414141414141414141414141414141
0x14000a485  movd    dword ptr [rbx], xmm0
0x14000a489  vpsrlvd xmm0, xmm4, cs:__xmm@0000001c000000180000001400000010
0x14000a492  pshufb  xmm0, cs:__xmm@000000000c080400000000000c080400
0x14000a49b  andps   xmm0, cs:__xmm@0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f0f
0x14000a4a2  paddb   xmm0, cs:__xmm@41414141414141414141414141414141
0x14000a4aa  movd    dword ptr [rbx+4], xmm0
0x14000a4af  mov     byte ptr [rbx+8], 0
0x14000a4b3  add     rsp, 20h
0x14000a4b7  pop     rbx
0x14000a4b8  retn
0x14000a4b9  xor     eax, eax
0x14000a4bb  nop     dword ptr [rax+rax+00h]
0x14000a4c0  lea     ecx, ds:0[rax*4]
0x14000a4c7  mov     edx, r8d
0x14000a4ca  shr     edx, cl
0x14000a4cc  lea     rbx, [rbx+1]
0x14000a4d0  and     dl, 0Fh
0x14000a4d3  inc     eax
0x14000a4d5  add     dl, 41h ; 'A'
0x14000a4d8  mov     [rbx-1], dl
0x14000a4db  cmp     eax, 8
0x14000a4de  jb      short loc_14000A4C0
0x14000a4e0  mov     byte ptr [rbx], 0
0x14000a4e3  add     rsp, 20h
0x14000a4e7  pop     rbx
0x14000a4e8  retn
```

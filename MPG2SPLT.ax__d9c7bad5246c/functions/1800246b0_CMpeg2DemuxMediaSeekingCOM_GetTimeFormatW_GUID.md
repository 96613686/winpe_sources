# CMpeg2DemuxMediaSeekingCOM::GetTimeFormatW(_GUID *)

- ea: `0x1800246b0`
- end: `0x18002471d`
- name: `?GetTimeFormatW@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800246b0`
- `0x180024804`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetTimeFormatW(CMpeg2DemuxMediaSeekingCOM *this, struct _GUID *a2)
{
  CMpeg2DemuxMediaSeekingCore *v5; // rdi
  __int64 v6; // rcx
  GUID v7; // xmm0

  if ( !a2 )
    return 2147500035LL;
  v5 = (CMpeg2DemuxMediaSeekingCore *)*((_QWORD *)this + 6);
  v6 = *(_QWORD *)(*((_QWORD *)v5 + 5) + 336LL);
  if ( !v6 || !*(_DWORD *)(v6 + 176) )
    return 2147549183LL;
  if ( (unsigned int)CMpeg2DemuxMediaSeekingCore::IsSeekingPin(v5, *((struct CMPEG2DemuxOutputPin **)this + 1)) )
    v7 = *(GUID *)v5;
  else
    v7 = TIME_FORMAT_NONE;
  *a2 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800246b0  mov     [rsp+arg_0], rbx
0x1800246b5  push    rdi
0x1800246b6  sub     rsp, 20h
0x1800246ba  mov     rbx, rdx
0x1800246bd  mov     rdx, rcx
0x1800246c0  test    rbx, rbx
0x1800246c3  jnz     short loc_1800246CC
0x1800246c5  mov     eax, 80004003h
0x1800246ca  jmp     short loc_180024712
0x1800246cc  mov     rdi, [rcx+30h]
0x1800246d0  mov     rax, [rdi+28h]
0x1800246d4  mov     rcx, [rax+150h]
0x1800246db  test    rcx, rcx
0x1800246de  jz      short loc_18002470D
0x1800246e0  cmp     dword ptr [rcx+0B0h], 0
0x1800246e7  jz      short loc_18002470D
0x1800246e9  mov     rdx, [rdx+8]; struct CMPEG2DemuxOutputPin *
0x1800246ed  mov     rcx, rdi; this
0x1800246f0  call    ?IsSeekingPin@CMpeg2DemuxMediaSeekingCore@@QEAAHPEAVCMPEG2DemuxOutputPin@@@Z; CMpeg2DemuxMediaSeekingCore::IsSeekingPin(CMPEG2DemuxOutputPin *)
0x1800246f5  test    eax, eax
0x1800246f7  jz      short loc_1800246FE
0x1800246f9  movups  xmm0, xmmword ptr [rdi]
0x1800246fc  jmp     short loc_180024705
0x1800246fe  movups  xmm0, xmmword ptr cs:TIME_FORMAT_NONE.Data1
0x180024705  movdqu  xmmword ptr [rbx], xmm0
0x180024709  xor     eax, eax
0x18002470b  jmp     short loc_180024712
0x18002470d  mov     eax, 8000FFFFh
0x180024712  mov     rbx, [rsp+28h+arg_0]
0x180024717  add     rsp, 20h
0x18002471b  pop     rdi
0x18002471c  retn
```

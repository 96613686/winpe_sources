# CMpeg2DemuxMediaSeekingCOM::QueryPreferredFormat(_GUID *)

- ea: `0x180024950`
- end: `0x1800249cf`
- name: `?QueryPreferredFormat@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEAU_GUID@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024804`
- `0x180024950`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::QueryPreferredFormat(CMpeg2DemuxMediaSeekingCOM *this, struct _GUID *a2)
{
  __int64 result; // rax
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
  {
    if ( *((_QWORD *)v5 + 2) == -1 )
      return 2147500037LL;
    v7 = TIME_FORMAT_BYTE;
  }
  else
  {
    v7 = TIME_FORMAT_NONE;
  }
  result = 0;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x180024950  mov     [rsp+arg_0], rbx
0x180024955  push    rdi
0x180024956  sub     rsp, 20h
0x18002495a  mov     rbx, rdx
0x18002495d  mov     rdx, rcx
0x180024960  test    rbx, rbx
0x180024963  jnz     short loc_18002496C
0x180024965  mov     eax, 80004003h
0x18002496a  jmp     short loc_1800249C4
0x18002496c  mov     rdi, [rcx+30h]
0x180024970  mov     rax, [rdi+28h]
0x180024974  mov     rcx, [rax+150h]
0x18002497b  test    rcx, rcx
0x18002497e  jz      short loc_1800249BF
0x180024980  cmp     dword ptr [rcx+0B0h], 0
0x180024987  jz      short loc_1800249BF
0x180024989  mov     rdx, [rdx+8]; struct CMPEG2DemuxOutputPin *
0x18002498d  mov     rcx, rdi; this
0x180024990  call    ?IsSeekingPin@CMpeg2DemuxMediaSeekingCore@@QEAAHPEAVCMPEG2DemuxOutputPin@@@Z; CMpeg2DemuxMediaSeekingCore::IsSeekingPin(CMPEG2DemuxOutputPin *)
0x180024995  test    eax, eax
0x180024997  jz      short loc_1800249B0
0x180024999  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18002499e  jz      short loc_1800249A9
0x1800249a0  movups  xmm0, xmmword ptr cs:TIME_FORMAT_BYTE.Data1
0x1800249a7  jmp     short loc_1800249B7
0x1800249a9  mov     eax, 80004005h
0x1800249ae  jmp     short loc_1800249C4
0x1800249b0  movups  xmm0, xmmword ptr cs:TIME_FORMAT_NONE.Data1
0x1800249b7  xor     eax, eax
0x1800249b9  movdqu  xmmword ptr [rbx], xmm0
0x1800249bd  jmp     short loc_1800249C4
0x1800249bf  mov     eax, 8000FFFFh
0x1800249c4  mov     rbx, [rsp+28h+arg_0]
0x1800249c9  add     rsp, 20h
0x1800249cd  pop     rdi
0x1800249ce  retn
```

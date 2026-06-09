# CMpeg2DemuxMediaSeekingCOM::IsFormatSupported(_GUID const *)

- ea: `0x180024730`
- end: `0x1800247fc`
- name: `?IsFormatSupported@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEBU_GUID@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180024730`
- `0x180024804`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::IsFormatSupported(
        CMpeg2DemuxMediaSeekingCOM *this,
        const struct _GUID *a2)
{
  CMpeg2DemuxMediaSeekingCore *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx

  if ( !a2 )
    return 2147500035LL;
  v5 = (CMpeg2DemuxMediaSeekingCore *)*((_QWORD *)this + 6);
  v6 = *(_QWORD *)(*((_QWORD *)v5 + 5) + 336LL);
  if ( !v6 || !*(_DWORD *)(v6 + 176) )
    return 2147549183LL;
  if ( (unsigned int)CMpeg2DemuxMediaSeekingCore::IsSeekingPin(v5, *((struct CMPEG2DemuxOutputPin **)this + 1)) )
    return (*(_QWORD *)&a2->Data1 != *(_QWORD *)&TIME_FORMAT_BYTE.Data1
         || *(_QWORD *)a2->Data4 != *(_QWORD *)TIME_FORMAT_BYTE.Data4
         || *((_QWORD *)v5 + 2) == -1)
        && (*(_QWORD *)&a2->Data1 != *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1
         || *(_QWORD *)a2->Data4 != *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4
         || *((_QWORD *)v5 + 3) == -1);
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4;
  return v7 != 0;
}

```

## disassembly

```asm
0x180024730  mov     [rsp+arg_0], rbx
0x180024735  push    rdi
0x180024736  sub     rsp, 20h
0x18002473a  mov     rbx, rdx
0x18002473d  mov     rdx, rcx
0x180024740  test    rbx, rbx
0x180024743  jnz     short loc_18002474F
0x180024745  mov     eax, 80004003h
0x18002474a  jmp     loc_1800247F1
0x18002474f  mov     rdi, [rcx+30h]
0x180024753  mov     rax, [rdi+28h]
0x180024757  mov     rcx, [rax+150h]
0x18002475e  test    rcx, rcx
0x180024761  jz      loc_1800247EC
0x180024767  cmp     dword ptr [rcx+0B0h], 0
0x18002476e  jz      short loc_1800247EC
0x180024770  mov     rdx, [rdx+8]; struct CMPEG2DemuxOutputPin *
0x180024774  mov     rcx, rdi; this
0x180024777  call    ?IsSeekingPin@CMpeg2DemuxMediaSeekingCore@@QEAAHPEAVCMPEG2DemuxOutputPin@@@Z; CMpeg2DemuxMediaSeekingCore::IsSeekingPin(CMPEG2DemuxOutputPin *)
0x18002477c  test    eax, eax
0x18002477e  jz      short loc_1800247CB
0x180024780  mov     rax, [rbx]
0x180024783  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data1
0x18002478a  jnz     short loc_1800247A0
0x18002478c  mov     rax, [rbx+8]
0x180024790  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data4
0x180024797  jnz     short loc_1800247A0
0x180024799  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18002479e  jnz     short loc_1800247C0
0x1800247a0  mov     rax, [rbx]
0x1800247a3  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x1800247aa  jnz     short loc_1800247C4
0x1800247ac  mov     rax, [rbx+8]
0x1800247b0  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x1800247b7  jnz     short loc_1800247C4
0x1800247b9  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800247be  jz      short loc_1800247C4
0x1800247c0  xor     eax, eax
0x1800247c2  jmp     short loc_1800247F1
0x1800247c4  mov     eax, 1
0x1800247c9  jmp     short loc_1800247F1
0x1800247cb  mov     rcx, [rbx]
0x1800247ce  sub     rcx, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x1800247d5  jnz     short loc_1800247E2
0x1800247d7  mov     rcx, [rbx+8]
0x1800247db  sub     rcx, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x1800247e2  xor     eax, eax
0x1800247e4  test    rcx, rcx
0x1800247e7  setnz   al
0x1800247ea  jmp     short loc_1800247F1
0x1800247ec  mov     eax, 8000FFFFh
0x1800247f1  mov     rbx, [rsp+28h+arg_0]
0x1800247f6  add     rsp, 20h
0x1800247fa  pop     rdi
0x1800247fb  retn
```

# CMpeg2PESStreamParser::ParseCommonPESHeader_(uchar *)

- ea: `0x180029530`
- end: `0x1800295de`
- name: `?ParseCommonPESHeader_@CMpeg2PESStreamParser@@AEAAHPEAE@Z`
- size: `174`
- prototype: `__int64 __fastcall(CMpeg2PESStreamParser *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029f5c`

## callees

- `0x180027674`
- `0x180029530`

## pseudocode

```c
_BOOL8 __fastcall CMpeg2PESStreamParser::ParseCommonPESHeader_(CMpeg2PESStreamParser *this, unsigned __int8 *a2)
{
  int v3; // r9d
  __int64 v4; // rcx
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]

  v3 = *(_DWORD *)a2 & 0xFF00 | a2[2] | ((unsigned __int8)*(_DWORD *)a2 << 16);
  *((_DWORD *)this + 98) = v3;
  *((_DWORD *)this + 99) = a2[3];
  *((_DWORD *)this + 100) = HIBYTE(*((unsigned __int16 *)a2 + 2)) | ((unsigned __int8)*((_WORD *)a2 + 2) << 8);
  if ( v3 != 1 )
  {
    v6 = 0;
    BYTE10(v6) = BYTE2(v3);
    v4 = *((_QWORD *)this + 76) + 8512LL;
    v7 = 0;
    WORD4(v6) = v3;
    BYTE11(v6) = HIBYTE(v3);
    Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(v4, &v6);
  }
  return *((_DWORD *)this + 98) == 1;
}

```

## disassembly

```asm
0x180029530  push    rbx
0x180029532  sub     rsp, 40h
0x180029536  mov     r8d, [rdx]
0x180029539  mov     rbx, rcx
0x18002953c  movzx   eax, byte ptr [rdx+2]
0x180029540  movzx   r9d, r8b
0x180029544  and     r8d, 0FF00h
0x18002954b  shl     r9d, 10h
0x18002954f  or      r9d, eax
0x180029552  or      r9d, r8d
0x180029555  mov     [rcx+188h], r9d
0x18002955c  movzx   eax, byte ptr [rdx+3]
0x180029560  mov     [rcx+18Ch], eax
0x180029566  movzx   ecx, word ptr [rdx+4]
0x18002956a  movzx   eax, cl
0x18002956d  shl     eax, 8
0x180029570  shr     ecx, 8
0x180029573  or      eax, ecx
0x180029575  mov     [rbx+190h], eax
0x18002957b  cmp     r9d, 1
0x18002957f  jz      short loc_1800295CC
0x180029581  mov     ecx, r9d
0x180029584  mov     edx, r9d
0x180029587  shr     ecx, 10h
0x18002958a  xorps   xmm0, xmm0
0x18002958d  movups  [rsp+48h+var_28], xmm0
0x180029592  mov     byte ptr [rsp+48h+var_28+0Ah], cl
0x180029596  mov     eax, r9d
0x180029599  mov     rcx, [rbx+260h]
0x1800295a0  xor     r8d, r8d
0x1800295a3  shr     edx, 8
0x1800295a6  add     rcx, 2140h
0x1800295ad  shr     eax, 18h
0x1800295b0  mov     byte ptr [rsp+48h+var_28+9], dl
0x1800295b4  lea     rdx, [rsp+48h+var_28]
0x1800295b9  mov     [rsp+48h+var_18], r8
0x1800295be  mov     byte ptr [rsp+48h+var_28+8], r9b
0x1800295c3  mov     byte ptr [rsp+48h+var_28+0Bh], al
0x1800295c7  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_MPEG2_ERROR_EVENT@@@Mpeg2DemuxTrace@@QEAAXPEAUEH_MPEG2_ERROR_EVENT@@@Z; Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(EH_MPEG2_ERROR_EVENT *)
0x1800295cc  xor     eax, eax
0x1800295ce  cmp     dword ptr [rbx+188h], 1
0x1800295d5  setz    al
0x1800295d8  add     rsp, 40h
0x1800295dc  pop     rbx
0x1800295dd  retn
```

# GenDefaultAudioMediaType

- ea: `0x18008c580`
- end: `0x18008c703`
- name: `GenDefaultAudioMediaType`
- size: `387`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180090050`
- `0x180090560`

## callees

- `0x18008c580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c5e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c6a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c5e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c6a3`

## pseudocode

```c
__int64 __fastcall GenDefaultAudioMediaType(unsigned __int8 a1, __int64 a2)
{
  unsigned int v2; // ebx
  GUID v5; // xmm1
  char *v6; // rax

  v2 = 0;
  switch ( a1 )
  {
    case 3u:
      *(GUID *)a2 = MEDIATYPE_Audio;
      *(_DWORD *)(a2 + 72) = 40;
      *(GUID *)(a2 + 44) = FORMAT_WaveFormatEx;
      v6 = (char *)CoTaskMemAlloc(0x28u);
      *(_QWORD *)(a2 + 80) = v6;
      if ( v6 )
      {
        *(_OWORD *)v6 = 0;
        *((_OWORD *)v6 + 1) = 0;
        *((_QWORD *)v6 + 4) = 0;
        *((_WORD *)v6 + 6) = 768;
        *((_WORD *)v6 + 8) = 22;
        *(_DWORD *)v6 = 131152;
        goto LABEL_14;
      }
      return (unsigned int)-2147024882;
    case 4u:
      *(GUID *)a2 = MEDIATYPE_Audio;
      v5 = MEDIASUBTYPE_MPEG2_AUDIO;
      goto LABEL_7;
    case 0xFu:
      *(GUID *)a2 = MEDIATYPE_Audio;
      *(GUID *)(a2 + 16) = MFAudioFormat_ADTS;
      *(_DWORD *)(a2 + 72) = 18;
      *(GUID *)(a2 + 44) = FORMAT_WaveFormatEx;
      v6 = (char *)CoTaskMemAlloc(0x12u);
      *(_QWORD *)(a2 + 80) = v6;
      if ( v6 )
      {
        *(_DWORD *)(v6 + 14) = 0;
        *((_WORD *)v6 + 6) = 1;
        *(_DWORD *)v6 = 136704;
        goto LABEL_14;
      }
      return (unsigned int)-2147024882;
  }
  if ( a1 != 129 )
    return 2147942487LL;
  *(GUID *)a2 = MEDIATYPE_Audio;
  v5 = MEDIASUBTYPE_DOLBY_AC3;
LABEL_7:
  *(GUID *)(a2 + 16) = v5;
  *(_DWORD *)(a2 + 72) = 18;
  *(GUID *)(a2 + 44) = FORMAT_WaveFormatEx;
  v6 = (char *)CoTaskMemAlloc(0x12u);
  *(_QWORD *)(a2 + 80) = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  *(_DWORD *)(v6 + 14) = 0;
  *(_DWORD *)v6 = 0x20000;
  *((_WORD *)v6 + 6) = 1;
LABEL_14:
  *((_DWORD *)v6 + 2) = 32000;
  *((_DWORD *)v6 + 1) = 48000;
  return v2;
}

```

## disassembly

```asm
0x18008c580  mov     [rsp+arg_0], rbx
0x18008c585  push    rdi
0x18008c586  sub     rsp, 20h
0x18008c58a  xor     ebx, ebx
0x18008c58c  movzx   r8d, cl
0x18008c590  mov     rdi, rdx
0x18008c593  sub     r8d, 3
0x18008c597  jz      loc_18008C684
0x18008c59d  sub     r8d, 1
0x18008c5a1  jz      loc_18008C66D
0x18008c5a7  sub     r8d, 0Bh
0x18008c5ab  jz      short loc_18008C615
0x18008c5ad  cmp     r8d, 72h ; 'r'
0x18008c5b1  jz      short loc_18008C5BD
0x18008c5b3  mov     eax, 80070057h
0x18008c5b8  jmp     loc_18008C6F7
0x18008c5bd  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18008c5c4  movdqu  xmmword ptr [rdx], xmm0
0x18008c5c8  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_DOLBY_AC3.Data1
0x18008c5cf  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c5d4  mov     ecx, 12h; cb
0x18008c5d9  movups  xmm0, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18008c5e0  mov     [rdx+48h], ecx
0x18008c5e3  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18008c5e8  call    cs:__imp_CoTaskMemAlloc
0x18008c5ef  nop     dword ptr [rax+rax+00h]
0x18008c5f4  mov     [rdi+50h], rax
0x18008c5f8  test    rax, rax
0x18008c5fb  jz      loc_18008C6F0
0x18008c601  mov     [rax+0Eh], ebx
0x18008c604  mov     dword ptr [rax], 20000h
0x18008c60a  mov     word ptr [rax+0Ch], 1
0x18008c610  jmp     loc_18008C6E0
0x18008c615  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18008c61c  mov     ecx, 12h; cb
0x18008c621  movups  xmm1, xmmword ptr cs:MFAudioFormat_ADTS.Data1
0x18008c628  movdqu  xmmword ptr [rdx], xmm0
0x18008c62c  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c631  movups  xmm0, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18008c638  mov     [rdx+48h], ecx
0x18008c63b  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18008c640  call    cs:__imp_CoTaskMemAlloc
0x18008c647  nop     dword ptr [rax+rax+00h]
0x18008c64c  mov     [rdi+50h], rax
0x18008c650  test    rax, rax
0x18008c653  jz      loc_18008C6F0
0x18008c659  mov     [rax+0Eh], ebx
0x18008c65c  mov     edx, 1
0x18008c661  mov     [rax+0Ch], dx
0x18008c665  mov     dword ptr [rax], 21600h
0x18008c66b  jmp     short loc_18008C6E0
0x18008c66d  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18008c674  movdqu  xmmword ptr [rdx], xmm0
0x18008c678  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MPEG2_AUDIO.Data1
0x18008c67f  jmp     loc_18008C5CF
0x18008c684  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18008c68b  mov     ecx, 28h ; '('; cb
0x18008c690  movdqu  xmmword ptr [rdx], xmm0
0x18008c694  movups  xmm1, xmmword ptr cs:FORMAT_WaveFormatEx.Data1
0x18008c69b  mov     [rdx+48h], ecx
0x18008c69e  movdqu  xmmword ptr [rdx+2Ch], xmm1
0x18008c6a3  call    cs:__imp_CoTaskMemAlloc
0x18008c6aa  nop     dword ptr [rax+rax+00h]
0x18008c6af  mov     [rdi+50h], rax
0x18008c6b3  test    rax, rax
0x18008c6b6  jz      short loc_18008C6F0
0x18008c6b8  xor     ecx, ecx
0x18008c6ba  xorps   xmm0, xmm0
0x18008c6bd  movups  xmmword ptr [rax], xmm0
0x18008c6c0  movups  xmmword ptr [rax+10h], xmm0
0x18008c6c4  mov     [rax+20h], rcx
0x18008c6c8  mov     ecx, 300h
0x18008c6cd  mov     [rax+0Ch], cx
0x18008c6d1  mov     ecx, 16h
0x18008c6d6  mov     [rax+10h], cx
0x18008c6da  mov     dword ptr [rax], 20050h
0x18008c6e0  mov     dword ptr [rax+8], 7D00h
0x18008c6e7  mov     dword ptr [rax+4], 0BB80h
0x18008c6ee  jmp     short loc_18008C6F5
0x18008c6f0  mov     ebx, 8007000Eh
0x18008c6f5  mov     eax, ebx
0x18008c6f7  mov     rbx, [rsp+28h+arg_0]
0x18008c6fc  add     rsp, 20h
0x18008c700  pop     rdi
0x18008c701  retn
```

# GenDefaultVideoMediaType

- ea: `0x18008c70c`
- end: `0x18008c8ef`
- name: `GenDefaultVideoMediaType`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180090050`
- `0x180090560`

## callees

- `0x180074a06`
- `0x18008c70c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c89c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008c89c`

## pseudocode

```c
__int64 __fastcall GenDefaultVideoMediaType(unsigned __int8 a1, __int64 a2)
{
  unsigned int v2; // ebx
  _DWORD *v5; // rax
  _DWORD *v6; // rsi
  SIZE_T v7; // rbp
  GUID v8; // xmm0
  _DWORD *v9; // rax
  _DWORD *v10; // rsi
  _DWORD *v11; // rax
  _DWORD *v12; // rsi
  int v13; // eax

  v2 = 0;
  switch ( a1 )
  {
    case 1u:
      v7 = 104;
      *(GUID *)a2 = MEDIATYPE_Video;
      *(GUID *)(a2 + 16) = MEDIASUBTYPE_MPEG1Video;
      v8 = FORMAT_MPEGVideo;
LABEL_13:
      *(_DWORD *)(a2 + 72) = v7;
      *(GUID *)(a2 + 44) = v8;
      v11 = CoTaskMemAlloc(v7);
      *(_QWORD *)(a2 + 80) = v11;
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, v7);
        v13 = *(_DWORD *)(a2 + 16);
        v12[14] = 480;
        v12[13] = 720;
        v12[12] = 40;
        v12[16] = v13;
        return v2;
      }
      return (unsigned int)-2147024882;
    case 2u:
      goto LABEL_10;
    case 0x1Bu:
      v7 = 88;
      *(GUID *)a2 = MEDIATYPE_Video;
      *(GUID *)(a2 + 16) = MEDIASUBTYPE_H264;
      v8 = FORMAT_VideoInfo;
      goto LABEL_13;
    case 0x80u:
LABEL_10:
      *(GUID *)a2 = MEDIATYPE_Video;
      *(GUID *)(a2 + 16) = MEDIASUBTYPE_MPEG2_VIDEO;
      *(_DWORD *)(a2 + 72) = 136;
      *(GUID *)(a2 + 44) = FORMAT_MPEG2Video;
      v9 = CoTaskMemAlloc(0x88u);
      *(_QWORD *)(a2 + 80) = v9;
      v10 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, 0x88u);
        v10[22] = *(_DWORD *)(a2 + 16);
        v10[18] = 40;
        v10[19] = 720;
        v10[20] = 480;
        return v2;
      }
      return (unsigned int)-2147024882;
  }
  if ( a1 != 234 )
    return 2147942487LL;
  *(GUID *)a2 = MEDIATYPE_Video;
  *(GUID *)(a2 + 16) = MFVideoFormat_WVC1;
  *(_DWORD *)(a2 + 72) = 89;
  *(GUID *)(a2 + 44) = FORMAT_VideoInfo;
  v5 = CoTaskMemAlloc(0x59u);
  *(_QWORD *)(a2 + 80) = v5;
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  memset_0(v5, 0, 0x58u);
  v6[16] = *(_DWORD *)(a2 + 16);
  v6[12] = 40;
  v6[13] = 720;
  v6[14] = 480;
  *(_BYTE *)(*(_QWORD *)(a2 + 80) + 88LL) = 1;
  return v2;
}

```

## disassembly

```asm
0x18008c70c  push    rbx
0x18008c70e  push    rbp
0x18008c70f  push    rsi
0x18008c710  push    rdi
0x18008c711  sub     rsp, 28h
0x18008c715  xor     ebx, ebx
0x18008c717  movzx   r8d, cl
0x18008c71b  mov     rdi, rdx
0x18008c71e  sub     r8d, 1
0x18008c722  jz      loc_18008C86E
0x18008c728  sub     r8d, 1
0x18008c72c  jz      loc_18008C7FB
0x18008c732  sub     r8d, 19h
0x18008c736  jz      loc_18008C7D3
0x18008c73c  sub     r8d, 65h ; 'e'
0x18008c740  jz      loc_18008C7FB
0x18008c746  cmp     r8d, 6Ah ; 'j'
0x18008c74a  jz      short loc_18008C756
0x18008c74c  mov     eax, 80070057h
0x18008c751  jmp     loc_18008C8E5
0x18008c756  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18008c75d  mov     ecx, 59h ; 'Y'; cb
0x18008c762  movups  xmm1, xmmword ptr cs:MFVideoFormat_WVC1.Data1
0x18008c769  movdqu  xmmword ptr [rdx], xmm0
0x18008c76d  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c772  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x18008c779  mov     [rdx+48h], ecx
0x18008c77c  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18008c781  call    cs:__imp_CoTaskMemAlloc
0x18008c788  nop     dword ptr [rax+rax+00h]
0x18008c78d  mov     [rdi+50h], rax
0x18008c791  mov     rsi, rax
0x18008c794  test    rax, rax
0x18008c797  jz      loc_18008C8DE
0x18008c79d  xor     edx, edx; Val
0x18008c79f  mov     rcx, rax; void *
0x18008c7a2  lea     r8d, [rdx+58h]; Size
0x18008c7a6  call    memset_0
0x18008c7ab  mov     eax, [rdi+10h]
0x18008c7ae  mov     [rsi+40h], eax
0x18008c7b1  mov     dword ptr [rsi+30h], 28h ; '('
0x18008c7b8  mov     dword ptr [rsi+34h], 2D0h
0x18008c7bf  mov     dword ptr [rsi+38h], 1E0h
0x18008c7c6  mov     rax, [rdi+50h]
0x18008c7ca  mov     byte ptr [rax+58h], 1
0x18008c7ce  jmp     loc_18008C8E3
0x18008c7d3  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18008c7da  mov     ebp, 58h ; 'X'
0x18008c7df  movdqu  xmmword ptr [rdx], xmm0
0x18008c7e3  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_H264.Data1
0x18008c7ea  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c7ef  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x18008c7f6  jmp     loc_18008C891
0x18008c7fb  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18008c802  mov     ebp, 88h
0x18008c807  mov     ecx, ebp; cb
0x18008c809  movdqu  xmmword ptr [rdx], xmm0
0x18008c80d  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MPEG2_VIDEO.Data1
0x18008c814  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c819  movups  xmm0, xmmword ptr cs:FORMAT_MPEG2Video.Data1
0x18008c820  mov     [rdx+48h], ebp
0x18008c823  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18008c828  call    cs:__imp_CoTaskMemAlloc
0x18008c82f  nop     dword ptr [rax+rax+00h]
0x18008c834  mov     [rdi+50h], rax
0x18008c838  mov     rsi, rax
0x18008c83b  test    rax, rax
0x18008c83e  jz      loc_18008C8DE
0x18008c844  mov     r8d, ebp; Size
0x18008c847  xor     edx, edx; Val
0x18008c849  mov     rcx, rax; void *
0x18008c84c  call    memset_0
0x18008c851  mov     eax, [rdi+10h]
0x18008c854  mov     [rsi+58h], eax
0x18008c857  mov     dword ptr [rsi+48h], 28h ; '('
0x18008c85e  mov     dword ptr [rsi+4Ch], 2D0h
0x18008c865  mov     dword ptr [rsi+50h], 1E0h
0x18008c86c  jmp     short loc_18008C8E3
0x18008c86e  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18008c875  mov     ebp, 68h ; 'h'
0x18008c87a  movdqu  xmmword ptr [rdx], xmm0
0x18008c87e  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MPEG1Video.Data1
0x18008c885  movdqu  xmmword ptr [rdx+10h], xmm1
0x18008c88a  movups  xmm0, xmmword ptr cs:FORMAT_MPEGVideo.Data1
0x18008c891  mov     rcx, rbp; cb
0x18008c894  mov     [rdx+48h], ebp
0x18008c897  movdqu  xmmword ptr [rdx+2Ch], xmm0
0x18008c89c  call    cs:__imp_CoTaskMemAlloc
0x18008c8a3  nop     dword ptr [rax+rax+00h]
0x18008c8a8  mov     [rdi+50h], rax
0x18008c8ac  mov     rsi, rax
0x18008c8af  test    rax, rax
0x18008c8b2  jz      short loc_18008C8DE
0x18008c8b4  mov     r8, rbp; Size
0x18008c8b7  xor     edx, edx; Val
0x18008c8b9  mov     rcx, rax; void *
0x18008c8bc  call    memset_0
0x18008c8c1  mov     eax, [rdi+10h]
0x18008c8c4  mov     dword ptr [rsi+38h], 1E0h
0x18008c8cb  mov     dword ptr [rsi+34h], 2D0h
0x18008c8d2  mov     dword ptr [rsi+30h], 28h ; '('
0x18008c8d9  mov     [rsi+40h], eax
0x18008c8dc  jmp     short loc_18008C8E3
0x18008c8de  mov     ebx, 8007000Eh
0x18008c8e3  mov     eax, ebx
0x18008c8e5  add     rsp, 28h
0x18008c8e9  pop     rdi
0x18008c8ea  pop     rsi
0x18008c8eb  pop     rbp
0x18008c8ec  pop     rbx
0x18008c8ed  retn
```

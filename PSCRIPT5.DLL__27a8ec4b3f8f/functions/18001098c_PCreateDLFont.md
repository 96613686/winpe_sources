# PCreateDLFont

- ea: `0x18001098c`
- end: `0x180010cf8`
- name: `PCreateDLFont`
- size: `876`
- prototype: `unsigned int *__fastcall(__int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bdac`
- `0x18000f2e4`

## callees

- `0x18001071c`
- `0x18001098c`
- `0x180010e58`
- `0x180011674`
- `0x1800116f8`
- `0x1800118c4`
- `0x18002a64c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180010c82`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180010c82`
- `KERNEL32!LocalFree` at `0x180010b64`
- `KERNEL32!LocalFree` at `0x180010cc4`
- `KERNEL32!LocalFree` at `0x180010cd3`
- `KERNEL32!LocalFree` at `0x180010b64`
- `KERNEL32!LocalFree` at `0x180010cc4`
- `KERNEL32!LocalFree` at `0x180010cd3`
- `KERNEL32!LocalAlloc` at `0x1800109e9`
- `KERNEL32!LocalAlloc` at `0x180010b1e`
- `KERNEL32!LocalAlloc` at `0x180010c5a`
- `KERNEL32!LocalAlloc` at `0x1800109e9`
- `KERNEL32!LocalAlloc` at `0x180010b1e`
- `KERNEL32!LocalAlloc` at `0x180010c5a`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010aed`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010b3f`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010aed`
- `GDI32!FONTOBJ_cGetAllGlyphHandles` at `0x180010b3f`
- `GDI32!FONTOBJ_pifi` at `0x1800109c0`
- `GDI32!FONTOBJ_pifi` at `0x1800109c0`

## pseudocode

```c
char *__fastcall PCreateDLFont(__int64 a1, int a2, int a3)
{
  IFIMETRICS *v6; // rsi
  IFIMETRICS *v7; // rax
  char *v8; // rax
  int v9; // edx
  char *v10; // rbx
  int v11; // r14d
  int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  ULONG AllGlyphHandles; // eax
  ULONG v16; // r14d
  HGLYPH *v17; // rax
  HGLYPH *v18; // r15
  __int64 v19; // rax
  HGLYPH v20; // edx
  WCHAR *v21; // rdx
  __int64 v22; // rsi
  __int64 v23; // rax
  _BYTE *v24; // rdx
  _BYTE *v25; // rcx
  _BYTE *v26; // rax
  unsigned int v27; // ecx
  unsigned int v28; // eax
  HLOCAL v29; // rax
  char *v30; // rax
  __int64 v31; // r8
  void *v32; // rcx

  if ( !a3 )
    return 0;
  v6 = *(IFIMETRICS **)(a1 + 3544);
  if ( !v6 )
  {
    v7 = FONTOBJ_pifi(*(FONTOBJ **)(a1 + 3536));
    *(_QWORD *)(a1 + 3544) = v7;
    v6 = v7;
    if ( !v7 )
      return 0;
  }
  v8 = (char *)LocalAlloc(0x40u, 0x1A8u);
  v10 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 1) = a1;
    *((_DWORD *)v8 + 49) = a3;
    v11 = 1;
    *((_DWORD *)v8 + 48) = 0;
    v12 = 0;
    if ( (*(_DWORD *)(a1 + 3564) & 0x4000) != 0 )
    {
      *((_DWORD *)v10 + 48) = 8;
      v12 = 8;
    }
    if ( a2 )
      *((_DWORD *)v10 + 48) = v12 | 0x10;
    *((_QWORD *)v10 + 51) = 0;
    v13 = PGetFontFile(a1, v9, (__int64)v10);
    *((_QWORD *)v10 + 50) = v13;
    if ( !v13 && (unsigned int)(a3 - 6) <= 4 )
      v11 = 0;
    *((_QWORD *)v10 + 22) = ULGetUniqueId(a1, *((_DWORD *)v10 + 49));
    *((_QWORD *)v10 + 23) = 0;
    if ( a3 != 7 && a3 != 10
      || (v14 = ULGetFontFileClassUniqueID(a1, *((_QWORD *)v10 + 50)), (*((_QWORD *)v10 + 23) = v14) == 0) )
    {
      *((_QWORD *)v10 + 23) = *((_QWORD *)v10 + 22);
    }
    if ( v11 )
    {
      *((_DWORD *)v10 + 97) = 65537;
      *((_QWORD *)v10 + 47) = 0;
      AllGlyphHandles = FONTOBJ_cGetAllGlyphHandles(*(FONTOBJ **)(a1 + 3536), 0);
      v16 = AllGlyphHandles;
      *((_DWORD *)v10 + 92) = AllGlyphHandles;
      if ( v6->cjIfiExtra <= 8 || !v6[1].dpwszFamilyName )
      {
        v17 = (HGLYPH *)LocalAlloc(0x40u, 4LL * AllGlyphHandles);
        v18 = v17;
        if ( v17 )
        {
          v16 = 0;
          LODWORD(v19) = FONTOBJ_cGetAllGlyphHandles(*(FONTOBJ **)(a1 + 3536), v17);
          while ( (_DWORD)v19 )
          {
            v19 = (unsigned int)(v19 - 1);
            v20 = v18[v19];
            if ( v20 <= v16 )
              v20 = v16;
            v16 = v20;
          }
          LocalFree(v18);
        }
        *((_DWORD *)v10 + 92) = v16 + 1;
      }
      v21 = (WCHAR *)((char *)v6 + v6->dpwszFaceName);
      v22 = 32;
      VCopyUnicodeStringToAnsi(v10 + 16, v21, 32);
      if ( v10[16] == 64 )
      {
        v23 = 2147483646;
        v24 = v10 + 17;
        v25 = v10 + 16;
        do
        {
          if ( !v23 )
            break;
          if ( !*v24 )
            break;
          *v25++ = *v24++;
          --v23;
          --v22;
        }
        while ( v22 );
        v26 = v25 - 1;
        if ( v22 )
          v26 = v25;
        *v26 = 0;
      }
      if ( (unsigned int)(*((_DWORD *)v10 + 49) - 8) <= 2 )
      {
        v30 = strchr(v10 + 16, 95);
        if ( v30 )
          *v30 = 0;
        VGetPSName(a1, v10 + 48, v31, 1);
      }
      else
      {
        GeneratePSName((__int64)(v10 + 48));
        if ( !a2 && a3 != 7 && a3 != 10 )
        {
          v27 = *((_DWORD *)v10 + 92);
          v28 = 512;
          if ( v27 > 0x7D0 )
            v28 = 0x3FFF;
          if ( v27 < v28 )
            v28 = *((_DWORD *)v10 + 92);
          *((_DWORD *)v10 + 96) = v28;
          v29 = LocalAlloc(0x40u, 2LL * v28);
          *((_QWORD *)v10 + 47) = v29;
          if ( !v29 )
            *((_DWORD *)v10 + 96) = 0;
        }
      }
      *(_QWORD *)v10 = *(_QWORD *)(a1 + 3512);
      *(_QWORD *)(a1 + 3512) = v10;
    }
    else
    {
      v32 = (void *)*((_QWORD *)v10 + 47);
      if ( v32 )
        LocalFree(v32);
      LocalFree(v10);
      return 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18001098c  push    rbx
0x18001098e  push    rbp
0x18001098f  push    rsi
0x180010990  push    rdi
0x180010991  push    r12
0x180010993  push    r14
0x180010995  push    r15
0x180010997  sub     rsp, 40h
0x18001099b  mov     ebp, r8d
0x18001099e  mov     r12d, edx
0x1800109a1  mov     rdi, rcx
0x1800109a4  test    r8d, r8d
0x1800109a7  jz      loc_180010CE6
0x1800109ad  mov     rsi, [rcx+0DD8h]
0x1800109b4  test    rsi, rsi
0x1800109b7  jnz     short loc_1800109DF
0x1800109b9  mov     rcx, [rcx+0DD0h]; pfo
0x1800109c0  call    cs:__imp_FONTOBJ_pifi
0x1800109c7  nop     dword ptr [rax+rax+00h]
0x1800109cc  mov     [rdi+0DD8h], rax
0x1800109d3  mov     rsi, rax
0x1800109d6  test    rax, rax
0x1800109d9  jz      loc_180010CE6
0x1800109df  mov     edx, 1A8h; uBytes
0x1800109e4  mov     ecx, 40h ; '@'; uFlags
0x1800109e9  call    cs:__imp_LocalAlloc
0x1800109f0  nop     dword ptr [rax+rax+00h]
0x1800109f5  mov     rbx, rax
0x1800109f8  test    rax, rax
0x1800109fb  jz      loc_180010CE1
0x180010a01  mov     [rax+8], rdi
0x180010a05  mov     r15d, 1
0x180010a0b  mov     [rax+0C4h], ebp
0x180010a11  mov     r14d, r15d
0x180010a14  mov     dword ptr [rax+0C0h], 0
0x180010a1e  xor     eax, eax
0x180010a20  test    dword ptr [rdi+0DECh], 4000h
0x180010a2a  lea     ecx, [rax+8]
0x180010a2d  jz      short loc_180010A37
0x180010a2f  mov     [rbx+0C0h], ecx
0x180010a35  mov     eax, ecx
0x180010a37  test    r12d, r12d
0x180010a3a  jz      short loc_180010A45
0x180010a3c  or      eax, 10h
0x180010a3f  mov     [rbx+0C0h], eax
0x180010a45  mov     r8, rbx
0x180010a48  mov     qword ptr [rbx+198h], 0
0x180010a53  mov     rcx, rdi
0x180010a56  call    PGetFontFile
0x180010a5b  mov     [rbx+190h], rax
0x180010a62  test    rax, rax
0x180010a65  jnz     short loc_180010A71
0x180010a67  lea     ecx, [rbp-6]
0x180010a6a  cmp     ecx, 4
0x180010a6d  cmovbe  r14d, eax
0x180010a71  mov     edx, [rbx+0C4h]
0x180010a77  mov     rcx, rdi
0x180010a7a  call    ULGetUniqueId
0x180010a7f  mov     [rbx+0B0h], rax
0x180010a86  mov     qword ptr [rbx+0B8h], 0
0x180010a91  cmp     ebp, 7
0x180010a94  jz      short loc_180010A9B
0x180010a96  cmp     ebp, 0Ah
0x180010a99  jnz     short loc_180010AB8
0x180010a9b  mov     rdx, [rbx+190h]
0x180010aa2  mov     rcx, rdi
0x180010aa5  call    ULGetFontFileClassUniqueID
0x180010aaa  mov     eax, eax
0x180010aac  mov     [rbx+0B8h], rax
0x180010ab3  test    rax, rax
0x180010ab6  jnz     short loc_180010AC6
0x180010ab8  mov     rax, [rbx+0B0h]
0x180010abf  mov     [rbx+0B8h], rax
0x180010ac6  test    r14d, r14d
0x180010ac9  jz      loc_180010CB8
0x180010acf  mov     dword ptr [rbx+184h], 10001h
0x180010ad9  xor     edx, edx; phg
0x180010adb  mov     qword ptr [rbx+178h], 0
0x180010ae6  mov     rcx, [rdi+0DD0h]; pfo
0x180010aed  call    cs:__imp_FONTOBJ_cGetAllGlyphHandles
0x180010af4  nop     dword ptr [rax+rax+00h]
0x180010af9  mov     r14d, eax
0x180010afc  mov     [rbx+170h], r14d
0x180010b03  cmp     dword ptr [rsi+4], 8
0x180010b07  jbe     short loc_180010B12
0x180010b09  cmp     dword ptr [rsi+0C8h], 0
0x180010b10  jnz     short loc_180010B80
0x180010b12  mov     rdx, r14
0x180010b15  mov     ecx, 40h ; '@'; uFlags
0x180010b1a  shl     rdx, 2; uBytes
0x180010b1e  call    cs:__imp_LocalAlloc
0x180010b25  nop     dword ptr [rax+rax+00h]
0x180010b2a  mov     r15, rax
0x180010b2d  test    rax, rax
0x180010b30  jz      short loc_180010B70
0x180010b32  mov     rcx, [rdi+0DD0h]; pfo
0x180010b39  xor     r14d, r14d
0x180010b3c  mov     rdx, rax; phg
0x180010b3f  call    cs:__imp_FONTOBJ_cGetAllGlyphHandles
0x180010b46  nop     dword ptr [rax+rax+00h]
0x180010b4b  jmp     short loc_180010B5D
0x180010b4d  dec     eax
0x180010b4f  mov     edx, [r15+rax*4]
0x180010b53  cmp     edx, r14d
0x180010b56  cmovbe  edx, r14d
0x180010b5a  mov     r14d, edx
0x180010b5d  test    eax, eax
0x180010b5f  jnz     short loc_180010B4D
0x180010b61  mov     rcx, r15; hMem
0x180010b64  call    cs:__imp_LocalFree
0x180010b6b  nop     dword ptr [rax+rax+00h]
0x180010b70  lea     eax, [r14+1]
0x180010b74  mov     r15d, 1
0x180010b7a  mov     [rbx+170h], eax
0x180010b80  movsxd  rdx, dword ptr [rsi+10h]
0x180010b84  lea     r14, [rbx+10h]
0x180010b88  add     rdx, rsi
0x180010b8b  mov     rcx, r14
0x180010b8e  mov     esi, 20h ; ' '
0x180010b93  mov     r8d, esi
0x180010b96  call    VCopyUnicodeStringToAnsi
0x180010b9b  cmp     byte ptr [r14], 40h ; '@'
0x180010b9f  jnz     short loc_180010BD9
0x180010ba1  mov     eax, 7FFFFFFEh
0x180010ba6  lea     rdx, [r14+1]
0x180010baa  mov     rcx, r14
0x180010bad  test    rax, rax
0x180010bb0  jz      short loc_180010BCB
0x180010bb2  mov     r8b, [rdx]
0x180010bb5  test    r8b, r8b
0x180010bb8  jz      short loc_180010BCB
0x180010bba  mov     [rcx], r8b
0x180010bbd  add     rdx, r15
0x180010bc0  add     rcx, r15
0x180010bc3  sub     rax, r15
0x180010bc6  sub     rsi, r15
0x180010bc9  jnz     short loc_180010BAD
0x180010bcb  test    rsi, rsi
0x180010bce  lea     rax, [rcx-1]
0x180010bd2  cmovnz  rax, rcx
0x180010bd6  mov     byte ptr [rax], 0
0x180010bd9  mov     r8d, [rbx+0C4h]
0x180010be0  lea     eax, [r8-8]
0x180010be4  cmp     eax, 2
0x180010be7  jbe     loc_180010C7A
0x180010bed  mov     rax, [rdi+0DD0h]
0x180010bf4  lea     rcx, [rbx+30h]
0x180010bf8  mov     r9, [rbx+0B0h]
0x180010bff  mov     [rsp+78h+var_48], r12d
0x180010c04  mov     [rsp+78h+var_50], rax
0x180010c09  mov     rax, [rbx+0B8h]
0x180010c10  mov     [rsp+78h+var_58], rax
0x180010c15  call    GeneratePSName
0x180010c1a  test    r12d, r12d
0x180010c1d  jnz     loc_180010CA5
0x180010c23  cmp     ebp, 7
0x180010c26  jz      short loc_180010CA5
0x180010c28  cmp     ebp, 0Ah
0x180010c2b  jz      short loc_180010CA5
0x180010c2d  mov     ecx, [rbx+170h]
0x180010c33  mov     eax, 200h
0x180010c38  cmp     ecx, 7D0h
0x180010c3e  jbe     short loc_180010C45
0x180010c40  mov     eax, 3FFFh
0x180010c45  cmp     ecx, eax
0x180010c47  cmovb   eax, ecx
0x180010c4a  mov     ecx, 40h ; '@'; uFlags
0x180010c4f  mov     edx, eax
0x180010c51  add     rdx, rdx; uBytes
0x180010c54  mov     [rbx+180h], eax
0x180010c5a  call    cs:__imp_LocalAlloc
0x180010c61  nop     dword ptr [rax+rax+00h]
0x180010c66  mov     [rbx+178h], rax
0x180010c6d  test    rax, rax
0x180010c70  jnz     short loc_180010CA5
0x180010c72  mov     [rbx+180h], eax
0x180010c78  jmp     short loc_180010CA5
0x180010c7a  mov     edx, 5Fh ; '_'; Val
0x180010c7f  mov     rcx, r14; Str
0x180010c82  call    cs:__imp_strchr
0x180010c89  nop     dword ptr [rax+rax+00h]
0x180010c8e  test    rax, rax
0x180010c91  jz      short loc_180010C96
0x180010c93  mov     byte ptr [rax], 0
0x180010c96  lea     rdx, [rbx+30h]
0x180010c9a  mov     r9d, r15d
0x180010c9d  mov     rcx, rdi
0x180010ca0  call    VGetPSName
0x180010ca5  mov     rax, [rdi+0DB8h]
0x180010cac  mov     [rbx], rax
0x180010caf  mov     [rdi+0DB8h], rbx
0x180010cb6  jmp     short loc_180010CE1
0x180010cb8  mov     rcx, [rbx+178h]; hMem
0x180010cbf  test    rcx, rcx
0x180010cc2  jz      short loc_180010CD0
0x180010cc4  call    cs:__imp_LocalFree
0x180010ccb  nop     dword ptr [rax+rax+00h]
0x180010cd0  mov     rcx, rbx; hMem
0x180010cd3  call    cs:__imp_LocalFree
0x180010cda  nop     dword ptr [rax+rax+00h]
0x180010cdf  xor     ebx, ebx
0x180010ce1  mov     rax, rbx
0x180010ce4  jmp     short loc_180010CE8
0x180010ce6  xor     eax, eax
0x180010ce8  add     rsp, 40h
0x180010cec  pop     r15
0x180010cee  pop     r14
0x180010cf0  pop     r12
0x180010cf2  pop     rdi
0x180010cf3  pop     rsi
0x180010cf4  pop     rbp
0x180010cf5  pop     rbx
0x180010cf6  retn
```

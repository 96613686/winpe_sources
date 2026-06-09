# GpMetafile::Clone(void)

- ea: `0x180119ae0`
- end: `0x180119c90`
- name: `?Clone@GpMetafile@@UEBAPEAVGpImage@@XZ`
- size: `432`
- prototype: `struct GpImage *__fastcall(GpMetafile *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1800067bc`
- `0x180099a84`
- `0x18009a6dc`
- `0x1800fe680`
- `0x1800fefe0`
- `0x18011995c`
- `0x180119ae0`
- `0x180169010`

## import_xrefs

- `GDI32!CopyMetaFileA` at `0x180119b87`
- `GDI32!CopyMetaFileA` at `0x180119b87`
- `GDI32!CopyEnhMetaFileA` at `0x180119b20`
- `GDI32!CopyEnhMetaFileA` at `0x180119b20`
- `GDI32!DeleteMetaFile` at `0x180119c56`
- `GDI32!DeleteMetaFile` at `0x180119c56`
- `GDI32!DeleteEnhMetaFile` at `0x180119b7c`
- `GDI32!DeleteEnhMetaFile` at `0x180119b7c`

## pseudocode

```c
struct GpImage *__fastcall GpMetafile::Clone(GpMetafile *this)
{
  GpMetafile *v1; // rbx
  HENHMETAFILE v3; // rcx
  HENHMETAFILE v4; // rdi
  GpMetafile *v5; // rax
  GpMetafile *v6; // rax
  HMETAFILE v7; // rsi
  __m128 v8; // xmm1
  __int16 v9; // ax
  int v10; // eax
  GpMetafile *v11; // rax
  GpMetafile *v12; // rax
  __int64 v13; // rax
  int v15; // [rsp+30h] [rbp-28h] BYREF
  __int16 v16; // [rsp+34h] [rbp-24h]
  __int16 v17; // [rsp+36h] [rbp-22h]
  __int16 v18; // [rsp+38h] [rbp-20h]
  __int16 v19; // [rsp+3Ah] [rbp-1Eh]
  __int16 v20; // [rsp+3Ch] [rbp-1Ch]
  __int16 v21; // [rsp+3Eh] [rbp-1Ah]
  int v22; // [rsp+40h] [rbp-18h]
  __int16 v23; // [rsp+44h] [rbp-14h]

  v1 = 0;
  if ( (unsigned int)(*((_DWORD *)this + 44) - 3) <= 1 )
  {
    v3 = (HENHMETAFILE)*((_QWORD *)this + 23);
    if ( *((int *)this + 8) < 3 )
    {
      v7 = CopyMetaFileA((HMETAFILE)v3, 0);
      if ( v7 )
      {
        v8 = (__m128)*((unsigned int *)this + 12);
        v8.m128_f32[0] = v8.m128_f32[0] + 0.5;
        v23 = 0;
        v16 = 0;
        v17 = *((_WORD *)this + 28);
        v19 = *((_WORD *)this + 32) + v17;
        v18 = *((_WORD *)this + 30);
        v9 = *((_WORD *)this + 34) + v18;
        v15 = -1698247209;
        v20 = v9;
        v10 = Feature_GdiPlusOptimizations_Misc_IsEnabled
            ? (int)_mm_round_ss(v8, v8, 9).m128_f32[0]
            : (int)floor(v8.m128_f32[0]);
        v21 = v10;
        v22 = 0;
        v23 = GetWmfPlaceableCheckSum((const struct WmfPlaceableFileHeader *)&v15);
        v11 = (GpMetafile *)GpMallocEx(256, 0);
        if ( v11 )
        {
          v12 = GpMetafile::GpMetafile(v11, v7, (const struct WmfPlaceableFileHeader *)&v15, 1, 0);
          v1 = v12;
          if ( v12 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v12 + 8LL))(v12) )
            {
              DeleteMetaFile(v7);
              goto LABEL_16;
            }
          }
        }
      }
    }
    else
    {
      v4 = CopyEnhMetaFileA(v3, 0);
      if ( v4 )
      {
        v5 = (GpMetafile *)GpMallocEx(256, 0);
        if ( v5 )
        {
          v6 = GpMetafile::GpMetafile(v5, v4, 1);
          v1 = v6;
          if ( v6 )
          {
            if ( !(*(unsigned int (__fastcall **)(GpMetafile *))(*(_QWORD *)v6 + 8LL))(v6) )
            {
              DeleteEnhMetaFile(v4);
LABEL_16:
              v13 = *(_QWORD *)v1;
              *((_QWORD *)v1 + 23) = 0;
              (*(void (__fastcall **)(GpMetafile *))(v13 + 56))(v1);
              return 0;
            }
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180119ae0  push    rbp
0x180119ae2  push    rbx
0x180119ae3  push    rsi
0x180119ae4  push    rdi
0x180119ae5  mov     rbp, rsp
0x180119ae8  sub     rsp, 58h
0x180119aec  mov     rax, cs:__security_cookie
0x180119af3  xor     rax, rsp
0x180119af6  mov     [rbp+var_10], rax
0x180119afa  mov     eax, [rcx+0B0h]
0x180119b00  xor     ebx, ebx
0x180119b02  sub     eax, 3
0x180119b05  mov     rdi, rcx
0x180119b08  cmp     eax, 1
0x180119b0b  ja      loc_180119C78
0x180119b11  mov     rcx, [rcx+0B8h]; HMETAFILE
0x180119b18  xor     edx, edx; LPCSTR
0x180119b1a  cmp     dword ptr [rdi+20h], 3
0x180119b1e  jl      short loc_180119B87
0x180119b20  call    cs:__imp_CopyEnhMetaFileA
0x180119b26  mov     rdi, rax
0x180119b29  test    rax, rax
0x180119b2c  jz      loc_180119C78
0x180119b32  xor     edx, edx
0x180119b34  mov     ecx, 100h
0x180119b39  call    GpMallocEx
0x180119b3e  test    rax, rax
0x180119b41  jz      loc_180119C78
0x180119b47  lea     r8d, [rbx+1]; int
0x180119b4b  mov     rdx, rdi; HENHMETAFILE
0x180119b4e  mov     rcx, rax; this
0x180119b51  call    ??0GpMetafile@@QEAA@PEAUHENHMETAFILE__@@H@Z; GpMetafile::GpMetafile(HENHMETAFILE__ *,int)
0x180119b56  mov     rbx, rax
0x180119b59  test    rax, rax
0x180119b5c  jz      loc_180119C78
0x180119b62  mov     rax, [rax]
0x180119b65  mov     rcx, rbx
0x180119b68  mov     rax, [rax+8]
0x180119b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119b71  test    eax, eax
0x180119b73  jnz     loc_180119C78
0x180119b79  mov     rcx, rdi; hmf
0x180119b7c  call    cs:__imp_DeleteEnhMetaFile
0x180119b82  jmp     loc_180119C5C
0x180119b87  call    cs:__imp_CopyMetaFileA
0x180119b8d  mov     rsi, rax
0x180119b90  test    rax, rax
0x180119b93  jz      loc_180119C78
0x180119b99  movss   xmm1, dword ptr [rdi+30h]
0x180119b9e  xor     eax, eax
0x180119ba0  addss   xmm1, cs:__real@3f000000
0x180119ba8  mov     [rbp+var_14], ax
0x180119bac  mov     [rbp+var_24], ax
0x180119bb0  movzx   eax, word ptr [rdi+38h]
0x180119bb4  mov     [rbp+var_22], ax
0x180119bb8  add     ax, [rdi+40h]
0x180119bbc  mov     [rbp+var_1E], ax
0x180119bc0  movzx   eax, word ptr [rdi+3Ch]
0x180119bc4  mov     [rbp+var_20], ax
0x180119bc8  add     ax, [rdi+44h]
0x180119bcc  cmp     cs:?Feature_GdiPlusOptimizations_Misc_IsEnabled@@3_NA, bl; bool Feature_GdiPlusOptimizations_Misc_IsEnabled
0x180119bd2  mov     [rbp+var_28], 9AC6CDD7h
0x180119bd9  mov     [rbp+var_1C], ax
0x180119bdd  jz      short loc_180119BEE
0x180119bdf  movaps  xmm0, xmm1
0x180119be2  roundss xmm0, xmm0, 9
0x180119be8  cvttss2si eax, xmm0
0x180119bec  jmp     short loc_180119BFA
0x180119bee  cvtps2pd xmm0, xmm1; X
0x180119bf1  call    floor
0x180119bf6  cvttsd2si eax, xmm0
0x180119bfa  lea     rcx, [rbp+var_28]; struct WmfPlaceableFileHeader *
0x180119bfe  mov     [rbp+var_1A], ax
0x180119c02  mov     [rbp+var_18], ebx
0x180119c05  call    ?GetWmfPlaceableCheckSum@@YAFPEBUWmfPlaceableFileHeader@@@Z; GetWmfPlaceableCheckSum(WmfPlaceableFileHeader const *)
0x180119c0a  xor     edx, edx
0x180119c0c  mov     [rbp+var_14], ax
0x180119c10  mov     ecx, 100h
0x180119c15  call    GpMallocEx
0x180119c1a  test    rax, rax
0x180119c1d  jz      short loc_180119C78
0x180119c1f  mov     r9d, 1; int
0x180119c25  mov     [rsp+58h+var_38], ebx; int
0x180119c29  lea     r8, [rbp+var_28]; struct WmfPlaceableFileHeader *
0x180119c2d  mov     rdx, rsi; HMETAFILE
0x180119c30  mov     rcx, rax; this
0x180119c33  call    ??0GpMetafile@@QEAA@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::GpMetafile(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x180119c38  mov     rbx, rax
0x180119c3b  test    rax, rax
0x180119c3e  jz      short loc_180119C78
0x180119c40  mov     rax, [rax]
0x180119c43  mov     rcx, rbx
0x180119c46  mov     rax, [rax+8]
0x180119c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119c4f  test    eax, eax
0x180119c51  jnz     short loc_180119C78
0x180119c53  mov     rcx, rsi; hmf
0x180119c56  call    cs:__imp_DeleteMetaFile
0x180119c5c  mov     rax, [rbx]
0x180119c5f  mov     rcx, rbx
0x180119c62  mov     qword ptr [rbx+0B8h], 0
0x180119c6d  mov     rax, [rax+38h]
0x180119c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119c76  xor     ebx, ebx
0x180119c78  mov     rax, rbx
0x180119c7b  mov     rcx, [rbp+var_10]
0x180119c7f  xor     rcx, rsp; StackCookie
0x180119c82  call    __security_check_cookie
0x180119c87  add     rsp, 58h
0x180119c8b  pop     rdi
0x180119c8c  pop     rsi
0x180119c8d  pop     rbx
0x180119c8e  pop     rbp
0x180119c8f  retn
```

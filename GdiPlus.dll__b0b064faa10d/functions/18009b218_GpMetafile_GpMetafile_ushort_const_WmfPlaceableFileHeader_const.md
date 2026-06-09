# GpMetafile::GpMetafile(ushort const *,WmfPlaceableFileHeader const *)

- ea: `0x18009b218`
- end: `0x18009b45f`
- name: `??0GpMetafile@@QEAA@PEBGPEBUWmfPlaceableFileHeader@@@Z`
- size: `583`
- prototype: `GpMetafile *__fastcall(GpMetafile *__hidden this, const unsigned __int16 *, const struct WmfPlaceableFileHeader *)`
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x18009a180`
- `0x18009ac30`
- `0x18009ae20`
- `0x18009b134`
- `0x180105f70`

## callees

- `0x1800056bc`
- `0x1800998a0`
- `0x18009b218`
- `0x18009b468`
- `0x18009b8f0`
- `0x18009b98c`
- `0x18009c084`
- `0x18009c1b0`
- `0x18009dfe4`
- `0x180169010`

## import_xrefs

- `GDI32!GetEnhMetaFileW` at `0x18009b36c`
- `GDI32!GetEnhMetaFileW` at `0x18009b36c`
- `GDI32!GetMetaFileW` at `0x18009b311`
- `GDI32!GetMetaFileW` at `0x18009b311`
- `GDI32!GetMetaFileBitsEx` at `0x18009b41a`
- `GDI32!GetMetaFileBitsEx` at `0x18009b41a`
- `GDI32!DeleteMetaFile` at `0x18009b454`
- `GDI32!DeleteMetaFile` at `0x18009b454`

## pseudocode

```c
GpMetafile *__fastcall GpMetafile::GpMetafile(GpMetafile *this, GpRuntime *a2, const struct WmfPlaceableFileHeader *a3)
{
  const unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // rdx
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r10
  const wchar_t *v12; // r8
  unsigned __int16 *i; // r9
  wchar_t v14; // dx
  wchar_t v15; // cx
  int v16; // edi
  int v17; // ebp
  HMETAFILE MetaFileW; // rax
  HMETAFILE v19; // rsi
  struct IStream *StreamOnFile; // rax
  struct IStream *v21; // rsi
  HENHMETAFILE EnhMetaFileW; // rax
  const wchar_t *j; // r8
  wchar_t v25; // dx
  wchar_t v26; // cx

  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 7) = -1;
  *((_DWORD *)this + 6) = 2;
  *((_DWORD *)this + 2) = 1735215409;
  *(_QWORD *)this = &GpMetafile::`vftable';
  GpMetafile::InitDefaults(this);
  v7 = GpRuntime::UnicodeStringDuplicate(a2, v6);
  *((_QWORD *)this + 24) = v7;
  if ( v7 )
  {
    v10 = GpRuntime::UnicodeStringReverseSearch(a2, v8, v9);
    v11 = v10;
    if ( !a3 )
    {
      if ( !v10 )
        goto LABEL_39;
      v12 = L".WMF";
      for ( i = v10; ; ++i )
      {
        v14 = *i;
        v15 = *v12;
        if ( !*i )
          break;
        if ( !v15 )
          goto LABEL_28;
        if ( (unsigned __int16)(v14 - 97) <= 0x19u )
          v14 -= 32;
        if ( (unsigned __int16)(v15 - 97) <= 0x19u )
          v15 -= 32;
        if ( v14 < v15 || v14 > v15 )
          goto LABEL_28;
        ++v12;
      }
      if ( !v15 )
        goto LABEL_15;
LABEL_28:
      for ( j = L".APM"; ; ++j )
      {
        v25 = *v11;
        v26 = *j;
        if ( !*v11 )
          break;
        if ( !v26 )
          goto LABEL_39;
        if ( (unsigned __int16)(v25 - 97) <= 0x19u )
          v25 -= 32;
        if ( (unsigned __int16)(v26 - 97) <= 0x19u )
          v26 -= 32;
        if ( v25 < v26 || v25 > v26 )
          goto LABEL_39;
        ++v11;
      }
      if ( v26 )
      {
LABEL_39:
        v16 = 0;
LABEL_16:
        v17 = 0;
        if ( !v16 )
          goto LABEL_23;
        while ( 1 )
        {
          MetaFileW = GetMetaFileW((LPCWSTR)a2);
          v19 = MetaFileW;
          if ( MetaFileW )
          {
            if ( GetMetaFileBitsEx(MetaFileW, 0, 0) )
            {
              GpMetafile::InitWmf(this, v19, a3, 1, 0);
              goto LABEL_20;
            }
            DeleteMetaFile(v19);
          }
          StreamOnFile = CreateStreamOnFile((const unsigned __int16 *)a2);
          v21 = StreamOnFile;
          if ( !StreamOnFile )
            goto LABEL_22;
          GpMetafile::InitStream(this, StreamOnFile, 1);
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_20:
          if ( (unsigned int)GpMetafile::IsValid(this) || *((_DWORD *)this + 44) == 1 )
            return this;
LABEL_22:
          if ( v17 )
            return this;
LABEL_23:
          EnhMetaFileW = GetEnhMetaFileW((LPCWSTR)a2);
          if ( EnhMetaFileW )
          {
            GpMetafile::InitEmf(this, EnhMetaFileW, 1);
            if ( (unsigned int)GpMetafile::IsValid(this) || *((_DWORD *)this + 44) == 1 )
              return this;
          }
          if ( v16 )
            return this;
          v17 = 1;
          v16 = 1;
        }
      }
    }
LABEL_15:
    v16 = 1;
    goto LABEL_16;
  }
  return this;
}

```

## disassembly

```asm
0x18009b218  push    rbx
0x18009b21a  push    rbp
0x18009b21b  push    rsi
0x18009b21c  push    rdi
0x18009b21d  push    r12
0x18009b21f  push    r13
0x18009b221  push    r14
0x18009b223  push    r15
0x18009b225  sub     rsp, 38h
0x18009b229  lea     rax, ??_7GpMetafile@@6B@; const GpMetafile::`vftable'
0x18009b230  xor     r12d, r12d
0x18009b233  mov     [rcx+10h], r12
0x18009b237  mov     r15, r8
0x18009b23a  mov     dword ptr [rcx+1Ch], 0FFFFFFFFh
0x18009b241  mov     r14, rdx
0x18009b244  mov     dword ptr [rcx+18h], 2
0x18009b24b  mov     rbx, rcx
0x18009b24e  mov     dword ptr [rcx+8], 676D4931h
0x18009b255  mov     [rcx], rax
0x18009b258  call    ?InitDefaults@GpMetafile@@IEAAXXZ; GpMetafile::InitDefaults(void)
0x18009b25d  mov     rcx, r14; this
0x18009b260  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18009b265  mov     [rbx+0C0h], rax
0x18009b26c  test    rax, rax
0x18009b26f  jz      loc_18009B3A1
0x18009b275  mov     rcx, r14; this
0x18009b278  call    ?UnicodeStringReverseSearch@GpRuntime@@YAPEAGPEBGG@Z; GpRuntime::UnicodeStringReverseSearch(ushort const *,ushort)
0x18009b27d  lea     r13d, [r12+1]
0x18009b282  mov     r10, rax
0x18009b285  test    r15, r15
0x18009b288  jnz     short loc_18009B304
0x18009b28a  test    rax, rax
0x18009b28d  jz      loc_18009B40A
0x18009b293  lea     r8, aWmf_0; ".WMF"
0x18009b29a  mov     r9, rax
0x18009b29d  mov     r11w, 61h ; 'a'
0x18009b2a2  mov     di, 19h
0x18009b2a6  mov     si, 20h ; ' '
0x18009b2aa  movzx   edx, word ptr [r9]
0x18009b2ae  movzx   ecx, word ptr [r8]
0x18009b2b2  test    dx, dx
0x18009b2b5  jz      short loc_18009B2FB
0x18009b2b7  test    cx, cx
0x18009b2ba  jz      loc_18009B3B5
0x18009b2c0  movzx   eax, dx
0x18009b2c3  sub     ax, r11w
0x18009b2c7  cmp     ax, di
0x18009b2ca  jbe     short loc_18009B2F6
0x18009b2cc  movzx   eax, cx
0x18009b2cf  sub     ax, r11w
0x18009b2d3  cmp     ax, di
0x18009b2d6  jbe     short loc_18009B2F1
0x18009b2d8  cmp     dx, cx
0x18009b2db  jb      loc_18009B3B5
0x18009b2e1  ja      loc_18009B3B5
0x18009b2e7  add     r9, 2
0x18009b2eb  add     r8, 2
0x18009b2ef  jmp     short loc_18009B2AA
0x18009b2f1  sub     cx, si
0x18009b2f4  jmp     short loc_18009B2D8
0x18009b2f6  sub     dx, si
0x18009b2f9  jmp     short loc_18009B2CC
0x18009b2fb  test    cx, cx
0x18009b2fe  jnz     loc_18009B3B5
0x18009b304  mov     edi, r13d
0x18009b307  mov     ebp, r12d
0x18009b30a  test    edi, edi
0x18009b30c  jz      short loc_18009B369
0x18009b30e  mov     rcx, r14; lpName
0x18009b311  call    cs:__imp_GetMetaFileW
0x18009b317  mov     rsi, rax
0x18009b31a  test    rax, rax
0x18009b31d  jnz     loc_18009B412
0x18009b323  mov     rcx, r14; unsigned __int16 *
0x18009b326  call    ?CreateStreamOnFile@@YAPEAUIStream@@PEBGI@Z; CreateStreamOnFile(ushort const *,uint)
0x18009b32b  mov     rsi, rax
0x18009b32e  test    rax, rax
0x18009b331  jz      short loc_18009B365
0x18009b333  mov     r8d, r13d; int
0x18009b336  mov     rdx, rax; struct IStream *
0x18009b339  mov     rcx, rbx; this
0x18009b33c  call    ?InitStream@GpMetafile@@IEAAXPEAUIStream@@H@Z; GpMetafile::InitStream(IStream *,int)
0x18009b341  mov     rcx, [rsi]
0x18009b344  mov     rax, [rcx+10h]
0x18009b348  mov     rcx, rsi
0x18009b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b350  mov     rcx, rbx; this
0x18009b353  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18009b358  test    eax, eax
0x18009b35a  jnz     short loc_18009B3A1
0x18009b35c  cmp     [rbx+0B0h], r13d
0x18009b363  jz      short loc_18009B3A1
0x18009b365  test    ebp, ebp
0x18009b367  jnz     short loc_18009B3A1
0x18009b369  mov     rcx, r14; lpName
0x18009b36c  call    cs:__imp_GetEnhMetaFileW
0x18009b372  test    rax, rax
0x18009b375  jnz     short loc_18009B383
0x18009b377  test    edi, edi
0x18009b379  jnz     short loc_18009B3A1
0x18009b37b  mov     ebp, r13d
0x18009b37e  mov     edi, r13d
0x18009b381  jmp     short loc_18009B30E
0x18009b383  mov     r8d, r13d; int
0x18009b386  mov     rdx, rax; HENHMETAFILE
0x18009b389  mov     rcx, rbx; this
0x18009b38c  call    ?InitEmf@GpMetafile@@IEAAXPEAUHENHMETAFILE__@@H@Z; GpMetafile::InitEmf(HENHMETAFILE__ *,int)
0x18009b391  mov     rcx, rbx; this
0x18009b394  call    ?IsValid@GpMetafile@@UEBAHXZ; GpMetafile::IsValid(void)
0x18009b399  test    eax, eax
0x18009b39b  jz      loc_18009B43F
0x18009b3a1  mov     rax, rbx
0x18009b3a4  add     rsp, 38h
0x18009b3a8  pop     r15
0x18009b3aa  pop     r14
0x18009b3ac  pop     r13
0x18009b3ae  pop     r12
0x18009b3b0  pop     rdi
0x18009b3b1  pop     rsi
0x18009b3b2  pop     rbp
0x18009b3b3  pop     rbx
0x18009b3b4  retn
0x18009b3b5  lea     r8, aApm; ".APM"
0x18009b3bc  movzx   edx, word ptr [r10]
0x18009b3c0  movzx   ecx, word ptr [r8]
0x18009b3c4  test    dx, dx
0x18009b3c7  jz      short loc_18009B401
0x18009b3c9  test    cx, cx
0x18009b3cc  jz      short loc_18009B40A
0x18009b3ce  movzx   eax, dx
0x18009b3d1  sub     ax, r11w
0x18009b3d5  cmp     ax, di
0x18009b3d8  jbe     short loc_18009B3FC
0x18009b3da  movzx   eax, cx
0x18009b3dd  sub     ax, r11w
0x18009b3e1  cmp     ax, di
0x18009b3e4  jbe     short loc_18009B3F7
0x18009b3e6  cmp     dx, cx
0x18009b3e9  jb      short loc_18009B40A
0x18009b3eb  ja      short loc_18009B40A
0x18009b3ed  add     r10, 2
0x18009b3f1  add     r8, 2
0x18009b3f5  jmp     short loc_18009B3BC
0x18009b3f7  sub     cx, si
0x18009b3fa  jmp     short loc_18009B3E6
0x18009b3fc  sub     dx, si
0x18009b3ff  jmp     short loc_18009B3DA
0x18009b401  test    cx, cx
0x18009b404  jz      loc_18009B304
0x18009b40a  mov     edi, r12d
0x18009b40d  jmp     loc_18009B307
0x18009b412  xor     r8d, r8d; lpData
0x18009b415  xor     edx, edx; cbBuffer
0x18009b417  mov     rcx, rsi; hMF
0x18009b41a  call    cs:__imp_GetMetaFileBitsEx
0x18009b420  test    eax, eax
0x18009b422  jz      short loc_18009B451
0x18009b424  mov     r9d, r13d; int
0x18009b427  mov     [rsp+78h+var_58], r12d; int
0x18009b42c  mov     r8, r15; struct WmfPlaceableFileHeader *
0x18009b42f  mov     rdx, rsi; HMETAFILE
0x18009b432  mov     rcx, rbx; this
0x18009b435  call    ?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z; GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)
0x18009b43a  jmp     loc_18009B350
0x18009b43f  cmp     [rbx+0B0h], r13d
0x18009b446  jnz     loc_18009B377
0x18009b44c  jmp     loc_18009B3A1
0x18009b451  mov     rcx, rsi; hmf
0x18009b454  call    cs:__imp_DeleteMetaFile
0x18009b45a  jmp     loc_18009B323
```

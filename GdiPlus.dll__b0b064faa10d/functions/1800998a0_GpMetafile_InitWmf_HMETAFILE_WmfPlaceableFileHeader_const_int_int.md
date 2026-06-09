# GpMetafile::InitWmf(HMETAFILE__ *,WmfPlaceableFileHeader const *,int,int)

- ea: `0x1800998a0`
- end: `0x180099a34`
- name: `?InitWmf@GpMetafile@@IEAAXPEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@HH@Z`
- size: `404`
- prototype: `void(GpMetafile *__hidden this, HMETAFILE, const struct WmfPlaceableFileHeader *, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18009a6dc`
- `0x18009b218`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x180098e7c`
- `0x180098f84`
- `0x1800998a0`
- `0x180099a3c`
- `0x18009ce90`

## import_xrefs

- `GDI32!GetMetaFileBitsEx` at `0x1800998d5`
- `GDI32!GetMetaFileBitsEx` at `0x180099905`
- `GDI32!GetMetaFileBitsEx` at `0x1800998d5`
- `GDI32!GetMetaFileBitsEx` at `0x180099905`
- `GDI32!DeleteMetaFile` at `0x180099a29`
- `GDI32!DeleteMetaFile` at `0x180099a29`
- `GDI32!DeleteEnhMetaFile` at `0x180099a1b`
- `GDI32!DeleteEnhMetaFile` at `0x180099a1b`

## pseudocode

```c
void __fastcall GpMetafile::InitWmf(
        GpMetafile *this,
        HMETAFILE a2,
        const struct WmfPlaceableFileHeader *a3,
        int a4,
        int a5)
{
  const struct WmfPlaceableFileHeader *v6; // r10
  __int16 *v9; // rsi
  UINT MetaFileBits; // eax
  unsigned int v11; // r14d
  void *v12; // rax
  __int64 v13; // rbp
  HENHMETAFILE EmfFromWmfData; // rax
  HENHMETAFILE v15; // rsi
  __int16 *v16; // r10
  int v17; // [rsp+80h] [rbp+18h] BYREF

  v6 = a3;
  if ( a3 && (unsigned int)WmfPlaceableHeaderIsValid(a3) && !a5 )
  {
    if ( !(unsigned int)GetMetafileHeader(a2, v6, (char *)this + 32) )
    {
      *((_QWORD *)this + 23) = a2;
      *((_DWORD *)this + 44) = 3;
      *((_DWORD *)this + 57) = a4 != 0;
      return;
    }
    *((_DWORD *)this + 44) = 1;
  }
  else
  {
    v9 = 0;
    if ( v6 && (unsigned int)WmfPlaceableHeaderIsValid(v6) )
      v9 = v16;
    MetaFileBits = GetMetaFileBitsEx(a2, 0, 0);
    v11 = MetaFileBits;
    if ( MetaFileBits )
    {
      v12 = (void *)GpMallocEx(MetaFileBits, 0);
      v13 = (__int64)v12;
      if ( v12 )
      {
        if ( (int)GetMetaFileBitsEx(a2, v11, v12) > 0 )
        {
          EmfFromWmfData = GetEmfFromWmfData(a2, v9, v13, v11, *((_DWORD *)this + 61));
          v15 = EmfFromWmfData;
          if ( EmfFromWmfData )
          {
            v17 = 0;
            if ( (unsigned int)GetMetafileHeader(EmfFromWmfData, (char *)this + 32, &v17) )
            {
              if ( v17 )
                *((_DWORD *)this + 44) = 1;
              DeleteEnhMetaFile(v15);
            }
            else
            {
              *((_DWORD *)this + 57) = 1;
              *((_QWORD *)this + 23) = v15;
              *((_DWORD *)this + 44) = 3;
            }
          }
        }
        GpFree(v13);
      }
    }
  }
  if ( a4 )
    DeleteMetaFile(a2);
}

```

## disassembly

```asm
0x1800998a0  push    rbx
0x1800998a2  push    rbp
0x1800998a3  push    rsi
0x1800998a4  push    rdi
0x1800998a5  push    r14
0x1800998a7  push    r15
0x1800998a9  sub     rsp, 38h
0x1800998ad  mov     r15d, r9d
0x1800998b0  mov     r10, r8
0x1800998b3  mov     rdi, rdx
0x1800998b6  mov     rbx, rcx
0x1800998b9  test    r8, r8
0x1800998bc  jnz     loc_180099992
0x1800998c2  xor     esi, esi
0x1800998c4  test    r10, r10
0x1800998c7  jnz     loc_1800999E2
0x1800998cd  xor     r8d, r8d; lpData
0x1800998d0  xor     edx, edx; cbBuffer
0x1800998d2  mov     rcx, rdi; hMF
0x1800998d5  call    cs:__imp_GetMetaFileBitsEx
0x1800998db  mov     r14d, eax
0x1800998de  test    eax, eax
0x1800998e0  jz      loc_18009997C
0x1800998e6  mov     ecx, r14d
0x1800998e9  xor     edx, edx
0x1800998eb  call    GpMallocEx
0x1800998f0  mov     rbp, rax
0x1800998f3  test    rax, rax
0x1800998f6  jz      loc_18009997C
0x1800998fc  mov     r8, rax; lpData
0x1800998ff  mov     edx, r14d; cbBuffer
0x180099902  mov     rcx, rdi; hMF
0x180099905  call    cs:__imp_GetMetaFileBitsEx
0x18009990b  test    eax, eax
0x18009990d  jle     short loc_180099974
0x18009990f  mov     ecx, [rbx+0F4h]
0x180099915  mov     r9d, r14d
0x180099918  mov     [rsp+68h+var_48], ecx
0x18009991c  mov     r8, rbp
0x18009991f  mov     rcx, rdi
0x180099922  mov     rdx, rsi
0x180099925  call    ?GetEmfFromWmfData@@YAPEAUHENHMETAFILE__@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@PEAEIW4WmfCompatibilityMode@@@Z; GetEmfFromWmfData(HMETAFILE__ *,WmfPlaceableFileHeader const *,uchar *,uint,WmfCompatibilityMode)
0x18009992a  mov     rsi, rax
0x18009992d  test    rax, rax
0x180099930  jz      short loc_180099974
0x180099932  lea     rdx, [rbx+20h]
0x180099936  mov     [rsp+68h+arg_10], 0
0x180099941  lea     r8, [rsp+68h+arg_10]
0x180099949  mov     rcx, rax
0x18009994c  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHENHMETAFILE__@@AEAVMetafileHeader@@PEAH@Z; GetMetafileHeader(HENHMETAFILE__ *,MetafileHeader &,int *)
0x180099951  test    eax, eax
0x180099953  jnz     loc_180099A04
0x180099959  mov     dword ptr [rbx+0E4h], 1
0x180099963  mov     [rbx+0B8h], rsi
0x18009996a  mov     dword ptr [rbx+0B0h], 3
0x180099974  mov     rcx, rbp
0x180099977  call    GpFree
0x18009997c  test    r15d, r15d
0x18009997f  jnz     loc_180099A26
0x180099985  add     rsp, 38h
0x180099989  pop     r15
0x18009998b  pop     r14
0x18009998d  pop     rdi
0x18009998e  pop     rsi
0x18009998f  pop     rbp
0x180099990  pop     rbx
0x180099991  retn
0x180099992  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x180099995  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x18009999a  test    eax, eax
0x18009999c  jz      loc_1800998C2
0x1800999a2  cmp     [rsp+68h+arg_20], 0
0x1800999aa  jnz     loc_1800998C2
0x1800999b0  lea     r8, [rbx+20h]
0x1800999b4  mov     rdx, r10
0x1800999b7  mov     rcx, rdi
0x1800999ba  call    ?GetMetafileHeader@@YA?AW4Status@@PEAUHMETAFILE__@@PEBUWmfPlaceableFileHeader@@AEAVMetafileHeader@@@Z; GetMetafileHeader(HMETAFILE__ *,WmfPlaceableFileHeader const *,MetafileHeader &)
0x1800999bf  test    eax, eax
0x1800999c1  jnz     short loc_1800999F5
0x1800999c3  test    r15d, r15d
0x1800999c6  mov     [rbx+0B8h], rdi
0x1800999cd  mov     dword ptr [rbx+0B0h], 3
0x1800999d7  setnz   al
0x1800999da  mov     [rbx+0E4h], eax
0x1800999e0  jmp     short loc_180099985
0x1800999e2  mov     rcx, r10; struct WmfPlaceableFileHeader *
0x1800999e5  call    ?WmfPlaceableHeaderIsValid@@YAHPEBUWmfPlaceableFileHeader@@@Z; WmfPlaceableHeaderIsValid(WmfPlaceableFileHeader const *)
0x1800999ea  test    eax, eax
0x1800999ec  cmovnz  rsi, r10
0x1800999f0  jmp     loc_1800998CD
0x1800999f5  mov     dword ptr [rbx+0B0h], 1
0x1800999ff  jmp     loc_18009997C
0x180099a04  cmp     [rsp+68h+arg_10], 0
0x180099a0c  jz      short loc_180099A18
0x180099a0e  mov     dword ptr [rbx+0B0h], 1
0x180099a18  mov     rcx, rsi; hmf
0x180099a1b  call    cs:__imp_DeleteEnhMetaFile
0x180099a21  jmp     loc_180099974
0x180099a26  mov     rcx, rdi; hmf
0x180099a29  call    cs:__imp_DeleteMetaFile
0x180099a2f  jmp     loc_180099985
```

# DllGetClassObject

- ea: `0x180006bf0`
- end: `0x180006d4b`
- name: `DllGetClassObject`
- size: `347`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180006bf0`
- `0x18000fe90`
- `0x180010320`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  char *v6; // rax
  void *v7; // rdi
  HRESULT Interface; // ebx
  CPSFactory *v9; // rdi

  *ppv = 0;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_AVIFile
    || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_ACMCmprs.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_ACMCmprs.Data4
    || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_AVIWaveFileReader.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_AVIWaveFileReader.Data4
    || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_AVICmprsStream.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_AVICmprsStream.Data4 )
  {
    v6 = (char *)operator new(0x38u);
    v7 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 1) = v6;
      *(_QWORD *)v6 = &CAVIFileCF::CUnknownImpl::`vftable';
      *((_DWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 3) = &CAVIFileCF::CI::`vftable';
      *((_QWORD *)v6 + 4) = v6;
      *(IID *)(v6 + 40) = *rclsid;
      Interface = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
      if ( Interface < 0 )
        operator delete(v7);
      return Interface;
    }
    return -2147024882;
  }
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_AVIStreamPS.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_AVIStreamPS.Data4 )
  {
    v9 = (CPSFactory *)operator new(0x10u);
    if ( v9 )
    {
      ++uUseCount;
      *(_QWORD *)v9 = &CPSFactory::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      Interface = CPSFactory::QueryInterface(v9, riid, ppv);
      CPSFactory::Release(v9);
      return Interface;
    }
    return -2147024882;
  }
  return -2147418113;
}

```

## disassembly

```asm
0x180006bf0  push    rbx
0x180006bf2  push    rbp
0x180006bf3  push    rsi
0x180006bf4  push    rdi
0x180006bf5  sub     rsp, 28h
0x180006bf9  mov     qword ptr [r8], 0
0x180006c00  mov     rsi, r8
0x180006c03  mov     rax, [rcx]
0x180006c06  mov     rbp, rdx
0x180006c09  cmp     rax, qword ptr cs:CLSID_AVIFile.Data1
0x180006c10  mov     rbx, rcx
0x180006c13  jnz     short loc_180006C22
0x180006c15  mov     rax, [rcx+8]
0x180006c19  cmp     rax, qword ptr cs:CLSID_AVIFile.Data4
0x180006c20  jz      short loc_180006C6D
0x180006c22  mov     rax, [rcx]
0x180006c25  cmp     rax, qword ptr cs:CLSID_ACMCmprs.Data1
0x180006c2c  jnz     short loc_180006C3B
0x180006c2e  mov     rax, [rcx+8]
0x180006c32  cmp     rax, qword ptr cs:CLSID_ACMCmprs.Data4
0x180006c39  jz      short loc_180006C6D
0x180006c3b  mov     rax, [rcx]
0x180006c3e  cmp     rax, qword ptr cs:CLSID_AVIWaveFileReader.Data1
0x180006c45  jnz     short loc_180006C54
0x180006c47  mov     rax, [rcx+8]
0x180006c4b  cmp     rax, qword ptr cs:CLSID_AVIWaveFileReader.Data4
0x180006c52  jz      short loc_180006C6D
0x180006c54  mov     rax, [rcx]
0x180006c57  cmp     rax, qword ptr cs:CLSID_AVICmprsStream.Data1
0x180006c5e  jnz     short loc_180006CD8
0x180006c60  mov     rax, [rcx+8]
0x180006c64  cmp     rax, qword ptr cs:CLSID_AVICmprsStream.Data4
0x180006c6b  jnz     short loc_180006CD8
0x180006c6d  mov     ecx, 38h ; '8'; Size
0x180006c72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c77  mov     rdi, rax
0x180006c7a  test    rax, rax
0x180006c7d  jz      loc_180006D34
0x180006c83  mov     [rdi+8], rdi
0x180006c87  lea     rax, ??_7CUnknownImpl@CAVIFileCF@@6B@; const CAVIFileCF::CUnknownImpl::`vftable'
0x180006c8e  mov     [rdi], rax
0x180006c91  mov     r8, rsi
0x180006c94  mov     dword ptr [rdi+10h], 0
0x180006c9b  lea     rax, ??_7CI@CAVIFileCF@@6B@; const CAVIFileCF::CI::`vftable'
0x180006ca2  mov     [rdi+18h], rax
0x180006ca6  mov     rdx, rbp
0x180006ca9  mov     [rdi+20h], rdi
0x180006cad  movups  xmm0, xmmword ptr [rbx]
0x180006cb0  movdqu  xmmword ptr [rdi+28h], xmm0
0x180006cb5  mov     rcx, [rdi]
0x180006cb8  mov     rax, [rcx]
0x180006cbb  mov     rcx, rdi
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  mov     ebx, eax
0x180006cc5  test    eax, eax
0x180006cc7  jns     short loc_180006D39
0x180006cc9  mov     edx, 38h ; '8'; unsigned __int64
0x180006cce  mov     rcx, rdi; void *
0x180006cd1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006cd6  jmp     short loc_180006D39
0x180006cd8  mov     rax, [rcx]
0x180006cdb  cmp     rax, qword ptr cs:CLSID_AVIStreamPS.Data1
0x180006ce2  jnz     short loc_180006D3D
0x180006ce4  mov     rax, [rcx+8]
0x180006ce8  cmp     rax, qword ptr cs:CLSID_AVIStreamPS.Data4
0x180006cef  jnz     short loc_180006D3D
0x180006cf1  mov     ecx, 10h; Size
0x180006cf6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006cfb  mov     rdi, rax
0x180006cfe  test    rax, rax
0x180006d01  jz      short loc_180006D34
0x180006d03  inc     cs:uUseCount
0x180006d09  lea     rax, ??_7CPSFactory@@6B@; const CPSFactory::`vftable'
0x180006d10  mov     r8, rsi; void **
0x180006d13  mov     [rdi], rax
0x180006d16  mov     rdx, rbp; struct _GUID *
0x180006d19  mov     dword ptr [rdi+8], 1
0x180006d20  mov     rcx, rdi; this
0x180006d23  call    ?QueryInterface@CPSFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CPSFactory::QueryInterface(_GUID const &,void * *)
0x180006d28  mov     rcx, rdi; this
0x180006d2b  mov     ebx, eax
0x180006d2d  call    ?Release@CPSFactory@@UEAAKXZ; CPSFactory::Release(void)
0x180006d32  jmp     short loc_180006D39
0x180006d34  mov     ebx, 8007000Eh
0x180006d39  mov     eax, ebx
0x180006d3b  jmp     short loc_180006D42
0x180006d3d  mov     eax, 8000FFFFh
0x180006d42  add     rsp, 28h
0x180006d46  pop     rdi
0x180006d47  pop     rsi
0x180006d48  pop     rbp
0x180006d49  pop     rbx
0x180006d4a  retn
```

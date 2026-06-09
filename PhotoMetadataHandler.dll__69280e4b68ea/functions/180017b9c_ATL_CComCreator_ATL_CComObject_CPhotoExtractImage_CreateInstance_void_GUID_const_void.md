# ATL::CComCreator<ATL::CComObject<CPhotoExtractImage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180017b9c`
- end: `0x180017cbb`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoExtractImage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017b70`

## callees

- `0x180002920`
- `0x180011780`
- `0x180017b9c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017be3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017be3`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPhotoExtractImage>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CPhotoExtractImage *v7; // rax
  CPhotoExtractImage *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CPhotoExtractImage *)LocalAlloc(0x40u, 0x2B0u);
  v8 = v7;
  if ( v7 )
  {
    CPhotoExtractImage::CPhotoExtractImage(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IExtractImage'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IPersistFile'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithStream'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithFile'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v8 + 1);
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CPhotoExtractImage *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CPhotoExtractImage *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180017b9c  mov     [rsp+arg_10], r8
0x180017ba1  mov     [rsp+arg_8], rdx
0x180017ba6  mov     [rsp+arg_0], rcx
0x180017bab  push    rbx
0x180017bac  push    rsi
0x180017bad  push    rdi
0x180017bae  push    r14
0x180017bb0  sub     rsp, 28h
0x180017bb4  mov     rsi, r8
0x180017bb7  mov     r14, rdx
0x180017bba  test    r8, r8
0x180017bbd  jnz     short loc_180017BC9
0x180017bbf  mov     eax, 80004003h
0x180017bc4  jmp     loc_180017CB0
0x180017bc9  mov     qword ptr [r8], 0
0x180017bd0  mov     edi, 8007000Eh
0x180017bd5  mov     dword ptr [rsp+48h+arg_0], edi
0x180017bd9  mov     edx, 2B0h; uBytes
0x180017bde  mov     ecx, 40h ; '@'; uFlags
0x180017be3  call    cs:__imp_LocalAlloc
0x180017bea  nop     dword ptr [rax+rax+00h]
0x180017bef  mov     rbx, rax
0x180017bf2  mov     [rsp+48h+arg_18], rax
0x180017bf7  test    rax, rax
0x180017bfa  jz      short loc_180017C44
0x180017bfc  mov     rcx, rax; this
0x180017bff  call    ??0CPhotoExtractImage@@QEAA@XZ; CPhotoExtractImage::CPhotoExtractImage(void)
0x180017c04  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIExtractImage@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IExtractImage'}
0x180017c0b  mov     [rbx], rax
0x180017c0e  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IPersistFile'}
0x180017c15  mov     [rbx+8], rax
0x180017c19  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIInitializeWithStream@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithStream'}
0x180017c20  mov     [rbx+10h], rax
0x180017c24  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithFile'}
0x180017c2b  mov     [rbx+18h], rax
0x180017c2f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180017c36  mov     rax, [rcx]
0x180017c39  mov     rax, [rax+8]
0x180017c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c42  jmp     short loc_180017C46
0x180017c44  xor     ebx, ebx
0x180017c46  mov     [rsp+48h+arg_18], rbx
0x180017c4b  jmp     short loc_180017C60
0x180017c4d  mov     rsi, [rsp+48h+arg_10]
0x180017c52  mov     r14, [rsp+48h+arg_8]
0x180017c57  mov     edi, dword ptr [rsp+48h+arg_0]
0x180017c5b  mov     rbx, [rsp+48h+arg_18]
0x180017c60  test    rbx, rbx
0x180017c63  jz      short loc_180017CAE
0x180017c65  lea     rcx, [rbx+28h]; this
0x180017c69  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180017c6e  xor     ecx, ecx
0x180017c70  test    eax, eax
0x180017c72  cmovs   ecx, eax
0x180017c75  xor     edi, edi
0x180017c77  test    ecx, ecx
0x180017c79  cmovs   edi, ecx
0x180017c7c  test    edi, edi
0x180017c7e  jnz     short loc_180017C9A
0x180017c80  mov     rax, [rbx]
0x180017c83  mov     r8, rsi
0x180017c86  mov     rdx, r14
0x180017c89  mov     rcx, rbx
0x180017c8c  mov     rax, [rax]
0x180017c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c94  mov     edi, eax
0x180017c96  test    eax, eax
0x180017c98  jz      short loc_180017CAE
0x180017c9a  mov     rdx, [rbx]
0x180017c9d  mov     rax, [rdx+28h]
0x180017ca1  mov     edx, 1
0x180017ca6  mov     rcx, rbx
0x180017ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cae  mov     eax, edi
0x180017cb0  add     rsp, 28h
0x180017cb4  pop     r14
0x180017cb6  pop     rdi
0x180017cb7  pop     rsi
0x180017cb8  pop     rbx
0x180017cb9  retn
```

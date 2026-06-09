# ATL::CComCreator<ATL::CComObject<CPhotoExtractImage>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180017128`
- end: `0x180017240`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoExtractImage@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180017100`

## callees

- `0x180002800`
- `0x180010fd8`
- `0x180017128`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001716f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001716f`

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
0x180017128  mov     [rsp+arg_10], r8
0x18001712d  mov     [rsp+arg_8], rdx
0x180017132  mov     [rsp+arg_0], rcx
0x180017137  push    rbx
0x180017138  push    rsi
0x180017139  push    rdi
0x18001713a  push    r14
0x18001713c  sub     rsp, 28h
0x180017140  mov     rsi, r8
0x180017143  mov     r14, rdx
0x180017146  test    r8, r8
0x180017149  jnz     short loc_180017155
0x18001714b  mov     eax, 80004003h
0x180017150  jmp     loc_180017236
0x180017155  mov     qword ptr [r8], 0
0x18001715c  mov     edi, 8007000Eh
0x180017161  mov     dword ptr [rsp+48h+arg_0], edi
0x180017165  mov     edx, 2B0h; uBytes
0x18001716a  mov     ecx, 40h ; '@'; uFlags
0x18001716f  call    cs:__imp_LocalAlloc
0x180017175  mov     rbx, rax
0x180017178  mov     [rsp+48h+arg_18], rax
0x18001717d  test    rax, rax
0x180017180  jz      short loc_1800171CA
0x180017182  mov     rcx, rax; this
0x180017185  call    ??0CPhotoExtractImage@@QEAA@XZ; CPhotoExtractImage::CPhotoExtractImage(void)
0x18001718a  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIExtractImage@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IExtractImage'}
0x180017191  mov     [rbx], rax
0x180017194  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IPersistFile'}
0x18001719b  mov     [rbx+8], rax
0x18001719f  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIInitializeWithStream@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithStream'}
0x1800171a6  mov     [rbx+10h], rax
0x1800171aa  lea     rax, ??_7?$CComObject@VCPhotoExtractImage@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CPhotoExtractImage>::`vftable'{for `IInitializeWithFile'}
0x1800171b1  mov     [rbx+18h], rax
0x1800171b5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800171bc  mov     rax, [rcx]
0x1800171bf  mov     rax, [rax+8]
0x1800171c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c8  jmp     short loc_1800171CC
0x1800171ca  xor     ebx, ebx
0x1800171cc  mov     [rsp+48h+arg_18], rbx
0x1800171d1  jmp     short loc_1800171E6
0x1800171d3  mov     rsi, [rsp+48h+arg_10]
0x1800171d8  mov     r14, [rsp+48h+arg_8]
0x1800171dd  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800171e1  mov     rbx, [rsp+48h+arg_18]
0x1800171e6  test    rbx, rbx
0x1800171e9  jz      short loc_180017234
0x1800171eb  lea     rcx, [rbx+28h]; this
0x1800171ef  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800171f4  xor     ecx, ecx
0x1800171f6  test    eax, eax
0x1800171f8  cmovs   ecx, eax
0x1800171fb  xor     edi, edi
0x1800171fd  test    ecx, ecx
0x1800171ff  cmovs   edi, ecx
0x180017202  test    edi, edi
0x180017204  jnz     short loc_180017220
0x180017206  mov     rax, [rbx]
0x180017209  mov     r8, rsi
0x18001720c  mov     rdx, r14
0x18001720f  mov     rcx, rbx
0x180017212  mov     rax, [rax]
0x180017215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721a  mov     edi, eax
0x18001721c  test    eax, eax
0x18001721e  jz      short loc_180017234
0x180017220  mov     rdx, [rbx]
0x180017223  mov     rax, [rdx+28h]
0x180017227  mov     edx, 1
0x18001722c  mov     rcx, rbx
0x18001722f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017234  mov     eax, edi
0x180017236  add     rsp, 28h
0x18001723a  pop     r14
0x18001723c  pop     rdi
0x18001723d  pop     rsi
0x18001723e  pop     rbx
0x18001723f  retn
```

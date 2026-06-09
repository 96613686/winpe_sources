# ATL::CComCreator<ATL::CComObject<CPhotoThumbnailProvider>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002098`
- end: `0x1800021aa`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoThumbnailProvider@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002070`

## callees

- `0x180002098`
- `0x1800021b0`
- `0x180002800`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020d7`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPhotoThumbnailProvider>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // edi
  CPhotoThumbnailProvider *v6; // rax
  CPhotoThumbnailProvider *v7; // rbx
  int v8; // eax
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (CPhotoThumbnailProvider *)LocalAlloc(0x40u, 0x98u);
  v7 = v6;
  if ( v6 )
  {
    CPhotoThumbnailProvider::CPhotoThumbnailProvider(v6);
    *(_QWORD *)v7 = &ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithStream'};
    *((_QWORD *)v7 + 1) = &ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithFile'};
    *((_QWORD *)v7 + 2) = &ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IThumbnailProvider'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v8 = ATL::CComSafeDeleteCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v7 + 32));
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v5 = 0;
    if ( v9 < 0 )
      v5 = v9;
    if ( v5 || (v5 = (**(__int64 (__fastcall ***)(CPhotoThumbnailProvider *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0 )
      (*(void (__fastcall **)(CPhotoThumbnailProvider *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180002098  mov     [rsp+arg_10], r8
0x18000209d  mov     [rsp+arg_8], rdx
0x1800020a2  mov     [rsp+arg_0], rcx
0x1800020a7  push    rbx
0x1800020a8  push    rsi
0x1800020a9  push    rdi
0x1800020aa  push    r14
0x1800020ac  sub     rsp, 28h
0x1800020b0  mov     rsi, r8
0x1800020b3  mov     r14, rdx
0x1800020b6  test    r8, r8
0x1800020b9  jz      loc_180002174
0x1800020bf  mov     qword ptr [r8], 0
0x1800020c6  mov     edi, 8007000Eh
0x1800020cb  mov     dword ptr [rsp+48h+arg_0], edi
0x1800020cf  mov     edx, 98h; uBytes
0x1800020d4  lea     ecx, [rdx-58h]; uFlags
0x1800020d7  call    cs:__imp_LocalAlloc
0x1800020dd  mov     rbx, rax
0x1800020e0  mov     [rsp+48h+arg_18], rax
0x1800020e5  test    rax, rax
0x1800020e8  jz      loc_180002191
0x1800020ee  mov     rcx, rax; this
0x1800020f1  call    ??0CPhotoThumbnailProvider@@QEAA@XZ; CPhotoThumbnailProvider::CPhotoThumbnailProvider(void)
0x1800020f6  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIInitializeWithStream@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithStream'}
0x1800020fd  mov     [rbx], rax
0x180002100  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithFile'}
0x180002107  mov     [rbx+8], rax
0x18000210b  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIThumbnailProvider@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IThumbnailProvider'}
0x180002112  mov     [rbx+10h], rax
0x180002116  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000211d  mov     rax, [rcx]
0x180002120  mov     rax, [rax+8]
0x180002124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002129  mov     [rsp+48h+arg_18], rbx
0x18000212e  test    rbx, rbx
0x180002131  jz      short loc_180002168
0x180002133  lea     rcx, [rbx+20h]; this
0x180002137  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000213c  xor     ecx, ecx
0x18000213e  test    eax, eax
0x180002140  cmovs   ecx, eax
0x180002143  xor     edi, edi
0x180002145  test    ecx, ecx
0x180002147  cmovs   edi, ecx
0x18000214a  test    edi, edi
0x18000214c  jnz     short loc_18000217B
0x18000214e  mov     rax, [rbx]
0x180002151  mov     r8, rsi
0x180002154  mov     rdx, r14
0x180002157  mov     rcx, rbx
0x18000215a  mov     rax, [rax]
0x18000215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002162  mov     edi, eax
0x180002164  test    eax, eax
0x180002166  jnz     short loc_18000217B
0x180002168  mov     eax, edi
0x18000216a  add     rsp, 28h
0x18000216e  pop     r14
0x180002170  pop     rdi
0x180002171  pop     rsi
0x180002172  pop     rbx
0x180002173  retn
0x180002174  mov     eax, 80004003h
0x180002179  jmp     short loc_18000216A
0x18000217b  mov     rdx, [rbx]
0x18000217e  mov     rax, [rdx+20h]
0x180002182  mov     edx, 1
0x180002187  mov     rcx, rbx
0x18000218a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000218f  jmp     short loc_180002168
0x180002191  xor     ebx, ebx
0x180002193  jmp     short loc_180002129
0x180002195  mov     rsi, [rsp+48h+arg_10]
0x18000219a  mov     r14, [rsp+48h+arg_8]
0x18000219f  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800021a3  mov     rbx, [rsp+48h+arg_18]
0x1800021a8  jmp     short loc_18000212E
```

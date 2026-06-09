# ATL::CComCreator<ATL::CComObject<CPhotoThumbnailProvider>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000214c`
- end: `0x180002265`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPhotoThumbnailProvider@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002120`

## callees

- `0x18000214c`
- `0x18000226c`
- `0x180002920`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000218b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000218b`

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
0x18000214c  mov     [rsp+arg_10], r8
0x180002151  mov     [rsp+arg_8], rdx
0x180002156  mov     [rsp+arg_0], rcx
0x18000215b  push    rbx
0x18000215c  push    rsi
0x18000215d  push    rdi
0x18000215e  push    r14
0x180002160  sub     rsp, 28h
0x180002164  mov     rsi, r8
0x180002167  mov     r14, rdx
0x18000216a  test    r8, r8
0x18000216d  jz      loc_18000222F
0x180002173  mov     qword ptr [r8], 0
0x18000217a  mov     edi, 8007000Eh
0x18000217f  mov     dword ptr [rsp+48h+arg_0], edi
0x180002183  mov     edx, 98h; uBytes
0x180002188  lea     ecx, [rdx-58h]; uFlags
0x18000218b  call    cs:__imp_LocalAlloc
0x180002192  nop     dword ptr [rax+rax+00h]
0x180002197  mov     rbx, rax
0x18000219a  mov     [rsp+48h+arg_18], rax
0x18000219f  test    rax, rax
0x1800021a2  jz      loc_18000224C
0x1800021a8  mov     rcx, rax; this
0x1800021ab  call    ??0CPhotoThumbnailProvider@@QEAA@XZ; CPhotoThumbnailProvider::CPhotoThumbnailProvider(void)
0x1800021b0  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIInitializeWithStream@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithStream'}
0x1800021b7  mov     [rbx], rax
0x1800021ba  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIInitializeWithFile@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IInitializeWithFile'}
0x1800021c1  mov     [rbx+8], rax
0x1800021c5  lea     rax, ??_7?$CComObject@VCPhotoThumbnailProvider@@@ATL@@6BIThumbnailProvider@@@; const ATL::CComObject<CPhotoThumbnailProvider>::`vftable'{for `IThumbnailProvider'}
0x1800021cc  mov     [rbx+10h], rax
0x1800021d0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800021d7  mov     rax, [rcx]
0x1800021da  mov     rax, [rax+8]
0x1800021de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e3  mov     [rsp+48h+arg_18], rbx
0x1800021e8  test    rbx, rbx
0x1800021eb  jz      short loc_180002222
0x1800021ed  lea     rcx, [rbx+20h]; this
0x1800021f1  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800021f6  xor     ecx, ecx
0x1800021f8  test    eax, eax
0x1800021fa  cmovs   ecx, eax
0x1800021fd  xor     edi, edi
0x1800021ff  test    ecx, ecx
0x180002201  cmovs   edi, ecx
0x180002204  test    edi, edi
0x180002206  jnz     short loc_180002236
0x180002208  mov     rax, [rbx]
0x18000220b  mov     r8, rsi
0x18000220e  mov     rdx, r14
0x180002211  mov     rcx, rbx
0x180002214  mov     rax, [rax]
0x180002217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221c  mov     edi, eax
0x18000221e  test    eax, eax
0x180002220  jnz     short loc_180002236
0x180002222  mov     eax, edi
0x180002224  add     rsp, 28h
0x180002228  pop     r14
0x18000222a  pop     rdi
0x18000222b  pop     rsi
0x18000222c  pop     rbx
0x18000222d  retn
0x18000222f  mov     eax, 80004003h
0x180002234  jmp     short loc_180002224
0x180002236  mov     rdx, [rbx]
0x180002239  mov     rax, [rdx+20h]
0x18000223d  mov     edx, 1
0x180002242  mov     rcx, rbx
0x180002245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000224a  jmp     short loc_180002222
0x18000224c  xor     ebx, ebx
0x18000224e  jmp     short loc_1800021E3
0x180002250  mov     rsi, [rsp+48h+arg_10]
0x180002255  mov     r14, [rsp+48h+arg_8]
0x18000225a  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000225e  mov     rbx, [rsp+48h+arg_18]
0x180002263  jmp     short loc_1800021E8
```

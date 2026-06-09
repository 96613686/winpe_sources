# CSurrogate_CreateInstance(ISurrogate * *)

- ea: `0x140004200`
- end: `0x140004345`
- name: `?CSurrogate_CreateInstance@@YAJPEAPEAUISurrogate@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct ISurrogate **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002a94`

## callees

- `0x14000190c`
- `0x140004200`
- `0x140011010`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140004297`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140004297`

## pseudocode

```c
__int64 __fastcall CSurrogate_CreateInstance(struct ISurrogate **a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  int v4; // edi
  int v6; // ebx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v2 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
LABEL_6:
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return (unsigned int)v4;
  }
  v2[3] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISurrogate>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v3 = &CSurrogate::`vftable';
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  v3[7] = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v3 + 4), 0);
  v4 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v3)(
         v3,
         &GUID_00000022_0000_0000_c000_000000000046,
         &v7);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v4 < 0 )
    goto LABEL_6;
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ISurrogate **))v7)(
         v7,
         &GUID_00000022_0000_0000_c000_000000000046,
         a1);
  if ( v6 >= 0 )
  {
    if ( v7 )
      (*(void (**)(void))(*(_QWORD *)v7 + 16LL))();
    return 0;
  }
  else
  {
    if ( v7 )
      (*(void (**)(void))(*(_QWORD *)v7 + 16LL))();
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x140004200  mov     [rsp+arg_0], rbx
0x140004205  mov     [rsp+arg_10], rsi
0x14000420a  push    rdi
0x14000420b  sub     rsp, 20h
0x14000420f  mov     rsi, rcx
0x140004212  mov     [rsp+28h+arg_8], 0
0x14000421b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140004222  mov     ecx, 50h ; 'P'; unsigned __int64
0x140004227  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000422c  mov     rbx, rax
0x14000422f  test    rax, rax
0x140004232  jnz     short loc_14000423E
0x140004234  mov     edi, 8007000Eh
0x140004239  jmp     loc_1400042CE
0x14000423e  mov     dword ptr [rax+0Ch], 1
0x140004245  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UISurrogate@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ISurrogate>::`vftable'
0x14000424c  mov     [rbx], rax
0x14000424f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140004256  test    rcx, rcx
0x140004259  jz      short loc_140004268
0x14000425b  mov     rax, [rcx]
0x14000425e  mov     rax, [rax+8]
0x140004262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004267  nop
0x140004268  lea     rax, ??_7CSurrogate@@6B@; const CSurrogate::`vftable'
0x14000426f  mov     [rbx], rax
0x140004272  mov     qword ptr [rbx+38h], 0
0x14000427a  mov     qword ptr [rbx+40h], 0
0x140004282  mov     qword ptr [rbx+48h], 0
0x14000428a  lea     rcx, [rbx+10h]; lpCriticalSection
0x14000428e  mov     dword ptr [rcx+0Ch], 0
0x140004295  xor     edx, edx; dwSpinCount
0x140004297  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000429d  nop
0x14000429e  mov     rax, [rbx]
0x1400042a1  lea     r8, [rsp+28h+arg_8]
0x1400042a6  lea     rdx, _GUID_00000022_0000_0000_c000_000000000046
0x1400042ad  mov     rcx, rbx
0x1400042b0  mov     rax, [rax]
0x1400042b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042b8  mov     edi, eax
0x1400042ba  mov     rax, [rbx]
0x1400042bd  mov     rcx, rbx
0x1400042c0  mov     rax, [rax+10h]
0x1400042c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042c9  nop
0x1400042ca  test    edi, edi
0x1400042cc  jns     short loc_1400042E8
0x1400042ce  mov     rcx, [rsp+28h+arg_8]
0x1400042d3  test    rcx, rcx
0x1400042d6  jz      short loc_1400042E4
0x1400042d8  mov     rdx, [rcx]
0x1400042db  mov     rax, [rdx+10h]
0x1400042df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042e4  mov     eax, edi
0x1400042e6  jmp     short loc_140004335
0x1400042e8  mov     rcx, [rsp+28h+arg_8]
0x1400042ed  mov     rax, [rcx]
0x1400042f0  mov     r8, rsi
0x1400042f3  lea     rdx, _GUID_00000022_0000_0000_c000_000000000046
0x1400042fa  mov     rax, [rax]
0x1400042fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004302  mov     ebx, eax
0x140004304  mov     rcx, [rsp+28h+arg_8]
0x140004309  test    eax, eax
0x14000430b  jns     short loc_140004322
0x14000430d  test    rcx, rcx
0x140004310  jz      short loc_14000431E
0x140004312  mov     rdx, [rcx]
0x140004315  mov     rax, [rdx+10h]
0x140004319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000431e  mov     eax, ebx
0x140004320  jmp     short loc_140004335
0x140004322  test    rcx, rcx
0x140004325  jz      short loc_140004333
0x140004327  mov     rax, [rcx]
0x14000432a  mov     rax, [rax+10h]
0x14000432e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004333  xor     eax, eax
0x140004335  mov     rbx, [rsp+28h+arg_0]
0x14000433a  mov     rsi, [rsp+28h+arg_10]
0x14000433f  add     rsp, 20h
0x140004343  pop     rdi
0x140004344  retn
```

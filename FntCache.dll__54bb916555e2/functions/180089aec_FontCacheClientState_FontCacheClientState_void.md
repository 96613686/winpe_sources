# FontCacheClientState::~FontCacheClientState(void)

- ea: `0x180089aec`
- end: `0x180089bd5`
- name: `??1FontCacheClientState@@UEAA@XZ`
- size: `233`
- prototype: `void __fastcall(FontCacheClientState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180089ab0`

## callees

- `0x1800124f4`
- `0x18004ff84`
- `0x180089aec`
- `0x180089bdc`
- `0x18009f220`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089bac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089bac`

## pseudocode

```c
void __fastcall FontCacheClientState::~FontCacheClientState(FontCacheClientState *this)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rdi
  _QWORD *v4; // rcx
  _QWORD *v5; // rdi
  _QWORD *v6; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-30h]

  *(_QWORD *)this = &FontCacheClientState::`vftable';
  v2 = (_QWORD *)*((_QWORD *)this + 11);
  v3 = (_QWORD *)*((_QWORD *)this + 12);
  while ( v2 != v3 && !*v2 )
    ++v2;
  v6 = v2;
  v7 = v3;
  while ( v2 != v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    PointerRegistryImpl::iterator::operator++(&v6);
    v2 = v6;
  }
  v4 = (_QWORD *)*((_QWORD *)this + 15);
  v5 = (_QWORD *)*((_QWORD *)this + 16);
  while ( v4 != v5 && !*v4 )
    ++v4;
  v6 = v4;
  v7 = v5;
  while ( v4 != v5 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    PointerRegistryImpl::iterator::operator++(&v6);
    v4 = v6;
  }
  std::vector<unsigned __int64>::~vector<unsigned __int64>((char *)this + 120);
  std::vector<unsigned __int64>::~vector<unsigned __int64>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 40);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 32);
  EventSource<ComInterfaceList<FontCacheClientState,IFontCacheClientState>,IFontCacheClientState>::~EventSource<ComInterfaceList<FontCacheClientState,IFontCacheClientState>,IFontCacheClientState>(this);
}

```

## disassembly

```asm
0x180089aec  push    rbx
0x180089aee  push    rsi
0x180089aef  push    rdi
0x180089af0  push    r14
0x180089af2  sub     rsp, 38h
0x180089af6  mov     rbx, rcx
0x180089af9  lea     rax, ??_7FontCacheClientState@@6B@; const FontCacheClientState::`vftable'
0x180089b00  mov     [rcx], rax
0x180089b03  mov     rcx, [rcx+58h]
0x180089b07  mov     rdi, [rbx+60h]
0x180089b0b  cmp     rcx, rdi
0x180089b0e  jz      short loc_180089B1C
0x180089b10  cmp     qword ptr [rcx], 0
0x180089b14  jnz     short loc_180089B1C
0x180089b16  add     rcx, 8
0x180089b1a  jmp     short loc_180089B0B
0x180089b1c  mov     [rsp+58h+var_38], rcx
0x180089b21  mov     [rsp+58h+var_30], rdi
0x180089b26  cmp     rcx, rdi
0x180089b29  jnz     short loc_180089B76
0x180089b2b  mov     rcx, [rbx+78h]
0x180089b2f  mov     rdi, [rbx+80h]
0x180089b36  cmp     rcx, rdi
0x180089b39  jz      short loc_180089B47
0x180089b3b  cmp     qword ptr [rcx], 0
0x180089b3f  jnz     short loc_180089B47
0x180089b41  add     rcx, 8
0x180089b45  jmp     short loc_180089B36
0x180089b47  mov     [rsp+58h+var_38], rcx
0x180089b4c  mov     [rsp+58h+var_30], rdi
0x180089b51  cmp     rcx, rdi
0x180089b54  jz      short loc_180089B96
0x180089b56  mov     rcx, [rcx]
0x180089b59  mov     rax, [rcx]
0x180089b5c  mov     rax, [rax+10h]
0x180089b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b65  lea     rcx, [rsp+58h+var_38]
0x180089b6a  call    ??Eiterator@PointerRegistryImpl@@QEAAAEAV01@XZ; PointerRegistryImpl::iterator::operator++(void)
0x180089b6f  mov     rcx, [rsp+58h+var_38]
0x180089b74  jmp     short loc_180089B51
0x180089b76  mov     rcx, [rcx]
0x180089b79  mov     rax, [rcx]
0x180089b7c  mov     rax, [rax+10h]
0x180089b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089b85  lea     rcx, [rsp+58h+var_38]
0x180089b8a  call    ??Eiterator@PointerRegistryImpl@@QEAAAEAV01@XZ; PointerRegistryImpl::iterator::operator++(void)
0x180089b8f  mov     rcx, [rsp+58h+var_38]
0x180089b94  jmp     short loc_180089B26
0x180089b96  lea     rcx, [rbx+78h]
0x180089b9a  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x180089b9f  lea     rcx, [rbx+58h]
0x180089ba3  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x180089ba8  lea     rcx, [rbx+30h]; lpCriticalSection
0x180089bac  call    cs:__imp_DeleteCriticalSection
0x180089bb2  lea     rcx, [rbx+28h]
0x180089bb6  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180089bbb  lea     rcx, [rbx+20h]
0x180089bbf  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180089bc4  mov     rcx, rbx
0x180089bc7  add     rsp, 38h
0x180089bcb  pop     r14
0x180089bcd  pop     rdi
0x180089bce  pop     rsi
0x180089bcf  pop     rbx
0x180089bd0  jmp     ??1?$EventSource@V?$ComInterfaceList@VFontCacheClientState@@UIFontCacheClientState@@@@UIFontCacheClientState@@@@UEAA@XZ; EventSource<ComInterfaceList<FontCacheClientState,IFontCacheClientState>,IFontCacheClientState>::~EventSource<ComInterfaceList<FontCacheClientState,IFontCacheClientState>,IFontCacheClientState>(void)
```

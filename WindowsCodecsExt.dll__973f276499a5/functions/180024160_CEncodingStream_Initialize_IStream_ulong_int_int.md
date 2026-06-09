# CEncodingStream::Initialize(IStream *,ulong,int,int)

- ea: `0x180024160`
- end: `0x180024261`
- name: `?Initialize@CEncodingStream@@UEAAJPEAUIStream@@KHH@Z`
- size: `257`
- prototype: `__int64 __fastcall(CEncodingStream *__hidden this, struct IStream *, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800171c4`
- `0x180024160`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800241ee`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800241ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002420d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002420d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800241c1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800241c1`

## pseudocode

```c
__int64 __fastcall CEncodingStream::Initialize(CEncodingStream *this, struct IStream *a2, int a3, int a4, int a5)
{
  __int64 v9; // rcx
  unsigned int v10; // ebx
  void *v11; // rbp
  HGLOBAL v12; // rax
  HRESULT StreamOnHGlobal; // eax
  __int64 v15; // rcx

  if ( (a3 & 1) != 0 && !a5 )
  {
    v9 = *((_QWORD *)this + 6);
    v10 = 0;
    v11 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 6) = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a2 + 8LL))(a2);
    goto LABEL_16;
  }
  v12 = GlobalAlloc(2u, 0);
  v11 = v12;
  if ( v12 )
  {
    StreamOnHGlobal = CreateStreamOnHGlobal(v12, 0, (LPSTREAM *)this + 6);
    v10 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
LABEL_16:
      v15 = *((_QWORD *)this + 5);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      *((_QWORD *)this + 5) = a2;
      if ( a2 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a2 + 8LL))(a2);
      *((_QWORD *)this + 4) = v11;
      *((_DWORD *)this + 6) = a3;
      *((_DWORD *)this + 7) = a4;
      return v10;
    }
    if ( g_doStackCaptures )
      DoStackCapture(StreamOnHGlobal);
    GlobalFree(v11);
  }
  else
  {
    v10 = -2147024882;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v10;
}

```

## disassembly

```asm
0x180024160  push    rbx
0x180024162  push    rbp
0x180024163  push    rsi
0x180024164  push    rdi
0x180024165  push    r14
0x180024167  push    r15
0x180024169  sub     rsp, 28h
0x18002416d  mov     r15d, r9d
0x180024170  mov     r14d, r8d
0x180024173  mov     rsi, rdx
0x180024176  mov     rdi, rcx
0x180024179  test    r8b, 1
0x18002417d  jz      short loc_1800241BC
0x18002417f  cmp     [rsp+58h+arg_20], 0
0x180024187  jnz     short loc_1800241BC
0x180024189  mov     rcx, [rcx+30h]
0x18002418d  xor     ebx, ebx
0x18002418f  xor     ebp, ebp
0x180024191  test    rcx, rcx
0x180024194  jz      short loc_1800241A2
0x180024196  mov     rax, [rcx]
0x180024199  mov     rax, [rax+10h]
0x18002419d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a2  mov     [rdi+30h], rsi
0x1800241a6  test    rsi, rsi
0x1800241a9  jz      short loc_180024226
0x1800241ab  mov     rax, [rsi]
0x1800241ae  mov     rcx, rsi
0x1800241b1  mov     rax, [rax+8]
0x1800241b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ba  jmp     short loc_180024226
0x1800241bc  xor     edx, edx; dwBytes
0x1800241be  lea     ecx, [rdx+2]; uFlags
0x1800241c1  call    cs:__imp_GlobalAlloc
0x1800241c7  mov     rbp, rax
0x1800241ca  test    rax, rax
0x1800241cd  jnz     short loc_1800241E5
0x1800241cf  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800241d5  mov     ebx, 8007000Eh
0x1800241da  jz      short loc_180024213
0x1800241dc  mov     ecx, ebx; int
0x1800241de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800241e3  jmp     short loc_180024213
0x1800241e5  lea     r8, [rdi+30h]; ppstm
0x1800241e9  xor     edx, edx; fDeleteOnRelease
0x1800241eb  mov     rcx, rbp; hGlobal
0x1800241ee  call    cs:__imp_CreateStreamOnHGlobal
0x1800241f4  mov     ebx, eax
0x1800241f6  test    eax, eax
0x1800241f8  jns     short loc_180024226
0x1800241fa  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180024201  jz      short loc_180024222
0x180024203  mov     ecx, eax; int
0x180024205  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002420a  mov     rcx, rbp; hMem
0x18002420d  call    cs:__imp_GlobalFree
0x180024213  mov     eax, ebx
0x180024215  add     rsp, 28h
0x180024219  pop     r15
0x18002421b  pop     r14
0x18002421d  pop     rdi
0x18002421e  pop     rsi
0x18002421f  pop     rbp
0x180024220  pop     rbx
0x180024221  retn
0x180024222  test    eax, eax
0x180024224  js      short loc_18002420A
0x180024226  mov     rcx, [rdi+28h]
0x18002422a  test    rcx, rcx
0x18002422d  jz      short loc_18002423B
0x18002422f  mov     rax, [rcx]
0x180024232  mov     rax, [rax+10h]
0x180024236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002423b  mov     [rdi+28h], rsi
0x18002423f  test    rsi, rsi
0x180024242  jz      short loc_180024253
0x180024244  mov     rax, [rsi]
0x180024247  mov     rcx, rsi
0x18002424a  mov     rax, [rax+8]
0x18002424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024253  mov     [rdi+20h], rbp
0x180024257  mov     [rdi+18h], r14d
0x18002425b  mov     [rdi+1Ch], r15d
0x18002425f  jmp     short loc_180024213
```

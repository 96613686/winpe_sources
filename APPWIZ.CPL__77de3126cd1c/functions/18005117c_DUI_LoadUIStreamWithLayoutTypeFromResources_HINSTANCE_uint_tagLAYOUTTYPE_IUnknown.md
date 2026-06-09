# DUI_LoadUIStreamWithLayoutTypeFromResources(HINSTANCE__ *,uint,tagLAYOUTTYPE,IUnknown * *)

- ea: `0x18005117c`
- end: `0x1800512a0`
- name: `?DUI_LoadUIStreamWithLayoutTypeFromResources@@YAJPEAUHINSTANCE__@@IW4tagLAYOUTTYPE@@PEAPEAUIUnknown@@@Z`
- size: `292`
- prototype: `int __high(HINSTANCE, unsigned int, enum tagLAYOUTTYPE, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013c50`
- `0x180042f70`

## callees

- `0x180002fc4`
- `0x1800510dc`
- `0x18005117c`
- `0x180051320`
- `0x180059010`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x1800511de`
- `SHCORE!SHCreateMemStream` at `0x1800511de`
- `SHLWAPI!__imp_QISearch` at `0x180051251`
- `SHLWAPI!__imp_QISearch` at `0x180051251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051281`

## pseudocode

```c
__int64 __fastcall DUI_LoadUIStreamWithLayoutTypeFromResources(__int64 a1, unsigned int a2, int a3, void **a4)
{
  HINSTANCE v4; // rcx
  HRESULT UIFileFromResources; // ebx
  BYTE *v8; // rsi
  __int64 v9; // rdx
  IStream *v10; // rdi
  _QWORD *v11; // rax
  void *v12; // r14
  BYTE *pInit; // [rsp+50h] [rbp+8h] BYREF

  v4 = g_hinst;
  *a4 = 0;
  pInit = 0;
  UIFileFromResources = DUI_LoadUIFileFromResources(v4, a2, (unsigned __int16 **)&pInit);
  if ( UIFileFromResources >= 0 )
  {
    v8 = pInit;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&pInit[2 * v9] );
    v10 = SHCreateMemStream(pInit, 2 * (int)v9 + 2);
    if ( v10 )
    {
      v11 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      if ( v11 )
      {
        *((_DWORD *)v11 + 4) = 1;
        *v11 = &CStreamWithLayoutType::`vftable'{for `IStream'};
        v11[1] = &CStreamWithLayoutType::`vftable'{for `ILayoutType'};
        *((_DWORD *)v11 + 5) = a3;
        v11[3] = v10;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 8LL))(v10);
        UIFileFromResources = QISearch(
                                v12,
                                &`CStreamWithLayoutType::QueryInterface'::`2'::qit,
                                &GUID_00000000_0000_0000_c000_000000000046,
                                a4);
        CStreamWithLayoutType::Release((CStreamWithLayoutType *)v12);
      }
      else
      {
        UIFileFromResources = -2147024882;
      }
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    else
    {
      UIFileFromResources = -2147024882;
    }
    LocalFree(v8);
  }
  return (unsigned int)UIFileFromResources;
}

```

## disassembly

```asm
0x18005117c  mov     rax, rsp
0x18005117f  mov     [rax+10h], rbx
0x180051183  mov     [rax+18h], rbp
0x180051187  mov     [rax+8], rcx
0x18005118b  push    rsi
0x18005118c  push    rdi
0x18005118d  push    r12
0x18005118f  push    r14
0x180051191  push    r15
0x180051193  sub     rsp, 20h
0x180051197  mov     rcx, cs:g_hinst; hModule
0x18005119e  mov     ebp, r8d
0x1800511a1  xor     r12d, r12d
0x1800511a4  lea     r8, [rax+8]; unsigned __int16 **
0x1800511a8  mov     [r9], r12
0x1800511ab  mov     r15, r9
0x1800511ae  mov     [rax+8], r12
0x1800511b2  call    ?DUI_LoadUIFileFromResources@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; DUI_LoadUIFileFromResources(HINSTANCE__ *,uint,ushort * *)
0x1800511b7  mov     ebx, eax
0x1800511b9  test    eax, eax
0x1800511bb  js      loc_180051287
0x1800511c1  mov     rsi, [rsp+48h+pInit]
0x1800511c6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800511ca  inc     rdx
0x1800511cd  cmp     [rsi+rdx*2], r12w
0x1800511d2  jnz     short loc_1800511CA
0x1800511d4  lea     edx, ds:2[rdx*2]; cbInit
0x1800511db  mov     rcx, rsi; pInit
0x1800511de  call    cs:__imp_SHCreateMemStream
0x1800511e4  mov     rdi, rax
0x1800511e7  test    rax, rax
0x1800511ea  jz      loc_180051279
0x1800511f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800511f7  mov     ecx, 20h ; ' '; unsigned __int64
0x1800511fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180051201  mov     r14, rax
0x180051204  test    rax, rax
0x180051207  jz      short loc_180051263
0x180051209  lea     rax, ??_7CStreamWithLayoutType@@6BIStream@@@; const CStreamWithLayoutType::`vftable'{for `IStream'}
0x180051210  mov     dword ptr [r14+10h], 1
0x180051218  mov     [r14], rax
0x18005121b  lea     rax, ??_7CStreamWithLayoutType@@6BILayoutType@@@; const CStreamWithLayoutType::`vftable'{for `ILayoutType'}
0x180051222  mov     [r14+8], rax
0x180051226  mov     [r14+14h], ebp
0x18005122a  mov     [r14+18h], rdi
0x18005122e  mov     rcx, [rdi]
0x180051231  mov     rax, [rcx+8]
0x180051235  mov     rcx, rdi
0x180051238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005123d  mov     r9, r15; ppv
0x180051240  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180051247  lea     rdx, ?qit@?1??QueryInterface@CStreamWithLayoutType@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18005124e  mov     rcx, r14; that
0x180051251  call    cs:__imp_QISearch
0x180051257  mov     rcx, r14; this
0x18005125a  mov     ebx, eax
0x18005125c  call    ?Release@CStreamWithLayoutType@@UEAAKXZ; CStreamWithLayoutType::Release(void)
0x180051261  jmp     short loc_180051268
0x180051263  mov     ebx, 8007000Eh
0x180051268  mov     rax, [rdi]
0x18005126b  mov     rcx, rdi
0x18005126e  mov     rax, [rax+10h]
0x180051272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051277  jmp     short loc_18005127E
0x180051279  mov     ebx, 8007000Eh
0x18005127e  mov     rcx, rsi; hMem
0x180051281  call    cs:__imp_LocalFree
0x180051287  mov     rbp, [rsp+48h+arg_10]
0x18005128c  mov     eax, ebx
0x18005128e  mov     rbx, [rsp+48h+arg_8]
0x180051293  add     rsp, 20h
0x180051297  pop     r15
0x180051299  pop     r14
0x18005129b  pop     r12
0x18005129d  pop     rdi
0x18005129e  pop     rsi
0x18005129f  retn
```

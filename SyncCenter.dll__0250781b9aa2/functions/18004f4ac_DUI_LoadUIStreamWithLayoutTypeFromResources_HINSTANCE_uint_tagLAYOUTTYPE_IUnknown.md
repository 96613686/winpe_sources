# DUI_LoadUIStreamWithLayoutTypeFromResources(HINSTANCE__ *,uint,tagLAYOUTTYPE,IUnknown * *)

- ea: `0x18004f4ac`
- end: `0x18004f5be`
- name: `?DUI_LoadUIStreamWithLayoutTypeFromResources@@YAJPEAUHINSTANCE__@@IW4tagLAYOUTTYPE@@PEAPEAUIUnknown@@@Z`
- size: `274`
- prototype: `int __high(HINSTANCE, unsigned int, enum tagLAYOUTTYPE, struct IUnknown **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180033760`

## callees

- `0x18000d5e8`
- `0x18004f40c`
- `0x18004f4ac`
- `0x18004f650`
- `0x180053010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18004f504`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18004f504`
- `SHLWAPI!__imp_QISearch` at `0x18004f579`
- `SHLWAPI!__imp_QISearch` at `0x18004f579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f5a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f5a9`

## pseudocode

```c
__int64 __fastcall DUI_LoadUIStreamWithLayoutTypeFromResources(__int64 a1, unsigned int a2, __int64 a3, void **a4)
{
  HINSTANCE v4; // rcx
  HRESULT UIFileFromResources; // ebx
  BYTE *v7; // rbp
  __int64 v8; // rdx
  IStream *v9; // rdi
  _QWORD *v10; // rax
  void *v11; // rsi
  BYTE *pInit; // [rsp+60h] [rbp+8h] BYREF

  v4 = g_hmodThisDll;
  *a4 = 0;
  pInit = 0;
  UIFileFromResources = DUI_LoadUIFileFromResources(v4, a2, (unsigned __int16 **)&pInit);
  if ( UIFileFromResources >= 0 )
  {
    v7 = pInit;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&pInit[2 * v8] );
    v9 = SHCreateMemStream(pInit, 2 * (int)v8 + 2);
    if ( v9 )
    {
      v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        *((_DWORD *)v10 + 4) = 1;
        *v10 = &CStreamWithLayoutType::`vftable'{for `IStream'};
        v10[1] = &CStreamWithLayoutType::`vftable'{for `ILayoutType'};
        *((_DWORD *)v10 + 5) = 18;
        v10[3] = v9;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 8LL))(v9);
        UIFileFromResources = QISearch(
                                v11,
                                &`CStreamWithLayoutType::QueryInterface'::`2'::qit,
                                &GUID_00000000_0000_0000_c000_000000000046,
                                a4);
        CStreamWithLayoutType::Release((CStreamWithLayoutType *)v11);
      }
      else
      {
        UIFileFromResources = -2147024882;
      }
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      UIFileFromResources = -2147024882;
    }
    LocalFree(v7);
  }
  return (unsigned int)UIFileFromResources;
}

```

## disassembly

```asm
0x18004f4ac  mov     [rsp+pInit], rcx
0x18004f4b1  push    rbx
0x18004f4b2  push    rbp
0x18004f4b3  push    rsi
0x18004f4b4  push    rdi
0x18004f4b5  push    r14
0x18004f4b7  push    r15
0x18004f4b9  sub     rsp, 28h
0x18004f4bd  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hModule
0x18004f4c4  lea     r8, [rsp+58h+pInit]; unsigned __int16 **
0x18004f4c9  xor     r15d, r15d
0x18004f4cc  mov     r14, r9
0x18004f4cf  mov     [r9], r15
0x18004f4d2  mov     [rsp+58h+pInit], r15
0x18004f4d7  call    ?DUI_LoadUIFileFromResources@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; DUI_LoadUIFileFromResources(HINSTANCE__ *,uint,ushort * *)
0x18004f4dc  mov     ebx, eax
0x18004f4de  test    eax, eax
0x18004f4e0  js      loc_18004F5AF
0x18004f4e6  mov     rbp, [rsp+58h+pInit]
0x18004f4eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004f4ef  inc     rdx
0x18004f4f2  cmp     [rbp+rdx*2+0], r15w
0x18004f4f8  jnz     short loc_18004F4EF
0x18004f4fa  lea     edx, ds:2[rdx*2]; cbInit
0x18004f501  mov     rcx, rbp; pInit
0x18004f504  call    cs:__imp_SHCreateMemStream
0x18004f50a  mov     rdi, rax
0x18004f50d  test    rax, rax
0x18004f510  jz      loc_18004F5A1
0x18004f516  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f51d  mov     ecx, 20h ; ' '; unsigned __int64
0x18004f522  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004f527  mov     rsi, rax
0x18004f52a  test    rax, rax
0x18004f52d  jz      short loc_18004F58B
0x18004f52f  lea     rax, ??_7CStreamWithLayoutType@@6BIStream@@@; const CStreamWithLayoutType::`vftable'{for `IStream'}
0x18004f536  mov     dword ptr [rsi+10h], 1
0x18004f53d  mov     [rsi], rax
0x18004f540  lea     rax, ??_7CStreamWithLayoutType@@6BILayoutType@@@; const CStreamWithLayoutType::`vftable'{for `ILayoutType'}
0x18004f547  mov     [rsi+8], rax
0x18004f54b  mov     dword ptr [rsi+14h], 12h
0x18004f552  mov     [rsi+18h], rdi
0x18004f556  mov     rcx, [rdi]
0x18004f559  mov     rax, [rcx+8]
0x18004f55d  mov     rcx, rdi
0x18004f560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f565  mov     r9, r14; ppv
0x18004f568  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18004f56f  lea     rdx, ?qit@?1??QueryInterface@CStreamWithLayoutType@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18004f576  mov     rcx, rsi; that
0x18004f579  call    cs:__imp_QISearch
0x18004f57f  mov     rcx, rsi; this
0x18004f582  mov     ebx, eax
0x18004f584  call    ?Release@CStreamWithLayoutType@@UEAAKXZ; CStreamWithLayoutType::Release(void)
0x18004f589  jmp     short loc_18004F590
0x18004f58b  mov     ebx, 8007000Eh
0x18004f590  mov     rax, [rdi]
0x18004f593  mov     rcx, rdi
0x18004f596  mov     rax, [rax+10h]
0x18004f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f59f  jmp     short loc_18004F5A6
0x18004f5a1  mov     ebx, 8007000Eh
0x18004f5a6  mov     rcx, rbp; hMem
0x18004f5a9  call    cs:__imp_LocalFree
0x18004f5af  mov     eax, ebx
0x18004f5b1  add     rsp, 28h
0x18004f5b5  pop     r15
0x18004f5b7  pop     r14
0x18004f5b9  pop     rdi
0x18004f5ba  pop     rsi
0x18004f5bb  pop     rbp
0x18004f5bc  pop     rbx
0x18004f5bd  retn
```

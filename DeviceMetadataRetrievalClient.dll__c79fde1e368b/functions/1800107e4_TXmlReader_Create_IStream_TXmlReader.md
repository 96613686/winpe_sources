# TXmlReader::Create(IStream *,TXmlReader * *)

- ea: `0x1800107e4`
- end: `0x1800108d2`
- name: `?Create@TXmlReader@@SAJPEAUIStream@@PEAPEAV1@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct IStream *, struct TXmlReader **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x180001c48`
- `0x1800107e4`
- `0x180014010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180010817`
- `XmlLite!CreateXmlReader` at `0x180010817`

## pseudocode

```c
__int64 __fastcall TXmlReader::Create(struct IStream *a1, struct TXmlReader **a2)
{
  unsigned int v4; // ebx
  struct TXmlReader *v5; // rax
  struct TXmlReader *v6; // rdi
  void *v7; // rcx
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v9 = 0;
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &v9, 0);
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, 4, 0);
    if ( !v4 )
    {
      v4 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)v9 + 24LL))(v9, a1);
      if ( !v4 )
      {
        v5 = (struct TXmlReader *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        v6 = v5;
        if ( v5 )
        {
          v7 = v9;
          *(_QWORD *)v5 = v9;
          *((_QWORD *)v5 + 1) = 0;
          *((_QWORD *)v5 + 2) = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
          *a2 = v6;
        }
        else
        {
          *a2 = 0;
          v4 = -2147024882;
        }
      }
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  return v4;
}

```

## disassembly

```asm
0x1800107e4  mov     rax, rsp
0x1800107e7  mov     [rax+8], rbx
0x1800107eb  mov     [rax+18h], rsi
0x1800107ef  push    rdi
0x1800107f0  sub     rsp, 20h
0x1800107f4  mov     rsi, rdx
0x1800107f7  mov     qword ptr [rdx], 0
0x1800107fe  mov     rdi, rcx
0x180010801  mov     qword ptr [rax+10h], 0
0x180010809  lea     rdx, [rax+10h]; ppvObject
0x18001080d  xor     r8d, r8d; pMalloc
0x180010810  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180010817  call    cs:__imp_CreateXmlReader
0x18001081d  mov     ebx, eax
0x18001081f  test    eax, eax
0x180010821  jnz     loc_1800108AA
0x180010827  mov     rcx, [rsp+28h+arg_8]
0x18001082c  lea     edx, [rbx+4]
0x18001082f  xor     r8d, r8d
0x180010832  mov     rax, [rcx]
0x180010835  mov     rax, [rax+28h]
0x180010839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083e  mov     ebx, eax
0x180010840  test    eax, eax
0x180010842  jnz     short loc_1800108AA
0x180010844  mov     rcx, [rsp+28h+arg_8]
0x180010849  mov     rdx, rdi
0x18001084c  mov     rax, [rcx]
0x18001084f  mov     rax, [rax+18h]
0x180010853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010858  mov     ebx, eax
0x18001085a  test    eax, eax
0x18001085c  jnz     short loc_1800108AA
0x18001085e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010865  lea     ecx, [rax+18h]; unsigned __int64
0x180010868  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001086d  mov     rdi, rax
0x180010870  test    rax, rax
0x180010873  jz      short loc_18001089E
0x180010875  mov     rcx, [rsp+28h+arg_8]
0x18001087a  mov     [rax], rcx
0x18001087d  mov     qword ptr [rax+8], 0
0x180010885  mov     qword ptr [rax+10h], 0
0x18001088d  mov     rdx, [rcx]
0x180010890  mov     rax, [rdx+8]
0x180010894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010899  mov     [rsi], rdi
0x18001089c  jmp     short loc_1800108AA
0x18001089e  mov     qword ptr [rsi], 0
0x1800108a5  mov     ebx, 8007000Eh
0x1800108aa  mov     rcx, [rsp+28h+arg_8]
0x1800108af  test    rcx, rcx
0x1800108b2  jz      short loc_1800108C0
0x1800108b4  mov     rax, [rcx]
0x1800108b7  mov     rax, [rax+10h]
0x1800108bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c0  mov     rsi, [rsp+28h+arg_10]
0x1800108c5  mov     eax, ebx
0x1800108c7  mov     rbx, [rsp+28h+arg_0]
0x1800108cc  add     rsp, 20h
0x1800108d0  pop     rdi
0x1800108d1  retn
```

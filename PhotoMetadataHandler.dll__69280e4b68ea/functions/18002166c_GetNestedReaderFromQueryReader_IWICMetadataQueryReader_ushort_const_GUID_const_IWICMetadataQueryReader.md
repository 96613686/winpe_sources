# GetNestedReaderFromQueryReader(IWICMetadataQueryReader *,ushort const *,_GUID const &,IWICMetadataQueryReader * *)

- ea: `0x18002166c`
- end: `0x180021763`
- name: `?GetNestedReaderFromQueryReader@@YAJPEAUIWICMetadataQueryReader@@PEBGAEBU_GUID@@PEAPEAU1@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, const unsigned __int16 *, const struct _GUID *, struct IWICMetadataQueryReader **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014640`

## callees

- `0x180016a40`
- `0x18001d2a0`
- `0x18002166c`
- `0x18002773c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021740`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021740`

## pseudocode

```c
__int64 __fastcall GetNestedReaderFromQueryReader(
        struct IWICMetadataQueryReader *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct IWICMetadataQueryReader **a4)
{
  struct IWICMetadataQueryReaderVtbl *lpVtbl; // rax
  const struct _GUID *v6; // rdx
  int v7; // ebx
  void *v9; // [rsp+20h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+28h] [rbp-38h] BYREF
  GUID Buf1; // [rsp+40h] [rbp-20h] BYREF

  *a4 = 0;
  lpVtbl = a1->lpVtbl;
  memset(&pvar, 0, sizeof(pvar));
  v7 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, const unsigned __int16 *, PROPVARIANT *))lpVtbl->GetMetadataByName)(
         a1,
         a2,
         &pvar);
  if ( v7 >= 0 )
  {
    v9 = 0;
    v7 = QueryInterfacePropVariant(&pvar, v6, &v9);
    if ( v7 >= 0 )
    {
      Buf1 = GUID_NULL;
      v7 = (*(__int64 (__fastcall **)(void *, GUID *))(*(_QWORD *)v9 + 24LL))(v9, &Buf1);
      if ( v7 >= 0 )
      {
        if ( !memcmp_0(&Buf1, &GUID_MetadataFormatXMPStruct, 0x10u) )
        {
          *a4 = (struct IWICMetadataQueryReader *)v9;
          v9 = 0;
          goto LABEL_9;
        }
        v7 = -2147418113;
      }
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    }
LABEL_9:
    PropVariantClear(&pvar);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002166c  push    rbp
0x18002166e  push    rbx
0x18002166f  push    rdi
0x180021670  mov     rbp, rsp
0x180021673  sub     rsp, 60h
0x180021677  mov     rax, cs:__security_cookie
0x18002167e  xor     rax, rsp
0x180021681  mov     [rbp+var_10], rax
0x180021685  xor     eax, eax
0x180021687  mov     qword ptr [r9], 0
0x18002168e  mov     qword ptr [rbp+pvar+10h], rax
0x180021692  lea     r8, [rbp+pvar]
0x180021696  mov     rax, [rcx]
0x180021699  xorps   xmm0, xmm0
0x18002169c  mov     rdi, r9
0x18002169f  movups  xmmword ptr [rbp+pvar], xmm0
0x1800216a3  mov     rax, [rax+28h]
0x1800216a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ac  mov     ebx, eax
0x1800216ae  test    eax, eax
0x1800216b0  js      loc_18002174C
0x1800216b6  lea     r8, [rbp+var_40]; void **
0x1800216ba  mov     [rbp+var_40], 0
0x1800216c2  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800216c6  call    ?QueryInterfacePropVariant@@YAJAEBUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; QueryInterfacePropVariant(tagPROPVARIANT const &,_GUID const &,void * *)
0x1800216cb  mov     ebx, eax
0x1800216cd  test    eax, eax
0x1800216cf  js      short loc_18002173C
0x1800216d1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800216d8  mov     rcx, [rbp+var_40]
0x1800216dc  lea     rdx, [rbp+Buf1]
0x1800216e0  movdqu  [rbp+Buf1], xmm0
0x1800216e5  mov     rax, [rcx]
0x1800216e8  mov     rax, [rax+18h]
0x1800216ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216f1  mov     ebx, eax
0x1800216f3  test    eax, eax
0x1800216f5  js      short loc_180021727
0x1800216f7  mov     r8d, 10h; Size
0x1800216fd  lea     rdx, GUID_MetadataFormatXMPStruct; Buf2
0x180021704  lea     rcx, [rbp+Buf1]; Buf1
0x180021708  call    memcmp_0
0x18002170d  test    eax, eax
0x18002170f  jnz     short loc_180021722
0x180021711  mov     rax, [rbp+var_40]
0x180021715  mov     [rdi], rax
0x180021718  mov     [rbp+var_40], 0
0x180021720  jmp     short loc_18002173C
0x180021722  mov     ebx, 8000FFFFh
0x180021727  mov     rcx, [rbp+var_40]
0x18002172b  test    rcx, rcx
0x18002172e  jz      short loc_18002173C
0x180021730  mov     rax, [rcx]
0x180021733  mov     rax, [rax+10h]
0x180021737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002173c  lea     rcx, [rbp+pvar]; pvar
0x180021740  call    cs:__imp_PropVariantClear
0x180021747  nop     dword ptr [rax+rax+00h]
0x18002174c  mov     eax, ebx
0x18002174e  mov     rcx, [rbp+var_10]
0x180021752  xor     rcx, rsp; StackCookie
0x180021755  call    __security_check_cookie
0x18002175a  add     rsp, 60h
0x18002175e  pop     rdi
0x18002175f  pop     rbx
0x180021760  pop     rbp
0x180021761  retn
```

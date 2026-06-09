# GetNestedReaderFromQueryReader(IWICMetadataQueryReader *,ushort const *,_GUID const &,IWICMetadataQueryReader * *)

- ea: `0x18002061c`
- end: `0x18002070c`
- name: `?GetNestedReaderFromQueryReader@@YAJPEAUIWICMetadataQueryReader@@PEBGAEBU_GUID@@PEAPEAU1@@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, const unsigned __int16 *, const struct _GUID *, struct IWICMetadataQueryReader **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013c88`

## callees

- `0x180016020`
- `0x18001c564`
- `0x18002061c`
- `0x18002648c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800206f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800206f0`

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
0x18002061c  push    rbp
0x18002061e  push    rbx
0x18002061f  push    rdi
0x180020620  mov     rbp, rsp
0x180020623  sub     rsp, 60h
0x180020627  mov     rax, cs:__security_cookie
0x18002062e  xor     rax, rsp
0x180020631  mov     [rbp+var_10], rax
0x180020635  xor     eax, eax
0x180020637  mov     qword ptr [r9], 0
0x18002063e  mov     qword ptr [rbp+pvar+10h], rax
0x180020642  lea     r8, [rbp+pvar]
0x180020646  mov     rax, [rcx]
0x180020649  xorps   xmm0, xmm0
0x18002064c  mov     rdi, r9
0x18002064f  movups  xmmword ptr [rbp+pvar], xmm0
0x180020653  mov     rax, [rax+28h]
0x180020657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002065c  mov     ebx, eax
0x18002065e  test    eax, eax
0x180020660  js      loc_1800206F6
0x180020666  lea     r8, [rbp+var_40]; void **
0x18002066a  mov     [rbp+var_40], 0
0x180020672  lea     rcx, [rbp+pvar]; struct tagPROPVARIANT *
0x180020676  call    ?QueryInterfacePropVariant@@YAJAEBUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; QueryInterfacePropVariant(tagPROPVARIANT const &,_GUID const &,void * *)
0x18002067b  mov     ebx, eax
0x18002067d  test    eax, eax
0x18002067f  js      short loc_1800206EC
0x180020681  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180020688  mov     rcx, [rbp+var_40]
0x18002068c  lea     rdx, [rbp+Buf1]
0x180020690  movdqu  [rbp+Buf1], xmm0
0x180020695  mov     rax, [rcx]
0x180020698  mov     rax, [rax+18h]
0x18002069c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a1  mov     ebx, eax
0x1800206a3  test    eax, eax
0x1800206a5  js      short loc_1800206D7
0x1800206a7  mov     r8d, 10h; Size
0x1800206ad  lea     rdx, GUID_MetadataFormatXMPStruct; Buf2
0x1800206b4  lea     rcx, [rbp+Buf1]; Buf1
0x1800206b8  call    memcmp_0
0x1800206bd  test    eax, eax
0x1800206bf  jnz     short loc_1800206D2
0x1800206c1  mov     rax, [rbp+var_40]
0x1800206c5  mov     [rdi], rax
0x1800206c8  mov     [rbp+var_40], 0
0x1800206d0  jmp     short loc_1800206EC
0x1800206d2  mov     ebx, 8000FFFFh
0x1800206d7  mov     rcx, [rbp+var_40]
0x1800206db  test    rcx, rcx
0x1800206de  jz      short loc_1800206EC
0x1800206e0  mov     rax, [rcx]
0x1800206e3  mov     rax, [rax+10h]
0x1800206e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206ec  lea     rcx, [rbp+pvar]; pvar
0x1800206f0  call    cs:__imp_PropVariantClear
0x1800206f6  mov     eax, ebx
0x1800206f8  mov     rcx, [rbp+var_10]
0x1800206fc  xor     rcx, rsp; StackCookie
0x1800206ff  call    __security_check_cookie
0x180020704  add     rsp, 60h
0x180020708  pop     rdi
0x180020709  pop     rbx
0x18002070a  pop     rbp
0x18002070b  retn
```

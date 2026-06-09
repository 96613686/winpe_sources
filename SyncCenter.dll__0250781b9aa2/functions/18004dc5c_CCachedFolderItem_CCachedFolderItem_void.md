# CCachedFolderItem::~CCachedFolderItem(void)

- ea: `0x18004dc5c`
- end: `0x18004dcb8`
- name: `??1CCachedFolderItem@@AEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CCachedFolderItem *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004e3e0`

## callees

- `0x18004dc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004dc85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004dc85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dc92`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004dc92`
- `USER32!DestroyIcon` at `0x18004dc7b`
- `USER32!DestroyIcon` at `0x18004dc7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18004dc9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004dc9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004dcb1`

## pseudocode

```c
void __fastcall CCachedFolderItem::~CCachedFolderItem(CCachedFolderItem *this)
{
  HICON v2; // rcx

  *(_QWORD *)this = &CCachedFolderItem::`vftable';
  v2 = (HICON)*((_QWORD *)this + 110);
  if ( v2 )
    DestroyIcon(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  PropVariantClear((PROPVARIANT *)this + 180);
  SysFreeString(*((BSTR *)this + 178));
  SysFreeString(*((BSTR *)this + 179));
}

```

## disassembly

```asm
0x18004dc5c  push    rbx
0x18004dc5e  sub     rsp, 20h
0x18004dc62  lea     rax, ??_7CCachedFolderItem@@6B@; const CCachedFolderItem::`vftable'
0x18004dc69  mov     rbx, rcx
0x18004dc6c  mov     [rcx], rax
0x18004dc6f  mov     rcx, [rcx+370h]; hIcon
0x18004dc76  test    rcx, rcx
0x18004dc79  jz      short loc_18004DC81
0x18004dc7b  call    cs:__imp_DestroyIcon
0x18004dc81  lea     rcx, [rbx+18h]; lpCriticalSection
0x18004dc85  call    cs:__imp_DeleteCriticalSection
0x18004dc8b  lea     rcx, [rbx+5A0h]; pvar
0x18004dc92  call    cs:__imp_PropVariantClear
0x18004dc98  mov     rcx, [rbx+590h]; bstrString
0x18004dc9f  call    cs:__imp_SysFreeString
0x18004dca5  mov     rcx, [rbx+598h]
0x18004dcac  add     rsp, 20h
0x18004dcb0  pop     rbx
0x18004dcb1  jmp     cs:__imp_SysFreeString
```

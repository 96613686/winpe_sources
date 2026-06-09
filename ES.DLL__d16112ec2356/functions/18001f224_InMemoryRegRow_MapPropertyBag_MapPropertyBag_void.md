# InMemoryRegRow::MapPropertyBag::~MapPropertyBag(void)

- ea: `0x18001f224`
- end: `0x18001f294`
- name: `??1MapPropertyBag@InMemoryRegRow@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(InMemoryRegRow::MapPropertyBag *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f1fc`

## callees

- `0x18001f224`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f24a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001f24a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f285`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f25c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f285`

## pseudocode

```c
void __fastcall InMemoryRegRow::MapPropertyBag::~MapPropertyBag(InMemoryRegRow::MapPropertyBag *this)
{
  __int64 i; // rbp
  void *v3; // rcx
  void *v4; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
  {
    PropVariantClear((PROPVARIANT *)(*((_QWORD *)this + 1) + 24 * i));
    v3 = *(void **)(*(_QWORD *)this + 8 * i);
    if ( v3 )
      CoTaskMemFree(v3);
  }
  CoTaskMemFree(*(LPVOID *)this);
  CoTaskMemFree(*((LPVOID *)this + 1));
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x18001f224  push    rbx
0x18001f226  push    rbp
0x18001f227  push    rsi
0x18001f228  push    rdi
0x18001f229  sub     rsp, 28h
0x18001f22d  xor     ebp, ebp
0x18001f22f  mov     rdi, rcx
0x18001f232  cmp     [rcx+10h], ebp
0x18001f235  jbe     short loc_18001F269
0x18001f237  mov     rax, [rdi+8]
0x18001f23b  lea     rcx, ds:0[rbp*2]
0x18001f243  add     rcx, rbp
0x18001f246  lea     rcx, [rax+rcx*8]; pvar
0x18001f24a  call    cs:__imp_PropVariantClear
0x18001f250  mov     rax, [rdi]
0x18001f253  mov     rcx, [rax+rbp*8]; pv
0x18001f257  test    rcx, rcx
0x18001f25a  jz      short loc_18001F262
0x18001f25c  call    cs:__imp_CoTaskMemFree
0x18001f262  inc     ebp
0x18001f264  cmp     ebp, [rdi+10h]
0x18001f267  jb      short loc_18001F237
0x18001f269  mov     rcx, [rdi]; pv
0x18001f26c  call    cs:__imp_CoTaskMemFree
0x18001f272  mov     rcx, [rdi+8]; pv
0x18001f276  call    cs:__imp_CoTaskMemFree
0x18001f27c  mov     rcx, [rdi+18h]; pv
0x18001f280  test    rcx, rcx
0x18001f283  jz      short loc_18001F28B
0x18001f285  call    cs:__imp_CoTaskMemFree
0x18001f28b  add     rsp, 28h
0x18001f28f  pop     rdi
0x18001f290  pop     rsi
0x18001f291  pop     rbp
0x18001f292  pop     rbx
0x18001f293  retn
```

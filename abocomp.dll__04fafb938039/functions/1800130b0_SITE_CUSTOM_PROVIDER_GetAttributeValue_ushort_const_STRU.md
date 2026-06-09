# SITE_CUSTOM_PROVIDER::GetAttributeValue(ushort const *,STRU *)

- ea: `0x1800130b0`
- end: `0x180013107`
- name: `?GetAttributeValue@SITE_CUSTOM_PROVIDER@@UEAAJPEBGPEAVSTRU@@@Z`
- size: `87`
- prototype: `int(SITE_CUSTOM_PROVIDER *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800130b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800130d7`
- `msvcrt!_wcsicmp` at `0x1800130d7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800130e8`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800130e8`

## pseudocode

```c
int __fastcall SITE_CUSTOM_PROVIDER::GetAttributeValue(
        SITE_CUSTOM_PROVIDER *this,
        const unsigned __int16 *a2,
        struct STRU *a3)
{
  if ( !a2 || !a3 )
    return -2147024809;
  if ( _wcsicmp(a2, L"siteName") )
    return -2147024894;
  return STRU::Copy(a3, (SITE_CUSTOM_PROVIDER *)((char *)this + 56));
}

```

## disassembly

```asm
0x1800130b0  mov     [rsp+arg_0], rbx
0x1800130b5  push    rdi
0x1800130b6  sub     rsp, 20h
0x1800130ba  mov     rbx, r8
0x1800130bd  mov     rax, rdx
0x1800130c0  mov     rdi, rcx
0x1800130c3  test    rdx, rdx
0x1800130c6  jz      short loc_1800130F7
0x1800130c8  test    rbx, rbx
0x1800130cb  jz      short loc_1800130F7
0x1800130cd  lea     rdx, aSitename; "siteName"
0x1800130d4  mov     rcx, rax; String1
0x1800130d7  call    cs:__imp__wcsicmp
0x1800130dd  test    eax, eax
0x1800130df  jnz     short loc_1800130F0
0x1800130e1  lea     rdx, [rdi+38h]
0x1800130e5  mov     rcx, rbx
0x1800130e8  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800130ee  jmp     short loc_1800130FC
0x1800130f0  mov     eax, 80070002h
0x1800130f5  jmp     short loc_1800130FC
0x1800130f7  mov     eax, 80070057h
0x1800130fc  mov     rbx, [rsp+28h+arg_0]
0x180013101  add     rsp, 20h
0x180013105  pop     rdi
0x180013106  retn
```

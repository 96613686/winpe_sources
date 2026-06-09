# Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)

- ea: `0x18000fda8`
- end: `0x18000fde9`
- name: `?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z`
- size: `65`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, REGSAM, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c430`
- `0x18000d170`
- `0x18000d560`

## callees

- `0x18000940c`
- `0x18000fd50`
- `0x18000fda8`

## string_xrefs

- `0x18000fdc9`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall Common::RegistryKey::OpenSubKeyIfExists(HKEY *this, const unsigned __int16 *a2, REGSAM a3, HKEY *a4)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = Common::RegistryKey::OpenSubKey(this, a2, a3, a4);
  v5 = v4;
  if ( (unsigned int)(v4 + 2147024894) <= 1 || v4 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
    (const char *)(unsigned int)v4,
    v7);
  return v5;
}

```

## disassembly

```asm
0x18000fda8  push    rbx; int
0x18000fdaa  sub     rsp, 20h
0x18000fdae  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000fdb3  mov     ebx, eax
0x18000fdb5  lea     ecx, [rax+7FF8FFFEh]
0x18000fdbb  cmp     ecx, 1
0x18000fdbe  jbe     short loc_18000FDE1
0x18000fdc0  test    eax, eax
0x18000fdc2  jns     short loc_18000FDE1
0x18000fdc4  mov     rcx, [rsp+28h]; this
0x18000fdc9  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\regist"...
0x18000fdd0  mov     r9d, eax; char *
0x18000fdd3  mov     edx, 0ADh; void *
0x18000fdd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fddd  mov     eax, ebx
0x18000fddf  jmp     short loc_18000FDE3
0x18000fde1  xor     eax, eax
0x18000fde3  add     rsp, 20h
0x18000fde7  pop     rbx
0x18000fde8  retn
```

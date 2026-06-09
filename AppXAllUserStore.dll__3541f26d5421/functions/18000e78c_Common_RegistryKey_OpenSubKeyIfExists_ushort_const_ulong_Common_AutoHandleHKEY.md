# Common::RegistryKey::OpenSubKeyIfExists(ushort const *,ulong,Common::AutoHandleHKEY &)

- ea: `0x18000e78c`
- end: `0x18000e81c`
- name: `?OpenSubKeyIfExists@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z`
- size: `144`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int, struct Common::AutoHandleHKEY *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ee7c`
- `0x18002900c`
- `0x180033248`
- `0x1800365e4`
- `0x1800499c4`

## callees

- `0x18000e78c`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e7f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7c7`

## string_xrefs

- `0x18000e804`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall Common::RegistryKey::OpenSubKeyIfExists(HKEY *this, const unsigned __int16 *a2, REGSAM a3, HKEY *a4)
{
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  int phkResult; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (unsigned __int64)*a4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(*a4);
  *a4 = 0;
  v8 = RegOpenKeyExW(*this, a2, 0, a3, a4);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 + 2147024894 <= 1 || (v9 & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
    (const char *)v9,
    phkResult);
  return v9;
}

```

## disassembly

```asm
0x18000e78c  push    rbx
0x18000e78e  push    rsi
0x18000e78f  push    rdi
0x18000e790  push    r14
0x18000e792  sub     rsp, 38h
0x18000e796  mov     r14, rcx
0x18000e799  mov     rbx, r9
0x18000e79c  mov     rcx, [r9]; hKey
0x18000e79f  mov     edi, r8d
0x18000e7a2  mov     rsi, rdx
0x18000e7a5  lea     rax, [rcx-1]
0x18000e7a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e7ad  jbe     short loc_18000E7F3
0x18000e7af  mov     qword ptr [rbx], 0
0x18000e7b6  mov     r9d, edi; samDesired
0x18000e7b9  mov     rcx, [r14]; hKey
0x18000e7bc  xor     r8d, r8d; ulOptions
0x18000e7bf  mov     rdx, rsi; lpSubKey
0x18000e7c2  mov     qword ptr [rsp+58h+phkResult], rbx; int
0x18000e7c7  call    cs:__imp_RegOpenKeyExW
0x18000e7cd  mov     ebx, eax
0x18000e7cf  test    eax, eax
0x18000e7d1  jle     short loc_18000E7DC
0x18000e7d3  movzx   ebx, ax
0x18000e7d6  or      ebx, 80070000h
0x18000e7dc  lea     ecx, [rbx+7FF8FFFEh]
0x18000e7e2  cmp     ecx, 1
0x18000e7e5  ja      short loc_18000E7FB
0x18000e7e7  xor     eax, eax
0x18000e7e9  add     rsp, 38h
0x18000e7ed  pop     r14
0x18000e7ef  pop     rdi
0x18000e7f0  pop     rsi
0x18000e7f1  pop     rbx
0x18000e7f2  retn
0x18000e7f3  call    cs:__imp_RegCloseKey
0x18000e7f9  jmp     short loc_18000E7AF
0x18000e7fb  test    ebx, ebx
0x18000e7fd  jns     short loc_18000E7E7
0x18000e7ff  mov     rcx, [rsp+58h]; this
0x18000e804  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\regist"...
0x18000e80b  mov     r9d, ebx; char *
0x18000e80e  mov     edx, 0ADh; void *
0x18000e813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e818  mov     eax, ebx
0x18000e81a  jmp     short loc_18000E7E9
```

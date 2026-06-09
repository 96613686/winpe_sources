# Common::RegistryKey::OpenIfExists(HKEY__ * const,ushort const *,ulong)

- ea: `0x180003da0`
- end: `0x180003e21`
- name: `?OpenIfExists@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z`
- size: `129`
- prototype: `__int64 __fastcall(Common::RegistryKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003bf0`
- `0x180014548`
- `0x180029594`
- `0x18002e280`
- `0x18002f7e0`
- `0x18003e13c`
- `0x18003ec78`
- `0x180046c78`
- `0x1800499c4`
- `0x180049bb0`

## callees

- `0x180003da0`
- `0x180007860`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003dd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003dd5`

## string_xrefs

- `0x180003dfe`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
__int64 __fastcall Common::RegistryKey::OpenIfExists(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)
{
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  int phkResult; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Common::AutoHandleCloseHKEY<HKEY__ *>(*this);
  *this = 0;
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, this);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 + 2147024894 <= 1 || (v9 & 0x80000000) == 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A,
    (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
    (const char *)v9,
    phkResult);
  return v9;
}

```

## disassembly

```asm
0x180003da0  push    rbx
0x180003da2  push    rbp
0x180003da3  push    rsi
0x180003da4  push    rdi
0x180003da5  sub     rsp, 38h
0x180003da9  mov     rbx, rcx
0x180003dac  mov     edi, r9d
0x180003daf  mov     rcx, [rcx]
0x180003db2  mov     rsi, r8
0x180003db5  mov     rbp, rdx
0x180003db8  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003dbd  mov     r9d, edi; samDesired
0x180003dc0  mov     qword ptr [rbx], 0
0x180003dc7  xor     r8d, r8d; ulOptions
0x180003dca  mov     qword ptr [rsp+58h+phkResult], rbx; int
0x180003dcf  mov     rdx, rsi; lpSubKey
0x180003dd2  mov     rcx, rbp; hKey
0x180003dd5  call    cs:__imp_RegOpenKeyExW
0x180003ddb  mov     ebx, eax
0x180003ddd  test    eax, eax
0x180003ddf  jle     short loc_180003DEA
0x180003de1  movzx   ebx, ax
0x180003de4  or      ebx, 80070000h
0x180003dea  lea     ecx, [rbx+7FF8FFFEh]
0x180003df0  cmp     ecx, 1
0x180003df3  jbe     short loc_180003E16
0x180003df5  test    ebx, ebx
0x180003df7  jns     short loc_180003E16
0x180003df9  mov     rcx, [rsp+58h]; this
0x180003dfe  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\regist"...
0x180003e05  mov     r9d, ebx; char *
0x180003e08  mov     edx, 5Ah ; 'Z'; void *
0x180003e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e12  mov     eax, ebx
0x180003e14  jmp     short loc_180003E18
0x180003e16  xor     eax, eax
0x180003e18  add     rsp, 38h
0x180003e1c  pop     rdi
0x180003e1d  pop     rsi
0x180003e1e  pop     rbp
0x180003e1f  pop     rbx
0x180003e20  retn
```

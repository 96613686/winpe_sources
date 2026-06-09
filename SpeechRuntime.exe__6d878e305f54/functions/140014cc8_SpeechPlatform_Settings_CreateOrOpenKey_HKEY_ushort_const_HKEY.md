# SpeechPlatform::Settings::CreateOrOpenKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x140014cc8`
- end: `0x140014d15`
- name: `?CreateOrOpenKey@Settings@SpeechPlatform@@YAJPEAUHKEY__@@PEBGPEAPEAU3@@Z`
- size: `77`
- prototype: `__int64 __fastcall(SpeechPlatform::Settings *__hidden this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013588`

## callees

- `0x140014cc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014cfe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140014cfe`

## pseudocode

```c
LSTATUS __fastcall SpeechPlatform::Settings::CreateOrOpenKey(
        SpeechPlatform::Settings *this,
        const WCHAR *a2,
        HKEY *a3,
        HKEY *a4)
{
  LSTATUS result; // eax

  result = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 0x102u, 0, a3, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140014cc8  mov     rax, rsp
0x140014ccb  sub     rsp, 58h
0x140014ccf  mov     qword ptr [rax-18h], 0
0x140014cd7  xor     r9d, r9d; lpClass
0x140014cda  mov     [rax-20h], r8
0x140014cde  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014ce5  mov     qword ptr [rax-28h], 0
0x140014ced  xor     r8d, r8d; Reserved
0x140014cf0  mov     dword ptr [rax-30h], 102h
0x140014cf7  mov     dword ptr [rax-38h], 0
0x140014cfe  call    cs:__imp_RegCreateKeyExW
0x140014d04  test    eax, eax
0x140014d06  jle     short loc_140014D10
0x140014d08  movzx   eax, ax
0x140014d0b  or      eax, 80070000h
0x140014d10  add     rsp, 58h
0x140014d14  retn
```

# __acrt_get_utf8_acp_compatibility_codepage(void)

- ea: `0x40f43d`
- end: `0x40f47c`
- name: `?__acrt_get_utf8_acp_compatibility_codepage@@YAIXZ`
- size: `63`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40f1e6`
- `0x40f6c4`

## callees

- `0x40ca5a`
- `0x40f43d`
- `0x4113ae`

## pseudocode

```c
int __cdecl __acrt_get_utf8_acp_compatibility_codepage()
{
  int v0; // edx
  _DWORD v2[3]; // [esp+0h] [ebp-10h] BYREF
  char v3; // [esp+Ch] [ebp-4h]

  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v2, 0);
  v0 = 65001;
  if ( *(_DWORD *)(v2[1] + 8) != 65001 )
    v0 = __acrt_AreFileApisANSI() == 0;
  if ( v3 )
    *(_DWORD *)(v2[0] + 848) &= ~2u;
  return v0;
}

```

## disassembly

```asm
0x40f43d  mov     edi, edi
0x40f43f  push    ebp
0x40f440  mov     ebp, esp
0x40f442  sub     esp, 10h
0x40f445  push    0; struct __crt_locale_pointers *
0x40f447  lea     ecx, [ebp+var_10]; this
0x40f44a  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x40f44f  mov     eax, [ebp+var_C]
0x40f452  mov     edx, 0FDE9h
0x40f457  cmp     [eax+8], edx
0x40f45a  jz      short loc_40F468
0x40f45c  call    ___acrt_AreFileApisANSI@0
0x40f461  xor     edx, edx
0x40f463  test    eax, eax
0x40f465  jnz     short loc_40F468
0x40f467  inc     edx
0x40f468  cmp     [ebp+var_4], 0
0x40f46c  jz      short loc_40F478
0x40f46e  mov     ecx, [ebp+var_10]
0x40f471  and     dword ptr [ecx+350h], 0FFFFFFFDh
0x40f478  mov     eax, edx
0x40f47a  leave
0x40f47b  retn
```

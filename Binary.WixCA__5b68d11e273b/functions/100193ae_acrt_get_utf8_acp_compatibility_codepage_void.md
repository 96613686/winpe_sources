# __acrt_get_utf8_acp_compatibility_codepage(void)

- ea: `0x100193ae`
- end: `0x100193ef`
- name: `?__acrt_get_utf8_acp_compatibility_codepage@@YAIXZ`
- size: `65`
- prototype: `unsigned int __cdecl()`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10019155`
- `0x10019637`

## callees

- `0x10013673`
- `0x100193ae`
- `0x1001a301`

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
0x100193ae  mov     edi, edi
0x100193b0  push    ebp
0x100193b1  mov     ebp, esp
0x100193b3  sub     esp, 10h
0x100193b6  push    0; struct __crt_locale_pointers *
0x100193b8  lea     ecx, [ebp+var_10]; this
0x100193bb  call    ??0_LocaleUpdate@@QAE@QAU__crt_locale_pointers@@@Z
0x100193c0  mov     eax, [ebp+var_C]
0x100193c3  mov     edx, 0FDE9h
0x100193c8  cmp     [eax+8], edx
0x100193cb  jz      short loc_100193D9
0x100193cd  call    ___acrt_AreFileApisANSI@0
0x100193d2  xor     edx, edx
0x100193d4  test    eax, eax
0x100193d6  jnz     short loc_100193D9
0x100193d8  inc     edx
0x100193d9  cmp     [ebp+var_4], 0
0x100193dd  jz      short loc_100193E9
0x100193df  mov     ecx, [ebp+var_10]
0x100193e2  and     dword ptr [ecx+350h], 0FFFFFFFDh
0x100193e9  mov     eax, edx
0x100193eb  mov     esp, ebp
0x100193ed  pop     ebp
0x100193ee  retn
```

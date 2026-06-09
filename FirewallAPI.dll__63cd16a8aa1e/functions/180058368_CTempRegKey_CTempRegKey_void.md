# CTempRegKey::~CTempRegKey(void)

- ea: `0x180058368`
- end: `0x1800583c1`
- name: `??1CTempRegKey@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CTempRegKey *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025744`
- `0x180058420`
- `0x1800587a0`
- `0x18005bb56`
- `0x18005c26e`

## callees

- `0x180058368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005839c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800583ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005839c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800583ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005838d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005838d`
- `fwbase!FwBaseFree` at `0x1800583ba`

## pseudocode

```c
void __fastcall CTempRegKey::~CTempRegKey(CTempRegKey *this)
{
  HKEY v2; // rcx
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  HKEY v5; // rcx

  *(_QWORD *)this = &CTempRegKey::`vftable';
  v2 = (HKEY)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 3);
    if ( v3 )
      RegDeleteTreeW(v2, v3);
  }
  v4 = (HKEY)*((_QWORD *)this + 2);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (HKEY)*((_QWORD *)this + 1);
  if ( v5 )
    RegCloseKey(v5);
  FwBaseFree(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x180058368  push    rbx
0x18005836a  sub     rsp, 20h
0x18005836e  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x180058375  mov     rbx, rcx
0x180058378  mov     [rcx], rax
0x18005837b  mov     rcx, [rcx+10h]; hKey
0x18005837f  test    rcx, rcx
0x180058382  jz      short loc_180058393
0x180058384  mov     rdx, [rbx+18h]; lpSubKey
0x180058388  test    rdx, rdx
0x18005838b  jz      short loc_180058393
0x18005838d  call    cs:__imp_RegDeleteTreeW
0x180058393  mov     rcx, [rbx+10h]; hKey
0x180058397  test    rcx, rcx
0x18005839a  jz      short loc_1800583A2
0x18005839c  call    cs:__imp_RegCloseKey
0x1800583a2  mov     rcx, [rbx+8]; hKey
0x1800583a6  test    rcx, rcx
0x1800583a9  jz      short loc_1800583B1
0x1800583ab  call    cs:__imp_RegCloseKey
0x1800583b1  mov     rcx, [rbx+18h]
0x1800583b5  add     rsp, 20h
0x1800583b9  pop     rbx
0x1800583ba  jmp     cs:__imp_FwBaseFree
```

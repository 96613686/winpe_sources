# DidUpdateUseSystemVolume(wchar_t const *)

- ea: `0x180020b5c`
- end: `0x180020bf6`
- name: `?DidUpdateUseSystemVolume@@YA_NPEB_W@Z`
- size: `154`
- prototype: `bool __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800330b8`

## callees

- `0x180020b5c`
- `0x18004bcd4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020b90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020b90`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020bcd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020bcd`

## pseudocode

```c
bool __fastcall DidUpdateUseSystemVolume(PCNZWCH lpString1)
{
  const wchar_t *v3; // rdx
  wchar_t *v4; // r9
  WCHAR String2[56]; // [rsp+30h] [rbp-298h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-228h] BYREF

  if ( !lpString1 )
    return 1;
  if ( GetSystemDirectoryW(Buffer, 0x105u) && (int)VolumeUtil::GetVolumeIdForPath(Buffer, v3, String2, v4) >= 0 )
    return CompareStringW(0x7Fu, 1u, lpString1, -1, String2, -1) == 2;
  return 0;
}

```

## disassembly

```asm
0x180020b5c  push    rbx
0x180020b5e  sub     rsp, 2C0h
0x180020b65  mov     rax, cs:__security_cookie
0x180020b6c  xor     rax, rsp
0x180020b6f  mov     [rsp+2C8h+var_18], rax
0x180020b77  mov     rbx, rcx
0x180020b7a  test    rcx, rcx
0x180020b7d  jnz     short loc_180020B83
0x180020b7f  mov     al, 1
0x180020b81  jmp     short loc_180020BDD
0x180020b83  mov     edx, 105h; uSize
0x180020b88  lea     rcx, [rsp+2C8h+Buffer]; lpBuffer
0x180020b90  call    cs:__imp_GetSystemDirectoryW
0x180020b96  test    eax, eax
0x180020b98  jz      short loc_180020BDB
0x180020b9a  lea     r8, [rsp+2C8h+String2]; unsigned __int64
0x180020b9f  lea     rcx, [rsp+2C8h+Buffer]; this
0x180020ba7  call    ?GetVolumeIdForPath@VolumeUtil@@YAJPEB_W_KPEA_W@Z; VolumeUtil::GetVolumeIdForPath(wchar_t const *,unsigned __int64,wchar_t *)
0x180020bac  test    eax, eax
0x180020bae  js      short loc_180020BDB
0x180020bb0  or      r9d, 0FFFFFFFFh; cchCount1
0x180020bb4  lea     rax, [rsp+2C8h+String2]
0x180020bb9  mov     [rsp+2C8h+cchCount2], r9d; cchCount2
0x180020bbe  mov     r8, rbx; lpString1
0x180020bc1  mov     [rsp+2C8h+lpString2], rax; lpString2
0x180020bc6  lea     edx, [r9+2]; dwCmpFlags
0x180020bca  lea     ecx, [rdx+7Eh]; Locale
0x180020bcd  call    cs:__imp_CompareStringW
0x180020bd3  cmp     eax, 2
0x180020bd6  setz    al
0x180020bd9  jmp     short loc_180020BDD
0x180020bdb  xor     al, al
0x180020bdd  mov     rcx, [rsp+2C8h+var_18]
0x180020be5  xor     rcx, rsp; StackCookie
0x180020be8  call    __security_check_cookie
0x180020bed  add     rsp, 2C0h
0x180020bf4  pop     rbx
0x180020bf5  retn
```

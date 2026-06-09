# NetSetupImplementation::OFFLINE_HOST::LoadLibraryWrapper(wchar_t const *,ulong)

- ea: `0x18006339c`
- end: `0x180063409`
- name: `?LoadLibraryWrapper@OFFLINE_HOST@NetSetupImplementation@@AEAAPEAUHINSTANCE__@@PEB_WK@Z`
- size: `109`
- prototype: `HINSTANCE __fastcall(NetSetupImplementation::OFFLINE_HOST *this, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180067c30`
- `0x180067c50`

## callees

- `0x180011740`
- `0x18006339c`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800633ea`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800633ea`

## pseudocode

```c
HINSTANCE __fastcall NetSetupImplementation::OFFLINE_HOST::LoadLibraryWrapper(
        NetSetupImplementation::OFFLINE_HOST *this,
        const wchar_t *a2,
        int a3)
{
  _QWORD *v4; // r8
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 15) >= 8u )
    v4 = (_QWORD *)*v4;
  swprintf_s<260>(LibFileName, L"%s\\%s", v4, a2);
  return LoadLibraryExW(LibFileName, 0, a3 | 0x800u);
}

```

## disassembly

```asm
0x18006339c  push    rbx
0x18006339e  sub     rsp, 240h
0x1800633a5  mov     rax, cs:__security_cookie
0x1800633ac  xor     rax, rsp
0x1800633af  mov     [rsp+248h+var_18], rax
0x1800633b7  mov     ebx, r8d
0x1800633ba  lea     r8, [rcx+60h]
0x1800633be  cmp     qword ptr [r8+18h], 8
0x1800633c3  jb      short loc_1800633C8
0x1800633c5  mov     r8, [r8]
0x1800633c8  mov     r9, rdx
0x1800633cb  lea     rcx, [rsp+248h+LibFileName]
0x1800633d0  lea     rdx, aSS; "%s\\%s"
0x1800633d7  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@_WPEB_WZZ; swprintf_s<260>(wchar_t (&)[260],wchar_t const *,...)
0x1800633dc  bts     ebx, 0Bh
0x1800633e0  lea     rcx, [rsp+248h+LibFileName]; lpLibFileName
0x1800633e5  mov     r8d, ebx; dwFlags
0x1800633e8  xor     edx, edx; hFile
0x1800633ea  call    cs:__imp_LoadLibraryExW
0x1800633f0  mov     rcx, [rsp+248h+var_18]
0x1800633f8  xor     rcx, rsp; StackCookie
0x1800633fb  call    __security_check_cookie
0x180063400  add     rsp, 240h
0x180063407  pop     rbx
0x180063408  retn
```

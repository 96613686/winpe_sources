# stringCmpI(wchar_t const *,wchar_t const *)

- ea: `0x140038e60`
- end: `0x140038f02`
- name: `?stringCmpI@@YAHPEB_W0@Z`
- size: `162`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, LPCWSTR lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010520`

## callees

- `0x1400053cc`
- `0x140005434`
- `0x140038e60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140038ee0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140038ee0`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x140038ea1`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x140038ea1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140038ef1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140038ef1`

## pseudocode

```c
int __fastcall stringCmpI(LPCWSTR lpString1, LPCWSTR lpString2)
{
  if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA == -1 )
    {
      `stringCmpI'::`2'::lcidSystem = GetSystemDefaultLCID();
      Init_thread_footer(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    }
  }
  if ( `stringCmpI'::`2'::lcidSystem == 1055 )
    return CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) - 2;
  else
    return lstrcmpiW(lpString1, lpString2);
}

```

## disassembly

```asm
0x140038e60  mov     [rsp+arg_0], rbx
0x140038e65  push    rdi
0x140038e66  sub     rsp, 30h
0x140038e6a  mov     rax, gs:58h
0x140038e73  mov     rdi, rcx
0x140038e76  mov     ecx, 4
0x140038e7b  mov     rbx, rdx
0x140038e7e  mov     rax, [rax]
0x140038e81  mov     eax, [rcx+rax]
0x140038e84  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, eax
0x140038e8a  jle     short loc_140038EB9
0x140038e8c  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x140038e93  call    _Init_thread_header
0x140038e98  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, 0FFFFFFFFh
0x140038e9f  jnz     short loc_140038EB9
0x140038ea1  call    cs:__imp_GetSystemDefaultLCID
0x140038ea7  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x140038eae  mov     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, eax; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x140038eb4  call    _Init_thread_footer
0x140038eb9  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x140038ec3  jnz     short loc_140038EEB
0x140038ec5  or      r9d, 0FFFFFFFFh; cchCount1
0x140038ec9  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x140038ed1  mov     r8, rdi; lpString1
0x140038ed4  mov     [rsp+38h+lpString2], rbx; lpString2
0x140038ed9  lea     edx, [r9+2]; dwCmpFlags
0x140038edd  lea     ecx, [rdx+7Eh]; Locale
0x140038ee0  call    cs:__imp_CompareStringW
0x140038ee6  sub     eax, 2
0x140038ee9  jmp     short loc_140038EF7
0x140038eeb  mov     rdx, rbx; lpString2
0x140038eee  mov     rcx, rdi; lpString1
0x140038ef1  call    cs:__imp_lstrcmpiW
0x140038ef7  mov     rbx, [rsp+38h+arg_0]
0x140038efc  add     rsp, 30h
0x140038f00  pop     rdi
0x140038f01  retn
```

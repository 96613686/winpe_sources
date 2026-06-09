# stringCmpI(wchar_t const *,wchar_t const *)

- ea: `0x1800227c4`
- end: `0x18002286e`
- name: `?stringCmpI@@YAHPEB_W0@Z`
- size: `170`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, LPCWSTR lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e700`
- `0x180020a48`

## callees

- `0x1800028c0`
- `0x180002928`
- `0x1800227c4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002280d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18002280d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002284c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002284c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002285d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002285d`

## pseudocode

```c
int __fastcall stringCmpI(LPCWSTR lpString1, LPCWSTR lpString2)
{
  if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + (unsigned int)tls_index)
                                                          + 4LL) )
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
0x1800227c4  mov     [rsp+arg_0], rbx
0x1800227c9  push    rdi
0x1800227ca  sub     rsp, 30h
0x1800227ce  mov     r8d, cs:_tls_index
0x1800227d5  mov     rdi, rcx
0x1800227d8  mov     rax, gs:58h
0x1800227e1  mov     rbx, rdx
0x1800227e4  mov     ecx, 4
0x1800227e9  mov     rax, [rax+r8*8]
0x1800227ed  mov     eax, [rcx+rax]
0x1800227f0  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, eax
0x1800227f6  jle     short loc_180022825
0x1800227f8  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x1800227ff  call    _Init_thread_header
0x180022804  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, 0FFFFFFFFh
0x18002280b  jnz     short loc_180022825
0x18002280d  call    cs:__imp_GetSystemDefaultLCID
0x180022813  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x18002281a  mov     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, eax; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180022820  call    _Init_thread_footer
0x180022825  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x18002282f  jnz     short loc_180022857
0x180022831  or      r9d, 0FFFFFFFFh; cchCount1
0x180022835  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002283d  mov     r8, rdi; lpString1
0x180022840  mov     [rsp+38h+lpString2], rbx; lpString2
0x180022845  lea     edx, [r9+2]; dwCmpFlags
0x180022849  lea     ecx, [rdx+7Eh]; Locale
0x18002284c  call    cs:__imp_CompareStringW
0x180022852  sub     eax, 2
0x180022855  jmp     short loc_180022863
0x180022857  mov     rdx, rbx; lpString2
0x18002285a  mov     rcx, rdi; lpString1
0x18002285d  call    cs:__imp_lstrcmpiW
0x180022863  mov     rbx, [rsp+38h+arg_0]
0x180022868  add     rsp, 30h
0x18002286c  pop     rdi
0x18002286d  retn
```

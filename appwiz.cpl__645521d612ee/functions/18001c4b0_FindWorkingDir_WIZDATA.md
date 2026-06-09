# FindWorkingDir(_WIZDATA *)

- ea: `0x18001c4b0`
- end: `0x18001c5c5`
- name: `?FindWorkingDir@@YAXPEAU_WIZDATA@@@Z`
- size: `277`
- prototype: `void __fastcall(struct _WIZDATA *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001c5cc`
- `0x18001ce3c`

## callees

- `0x180007828`
- `0x18000791c`
- `0x18001c4b0`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathIsPrefixW` at `0x18001c567`
- `SHLWAPI!PathIsPrefixW` at `0x18001c567`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001c520`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001c520`
- `SHLWAPI!PathIsDirectoryW` at `0x18001c4ff`
- `SHLWAPI!PathIsDirectoryW` at `0x18001c4ff`
- `SHLWAPI!PathIsUNCW` at `0x18001c4ed`
- `SHLWAPI!PathIsUNCW` at `0x18001c4ed`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001c54c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001c54c`

## pseudocode

```c
void __fastcall FindWorkingDir(struct _WIZDATA *a1)
{
  const unsigned __int16 *v2; // rsi
  unsigned __int16 *v3; // rbx
  DWORD v4; // eax
  __int64 v5; // rdi
  WCHAR Dst[264]; // [rsp+20h] [rbp-458h] BYREF
  unsigned __int16 v7[264]; // [rsp+230h] [rbp-248h] BYREF

  v2 = (const unsigned __int16 *)((char *)a1 + ((*((_DWORD *)a1 + 2) & 0x10000000) != 0 ? 0x208 : 0) + 12);
  if ( PathIsUNCW(v2) || PathIsDirectoryW(v2) )
  {
    v3 = (unsigned __int16 *)((char *)a1 + 2092);
    *((_WORD *)a1 + 1046) = 0;
  }
  else
  {
    v3 = (unsigned __int16 *)((char *)a1 + 2092);
    StringCchCopyW((unsigned __int16 *)a1 + 1046, 0x104u, v2);
    PathRemoveFileSpecW((LPWSTR)a1 + 1046);
  }
  if ( (*((_DWORD *)a1 + 2) & 0x10000000) != 0 )
  {
    v4 = ExpandEnvironmentStringsW(L"%windir%", Dst, 0x104u);
    v5 = v4;
    if ( v4 - 1 <= 0x102 )
    {
      if ( PathIsPrefixW(Dst, v3) )
      {
        StringCchCopyW(v7, 0x104u, v3);
        StringCchCopyW(v3, 0x104u, L"%windir%");
        StringCchCatW(v3, 0x104u, &Dst[v5 + 263]);
      }
    }
  }
}

```

## disassembly

```asm
0x18001c4b0  push    rbx
0x18001c4b2  push    rbp
0x18001c4b3  push    rsi
0x18001c4b4  push    rdi
0x18001c4b5  sub     rsp, 458h
0x18001c4bc  mov     rax, cs:__security_cookie
0x18001c4c3  xor     rax, rsp
0x18001c4c6  mov     [rsp+478h+var_38], rax
0x18001c4ce  mov     eax, [rcx+8]
0x18001c4d1  lea     rsi, [rcx+0Ch]
0x18001c4d5  and     eax, 10000000h
0x18001c4da  mov     rdi, rcx
0x18001c4dd  neg     eax
0x18001c4df  sbb     rax, rax
0x18001c4e2  and     eax, 208h
0x18001c4e7  add     rsi, rax
0x18001c4ea  mov     rcx, rsi; pszPath
0x18001c4ed  call    cs:__imp_PathIsUNCW
0x18001c4f3  mov     ebp, 104h
0x18001c4f8  test    eax, eax
0x18001c4fa  jnz     short loc_18001C528
0x18001c4fc  mov     rcx, rsi; pszPath
0x18001c4ff  call    cs:__imp_PathIsDirectoryW
0x18001c505  test    eax, eax
0x18001c507  jnz     short loc_18001C528
0x18001c509  lea     rbx, [rdi+82Ch]
0x18001c510  mov     r8, rsi; unsigned __int16 *
0x18001c513  mov     rcx, rbx; unsigned __int16 *
0x18001c516  mov     edx, ebp; unsigned __int64
0x18001c518  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c51d  mov     rcx, rbx; pszPath
0x18001c520  call    cs:__imp_PathRemoveFileSpecW
0x18001c526  jmp     short loc_18001C534
0x18001c528  lea     rbx, [rdi+82Ch]
0x18001c52f  xor     eax, eax
0x18001c531  mov     [rbx], ax
0x18001c534  test    dword ptr [rdi+8], 10000000h
0x18001c53b  jz      short loc_18001C5A9
0x18001c53d  mov     r8d, ebp; nSize
0x18001c540  lea     rdx, [rsp+478h+Dst]; lpDst
0x18001c545  lea     rcx, Src; "%windir%"
0x18001c54c  call    cs:__imp_ExpandEnvironmentStringsW
0x18001c552  mov     edi, eax
0x18001c554  lea     ecx, [rdi-1]
0x18001c557  cmp     ecx, 102h
0x18001c55d  ja      short loc_18001C5A9
0x18001c55f  mov     rdx, rbx; pszPath
0x18001c562  lea     rcx, [rsp+478h+Dst]; pszPrefix
0x18001c567  call    cs:__imp_PathIsPrefixW
0x18001c56d  test    eax, eax
0x18001c56f  jz      short loc_18001C5A9
0x18001c571  mov     r8, rbx; unsigned __int16 *
0x18001c574  lea     rcx, [rsp+478h+var_248]; unsigned __int16 *
0x18001c57c  mov     rdx, rbp; unsigned __int64
0x18001c57f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c584  lea     r8, Src; "%windir%"
0x18001c58b  mov     rdx, rbp; unsigned __int64
0x18001c58e  mov     rcx, rbx; unsigned __int16 *
0x18001c591  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c596  lea     r8, [rsp+rdi*2+478h+var_24A]; unsigned __int16 *
0x18001c59e  mov     rdx, rbp; unsigned __int64
0x18001c5a1  mov     rcx, rbx; unsigned __int16 *
0x18001c5a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c5a9  mov     rcx, [rsp+478h+var_38]
0x18001c5b1  xor     rcx, rsp; StackCookie
0x18001c5b4  call    __security_check_cookie
0x18001c5b9  add     rsp, 458h
0x18001c5c0  pop     rdi
0x18001c5c1  pop     rsi
0x18001c5c2  pop     rbp
0x18001c5c3  pop     rbx
0x18001c5c4  retn
```

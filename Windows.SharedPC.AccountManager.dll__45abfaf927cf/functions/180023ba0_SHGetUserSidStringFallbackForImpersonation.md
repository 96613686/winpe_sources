# SHGetUserSidStringFallbackForImpersonation

- ea: `0x180023ba0`
- end: `0x180023c93`
- name: `SHGetUserSidStringFallbackForImpersonation`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000af0c`

## callees

- `0x180018070`
- `0x1800194d0`
- `0x18002381c`
- `0x180023940`
- `0x180023a40`
- `0x180023ba0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023bed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180023bed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c72`

## pseudocode

```c
__int64 __fastcall SHGetUserSidStringFallbackForImpersonation(WCHAR *a1, void **a2, DWORD a3)
{
  int Error; // ebx
  HLOCAL v5; // r14
  unsigned __int64 v6; // rdx
  const unsigned __int16 *v7; // r15
  unsigned __int64 v8; // rdi
  __int64 v9; // rdx
  void *v10; // rcx
  unsigned __int16 **v12; // [rsp+20h] [rbp-48h]
  unsigned __int64 *v13; // [rsp+28h] [rbp-40h]
  unsigned int v14; // [rsp+30h] [rbp-38h]
  LPWSTR StringSid; // [rsp+70h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  StringSid = a1;
  *a2 = 0;
  hMem = 0;
  Error = SHQueryToken<_TOKEN_USER>(a1, (int)a2, a3, &hMem);
  if ( Error >= 0 )
  {
    v5 = hMem;
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)hMem, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      v7 = StringSid;
      v8 = -1;
      do
        ++v8;
      while ( StringSid[v8] );
      *a2 = 0;
      if ( v8 + 1 < v8 )
      {
        Error = -2147024362;
      }
      else
      {
        hMem = 0;
        Error = ULongLongMult(v8 + 1, v6, (unsigned __int64 *)&hMem);
        if ( Error >= 0 )
          Error = CTCoAllocPolicy::Alloc(v10, v9, (SIZE_T)hMem, a2);
        if ( Error >= 0 )
          StringCchCopyNExW((unsigned __int16 *)*a2, v8 + 1, v7, v8, v12, v13, v14);
      }
      LocalFree(StringSid);
    }
    LocalFree(v5);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180023ba0  mov     rax, rsp
0x180023ba3  mov     [rax+18h], rbx
0x180023ba7  mov     [rax+20h], rbp
0x180023bab  mov     [rax+8], rcx
0x180023baf  push    rsi
0x180023bb0  push    rdi
0x180023bb1  push    r12
0x180023bb3  push    r14
0x180023bb5  push    r15
0x180023bb7  sub     rsp, 40h
0x180023bbb  xor     r12d, r12d
0x180023bbe  lea     r9, [rax+10h]
0x180023bc2  mov     [rdx], r12
0x180023bc5  mov     rsi, rdx
0x180023bc8  mov     [rax+10h], r12
0x180023bcc  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180023bd1  mov     ebx, eax
0x180023bd3  test    eax, eax
0x180023bd5  js      loc_180023C78
0x180023bdb  mov     r14, [rsp+68h+hMem]
0x180023be0  lea     rdx, [rsp+68h+StringSid]; StringSid
0x180023be5  mov     [rsp+68h+StringSid], r12
0x180023bea  mov     rcx, [r14]; Sid
0x180023bed  call    cs:__imp_ConvertSidToStringSidW
0x180023bf3  test    eax, eax
0x180023bf5  jnz     short loc_180023C02
0x180023bf7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023bfc  mov     ebx, eax
0x180023bfe  test    eax, eax
0x180023c00  js      short loc_180023C6F
0x180023c02  mov     r15, [rsp+68h+StringSid]
0x180023c07  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180023c0b  inc     rdi
0x180023c0e  cmp     [r15+rdi*2], r12w
0x180023c13  jnz     short loc_180023C0B
0x180023c15  lea     rbp, [rdi+1]
0x180023c19  mov     [rsi], r12
0x180023c1c  cmp     rbp, rdi
0x180023c1f  jb      short loc_180023C5F
0x180023c21  lea     r8, [rsp+68h+hMem]; unsigned __int64 *
0x180023c26  mov     [rsp+68h+hMem], r12
0x180023c2b  mov     rcx, rbp; unsigned __int64
0x180023c2e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180023c33  mov     ebx, eax
0x180023c35  test    eax, eax
0x180023c37  js      short loc_180023C48
0x180023c39  mov     r8, [rsp+68h+hMem]; unsigned __int64
0x180023c3e  mov     r9, rsi; void **
0x180023c41  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180023c46  mov     ebx, eax
0x180023c48  test    ebx, ebx
0x180023c4a  js      short loc_180023C64
0x180023c4c  mov     rcx, [rsi]; unsigned __int16 *
0x180023c4f  mov     r9, rdi; unsigned __int64
0x180023c52  mov     r8, r15; unsigned __int16 *
0x180023c55  mov     rdx, rbp; unsigned __int64
0x180023c58  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180023c5d  jmp     short loc_180023C64
0x180023c5f  mov     ebx, 80070216h
0x180023c64  mov     rcx, [rsp+68h+StringSid]; hMem
0x180023c69  call    cs:__imp_LocalFree
0x180023c6f  mov     rcx, r14; hMem
0x180023c72  call    cs:__imp_LocalFree
0x180023c78  lea     r11, [rsp+68h+var_28]
0x180023c7d  mov     eax, ebx
0x180023c7f  mov     rbx, [r11+40h]
0x180023c83  mov     rbp, [r11+48h]
0x180023c87  mov     rsp, r11
0x180023c8a  pop     r15
0x180023c8c  pop     r14
0x180023c8e  pop     r12
0x180023c90  pop     rdi
0x180023c91  pop     rsi
0x180023c92  retn
```

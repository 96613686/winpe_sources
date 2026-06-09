# FineReaderCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x180035400`
- end: `0x1800354fa`
- name: `?FineReaderCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `250`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180001cf0`
- `0x180035198`
- `0x180035214`
- `0x180035400`
- `0x1800543c0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1800354a1`
- `ADVAPI32!RegEnumKeyExW` at `0x1800354a1`

## string_xrefs

- `0x1800354b9`: `Failed to collect fine reader license keys [%d]`
- `0x1800354c0`: `FineReaderCollect`

## pseudocode

```c
__int64 __fastcall FineReaderCollect(
        CFineReaderShim *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  int FineReaderKeys; // ebx
  DWORD v6; // ebx
  DWORD i; // edx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-B0h]
  int v12; // [rsp+58h] [rbp-A8h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v10 = 0;
  v12 = 0;
  *(_DWORD *)a1 = 0;
  cchName = 0;
  FineReaderKeys = CFineReaderShim::EnablePrivileges(a1);
  if ( FineReaderKeys
    || (v11 = a2, (FineReaderKeys = CFineReaderShim::FindFineReaderKeys((CFineReaderShim *)&v10, 0)) != 0) )
  {
    AslLogCallPrintf(1, "FineReaderCollect", 92, "Failed to collect fine reader license keys [%d]", FineReaderKeys);
    if ( FineReaderKeys > 0 )
      return (unsigned __int16)FineReaderKeys | 0x80070000;
  }
  else
  {
    v6 = 0;
    for ( i = 0; ; i = v6 )
    {
      cchName = 259;
      if ( RegEnumKeyExW(HKEY_USERS, i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      CFineReaderShim::FindFineReaderKeys((CFineReaderShim *)&v10, Name);
      ++v6;
    }
    return 0;
  }
  return (unsigned int)FineReaderKeys;
}

```

## disassembly

```asm
0x180035400  push    rbp
0x180035402  push    rbx
0x180035403  push    rsi
0x180035404  push    rdi
0x180035405  lea     rbp, [rsp-188h]
0x18003540d  sub     rsp, 288h
0x180035414  mov     rax, cs:__security_cookie
0x18003541b  xor     rax, rsp
0x18003541e  mov     [rbp+1A0h+var_30], rax
0x180035425  xor     esi, esi
0x180035427  mov     rdi, rdx
0x18003542a  mov     [rsp+2A0h+var_258], esi
0x18003542e  mov     [rsp+2A0h+var_248], esi
0x180035432  mov     [rcx], esi
0x180035434  mov     [rsp+2A0h+cchName], esi
0x180035438  call    ?EnablePrivileges@CFineReaderShim@@AEAAKXZ; CFineReaderShim::EnablePrivileges(void)
0x18003543d  mov     ebx, eax
0x18003543f  test    eax, eax
0x180035441  jnz     short loc_1800354AF
0x180035443  xor     edx, edx; unsigned __int16 *
0x180035445  mov     [rsp+2A0h+var_250], rdi
0x18003544a  lea     rcx, [rsp+2A0h+var_258]; this
0x18003544f  call    ?FindFineReaderKeys@CFineReaderShim@@AEAAKPEAG@Z; CFineReaderShim::FindFineReaderKeys(ushort *)
0x180035454  mov     ebx, eax
0x180035456  test    eax, eax
0x180035458  jnz     short loc_1800354AF
0x18003545a  mov     ebx, esi
0x18003545c  mov     edi, 103h
0x180035461  xor     edx, edx
0x180035463  jmp     short loc_180035478
0x180035465  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x18003546a  lea     rcx, [rsp+2A0h+var_258]; this
0x18003546f  call    ?FindFineReaderKeys@CFineReaderShim@@AEAAKPEAG@Z; CFineReaderShim::FindFineReaderKeys(ushort *)
0x180035474  inc     ebx
0x180035476  mov     edx, ebx; dwIndex
0x180035478  mov     [rsp+2A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003547d  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180035482  mov     [rsp+2A0h+lpcchClass], rsi; lpcchClass
0x180035487  lea     r8, [rsp+2A0h+Name]; lpName
0x18003548c  mov     [rsp+2A0h+lpClass], rsi; lpClass
0x180035491  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180035498  mov     [rsp+2A0h+lpReserved], rsi; lpReserved
0x18003549d  mov     [rsp+2A0h+cchName], edi
0x1800354a1  call    cs:__imp_RegEnumKeyExW
0x1800354a7  cmp     eax, edi
0x1800354a9  jnz     short loc_180035465
0x1800354ab  mov     ebx, esi
0x1800354ad  jmp     short loc_1800354DD
0x1800354af  mov     r8d, 5Ch ; '\'
0x1800354b5  mov     dword ptr [rsp+2A0h+lpReserved], ebx
0x1800354b9  lea     r9, aFailedToCollec; "Failed to collect fine reader license k"...
0x1800354c0  lea     rdx, aFinereadercoll; "FineReaderCollect"
0x1800354c7  lea     ecx, [r8-5Bh]
0x1800354cb  call    AslLogCallPrintf
0x1800354d0  test    ebx, ebx
0x1800354d2  jle     short loc_1800354DD
0x1800354d4  movzx   ebx, bx
0x1800354d7  or      ebx, 80070000h
0x1800354dd  mov     eax, ebx
0x1800354df  mov     rcx, [rbp+1A0h+var_30]
0x1800354e6  xor     rcx, rsp; StackCookie
0x1800354e9  call    __security_check_cookie
0x1800354ee  add     rsp, 288h
0x1800354f5  pop     rdi
0x1800354f6  pop     rsi
0x1800354f7  pop     rbx
0x1800354f8  pop     rbp
0x1800354f9  retn
```

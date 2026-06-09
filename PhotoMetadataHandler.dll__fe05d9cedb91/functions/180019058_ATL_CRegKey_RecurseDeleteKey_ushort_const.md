# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180019058`
- end: `0x180019165`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019058`
- `0x180019528`

## callees

- `0x18000f620`
- `0x18000f678`
- `0x180016020`
- `0x180018998`
- `0x180019058`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019104`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019104`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180019058  mov     [rsp-8+arg_10], rbx
0x18001905d  push    rbp
0x18001905e  push    rsi
0x18001905f  push    rdi
0x180019060  lea     rbp, [rsp-180h]
0x180019068  sub     rsp, 280h
0x18001906f  mov     rax, cs:__security_cookie
0x180019076  xor     rax, rsp
0x180019079  mov     [rbp+190h+var_20], rax
0x180019080  mov     rsi, rdx
0x180019083  mov     [rsp+290h+hKey], 0
0x18001908c  mov     r8, rdx; lpSubKey
0x18001908f  mov     [rsp+290h+var_240], 0
0x180019098  mov     rdx, [rcx]; hKey
0x18001909b  mov     rdi, rcx
0x18001909e  lea     rcx, [rsp+290h+hKey]; this
0x1800190a3  mov     [rsp+290h+var_238], 0
0x1800190ac  mov     r9d, 2001Fh; unsigned int
0x1800190b2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800190b7  mov     ebx, eax
0x1800190b9  test    eax, eax
0x1800190bb  jnz     short loc_180019137
0x1800190bd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800190c6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800190cb  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800190d0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800190d5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800190da  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800190e3  lea     r8, [rsp+290h+Name]; lpName
0x1800190e8  mov     [rsp+290h+lpClass], 0; lpClass
0x1800190f1  xor     edx, edx; dwIndex
0x1800190f3  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800190fc  mov     [rsp+290h+cchName], 100h
0x180019104  call    cs:__imp_RegEnumKeyExW
0x18001910a  lea     rcx, [rsp+290h+hKey]; this
0x18001910f  test    eax, eax
0x180019111  jnz     short loc_180019125
0x180019113  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180019118  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001911d  mov     ebx, eax
0x18001911f  test    eax, eax
0x180019121  jnz     short loc_180019137
0x180019123  jmp     short loc_1800190C6
0x180019125  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001912a  mov     rdx, rsi; unsigned __int16 *
0x18001912d  mov     rcx, rdi; this
0x180019130  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180019135  mov     ebx, eax
0x180019137  lea     rcx, [rsp+290h+hKey]; this
0x18001913c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019141  mov     eax, ebx
0x180019143  mov     rcx, [rbp+190h+var_20]
0x18001914a  xor     rcx, rsp; StackCookie
0x18001914d  call    __security_check_cookie
0x180019152  mov     rbx, [rsp+290h+arg_10]
0x18001915a  add     rsp, 280h
0x180019161  pop     rdi
0x180019162  pop     rsi
0x180019163  pop     rbp
0x180019164  retn
```

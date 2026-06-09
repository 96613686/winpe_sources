# IsROBOMode(ushort const *,int *)

- ea: `0x180095d0c`
- end: `0x180095e0c`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `256`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800323e8`

## callees

- `0x18002a028`
- `0x180095d0c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180095dad`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180095dad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095d8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095d8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095dec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095d58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, int *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  signed int DWORD; // eax
  int v9; // eax
  HKEY v10; // rcx
  int v12; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  hKey = 0;
  v4 = (const WCHAR *)DMGetKnownRegPath(1);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    DWORD = OmaDmRegistryGetDWORD(hKey, a1, L"RenewROBOSupport", (unsigned int *)&v12);
    v6 = DWORD;
    if ( DWORD == -2147024894 || DWORD == -2147023267 )
    {
      v9 = 0;
      v12 = 0;
      v6 = 0;
    }
    else
    {
      v9 = v12;
    }
    *a2 = v9;
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
  }
  else
  {
    v7 = hKey;
    hKey = 0;
    if ( v7 )
      RegCloseKey(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180095d0c  mov     rax, rsp
0x180095d0f  mov     [rax+8], rbx
0x180095d13  mov     [rax+10h], rsi
0x180095d17  push    rdi
0x180095d18  sub     rsp, 30h
0x180095d1c  mov     rdi, rdx
0x180095d1f  mov     rsi, rcx
0x180095d22  mov     dword ptr [rax+18h], 0
0x180095d29  mov     qword ptr [rax+20h], 0
0x180095d31  mov     ecx, 1
0x180095d36  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180095d3b  lea     rcx, [rsp+38h+hKey]
0x180095d40  mov     [rsp+38h+phkResult], rcx; phkResult
0x180095d45  mov     r9d, 20019h; samDesired
0x180095d4b  xor     r8d, r8d; ulOptions
0x180095d4e  mov     rdx, rax; lpSubKey
0x180095d51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095d58  call    cs:__imp_RegOpenKeyExW
0x180095d5f  nop     dword ptr [rax+rax+00h]
0x180095d64  mov     ebx, eax
0x180095d66  test    eax, eax
0x180095d68  jle     short loc_180095D73
0x180095d6a  movzx   ebx, ax
0x180095d6d  or      ebx, 80070000h
0x180095d73  test    ebx, ebx
0x180095d75  jns     short loc_180095D99
0x180095d77  mov     rcx, [rsp+38h+hKey]; hKey
0x180095d7c  mov     [rsp+38h+hKey], 0
0x180095d85  test    rcx, rcx
0x180095d88  jz      short loc_180095D97
0x180095d8a  call    cs:__imp_RegCloseKey
0x180095d91  nop     dword ptr [rax+rax+00h]
0x180095d96  nop
0x180095d97  jmp     short loc_180095DF9
0x180095d99  lea     r9, [rsp+38h+arg_10]
0x180095d9e  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x180095da5  mov     rdx, rsi
0x180095da8  mov     rcx, [rsp+38h+hKey]
0x180095dad  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180095db4  nop     dword ptr [rax+rax+00h]
0x180095db9  mov     ebx, eax
0x180095dbb  cmp     eax, 80070002h
0x180095dc0  jz      short loc_180095DCF
0x180095dc2  cmp     eax, 8007065Dh
0x180095dc7  jz      short loc_180095DCF
0x180095dc9  mov     eax, [rsp+38h+arg_10]
0x180095dcd  jmp     short loc_180095DD7
0x180095dcf  xor     eax, eax
0x180095dd1  mov     [rsp+38h+arg_10], eax
0x180095dd5  xor     ebx, ebx
0x180095dd7  mov     [rdi], eax
0x180095dd9  mov     rcx, [rsp+38h+hKey]; hKey
0x180095dde  mov     [rsp+38h+hKey], 0
0x180095de7  test    rcx, rcx
0x180095dea  jz      short loc_180095DF9
0x180095dec  call    cs:__imp_RegCloseKey
0x180095df3  nop     dword ptr [rax+rax+00h]
0x180095df8  nop
0x180095df9  mov     eax, ebx
0x180095dfb  mov     rbx, [rsp+38h+arg_0]
0x180095e00  mov     rsi, [rsp+38h+arg_8]
0x180095e05  add     rsp, 30h
0x180095e09  pop     rdi
0x180095e0a  retn
```

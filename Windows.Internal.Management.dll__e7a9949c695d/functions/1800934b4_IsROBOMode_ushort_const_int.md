# IsROBOMode(ushort const *,int *)

- ea: `0x1800934b4`
- end: `0x18009359b`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `231`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180033584`

## callees

- `0x18002b664`
- `0x1800934b4`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180093549`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180093549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009352c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093582`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009352c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093582`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093500`

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
0x1800934b4  mov     rax, rsp
0x1800934b7  mov     [rax+8], rbx
0x1800934bb  mov     [rax+10h], rsi
0x1800934bf  push    rdi
0x1800934c0  sub     rsp, 30h
0x1800934c4  mov     rdi, rdx
0x1800934c7  mov     rsi, rcx
0x1800934ca  mov     dword ptr [rax+18h], 0
0x1800934d1  mov     qword ptr [rax+20h], 0
0x1800934d9  mov     ecx, 1
0x1800934de  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800934e3  lea     rcx, [rsp+38h+hKey]
0x1800934e8  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800934ed  mov     r9d, 20019h; samDesired
0x1800934f3  xor     r8d, r8d; ulOptions
0x1800934f6  mov     rdx, rax; lpSubKey
0x1800934f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093500  call    cs:__imp_RegOpenKeyExW
0x180093506  mov     ebx, eax
0x180093508  test    eax, eax
0x18009350a  jle     short loc_180093515
0x18009350c  movzx   ebx, ax
0x18009350f  or      ebx, 80070000h
0x180093515  test    ebx, ebx
0x180093517  jns     short loc_180093535
0x180093519  mov     rcx, [rsp+38h+hKey]; hKey
0x18009351e  mov     [rsp+38h+hKey], 0
0x180093527  test    rcx, rcx
0x18009352a  jz      short loc_180093533
0x18009352c  call    cs:__imp_RegCloseKey
0x180093532  nop
0x180093533  jmp     short loc_180093589
0x180093535  lea     r9, [rsp+38h+arg_10]
0x18009353a  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x180093541  mov     rdx, rsi
0x180093544  mov     rcx, [rsp+38h+hKey]
0x180093549  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18009354f  mov     ebx, eax
0x180093551  cmp     eax, 80070002h
0x180093556  jz      short loc_180093565
0x180093558  cmp     eax, 8007065Dh
0x18009355d  jz      short loc_180093565
0x18009355f  mov     eax, [rsp+38h+arg_10]
0x180093563  jmp     short loc_18009356D
0x180093565  xor     eax, eax
0x180093567  mov     [rsp+38h+arg_10], eax
0x18009356b  xor     ebx, ebx
0x18009356d  mov     [rdi], eax
0x18009356f  mov     rcx, [rsp+38h+hKey]; hKey
0x180093574  mov     [rsp+38h+hKey], 0
0x18009357d  test    rcx, rcx
0x180093580  jz      short loc_180093589
0x180093582  call    cs:__imp_RegCloseKey
0x180093588  nop
0x180093589  mov     eax, ebx
0x18009358b  mov     rbx, [rsp+38h+arg_0]
0x180093590  mov     rsi, [rsp+38h+arg_8]
0x180093595  add     rsp, 30h
0x180093599  pop     rdi
0x18009359a  retn
```

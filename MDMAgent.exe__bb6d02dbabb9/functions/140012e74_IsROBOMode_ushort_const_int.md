# IsROBOMode(ushort const *,int *)

- ea: `0x140012e74`
- end: `0x140012f51`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000829c`

## callees

- `0x14000b784`
- `0x140012e74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012f32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012ec0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012ec0`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012ef3`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140012ef3`

## pseudocode

```c
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, int *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  signed int DWORD; // eax
  int v9; // eax
  int v11; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  hKey = 0;
  v4 = (const WCHAR *)DMGetKnownRegPath(1);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = hKey;
  if ( v6 >= 0 )
  {
    DWORD = OmaDmRegistryGetDWORD(hKey, a1, L"RenewROBOSupport", (unsigned int *)&v11);
    v6 = DWORD;
    if ( DWORD == -2147024894 || DWORD == -2147023267 )
    {
      v9 = 0;
      v11 = 0;
      v6 = 0;
    }
    else
    {
      v9 = v11;
    }
    v7 = hKey;
    *a2 = v9;
  }
  hKey = 0;
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140012e74  mov     rax, rsp
0x140012e77  mov     [rax+8], rbx
0x140012e7b  mov     [rax+10h], rsi
0x140012e7f  push    rdi
0x140012e80  sub     rsp, 30h
0x140012e84  mov     rsi, rcx
0x140012e87  mov     dword ptr [rax+18h], 0
0x140012e8e  mov     ecx, 1
0x140012e93  mov     qword ptr [rax+20h], 0
0x140012e9b  mov     rdi, rdx
0x140012e9e  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x140012ea3  lea     rcx, [rsp+38h+hKey]
0x140012ea8  mov     r9d, 20019h; samDesired
0x140012eae  mov     [rsp+38h+phkResult], rcx; phkResult
0x140012eb3  xor     r8d, r8d; ulOptions
0x140012eb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012ebd  mov     rdx, rax; lpSubKey
0x140012ec0  call    cs:__imp_RegOpenKeyExW
0x140012ec7  nop     dword ptr [rax+rax+00h]
0x140012ecc  mov     ebx, eax
0x140012ece  test    eax, eax
0x140012ed0  jle     short loc_140012EDB
0x140012ed2  movzx   ebx, ax
0x140012ed5  or      ebx, 80070000h
0x140012edb  mov     rcx, [rsp+38h+hKey]
0x140012ee0  test    ebx, ebx
0x140012ee2  js      short loc_140012F24
0x140012ee4  lea     r9, [rsp+38h+arg_10]
0x140012ee9  mov     rdx, rsi
0x140012eec  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x140012ef3  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140012efa  nop     dword ptr [rax+rax+00h]
0x140012eff  mov     ebx, eax
0x140012f01  cmp     eax, 80070002h
0x140012f06  jz      short loc_140012F15
0x140012f08  cmp     eax, 8007065Dh
0x140012f0d  jz      short loc_140012F15
0x140012f0f  mov     eax, [rsp+38h+arg_10]
0x140012f13  jmp     short loc_140012F1D
0x140012f15  xor     eax, eax
0x140012f17  mov     [rsp+38h+arg_10], eax
0x140012f1b  xor     ebx, ebx
0x140012f1d  mov     rcx, [rsp+38h+hKey]; hKey
0x140012f22  mov     [rdi], eax
0x140012f24  mov     [rsp+38h+hKey], 0
0x140012f2d  test    rcx, rcx
0x140012f30  jz      short loc_140012F3E
0x140012f32  call    cs:__imp_RegCloseKey
0x140012f39  nop     dword ptr [rax+rax+00h]
0x140012f3e  mov     rsi, [rsp+38h+arg_8]
0x140012f43  mov     eax, ebx
0x140012f45  mov     rbx, [rsp+38h+arg_0]
0x140012f4a  add     rsp, 30h
0x140012f4e  pop     rdi
0x140012f4f  retn
```

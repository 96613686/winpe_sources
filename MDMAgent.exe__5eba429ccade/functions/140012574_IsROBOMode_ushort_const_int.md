# IsROBOMode(ushort const *,int *)

- ea: `0x140012574`
- end: `0x14001263e`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007f34`

## callees

- `0x14000b288`
- `0x140012574`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012626`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400125c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400125c0`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400125ed`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400125ed`

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
0x140012574  mov     rax, rsp
0x140012577  mov     [rax+8], rbx
0x14001257b  mov     [rax+10h], rsi
0x14001257f  push    rdi
0x140012580  sub     rsp, 30h
0x140012584  mov     rsi, rcx
0x140012587  mov     dword ptr [rax+18h], 0
0x14001258e  mov     ecx, 1
0x140012593  mov     qword ptr [rax+20h], 0
0x14001259b  mov     rdi, rdx
0x14001259e  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1400125a3  lea     rcx, [rsp+38h+hKey]
0x1400125a8  mov     r9d, 20019h; samDesired
0x1400125ae  mov     [rsp+38h+phkResult], rcx; phkResult
0x1400125b3  xor     r8d, r8d; ulOptions
0x1400125b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400125bd  mov     rdx, rax; lpSubKey
0x1400125c0  call    cs:__imp_RegOpenKeyExW
0x1400125c6  mov     ebx, eax
0x1400125c8  test    eax, eax
0x1400125ca  jle     short loc_1400125D5
0x1400125cc  movzx   ebx, ax
0x1400125cf  or      ebx, 80070000h
0x1400125d5  mov     rcx, [rsp+38h+hKey]
0x1400125da  test    ebx, ebx
0x1400125dc  js      short loc_140012618
0x1400125de  lea     r9, [rsp+38h+arg_10]
0x1400125e3  mov     rdx, rsi
0x1400125e6  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x1400125ed  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400125f3  mov     ebx, eax
0x1400125f5  cmp     eax, 80070002h
0x1400125fa  jz      short loc_140012609
0x1400125fc  cmp     eax, 8007065Dh
0x140012601  jz      short loc_140012609
0x140012603  mov     eax, [rsp+38h+arg_10]
0x140012607  jmp     short loc_140012611
0x140012609  xor     eax, eax
0x14001260b  mov     [rsp+38h+arg_10], eax
0x14001260f  xor     ebx, ebx
0x140012611  mov     rcx, [rsp+38h+hKey]; hKey
0x140012616  mov     [rdi], eax
0x140012618  mov     [rsp+38h+hKey], 0
0x140012621  test    rcx, rcx
0x140012624  jz      short loc_14001262C
0x140012626  call    cs:__imp_RegCloseKey
0x14001262c  mov     rsi, [rsp+38h+arg_8]
0x140012631  mov     eax, ebx
0x140012633  mov     rbx, [rsp+38h+arg_0]
0x140012638  add     rsp, 30h
0x14001263c  pop     rdi
0x14001263d  retn
```

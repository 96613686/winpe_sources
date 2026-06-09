# IsROBOMode(ushort const *,int *)

- ea: `0x140051d84`
- end: `0x140051e5a`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c1b0`

## callees

- `0x140051d84`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051e09`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051e09`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051da9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051da9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051ddc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051ddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051e42`

## pseudocode

```c
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, int *a2)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  signed int DWORD; // eax
  int v9; // eax
  int v11; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
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
0x140051d84  mov     rax, rsp
0x140051d87  mov     [rax+8], rbx
0x140051d8b  mov     [rax+10h], rsi
0x140051d8f  push    rdi
0x140051d90  sub     rsp, 30h
0x140051d94  mov     rdi, rdx
0x140051d97  mov     dword ptr [rax+18h], 0
0x140051d9e  mov     rsi, rcx
0x140051da1  mov     qword ptr [rax+20h], 0
0x140051da9  call    cs:__imp_RtlIsStateSeparationEnabled
0x140051daf  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x140051db6  mov     r9d, 20019h; samDesired
0x140051dbc  neg     al
0x140051dbe  lea     rax, [rsp+38h+hKey]
0x140051dc3  sbb     rdx, rdx
0x140051dc6  mov     [rsp+38h+phkResult], rax; phkResult
0x140051dcb  and     edx, 8
0x140051dce  xor     r8d, r8d; ulOptions
0x140051dd1  mov     rdx, [rdx+rcx]; lpSubKey
0x140051dd5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140051ddc  call    cs:__imp_RegOpenKeyExW
0x140051de2  mov     ebx, eax
0x140051de4  test    eax, eax
0x140051de6  jle     short loc_140051DF1
0x140051de8  movzx   ebx, ax
0x140051deb  or      ebx, 80070000h
0x140051df1  mov     rcx, [rsp+38h+hKey]
0x140051df6  test    ebx, ebx
0x140051df8  js      short loc_140051E34
0x140051dfa  lea     r9, [rsp+38h+arg_10]
0x140051dff  mov     rdx, rsi
0x140051e02  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x140051e09  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140051e0f  mov     ebx, eax
0x140051e11  cmp     eax, 80070002h
0x140051e16  jz      short loc_140051E25
0x140051e18  cmp     eax, 8007065Dh
0x140051e1d  jz      short loc_140051E25
0x140051e1f  mov     eax, [rsp+38h+arg_10]
0x140051e23  jmp     short loc_140051E2D
0x140051e25  xor     eax, eax
0x140051e27  mov     [rsp+38h+arg_10], eax
0x140051e2b  xor     ebx, ebx
0x140051e2d  mov     rcx, [rsp+38h+hKey]; hKey
0x140051e32  mov     [rdi], eax
0x140051e34  mov     [rsp+38h+hKey], 0
0x140051e3d  test    rcx, rcx
0x140051e40  jz      short loc_140051E48
0x140051e42  call    cs:__imp_RegCloseKey
0x140051e48  mov     rsi, [rsp+38h+arg_8]
0x140051e4d  mov     eax, ebx
0x140051e4f  mov     rbx, [rsp+38h+arg_0]
0x140051e54  add     rsp, 30h
0x140051e58  pop     rdi
0x140051e59  retn
```

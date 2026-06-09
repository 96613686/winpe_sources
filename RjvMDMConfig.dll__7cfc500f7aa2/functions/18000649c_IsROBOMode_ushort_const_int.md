# IsROBOMode(ushort const *,int *)

- ea: `0x18000649c`
- end: `0x18000656e`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `210`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004168`

## callees

- `0x180005a38`
- `0x18000649c`
- `0x180017278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000654f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000654f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, unsigned int *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  signed int DWORD; // eax
  unsigned int v8; // eax
  HKEY v9; // rcx
  bool v10; // zf
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF
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
    DWORD = OmaDmRegistryGetDWORD(hKey, a1, L"RenewROBOSupport", &v12);
    v6 = DWORD;
    if ( DWORD == -2147024894 || DWORD == -2147023267 )
    {
      v8 = 0;
      v6 = 0;
    }
    else
    {
      v8 = v12;
    }
    *a2 = v8;
  }
  v9 = hKey;
  v10 = hKey == 0;
  hKey = 0;
  if ( !v10 )
    RegCloseKey(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000649c  mov     rax, rsp
0x18000649f  mov     [rax+8], rbx
0x1800064a3  mov     [rax+10h], rsi
0x1800064a7  push    rdi
0x1800064a8  sub     rsp, 30h
0x1800064ac  mov     rdi, rdx
0x1800064af  mov     rsi, rcx
0x1800064b2  mov     dword ptr [rax+18h], 0
0x1800064b9  mov     qword ptr [rax+20h], 0
0x1800064c1  mov     ecx, 1
0x1800064c6  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800064cb  lea     rcx, [rsp+38h+hKey]
0x1800064d0  mov     [rsp+38h+phkResult], rcx; phkResult
0x1800064d5  mov     r9d, 20019h; samDesired
0x1800064db  xor     r8d, r8d; ulOptions
0x1800064de  mov     rdx, rax; lpSubKey
0x1800064e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800064e8  call    cs:__imp_RegOpenKeyExW
0x1800064ef  nop     dword ptr [rax+rax+00h]
0x1800064f4  mov     ebx, eax
0x1800064f6  test    eax, eax
0x1800064f8  jle     short loc_180006503
0x1800064fa  movzx   ebx, ax
0x1800064fd  or      ebx, 80070000h
0x180006503  test    ebx, ebx
0x180006505  js      short loc_18000653C
0x180006507  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x18000650c  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x180006513  mov     rdx, rsi; unsigned __int16 *
0x180006516  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000651b  call    ?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180006520  mov     ebx, eax
0x180006522  cmp     eax, 80070002h
0x180006527  jz      short loc_180006536
0x180006529  cmp     eax, 8007065Dh
0x18000652e  jz      short loc_180006536
0x180006530  mov     eax, [rsp+38h+arg_10]
0x180006534  jmp     short loc_18000653A
0x180006536  xor     eax, eax
0x180006538  xor     ebx, ebx
0x18000653a  mov     [rdi], eax
0x18000653c  mov     rcx, [rsp+38h+hKey]; hKey
0x180006541  test    rcx, rcx
0x180006544  mov     [rsp+38h+hKey], 0
0x18000654d  jz      short loc_18000655B
0x18000654f  call    cs:__imp_RegCloseKey
0x180006556  nop     dword ptr [rax+rax+00h]
0x18000655b  mov     eax, ebx
0x18000655d  mov     rbx, [rsp+38h+arg_0]
0x180006562  mov     rsi, [rsp+38h+arg_8]
0x180006567  add     rsp, 30h
0x18000656b  pop     rdi
0x18000656c  retn
```

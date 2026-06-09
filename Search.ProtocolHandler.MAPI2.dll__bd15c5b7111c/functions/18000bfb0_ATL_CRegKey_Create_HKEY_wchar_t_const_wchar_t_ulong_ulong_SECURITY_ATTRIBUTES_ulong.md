# ATL::CRegKey::Create(HKEY__ *,wchar_t const *,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000bfb0`
- end: `0x18000c02f`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WPEA_WKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d0b8`
- `0x180031bdc`
- `0x180032328`
- `0x180034b8c`

## callees

- `0x18000bf84`
- `0x18000bfb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c009`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c009`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, wchar_t *a4, unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000bfb0  mov     r11, rsp
0x18000bfb3  mov     [r11+20h], r9
0x18000bfb7  push    rbx
0x18000bfb8  sub     rsp, 50h
0x18000bfbc  mov     rbx, rcx
0x18000bfbf  mov     dword ptr [r11+28h], 0
0x18000bfc7  lea     rcx, [r11+28h]
0x18000bfcb  mov     qword ptr [r11+20h], 0
0x18000bfd3  mov     [r11-18h], rcx
0x18000bfd7  mov     rax, r8
0x18000bfda  lea     rcx, [r11+20h]
0x18000bfde  mov     r10, rdx
0x18000bfe1  mov     [r11-20h], rcx
0x18000bfe5  xor     r9d, r9d; lpClass
0x18000bfe8  mov     qword ptr [r11-28h], 0
0x18000bff0  xor     r8d, r8d; Reserved
0x18000bff3  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18000bffb  mov     rdx, rax; lpSubKey
0x18000bffe  mov     rcx, r10; hKey
0x18000c001  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000c009  call    cs:__imp_RegCreateKeyExW
0x18000c00f  mov     ecx, eax
0x18000c011  test    eax, eax
0x18000c013  jnz     short loc_18000C027
0x18000c015  mov     rcx, rbx; this
0x18000c018  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c01d  mov     ecx, eax
0x18000c01f  mov     rax, [rsp+58h+arg_18]
0x18000c024  mov     [rbx], rax
0x18000c027  mov     eax, ecx
0x18000c029  add     rsp, 50h
0x18000c02d  pop     rbx
0x18000c02e  retn
```

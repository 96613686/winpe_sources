# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180018274`
- end: `0x1800182f3`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `127`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019820`
- `0x18001c710`
- `0x1800336ac`

## callees

- `0x18000de7c`
- `0x180018274`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800182cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800182cd`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *a4, unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x180018274  mov     r11, rsp
0x180018277  mov     [r11+20h], r9
0x18001827b  push    rbx
0x18001827c  sub     rsp, 50h
0x180018280  mov     rbx, rcx
0x180018283  mov     dword ptr [r11+28h], 0
0x18001828b  lea     rcx, [r11+28h]
0x18001828f  mov     qword ptr [r11+20h], 0
0x180018297  mov     [r11-18h], rcx
0x18001829b  mov     rax, r8
0x18001829e  lea     rcx, [r11+20h]
0x1800182a2  mov     r10, rdx
0x1800182a5  mov     [r11-20h], rcx
0x1800182a9  xor     r9d, r9d; lpClass
0x1800182ac  mov     qword ptr [r11-28h], 0
0x1800182b4  xor     r8d, r8d; Reserved
0x1800182b7  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x1800182bf  mov     rdx, rax; lpSubKey
0x1800182c2  mov     rcx, r10; hKey
0x1800182c5  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800182cd  call    cs:__imp_RegCreateKeyExW
0x1800182d3  mov     ecx, eax
0x1800182d5  test    eax, eax
0x1800182d7  jnz     short loc_1800182EB
0x1800182d9  mov     rcx, rbx; this
0x1800182dc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800182e1  mov     ecx, eax
0x1800182e3  mov     rax, [rsp+58h+arg_18]
0x1800182e8  mov     [rbx], rax
0x1800182eb  mov     eax, ecx
0x1800182ed  add     rsp, 50h
0x1800182f1  pop     rbx
0x1800182f2  retn
```

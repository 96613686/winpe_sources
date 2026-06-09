# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000e40c`
- end: `0x18000e48c`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e494`
- `0x180010c28`
- `0x180010d3c`

## callees

- `0x18000e40c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e460`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e460`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e474`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e474`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v6; // ecx
  HKEY v8; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v8 = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x2001Fu, 0, &v8, &a5);
  if ( !v6 )
  {
    if ( *this )
      v6 = RegCloseKey(*this);
    *this = v8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000e40c  mov     rax, rsp
0x18000e40f  mov     [rax+20h], r9
0x18000e413  push    rbx
0x18000e414  sub     rsp, 50h
0x18000e418  mov     rbx, rcx
0x18000e41b  mov     dword ptr [rax+28h], 0
0x18000e422  lea     rcx, [rax+28h]
0x18000e426  mov     qword ptr [rax+20h], 0
0x18000e42e  mov     [rax-18h], rcx
0x18000e432  mov     rdx, r8; lpSubKey
0x18000e435  lea     rcx, [rax+20h]
0x18000e439  xor     r9d, r9d; lpClass
0x18000e43c  mov     [rax-20h], rcx
0x18000e440  xor     r8d, r8d; Reserved
0x18000e443  mov     qword ptr [rax-28h], 0
0x18000e44b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e452  mov     dword ptr [rax-30h], 2001Fh
0x18000e459  mov     dword ptr [rax-38h], 0
0x18000e460  call    cs:__imp_RegCreateKeyExW
0x18000e466  mov     ecx, eax
0x18000e468  test    eax, eax
0x18000e46a  jnz     short loc_18000E484
0x18000e46c  cmp     [rbx], rcx
0x18000e46f  jz      short loc_18000E47C
0x18000e471  mov     rcx, [rbx]; hKey
0x18000e474  call    cs:__imp_RegCloseKey
0x18000e47a  mov     ecx, eax
0x18000e47c  mov     rax, [rsp+58h+arg_18]
0x18000e481  mov     [rbx], rax
0x18000e484  mov     eax, ecx
0x18000e486  add     rsp, 50h
0x18000e48a  pop     rbx
0x18000e48b  retn
```

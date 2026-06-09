# CRegKeyWrapper::Create(ATL::CRegKey *,HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180015d90`
- end: `0x180015e2a`
- name: `?Create@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `154`
- prototype: `__int64 __fastcall(CRegKeyWrapper *this, struct ATL::CRegKey *, HKEY, const unsigned __int16 *, unsigned __int16 *lpClass, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e0c4`
- `0x180015d90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015df1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015df1`

## pseudocode

```c
__int64 __fastcall CRegKeyWrapper::Create(
        CRegKeyWrapper *this,
        struct ATL::CRegKey *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        unsigned __int16 *lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a8,
        unsigned int *a9)
{
  unsigned int v10; // edx
  DWORD v12; // [rsp+50h] [rbp-18h] BYREF
  HKEY v13; // [rsp+58h] [rbp-10h] BYREF

  v12 = 0;
  v13 = 0;
  v10 = RegCreateKeyExW(a3, a4, 0, lpClass, dwOptions, samDesired, a8, &v13, &v12);
  if ( a9 )
    *a9 = v12;
  if ( !v10 )
  {
    v10 = ATL::CRegKey::Close(a2);
    *(_QWORD *)a2 = v13;
  }
  return v10;
}

```

## disassembly

```asm
0x180015d90  mov     r11, rsp
0x180015d93  push    rbx
0x180015d94  sub     rsp, 60h
0x180015d98  lea     rax, [r11-18h]
0x180015d9c  mov     [rsp+68h+var_18], 0
0x180015da4  mov     [r11-28h], rax
0x180015da8  mov     r10, r9
0x180015dab  mov     r9, [rsp+68h+lpClass]; lpClass
0x180015db3  lea     rax, [r11-10h]
0x180015db7  mov     [r11-30h], rax
0x180015dbb  mov     rcx, r8; hKey
0x180015dbe  mov     rax, [rsp+68h+arg_38]
0x180015dc6  mov     rbx, rdx
0x180015dc9  mov     [r11-38h], rax
0x180015dcd  xor     r8d, r8d; Reserved
0x180015dd0  mov     eax, [rsp+68h+arg_30]
0x180015dd7  mov     rdx, r10; lpSubKey
0x180015dda  mov     [rsp+68h+samDesired], eax; samDesired
0x180015dde  mov     eax, [rsp+68h+arg_28]
0x180015de5  mov     [rsp+68h+dwOptions], eax; dwOptions
0x180015de9  mov     qword ptr [r11-10h], 0
0x180015df1  call    cs:__imp_RegCreateKeyExW
0x180015df7  mov     edx, eax
0x180015df9  mov     rax, [rsp+68h+arg_40]
0x180015e01  test    rax, rax
0x180015e04  jz      short loc_180015E0C
0x180015e06  mov     ecx, [rsp+68h+var_18]
0x180015e0a  mov     [rax], ecx
0x180015e0c  test    edx, edx
0x180015e0e  jnz     short loc_180015E22
0x180015e10  mov     rcx, rbx; this
0x180015e13  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015e18  mov     edx, eax
0x180015e1a  mov     rax, [rsp+68h+var_10]
0x180015e1f  mov     [rbx], rax
0x180015e22  mov     eax, edx
0x180015e24  add     rsp, 60h
0x180015e28  pop     rbx
0x180015e29  retn
```

# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180016210`
- end: `0x18001628a`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `122`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018fb0`
- `0x18001f264`
- `0x180020d34`

## callees

- `0x1800161e0`
- `0x180016210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001625d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001625d`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        unsigned int a5)
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
0x180016210  mov     r11, rsp
0x180016213  mov     [r11+20h], r9
0x180016217  push    rbx
0x180016218  sub     rsp, 50h
0x18001621c  and     dword ptr [r11+28h], 0
0x180016221  mov     rbx, rcx
0x180016224  and     qword ptr [r11+20h], 0
0x180016229  lea     rcx, [r11+28h]
0x18001622d  mov     [r11-18h], rcx
0x180016231  mov     rax, r8
0x180016234  lea     rcx, [r11+20h]
0x180016238  mov     r10, rdx
0x18001623b  mov     [r11-20h], rcx
0x18001623f  xor     r9d, r9d; lpClass
0x180016242  and     qword ptr [r11-28h], 0
0x180016247  xor     r8d, r8d; Reserved
0x18001624a  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180016252  mov     rdx, rax; lpSubKey
0x180016255  and     [rsp+58h+var_38], 0
0x18001625a  mov     rcx, r10; hKey
0x18001625d  call    cs:__imp_RegCreateKeyExW
0x180016264  nop     dword ptr [rax+rax+00h]
0x180016269  mov     ecx, eax
0x18001626b  test    eax, eax
0x18001626d  jnz     short loc_180016281
0x18001626f  mov     rcx, rbx; this
0x180016272  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180016277  mov     ecx, eax
0x180016279  mov     rax, [rsp+58h+arg_18]
0x18001627e  mov     [rbx], rax
0x180016281  mov     eax, ecx
0x180016283  add     rsp, 50h
0x180016287  pop     rbx
0x180016288  retn
```

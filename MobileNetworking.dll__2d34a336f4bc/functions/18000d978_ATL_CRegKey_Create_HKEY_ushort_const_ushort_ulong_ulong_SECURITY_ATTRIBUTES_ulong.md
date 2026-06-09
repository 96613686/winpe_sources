# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000d978`
- end: `0x18000d9f8`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, REGSAM samDesired)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ce0`
- `0x18000eac4`
- `0x18000eda0`
- `0x18000f160`

## callees

- `0x180008cb0`
- `0x18000d978`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d9d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d9d2`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        REGSAM samDesired)
{
  unsigned int v7; // ecx
  HKEY v9; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v9 = 0;
  v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, samDesired, 0, &v9, &a5);
  if ( !v7 )
  {
    v7 = ATL::CRegKey::Close(this);
    *this = v9;
  }
  return v7;
}

```

## disassembly

```asm
0x18000d978  mov     r11, rsp
0x18000d97b  mov     [r11+20h], r9
0x18000d97f  push    rbx
0x18000d980  sub     rsp, 50h
0x18000d984  mov     rdx, r8; lpSubKey
0x18000d987  mov     rbx, rcx
0x18000d98a  mov     dword ptr [r11+28h], 0
0x18000d992  mov     qword ptr [r11+20h], 0
0x18000d99a  lea     rax, [r11+28h]
0x18000d99e  mov     [r11-18h], rax
0x18000d9a2  lea     rax, [r11+20h]
0x18000d9a6  mov     [r11-20h], rax
0x18000d9aa  mov     qword ptr [r11-28h], 0
0x18000d9b2  mov     eax, [rsp+58h+arg_28]
0x18000d9b9  mov     [rsp+58h+samDesired], eax; samDesired
0x18000d9bd  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000d9c5  xor     r9d, r9d; lpClass
0x18000d9c8  xor     r8d, r8d; Reserved
0x18000d9cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d9d2  call    cs:__imp_RegCreateKeyExW
0x18000d9d8  mov     ecx, eax
0x18000d9da  test    eax, eax
0x18000d9dc  jnz     short loc_18000D9F0
0x18000d9de  mov     rcx, rbx; this
0x18000d9e1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d9e6  mov     ecx, eax
0x18000d9e8  mov     rax, [rsp+58h+arg_18]
0x18000d9ed  mov     [rbx], rax
0x18000d9f0  mov     eax, ecx
0x18000d9f2  add     rsp, 50h
0x18000d9f6  pop     rbx
0x18000d9f7  retn
```

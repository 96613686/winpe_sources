# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x140006aa4`
- end: `0x140006b25`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `129`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400074b8`

## callees

- `0x140006a78`
- `0x140006aa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006aff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006aff`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *a7)
{
  unsigned int v8; // ecx
  HKEY v10; // [rsp+78h] [rbp+20h] BYREF

  a5 = 0;
  v10 = 0;
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0xF003Fu, a7, &v10, &a5);
  if ( !v8 )
  {
    v8 = ATL::CRegKey::Close(this);
    *this = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x140006aa4  mov     r11, rsp
0x140006aa7  mov     [r11+20h], r9
0x140006aab  push    rbx
0x140006aac  sub     rsp, 50h
0x140006ab0  lea     rax, [r11+28h]
0x140006ab4  mov     dword ptr [r11+28h], 0
0x140006abc  mov     [r11-18h], rax
0x140006ac0  mov     rdx, r8; lpSubKey
0x140006ac3  lea     rax, [r11+20h]
0x140006ac7  mov     qword ptr [r11+20h], 0
0x140006acf  mov     [r11-20h], rax
0x140006ad3  mov     rbx, rcx
0x140006ad6  mov     rax, [rsp+58h+arg_30]
0x140006ade  xor     r9d, r9d; lpClass
0x140006ae1  mov     [r11-28h], rax
0x140006ae5  xor     r8d, r8d; Reserved
0x140006ae8  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x140006af0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006af7  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140006aff  call    cs:__imp_RegCreateKeyExW
0x140006b05  mov     ecx, eax
0x140006b07  test    eax, eax
0x140006b09  jnz     short loc_140006B1D
0x140006b0b  mov     rcx, rbx; this
0x140006b0e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140006b13  mov     ecx, eax
0x140006b15  mov     rax, [rsp+58h+arg_18]
0x140006b1a  mov     [rbx], rax
0x140006b1d  mov     eax, ecx
0x140006b1f  add     rsp, 50h
0x140006b23  pop     rbx
0x140006b24  retn
```

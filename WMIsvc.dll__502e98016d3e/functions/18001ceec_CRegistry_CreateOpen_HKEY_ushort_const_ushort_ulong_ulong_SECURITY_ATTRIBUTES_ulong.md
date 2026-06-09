# CRegistry::CreateOpen(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18001ceec`
- end: `0x18001d02b`
- name: `?CreateOpen@CRegistry@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `319`
- prototype: `int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800174ec`

## callees

- `0x18000354c`
- `0x18001ceec`
- `0x18001d034`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cf69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001cf69`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001cffe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001cffe`

## pseudocode

```c
LSTATUS __fastcall CRegistry::CreateOpen(
        CRegistry *this,
        HKEY a2,
        WCHAR *a3,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        unsigned int *a8)
{
  HKEY *phkResult; // r15
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+90h] [rbp+8h] BYREF

  phkResult = (HKEY *)((char *)this + 8);
  dwDisposition = 0;
  if ( *((_QWORD *)this + 1) )
    CRegistry::PrepareToReOpen(this);
  *(_QWORD *)this = a2;
  result = RegCreateKeyExW(a2, a3, 0, a4, dwOptions, samDesired, lpSecurityAttributes, phkResult, &dwDisposition);
  if ( !result )
  {
    if ( a8 )
      *a8 = dwDisposition;
    RegQueryInfoKeyW(
      *phkResult,
      (LPWSTR)this + 19,
      (LPDWORD)this + 140,
      0,
      (LPDWORD)this + 141,
      (LPDWORD)this + 142,
      (LPDWORD)this + 143,
      (LPDWORD)this + 144,
      (LPDWORD)this + 145,
      (LPDWORD)this + 146,
      (LPDWORD)this + 147,
      (PFILETIME)this + 74);
    CHString::operator=((CRegistry *)((char *)this + 24), a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ceec  mov     rax, rsp
0x18001ceef  mov     [rax+10h], rbx
0x18001cef3  mov     [rax+18h], rbp
0x18001cef7  push    rsi
0x18001cef8  push    rdi
0x18001cef9  push    r12
0x18001cefb  push    r14
0x18001cefd  push    r15
0x18001ceff  sub     rsp, 60h
0x18001cf03  lea     r15, [rcx+8]
0x18001cf07  mov     dword ptr [rax+8], 0
0x18001cf0e  cmp     qword ptr [r15], 0
0x18001cf12  mov     rdi, r9
0x18001cf15  mov     r12, r8
0x18001cf18  mov     rbx, rdx
0x18001cf1b  mov     r14, rcx
0x18001cf1e  jz      short loc_18001CF25
0x18001cf20  call    ?PrepareToReOpen@CRegistry@@AEAAXXZ; CRegistry::PrepareToReOpen(void)
0x18001cf25  lea     rax, [rsp+88h+dwDisposition]
0x18001cf2d  mov     [r14], rbx
0x18001cf30  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x18001cf35  mov     r9, rdi; lpClass
0x18001cf38  mov     rax, [rsp+88h+arg_30]
0x18001cf40  xor     r8d, r8d; Reserved
0x18001cf43  mov     [rsp+88h+phkResult], r15; phkResult
0x18001cf48  mov     rdx, r12; lpSubKey
0x18001cf4b  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001cf50  mov     rcx, rbx; hKey
0x18001cf53  mov     eax, [rsp+88h+arg_28]
0x18001cf5a  mov     [rsp+88h+samDesired], eax; samDesired
0x18001cf5e  mov     eax, [rsp+88h+arg_20]
0x18001cf65  mov     [rsp+88h+dwOptions], eax; dwOptions
0x18001cf69  call    cs:__imp_RegCreateKeyExW
0x18001cf6f  test    eax, eax
0x18001cf71  jnz     loc_18001D012
0x18001cf77  mov     rcx, [rsp+88h+arg_38]
0x18001cf7f  test    rcx, rcx
0x18001cf82  jz      short loc_18001CF8D
0x18001cf84  mov     eax, [rsp+88h+dwDisposition]
0x18001cf8b  mov     [rcx], eax
0x18001cf8d  mov     rcx, [r15]; hKey
0x18001cf90  lea     rax, [r14+250h]
0x18001cf97  mov     [rsp+88h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001cf9c  lea     r9, [r14+24Ch]
0x18001cfa3  mov     [rsp+88h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x18001cfa8  lea     r10, [r14+248h]
0x18001cfaf  mov     [rsp+88h+lpcbMaxValueLen], r10; lpcbMaxValueLen
0x18001cfb4  lea     r11, [r14+244h]
0x18001cfbb  mov     [rsp+88h+lpdwDisposition], r11; lpcbMaxValueNameLen
0x18001cfc0  lea     rbx, [r14+240h]
0x18001cfc7  mov     [rsp+88h+phkResult], rbx; lpcValues
0x18001cfcc  lea     rdi, [r14+23Ch]
0x18001cfd3  mov     [rsp+88h+lpSecurityAttributes], rdi; lpcbMaxClassLen
0x18001cfd8  lea     rsi, [r14+238h]
0x18001cfdf  lea     rbp, [r14+234h]
0x18001cfe6  mov     qword ptr [rsp+88h+samDesired], rsi; lpcbMaxSubKeyLen
0x18001cfeb  lea     r8, [r14+230h]; lpcchClass
0x18001cff2  mov     qword ptr [rsp+88h+dwOptions], rbp; lpcSubKeys
0x18001cff7  lea     rdx, [r14+26h]; lpClass
0x18001cffb  xor     r9d, r9d; lpReserved
0x18001cffe  call    cs:__imp_RegQueryInfoKeyW
0x18001d004  lea     rcx, [r14+18h]; this
0x18001d008  mov     rdx, r12; unsigned __int16 *
0x18001d00b  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x18001d010  xor     eax, eax
0x18001d012  lea     r11, [rsp+88h+var_28]
0x18001d017  mov     rbx, [r11+38h]
0x18001d01b  mov     rbp, [r11+40h]
0x18001d01f  mov     rsp, r11
0x18001d022  pop     r15
0x18001d024  pop     r14
0x18001d026  pop     r12
0x18001d028  pop     rdi
0x18001d029  pop     rsi
0x18001d02a  retn
```

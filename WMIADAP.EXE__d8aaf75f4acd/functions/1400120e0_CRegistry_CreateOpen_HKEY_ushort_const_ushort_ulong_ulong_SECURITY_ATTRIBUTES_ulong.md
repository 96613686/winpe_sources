# CRegistry::CreateOpen(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400120e0`
- end: `0x14001221f`
- name: `?CreateOpen@CRegistry@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `319`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, WCHAR *, unsigned __int16 *, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f91c`

## callees

- `0x140010190`
- `0x1400120e0`
- `0x1400134b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001215d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001215d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400121f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400121f2`

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
0x1400120e0  mov     rax, rsp
0x1400120e3  mov     [rax+10h], rbx
0x1400120e7  mov     [rax+18h], rbp
0x1400120eb  push    rsi
0x1400120ec  push    rdi
0x1400120ed  push    r12
0x1400120ef  push    r14
0x1400120f1  push    r15
0x1400120f3  sub     rsp, 60h
0x1400120f7  lea     r15, [rcx+8]
0x1400120fb  mov     dword ptr [rax+8], 0
0x140012102  cmp     qword ptr [r15], 0
0x140012106  mov     rdi, r9
0x140012109  mov     r12, r8
0x14001210c  mov     rbx, rdx
0x14001210f  mov     r14, rcx
0x140012112  jz      short loc_140012119
0x140012114  call    ?PrepareToReOpen@CRegistry@@AEAAXXZ; CRegistry::PrepareToReOpen(void)
0x140012119  lea     rax, [rsp+88h+dwDisposition]
0x140012121  mov     [r14], rbx
0x140012124  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x140012129  mov     r9, rdi; lpClass
0x14001212c  mov     rax, [rsp+88h+arg_30]
0x140012134  xor     r8d, r8d; Reserved
0x140012137  mov     [rsp+88h+phkResult], r15; phkResult
0x14001213c  mov     rdx, r12; lpSubKey
0x14001213f  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140012144  mov     rcx, rbx; hKey
0x140012147  mov     eax, [rsp+88h+arg_28]
0x14001214e  mov     [rsp+88h+samDesired], eax; samDesired
0x140012152  mov     eax, [rsp+88h+arg_20]
0x140012159  mov     [rsp+88h+dwOptions], eax; dwOptions
0x14001215d  call    cs:__imp_RegCreateKeyExW
0x140012163  test    eax, eax
0x140012165  jnz     loc_140012206
0x14001216b  mov     rcx, [rsp+88h+arg_38]
0x140012173  test    rcx, rcx
0x140012176  jz      short loc_140012181
0x140012178  mov     eax, [rsp+88h+dwDisposition]
0x14001217f  mov     [rcx], eax
0x140012181  mov     rcx, [r15]; hKey
0x140012184  lea     rax, [r14+250h]
0x14001218b  mov     [rsp+88h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140012190  lea     r9, [r14+24Ch]
0x140012197  mov     [rsp+88h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x14001219c  lea     r10, [r14+248h]
0x1400121a3  mov     [rsp+88h+lpcbMaxValueLen], r10; lpcbMaxValueLen
0x1400121a8  lea     r11, [r14+244h]
0x1400121af  mov     [rsp+88h+lpdwDisposition], r11; lpcbMaxValueNameLen
0x1400121b4  lea     rbx, [r14+240h]
0x1400121bb  mov     [rsp+88h+phkResult], rbx; lpcValues
0x1400121c0  lea     rdi, [r14+23Ch]
0x1400121c7  mov     [rsp+88h+lpSecurityAttributes], rdi; lpcbMaxClassLen
0x1400121cc  lea     rsi, [r14+238h]
0x1400121d3  lea     rbp, [r14+234h]
0x1400121da  mov     qword ptr [rsp+88h+samDesired], rsi; lpcbMaxSubKeyLen
0x1400121df  lea     r8, [r14+230h]; lpcchClass
0x1400121e6  mov     qword ptr [rsp+88h+dwOptions], rbp; lpcSubKeys
0x1400121eb  lea     rdx, [r14+26h]; lpClass
0x1400121ef  xor     r9d, r9d; lpReserved
0x1400121f2  call    cs:__imp_RegQueryInfoKeyW
0x1400121f8  lea     rcx, [r14+18h]; this
0x1400121fc  mov     rdx, r12; unsigned __int16 *
0x1400121ff  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x140012204  xor     eax, eax
0x140012206  lea     r11, [rsp+88h+var_28]
0x14001220b  mov     rbx, [r11+38h]
0x14001220f  mov     rbp, [r11+40h]
0x140012213  mov     rsp, r11
0x140012216  pop     r15
0x140012218  pop     r14
0x14001221a  pop     r12
0x14001221c  pop     rdi
0x14001221d  pop     rsi
0x14001221e  retn
```

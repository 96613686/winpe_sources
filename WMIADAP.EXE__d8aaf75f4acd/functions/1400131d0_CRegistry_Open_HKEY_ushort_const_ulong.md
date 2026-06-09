# CRegistry::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1400131d0`
- end: `0x1400132b7`
- name: `?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `231`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, WCHAR *, REGSAM)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f91c`
- `0x140012f60`
- `0x1400132c0`
- `0x1400133e0`
- `0x140013510`

## callees

- `0x140010190`
- `0x1400131d0`
- `0x1400134b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001320e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001320e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140013294`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140013294`

## pseudocode

```c
LSTATUS __fastcall CRegistry::Open(CRegistry *this, HKEY a2, WCHAR *a3, REGSAM a4)
{
  HKEY *phkResult; // r15
  LSTATUS result; // eax
  HKEY v10; // rcx

  phkResult = (HKEY *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    CRegistry::PrepareToReOpen(this);
  *(_QWORD *)this = a2;
  result = RegOpenKeyExW(a2, a3, 0, a4, phkResult);
  if ( !result )
  {
    v10 = *phkResult;
    *((_DWORD *)this + 140) = 260;
    RegQueryInfoKeyW(
      v10,
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
0x1400131d0  push    rbx
0x1400131d2  push    rbp
0x1400131d3  push    rsi
0x1400131d4  push    rdi
0x1400131d5  push    r12
0x1400131d7  push    r14
0x1400131d9  push    r15
0x1400131db  sub     rsp, 60h
0x1400131df  lea     r15, [rcx+8]
0x1400131e3  mov     edi, r9d
0x1400131e6  cmp     qword ptr [r15], 0
0x1400131ea  mov     r12, r8
0x1400131ed  mov     rbx, rdx
0x1400131f0  mov     r14, rcx
0x1400131f3  jz      short loc_1400131FA
0x1400131f5  call    ?PrepareToReOpen@CRegistry@@AEAAXXZ; CRegistry::PrepareToReOpen(void)
0x1400131fa  mov     r9d, edi; samDesired
0x1400131fd  mov     [r14], rbx
0x140013200  xor     r8d, r8d; ulOptions
0x140013203  mov     [rsp+98h+phkResult], r15; phkResult
0x140013208  mov     rdx, r12; lpSubKey
0x14001320b  mov     rcx, rbx; hKey
0x14001320e  call    cs:__imp_RegOpenKeyExW
0x140013214  test    eax, eax
0x140013216  jnz     loc_1400132A8
0x14001321c  mov     rcx, [r15]; hKey
0x14001321f  lea     rax, [r14+250h]
0x140013226  mov     [rsp+98h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14001322b  lea     r9, [r14+24Ch]
0x140013232  mov     [rsp+98h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x140013237  lea     r10, [r14+248h]
0x14001323e  mov     [rsp+98h+lpcbMaxValueLen], r10; lpcbMaxValueLen
0x140013243  lea     r11, [r14+244h]
0x14001324a  mov     [rsp+98h+lpcbMaxValueNameLen], r11; lpcbMaxValueNameLen
0x14001324f  lea     r8, [r14+230h]; lpcchClass
0x140013256  lea     rbx, [r14+240h]
0x14001325d  mov     dword ptr [r8], 104h
0x140013264  mov     [rsp+98h+lpcValues], rbx; lpcValues
0x140013269  lea     rdi, [r14+23Ch]
0x140013270  mov     [rsp+98h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x140013275  lea     rsi, [r14+238h]
0x14001327c  lea     rbp, [r14+234h]
0x140013283  mov     [rsp+98h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x140013288  lea     rdx, [r14+26h]; lpClass
0x14001328c  mov     [rsp+98h+phkResult], rbp; lpcSubKeys
0x140013291  xor     r9d, r9d; lpReserved
0x140013294  call    cs:__imp_RegQueryInfoKeyW
0x14001329a  lea     rcx, [r14+18h]; this
0x14001329e  mov     rdx, r12; unsigned __int16 *
0x1400132a1  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x1400132a6  xor     eax, eax
0x1400132a8  add     rsp, 60h
0x1400132ac  pop     r15
0x1400132ae  pop     r14
0x1400132b0  pop     r12
0x1400132b2  pop     rdi
0x1400132b3  pop     rsi
0x1400132b4  pop     rbp
0x1400132b5  pop     rbx
0x1400132b6  retn
```

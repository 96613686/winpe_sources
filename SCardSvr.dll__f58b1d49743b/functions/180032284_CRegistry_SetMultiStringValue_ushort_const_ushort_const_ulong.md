# CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180032284`
- end: `0x180032301`
- name: `?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z`
- size: `125`
- prototype: `void __fastcall(CRegistry *this, const unsigned __int16 *, const unsigned __int16 *, ulong)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180031df0`

## callees

- `0x18001b92c`
- `0x180032284`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800322db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800322db`

## string_xrefs

- `0x1800322ae`: `SCard$DefaultReaders`

## pseudocode

```c
void __fastcall CRegistry::SetMultiStringValue(
        CRegistry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        ulong a4)
{
  unsigned int v4; // eax
  HKEY *v5; // r11
  LSTATUS v6; // eax
  ulong pExceptionObject; // [rsp+58h] [rbp+20h] BYREF

  pExceptionObject = a4;
  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw &pExceptionObject;
  }
  v4 = MStrLen(L"SCard$DefaultReaders");
  v6 = RegSetValueExW(*v5, L"Groups", 0, 7u, L"SCard$DefaultReaders", 2 * v4);
  if ( v6 )
  {
    pExceptionObject = v6;
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x180032284  mov     [rsp+pExceptionObject], r9d
0x180032289  push    rbx
0x18003228a  sub     rsp, 30h
0x18003228e  mov     eax, [rcx+28h]
0x180032291  mov     r11, rcx
0x180032294  test    eax, eax
0x180032296  jz      short loc_1800322AE
0x180032298  lea     rdx, _TI1K; pThrowInfo
0x18003229f  mov     [rsp+38h+pExceptionObject], eax
0x1800322a3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800322a8  call    _CxxThrowException_0
0x1800322ae  lea     rbx, aScardDefaultre; "SCard$DefaultReaders"
0x1800322b5  mov     rcx, rbx; unsigned __int16 *
0x1800322b8  call    ?MStrLen@@YAKPEBG@Z; MStrLen(ushort const *)
0x1800322bd  mov     rcx, [r11]; hKey
0x1800322c0  lea     rdx, aGroups_0; "Groups"
0x1800322c7  add     eax, eax
0x1800322c9  mov     r9d, 7; dwType
0x1800322cf  mov     [rsp+38h+cbData], eax; cbData
0x1800322d3  xor     r8d, r8d; Reserved
0x1800322d6  mov     [rsp+38h+lpData], rbx; lpData
0x1800322db  call    cs:__imp_RegSetValueExW
0x1800322e1  test    eax, eax
0x1800322e3  jz      short loc_1800322FB
0x1800322e5  lea     rdx, _TI1K; pThrowInfo
0x1800322ec  mov     [rsp+38h+pExceptionObject], eax
0x1800322f0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800322f5  call    _CxxThrowException_0
0x1800322fb  add     rsp, 30h
0x1800322ff  pop     rbx
0x180032300  retn
```

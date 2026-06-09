# CRegistry::SetValue(ushort const *,uchar const *,ulong,ulong)

- ea: `0x18002a774`
- end: `0x18002a7d0`
- name: `?SetValue@CRegistry@@QEBAXPEBGPEBEKK@Z`
- size: `92`
- prototype: `void(CRegistry *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001aae0`
- `0x18001b044`

## callees

- `0x18002a774`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a7ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a7ab`

## pseudocode

```c
void __fastcall CRegistry::SetValue(
        CRegistry *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *lpData,
        DWORD cbData,
        LSTATUS pExceptionObject)
{
  LSTATUS v5; // eax

  if ( *((_DWORD *)this + 10) )
  {
    pExceptionObject = *((_DWORD *)this + 10);
    throw (ulong *)&pExceptionObject;
  }
  v5 = RegSetValueExW(*(HKEY *)this, a2, 0, 3u, lpData, cbData);
  if ( v5 )
  {
    pExceptionObject = v5;
    throw (ulong *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002a774  sub     rsp, 38h
0x18002a778  mov     eax, [rcx+28h]
0x18002a77b  test    eax, eax
0x18002a77d  jz      short loc_18002A795
0x18002a77f  lea     rdx, _TI1K; pThrowInfo
0x18002a786  mov     [rsp+38h+pExceptionObject], eax
0x18002a78a  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a78f  call    _CxxThrowException_0
0x18002a795  mov     rcx, [rcx]; hKey
0x18002a798  mov     [rsp+38h+cbData], r9d; cbData
0x18002a79d  mov     r9d, 3; dwType
0x18002a7a3  mov     [rsp+38h+lpData], r8; lpData
0x18002a7a8  xor     r8d, r8d; Reserved
0x18002a7ab  call    cs:__imp_RegSetValueExW
0x18002a7b1  test    eax, eax
0x18002a7b3  jz      short loc_18002A7CB
0x18002a7b5  lea     rdx, _TI1K; pThrowInfo
0x18002a7bc  mov     [rsp+38h+pExceptionObject], eax
0x18002a7c0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a7c5  call    _CxxThrowException_0
0x18002a7cb  add     rsp, 38h
0x18002a7cf  retn
```

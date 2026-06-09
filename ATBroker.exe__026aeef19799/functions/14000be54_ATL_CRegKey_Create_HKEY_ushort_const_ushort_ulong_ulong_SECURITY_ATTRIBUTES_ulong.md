# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x14000be54`
- end: `0x14000befb`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `167`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e538`
- `0x14000ea38`
- `0x14000f9c0`
- `0x140010194`
- `0x1400127f8`
- `0x140012a48`

## callees

- `0x14000be54`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000bee0`
- `ADVAPI32!RegCloseKey` at `0x14000bee0`
- `KERNEL32!RegCreateKeyExW` at `0x14000beb9`
- `KERNEL32!RegCreateKeyExW` at `0x14000beb9`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *phkResult,
        unsigned int *a8)
{
  unsigned int v9; // edx
  DWORD lpdwDisposition; // [rsp+78h] [rbp+20h] BYREF
  int v12; // [rsp+7Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  lpdwDisposition = 0;
  phkResult = 0;
  v9 = RegCreateKeyExW(a2, a3, 0, 0, dwOptions, samDesired, 0, (PHKEY)&phkResult, &lpdwDisposition);
  if ( a8 )
    *a8 = lpdwDisposition;
  if ( !v9 )
  {
    if ( *this )
      v9 = RegCloseKey(*this);
    *this = (HKEY)phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x14000be54  mov     rax, rsp
0x14000be57  mov     [rax+20h], r9
0x14000be5b  push    rbx
0x14000be5c  sub     rsp, 50h
0x14000be60  mov     r10, r8
0x14000be63  mov     r11, rdx
0x14000be66  mov     rbx, rcx
0x14000be69  mov     dword ptr [rax+20h], 0
0x14000be70  mov     qword ptr [rax+38h], 0
0x14000be78  lea     rax, [rax+20h]
0x14000be7c  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x14000be81  lea     rax, [rsp+58h+arg_30]
0x14000be89  mov     [rsp+58h+phkResult], rax; phkResult
0x14000be8e  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000be97  mov     eax, [rsp+58h+arg_28]
0x14000be9e  mov     [rsp+58h+samDesired], eax; samDesired
0x14000bea2  mov     eax, [rsp+58h+arg_20]
0x14000bea9  mov     [rsp+58h+dwOptions], eax; dwOptions
0x14000bead  xor     r9d, r9d; lpClass
0x14000beb0  xor     r8d, r8d; Reserved
0x14000beb3  mov     rdx, r10; lpSubKey
0x14000beb6  mov     rcx, r11; hKey
0x14000beb9  call    cs:__imp_RegCreateKeyExW
0x14000bebf  mov     edx, eax
0x14000bec1  mov     rax, [rsp+58h+arg_38]
0x14000bec9  test    rax, rax
0x14000becc  jz      short loc_14000BED4
0x14000bece  mov     ecx, [rsp+58h+arg_18]
0x14000bed2  mov     [rax], ecx
0x14000bed4  test    edx, edx
0x14000bed6  jnz     short loc_14000BEF3
0x14000bed8  mov     rcx, [rbx]; hKey
0x14000bedb  test    rcx, rcx
0x14000bede  jz      short loc_14000BEE8
0x14000bee0  call    cs:__imp_RegCloseKey
0x14000bee6  mov     edx, eax
0x14000bee8  mov     rax, [rsp+58h+arg_30]
0x14000bef0  mov     [rbx], rax
0x14000bef3  mov     eax, edx
0x14000bef5  add     rsp, 50h
0x14000bef9  pop     rbx
0x14000befa  retn
```

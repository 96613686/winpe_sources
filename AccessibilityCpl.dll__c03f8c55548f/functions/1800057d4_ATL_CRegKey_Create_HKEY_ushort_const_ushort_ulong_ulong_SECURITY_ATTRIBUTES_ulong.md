# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1800057d4`
- end: `0x180005875`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `161`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, DWORD, REGSAM, HKEY, unsigned int *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019740`
- `0x18001d6dc`
- `0x18001d978`
- `0x18001f4c8`
- `0x1800229ec`
- `0x180023bc0`
- `0x1800241b0`
- `0x1800251dc`
- `0x180025a18`
- `0x180029268`
- `0x1800293c4`

## callees

- `0x1800055c0`
- `0x1800057d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005839`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005839`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        HKEY phkResult,
        unsigned int *a8)
{
  unsigned int v9; // edx
  DWORD lpdwDisposition; // [rsp+78h] [rbp+20h] BYREF
  int v12; // [rsp+7Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  lpdwDisposition = 0;
  phkResult = 0;
  v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, dwOptions, samDesired, 0, &phkResult, &lpdwDisposition);
  if ( a8 )
    *a8 = lpdwDisposition;
  if ( !v9 )
  {
    v9 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x1800057d4  mov     rax, rsp
0x1800057d7  mov     [rax+20h], r9
0x1800057db  push    rbx
0x1800057dc  sub     rsp, 50h
0x1800057e0  mov     dword ptr [rax+20h], 0
0x1800057e7  mov     r10, r8
0x1800057ea  mov     qword ptr [rax+38h], 0
0x1800057f2  lea     rax, [rax+20h]
0x1800057f6  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800057fb  mov     r11, rdx
0x1800057fe  lea     rax, [rsp+58h+arg_30]
0x180005806  mov     rbx, rcx
0x180005809  mov     [rsp+58h+phkResult], rax; phkResult
0x18000580e  xor     r9d, r9d; lpClass
0x180005811  mov     eax, [rsp+58h+arg_28]
0x180005818  xor     r8d, r8d; Reserved
0x18000581b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180005824  mov     rdx, r10; lpSubKey
0x180005827  mov     [rsp+58h+samDesired], eax; samDesired
0x18000582b  mov     rcx, r11; hKey
0x18000582e  mov     eax, [rsp+58h+arg_20]
0x180005835  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180005839  call    cs:__imp_RegCreateKeyExW
0x18000583f  mov     edx, eax
0x180005841  mov     rax, [rsp+58h+arg_38]
0x180005849  test    rax, rax
0x18000584c  jz      short loc_180005854
0x18000584e  mov     ecx, [rsp+58h+arg_18]
0x180005852  mov     [rax], ecx
0x180005854  test    edx, edx
0x180005856  jnz     short loc_18000586D
0x180005858  mov     rcx, rbx; this
0x18000585b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005860  mov     edx, eax
0x180005862  mov     rax, [rsp+58h+arg_30]
0x18000586a  mov     [rbx], rax
0x18000586d  mov     eax, edx
0x18000586f  add     rsp, 50h
0x180005873  pop     rbx
0x180005874  retn
```

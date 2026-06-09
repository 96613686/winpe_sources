# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180039ed8`
- end: `0x180039f5d`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c40`
- `0x18003c92c`
- `0x180060f8c`
- `0x18006253c`

## callees

- `0x180008270`
- `0x180039ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039f37`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039f37`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwOptions,
        unsigned int lpdwDisposition)
{
  unsigned int v7; // ecx
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  lpdwDisposition = 0;
  phkResult = 0;
  v7 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, dwOptions, 0x2001Fu, 0, &phkResult, &lpdwDisposition);
  if ( !v7 )
  {
    v7 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v7;
}

```

## disassembly

```asm
0x180039ed8  mov     rax, rsp
0x180039edb  mov     [rax+20h], r9
0x180039edf  push    rbx
0x180039ee0  sub     rsp, 50h
0x180039ee4  mov     dword ptr [rax+30h], 0
0x180039eeb  mov     r10, r8
0x180039eee  mov     qword ptr [rax+20h], 0
0x180039ef6  lea     rax, [rax+30h]
0x180039efa  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180039eff  mov     r11, rdx
0x180039f02  lea     rax, [rsp+58h+arg_18]
0x180039f07  mov     rbx, rcx
0x180039f0a  mov     [rsp+58h+phkResult], rax; phkResult
0x180039f0f  xor     r9d, r9d; lpClass
0x180039f12  mov     eax, [rsp+58h+arg_20]
0x180039f19  xor     r8d, r8d; Reserved
0x180039f1c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180039f25  mov     rdx, r10; lpSubKey
0x180039f28  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180039f30  mov     rcx, r11; hKey
0x180039f33  mov     [rsp+58h+dwOptions], eax; dwOptions
0x180039f37  call    cs:__imp_RegCreateKeyExW
0x180039f3d  mov     ecx, eax
0x180039f3f  test    eax, eax
0x180039f41  jnz     short loc_180039F55
0x180039f43  mov     rcx, rbx; this
0x180039f46  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180039f4b  mov     ecx, eax
0x180039f4d  mov     rax, [rsp+58h+arg_18]
0x180039f52  mov     [rbx], rax
0x180039f55  mov     eax, ecx
0x180039f57  add     rsp, 50h
0x180039f5b  pop     rbx
0x180039f5c  retn
```

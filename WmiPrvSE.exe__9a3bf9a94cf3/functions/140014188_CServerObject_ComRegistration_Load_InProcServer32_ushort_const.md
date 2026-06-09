# CServerObject_ComRegistration::Load_InProcServer32(ushort const *)

- ea: `0x140014188`
- end: `0x140014292`
- name: `?Load_InProcServer32@CServerObject_ComRegistration@@AEAAJPEBG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CServerObject_ComRegistration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014f2c`

## callees

- `0x14001342c`
- `0x140013f60`
- `0x140014188`
- `0x140014860`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140014266`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140014266`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014203`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014203`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014270`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014270`
- `OLEAUT32!__imp_SysFreeString` at `0x14001427a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001427a`

## pseudocode

```c
__int64 __fastcall CServerObject_ComRegistration::Load_InProcServer32(
        CServerObject_ComRegistration *this,
        const unsigned __int16 *a2)
{
  int ThreadingModel; // ebx
  int v4; // r9d
  HKEY v5; // rdx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  lpSubKey = 0;
  ThreadingModel = WmiHelper::ConcatenateStrings(2u, (BSTR *)&lpSubKey, a2, L"InProcServer32");
  if ( ThreadingModel >= 0 )
  {
    v4 = 512;
    if ( *((_DWORD *)this + 404) != 32 )
      v4 = 256;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, v4 | 0x20019, &hKey) )
    {
      v5 = hKey;
      *((_DWORD *)this + 4) = 1;
      ThreadingModel = CServerObject_ComRegistration::Load_ThreadingModel(this, v5);
      if ( ThreadingModel >= 0 )
        ThreadingModel = CServerObject_ComRegistration::Load_Synchronization(this, hKey);
      Type = 1;
      cbData = 520;
      RegQueryValueExW(hKey, CServerObject_ComRegistration::s_Strings_Reg_Null, 0, &Type, (LPBYTE)this + 56, &cbData);
      RegCloseKey(hKey);
    }
    SysFreeString((BSTR)lpSubKey);
  }
  return (unsigned int)ThreadingModel;
}

```

## disassembly

```asm
0x140014188  mov     [rsp-8+arg_0], rbx
0x14001418d  mov     [rsp-8+arg_8], rdi
0x140014192  push    rbp
0x140014193  mov     rbp, rsp
0x140014196  sub     rsp, 40h
0x14001419a  mov     rdi, rcx
0x14001419d  mov     [rbp+lpSubKey], 0
0x1400141a5  mov     r8, rdx
0x1400141a8  lea     r9, aInprocserver32; "InProcServer32"
0x1400141af  lea     rdx, [rbp+lpSubKey]
0x1400141b3  mov     ecx, 2
0x1400141b8  call    ?ConcatenateStrings@WmiHelper@@SA?AW4WmiStatusCode@@KPEAPEAGZZ; WmiHelper::ConcatenateStrings(ulong,ushort * *,...)
0x1400141bd  mov     ebx, eax
0x1400141bf  test    eax, eax
0x1400141c1  js      loc_140014280
0x1400141c7  cmp     dword ptr [rdi+650h], 20h ; ' '
0x1400141ce  mov     eax, 100h
0x1400141d3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1400141d7  mov     r9d, 200h
0x1400141dd  cmovnz  r9d, eax
0x1400141e1  mov     [rbp+hKey], 0
0x1400141e9  lea     rax, [rbp+hKey]
0x1400141ed  or      r9d, 20019h; samDesired
0x1400141f4  xor     r8d, r8d; ulOptions
0x1400141f7  mov     [rsp+40h+phkResult], rax; phkResult
0x1400141fc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140014203  call    cs:__imp_RegOpenKeyExW
0x140014209  test    eax, eax
0x14001420b  jnz     short loc_140014276
0x14001420d  mov     rdx, [rbp+hKey]; HKEY
0x140014211  mov     rcx, rdi; this
0x140014214  mov     dword ptr [rdi+10h], 1
0x14001421b  call    ?Load_ThreadingModel@CServerObject_ComRegistration@@AEAAJPEAUHKEY__@@@Z; CServerObject_ComRegistration::Load_ThreadingModel(HKEY__ *)
0x140014220  mov     ebx, eax
0x140014222  test    eax, eax
0x140014224  js      short loc_140014234
0x140014226  mov     rdx, [rbp+hKey]; HKEY
0x14001422a  mov     rcx, rdi; this
0x14001422d  call    ?Load_Synchronization@CServerObject_ComRegistration@@AEAAJPEAUHKEY__@@@Z; CServerObject_ComRegistration::Load_Synchronization(HKEY__ *)
0x140014232  mov     ebx, eax
0x140014234  mov     rdx, cs:?s_Strings_Reg_Null@CServerObject_ComRegistration@@1PEBGEB; lpValueName
0x14001423b  lea     rcx, [rbp+cbData]
0x14001423f  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x140014244  lea     rax, [rdi+38h]
0x140014248  mov     rcx, [rbp+hKey]; hKey
0x14001424c  lea     r9, [rbp+Type]; lpType
0x140014250  xor     r8d, r8d; lpReserved
0x140014253  mov     [rbp+Type], 1
0x14001425a  mov     [rbp+cbData], 208h
0x140014261  mov     [rsp+40h+phkResult], rax; lpData
0x140014266  call    cs:__imp_RegQueryValueExW
0x14001426c  mov     rcx, [rbp+hKey]; hKey
0x140014270  call    cs:__imp_RegCloseKey
0x140014276  mov     rcx, [rbp+lpSubKey]; bstrString
0x14001427a  call    cs:__imp_SysFreeString
0x140014280  mov     rdi, [rsp+40h+arg_8]
0x140014285  mov     eax, ebx
0x140014287  mov     rbx, [rsp+40h+arg_0]
0x14001428c  add     rsp, 40h
0x140014290  pop     rbp
0x140014291  retn
```

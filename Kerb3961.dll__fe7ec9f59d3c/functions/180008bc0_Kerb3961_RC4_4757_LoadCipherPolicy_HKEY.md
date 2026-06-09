# Kerb3961::RC4_4757::LoadCipherPolicy(HKEY__ *)

- ea: `0x180008bc0`
- end: `0x180008c99`
- name: `?LoadCipherPolicy@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@PEAUHKEY__@@@Z`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000485c`
- `0x180008bc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008c16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008c16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c63`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::RC4_4757::LoadCipherPolicy(__int64 a1, _DWORD *a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 v6; // rdx
  bool v7; // sf
  HKEY v8; // rcx
  int value_dword; // eax
  int v10; // eax
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  if ( (int)wil::reg::get_value_dword_nothrow<unsigned long,0>(a3, a2, &v12) >= 0 )
  {
LABEL_11:
    v10 = 2;
    if ( v12 <= 2 )
    {
      v10 = v12;
      if ( !v12 )
        v10 = 1;
    }
    *(_DWORD *)(a1 + 104) = v10;
    *a2 = 0;
    return a2;
  }
  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         &hKey);
  v7 = v5 < 0;
  if ( v5 > 0 )
    v7 = 1;
  v8 = hKey;
  if ( !v7 )
  {
    value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(hKey, v6, &v12);
    v8 = hKey;
    if ( value_dword >= 0 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_11;
    }
  }
  *a2 = 0;
  if ( v8 )
    RegCloseKey(v8);
  *(_DWORD *)(a1 + 104) = 2;
  return a2;
}

```

## disassembly

```asm
0x180008bc0  mov     [rsp+arg_8], rbx
0x180008bc5  push    rdi
0x180008bc6  sub     rsp, 30h
0x180008bca  mov     rax, r8
0x180008bcd  mov     [rsp+38h+arg_0], 0
0x180008bd5  mov     rdi, rcx
0x180008bd8  lea     r8, [rsp+38h+arg_0]
0x180008bdd  mov     rcx, rax
0x180008be0  mov     rbx, rdx
0x180008be3  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x180008be8  test    eax, eax
0x180008bea  jns     short loc_180008C69
0x180008bec  lea     rax, [rsp+38h+hKey]
0x180008bf1  mov     [rsp+38h+hKey], 0
0x180008bfa  mov     r9d, 20019h; samDesired
0x180008c00  mov     [rsp+38h+phkResult], rax; phkResult
0x180008c05  xor     r8d, r8d; ulOptions
0x180008c08  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008c0f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008c16  call    cs:__imp_RegOpenKeyExW
0x180008c1c  test    eax, eax
0x180008c1e  jle     short loc_180008C2A
0x180008c20  movzx   eax, ax
0x180008c23  or      eax, 80070000h
0x180008c28  test    eax, eax
0x180008c2a  mov     rcx, [rsp+38h+hKey]; hKey
0x180008c2f  jns     short loc_180008C4B
0x180008c31  mov     dword ptr [rbx], 0
0x180008c37  test    rcx, rcx
0x180008c3a  jz      short loc_180008C42
0x180008c3c  call    cs:__imp_RegCloseKey
0x180008c42  mov     dword ptr [rdi+68h], 2
0x180008c49  jmp     short loc_180008C8B
0x180008c4b  lea     r8, [rsp+38h+arg_0]
0x180008c50  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x180008c55  mov     rcx, [rsp+38h+hKey]; hKey
0x180008c5a  test    eax, eax
0x180008c5c  js      short loc_180008C31
0x180008c5e  test    rcx, rcx
0x180008c61  jz      short loc_180008C69
0x180008c63  call    cs:__imp_RegCloseKey
0x180008c69  mov     ecx, [rsp+38h+arg_0]
0x180008c6d  mov     eax, 2
0x180008c72  cmp     ecx, eax
0x180008c74  ja      short loc_180008C82
0x180008c76  mov     edx, 1
0x180008c7b  mov     eax, ecx
0x180008c7d  cmp     ecx, edx
0x180008c7f  cmovb   eax, edx
0x180008c82  mov     [rdi+68h], eax
0x180008c85  mov     dword ptr [rbx], 0
0x180008c8b  mov     rax, rbx
0x180008c8e  mov     rbx, [rsp+38h+arg_8]
0x180008c93  add     rsp, 30h
0x180008c97  pop     rdi
0x180008c98  retn
```

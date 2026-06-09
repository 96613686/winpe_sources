# GetMachineGUID(_GUID &)

- ea: `0x1800f4628`
- end: `0x1800f4809`
- name: `?GetMachineGUID@@YAJAEAU_GUID@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180036324`

## callees

- `0x180056564`
- `0x18005e428`
- `0x1800bb480`
- `0x1800f4628`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f47c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f47c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f475b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f475b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f46cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f46cf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f47e3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f47e3`

## pseudocode

```c
__int64 __fastcall GetMachineGUID(struct _GUID *a1)
{
  int v2; // [rsp+40h] [rbp-B8h]
  LSTATUS v3; // [rsp+48h] [rbp-B0h]
  LSTATUS ValueW; // [rsp+50h] [rbp-A8h]
  signed int v5; // [rsp+58h] [rbp-A0h]
  signed int v6; // [rsp+5Ch] [rbp-9Ch]
  DWORD pcbData[3]; // [rsp+64h] [rbp-94h] BYREF
  unsigned __int64 v8; // [rsp+70h] [rbp-88h] BYREF
  PVOID pvData; // [rsp+78h] [rbp-80h] BYREF
  HKEY hkey; // [rsp+80h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-68h] BYREF

  pvData = 0;
  v8 = 0;
  v2 = StringCchCopyExW(sz, 0x27u, L"{", (unsigned __int16 **)&pvData, &v8, 0);
  if ( v2 >= 0 )
  {
    hkey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography", 0, 0x101u, &hkey);
    v5 = v3 > 0 ? (unsigned __int16)v3 | 0x80070000 : v3;
    v2 = v5;
    if ( v5 >= 0 )
    {
      pcbData[0] = 2 * v8;
      ValueW = RegGetValueW(hkey, 0, L"MachineGuid", 2u, 0, pvData, pcbData);
      if ( ValueW > 0 )
        v6 = (unsigned __int16)ValueW | 0x80070000;
      else
        v6 = ValueW;
      pcbData[1] = v6;
      v2 = v6;
      if ( v6 >= 0 )
        v2 = StringCchCatW((unsigned __int16 *)pvData, v8, L"}");
      RegCloseKey(hkey);
    }
  }
  if ( v2 >= 0 )
    return (unsigned int)CLSIDFromString(sz, a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800f4628  mov     [rsp+pclsid], rcx
0x1800f462d  sub     rsp, 0F8h
0x1800f4634  mov     rax, cs:__security_cookie
0x1800f463b  xor     rax, rsp
0x1800f463e  mov     [rsp+0F8h+var_18], rax
0x1800f4646  mov     [rsp+0F8h+var_B8], 80004005h
0x1800f464e  mov     [rsp+0F8h+var_80], 0
0x1800f4657  mov     [rsp+0F8h+var_88], 0
0x1800f4660  mov     dword ptr [rsp+0F8h+pvData], 0; unsigned int
0x1800f4668  lea     rax, [rsp+0F8h+var_88]
0x1800f466d  mov     [rsp+0F8h+phkResult], rax; unsigned __int64 *
0x1800f4672  lea     r9, [rsp+0F8h+var_80]; unsigned __int16 **
0x1800f4677  lea     r8, asc_1802B2148; "{"
0x1800f467e  mov     edx, 27h ; '''; unsigned __int64
0x1800f4683  lea     rcx, [rsp+0F8h+sz]; pszDest
0x1800f468b  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800f4690  mov     [rsp+0F8h+var_B8], eax
0x1800f4694  cmp     [rsp+0F8h+var_B8], 0
0x1800f4699  jl      loc_1800F47CC
0x1800f469f  mov     [rsp+0F8h+hkey], 0
0x1800f46ab  lea     rax, [rsp+0F8h+hkey]
0x1800f46b3  mov     [rsp+0F8h+phkResult], rax; phkResult
0x1800f46b8  mov     r9d, 101h; samDesired
0x1800f46be  xor     r8d, r8d; ulOptions
0x1800f46c1  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Cryptography"
0x1800f46c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f46cf  call    cs:__imp_RegOpenKeyExW
0x1800f46d5  mov     [rsp+0F8h+var_B0], eax
0x1800f46d9  cmp     [rsp+0F8h+var_B0], 0
0x1800f46de  jg      short loc_1800F46EA
0x1800f46e0  mov     eax, [rsp+0F8h+var_B0]
0x1800f46e4  mov     [rsp+0F8h+var_A0], eax
0x1800f46e8  jmp     short loc_1800F4700
0x1800f46ea  mov     eax, [rsp+0F8h+var_B0]
0x1800f46ee  and     eax, 0FFFFh
0x1800f46f3  or      eax, 70000h
0x1800f46f8  bts     eax, 1Fh
0x1800f46fc  mov     [rsp+0F8h+var_A0], eax
0x1800f4700  mov     eax, [rsp+0F8h+var_A0]
0x1800f4704  mov     [rsp+0F8h+var_98], eax
0x1800f4708  mov     eax, [rsp+0F8h+var_98]
0x1800f470c  mov     [rsp+0F8h+var_B8], eax
0x1800f4710  cmp     [rsp+0F8h+var_B8], 0
0x1800f4715  jl      loc_1800F47CC
0x1800f471b  mov     rax, [rsp+0F8h+var_88]
0x1800f4720  shl     rax, 1
0x1800f4723  mov     [rsp+0F8h+var_94], eax
0x1800f4727  lea     rax, [rsp+0F8h+var_94]
0x1800f472c  mov     [rsp+0F8h+pcbData], rax; pcbData
0x1800f4731  mov     rax, [rsp+0F8h+var_80]
0x1800f4736  mov     [rsp+0F8h+pvData], rax; pvData
0x1800f473b  mov     [rsp+0F8h+phkResult], 0; pdwType
0x1800f4744  mov     r9d, 2; dwFlags
0x1800f474a  lea     r8, Value; "MachineGuid"
0x1800f4751  xor     edx, edx; lpSubKey
0x1800f4753  mov     rcx, [rsp+0F8h+hkey]; hkey
0x1800f475b  call    cs:__imp_RegGetValueW
0x1800f4761  mov     [rsp+0F8h+var_A8], eax
0x1800f4765  cmp     [rsp+0F8h+var_A8], 0
0x1800f476a  jg      short loc_1800F4776
0x1800f476c  mov     eax, [rsp+0F8h+var_A8]
0x1800f4770  mov     [rsp+0F8h+var_9C], eax
0x1800f4774  jmp     short loc_1800F478C
0x1800f4776  mov     eax, [rsp+0F8h+var_A8]
0x1800f477a  and     eax, 0FFFFh
0x1800f477f  or      eax, 70000h
0x1800f4784  bts     eax, 1Fh
0x1800f4788  mov     [rsp+0F8h+var_9C], eax
0x1800f478c  mov     eax, [rsp+0F8h+var_9C]
0x1800f4790  mov     [rsp+0F8h+var_90], eax
0x1800f4794  mov     eax, [rsp+0F8h+var_90]
0x1800f4798  mov     [rsp+0F8h+var_B8], eax
0x1800f479c  cmp     [rsp+0F8h+var_B8], 0
0x1800f47a1  jl      short loc_1800F47BD
0x1800f47a3  lea     r8, asc_1802B2208; "}"
0x1800f47aa  mov     rdx, [rsp+0F8h+var_88]; unsigned __int64
0x1800f47af  mov     rcx, [rsp+0F8h+var_80]; unsigned __int16 *
0x1800f47b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800f47b9  mov     [rsp+0F8h+var_B8], eax
0x1800f47bd  mov     rcx, [rsp+0F8h+hkey]; hKey
0x1800f47c5  call    cs:__imp_RegCloseKey
0x1800f47cb  nop
0x1800f47cc  cmp     [rsp+0F8h+var_B8], 0
0x1800f47d1  jl      short loc_1800F47ED
0x1800f47d3  mov     rdx, [rsp+0F8h+pclsid]; pclsid
0x1800f47db  lea     rcx, [rsp+0F8h+sz]; lpsz
0x1800f47e3  call    cs:__imp_CLSIDFromString
0x1800f47e9  mov     [rsp+0F8h+var_B8], eax
0x1800f47ed  mov     eax, [rsp+0F8h+var_B8]
0x1800f47f1  mov     rcx, [rsp+0F8h+var_18]
0x1800f47f9  xor     rcx, rsp; StackCookie
0x1800f47fc  call    __security_check_cookie
0x1800f4801  add     rsp, 0F8h
0x1800f4808  retn
```

# IsAPOClsidRegistered(HKEY__ *,ushort const *)

- ea: `0x18002707c`
- end: `0x180027103`
- name: `?IsAPOClsidRegistered@@YA_NPEAUHKEY__@@PEBG@Z`
- size: `135`
- prototype: `bool __fastcall(HKEY hKey, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027858`
- `0x18002b2a8`

## callees

- `0x18002707c`
- `0x180036c9c`
- `0x18003e920`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800270de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800270de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800270cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800270cf`

## pseudocode

```c
char __fastcall IsAPOClsidRegistered(HKEY hKey, const unsigned __int16 *a2)
{
  HKEY hKeya; // [rsp+30h] [rbp-C8h] BYREF
  WCHAR SubKey[80]; // [rsp+40h] [rbp-B8h] BYREF

  if ( (int)GetApoRegKeyPath(SubKey, (unsigned int)a2, a2) < 0 )
    return 0;
  hKeya = 0;
  if ( RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya) )
    return 0;
  RegCloseKey(hKeya);
  return 1;
}

```

## disassembly

```asm
0x18002707c  push    rbx
0x18002707e  sub     rsp, 0F0h
0x180027085  mov     rax, cs:__security_cookie
0x18002708c  xor     rax, rsp
0x18002708f  mov     [rsp+0F8h+var_18], rax
0x180027097  mov     rbx, rcx
0x18002709a  mov     r8, rdx; unsigned __int16 *
0x18002709d  lea     rcx, [rsp+0F8h+SubKey]; unsigned __int16 *
0x1800270a2  call    ?GetApoRegKeyPath@@YAJPEAGIPEBG@Z; GetApoRegKeyPath(ushort *,uint,ushort const *)
0x1800270a7  test    eax, eax
0x1800270a9  js      short loc_1800270E8
0x1800270ab  lea     rax, [rsp+0F8h+hKey]
0x1800270b0  mov     [rsp+0F8h+hKey], 0
0x1800270b9  mov     r9d, 20019h; samDesired
0x1800270bf  mov     [rsp+0F8h+phkResult], rax; phkResult
0x1800270c4  xor     r8d, r8d; ulOptions
0x1800270c7  lea     rdx, [rsp+0F8h+SubKey]; lpSubKey
0x1800270cc  mov     rcx, rbx; hKey
0x1800270cf  call    cs:__imp_RegOpenKeyExW
0x1800270d5  test    eax, eax
0x1800270d7  jnz     short loc_1800270E8
0x1800270d9  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1800270de  call    cs:__imp_RegCloseKey
0x1800270e4  mov     al, 1
0x1800270e6  jmp     short loc_1800270EA
0x1800270e8  xor     al, al
0x1800270ea  mov     rcx, [rsp+0F8h+var_18]
0x1800270f2  xor     rcx, rsp; StackCookie
0x1800270f5  call    __security_check_cookie
0x1800270fa  add     rsp, 0F0h
0x180027101  pop     rbx
0x180027102  retn
```

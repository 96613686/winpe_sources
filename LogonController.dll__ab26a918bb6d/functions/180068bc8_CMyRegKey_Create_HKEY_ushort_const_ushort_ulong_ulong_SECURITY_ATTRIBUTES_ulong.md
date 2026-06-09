# CMyRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180068bc8`
- end: `0x180068c99`
- name: `?Create@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `209`
- prototype: `__int64 __usercall@<rax>(CMyRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068790`

## callees

- `0x180007fc0`
- `0x180068bc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068c81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068c81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068c58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180068c58`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180068c0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180068c0e`

## pseudocode

```c
__int64 __fastcall CMyRegKey::Create(
        CMyRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwDisposition)
{
  HKEY v6; // rbx
  unsigned int v8; // ebx
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = 0;
  phkResult = 0;
  v6 = hKey;
  hKeya = 0;
  if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x2001Fu, &hKeya) )
    v6 = hKeya;
  v8 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  if ( !v8 )
  {
    v8 = CInputDllRegKey::Close(this);
    *((_QWORD *)this + 1) = phkResult;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v8;
}

```

## disassembly

```asm
0x180068bc8  mov     rax, rsp
0x180068bcb  mov     [rax+8], rbx
0x180068bcf  mov     [rax+18h], rsi
0x180068bd3  mov     [rax+20h], r9
0x180068bd7  push    rdi
0x180068bd8  sub     rsp, 50h
0x180068bdc  mov     dword ptr [rax+28h], 0
0x180068be3  mov     rsi, r8
0x180068be6  mov     qword ptr [rax+10h], 0
0x180068bee  mov     rbx, rdx
0x180068bf1  mov     qword ptr [rax+20h], 0
0x180068bf9  mov     rdi, rcx
0x180068bfc  cmp     rdx, 0FFFFFFFF80000001h
0x180068c03  jnz     short loc_180068C1C
0x180068c05  lea     rdx, [rax+20h]; phkResult
0x180068c09  mov     ecx, 2001Fh; samDesired
0x180068c0e  call    cs:__imp_RegOpenCurrentUser
0x180068c14  test    eax, eax
0x180068c16  cmovz   rbx, [rsp+58h+hKey]
0x180068c1c  lea     rax, [rsp+58h+dwDisposition]
0x180068c24  xor     r9d, r9d; lpClass
0x180068c27  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180068c2c  xor     r8d, r8d; Reserved
0x180068c2f  lea     rax, [rsp+58h+arg_8]
0x180068c34  mov     rdx, rsi; lpSubKey
0x180068c37  mov     [rsp+58h+phkResult], rax; phkResult
0x180068c3c  mov     rcx, rbx; hKey
0x180068c3f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180068c48  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180068c50  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180068c58  call    cs:__imp_RegCreateKeyExW
0x180068c5e  mov     ebx, eax
0x180068c60  test    eax, eax
0x180068c62  jnz     short loc_180068C77
0x180068c64  mov     rcx, rdi; this
0x180068c67  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180068c6c  mov     ebx, eax
0x180068c6e  mov     rax, [rsp+58h+arg_8]
0x180068c73  mov     [rdi+8], rax
0x180068c77  mov     rcx, [rsp+58h+hKey]; hKey
0x180068c7c  test    rcx, rcx
0x180068c7f  jz      short loc_180068C87
0x180068c81  call    cs:__imp_RegCloseKey
0x180068c87  mov     rsi, [rsp+58h+arg_10]
0x180068c8c  mov     eax, ebx
0x180068c8e  mov     rbx, [rsp+58h+arg_0]
0x180068c93  add     rsp, 50h
0x180068c97  pop     rdi
0x180068c98  retn
```

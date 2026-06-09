# UnregisterServer

- ea: `0x14001812c`
- end: `0x1400182bd`
- name: `UnregisterServer`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400184cc`

## callees

- `0x140016c58`
- `0x14001812c`
- `0x1400182c4`
- `0x140018350`
- `0x140046430`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018204`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018246`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001827d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018291`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018204`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018246`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14001827d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140018291`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018169`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018169`

## string_xrefs

- `0x140018174`: `CLSID\`

## pseudocode

```c
__int64 __fastcall UnregisterServer(__int64 a1, __int64 a2, const GUID *a3)
{
  __int64 v3; // rcx
  const unsigned __int16 *v4; // r8
  __int64 v5; // rdx
  WCHAR *v6; // rax
  WCHAR *v7; // rcx
  WCHAR v9[128]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SubKey[128]; // [rsp+130h] [rbp+30h] BYREF
  OLECHAR sz[128]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR v12[128]; // [rsp+330h] [rbp+230h] BYREF

  StringFromGUID2(a3, sz, 128);
  v3 = 2147483646;
  v4 = L"CLSID\\";
  v5 = 128;
  v6 = v9;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *v6++ = *v4++;
    --v3;
    --v5;
  }
  while ( v5 );
  v7 = v6 - 1;
  if ( v5 )
    v7 = v6;
  *v7 = 0;
  StringCchCatW(v9, 0x80u, sz);
  StringCchPrintfW(SubKey, 0x80u, L"%s\\%s", v9, L"NotInsertable");
  RegDeleteKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0);
  StringCchCopyW(v12, 0x80u, L"APPID\\");
  StringCchCatW(v12, 0x80u, sz);
  RegDeleteKeyExW(HKEY_CLASSES_ROOT, v12, 0, 0);
  StringCchPrintfW(SubKey, 0x80u, L"%s\\%s", v9, L"LocalServer32");
  RegDeleteKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0);
  RegDeleteKeyExW(HKEY_CLASSES_ROOT, v9, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14001812c  mov     [rsp-8+arg_0], rbx
0x140018131  mov     [rsp-8+arg_8], rdi
0x140018136  push    rbp
0x140018137  lea     rbp, [rsp-340h]
0x14001813f  sub     rsp, 440h
0x140018146  mov     rax, cs:__security_cookie
0x14001814d  xor     rax, rsp
0x140018150  mov     [rbp+340h+var_10], rax
0x140018157  mov     rcx, r8; rguid
0x14001815a  lea     rdx, [rbp+340h+sz]; lpsz
0x140018161  mov     edi, 80h
0x140018166  mov     r8d, edi; cchMax
0x140018169  call    cs:__imp_StringFromGUID2
0x14001816f  mov     ecx, 7FFFFFFEh
0x140018174  lea     r8, aClsid; "CLSID\\"
0x14001817b  mov     edx, edi
0x14001817d  lea     rax, [rsp+440h+var_410]
0x140018182  xor     r10d, r10d
0x140018185  test    rcx, rcx
0x140018188  jz      short loc_1400181A9
0x14001818a  movzx   r9d, word ptr [r8]
0x14001818e  test    r9w, r9w
0x140018192  jz      short loc_1400181A9
0x140018194  mov     [rax], r9w
0x140018198  add     r8, 2
0x14001819c  add     rax, 2
0x1400181a0  dec     rcx
0x1400181a3  sub     rdx, 1
0x1400181a7  jnz     short loc_140018185
0x1400181a9  test    rdx, rdx
0x1400181ac  lea     rcx, [rax-2]
0x1400181b0  lea     r8, [rbp+340h+sz]; unsigned __int16 *
0x1400181b7  mov     rdx, rdi; unsigned __int64
0x1400181ba  cmovnz  rcx, rax
0x1400181be  mov     [rcx], r10w
0x1400181c2  lea     rcx, [rsp+440h+var_410]; unsigned __int16 *
0x1400181c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400181cc  lea     rax, aNotinsertable; "NotInsertable"
0x1400181d3  mov     rdx, rdi; unsigned __int64
0x1400181d6  lea     r9, [rsp+440h+var_410]
0x1400181db  mov     [rsp+440h+var_420], rax
0x1400181e0  lea     r8, aSS; "%s\\%s"
0x1400181e7  lea     rcx, [rbp+340h+SubKey]; unsigned __int16 *
0x1400181eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400181f0  mov     rbx, 0FFFFFFFF80000000h
0x1400181f7  lea     rdx, [rbp+340h+SubKey]; lpSubKey
0x1400181fb  mov     rcx, rbx; hKey
0x1400181fe  xor     r9d, r9d; Reserved
0x140018201  xor     r8d, r8d; samDesired
0x140018204  call    cs:__imp_RegDeleteKeyExW
0x14001820a  lea     r8, aAppid_0; "APPID\\"
0x140018211  mov     rdx, rdi; unsigned __int64
0x140018214  lea     rcx, [rbp+340h+var_110]; unsigned __int16 *
0x14001821b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140018220  lea     r8, [rbp+340h+sz]; unsigned __int16 *
0x140018227  mov     rdx, rdi; unsigned __int64
0x14001822a  lea     rcx, [rbp+340h+var_110]; unsigned __int16 *
0x140018231  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018236  xor     r9d, r9d; Reserved
0x140018239  lea     rdx, [rbp+340h+var_110]; lpSubKey
0x140018240  xor     r8d, r8d; samDesired
0x140018243  mov     rcx, rbx; hKey
0x140018246  call    cs:__imp_RegDeleteKeyExW
0x14001824c  lea     rax, aLocalserver32; "LocalServer32"
0x140018253  mov     rdx, rdi; unsigned __int64
0x140018256  lea     r9, [rsp+440h+var_410]
0x14001825b  mov     [rsp+440h+var_420], rax
0x140018260  lea     r8, aSS; "%s\\%s"
0x140018267  lea     rcx, [rbp+340h+SubKey]; unsigned __int16 *
0x14001826b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018270  xor     r9d, r9d; Reserved
0x140018273  lea     rdx, [rbp+340h+SubKey]; lpSubKey
0x140018277  xor     r8d, r8d; samDesired
0x14001827a  mov     rcx, rbx; hKey
0x14001827d  call    cs:__imp_RegDeleteKeyExW
0x140018283  xor     r9d, r9d; Reserved
0x140018286  lea     rdx, [rsp+440h+var_410]; lpSubKey
0x14001828b  xor     r8d, r8d; samDesired
0x14001828e  mov     rcx, rbx; hKey
0x140018291  call    cs:__imp_RegDeleteKeyExW
0x140018297  xor     eax, eax
0x140018299  mov     rcx, [rbp+340h+var_10]
0x1400182a0  xor     rcx, rsp; StackCookie
0x1400182a3  call    __security_check_cookie
0x1400182a8  lea     r11, [rsp+440h+var_s0]
0x1400182b0  mov     rbx, [r11+10h]
0x1400182b4  mov     rdi, [r11+18h]
0x1400182b8  mov     rsp, r11
0x1400182bb  pop     rbp
0x1400182bc  retn
```

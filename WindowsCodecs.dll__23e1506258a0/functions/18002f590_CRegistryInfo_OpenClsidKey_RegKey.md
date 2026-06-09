# CRegistryInfo::OpenClsidKey(RegKey *)

- ea: `0x18002f590`
- end: `0x18002f6f5`
- name: `?OpenClsidKey@CRegistryInfo@@IEAAJPEAVRegKey@@@Z`
- size: `357`
- prototype: `int(CRegistryInfo *__hidden this, struct RegKey *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e050`
- `0x180031150`
- `0x180043fa8`
- `0x1800442f0`
- `0x180044790`
- `0x18008f034`

## callees

- `0x18002f590`
- `0x18002f6fc`
- `0x18002f820`
- `0x1800bb784`
- `0x1800e2f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f5c6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f5c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f67d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f67d`

## string_xrefs

- `0x18002f5dc`: `CLSID\`

## pseudocode

```c
__int64 __fastcall CRegistryInfo::OpenClsidKey(const GUID *this, struct RegKey *a2)
{
  const wchar_t *v3; // rcx
  __int64 v4; // rdx
  WCHAR *v5; // r8
  __int64 v6; // rax
  WCHAR *v7; // rcx
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v12; // ecx
  HKEY phkResult; // [rsp+30h] [rbp-478h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR SubKey[512]; // [rsp+90h] [rbp-418h] BYREF

  if ( !StringFromGUID2(this + 1, sz, 40) )
  {
    v8 = -2147467259;
LABEL_16:
    if ( !(_DWORD)g_doStackCaptures )
      return v8;
    v12 = v8;
LABEL_18:
    DoStackCapture(v12);
    return v8;
  }
  v3 = L"CLSID\\";
  v4 = 512;
  v5 = SubKey;
  v6 = 2147483646;
  do
  {
    if ( !v6 )
      break;
    if ( !*v3 )
      break;
    *v5++ = *v3++;
    --v6;
    --v4;
  }
  while ( v4 );
  v7 = v5 - 1;
  v8 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v7 = v5;
  *v7 = 0;
  if ( !v4 )
    goto LABEL_16;
  v9 = StringCchCatW(SubKey, 0x200u, sz);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      return v8;
    v12 = v9;
    goto LABEL_18;
  }
  phkResult = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult)
    || (v10 = RegKey::Close(a2), *(_QWORD *)a2 = phkResult, v10) )
  {
    v8 = -2003292278;
    goto LABEL_16;
  }
  return v8;
}

```

## disassembly

```asm
0x18002f590  mov     [rsp+arg_10], rbx
0x18002f595  mov     [rsp+arg_18], rsi
0x18002f59a  push    rdi
0x18002f59b  sub     rsp, 4A0h
0x18002f5a2  mov     rax, cs:__security_cookie
0x18002f5a9  xor     rax, rsp
0x18002f5ac  mov     [rsp+4A8h+var_18], rax
0x18002f5b4  mov     rdi, rdx
0x18002f5b7  add     rcx, 10h; rguid
0x18002f5bb  lea     rdx, [rsp+4A8h+sz]; lpsz
0x18002f5c0  mov     r8d, 28h ; '('; cchMax
0x18002f5c6  call    cs:__imp_StringFromGUID2
0x18002f5cc  xor     esi, esi
0x18002f5ce  test    eax, eax
0x18002f5d0  jz      loc_18002F6CE
0x18002f5d6  mov     r10d, 200h
0x18002f5dc  lea     rcx, aClsid; "CLSID\\"
0x18002f5e3  mov     edx, r10d
0x18002f5e6  lea     r8, [rsp+4A8h+SubKey]
0x18002f5ee  mov     eax, 7FFFFFFEh
0x18002f5f3  test    rax, rax
0x18002f5f6  jz      short loc_18002F617
0x18002f5f8  movzx   r9d, word ptr [rcx]
0x18002f5fc  test    r9w, r9w
0x18002f600  jz      short loc_18002F617
0x18002f602  mov     [r8], r9w
0x18002f606  add     rcx, 2
0x18002f60a  add     r8, 2
0x18002f60e  dec     rax
0x18002f611  sub     rdx, 1
0x18002f615  jnz     short loc_18002F5F3
0x18002f617  mov     rax, rdx
0x18002f61a  lea     rcx, [r8-2]
0x18002f61e  neg     rax
0x18002f621  sbb     ebx, ebx
0x18002f623  not     ebx
0x18002f625  and     ebx, 8007007Ah
0x18002f62b  test    rdx, rdx
0x18002f62e  cmovnz  rcx, r8
0x18002f632  mov     [rcx], si
0x18002f635  jz      loc_18002F6D3
0x18002f63b  lea     r8, [rsp+4A8h+sz]; unsigned __int16 *
0x18002f640  mov     rdx, r10; unsigned __int64
0x18002f643  lea     rcx, [rsp+4A8h+SubKey]; unsigned __int16 *
0x18002f64b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f650  mov     ebx, eax
0x18002f652  test    eax, eax
0x18002f654  js      short loc_18002F6C2
0x18002f656  lea     rax, [rsp+4A8h+var_478]
0x18002f65b  mov     [rsp+4A8h+var_478], rsi
0x18002f660  mov     r9d, 20019h; samDesired
0x18002f666  mov     [rsp+4A8h+phkResult], rax; phkResult
0x18002f66b  xor     r8d, r8d; ulOptions
0x18002f66e  lea     rdx, [rsp+4A8h+SubKey]; lpSubKey
0x18002f676  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002f67d  call    cs:__imp_RegOpenKeyExW
0x18002f683  test    eax, eax
0x18002f685  jnz     short loc_18002F6E4
0x18002f687  mov     rcx, rdi; this
0x18002f68a  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x18002f68f  mov     rcx, [rsp+4A8h+var_478]
0x18002f694  mov     [rdi], rcx
0x18002f697  test    eax, eax
0x18002f699  jnz     short loc_18002F6E4
0x18002f69b  mov     eax, ebx
0x18002f69d  mov     rcx, [rsp+4A8h+var_18]
0x18002f6a5  xor     rcx, rsp; StackCookie
0x18002f6a8  call    __security_check_cookie
0x18002f6ad  lea     r11, [rsp+4A8h+var_8]
0x18002f6b5  mov     rbx, [r11+20h]
0x18002f6b9  mov     rsi, [r11+28h]
0x18002f6bd  mov     rsp, r11
0x18002f6c0  pop     rdi
0x18002f6c1  retn
0x18002f6c2  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18002f6c8  jz      short loc_18002F6EB
0x18002f6ca  mov     ecx, eax
0x18002f6cc  jmp     short loc_18002F6DD
0x18002f6ce  mov     ebx, 80004005h
0x18002f6d3  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x18002f6d9  jz      short loc_18002F69B
0x18002f6db  mov     ecx, ebx; int
0x18002f6dd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002f6e2  jmp     short loc_18002F69B
0x18002f6e4  mov     ebx, 88982F8Ah
0x18002f6e9  jmp     short loc_18002F6D3
0x18002f6eb  test    eax, eax
0x18002f6ed  jns     loc_18002F656
0x18002f6f3  jmp     short loc_18002F69B
```

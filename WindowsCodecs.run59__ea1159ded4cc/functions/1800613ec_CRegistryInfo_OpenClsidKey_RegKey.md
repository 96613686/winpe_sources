# CRegistryInfo::OpenClsidKey(RegKey *)

- ea: `0x1800613ec`
- end: `0x18006155e`
- name: `?OpenClsidKey@CRegistryInfo@@IEAAJPEAVRegKey@@@Z`
- size: `370`
- prototype: `int(CRegistryInfo *__hidden this, struct RegKey *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002ef70`
- `0x18006108c`
- `0x1800616c0`
- `0x180061d70`
- `0x180062104`
- `0x180064c44`

## callees

- `0x1800613ec`
- `0x180061564`
- `0x18006168c`
- `0x1800bd9d4`
- `0x1800e5e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180061422`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180061422`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800614df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800614df`

## string_xrefs

- `0x18006143e`: `CLSID\`

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
0x1800613ec  mov     [rsp+arg_10], rbx
0x1800613f1  mov     [rsp+arg_18], rsi
0x1800613f6  push    rdi
0x1800613f7  sub     rsp, 4A0h
0x1800613fe  mov     rax, cs:__security_cookie
0x180061405  xor     rax, rsp
0x180061408  mov     [rsp+4A8h+var_18], rax
0x180061410  mov     rdi, rdx
0x180061413  add     rcx, 10h; rguid
0x180061417  lea     rdx, [rsp+4A8h+sz]; lpsz
0x18006141c  mov     r8d, 28h ; '('; cchMax
0x180061422  call    cs:__imp_StringFromGUID2
0x180061429  nop     dword ptr [rax+rax+00h]
0x18006142e  xor     esi, esi
0x180061430  test    eax, eax
0x180061432  jz      loc_180061537
0x180061438  mov     r10d, 200h
0x18006143e  lea     rcx, aClsid; "CLSID\\"
0x180061445  mov     edx, r10d
0x180061448  lea     r8, [rsp+4A8h+SubKey]
0x180061450  mov     eax, 7FFFFFFEh
0x180061455  test    rax, rax
0x180061458  jz      short loc_180061479
0x18006145a  movzx   r9d, word ptr [rcx]
0x18006145e  test    r9w, r9w
0x180061462  jz      short loc_180061479
0x180061464  mov     [r8], r9w
0x180061468  add     rcx, 2
0x18006146c  add     r8, 2
0x180061470  dec     rax
0x180061473  sub     rdx, 1
0x180061477  jnz     short loc_180061455
0x180061479  mov     rax, rdx
0x18006147c  lea     rcx, [r8-2]
0x180061480  neg     rax
0x180061483  sbb     ebx, ebx
0x180061485  not     ebx
0x180061487  and     ebx, 8007007Ah
0x18006148d  test    rdx, rdx
0x180061490  cmovnz  rcx, r8
0x180061494  mov     [rcx], si
0x180061497  jz      loc_18006153C
0x18006149d  lea     r8, [rsp+4A8h+sz]; unsigned __int16 *
0x1800614a2  mov     rdx, r10; unsigned __int64
0x1800614a5  lea     rcx, [rsp+4A8h+SubKey]; unsigned __int16 *
0x1800614ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800614b2  mov     ebx, eax
0x1800614b4  test    eax, eax
0x1800614b6  js      short loc_18006152B
0x1800614b8  lea     rax, [rsp+4A8h+var_478]
0x1800614bd  mov     [rsp+4A8h+var_478], rsi
0x1800614c2  mov     r9d, 20019h; samDesired
0x1800614c8  mov     [rsp+4A8h+phkResult], rax; phkResult
0x1800614cd  xor     r8d, r8d; ulOptions
0x1800614d0  lea     rdx, [rsp+4A8h+SubKey]; lpSubKey
0x1800614d8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800614df  call    cs:__imp_RegOpenKeyExW
0x1800614e6  nop     dword ptr [rax+rax+00h]
0x1800614eb  test    eax, eax
0x1800614ed  jnz     short loc_18006154D
0x1800614ef  mov     rcx, rdi; this
0x1800614f2  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x1800614f7  mov     rcx, [rsp+4A8h+var_478]
0x1800614fc  mov     [rdi], rcx
0x1800614ff  test    eax, eax
0x180061501  jnz     short loc_18006154D
0x180061503  mov     eax, ebx
0x180061505  mov     rcx, [rsp+4A8h+var_18]
0x18006150d  xor     rcx, rsp; StackCookie
0x180061510  call    __security_check_cookie
0x180061515  lea     r11, [rsp+4A8h+var_8]
0x18006151d  mov     rbx, [r11+20h]
0x180061521  mov     rsi, [r11+28h]
0x180061525  mov     rsp, r11
0x180061528  pop     rdi
0x180061529  retn
0x18006152b  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180061531  jz      short loc_180061554
0x180061533  mov     ecx, eax
0x180061535  jmp     short loc_180061546
0x180061537  mov     ebx, 80004005h
0x18006153c  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180061542  jz      short loc_180061503
0x180061544  mov     ecx, ebx; int
0x180061546  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18006154b  jmp     short loc_180061503
0x18006154d  mov     ebx, 88982F8Ah
0x180061552  jmp     short loc_18006153C
0x180061554  test    eax, eax
0x180061556  jns     loc_1800614B8
0x18006155c  jmp     short loc_180061503
```

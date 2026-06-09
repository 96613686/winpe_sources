# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400041b4`
- end: `0x140004276`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `194`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c40`

## callees

- `0x1400040ac`
- `0x1400041b4`
- `0x1400137e0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140004236`
- `ADVAPI32!RegCreateKeyExW` at `0x140004236`
- `ADVAPI32!RegCloseKey` at `0x14000424a`
- `ADVAPI32!RegCloseKey` at `0x14000424a`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(ATL::CRegKey *this, HKEY a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  ATL::CAtlTransactionManager *v5; // rcx
  LSTATUS v6; // eax
  unsigned int v7; // ecx
  unsigned __int16 *dwOptions; // [rsp+20h] [rbp-58h]
  REGSAM samDesired; // [rsp+28h] [rbp-50h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES *phkResult; // [rsp+38h] [rbp-40h]
  HKEY v13; // [rsp+50h] [rbp-28h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-20h] BYREF

  v13 = 0;
  v5 = (ATL::CAtlTransactionManager *)*((_QWORD *)this + 2);
  if ( v5 )
    v6 = ATL::CAtlTransactionManager::RegCreateKeyExW(
           v5,
           (HKEY)&v13,
           a3,
           (__int64)a4,
           dwOptions,
           samDesired,
           lpSecurityAttributes,
           phkResult,
           &v13,
           &dwDisposition);
  else
    v6 = RegCreateKeyExW(HKEY_CLASSES_ROOT, a3, 0, 0, 0, 0x2001Fu, 0, &v13, &dwDisposition);
  v7 = v6;
  if ( !v6 )
  {
    if ( *(_QWORD *)this )
      v7 = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = v13;
    *((_DWORD *)this + 2) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1400041b4  mov     r11, rsp
0x1400041b7  push    rbx
0x1400041b8  sub     rsp, 70h
0x1400041bc  mov     rax, cs:__security_cookie
0x1400041c3  xor     rax, rsp
0x1400041c6  mov     [rsp+78h+var_18], rax
0x1400041cb  mov     rax, r8
0x1400041ce  mov     rbx, rcx
0x1400041d1  mov     qword ptr [r11-28h], 0
0x1400041d9  mov     rcx, [rcx+10h]; this
0x1400041dd  test    rcx, rcx
0x1400041e0  jz      short loc_1400041F9
0x1400041e2  lea     rdx, [r11-20h]
0x1400041e6  mov     [r11-30h], rdx
0x1400041ea  lea     rdx, [r11-28h]; HKEY
0x1400041ee  mov     [r11-38h], rdx
0x1400041f2  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x1400041f7  jmp     short loc_14000423C
0x1400041f9  lea     rcx, [rsp+78h+dwDisposition]
0x1400041fe  mov     [rsp+78h+lpdwDisposition], rcx; lpdwDisposition
0x140004203  lea     rcx, [rsp+78h+var_28]
0x140004208  mov     [rsp+78h+phkResult], rcx; phkResult
0x14000420d  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140004216  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x14000421e  mov     dword ptr [rsp+78h+dwOptions], 0; dwOptions
0x140004226  xor     r9d, r9d; lpClass
0x140004229  xor     r8d, r8d; Reserved
0x14000422c  mov     rdx, rax; lpSubKey
0x14000422f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140004236  call    cs:__imp_RegCreateKeyExW
0x14000423c  mov     ecx, eax
0x14000423e  test    eax, eax
0x140004240  jnz     short loc_140004261
0x140004242  cmp     [rbx], rcx
0x140004245  jz      short loc_140004252
0x140004247  mov     rcx, [rbx]; hKey
0x14000424a  call    cs:__imp_RegCloseKey
0x140004250  mov     ecx, eax
0x140004252  mov     rax, [rsp+78h+var_28]
0x140004257  mov     [rbx], rax
0x14000425a  mov     dword ptr [rbx+8], 0
0x140004261  mov     eax, ecx
0x140004263  mov     rcx, [rsp+78h+var_18]
0x140004268  xor     rcx, rsp; StackCookie
0x14000426b  call    __security_check_cookie
0x140004270  add     rsp, 70h
0x140004274  pop     rbx
0x140004275  retn
```

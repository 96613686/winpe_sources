# DMClient::GetConfigRefreshKey(ushort const *,HKEY__ * *,int)

- ea: `0x140058594`
- end: `0x14005879c`
- name: `?GetConfigRefreshKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `520`
- prototype: `__int64 __fastcall(DMClient *__hidden this, const unsigned __int16 *, HKEY *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140019a6c`
- `0x1400584ac`
- `0x1400587a4`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140009fc4`
- `0x140058594`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1400585f8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400585f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140058734`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140058734`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058758`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005871c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005871c`

## string_xrefs

- `0x1400586ba`: `ConfigRefresh`

## pseudocode

```c
__int64 __fastcall DMClient::GetConfigRefreshKey(DMClient *this, unsigned __int16 *a2, HKEY *a3)
{
  int v3; // edi
  unsigned int v6; // ebx
  __int64 v7; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // r9
  WCHAR *v12; // rcx
  __int64 result; // rax
  LSTATUS v14; // eax
  HKEY v15; // rdi
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = (int)a3;
  memset_0(SubKey, 0, 0x208u);
  if ( !a2 )
    return (unsigned int)-2147024809;
  v7 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v9 = L"OSData\\";
  v10 = 260;
  v11 = SubKey;
  if ( !IsStateSeparationEnabled )
    v9 = &::SubKey;
  do
  {
    if ( !v7 )
      break;
    if ( !*v9 )
      break;
    *v11++ = *v9++;
    --v7;
    --v10;
  }
  while ( v10 );
  v12 = v11 - 1;
  if ( v10 )
    v12 = v11;
  *v12 = 0;
  if ( !v10 )
    return 2147942522LL;
  result = StringCchCatW(SubKey, 0x104u, c_szEnrollmentsDB);
  if ( (int)result >= 0 )
  {
    result = StringCchCatW(SubKey, 0x104u, (const unsigned __int16 *)this);
    if ( (int)result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x104u, L"\\");
      if ( (int)result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x104u, c_szEnrollmentsDBConfigRefresh);
        if ( (int)result >= 0 )
        {
          hKey = 0;
          if ( v3 )
          {
            dwDisposition = 0;
            v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
          }
          else
          {
            v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
          }
          v6 = v14;
          if ( v14 )
          {
            v15 = 0;
            if ( v14 > 0 )
              v6 = (unsigned __int16)v14 | 0x80070000;
            if ( hKey )
              RegCloseKey(hKey);
            if ( (v6 & 0x80000000) != 0 )
              return v6;
          }
          else
          {
            v15 = hKey;
            v6 = 0;
          }
          *(_QWORD *)a2 = v15;
          return v6;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140058594  mov     [rsp-8+arg_10], rbx
0x140058599  mov     [rsp-8+arg_18], rsi
0x14005859e  push    rbp
0x14005859f  push    rdi
0x1400585a0  push    r12
0x1400585a2  push    r14
0x1400585a4  push    r15
0x1400585a6  lea     rbp, [rsp-180h]
0x1400585ae  sub     rsp, 280h
0x1400585b5  mov     rax, cs:__security_cookie
0x1400585bc  xor     rax, rsp
0x1400585bf  mov     [rbp+1A0h+var_30], rax
0x1400585c6  mov     edi, r8d
0x1400585c9  mov     rsi, rdx
0x1400585cc  mov     r14, rcx
0x1400585cf  xor     edx, edx; Val
0x1400585d1  mov     r8d, 208h; Size
0x1400585d7  lea     rcx, [rsp+2A0h+SubKey]; void *
0x1400585dc  call    memset_0
0x1400585e1  xor     r15d, r15d
0x1400585e4  test    rsi, rsi
0x1400585e7  jnz     short loc_1400585F3
0x1400585e9  mov     ebx, 80070057h
0x1400585ee  jmp     loc_14005876F
0x1400585f3  mov     ebx, 7FFFFFFEh
0x1400585f8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400585fe  lea     rdx, SubKey
0x140058605  mov     r12d, 104h
0x14005860b  test    al, al
0x14005860d  lea     rcx, aOsdata; "OSData\\"
0x140058614  mov     r8d, r12d
0x140058617  lea     r9, [rsp+2A0h+SubKey]
0x14005861c  cmovz   rcx, rdx
0x140058620  test    rbx, rbx
0x140058623  jz      short loc_140058642
0x140058625  movzx   eax, word ptr [rcx]
0x140058628  test    ax, ax
0x14005862b  jz      short loc_140058642
0x14005862d  mov     [r9], ax
0x140058631  add     rcx, 2
0x140058635  add     r9, 2
0x140058639  dec     rbx
0x14005863c  sub     r8, 1
0x140058640  jnz     short loc_140058620
0x140058642  mov     rax, r8
0x140058645  lea     rcx, [r9-2]
0x140058649  neg     rax
0x14005864c  sbb     edx, edx
0x14005864e  not     edx
0x140058650  and     edx, 8007007Ah
0x140058656  test    r8, r8
0x140058659  cmovnz  rcx, r9
0x14005865d  mov     [rcx], r15w
0x140058661  jnz     short loc_14005866A
0x140058663  mov     eax, edx
0x140058665  jmp     loc_140058771
0x14005866a  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x140058671  mov     rdx, r12; unsigned __int64
0x140058674  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x140058679  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005867e  test    eax, eax
0x140058680  js      loc_140058771
0x140058686  mov     r8, r14; unsigned __int16 *
0x140058689  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x14005868e  mov     rdx, r12; unsigned __int64
0x140058691  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140058696  test    eax, eax
0x140058698  js      loc_140058771
0x14005869e  lea     r8, asc_140061150; "\\"
0x1400586a5  mov     rdx, r12; unsigned __int64
0x1400586a8  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1400586ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400586b2  test    eax, eax
0x1400586b4  js      loc_140058771
0x1400586ba  lea     r8, ?c_szEnrollmentsDBConfigRefresh@@3PAGA; "ConfigRefresh"
0x1400586c1  mov     rdx, r12; unsigned __int64
0x1400586c4  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1400586c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400586ce  test    eax, eax
0x1400586d0  js      loc_140058771
0x1400586d6  xor     r8d, r8d; ulOptions
0x1400586d9  mov     [rsp+2A0h+hKey], r15
0x1400586de  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1400586e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400586ea  test    edi, edi
0x1400586ec  jz      short loc_140058724
0x1400586ee  lea     rax, [rsp+2A0h+dwDisposition]
0x1400586f3  mov     [rsp+2A0h+dwDisposition], r15d
0x1400586f8  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1400586fd  xor     r9d, r9d; lpClass
0x140058700  lea     rax, [rsp+2A0h+hKey]
0x140058705  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14005870a  mov     [rsp+2A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14005870f  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x140058717  mov     [rsp+2A0h+dwOptions], r15d; dwOptions
0x14005871c  call    cs:__imp_RegCreateKeyExW
0x140058722  jmp     short loc_14005873A
0x140058724  lea     rax, [rsp+2A0h+hKey]
0x140058729  mov     r9d, 20019h; samDesired
0x14005872f  mov     qword ptr [rsp+2A0h+dwOptions], rax; phkResult
0x140058734  call    cs:__imp_RegOpenKeyExW
0x14005873a  mov     ebx, eax
0x14005873c  test    eax, eax
0x14005873e  jz      short loc_140058764
0x140058740  mov     rdi, r15
0x140058743  jle     short loc_14005874E
0x140058745  movzx   ebx, bx
0x140058748  or      ebx, 80070000h
0x14005874e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140058753  test    rcx, rcx
0x140058756  jz      short loc_14005875E
0x140058758  call    cs:__imp_RegCloseKey
0x14005875e  test    ebx, ebx
0x140058760  js      short loc_14005876F
0x140058762  jmp     short loc_14005876C
0x140058764  mov     rdi, [rsp+2A0h+hKey]
0x140058769  mov     ebx, r15d
0x14005876c  mov     [rsi], rdi
0x14005876f  mov     eax, ebx
0x140058771  mov     rcx, [rbp+1A0h+var_30]
0x140058778  xor     rcx, rsp; StackCookie
0x14005877b  call    __security_check_cookie
0x140058780  lea     r11, [rsp+2A0h+var_20]
0x140058788  mov     rbx, [r11+40h]
0x14005878c  mov     rsi, [r11+48h]
0x140058790  mov     rsp, r11
0x140058793  pop     r15
0x140058795  pop     r14
0x140058797  pop     r12
0x140058799  pop     rdi
0x14005879a  pop     rbp
0x14005879b  retn
```

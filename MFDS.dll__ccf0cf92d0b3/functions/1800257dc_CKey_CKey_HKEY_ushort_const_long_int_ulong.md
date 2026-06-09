# CKey::CKey(HKEY__ *,ushort const *,long *,int,ulong)

- ea: `0x1800257dc`
- end: `0x180025906`
- name: `??0CKey@@QEAA@PEAUHKEY__@@PEBGPEAJHK@Z`
- size: `298`
- prototype: `CKey *(CKey *__hidden this, HKEY, const unsigned __int16 *, int *, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024bcc`

## callees

- `0x1800257dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025843`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800258bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800258bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258f1`

## pseudocode

```c
CKey *__fastcall CKey::CKey(CKey *this, HKEY a2, const unsigned __int16 *a3, int *a4, DWORD cbSecurityDescriptor)
{
  HKEY *v5; // rsi
  DWORD *v6; // r15
  DWORD *lpcValues; // rbp
  int v10; // ebx
  struct _FILETIME ftLastWriteTime; // [rsp+A0h] [rbp+8h] BYREF

  v5 = (HKEY *)((char *)this + 8);
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = 0;
  v6 = (DWORD *)((char *)this + 88);
  lpcValues = (DWORD *)((char *)this + 96);
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 24) = 0;
  *(_QWORD *)this = &CKey::`vftable';
  *((_QWORD *)this + 10) = (char *)this + 20;
  v10 = RegOpenKeyExW(a2, a3, 0, 0x20019u, (PHKEY)this + 1);
  if ( !v10 )
  {
    cbSecurityDescriptor = 0;
    ftLastWriteTime = 0;
    v10 = RegQueryInfoKeyW(
            *v5,
            0,
            0,
            0,
            v6,
            (LPDWORD)this + 23,
            0,
            lpcValues,
            (LPDWORD)this + 25,
            (LPDWORD)this + 26,
            &cbSecurityDescriptor,
            &ftLastWriteTime);
    if ( v10 )
    {
      RegCloseKey(*v5);
      *v5 = 0;
    }
  }
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  *a4 = v10;
  return this;
}

```

## disassembly

```asm
0x1800257dc  push    rbx
0x1800257de  push    rbp
0x1800257df  push    rsi
0x1800257e0  push    rdi
0x1800257e1  push    r14
0x1800257e3  push    r15
0x1800257e5  sub     rsp, 68h
0x1800257e9  lea     rsi, [rcx+8]
0x1800257ed  mov     dword ptr [rcx+10h], 0
0x1800257f4  mov     r10, r8
0x1800257f7  mov     qword ptr [rsi], 0
0x1800257fe  mov     r11, rdx
0x180025801  mov     [rsp+98h+phkResult], rsi; phkResult
0x180025806  lea     r15, [rcx+58h]
0x18002580a  mov     r14, r9
0x18002580d  lea     rbp, [rcx+60h]
0x180025811  mov     dword ptr [r15], 0
0x180025818  lea     rax, ??_7CKey@@6B@; const CKey::`vftable'
0x18002581f  mov     dword ptr [rbp+0], 0
0x180025826  mov     [rcx], rax
0x180025829  mov     rdi, rcx
0x18002582c  lea     rax, [rcx+14h]
0x180025830  mov     r9d, 20019h; samDesired
0x180025836  mov     [rcx+50h], rax
0x18002583a  xor     r8d, r8d; ulOptions
0x18002583d  mov     rcx, r11; hKey
0x180025840  mov     rdx, r10; lpSubKey
0x180025843  call    cs:__imp_RegOpenKeyExW
0x18002584a  nop     dword ptr [rax+rax+00h]
0x18002584f  mov     ebx, eax
0x180025851  test    eax, eax
0x180025853  jnz     short loc_1800258CD
0x180025855  lea     r8, [rsp+98h+ftLastWriteTime]
0x18002585d  mov     [rsp+98h+cbSecurityDescriptor], eax
0x180025864  mov     [rsp+98h+lpftLastWriteTime], r8; lpftLastWriteTime
0x180025869  lea     rax, [rdi+68h]
0x18002586d  lea     r8, [rsp+98h+cbSecurityDescriptor]
0x180025875  mov     qword ptr [rsp+98h+ftLastWriteTime.dwLowDateTime], 0
0x180025881  mov     [rsp+98h+lpcbSecurityDescriptor], r8; lpcbSecurityDescriptor
0x180025886  lea     rcx, [rdi+64h]
0x18002588a  mov     [rsp+98h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002588f  lea     rdx, [rdi+5Ch]
0x180025893  mov     [rsp+98h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180025898  xor     r9d, r9d; lpReserved
0x18002589b  mov     rcx, [rsi]; hKey
0x18002589e  xor     r8d, r8d; lpcchClass
0x1800258a1  mov     [rsp+98h+lpcValues], rbp; lpcValues
0x1800258a6  mov     [rsp+98h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800258af  mov     [rsp+98h+lpcbMaxSubKeyLen], rdx; lpcbMaxSubKeyLen
0x1800258b4  xor     edx, edx; lpClass
0x1800258b6  mov     [rsp+98h+phkResult], r15; lpcSubKeys
0x1800258bb  call    cs:__imp_RegQueryInfoKeyW
0x1800258c2  nop     dword ptr [rax+rax+00h]
0x1800258c7  mov     ebx, eax
0x1800258c9  test    eax, eax
0x1800258cb  jnz     short loc_1800258EE
0x1800258cd  test    ebx, ebx
0x1800258cf  jle     short loc_1800258DA
0x1800258d1  movzx   ebx, bx
0x1800258d4  or      ebx, 80070000h
0x1800258da  mov     [r14], ebx
0x1800258dd  mov     rax, rdi
0x1800258e0  add     rsp, 68h
0x1800258e4  pop     r15
0x1800258e6  pop     r14
0x1800258e8  pop     rdi
0x1800258e9  pop     rsi
0x1800258ea  pop     rbp
0x1800258eb  pop     rbx
0x1800258ec  retn
0x1800258ee  mov     rcx, [rsi]; hKey
0x1800258f1  call    cs:__imp_RegCloseKey
0x1800258f8  nop     dword ptr [rax+rax+00h]
0x1800258fd  mov     qword ptr [rsi], 0
0x180025904  jmp     short loc_1800258CD
```

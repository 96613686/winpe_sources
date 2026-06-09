# EEDBManager::UpdateEnrollment(Enrollment *)

- ea: `0x180018c54`
- end: `0x180018da1`
- name: `?UpdateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct Enrollment *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ac70`

## callees

- `0x180001c60`
- `0x1800075e8`
- `0x180011828`
- `0x180017e2c`
- `0x18001895c`
- `0x180018c54`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018d55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018d55`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018ca9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018ca9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EEDBManager::UpdateEnrollment(EEDBManager *this, struct Enrollment *a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  HKEY v8; // [rsp+40h] [rbp-69h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-59h] BYREF
  wchar_t String1[40]; // [rsp+A0h] [rbp-9h] BYREF

  *(_DWORD *)Data = 63;
  hKey = 0;
  v8 = 0;
  String1[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 28), sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, String1);
    if ( v3 >= 0 )
    {
      v3 = EEDBManager::OpenEnrollmentHKEY(HKEY_LOCAL_MACHINE, String1, 131078, &v8, 0, 0);
      if ( v3 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          v8);
        v3 = (*(__int64 (__fastcall **)(struct Enrollment *, BYTE *))(*(_QWORD *)a2 + 56LL))(a2, Data);
        if ( v3 >= 0 )
        {
          v4 = RegSetValueExW(hKey, L"EnrollmentState", 0, 4u, Data, 4u);
          if ( v4 )
          {
            if ( v4 > 0 )
              v3 = (unsigned __int16)v4 | 0x80070000;
            else
              v3 = v4;
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018c54  mov     [rsp-8+arg_0], rbx
0x180018c59  mov     [rsp-8+arg_10], rdi
0x180018c5e  push    rbp
0x180018c5f  lea     rbp, [rsp-57h]
0x180018c64  sub     rsp, 100h
0x180018c6b  mov     rax, cs:__security_cookie
0x180018c72  xor     rax, rsp
0x180018c75  mov     [rbp+57h+var_10], rax
0x180018c79  mov     rdi, rdx
0x180018c7c  mov     dword ptr [rbp+57h+Data], 3Fh ; '?'
0x180018c83  mov     [rbp+57h+hKey], 0
0x180018c8b  mov     [rbp+57h+var_C0], 0
0x180018c93  xor     eax, eax
0x180018c95  mov     [rbp+57h+String1], ax
0x180018c99  mov     [rbp+57h+sz], ax
0x180018c9d  lea     rcx, [rdx+1Ch]; rguid
0x180018ca1  lea     r8d, [rax+27h]; cchMax
0x180018ca5  lea     rdx, [rbp+57h+sz]; lpsz
0x180018ca9  call    cs:__imp_StringFromGUID2
0x180018cb0  nop     dword ptr [rax+rax+00h]
0x180018cb5  cmp     eax, 27h ; '''
0x180018cb8  jz      short loc_180018CC4
0x180018cba  mov     ebx, 8000FFFFh
0x180018cbf  jmp     loc_180018D74
0x180018cc4  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180018cc8  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x180018ccc  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180018cd1  mov     ebx, eax
0x180018cd3  test    eax, eax
0x180018cd5  js      loc_180018D74
0x180018cdb  mov     qword ptr [rsp+100h+cbData], 0; unsigned __int64
0x180018ce4  mov     [rsp+100h+lpData], 0; unsigned __int16 *
0x180018ced  lea     r9, [rbp+57h+var_C0]; HKEY *
0x180018cf1  mov     r8d, 20006h; unsigned int
0x180018cf7  lea     rdx, [rbp+57h+String1]; String1
0x180018cfb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018d02  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x180018d07  mov     ebx, eax
0x180018d09  test    eax, eax
0x180018d0b  js      short loc_180018D74
0x180018d0d  mov     rdx, [rbp+57h+var_C0]
0x180018d11  lea     rcx, [rbp+57h+hKey]
0x180018d15  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018d1a  mov     rax, [rdi]
0x180018d1d  lea     rdx, [rbp+57h+Data]
0x180018d21  mov     rcx, rdi
0x180018d24  mov     rax, [rax+38h]
0x180018d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d2d  mov     ebx, eax
0x180018d2f  test    eax, eax
0x180018d31  js      short loc_180018D74
0x180018d33  mov     r9d, 4; dwType
0x180018d39  mov     [rsp+100h+cbData], r9d; cbData
0x180018d3e  lea     rax, [rbp+57h+Data]
0x180018d42  mov     [rsp+100h+lpData], rax; lpData
0x180018d47  xor     r8d, r8d; Reserved
0x180018d4a  lea     rdx, aEnrollmentstat; "EnrollmentState"
0x180018d51  mov     rcx, [rbp+57h+hKey]; hKey
0x180018d55  call    cs:__imp_RegSetValueExW
0x180018d5c  nop     dword ptr [rax+rax+00h]
0x180018d61  test    eax, eax
0x180018d63  jz      short loc_180018D74
0x180018d65  jg      short loc_180018D6B
0x180018d67  mov     ebx, eax
0x180018d69  jmp     short loc_180018D74
0x180018d6b  movzx   ebx, ax
0x180018d6e  or      ebx, 80070000h
0x180018d74  lea     rcx, [rbp+57h+hKey]
0x180018d78  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180018d7d  mov     eax, ebx
0x180018d7f  mov     rcx, [rbp+57h+var_10]
0x180018d83  xor     rcx, rsp; StackCookie
0x180018d86  call    __security_check_cookie
0x180018d8b  lea     r11, [rsp+100h+var_s0]
0x180018d93  mov     rbx, [r11+10h]
0x180018d97  mov     rdi, [r11+20h]
0x180018d9b  mov     rsp, r11
0x180018d9e  pop     rbp
0x180018d9f  retn
```

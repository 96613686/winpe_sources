# GetPackageFullNameFromManifest(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x180015a2c`
- end: `0x180015c26`
- name: `?GetPackageFullNameFromManifest@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000d2cc`

## callees

- `0x1800065f8`
- `0x18000a2c0`
- `0x180015674`
- `0x180015850`
- `0x180015a2c`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015bd5`
- `ole32!CoTaskMemFree` at `0x180015bd5`

## pseudocode

```c
__int64 __fastcall GetPackageFullNameFromManifest(const WCHAR *a1, __int64 a2, char a3)
{
  int BundleManifestReader; // ebx
  LPCWSTR v5; // rcx
  __int64 v6; // rdx
  struct IAppxManifestReader *v8; // [rsp+20h] [rbp-10h] BYREF
  struct IAppxBundleManifestReader *v9; // [rsp+28h] [rbp-8h] BYREF
  __int64 v10; // [rsp+40h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+28h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  pv = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( a3 )
  {
    BundleManifestReader = GetBundleManifestReader(a1, &v9);
    if ( BundleManifestReader < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_26;
      v6 = 83;
      goto LABEL_8;
    }
    BundleManifestReader = ((__int64 (__fastcall *)(struct IAppxBundleManifestReader *, __int64 *))v9->lpVtbl->GetPackageId)(
                             v9,
                             &v10);
    if ( BundleManifestReader < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_26;
      v6 = 84;
      goto LABEL_8;
    }
  }
  else
  {
    BundleManifestReader = GetManifestReader(a1, &v8);
    if ( BundleManifestReader < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_26;
      v6 = 85;
      goto LABEL_8;
    }
    BundleManifestReader = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 *))v8->lpVtbl->GetPackageId)(
                             v8,
                             &v10);
    if ( BundleManifestReader < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_26;
      v6 = 86;
      goto LABEL_8;
    }
  }
  BundleManifestReader = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 72LL))(v10, &pv);
  if ( BundleManifestReader >= 0 )
  {
    std::wstring::assign(a2, pv);
    goto LABEL_26;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
    goto LABEL_26;
  v6 = 87;
LABEL_8:
  WPP_SF_d(
    *((_QWORD *)v5 + 2),
    v6,
    &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
    (unsigned int)BundleManifestReader);
LABEL_26:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v8 )
    ((void (__fastcall *)(struct IAppxManifestReader *))v8->lpVtbl->Release)(v8);
  return (unsigned int)BundleManifestReader;
}

```

## disassembly

```asm
0x180015a2c  mov     [rsp-8+arg_8], rbx
0x180015a31  mov     [rsp-8+arg_10], rdi
0x180015a36  push    rbp
0x180015a37  mov     rbp, rsp
0x180015a3a  sub     rsp, 30h
0x180015a3e  mov     [rbp+var_10], 0
0x180015a46  mov     rdi, rdx
0x180015a49  mov     [rbp+var_8], 0
0x180015a51  mov     [rbp+arg_0], 0
0x180015a59  mov     [rbp+pv], 0
0x180015a61  test    rcx, rcx
0x180015a64  jnz     short loc_180015A70
0x180015a66  mov     ebx, 80070057h
0x180015a6b  jmp     loc_180015C13
0x180015a70  test    r8b, r8b
0x180015a73  jz      loc_180015B0C
0x180015a79  lea     rdx, [rbp+var_8]; struct IAppxBundleManifestReader **
0x180015a7d  call    ?GetBundleManifestReader@@YAJPEBGPEAPEAUIAppxBundleManifestReader@@@Z; GetBundleManifestReader(ushort const *,IAppxBundleManifestReader * *)
0x180015a82  mov     ebx, eax
0x180015a84  test    eax, eax
0x180015a86  jns     short loc_180015AC6
0x180015a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a8f  lea     rax, WPP_GLOBAL_Control
0x180015a96  cmp     rcx, rax
0x180015a99  jz      loc_180015BCC
0x180015a9f  test    byte ptr [rcx+1Ch], 4
0x180015aa3  jz      loc_180015BCC
0x180015aa9  mov     edx, 53h ; 'S'
0x180015aae  mov     rcx, [rcx+10h]
0x180015ab2  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015ab9  mov     r9d, ebx
0x180015abc  call    WPP_SF_d
0x180015ac1  jmp     loc_180015BCC
0x180015ac6  mov     rcx, [rbp+var_8]
0x180015aca  lea     rdx, [rbp+arg_0]
0x180015ace  mov     rax, [rcx]
0x180015ad1  mov     rax, [rax+18h]
0x180015ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ada  mov     ebx, eax
0x180015adc  test    eax, eax
0x180015ade  jns     loc_180015B83
0x180015ae4  mov     rcx, cs:WPP_GLOBAL_Control; pszFile
0x180015aeb  lea     rax, WPP_GLOBAL_Control
0x180015af2  cmp     rcx, rax
0x180015af5  jz      loc_180015BCC
0x180015afb  test    byte ptr [rcx+1Ch], 4
0x180015aff  jz      loc_180015BCC
0x180015b05  mov     edx, 54h ; 'T'
0x180015b0a  jmp     short loc_180015AAE
0x180015b0c  lea     rdx, [rbp+var_10]; struct IAppxManifestReader **
0x180015b10  call    ?GetManifestReader@@YAJPEBGPEAPEAUIAppxManifestReader@@@Z; GetManifestReader(ushort const *,IAppxManifestReader * *)
0x180015b15  mov     ebx, eax
0x180015b17  test    eax, eax
0x180015b19  jns     short loc_180015B46
0x180015b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b22  lea     rax, WPP_GLOBAL_Control
0x180015b29  cmp     rcx, rax
0x180015b2c  jz      loc_180015BCC
0x180015b32  test    byte ptr [rcx+1Ch], 4
0x180015b36  jz      loc_180015BCC
0x180015b3c  mov     edx, 55h ; 'U'
0x180015b41  jmp     loc_180015AAE
0x180015b46  mov     rcx, [rbp+var_10]
0x180015b4a  lea     rdx, [rbp+arg_0]
0x180015b4e  mov     rax, [rcx]
0x180015b51  mov     rax, [rax+18h]
0x180015b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b5a  mov     ebx, eax
0x180015b5c  test    eax, eax
0x180015b5e  jns     short loc_180015B83
0x180015b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b67  lea     rax, WPP_GLOBAL_Control
0x180015b6e  cmp     rcx, rax
0x180015b71  jz      short loc_180015BCC
0x180015b73  test    byte ptr [rcx+1Ch], 4
0x180015b77  jz      short loc_180015BCC
0x180015b79  mov     edx, 56h ; 'V'
0x180015b7e  jmp     loc_180015AAE
0x180015b83  mov     rcx, [rbp+arg_0]
0x180015b87  lea     rdx, [rbp+pv]
0x180015b8b  mov     rax, [rcx]
0x180015b8e  mov     rax, [rax+48h]
0x180015b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b97  mov     ebx, eax
0x180015b99  test    eax, eax
0x180015b9b  jns     short loc_180015BC0
0x180015b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ba4  lea     rax, WPP_GLOBAL_Control
0x180015bab  cmp     rcx, rax
0x180015bae  jz      short loc_180015BCC
0x180015bb0  test    byte ptr [rcx+1Ch], 4
0x180015bb4  jz      short loc_180015BCC
0x180015bb6  mov     edx, 57h ; 'W'
0x180015bbb  jmp     loc_180015AAE
0x180015bc0  mov     rdx, [rbp+pv]
0x180015bc4  mov     rcx, rdi
0x180015bc7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180015bcc  mov     rcx, [rbp+pv]; pv
0x180015bd0  test    rcx, rcx
0x180015bd3  jz      short loc_180015BE1
0x180015bd5  call    cs:__imp_CoTaskMemFree
0x180015bdc  nop     dword ptr [rax+rax+00h]
0x180015be1  mov     rcx, [rbp+arg_0]
0x180015be5  test    rcx, rcx
0x180015be8  jz      short loc_180015BFE
0x180015bea  mov     rax, [rcx]
0x180015bed  mov     rax, [rax+10h]
0x180015bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bf6  mov     [rbp+arg_0], 0
0x180015bfe  mov     rcx, [rbp+var_10]
0x180015c02  test    rcx, rcx
0x180015c05  jz      short loc_180015C13
0x180015c07  mov     rax, [rcx]
0x180015c0a  mov     rax, [rax+10h]
0x180015c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c13  mov     rdi, [rsp+30h+arg_10]
0x180015c18  mov     eax, ebx
0x180015c1a  mov     rbx, [rsp+30h+arg_8]
0x180015c1f  add     rsp, 30h
0x180015c23  pop     rbp
0x180015c24  retn
```

# RegistryOpenKey(RegistryIsolationKeys const &,ushort const *,HKEY__ * *,int *,ulong)

- ea: `0x18004ed50`
- end: `0x18004ee8a`
- name: `?RegistryOpenKey@@YAJAEBURegistryIsolationKeys@@PEBGPEAPEAUHKEY__@@PEAHK@Z`
- size: `314`
- prototype: `int(const struct RegistryIsolationKeys *, const unsigned __int16 *, HKEY *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180051ae4`
- `0x180051fa0`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18004e2ec`
- `0x18004eb80`
- `0x18004ed50`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ede6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ee11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ede6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ee11`

## string_xrefs

- `0x18004ee47`: `onecoreuap\internal\net\inc\phone\RegistryIsolationUtil.h`

## pseudocode

```c
__int64 __fastcall RegistryOpenKey(
        const struct RegistryIsolationKeys *a1,
        const unsigned __int16 *a2,
        HKEY *a3,
        int *a4,
        REGSAM samDesired)
{
  __int128 v5; // xmm0
  __int64 v7; // r10
  int NewRegistryPath; // eax
  unsigned int v9; // ebx
  int v10; // ecx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LPCWSTR v14[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v15; // [rsp+40h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h]

  v5 = 0;
  *a3 = 0;
  *(_OWORD *)lpSubKey = 0;
  v17 = 0;
  *(double *)&v5 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  *(_OWORD *)v14 = v5;
  v15 = v5;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v14);
  NewRegistryPath = RegistryIsolationUtil::GetNewRegistryPath(&c_MessagingSettingsRegKeys, v7, lpSubKey, v14);
  v9 = NewRegistryPath;
  if ( NewRegistryPath >= 0 )
  {
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, samDesired, a3);
    v9 = v11;
    if ( v11 )
    {
      if ( v14[0] == v14[1] )
      {
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_11;
      }
      v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v14[0], 0, samDesired & 0xFFFFFFF9, a3);
      v9 = v12;
      if ( v12 )
      {
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
LABEL_11:
        v10 = v9;
        goto LABEL_12;
      }
    }
    v9 = 0;
    goto LABEL_14;
  }
  v10 = NewRegistryPath;
LABEL_12:
  Log_HREvent_27(v10);
LABEL_14:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v14);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
  return v9;
}

```

## disassembly

```asm
0x18004ed50  mov     [rsp-18h+arg_0], rbx
0x18004ed55  push    rbp
0x18004ed56  push    rsi
0x18004ed57  push    rdi
0x18004ed58  mov     rbp, rsp
0x18004ed5b  sub     rsp, 80h
0x18004ed62  mov     rax, cs:__security_cookie
0x18004ed69  xor     rax, rsp
0x18004ed6c  mov     [rbp+var_10], rax
0x18004ed70  xorps   xmm0, xmm0
0x18004ed73  mov     qword ptr [r8], 0
0x18004ed7a  lea     rcx, [rbp+lpSubKey]
0x18004ed7e  mov     rsi, r8
0x18004ed81  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x18004ed85  mov     r10, rdx
0x18004ed88  movups  [rbp+var_20], xmm0
0x18004ed8c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004ed91  lea     rcx, [rbp+var_50]
0x18004ed95  movups  xmmword ptr [rbp+var_50], xmm0
0x18004ed99  movups  [rbp+var_40], xmm0
0x18004ed9d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18004eda2  mov     rdx, r10
0x18004eda5  lea     r9, [rbp+var_50]
0x18004eda9  lea     r8, [rbp+lpSubKey]
0x18004edad  lea     rcx, ?c_MessagingSettingsRegKeys@@3URegistryIsolationKeys@@B; RegistryIsolationKeys const c_MessagingSettingsRegKeys
0x18004edb4  call    ?GetNewRegistryPath@RegistryIsolationUtil@@YAJAEBURegistryIsolationKeys@@PEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@2@Z; RegistryIsolationUtil::GetNewRegistryPath(RegistryIsolationKeys const &,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18004edb9  mov     ebx, eax
0x18004edbb  test    eax, eax
0x18004edbd  jns     short loc_18004EDCD
0x18004edbf  mov     r9d, 6Dh ; 'm'
0x18004edc5  mov     ecx, eax
0x18004edc7  lea     edx, [r9-6Ch]
0x18004edcb  jmp     short loc_18004EE47
0x18004edcd  mov     edi, [rbp+samDesired]
0x18004edd0  xor     r8d, r8d; ulOptions
0x18004edd3  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18004edd7  mov     r9d, edi; samDesired
0x18004edda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ede1  mov     [rsp+80h+phkResult], rsi; phkResult
0x18004ede6  call    cs:__imp_RegOpenKeyExW
0x18004edec  mov     ebx, eax
0x18004edee  test    eax, eax
0x18004edf0  jz      short loc_18004EE55
0x18004edf2  mov     rdx, [rbp+var_50]; lpSubKey
0x18004edf6  cmp     rdx, [rbp+var_50+8]
0x18004edfa  jz      short loc_18004EE30
0x18004edfc  and     edi, 0FFFFFFF9h
0x18004edff  mov     [rsp+80h+phkResult], rsi; phkResult
0x18004ee04  mov     r9d, edi; samDesired
0x18004ee07  xor     r8d, r8d; ulOptions
0x18004ee0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ee11  call    cs:__imp_RegOpenKeyExW
0x18004ee17  mov     ebx, eax
0x18004ee19  test    eax, eax
0x18004ee1b  jz      short loc_18004EE55
0x18004ee1d  jle     short loc_18004EE28
0x18004ee1f  movzx   ebx, ax
0x18004ee22  or      ebx, 80070000h
0x18004ee28  mov     r9d, 7Ah ; 'z'
0x18004ee2e  jmp     short loc_18004EE43
0x18004ee30  test    eax, eax
0x18004ee32  jle     short loc_18004EE3D
0x18004ee34  movzx   ebx, ax
0x18004ee37  or      ebx, 80070000h
0x18004ee3d  mov     r9d, 73h ; 's'
0x18004ee43  xor     edx, edx
0x18004ee45  mov     ecx, ebx; int
0x18004ee47  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18004ee4e  call    Log_HREvent_27
0x18004ee53  jmp     short loc_18004EE57
0x18004ee55  xor     ebx, ebx
0x18004ee57  lea     rcx, [rbp+var_50]
0x18004ee5b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ee60  lea     rcx, [rbp+lpSubKey]
0x18004ee64  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ee69  mov     eax, ebx
0x18004ee6b  mov     rcx, [rbp+var_10]
0x18004ee6f  xor     rcx, rsp; StackCookie
0x18004ee72  call    __security_check_cookie
0x18004ee77  mov     rbx, [rsp+80h+arg_0]
0x18004ee7f  add     rsp, 80h
0x18004ee86  pop     rdi
0x18004ee87  pop     rsi
0x18004ee88  pop     rbp
0x18004ee89  retn
```

# CompareAndSaveAttributeValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ushort const *,ushort const *,int *)

- ea: `0x18003b9a0`
- end: `0x18003bb0b`
- name: `?CompareAndSaveAttributeValue@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG1PEAH@Z`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003bb14`

## callees

- `0x18000cd34`
- `0x18000e410`
- `0x18001a42c`
- `0x1800248b4`
- `0x18003b9a0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003badb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003badb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ba40`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ba40`
- `SHLWAPI!StrCmpIW` at `0x18003ba88`
- `SHLWAPI!StrCmpIW` at `0x18003ba88`

## string_xrefs

- `0x18003ba00`: `Attribute %s not found in registry, saving it`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompareAndSaveAttributeValue(HKEY *a1, const WCHAR *a2, _WORD *a3, _DWORD *a4)
{
  HKEY v8; // rbx
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // ebx
  DWORD cbData; // eax
  __int64 v13; // rax
  LSTATUS v14; // eax
  __int64 v15; // rax
  int v16; // eax
  wil::reg::reg_view_details *lpData; // [rsp+20h] [rbp-58h]
  int lpDataa; // [rsp+20h] [rbp-58h]
  HKEY v20; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  PCWSTR psz1; // [rsp+80h] [rbp+8h] BYREF

  psz1 = 0;
  v8 = *a1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psz1,
    0);
  v20 = v8;
  LODWORD(lpData) = 268435462;
  v10 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
          &v20,
          v9,
          a2,
          (PVOID *)&psz1,
          lpData);
  v11 = v10;
  if ( v10 == -2147024894 )
  {
    *a4 = 0;
    SBServicingLogMessage((wchar_t *)L"Attribute %s not found in registry, saving it", a2);
    if ( a3 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a3[v13] );
      cbData = 2 * v13 + 2;
    }
    else
    {
      cbData = 0;
    }
    v14 = RegSetKeyValueW(*a1, 0, a2, 1u, a3, cbData);
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
  }
  else if ( v10 >= 0 )
  {
    if ( StrCmpIW(psz1, a3) )
    {
      *a4 = 0;
      SBServicingLogMessage(
        (wchar_t *)L"Attribute %s has changed prevAttribute: %ls new Value:%ls, saving it",
        a2,
        psz1,
        a3);
      v15 = -1;
      do
        ++v15;
      while ( a3[v15] );
      v16 = RegSetValueExW(*a1, a2, 0, 1u, (const BYTE *)a3, 2 * v15 + 2);
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v11 = v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsattributes.cpp",
      (const char *)(unsigned int)v10,
      lpDataa);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&psz1);
  return v11;
}

```

## disassembly

```asm
0x18003b9a0  mov     rax, rsp
0x18003b9a3  push    rbx
0x18003b9a4  push    rbp
0x18003b9a5  push    rsi
0x18003b9a6  push    rdi
0x18003b9a7  push    r14
0x18003b9a9  push    r15
0x18003b9ab  sub     rsp, 48h
0x18003b9af  mov     r15, r9
0x18003b9b2  mov     rdi, r8
0x18003b9b5  mov     rsi, rdx
0x18003b9b8  mov     r14, rcx
0x18003b9bb  xor     ebp, ebp
0x18003b9bd  mov     [rax+8], rbp
0x18003b9c1  mov     rbx, [rcx]
0x18003b9c4  xor     edx, edx
0x18003b9c6  lea     rcx, [rax+8]
0x18003b9ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b9cf  mov     [rsp+78h+var_48], rbx
0x18003b9d4  mov     dword ptr [rsp+78h+lpData], 10000006h; int
0x18003b9dc  lea     r9, [rsp+78h+psz1]
0x18003b9e4  mov     r8, rsi
0x18003b9e7  lea     rcx, [rsp+78h+var_48]
0x18003b9ec  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003b9f1  mov     ebx, eax
0x18003b9f3  cmp     eax, 80070002h
0x18003b9f8  jnz     short loc_18003BA5E
0x18003b9fa  mov     [r15], ebp
0x18003b9fd  mov     rdx, rsi
0x18003ba00  lea     rcx, aAttributeSNotF; "Attribute %s not found in registry, sav"...
0x18003ba07  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003ba0c  test    rdi, rdi
0x18003ba0f  jnz     short loc_18003BA15
0x18003ba11  mov     eax, ebp
0x18003ba13  jmp     short loc_18003BA29
0x18003ba15  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ba19  inc     rax
0x18003ba1c  cmp     [rdi+rax*2], bp
0x18003ba20  jnz     short loc_18003BA19
0x18003ba22  lea     eax, ds:2[rax*2]
0x18003ba29  mov     [rsp+78h+cbData], eax; cbData
0x18003ba2d  mov     [rsp+78h+lpData], rdi; lpData
0x18003ba32  mov     r9d, 1; dwType
0x18003ba38  mov     r8, rsi; lpValueName
0x18003ba3b  xor     edx, edx; lpSubKey
0x18003ba3d  mov     rcx, [r14]; hKey
0x18003ba40  call    cs:__imp_RegSetKeyValueW
0x18003ba46  mov     ebx, eax
0x18003ba48  test    eax, eax
0x18003ba4a  jle     loc_18003BAEF
0x18003ba50  movzx   ebx, ax
0x18003ba53  or      ebx, 80070000h
0x18003ba59  jmp     loc_18003BAEF
0x18003ba5e  test    eax, eax
0x18003ba60  jns     short loc_18003BA7D
0x18003ba62  mov     rcx, [rsp+78h]; this
0x18003ba67  mov     r9d, eax; char *
0x18003ba6a  lea     r8, aOnecoreBaseSec_5; "onecore\\base\\secureboot\\servicing\\l"...
0x18003ba71  mov     edx, 84h; void *
0x18003ba76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba7b  jmp     short loc_18003BAEF
0x18003ba7d  mov     rdx, rdi; psz2
0x18003ba80  mov     rcx, [rsp+78h+psz1]; psz1
0x18003ba88  call    cs:__imp_StrCmpIW
0x18003ba8e  test    eax, eax
0x18003ba90  jz      short loc_18003BAEF
0x18003ba92  mov     [r15], ebp
0x18003ba95  mov     r9, rdi
0x18003ba98  mov     r8, [rsp+78h+psz1]
0x18003baa0  mov     rdx, rsi
0x18003baa3  lea     rcx, aAttributeSHasC; "Attribute %s has changed prevAttribute:"...
0x18003baaa  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003baaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003bab3  inc     rax
0x18003bab6  cmp     [rdi+rax*2], bp
0x18003baba  jnz     short loc_18003BAB3
0x18003babc  lea     eax, ds:2[rax*2]
0x18003bac3  mov     [rsp+78h+cbData], eax; cbData
0x18003bac7  mov     [rsp+78h+lpData], rdi; lpData
0x18003bacc  mov     r9d, 1; dwType
0x18003bad2  xor     r8d, r8d; Reserved
0x18003bad5  mov     rdx, rsi; lpValueName
0x18003bad8  mov     rcx, [r14]; hKey
0x18003badb  call    cs:__imp_RegSetValueExW
0x18003bae1  test    eax, eax
0x18003bae3  jle     short loc_18003BAED
0x18003bae5  movzx   eax, ax
0x18003bae8  or      eax, 80070000h
0x18003baed  mov     ebx, eax
0x18003baef  lea     rcx, [rsp+78h+psz1]
0x18003baf7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003bafc  mov     eax, ebx
0x18003bafe  add     rsp, 48h
0x18003bb02  pop     r15
0x18003bb04  pop     r14
0x18003bb06  pop     rdi
0x18003bb07  pop     rsi
0x18003bb08  pop     rbp
0x18003bb09  pop     rbx
0x18003bb0a  retn
```

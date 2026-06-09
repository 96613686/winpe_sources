# EnterpriseFeatureControl::GetPersistedRegistryLocation(ushort const *,ushort const *,ushort * *)

- ea: `0x1800649d0`
- end: `0x180064b11`
- name: `?GetPersistedRegistryLocation@EnterpriseFeatureControl@@CAJPEBG0PEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180068140`

## callees

- `0x1800077c8`
- `0x18002edcc`
- `0x18005fcdc`
- `0x180060300`
- `0x1800649d0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180064a34`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180064ac5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180064a34`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180064ac5`

## string_xrefs

- `0x180064a26`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180064aab`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180064a2d`: `WindowsUpdate`
- `0x180064abe`: `WindowsUpdate`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetPersistedRegistryLocation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int PersistedRegistryLocationW; // eax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rbx
  unsigned int v9; // eax
  const unsigned __int16 **v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v13; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = a2;
  v13 = a1;
  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 87;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v4,
      (int)v11);
    return v4;
  }
  LODWORD(v14) = 0;
  v11 = &v14;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdate",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate",
                                 0,
                                 0);
  v4 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v4 = -2147418113;
    v5 = 93;
    goto LABEL_3;
  }
  if ( PersistedRegistryLocationW == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v13,
      v7,
      (unsigned int)v14);
    v8 = (unsigned __int16 *)v13;
    if ( v13 )
    {
      v9 = GetPersistedRegistryLocationW(
             L"WindowsUpdate",
             L"SOFTWARE\\Microsoft\\WindowsUpdate",
             v13,
             (unsigned int)v14);
      if ( v9 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x63,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               (const char *)v9,
               0);
      }
      else
      {
        *a3 = v8;
        v4 = 0;
        v13 = 0;
      }
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)0x8007000ELL,
        (int)&v14);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v4 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      v5 = 94;
      goto LABEL_3;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800649d0  mov     [rsp+arg_10], rbx
0x1800649d5  mov     [rsp+arg_8], rdx
0x1800649da  mov     [rsp+arg_0], rcx
0x1800649df  push    rdi
0x1800649e0  sub     rsp, 30h
0x1800649e4  mov     rdi, r8
0x1800649e7  test    r8, r8
0x1800649ea  jnz     short loc_180064A0E
0x1800649ec  mov     ebx, 80004003h
0x1800649f1  lea     edx, [r8+57h]; void *
0x1800649f5  mov     rcx, [rsp+38h]; this
0x1800649fa  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180064a01  mov     r9d, ebx; char *
0x180064a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a09  jmp     loc_180064B04
0x180064a0e  lea     rax, [rsp+38h+arg_8]
0x180064a13  mov     dword ptr [rsp+38h+arg_8], 0
0x180064a1b  xor     r9d, r9d
0x180064a1e  mov     qword ptr [rsp+38h+var_18], rax; int
0x180064a23  xor     r8d, r8d
0x180064a26  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180064a2d  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180064a34  call    cs:__imp_GetPersistedRegistryLocationW
0x180064a3a  mov     ebx, eax
0x180064a3c  test    eax, eax
0x180064a3e  jnz     short loc_180064A4A
0x180064a40  mov     ebx, 8000FFFFh
0x180064a45  lea     edx, [rax+5Dh]
0x180064a48  jmp     short loc_1800649F5
0x180064a4a  cmp     eax, 0EAh
0x180064a4f  jz      short loc_180064A6D
0x180064a51  test    eax, eax
0x180064a53  jle     short loc_180064A5E
0x180064a55  movzx   ebx, ax
0x180064a58  or      ebx, 80070000h
0x180064a5e  test    ebx, ebx
0x180064a60  jns     loc_180064B04
0x180064a66  mov     edx, 5Eh ; '^'
0x180064a6b  jmp     short loc_1800649F5
0x180064a6d  mov     r8d, dword ptr [rsp+38h+arg_8]
0x180064a72  lea     rcx, [rsp+38h+arg_0]
0x180064a77  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180064a7c  mov     rbx, [rsp+38h+arg_0]
0x180064a81  test    rbx, rbx
0x180064a84  jnz     short loc_180064AA6
0x180064a86  mov     rcx, [rsp+38h]; this
0x180064a8b  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180064a92  mov     ebx, 8007000Eh
0x180064a97  mov     edx, 61h ; 'a'; void *
0x180064a9c  mov     r9d, ebx; char *
0x180064a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064aa4  jmp     short loc_180064AFA
0x180064aa6  mov     r9d, dword ptr [rsp+38h+arg_8]
0x180064aab  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180064ab2  mov     r8, rbx
0x180064ab5  mov     qword ptr [rsp+38h+var_18], 0; unsigned int
0x180064abe  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180064ac5  call    cs:__imp_GetPersistedRegistryLocationW
0x180064acb  test    eax, eax
0x180064acd  jz      short loc_180064AEC
0x180064acf  mov     rcx, [rsp+38h]; this
0x180064ad4  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180064adb  mov     r9d, eax; char *
0x180064ade  mov     edx, 63h ; 'c'; void *
0x180064ae3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180064ae8  mov     ebx, eax
0x180064aea  jmp     short loc_180064AFA
0x180064aec  mov     [rdi], rbx
0x180064aef  xor     ebx, ebx
0x180064af1  mov     [rsp+38h+arg_0], 0
0x180064afa  lea     rcx, [rsp+38h+arg_0]
0x180064aff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064b04  mov     eax, ebx
0x180064b06  mov     rbx, [rsp+38h+arg_10]
0x180064b0b  add     rsp, 30h
0x180064b0f  pop     rdi
0x180064b10  retn
```

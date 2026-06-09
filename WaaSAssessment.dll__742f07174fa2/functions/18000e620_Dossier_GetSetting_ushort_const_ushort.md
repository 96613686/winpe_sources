# Dossier::GetSetting(ushort const *,ushort * *)

- ea: `0x18000e620`
- end: `0x18000e74f`
- name: `?GetSetting@Dossier@@UEAAJPEBGPEAPEAG@Z`
- size: `303`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006e28`
- `0x18000d690`
- `0x18000e620`
- `0x18000efec`
- `0x180012e08`
- `0x18001592c`
- `0x18001752c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e710`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e739`

## pseudocode

```c
__int64 __fastcall Dossier::GetSetting(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  bool v3; // zf
  int CachedSetting; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 **v10; // rdi
  int v11; // eax
  int SettingValue; // eax
  void *v14; // rbx
  unsigned int v15; // edi
  unsigned __int16 *v16; // rdi
  int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v19; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 5) == 0;
  LODWORD(v19) = 0;
  pv = 0;
  if ( !v3 )
  {
    CachedSetting = Dossier::GetCachedSetting(this, a2, a3);
    v7 = CachedSetting;
    if ( CachedSetting >= 0 )
    {
      v7 = 0;
LABEL_10:
      CoTaskMemFree(0);
      return v7;
    }
    v8 = (unsigned int)CachedSetting;
    v9 = 73;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)v8,
      v17);
    goto LABEL_10;
  }
  v10 = (__int64 **)((char *)this + 8);
  v11 = WOSCOneSettings::SettingValueExists((Dossier *)((char *)this + 8), a2, (int *)&v19);
  v7 = v11;
  if ( v11 < 0 )
  {
    v8 = (unsigned int)v11;
    v9 = 78;
    goto LABEL_9;
  }
  if ( !(_DWORD)v19 )
  {
    v7 = -2147024894;
    v9 = 80;
    v8 = 2147942402LL;
    goto LABEL_9;
  }
  SettingValue = WOSCOneSettings::GetSettingValue(v10, a2, (struct CSpDynamicString *)&pv);
  v14 = pv;
  v15 = SettingValue;
  if ( SettingValue >= 0 )
  {
    if ( pv )
    {
      v19 = 0;
      CSpDynamicString::operator=(&v19, pv);
      v16 = v19;
      CoTaskMemFree(0);
    }
    else
    {
      v16 = 0;
    }
    *a3 = v16;
    LogLevel(4u, L"Setting Name:%s Value:%s", a2, a3);
    v15 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)SettingValue,
      v17);
  }
  CoTaskMemFree(v14);
  return v15;
}

```

## disassembly

```asm
0x18000e620  mov     [rsp+arg_8], rbx
0x18000e625  push    rsi
0x18000e626  push    rdi
0x18000e627  push    r14; int
0x18000e629  sub     rsp, 20h
0x18000e62d  cmp     dword ptr [rcx+14h], 0
0x18000e631  mov     r14, r8
0x18000e634  mov     rsi, rdx
0x18000e637  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e63f  mov     [rsp+38h+pv], 0
0x18000e648  jz      short loc_18000E663
0x18000e64a  call    ?GetCachedSetting@Dossier@@EEAAJPEBGPEAPEAG@Z; Dossier::GetCachedSetting(ushort const *,ushort * *)
0x18000e64f  mov     ebx, eax
0x18000e651  test    eax, eax
0x18000e653  jns     short loc_18000E65F
0x18000e655  mov     r9d, eax
0x18000e658  mov     edx, 49h ; 'I'; unsigned __int16 *
0x18000e65d  jmp     short loc_18000E698
0x18000e65f  xor     ebx, ebx
0x18000e661  jmp     short loc_18000E6A9
0x18000e663  lea     rdi, [rcx+8]
0x18000e667  mov     rcx, rdi; this
0x18000e66a  lea     r8, [rsp+38h+arg_0]; int *
0x18000e66f  call    ?SettingValueExists@WOSCOneSettings@@QEAAJPEBGPEAH@Z; WOSCOneSettings::SettingValueExists(ushort const *,int *)
0x18000e674  mov     ebx, eax
0x18000e676  test    eax, eax
0x18000e678  jns     short loc_18000E684
0x18000e67a  mov     r9d, eax
0x18000e67d  mov     edx, 4Eh ; 'N'
0x18000e682  jmp     short loc_18000E698
0x18000e684  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e689  jnz     short loc_18000E6B8
0x18000e68b  mov     ebx, 80070002h
0x18000e690  mov     edx, 50h ; 'P'; void *
0x18000e695  mov     r9d, ebx; char *
0x18000e698  mov     rcx, [rsp+38h]; this
0x18000e69d  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e6a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6a9  xor     ecx, ecx; pv
0x18000e6ab  call    cs:__imp_CoTaskMemFree
0x18000e6b1  mov     eax, ebx
0x18000e6b3  jmp     loc_18000E741
0x18000e6b8  lea     r8, [rsp+38h+pv]; struct CSpDynamicString *
0x18000e6bd  mov     rdx, rsi; unsigned __int16 *
0x18000e6c0  mov     rcx, rdi; this
0x18000e6c3  call    ?GetSettingValue@WOSCOneSettings@@QEAAJPEBGAEAVCSpDynamicString@@@Z; WOSCOneSettings::GetSettingValue(ushort const *,CSpDynamicString &)
0x18000e6c8  mov     rbx, [rsp+38h+pv]
0x18000e6cd  mov     edi, eax
0x18000e6cf  test    eax, eax
0x18000e6d1  jns     short loc_18000E6EE
0x18000e6d3  mov     rcx, [rsp+38h]; this
0x18000e6d8  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000e6df  mov     r9d, eax; char *
0x18000e6e2  mov     edx, 53h ; 'S'; void *
0x18000e6e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6ec  jmp     short loc_18000E736
0x18000e6ee  test    rbx, rbx
0x18000e6f1  jz      short loc_18000E718
0x18000e6f3  mov     rdx, rbx
0x18000e6f6  mov     [rsp+38h+arg_0], 0
0x18000e6ff  lea     rcx, [rsp+38h+arg_0]
0x18000e704  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18000e709  mov     rdi, [rsp+38h+arg_0]
0x18000e70e  xor     ecx, ecx; pv
0x18000e710  call    cs:__imp_CoTaskMemFree
0x18000e716  jmp     short loc_18000E71A
0x18000e718  xor     edi, edi
0x18000e71a  mov     r9, r14
0x18000e71d  mov     [r14], rdi
0x18000e720  mov     r8, rsi
0x18000e723  lea     rdx, aSettingNameSVa; "Setting Name:%s Value:%s"
0x18000e72a  mov     ecx, 4; unsigned __int8
0x18000e72f  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000e734  xor     edi, edi
0x18000e736  mov     rcx, rbx; pv
0x18000e739  call    cs:__imp_CoTaskMemFree
0x18000e73f  mov     eax, edi
0x18000e741  mov     rbx, [rsp+38h+arg_8]
0x18000e746  add     rsp, 20h
0x18000e74a  pop     r14
0x18000e74c  pop     rdi
0x18000e74d  pop     rsi
0x18000e74e  retn
```

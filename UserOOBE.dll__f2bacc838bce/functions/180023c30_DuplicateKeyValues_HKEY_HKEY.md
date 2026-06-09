# DuplicateKeyValues(HKEY__ *,HKEY__ *)

- ea: `0x180023c30`
- end: `0x180023e2f`
- name: `?DuplicateKeyValues@@YAJPEAUHKEY__@@0@Z`
- size: `511`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800233ec`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000e580`
- `0x18001f6c4`
- `0x180022a38`
- `0x180023c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d21`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023ca5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023ca5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180023d72`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180023d72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023d9d`

## string_xrefs

- `0x180023cb6`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x180023d01`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x180023dba`: `shell\OOBE\common\inc\CopyRegTree.h`
- `0x180023df1`: `shell\OOBE\common\inc\CopyRegTree.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall DuplicateKeyValues(HKEY hKey, HKEY a2)
{
  unsigned int v4; // eax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  BYTE *lpData; // rbx
  DWORD i; // edi
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int lpReserved; // [rsp+20h] [rbp-60h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-60h]
  DWORD cbData; // [rsp+60h] [rbp-20h] BYREF
  DWORD Type; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-18h] BYREF
  LPWSTR lpValueName; // [rsp+70h] [rbp-10h] BYREF
  BYTE *v19; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD v21; // [rsp+B0h] [rbp+30h] BYREF
  SIZE_T cb; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  LODWORD(cb) = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &v21, (LPDWORD)&cb, 0, 0);
  if ( v4 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xC,
             (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
             (const char *)v4,
             lpReserved);
  ++v21;
  lpValueName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpValueName,
    0);
  v7 = _AllocArray<unsigned short,CTCoAllocPolicy>(v6, 1, v21, &lpValueName);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
      (const char *)(unsigned int)v7,
      lpReserved);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpValueName);
    return v8;
  }
  Type = 0;
  lpData = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
  v19 = lpData;
  if ( !lpData )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
      (const char *)0x8007000ELL,
      lpReserved);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
    goto LABEL_17;
  }
  for ( i = 0; ; ++i )
  {
    cbData = cb;
    cchValueName = v21;
    v11 = RegEnumValueW(hKey, i, lpValueName, &cchValueName, 0, &Type, lpData, &cbData);
    if ( v11 == 259 )
      break;
    if ( v11 )
    {
      v12 = 30;
      goto LABEL_13;
    }
    v11 = RegSetValueExW(a2, lpValueName, 0, Type, lpData, cbData);
    if ( v11 )
    {
      v12 = 31;
LABEL_13:
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"shell\\OOBE\\common\\inc\\CopyRegTree.h",
             (const char *)v11,
             lpReserveda);
      goto LABEL_16;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpValueName);
  return 0;
}

```

## disassembly

```asm
0x180023c30  mov     r11, rsp
0x180023c33  mov     [r11+8], rbx
0x180023c37  mov     [r11+10h], rsi
0x180023c3b  push    rbp
0x180023c3c  push    rdi
0x180023c3d  push    r14
0x180023c3f  mov     rbp, rsp
0x180023c42  sub     rsp, 80h
0x180023c49  mov     r14, rdx
0x180023c4c  mov     rsi, rcx
0x180023c4f  mov     [rbp+arg_10], 0
0x180023c56  mov     dword ptr [rbp+cb], 0
0x180023c5d  mov     qword ptr [r11-40h], 0
0x180023c65  mov     qword ptr [r11-48h], 0
0x180023c6d  lea     rax, [rbp+cb]
0x180023c71  mov     [r11-50h], rax
0x180023c75  lea     rax, [rbp+arg_10]
0x180023c79  mov     [r11-58h], rax
0x180023c7d  mov     qword ptr [r11-60h], 0
0x180023c85  mov     qword ptr [r11-68h], 0
0x180023c8d  mov     qword ptr [r11-70h], 0
0x180023c95  mov     qword ptr [r11-78h], 0
0x180023c9d  xor     r9d, r9d; lpReserved
0x180023ca0  xor     r8d, r8d; lpcchClass
0x180023ca3  xor     edx, edx; lpClass
0x180023ca5  call    cs:__imp_RegQueryInfoKeyW
0x180023cab  test    eax, eax
0x180023cad  jz      short loc_180023CCC
0x180023caf  mov     rcx, [rbp+18h]; this
0x180023cb3  mov     r9d, eax; char *
0x180023cb6  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023cbd  mov     edx, 0Ch; void *
0x180023cc2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023cc7  jmp     loc_180023E17
0x180023ccc  inc     [rbp+arg_10]
0x180023ccf  mov     [rbp+lpValueName], 0
0x180023cd7  xor     edx, edx
0x180023cd9  lea     rcx, [rbp+lpValueName]
0x180023cdd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023ce2  mov     r8d, [rbp+arg_10]
0x180023ce6  lea     r9, [rbp+lpValueName]
0x180023cea  mov     edx, 1
0x180023cef  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180023cf4  mov     ebx, eax
0x180023cf6  test    eax, eax
0x180023cf8  jns     short loc_180023D17
0x180023cfa  mov     rcx, [rbp+18h]; this
0x180023cfe  mov     r9d, eax; char *
0x180023d01  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023d08  mov     edx, 11h; void *
0x180023d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d12  jmp     loc_180023E0C
0x180023d17  mov     [rbp+Type], 0
0x180023d1e  mov     ecx, dword ptr [rbp+cb]; cb
0x180023d21  call    cs:__imp_CoTaskMemAlloc
0x180023d27  mov     rbx, rax
0x180023d2a  mov     [rbp+var_8], rax
0x180023d2e  test    rax, rax
0x180023d31  jz      loc_180023DE5
0x180023d37  xor     edi, edi
0x180023d39  mov     eax, dword ptr [rbp+cb]
0x180023d3c  mov     [rbp+cbData], eax
0x180023d3f  mov     eax, [rbp+arg_10]
0x180023d42  mov     [rbp+cchValueName], eax
0x180023d45  lea     rax, [rbp+cbData]
0x180023d49  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180023d4e  mov     [rsp+80h+lpData], rbx; lpData
0x180023d53  lea     rax, [rbp+Type]
0x180023d57  mov     [rsp+80h+lpType], rax; lpType
0x180023d5c  mov     [rsp+80h+lpReserved], 0; unsigned int
0x180023d65  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180023d69  mov     r8, [rbp+lpValueName]; lpValueName
0x180023d6d  mov     edx, edi; dwIndex
0x180023d6f  mov     rcx, rsi; hKey
0x180023d72  call    cs:__imp_RegEnumValueW
0x180023d78  cmp     eax, 103h
0x180023d7d  jz      short loc_180023DCE
0x180023d7f  test    eax, eax
0x180023d81  jnz     short loc_180023DB2
0x180023d83  mov     eax, [rbp+cbData]
0x180023d86  mov     dword ptr [rsp+80h+lpType], eax; cbData
0x180023d8a  mov     [rsp+80h+lpReserved], rbx; lpData
0x180023d8f  mov     r9d, [rbp+Type]; dwType
0x180023d93  xor     r8d, r8d; Reserved
0x180023d96  mov     rdx, [rbp+lpValueName]; lpValueName
0x180023d9a  mov     rcx, r14; hKey
0x180023d9d  call    cs:__imp_RegSetValueExW
0x180023da3  test    eax, eax
0x180023da5  jnz     short loc_180023DAB
0x180023da7  inc     edi
0x180023da9  jmp     short loc_180023D39
0x180023dab  mov     edx, 1Fh
0x180023db0  jmp     short loc_180023DB7
0x180023db2  mov     edx, 1Eh; void *
0x180023db7  mov     r9d, eax; char *
0x180023dba  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023dc1  mov     rcx, [rbp+18h]; this
0x180023dc5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023dca  mov     ebx, eax
0x180023dcc  jmp     short loc_180023E02
0x180023dce  lea     rcx, [rbp+var_8]
0x180023dd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023dd7  nop
0x180023dd8  lea     rcx, [rbp+lpValueName]
0x180023ddc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023de1  xor     eax, eax
0x180023de3  jmp     short loc_180023E17
0x180023de5  mov     rcx, [rbp+18h]; this
0x180023de9  mov     ebx, 8007000Eh
0x180023dee  mov     r9d, ebx; char *
0x180023df1  lea     r8, aShellOobeCommo_0; "shell\\OOBE\\common\\inc\\CopyRegTree.h"
0x180023df8  mov     edx, 14h; void *
0x180023dfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e02  lea     rcx, [rbp+var_8]
0x180023e06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023e0b  nop
0x180023e0c  lea     rcx, [rbp+lpValueName]
0x180023e10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023e15  mov     eax, ebx
0x180023e17  lea     r11, [rsp+80h+var_s0]
0x180023e1f  mov     rbx, [r11+20h]
0x180023e23  mov     rsi, [r11+28h]
0x180023e27  mov     rsp, r11
0x180023e2a  pop     r14
0x180023e2c  pop     rdi
0x180023e2d  pop     rbp
0x180023e2e  retn
```

# QueryStorageRegSetting(ushort const *,ushort const *,ulong,void *)

- ea: `0x180050184`
- end: `0x18005029d`
- name: `?QueryStorageRegSetting@@YAJPEBG0KPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, int, BYTE *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004f390`
- `0x18004fb74`
- `0x18004fc68`
- `0x18004fdf8`
- `0x180053d68`

## callees

- `0x180012734`
- `0x180019db4`
- `0x180050184`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800501ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050265`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800501ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050265`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800501bf`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800501bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall QueryStorageRegSetting(LPCWSTR lpSubKey, LPCWSTR lpValueName, int a3, BYTE *a4)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  __int64 v9; // rdx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  int lpData; // [rsp+20h] [rbp-20h]
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+34h] [rbp-Ch] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  Type = 0;
  cbData = 0;
  phkResult = 0;
  v7 = RegOpenKeyW(HKEY_LOCAL_MACHINE, lpSubKey, &phkResult);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v10 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, 0, &cbData);
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v8 >= 0 )
    {
      if ( Type == 1 || cbData == a3 )
      {
        v11 = RegQueryValueExW(phkResult, lpValueName, 0, &Type, a4, &cbData);
        v8 = v11;
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        if ( v8 >= 0 )
        {
          v8 = 0;
          goto LABEL_18;
        }
        v9 = 23;
      }
      else
      {
        v8 = -2147024809;
        v9 = 21;
      }
    }
    else
    {
      v9 = 19;
    }
  }
  else
  {
    v9 = 17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\inc\\RegUtils.h",
    (const char *)(unsigned int)v8,
    lpData);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180050184  push    rbp
0x180050186  push    rbx
0x180050187  push    rsi
0x180050188  push    rdi
0x180050189  push    r14
0x18005018b  mov     rbp, rsp
0x18005018e  sub     rsp, 40h
0x180050192  mov     r14, r9
0x180050195  mov     esi, r8d
0x180050198  mov     rdi, rdx
0x18005019b  mov     [rbp+Type], 0
0x1800501a2  mov     [rbp+cbData], 0
0x1800501a9  mov     [rbp+phkResult], 0
0x1800501b1  lea     r8, [rbp+phkResult]; phkResult
0x1800501b5  mov     rdx, rcx; lpSubKey
0x1800501b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800501bf  call    cs:__imp_RegOpenKeyW
0x1800501c5  mov     ebx, eax
0x1800501c7  test    eax, eax
0x1800501c9  jle     short loc_1800501D4
0x1800501cb  movzx   ebx, ax
0x1800501ce  or      ebx, 80070000h
0x1800501d4  test    ebx, ebx
0x1800501d6  jns     short loc_1800501DF
0x1800501d8  mov     edx, 11h
0x1800501dd  jmp     short loc_18005021D
0x1800501df  lea     rax, [rbp+cbData]
0x1800501e3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800501e8  mov     [rsp+40h+lpData], 0; int
0x1800501f1  lea     r9, [rbp+Type]; lpType
0x1800501f5  xor     r8d, r8d; lpReserved
0x1800501f8  mov     rdx, rdi; lpValueName
0x1800501fb  mov     rcx, [rbp+phkResult]; hKey
0x1800501ff  call    cs:__imp_RegQueryValueExW
0x180050205  mov     ebx, eax
0x180050207  test    eax, eax
0x180050209  jle     short loc_180050214
0x18005020b  movzx   ebx, ax
0x18005020e  or      ebx, 80070000h
0x180050214  test    ebx, ebx
0x180050216  jns     short loc_180050232
0x180050218  mov     edx, 13h; void *
0x18005021d  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\inc"...
0x180050224  mov     r9d, ebx; char *
0x180050227  mov     rcx, [rbp+28h]; this
0x18005022b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050230  jmp     short loc_180050287
0x180050232  cmp     [rbp+Type], 1
0x180050236  jz      short loc_180050249
0x180050238  cmp     [rbp+cbData], esi
0x18005023b  jz      short loc_180050249
0x18005023d  mov     ebx, 80070057h
0x180050242  mov     edx, 15h
0x180050247  jmp     short loc_18005021D
0x180050249  lea     rax, [rbp+cbData]
0x18005024d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180050252  mov     [rsp+40h+lpData], r14; lpData
0x180050257  lea     r9, [rbp+Type]; lpType
0x18005025b  xor     r8d, r8d; lpReserved
0x18005025e  mov     rdx, rdi; lpValueName
0x180050261  mov     rcx, [rbp+phkResult]; hKey
0x180050265  call    cs:__imp_RegQueryValueExW
0x18005026b  mov     ebx, eax
0x18005026d  test    eax, eax
0x18005026f  jle     short loc_18005027A
0x180050271  movzx   ebx, ax
0x180050274  or      ebx, 80070000h
0x18005027a  test    ebx, ebx
0x18005027c  jns     short loc_180050285
0x18005027e  mov     edx, 17h
0x180050283  jmp     short loc_18005021D
0x180050285  xor     ebx, ebx
0x180050287  lea     rcx, [rbp+phkResult]
0x18005028b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050290  mov     eax, ebx
0x180050292  add     rsp, 40h
0x180050296  pop     r14
0x180050298  pop     rdi
0x180050299  pop     rsi
0x18005029a  pop     rbx
0x18005029b  pop     rbp
0x18005029c  retn
```

# MitigationRegUtils::GetRegBinary(HKEY__ * const &,ushort const *,ushort const *,void *,ulong)

- ea: `0x180029f90`
- end: `0x18002a073`
- name: `?GetRegBinary@MitigationRegUtils@@CAJAEBQEAUHKEY__@@PEBG1PEAXK@Z`
- size: `227`
- prototype: `static int(HKEY *, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029be8`

## callees

- `0x18001208c`
- `0x180019f10`
- `0x180024550`
- `0x180029f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029fdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029fdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a029`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a029`

## pseudocode

```c
__int64 __fastcall MitigationRegUtils::GetRegBinary(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  LSTATUS v8; // eax
  signed int v9; // ebx
  __int64 v10; // rdx
  LSTATUS ValueW; // eax
  int phkResult; // [rsp+20h] [rbp-58h]
  DWORD pcbData[14]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hkey; // [rsp+80h] [rbp+8h] BYREF

  pcbData[0] = 8;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v8 = RegOpenKeyExW(*a1, a2, 0, 0x20019u, &hkey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, a3, 8u, 0, a4, pcbData);
    v9 = ValueW;
    if ( ValueW > 0 )
      v9 = (unsigned __int16)ValueW | 0x80070000;
    if ( v9 >= 0 )
    {
      v9 = 0;
      goto LABEL_11;
    }
    v10 = 76;
  }
  else
  {
    v10 = 73;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationregutils.cpp",
    (const char *)(unsigned int)v9,
    phkResult);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029f90  mov     rax, rsp
0x180029f93  push    rbx
0x180029f94  push    rbp
0x180029f95  push    rsi
0x180029f96  push    rdi
0x180029f97  sub     rsp, 58h
0x180029f9b  mov     rbx, rdx
0x180029f9e  mov     dword ptr [rax-38h], 8
0x180029fa5  mov     rdi, rcx
0x180029fa8  mov     qword ptr [rax+8], 0
0x180029fb0  xor     edx, edx
0x180029fb2  lea     rcx, [rax+8]
0x180029fb6  mov     rsi, r9
0x180029fb9  mov     rbp, r8
0x180029fbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029fc1  mov     rcx, [rdi]; hKey
0x180029fc4  lea     rax, [rsp+78h+hkey]
0x180029fcc  mov     r9d, 20019h; samDesired
0x180029fd2  mov     [rsp+78h+phkResult], rax; phkResult
0x180029fd7  xor     r8d, r8d; ulOptions
0x180029fda  mov     rdx, rbx; lpSubKey
0x180029fdd  call    cs:__imp_RegOpenKeyExW
0x180029fe3  mov     ebx, eax
0x180029fe5  mov     edi, 80070000h
0x180029fea  test    eax, eax
0x180029fec  jle     short loc_180029FF3
0x180029fee  movzx   ebx, ax
0x180029ff1  or      ebx, edi
0x180029ff3  test    ebx, ebx
0x180029ff5  jns     short loc_180029FFE
0x180029ff7  mov     edx, 49h ; 'I'
0x180029ffc  jmp     short loc_18002A043
0x180029ffe  mov     rcx, [rsp+78h+hkey]; hkey
0x18002a006  lea     rax, [rsp+78h+var_38]
0x18002a00b  mov     [rsp+78h+pcbData], rax; pcbData
0x18002a010  mov     r9d, 8; dwFlags
0x18002a016  mov     [rsp+78h+pvData], rsi; pvData
0x18002a01b  mov     r8, rbp; lpValue
0x18002a01e  xor     edx, edx; lpSubKey
0x18002a020  mov     [rsp+78h+phkResult], 0; int
0x18002a029  call    cs:__imp_RegGetValueW
0x18002a02f  mov     ebx, eax
0x18002a031  test    eax, eax
0x18002a033  jle     short loc_18002A03A
0x18002a035  movzx   ebx, ax
0x18002a038  or      ebx, edi
0x18002a03a  test    ebx, ebx
0x18002a03c  jns     short loc_18002A059
0x18002a03e  mov     edx, 4Ch ; 'L'; void *
0x18002a043  mov     rcx, [rsp+78h]; this
0x18002a048  lea     r8, aOnecoreBaseDia_7; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002a04f  mov     r9d, ebx; char *
0x18002a052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a057  jmp     short loc_18002A05B
0x18002a059  xor     ebx, ebx
0x18002a05b  lea     rcx, [rsp+78h+hkey]
0x18002a063  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a068  mov     eax, ebx
0x18002a06a  add     rsp, 58h
0x18002a06e  pop     rdi
0x18002a06f  pop     rsi
0x18002a070  pop     rbp
0x18002a071  pop     rbx
0x18002a072  retn
```

# SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x14002c320`
- end: `0x14002c3d5`
- name: `?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG11@Z`
- size: `181`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14002c460`

## callees

- `0x14000e030`
- `0x14002172c`
- `0x140022fa8`
- `0x14002c320`
- `0x14002c3dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002c36c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002c36c`

## pseudocode

```c
__int64 __fastcall SpRegUtil::Set(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  unsigned int v5; // eax
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v5 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x113,
           (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
           (const char *)v5,
           dwOptions);
  }
  else
  {
    v8 = SpRegUtil::Set(hKey, v6, a4);
    v7 = v8;
    if ( v8 >= 0 )
      v7 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
        (const char *)(unsigned int)v8,
        dwOptions);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x14002c320  mov     r11, rsp
0x14002c323  mov     [r11+18h], r8
0x14002c327  push    rbx
0x14002c328  sub     rsp, 50h
0x14002c32c  mov     qword ptr [r11-18h], 0
0x14002c334  lea     rax, [r11+18h]
0x14002c338  mov     [r11-20h], rax
0x14002c33c  mov     rbx, r9
0x14002c33f  mov     qword ptr [r11-28h], 0
0x14002c347  xor     r9d, r9d; lpClass
0x14002c34a  mov     [rsp+58h+samDesired], 20006h; samDesired
0x14002c352  xor     r8d, r8d; Reserved
0x14002c355  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002c35c  mov     [rsp+58h+dwOptions], 0; int
0x14002c364  mov     qword ptr [r11+18h], 0
0x14002c36c  call    cs:__imp_RegCreateKeyExW
0x14002c372  test    eax, eax
0x14002c374  jz      short loc_14002C393
0x14002c376  mov     rcx, [rsp+58h]; this
0x14002c37b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x14002c382  mov     r9d, eax; char *
0x14002c385  mov     edx, 113h; void *
0x14002c38a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002c38f  mov     ebx, eax
0x14002c391  jmp     short loc_14002C3C3
0x14002c393  mov     rcx, [rsp+58h+hKey]; hKey
0x14002c398  mov     r8, rbx; unsigned __int16 *
0x14002c39b  call    ?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1@Z; SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *)
0x14002c3a0  mov     ebx, eax
0x14002c3a2  test    eax, eax
0x14002c3a4  jns     short loc_14002C3C1
0x14002c3a6  mov     rcx, [rsp+58h]; this
0x14002c3ab  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x14002c3b2  mov     r9d, eax; char *
0x14002c3b5  mov     edx, 114h; void *
0x14002c3ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c3bf  jmp     short loc_14002C3C3
0x14002c3c1  xor     ebx, ebx
0x14002c3c3  lea     rcx, [rsp+58h+hKey]
0x14002c3c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14002c3cd  mov     eax, ebx
0x14002c3cf  add     rsp, 50h
0x14002c3d3  pop     rbx
0x14002c3d4  retn
```

# ServiceBase::_CheckServiceShutdownAlready(void)

- ea: `0x1800225c8`
- end: `0x1800226a7`
- name: `?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ`
- size: `223`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001fab0`

## callees

- `0x1800202bc`
- `0x1800225c8`
- `0x180023df0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022667`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022640`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022640`

## string_xrefs

- `0x1800225fc`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002267a`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_CheckServiceShutdownAlready(ServiceBase *this)
{
  const WCHAR *v2; // rax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 80LL))(this);
  if ( v2 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, v2, 0, 0x20019u, &hKey);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 != -2147024894 )
    {
      if ( (v3 & 0x80000000) == 0 )
        v3 = -2147023781;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x263,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
          (const char *)v3,
          phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v3;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( ((*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 56LL))(this) & 0x100) == 0 )
    return 0;
  v3 = -2147483635;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x253,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    (const char *)0x8000000DLL,
    phkResult);
  return v3;
}

```

## disassembly

```asm
0x1800225c8  push    rbx
0x1800225ca  sub     rsp, 30h
0x1800225ce  mov     rax, [rcx]
0x1800225d1  mov     rbx, rcx
0x1800225d4  mov     rax, [rax+50h]
0x1800225d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225dd  test    rax, rax
0x1800225e0  jnz     short loc_18002261A
0x1800225e2  mov     rax, [rbx]
0x1800225e5  mov     rcx, rbx
0x1800225e8  mov     rax, [rax+38h]
0x1800225ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225f1  bt      eax, 8
0x1800225f5  jnb     short loc_18002266D
0x1800225f7  mov     rcx, [rsp+38h]; this
0x1800225fc  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180022603  mov     ebx, 8000000Dh
0x180022608  mov     edx, 253h; void *
0x18002260d  mov     r9d, ebx; char *
0x180022610  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022615  jmp     loc_18002269F
0x18002261a  lea     rcx, [rsp+38h+hKey]
0x18002261f  mov     [rsp+38h+hKey], 0
0x180022628  mov     qword ptr [rsp+38h+phkResult], rcx; int
0x18002262d  mov     r9d, 20019h; samDesired
0x180022633  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002263a  xor     r8d, r8d; ulOptions
0x18002263d  mov     rdx, rax; lpSubKey
0x180022640  call    cs:__imp_RegOpenKeyExW
0x180022646  mov     ebx, eax
0x180022648  test    eax, eax
0x18002264a  jle     short loc_180022655
0x18002264c  movzx   ebx, ax
0x18002264f  or      ebx, 80070000h
0x180022655  cmp     ebx, 80070002h
0x18002265b  jnz     short loc_180022671
0x18002265d  mov     rcx, [rsp+38h+hKey]; hKey
0x180022662  test    rcx, rcx
0x180022665  jz      short loc_18002266D
0x180022667  call    cs:__imp_RegCloseKey
0x18002266d  xor     eax, eax
0x18002266f  jmp     short loc_1800226A1
0x180022671  test    ebx, ebx
0x180022673  jns     short loc_180022690
0x180022675  mov     rcx, [rsp+38h]; this
0x18002267a  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180022681  mov     r9d, ebx; char *
0x180022684  mov     edx, 263h; void *
0x180022689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002268e  jmp     short loc_180022695
0x180022690  mov     ebx, 8007045Bh
0x180022695  lea     rcx, [rsp+38h+hKey]
0x18002269a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002269f  mov     eax, ebx
0x1800226a1  add     rsp, 30h
0x1800226a5  pop     rbx
0x1800226a6  retn
```

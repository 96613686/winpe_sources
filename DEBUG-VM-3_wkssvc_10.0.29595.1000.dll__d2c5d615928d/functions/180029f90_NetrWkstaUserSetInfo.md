# NetrWkstaUserSetInfo

- ea: `0x180029f90`
- end: `0x18002a064`
- name: `NetrWkstaUserSetInfo`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180009a40`
- `0x180029f90`
- `0x18002a06c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002a011`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a011`
- `ntdll!RtlReleaseResource` at `0x18002a05a`
- `ntdll!RtlReleaseResource` at `0x18002a05a`

## string_xrefs

- `0x180029fbf`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserSetInfo(__int64 a1, __int64 a2, BYTE ***a3, _DWORD *a4)
{
  int v6; // esi
  unsigned int v8; // edi

  v6 = a2;
  if ( a1 )
    return 87;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  if ( !*a3 )
  {
    if ( a4 )
      *a4 = -1;
    return 87;
  }
  if ( !RtlAcquireResourceExclusive(&WsInfo, 1u) )
    return 2140;
  if ( v6 == 1 || v6 == 1101 )
  {
    v8 = WsSetOtherDomains(v6, *a3);
    if ( v8 == 87 && a4 )
      *a4 = 101;
  }
  else
  {
    v8 = 124;
  }
  RtlReleaseResource(&WsInfo);
  return v8;
}

```

## disassembly

```asm
0x180029f90  mov     r11, rsp
0x180029f93  mov     [r11+8], rbx
0x180029f97  mov     [r11+10h], rsi
0x180029f9b  push    rdi
0x180029f9c  sub     rsp, 40h
0x180029fa0  mov     rbx, r9
0x180029fa3  mov     rdi, r8
0x180029fa6  mov     esi, edx
0x180029fa8  test    rcx, rcx
0x180029fab  jnz     short loc_180029FF3
0x180029fad  mov     rax, cs:ConfigurationInfoSd
0x180029fb4  lea     rcx, WsConfigInfoMapping
0x180029fbb  mov     [r11-18h], rcx
0x180029fbf  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180029fc6  mov     [rsp+48h+var_20], 8
0x180029fce  mov     [r11-28h], rax
0x180029fd2  call    NetpAccessCheckAndAuditEx
0x180029fd7  test    eax, eax
0x180029fd9  jz      short loc_180029FE2
0x180029fdb  mov     eax, 5
0x180029fe0  jmp     short loc_180029FF8
0x180029fe2  cmp     qword ptr [rdi], 0
0x180029fe6  jnz     short loc_18002A008
0x180029fe8  test    rbx, rbx
0x180029feb  jz      short loc_180029FF3
0x180029fed  mov     dword ptr [rbx], 0FFFFFFFFh
0x180029ff3  mov     eax, 57h ; 'W'
0x180029ff8  mov     rbx, [rsp+48h+arg_0]
0x180029ffd  mov     rsi, [rsp+48h+arg_8]
0x18002a002  add     rsp, 40h
0x18002a006  pop     rdi
0x18002a007  retn
0x18002a008  mov     dl, 1; Wait
0x18002a00a  lea     rcx, WsInfo; Resource
0x18002a011  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a017  test    al, al
0x18002a019  jnz     short loc_18002A022
0x18002a01b  mov     eax, 85Ch
0x18002a020  jmp     short loc_180029FF8
0x18002a022  mov     eax, esi
0x18002a024  sub     eax, 1
0x18002a027  jz      short loc_18002A037
0x18002a029  cmp     eax, 44Ch
0x18002a02e  jz      short loc_18002A037
0x18002a030  mov     edi, 7Ch ; '|'
0x18002a035  jmp     short loc_18002A053
0x18002a037  mov     rdx, [rdi]
0x18002a03a  mov     ecx, esi
0x18002a03c  call    WsSetOtherDomains
0x18002a041  mov     edi, eax
0x18002a043  cmp     eax, 57h ; 'W'
0x18002a046  jnz     short loc_18002A053
0x18002a048  test    rbx, rbx
0x18002a04b  jz      short loc_18002A053
0x18002a04d  mov     dword ptr [rbx], 65h ; 'e'
0x18002a053  lea     rcx, WsInfo; Resource
0x18002a05a  call    cs:__imp_RtlReleaseResource
0x18002a060  mov     eax, edi
0x18002a062  jmp     short loc_180029FF8
```

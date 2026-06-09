# Registry::OpenKeyForRead<Registry::NotFoundPolicy::Throw>(HKEY__ *,ushort const *)

- ea: `0x1800146cc`
- end: `0x180014749`
- name: `??$OpenKeyForRead@UThrow@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z`
- size: `125`
- prototype: `PHKEY __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800150ac`

## callees

- `0x1800146cc`
- `0x18001487c`
- `0x180019640`
- `0x18001993c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014713`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014713`

## string_xrefs

- `0x180014705`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall Registry::OpenKeyForRead<Registry::NotFoundPolicy::Throw>(PHKEY phkResult)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness",
         0,
         0x20019u,
         phkResult);
  if ( v2 == 2 )
    Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::Throw>();
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xB5, v3, (const char *)v2, phkResulta);
  return phkResult;
}

```

## disassembly

```asm
0x1800146cc  mov     [rsp+arg_0], rcx
0x1800146d1  push    rbx
0x1800146d2  sub     rsp, 40h
0x1800146d6  mov     rbx, rcx
0x1800146d9  mov     [rsp+48h+var_18], 0
0x1800146e1  mov     qword ptr [rcx], 0
0x1800146e8  mov     [rsp+48h+var_18], 1
0x1800146f0  xor     edx, edx
0x1800146f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800146f7  mov     qword ptr [rsp+48h+phkResult], rbx; unsigned int
0x1800146fc  mov     r9d, 20019h; samDesired
0x180014702  xor     r8d, r8d; ulOptions
0x180014705  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001470c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014713  call    cs:__imp_RegOpenKeyExW
0x180014719  mov     edx, 2
0x18001471e  cmp     eax, edx
0x180014720  jnz     short loc_180014728
0x180014722  call    ??$RegKeyNotFoundHandler@UThrow@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@JPEAUHKEY__@@PEBG@Z; Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::Throw>(long,HKEY__ *,ushort const *)
0x180014728  test    eax, eax
0x18001472a  jz      short loc_18001473F
0x18001472c  mov     rcx, [rsp+48h]; this
0x180014731  mov     r9d, eax; char *
0x180014734  mov     edx, 0B5h; void *
0x180014739  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001473f  mov     rax, rbx
0x180014742  add     rsp, 40h
0x180014746  pop     rbx
0x180014747  retn
```

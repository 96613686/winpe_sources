# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)

- ea: `0x18012913c`
- end: `0x18012920d`
- name: `?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z`
- size: `209`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801297e8`
- `0x18012cad4`
- `0x18012d6b0`

## callees

- `0x1800e7c08`
- `0x180104108`
- `0x18012886c`
- `0x18012913c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012918a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012918a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801291c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801291c8`

## string_xrefs

- `0x1801291e1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  const WCHAR *v5; // rax
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v13 = HIDWORD(this);
  *a3 = 63;
  pcbData = 4;
  hkey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath();
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v7 = 193;
  }
  else
  {
    ValueW = RegGetValueW(hkey, a2, L"EnrollmentType", 0x10u, 0, a3, &pcbData);
    if ( ValueW == 2 || !ValueW )
    {
      v8 = 0;
      goto LABEL_8;
    }
    v7 = 206;
  }
  v8 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v7,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
         (const char *)ValueW,
         phkResult);
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v8;
}

```

## disassembly

```asm
0x18012913c  mov     rax, rsp
0x18012913f  mov     [rax+10h], rbx
0x180129143  mov     [rax+8], rcx
0x180129147  push    rdi
0x180129148  sub     rsp, 40h
0x18012914c  mov     rbx, r8
0x18012914f  mov     dword ptr [r8], 3Fh ; '?'
0x180129156  mov     rdi, rdx
0x180129159  mov     dword ptr [rax+8], 4
0x180129160  mov     qword ptr [rax+18h], 0
0x180129168  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18012916d  lea     rcx, [rsp+48h+hkey]
0x180129172  mov     r9d, 20019h; samDesired
0x180129178  mov     [rsp+48h+phkResult], rcx; phkResult
0x18012917d  xor     r8d, r8d; ulOptions
0x180129180  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180129187  mov     rdx, rax; lpSubKey
0x18012918a  call    cs:__imp_RegOpenKeyExW
0x180129190  test    eax, eax
0x180129192  jz      short loc_18012919B
0x180129194  mov     edx, 0C1h
0x180129199  jmp     short loc_1801291DC
0x18012919b  mov     rcx, [rsp+48h+hkey]; hkey
0x1801291a0  lea     rax, [rsp+48h+arg_0]
0x1801291a5  mov     [rsp+48h+pcbData], rax; pcbData
0x1801291aa  lea     r8, aEnrollmenttype; "EnrollmentType"
0x1801291b1  mov     [rsp+48h+pvData], rbx; pvData
0x1801291b6  mov     r9d, 10h; dwFlags
0x1801291bc  mov     rdx, rdi; lpSubKey
0x1801291bf  mov     [rsp+48h+phkResult], 0; unsigned int
0x1801291c8  call    cs:__imp_RegGetValueW
0x1801291ce  cmp     eax, 2
0x1801291d1  jz      short loc_1801291F4
0x1801291d3  test    eax, eax
0x1801291d5  jz      short loc_1801291F4
0x1801291d7  mov     edx, 0CEh; void *
0x1801291dc  mov     rcx, [rsp+48h]; this
0x1801291e1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801291e8  mov     r9d, eax; char *
0x1801291eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801291f0  mov     ebx, eax
0x1801291f2  jmp     short loc_1801291F6
0x1801291f4  xor     ebx, ebx
0x1801291f6  lea     rcx, [rsp+48h+hkey]
0x1801291fb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180129200  mov     eax, ebx
0x180129202  mov     rbx, [rsp+48h+arg_8]
0x180129207  add     rsp, 40h
0x18012920b  pop     rdi
0x18012920c  retn
```

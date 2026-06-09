# OOBE::CompleteTime::TryGetTime

- ea: `0x18003639c`
- end: `0x18003647d`
- name: `OOBE::CompleteTime::TryGetTime`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d654`
- `0x180036910`

## callees

- `0x18003560c`
- `0x180035b08`
- `0x18003639c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800363ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036452`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800363ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036452`

## string_xrefs

- `0x1800363e2`: `OOBECompleteTimestamp`

## pseudocode

```c
__int64 __fastcall OOBE::CompleteTime::TryGetTime(bool *a1, _OWORD *a2)
{
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  *a1 = 0;
  pcbData = 16;
  hkey = 0;
  *a2 = 0;
  if ( (int)OOBE::CompleteTime::details::GetOOBECompleteKey((unsigned __int16 *)&hkey, (const unsigned __int16 *)a2) >= 0 )
    *a1 = RegGetValueW(hkey, 0, L"OOBECompleteTimestamp", 0x20000008u, 0, a2, &pcbData) == 0;
  if ( !*a1 )
  {
    pcbData = 16;
    *a1 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"EndTimeStamp",
            0x20000008u,
            0,
            a2,
            &pcbData) == 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x18003639c  mov     rax, rsp
0x18003639f  mov     [rax+10h], rbx
0x1800363a3  push    rdi
0x1800363a4  sub     rsp, 40h
0x1800363a8  mov     rbx, rcx
0x1800363ab  mov     byte ptr [rcx], 0
0x1800363ae  xorps   xmm0, xmm0
0x1800363b1  mov     dword ptr [rax+8], 10h
0x1800363b8  lea     rcx, [rax+18h]; phkResult
0x1800363bc  mov     qword ptr [rax+18h], 0
0x1800363c4  movups  xmmword ptr [rdx], xmm0
0x1800363c7  mov     rdi, rdx
0x1800363ca  call    OOBE__CompleteTime__details__GetOOBECompleteKey
0x1800363cf  test    eax, eax
0x1800363d1  js      short loc_180036412
0x1800363d3  mov     rcx, [rsp+48h+hkey]; hkey
0x1800363d8  lea     rax, [rsp+48h+arg_0]
0x1800363dd  mov     [rsp+48h+pcbData], rax; pcbData
0x1800363e2  lea     r8, aOobecompleteti; "OOBECompleteTimestamp"
0x1800363e9  mov     [rsp+48h+pvData], rdi; pvData
0x1800363ee  mov     r9d, 20000008h; dwFlags
0x1800363f4  xor     edx, edx; lpSubKey
0x1800363f6  mov     [rsp+48h+pdwType], 0; pdwType
0x1800363ff  call    cs:__imp_RegGetValueW
0x180036406  nop     dword ptr [rax+rax+00h]
0x18003640b  test    eax, eax
0x18003640d  setz    al
0x180036410  mov     [rbx], al
0x180036412  cmp     byte ptr [rbx], 0
0x180036415  jnz     short loc_180036465
0x180036417  lea     rax, [rsp+48h+arg_0]
0x18003641c  mov     [rsp+48h+arg_0], 10h
0x180036424  mov     [rsp+48h+pcbData], rax; pcbData
0x180036429  lea     r8, aEndtimestamp; "EndTimeStamp"
0x180036430  mov     [rsp+48h+pvData], rdi; pvData
0x180036435  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003643c  mov     r9d, 20000008h; dwFlags
0x180036442  mov     [rsp+48h+pdwType], 0; pdwType
0x18003644b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180036452  call    cs:__imp_RegGetValueW
0x180036459  nop     dword ptr [rax+rax+00h]
0x18003645e  test    eax, eax
0x180036460  setz    al
0x180036463  mov     [rbx], al
0x180036465  lea     rcx, [rsp+48h+hkey]
0x18003646a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003646f  mov     rbx, [rsp+48h+arg_8]
0x180036474  xor     eax, eax
0x180036476  add     rsp, 40h
0x18003647a  pop     rdi
0x18003647b  retn
```

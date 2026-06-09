# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize(void)

- ea: `0x18000c400`
- end: `0x18000c48f`
- name: `?Initialize@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@MEAA_NXZ`
- size: `143`
- prototype: `char __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b680`
- `0x18000c400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c440`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c45f`

## string_xrefs

- `0x18000c426`: `AssignedAccessConfiguration`
- `0x18000c41b`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  LPVOID v5; // rsi
  char v6; // al
  char v7; // bl
  void *v8; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              (char *)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
              (__int64)L"AssignedAccessConfiguration",
              &pv,
              a4) < 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  v5 = pv;
  v6 = 0;
  v7 = 1;
  if ( pv )
  {
    v8 = (void *)*((_QWORD *)this + 1);
    if ( v8 )
      CoTaskMemFree(v8);
    v6 = 1;
    *((_QWORD *)this + 1) = v5;
    *((_QWORD *)this + 3) = -1;
    *((_QWORD *)this + 2) = -1;
  }
  if ( !v6 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x18000c400  mov     rax, rsp
0x18000c403  mov     [rax+10h], rbx
0x18000c407  mov     [rax+18h], rsi
0x18000c40b  push    rdi
0x18000c40c  sub     rsp, 20h
0x18000c410  mov     rdi, rcx
0x18000c413  mov     qword ptr [rax+8], 0
0x18000c41b  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x18000c422  lea     r8, [rax+8]
0x18000c426  lea     rdx, aAssignedaccess; "AssignedAccessConfiguration"
0x18000c42d  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000c432  test    eax, eax
0x18000c434  jns     short loc_18000C448
0x18000c436  mov     rcx, [rsp+28h+pv]; pv
0x18000c43b  test    rcx, rcx
0x18000c43e  jz      short loc_18000C47B
0x18000c440  call    cs:__imp_CoTaskMemFree
0x18000c446  jmp     short loc_18000C47B
0x18000c448  mov     rsi, [rsp+28h+pv]
0x18000c44d  xor     al, al
0x18000c44f  mov     bl, 1
0x18000c451  test    rsi, rsi
0x18000c454  jz      short loc_18000C477
0x18000c456  mov     rcx, [rdi+8]; pv
0x18000c45a  test    rcx, rcx
0x18000c45d  jz      short loc_18000C465
0x18000c45f  call    cs:__imp_CoTaskMemFree
0x18000c465  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c469  mov     [rdi+8], rsi
0x18000c46d  mov     [rdi+18h], rax
0x18000c471  mov     [rdi+10h], rax
0x18000c475  mov     al, bl
0x18000c477  test    al, al
0x18000c479  jnz     short loc_18000C47D
0x18000c47b  xor     bl, bl
0x18000c47d  mov     rsi, [rsp+28h+arg_10]
0x18000c482  mov     al, bl
0x18000c484  mov     rbx, [rsp+28h+arg_8]
0x18000c489  add     rsp, 20h
0x18000c48d  pop     rdi
0x18000c48e  retn
```

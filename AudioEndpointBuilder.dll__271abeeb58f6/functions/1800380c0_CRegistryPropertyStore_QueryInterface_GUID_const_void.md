# CRegistryPropertyStore::QueryInterface(_GUID const &,void * *)

- ea: `0x1800380c0`
- end: `0x18003819f`
- name: `?QueryInterface@CRegistryPropertyStore@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: `int(CRegistryPropertyStore *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000fb60`
- `0x180010da8`
- `0x1800380c0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003817e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003817e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003818e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003818e`

## string_xrefs

- `0x1800380d3`: `avcore\audiocore\deviceapi\registrypropertystore\registrypropertystore.cpp`

## pseudocode

```c
__int64 __fastcall CRegistryPropertyStore::QueryInterface(
        CRegistryPropertyStore *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPOLESTR lpsz; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
      v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
    if ( !v5 )
      goto LABEL_12;
    v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1 )
      v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data4;
    if ( !v6 )
      goto LABEL_12;
    v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_95b0d208_7331_44a7_82d7_98408a20c299.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_95b0d208_7331_44a7_82d7_98408a20c299.Data1 )
      v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_95b0d208_7331_44a7_82d7_98408a20c299.Data4;
    if ( v7 )
    {
      lpsz = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &lpsz,
        0);
      StringFromCLSID(a2, &lpsz);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      return 2147500034LL;
    }
    else
    {
LABEL_12:
      *a3 = this;
      (*(void (__fastcall **)(CRegistryPropertyStore *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"avcore\\audiocore\\deviceapi\\registrypropertystore\\registrypropertystore.cpp",
      (const char *)0x80004003LL,
      v8);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800380c0  push    rbx; int
0x1800380c2  sub     rsp, 20h
0x1800380c6  mov     rbx, rdx
0x1800380c9  test    r8, r8
0x1800380cc  jnz     short loc_1800380F3
0x1800380ce  mov     rcx, [rsp+28h]; this
0x1800380d3  lea     r8, aAvcoreAudiocor_14; "avcore\\audiocore\\deviceapi\\registryp"...
0x1800380da  mov     ebx, 80004003h
0x1800380df  mov     edx, 152h; void *
0x1800380e4  mov     r9d, ebx; char *
0x1800380e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380ec  mov     eax, ebx
0x1800380ee  jmp     loc_180038199
0x1800380f3  mov     qword ptr [r8], 0
0x1800380fa  mov     rax, [rdx]
0x1800380fd  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x180038104  jnz     short loc_180038111
0x180038106  mov     rax, [rdx+8]
0x18003810a  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180038111  test    rax, rax
0x180038114  jz      short loc_18003814E
0x180038116  mov     rax, [rdx]
0x180038119  sub     rax, qword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1
0x180038120  jnz     short loc_18003812D
0x180038122  mov     rax, [rdx+8]
0x180038126  sub     rax, qword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data4
0x18003812d  test    rax, rax
0x180038130  jz      short loc_18003814E
0x180038132  mov     rax, [rdx]
0x180038135  sub     rax, qword ptr cs:_GUID_95b0d208_7331_44a7_82d7_98408a20c299.Data1
0x18003813c  jnz     short loc_180038149
0x18003813e  mov     rax, [rdx+8]
0x180038142  sub     rax, qword ptr cs:_GUID_95b0d208_7331_44a7_82d7_98408a20c299.Data4
0x180038149  test    rax, rax
0x18003814c  jnz     short loc_180038161
0x18003814e  mov     [r8], rcx
0x180038151  mov     rax, [rcx]
0x180038154  mov     rax, [rax+8]
0x180038158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003815d  xor     eax, eax
0x18003815f  jmp     short loc_180038199
0x180038161  xor     edx, edx
0x180038163  mov     [rsp+28h+lpsz], 0
0x18003816c  lea     rcx, [rsp+28h+lpsz]
0x180038171  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180038176  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18003817b  mov     rcx, rbx; rclsid
0x18003817e  call    cs:__imp_StringFromCLSID
0x180038184  mov     rcx, [rsp+28h+lpsz]; pv
0x180038189  test    rcx, rcx
0x18003818c  jz      short loc_180038194
0x18003818e  call    cs:__imp_CoTaskMemFree
0x180038194  mov     eax, 80004002h
0x180038199  add     rsp, 20h
0x18003819d  pop     rbx
0x18003819e  retn
```

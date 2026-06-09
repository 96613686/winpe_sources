# RfbServerFolderQuery::GetOneInstanceFromKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180013250`
- end: `0x1800132de`
- name: `?GetOneInstanceFromKey@RfbServerFolderQuery@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `142`
- prototype: `void __fastcall(__int64, _QWORD *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d6b8`
- `0x180013190`
- `0x180013250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132c8`

## pseudocode

```c
void __fastcall RfbServerFolderQuery::GetOneInstanceFromKey(__int64 a1, _QWORD *a2, void **a3)
{
  void *v5; // rcx
  __int64 v7; // rcx
  void **v8; // rax
  void *v9; // rdx
  void *v10; // rcx
  void *v11; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v5 = *a3;
  *a3 = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  if ( (unsigned __int8)RfbServerRegistrar::IsServerRegistered(*(PSRWLOCK *)(a1 + 72)) )
  {
    v8 = (void **)RfbServerFolderQuery::CreatePidl(v7, &pv, a2);
    v9 = *v8;
    *v8 = 0;
    v10 = *a3;
    *a3 = v9;
    if ( v10 )
      CoTaskMemFree(v10);
    v11 = pv;
    pv = 0;
    if ( v11 )
      CoTaskMemFree(v11);
  }
}

```

## disassembly

```asm
0x180013250  mov     [rsp+arg_8], rbx
0x180013255  mov     [rsp+arg_10], rsi
0x18001325a  push    rdi
0x18001325b  sub     rsp, 20h
0x18001325f  mov     rsi, rcx
0x180013262  mov     rbx, r8
0x180013265  mov     rcx, [r8]; pv
0x180013268  mov     rdi, rdx
0x18001326b  mov     qword ptr [r8], 0
0x180013272  test    rcx, rcx
0x180013275  jz      short loc_18001327D
0x180013277  call    cs:__imp_CoTaskMemFree
0x18001327d  mov     rcx, [rsi+48h]; SRWLock
0x180013281  mov     rdx, rdi
0x180013284  call    ?IsServerRegistered@RfbServerRegistrar@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbServerRegistrar::IsServerRegistered(std::wstring const &)
0x180013289  test    al, al
0x18001328b  jz      short loc_1800132CE
0x18001328d  mov     r8, rdi
0x180013290  lea     rdx, [rsp+28h+pv]
0x180013295  call    ?CreatePidl@RfbServerFolderQuery@@IEAA?AV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbServerFolderQuery::CreatePidl(std::wstring const &)
0x18001329a  mov     rdx, [rax]
0x18001329d  mov     qword ptr [rax], 0
0x1800132a4  mov     rcx, [rbx]; pv
0x1800132a7  mov     [rbx], rdx
0x1800132aa  test    rcx, rcx
0x1800132ad  jz      short loc_1800132B5
0x1800132af  call    cs:__imp_CoTaskMemFree
0x1800132b5  mov     rcx, [rsp+28h+pv]; pv
0x1800132ba  mov     [rsp+28h+pv], 0
0x1800132c3  test    rcx, rcx
0x1800132c6  jz      short loc_1800132CE
0x1800132c8  call    cs:__imp_CoTaskMemFree
0x1800132ce  mov     rbx, [rsp+28h+arg_8]
0x1800132d3  mov     rsi, [rsp+28h+arg_10]
0x1800132d8  add     rsp, 20h
0x1800132dc  pop     rdi
0x1800132dd  retn
```

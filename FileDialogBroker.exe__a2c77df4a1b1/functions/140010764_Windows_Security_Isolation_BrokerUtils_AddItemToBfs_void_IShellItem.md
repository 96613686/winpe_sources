# Windows::Security::Isolation::BrokerUtils::AddItemToBfs(void *,IShellItem *)

- ea: `0x140010764`
- end: `0x14001087e`
- name: `?AddItemToBfs@BrokerUtils@Isolation@Security@Windows@@SAXPEAXPEAUIShellItem@@@Z`
- size: `282`
- prototype: `void __fastcall(char *, struct IShellItem *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c230`
- `0x140010654`

## callees

- `0x140007df4`
- `0x14000fed4`
- `0x1400105c4`
- `0x140010764`
- `0x140014010`

## string_xrefs

- `0x14001078e`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x1400107af`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x1400107eb`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`
- `0x14001082b`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`

## pseudocode

```c
void __fastcall Windows::Security::Isolation::BrokerUtils::AddItemToBfs(char *a1, struct IShellItem *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // r8
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  try
  {
    if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)0x80070006LL,
        v8);
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)0x80004003LL,
        v8);
    v10 = 0;
    v4 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned int *))a2->lpVtbl->GetAttributes)(
           a2,
           1610612736,
           &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)(unsigned int)v4,
        v8);
    v11 = 0;
    v5 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, __int64 *))a2->lpVtbl->GetDisplayName)(
           a2,
           2147844096LL,
           &v11);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)(unsigned int)v5,
        v8);
    v6 = (v10 >> 30) & 1;
    if ( (v10 & 0x20000000) != 0 )
      v6 = 2;
    Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath(a1, v11, v6);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Throw_CaughtException(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x140010764  mov     [rsp+arg_8], rbx
0x140010769  push    rdi
0x14001076a  sub     rsp, 30h
0x14001076e  mov     rbx, rdx
0x140010771  mov     rdi, rcx
0x140010774  lea     rax, [rcx-1]
0x140010778  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001077c  setnbe  al
0x14001077f  mov     rcx, [rsp+38h]; this
0x140010784  test    al, al
0x140010786  jz      short loc_14001079F
0x140010788  mov     r9d, 80070006h; char *
0x14001078e  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010795  mov     edx, 0Dh; void *
0x14001079a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001079f  mov     rcx, [rsp+38h]; this
0x1400107a4  test    rbx, rbx
0x1400107a7  jnz     short loc_1400107BE
0x1400107a9  mov     r9d, 80004003h; char *
0x1400107af  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400107b6  lea     edx, [rbx+0Eh]; void *
0x1400107b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400107be  mov     [rsp+38h+arg_0], 0
0x1400107c6  mov     rax, [rdx]
0x1400107c9  lea     r8, [rsp+38h+arg_0]
0x1400107ce  mov     edx, 60000000h
0x1400107d3  mov     rcx, rbx
0x1400107d6  mov     rax, [rax+30h]
0x1400107da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107df  mov     rcx, [rsp+38h]; this
0x1400107e4  test    eax, eax
0x1400107e6  jns     short loc_1400107FD
0x1400107e8  mov     r9d, eax; char *
0x1400107eb  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x1400107f2  mov     edx, 11h; void *
0x1400107f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400107fd  mov     [rsp+38h+arg_10], 0
0x140010806  mov     rax, [rbx]
0x140010809  lea     r8, [rsp+38h+arg_10]
0x14001080e  mov     edx, 80058000h
0x140010813  mov     rcx, rbx
0x140010816  mov     rax, [rax+28h]
0x14001081a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001081f  mov     rcx, [rsp+38h]; this
0x140010824  test    eax, eax
0x140010826  jns     short loc_14001083C
0x140010828  mov     r9d, eax; char *
0x14001082b  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010832  mov     edx, 14h; void *
0x140010837  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14001083c  mov     r8d, [rsp+38h+arg_0]
0x140010841  shr     r8d, 1Eh
0x140010845  and     r8d, 1
0x140010849  test    [rsp+38h+arg_0], 20000000h
0x140010851  mov     eax, 2
0x140010856  cmovnz  r8d, eax
0x14001085a  mov     rdx, [rsp+38h+arg_10]
0x14001085f  mov     rcx, rdi
0x140010862  call    ?AddBfsPolicyEntryForTokenAndFilepath@BrokerUtils@Isolation@Security@Windows@@CAXPEAXPEAGW4_BFS_ENTRY_TYPE@@W4_BFS_POLICY@@K@Z; Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath(void *,ushort *,_BFS_ENTRY_TYPE,_BFS_POLICY,ulong)
0x140010867  nop
0x140010868  lea     rcx, [rsp+38h+arg_10]
0x14001086d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010872  nop
0x140010873  mov     rbx, [rsp+38h+arg_8]
0x140010878  add     rsp, 30h
0x14001087c  pop     rdi
0x14001087d  retn
```

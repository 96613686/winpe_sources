# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180016eec`
- end: `0x180016fd4`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `232`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e44`

## callees

- `0x18000912c`
- `0x180014ccc`
- `0x1800156c8`
- `0x180016eec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f3c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016f2b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016f6e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016f2b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180016f6e`

## string_xrefs

- `0x180016f21`: `OOBECompleteTimestamp`
- `0x180016f67`: `OOBECompleteTimestamp`
- `0x180016f13`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x180016f54`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall GetRedirectionKeyPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int *p_cb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v14; // [rsp+40h] [rbp+8h] BYREF
  unsigned int cb; // [rsp+48h] [rbp+10h] BYREF
  int cb_4; // [rsp+4Ch] [rbp+14h]

  cb_4 = HIDWORD(a2);
  v14 = a1;
  cb = 0;
  p_cb = &cb;
  *a3 = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"OOBECompleteTimestamp",
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                       a3,
                       0) == 234 )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc(cb);
    v14 = v7;
    v8 = v7;
    if ( v7 )
    {
      LODWORD(p_cb) = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(
                            L"OOBECompleteTimestamp",
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                            v7,
                            cb) )
      {
        v14 = 0;
        *a3 = v8;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  }
  if ( *a3 )
    return 0;
  v9 = _AllocStringWorker<CTCoAllocPolicy>(v5, v4, v6, 68);
  v10 = v9;
  if ( v9 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
    (const char *)(unsigned int)v9,
    (int)p_cb);
  return v10;
}

```

## disassembly

```asm
0x180016eec  mov     rax, rsp
0x180016eef  mov     [rax+18h], rbx
0x180016ef3  mov     [rax+10h], rdx
0x180016ef7  mov     [rax+8], rcx
0x180016efb  push    rdi
0x180016efc  sub     rsp, 30h
0x180016f00  mov     dword ptr [rax+10h], 0
0x180016f07  lea     rax, [rax+10h]
0x180016f0b  xor     r9d, r9d
0x180016f0e  mov     qword ptr [rsp+38h+var_18], rax
0x180016f13  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016f1a  mov     qword ptr [r8], 0
0x180016f21  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180016f28  mov     rdi, r8
0x180016f2b  call    cs:__imp_GetPersistedRegistryLocationW
0x180016f31  cmp     eax, 0EAh
0x180016f36  jnz     short loc_180016F8E
0x180016f38  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x180016f3c  call    cs:__imp_CoTaskMemAlloc
0x180016f42  mov     [rsp+38h+arg_0], rax
0x180016f47  mov     rbx, rax
0x180016f4a  test    rax, rax
0x180016f4d  jz      short loc_180016F84
0x180016f4f  mov     r9d, dword ptr [rsp+38h+cb]
0x180016f54  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180016f5b  mov     r8, rax
0x180016f5e  mov     qword ptr [rsp+38h+var_18], 0; int
0x180016f67  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180016f6e  call    cs:__imp_GetPersistedRegistryLocationW
0x180016f74  test    eax, eax
0x180016f76  jnz     short loc_180016F84
0x180016f78  mov     [rsp+38h+arg_0], 0
0x180016f81  mov     [rdi], rbx
0x180016f84  lea     rcx, [rsp+38h+arg_0]
0x180016f89  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016f8e  cmp     qword ptr [rdi], 0
0x180016f92  jnz     short loc_180016FC7
0x180016f94  mov     r9d, 44h ; 'D'
0x180016f9a  mov     [rsp+38h+var_10], rdi
0x180016f9f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180016fa4  mov     ebx, eax
0x180016fa6  test    eax, eax
0x180016fa8  jns     short loc_180016FC7
0x180016faa  mov     rcx, [rsp+38h]; this
0x180016faf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x180016fb6  mov     r9d, eax; char *
0x180016fb9  mov     edx, 2Eh ; '.'; void *
0x180016fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fc3  mov     eax, ebx
0x180016fc5  jmp     short loc_180016FC9
0x180016fc7  xor     eax, eax
0x180016fc9  mov     rbx, [rsp+38h+arg_10]
0x180016fce  add     rsp, 30h
0x180016fd2  pop     rdi
0x180016fd3  retn
```

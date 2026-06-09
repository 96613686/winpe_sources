# WindowsStorage::Utilities::registry_get_path(HKEY__ *,unsigned __int64 *)

- ea: `0x180010e74`
- end: `0x180010f70`
- name: `?registry_get_path@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEA_K@Z`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000cf04`

## callees

- `0x18000bf7c`
- `0x18000f594`
- `0x180010690`
- `0x1800106b0`
- `0x180010e74`

## import_xrefs

- `ntdll!NtQueryKey` at `0x180010ea5`
- `ntdll!NtQueryKey` at `0x180010f09`
- `ntdll!NtQueryKey` at `0x180010ea5`
- `ntdll!NtQueryKey` at `0x180010f09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ebf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010ebf`

## string_xrefs

- `0x180010ed7`: `onecore\base\windows.storage\src\Registry.h`
- `0x180010f1b`: `onecore\base\windows.storage\src\Registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WindowsStorage::Utilities::registry_get_path(_QWORD *a1, void *a2, unsigned __int64 *a3)
{
  unsigned int Key; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned int *v9; // rbx
  const char *v10; // r9
  NTSTATUS v11; // eax
  int ResultLength; // [rsp+20h] [rbp-48h]
  int ResultLengtha; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  SIZE_T uBytes; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(uBytes) = 0;
  Key = NtQueryKey(a2, KeyNameInformation, 0, 0, (PULONG)&uBytes);
  if ( Key != -1073741789 )
    wil::details::in1diag3::Throw_NtStatus(retaddr, v7, v8, (const char *)Key, ResultLength);
  v9 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
  if ( !v9 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      v10);
  v11 = NtQueryKey(a2, KeyNameInformation, v9, uBytes, (PULONG)&uBytes);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)(unsigned int)v11,
      ResultLengtha);
  if ( a3 )
    *a3 = (unsigned __int64)*v9 >> 1;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(a1);
  LocalFree(v9);
  return a1;
}

```

## disassembly

```asm
0x180010e74  mov     rax, rsp
0x180010e77  push    rbx
0x180010e78  push    rbp
0x180010e79  push    rsi
0x180010e7a  push    rdi
0x180010e7b  sub     rsp, 48h
0x180010e7f  mov     rdi, r8
0x180010e82  mov     rbp, rdx
0x180010e85  mov     rsi, rcx
0x180010e88  mov     dword ptr [rax+20h], 0
0x180010e8f  lea     rax, [rax+20h]
0x180010e93  mov     qword ptr [rsp+68h+ResultLength], rax; int
0x180010e98  xor     r9d, r9d; Length
0x180010e9b  xor     r8d, r8d; KeyInformation
0x180010e9e  lea     edx, [r9+3]; KeyInformationClass
0x180010ea2  mov     rcx, rbp; KeyHandle
0x180010ea5  call    cs:__imp_NtQueryKey
0x180010eab  cmp     eax, 0C0000023h
0x180010eb0  jnz     loc_180010F62
0x180010eb6  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x180010ebd  xor     ecx, ecx; uFlags
0x180010ebf  call    cs:__imp_LocalAlloc
0x180010ec5  mov     rbx, rax
0x180010ec8  mov     [rsp+68h+var_30], rax
0x180010ecd  mov     rcx, [rsp+68h]; this
0x180010ed2  test    rax, rax
0x180010ed5  jnz     short loc_180010EE9
0x180010ed7  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x180010ede  mov     edx, 99h; void *
0x180010ee3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180010ee9  lea     rax, [rsp+68h+uBytes]
0x180010ef1  mov     qword ptr [rsp+68h+ResultLength], rax; int
0x180010ef6  mov     r9d, dword ptr [rsp+68h+uBytes]; Length
0x180010efe  mov     r8, rbx; KeyInformation
0x180010f01  mov     edx, 3; KeyInformationClass
0x180010f06  mov     rcx, rbp; KeyHandle
0x180010f09  call    cs:__imp_NtQueryKey
0x180010f0f  mov     rcx, [rsp+68h]; this
0x180010f14  test    eax, eax
0x180010f16  jns     short loc_180010F2D
0x180010f18  mov     r9d, eax; char *
0x180010f1b  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x180010f22  mov     edx, 9Ch; void *
0x180010f27  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180010f2d  test    rdi, rdi
0x180010f30  jz      short loc_180010F3A
0x180010f32  mov     eax, [rbx]
0x180010f34  shr     rax, 1
0x180010f37  mov     [rdi], rax
0x180010f3a  lea     rdx, [rbx+4]
0x180010f3e  mov     r8d, [rbx]
0x180010f41  shr     r8, 1
0x180010f44  mov     rcx, rsi
0x180010f47  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180010f4c  nop
0x180010f4d  mov     rcx, rbx; hMem
0x180010f50  call    cs:__imp_LocalFree
0x180010f56  mov     rax, rsi
0x180010f59  add     rsp, 48h
0x180010f5d  pop     rdi
0x180010f5e  pop     rsi
0x180010f5f  pop     rbp
0x180010f60  pop     rbx
0x180010f61  retn
0x180010f62  mov     rcx, [rsp+68h]; this
0x180010f67  mov     r9d, eax; char *
0x180010f6a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```

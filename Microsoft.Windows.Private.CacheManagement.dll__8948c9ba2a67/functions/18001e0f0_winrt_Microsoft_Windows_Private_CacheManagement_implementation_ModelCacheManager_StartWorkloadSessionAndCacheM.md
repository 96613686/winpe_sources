# _winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow_::_1_::catch$0

- ea: `0x18001e0f0`
- end: `0x18001e14a`
- name: `_winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow_::_1_::catch$0`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f810`
- `0x18001e0f0`

## string_xrefs

- `0x18001e127`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`
- `0x18001e120`: `StartWorkloadSessionAndCacheModel failed with package: %ws`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::StartWorkloadSessionAndCacheModels_NoThrow_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax

  v2 = *(_QWORD *)(a2 + 72);
  if ( *(_QWORD *)v2 )
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      *(wil::details::in1diag3 **)(a2 + 56),
      (void *)0x1C3,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
      "StartWorkloadSessionAndCacheModel failed with package: %ws",
      *(const char **)(*(_QWORD *)v2 + 16LL));
  else
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      *(wil::details::in1diag3 **)(a2 + 56),
      (void *)0x1C3,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
      "StartWorkloadSessionAndCacheModel failed with package: %ws",
      (const char *)&S2);
  return 0;
}

```

## disassembly

```asm
0x18001e0f0  mov     [rsp+arg_8], rdx
0x18001e0f5  push    rbp
0x18001e0f6  sub     rsp, 30h
0x18001e0fa  mov     rbp, rdx
0x18001e0fd  mov     rax, [rbp+48h]
0x18001e101  cmp     qword ptr [rax], 0
0x18001e105  jz      short loc_18001E110
0x18001e107  mov     rax, [rax]
0x18001e10a  mov     rdx, [rax+10h]
0x18001e10e  jmp     short loc_18001E117
0x18001e110  lea     rdx, S2
0x18001e117  mov     rcx, [rbp+38h]; this
0x18001e11b  mov     [rsp+38h+var_18], rdx; char *
0x18001e120  lea     r9, aStartworkloads; "StartWorkloadSessionAndCacheModel faile"...
0x18001e127  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001e12e  mov     edx, 1C3h; void *
0x18001e133  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18001e138  nop
0x18001e139  mov     rax, 0
0x18001e143  add     rsp, 30h
0x18001e147  pop     rbp
0x18001e148  retn
```

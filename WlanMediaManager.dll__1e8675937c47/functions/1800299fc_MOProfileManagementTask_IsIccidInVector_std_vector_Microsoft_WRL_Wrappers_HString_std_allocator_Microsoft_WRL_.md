# MOProfileManagementTask::IsIccidInVector(std::vector<Microsoft::WRL::Wrappers::HString,std::allocator<Microsoft::WRL::Wrappers::HString>> &,Microsoft::WRL::Wrappers::HString &)

- ea: `0x1800299fc`
- end: `0x180029a7a`
- name: `?IsIccidInVector@MOProfileManagementTask@@AEAA_NAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029148`

## callees

- `0x18001b230`
- `0x1800299fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180029a32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180029a32`

## string_xrefs

- `0x180029a41`: `onecoreuap\net\ux\wlanmediamanager\lib\moprofilemanagementtask.cpp`

## pseudocode

```c
char __fastcall MOProfileManagementTask::IsIccidInVector(__int64 a1, HSTRING **a2, HSTRING *a3)
{
  HSTRING *i; // rbx
  HSTRING v6; // rdx
  HSTRING v7; // rcx
  HRESULT v8; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 result; // [rsp+30h] [rbp+8h] BYREF

  result = a1;
  for ( i = *a2; i != a2[1]; ++i )
  {
    v6 = *a3;
    v7 = *i;
    LODWORD(result) = 0;
    v8 = WindowsCompareStringOrdinal(v7, v6, (INT32 *)&result);
    if ( v8 >= 0 )
    {
      if ( !(_DWORD)result )
        return 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\moprofilemanagementtask.cpp",
        (const char *)(unsigned int)v8,
        v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800299fc  mov     [rsp+arg_8], rbx
0x180029a01  mov     [rsp+arg_10], rsi
0x180029a06  mov     [rsp+result], rcx
0x180029a0b  push    rdi; int
0x180029a0c  sub     rsp, 20h
0x180029a10  mov     rbx, [rdx]
0x180029a13  mov     rsi, r8
0x180029a16  mov     rdi, rdx
0x180029a19  cmp     rbx, [rdi+8]
0x180029a1d  jz      short loc_180029A68
0x180029a1f  mov     rdx, [rsi]; string2
0x180029a22  lea     r8, [rsp+28h+result]; result
0x180029a27  mov     rcx, [rbx]; string1
0x180029a2a  mov     dword ptr [rsp+28h+result], 0
0x180029a32  call    cs:__imp_WindowsCompareStringOrdinal
0x180029a38  test    eax, eax
0x180029a3a  jns     short loc_180029A57
0x180029a3c  mov     rcx, [rsp+28h]; this
0x180029a41  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180029a48  mov     r9d, eax; char *
0x180029a4b  mov     edx, 0C3h; void *
0x180029a50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029a55  jmp     short loc_180029A5E
0x180029a57  cmp     dword ptr [rsp+28h+result], 0
0x180029a5c  jz      short loc_180029A64
0x180029a5e  add     rbx, 8
0x180029a62  jmp     short loc_180029A19
0x180029a64  mov     al, 1
0x180029a66  jmp     short loc_180029A6A
0x180029a68  xor     al, al
0x180029a6a  mov     rbx, [rsp+28h+arg_8]
0x180029a6f  mov     rsi, [rsp+28h+arg_10]
0x180029a74  add     rsp, 20h
0x180029a78  pop     rdi
0x180029a79  retn
```

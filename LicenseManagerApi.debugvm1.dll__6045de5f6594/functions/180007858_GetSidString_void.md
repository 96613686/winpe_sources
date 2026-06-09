# GetSidString(void *)

- ea: `0x180007858`
- end: `0x1800078ba`
- name: `?GetSidString@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@PEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x180007858`
- `0x18000ef94`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007895`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180007895`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSidString(__int64 a1, void *a2)
{
  const char *v3; // r8

  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( a2 && !ConvertSidToStringSidW(a2, (LPWSTR *)(a1 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      (wil::details::in1diag3 *)0x25B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\apisethost\\activationapis.cpp",
      v3);
  return a1;
}

```

## disassembly

```asm
0x180007858  mov     [rsp+arg_0], rcx
0x18000785d  push    rbx
0x18000785e  sub     rsp, 30h
0x180007862  mov     rax, rdx
0x180007865  mov     rbx, rcx
0x180007868  mov     [rsp+38h+var_18], 0
0x180007870  lea     rcx, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180007877  mov     [rbx], rcx
0x18000787a  lea     rdx, [rbx+8]; StringSid
0x18000787e  mov     qword ptr [rdx], 0
0x180007885  mov     [rsp+38h+var_18], 1
0x18000788d  test    rax, rax
0x180007890  jz      short loc_18000789F
0x180007892  mov     rcx, rax; Sid
0x180007895  call    cs:__imp_ConvertSidToStringSidW
0x18000789b  test    eax, eax
0x18000789d  jz      short loc_1800078A8
0x18000789f  mov     rax, rbx
0x1800078a2  add     rsp, 30h
0x1800078a6  pop     rbx
0x1800078a7  retn
0x1800078a8  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800078af  mov     ecx, 25Bh; this
0x1800078b4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(uint,char const *)
```

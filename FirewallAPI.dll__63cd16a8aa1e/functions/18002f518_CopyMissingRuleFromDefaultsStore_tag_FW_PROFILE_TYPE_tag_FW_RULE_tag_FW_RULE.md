# CopyMissingRuleFromDefaultsStore(_tag_FW_PROFILE_TYPE,_tag_FW_RULE *,_tag_FW_RULE * *)

- ea: `0x18002f518`
- end: `0x18002f614`
- name: `?CopyMissingRuleFromDefaultsStore@@YAJW4_tag_FW_PROFILE_TYPE@@PEAU_tag_FW_RULE@@PEAPEAU2@@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800308f8`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x18002f518`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f595`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002f595`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002f579`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002f579`
- `fwbase!FwBaseFree` at `0x18002f5af`
- `fwbase!FwBaseFree` at `0x18002f5af`
- `fwbase!FwReportReturnError` at `0x18002f5d6`
- `fwbase!FwReportReturnError` at `0x18002f5e5`
- `fwbase!FwReportReturnError` at `0x18002f5d6`
- `fwbase!FwReportReturnError` at `0x18002f5e5`
- `fwbase!FwStringCopy` at `0x18002f5c1`
- `fwbase!FwStringCopy` at `0x18002f5c1`
- `FWPolicyIOMgr!FwCopyRule` at `0x18002f562`
- `FWPolicyIOMgr!FwCopyRule` at `0x18002f562`

## string_xrefs

- `0x18002f5cf`: `CopyMissingRuleFromDefaultsStore`
- `0x18002f5de`: `CopyMissingRuleFromDefaultsStore`

## pseudocode

```c
__int64 __fastcall CopyMissingRuleFromDefaultsStore(int a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  GUID pguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  v6 = FwCopyRule(a2, a3);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  *(_DWORD *)(*(_QWORD *)a3 + 40LL) = a1;
  v6 = CoCreateGuid(&pguid);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v7 = -2147418113;
    v8 = 2147549183LL;
LABEL_7:
    FwReportReturnError("CopyMissingRuleFromDefaultsStore", v8);
    return (unsigned int)FwReportReturnError("CopyMissingRuleFromDefaultsStore", v7);
  }
  FwBaseFree(*(_QWORD *)(*(_QWORD *)a3 + 16LL));
  v6 = FwStringCopy(sz, *(_QWORD *)a3 + 16LL);
  v7 = v6;
  if ( v6 < 0 )
  {
LABEL_6:
    v8 = (unsigned int)v6;
    goto LABEL_7;
  }
  return v7;
}

```

## disassembly

```asm
0x18002f518  mov     [rsp+arg_0], rbx
0x18002f51d  mov     [rsp+arg_18], rsi
0x18002f522  push    rdi
0x18002f523  sub     rsp, 90h
0x18002f52a  mov     rax, cs:__security_cookie
0x18002f531  xor     rax, rsp
0x18002f534  mov     [rsp+98h+var_18], rax
0x18002f53c  mov     rbx, rdx
0x18002f53f  mov     rdi, r8
0x18002f542  xor     edx, edx; Val
0x18002f544  mov     esi, ecx
0x18002f546  xorps   xmm0, xmm0
0x18002f549  lea     rcx, [rsp+98h+sz]; void *
0x18002f54e  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x18002f553  lea     r8d, [rdx+4Eh]; Size
0x18002f557  call    memset_0
0x18002f55c  mov     rdx, rdi
0x18002f55f  mov     rcx, rbx
0x18002f562  call    cs:__imp_FwCopyRule
0x18002f568  mov     ebx, eax
0x18002f56a  test    eax, eax
0x18002f56c  js      short loc_18002F5CD
0x18002f56e  mov     rax, [rdi]
0x18002f571  lea     rcx, [rsp+98h+pguid]; pguid
0x18002f576  mov     [rax+28h], esi
0x18002f579  call    cs:__imp_CoCreateGuid
0x18002f57f  mov     ebx, eax
0x18002f581  test    eax, eax
0x18002f583  js      short loc_18002F5CD
0x18002f585  mov     r8d, 27h ; '''; cchMax
0x18002f58b  lea     rdx, [rsp+98h+sz]; lpsz
0x18002f590  lea     rcx, [rsp+98h+pguid]; rguid
0x18002f595  call    cs:__imp_StringFromGUID2
0x18002f59b  test    eax, eax
0x18002f59d  jnz     short loc_18002F5A8
0x18002f59f  mov     ebx, 8000FFFFh
0x18002f5a4  mov     edx, ebx
0x18002f5a6  jmp     short loc_18002F5CF
0x18002f5a8  mov     rcx, [rdi]
0x18002f5ab  mov     rcx, [rcx+10h]
0x18002f5af  call    cs:__imp_FwBaseFree
0x18002f5b5  mov     rdx, [rdi]
0x18002f5b8  lea     rcx, [rsp+98h+sz]
0x18002f5bd  add     rdx, 10h
0x18002f5c1  call    cs:__imp_FwStringCopy
0x18002f5c7  mov     ebx, eax
0x18002f5c9  test    eax, eax
0x18002f5cb  jns     short loc_18002F5ED
0x18002f5cd  mov     edx, eax
0x18002f5cf  lea     rcx, aCopymissingrul; "CopyMissingRuleFromDefaultsStore"
0x18002f5d6  call    cs:__imp_FwReportReturnError
0x18002f5dc  mov     edx, ebx
0x18002f5de  lea     rcx, aCopymissingrul; "CopyMissingRuleFromDefaultsStore"
0x18002f5e5  call    cs:__imp_FwReportReturnError
0x18002f5eb  mov     ebx, eax
0x18002f5ed  mov     eax, ebx
0x18002f5ef  mov     rcx, [rsp+98h+var_18]
0x18002f5f7  xor     rcx, rsp; StackCookie
0x18002f5fa  call    __security_check_cookie
0x18002f5ff  lea     r11, [rsp+98h+var_8]
0x18002f607  mov     rbx, [r11+10h]
0x18002f60b  mov     rsi, [r11+28h]
0x18002f60f  mov     rsp, r11
0x18002f612  pop     rdi
0x18002f613  retn
```

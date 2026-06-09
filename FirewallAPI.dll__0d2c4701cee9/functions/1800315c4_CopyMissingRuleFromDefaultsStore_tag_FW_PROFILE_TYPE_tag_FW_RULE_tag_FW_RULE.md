# CopyMissingRuleFromDefaultsStore(_tag_FW_PROFILE_TYPE,_tag_FW_RULE *,_tag_FW_RULE * *)

- ea: `0x1800315c4`
- end: `0x1800316eb`
- name: `?CopyMissingRuleFromDefaultsStore@@YAJW4_tag_FW_PROFILE_TYPE@@PEAU_tag_FW_RULE@@PEAPEAU2@@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032ba8`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x1800315c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003164d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003164d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003162b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003162b`
- `fwbase!FwBaseFree` at `0x18003166d`
- `fwbase!FwBaseFree` at `0x18003166d`
- `fwbase!FwReportReturnError` at `0x1800316a0`
- `fwbase!FwReportReturnError` at `0x1800316b5`
- `fwbase!FwReportReturnError` at `0x1800316a0`
- `fwbase!FwReportReturnError` at `0x1800316b5`
- `fwbase!FwStringCopy` at `0x180031685`
- `fwbase!FwStringCopy` at `0x180031685`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003160e`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003160e`

## string_xrefs

- `0x180031699`: `CopyMissingRuleFromDefaultsStore`
- `0x1800316ae`: `CopyMissingRuleFromDefaultsStore`

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
0x1800315c4  mov     [rsp+arg_0], rbx
0x1800315c9  mov     [rsp+arg_18], rsi
0x1800315ce  push    rdi
0x1800315cf  sub     rsp, 90h
0x1800315d6  mov     rax, cs:__security_cookie
0x1800315dd  xor     rax, rsp
0x1800315e0  mov     [rsp+98h+var_18], rax
0x1800315e8  mov     rbx, rdx
0x1800315eb  mov     rdi, r8
0x1800315ee  xor     edx, edx; Val
0x1800315f0  mov     esi, ecx
0x1800315f2  xorps   xmm0, xmm0
0x1800315f5  lea     rcx, [rsp+98h+sz]; void *
0x1800315fa  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x1800315ff  lea     r8d, [rdx+4Eh]; Size
0x180031603  call    memset_0
0x180031608  mov     rdx, rdi
0x18003160b  mov     rcx, rbx
0x18003160e  call    cs:__imp_FwCopyRule
0x180031615  nop     dword ptr [rax+rax+00h]
0x18003161a  mov     ebx, eax
0x18003161c  test    eax, eax
0x18003161e  js      short loc_180031697
0x180031620  mov     rax, [rdi]
0x180031623  lea     rcx, [rsp+98h+pguid]; pguid
0x180031628  mov     [rax+28h], esi
0x18003162b  call    cs:__imp_CoCreateGuid
0x180031632  nop     dword ptr [rax+rax+00h]
0x180031637  mov     ebx, eax
0x180031639  test    eax, eax
0x18003163b  js      short loc_180031697
0x18003163d  mov     r8d, 27h ; '''; cchMax
0x180031643  lea     rdx, [rsp+98h+sz]; lpsz
0x180031648  lea     rcx, [rsp+98h+pguid]; rguid
0x18003164d  call    cs:__imp_StringFromGUID2
0x180031654  nop     dword ptr [rax+rax+00h]
0x180031659  test    eax, eax
0x18003165b  jnz     short loc_180031666
0x18003165d  mov     ebx, 8000FFFFh
0x180031662  mov     edx, ebx
0x180031664  jmp     short loc_180031699
0x180031666  mov     rcx, [rdi]
0x180031669  mov     rcx, [rcx+10h]
0x18003166d  call    cs:__imp_FwBaseFree
0x180031674  nop     dword ptr [rax+rax+00h]
0x180031679  mov     rdx, [rdi]
0x18003167c  lea     rcx, [rsp+98h+sz]
0x180031681  add     rdx, 10h
0x180031685  call    cs:__imp_FwStringCopy
0x18003168c  nop     dword ptr [rax+rax+00h]
0x180031691  mov     ebx, eax
0x180031693  test    eax, eax
0x180031695  jns     short loc_1800316C3
0x180031697  mov     edx, eax
0x180031699  lea     rcx, aCopymissingrul; "CopyMissingRuleFromDefaultsStore"
0x1800316a0  call    cs:__imp_FwReportReturnError
0x1800316a7  nop     dword ptr [rax+rax+00h]
0x1800316ac  mov     edx, ebx
0x1800316ae  lea     rcx, aCopymissingrul; "CopyMissingRuleFromDefaultsStore"
0x1800316b5  call    cs:__imp_FwReportReturnError
0x1800316bc  nop     dword ptr [rax+rax+00h]
0x1800316c1  mov     ebx, eax
0x1800316c3  mov     eax, ebx
0x1800316c5  mov     rcx, [rsp+98h+var_18]
0x1800316cd  xor     rcx, rsp; StackCookie
0x1800316d0  call    __security_check_cookie
0x1800316d5  lea     r11, [rsp+98h+var_8]
0x1800316dd  mov     rbx, [r11+10h]
0x1800316e1  mov     rsi, [r11+28h]
0x1800316e5  mov     rsp, r11
0x1800316e8  pop     rdi
0x1800316e9  retn
```

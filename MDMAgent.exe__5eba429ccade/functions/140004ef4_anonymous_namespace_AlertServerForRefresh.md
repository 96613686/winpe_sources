# _anonymous_namespace_::AlertServerForRefresh

- ea: `0x140004ef4`
- end: `0x140004fb1`
- name: `_anonymous_namespace_::AlertServerForRefresh`
- size: `189`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x14000349c`
- `0x140004ef4`
- `0x140005ec0`
- `0x140006984`

## import_xrefs

- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x140004fa2`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x140004fa2`

## string_xrefs

- `0x140004f0d`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140004f3a`: `com.microsoft:mdm.refresh`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::AlertServerForRefresh(__int64 a1)
{
  char IsAutomaticRedeploymentBoot; // al
  const wchar_t *v4; // rcx
  _DWORD v5[2]; // [rsp+40h] [rbp-48h] BYREF
  const wchar_t *v6; // [rsp+48h] [rbp-40h]
  const wchar_t *v7; // [rsp+58h] [rbp-30h]
  int v8; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a1 )
  {
    memset_0(v5, 0, 0x40u);
    v5[0] = 64;
    v6 = L"com.microsoft:mdm.refresh";
    v5[1] = 1226;
    IsAutomaticRedeploymentBoot = anonymous_namespace_::IsAutomaticRedeploymentBoot();
    v4 = L"2";
    v8 = 0;
    if ( !IsAutomaticRedeploymentBoot )
      v4 = L"1";
    v7 = v4;
    return OmaDmInitiateSessionAsDevice(a1, 1, 2, v5, 1, 0, 9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140004ef4  push    rbx
0x140004ef6  sub     rsp, 80h
0x140004efd  mov     rbx, rcx
0x140004f00  test    rcx, rcx
0x140004f03  jnz     short loc_140004F2A
0x140004f05  mov     rcx, [rsp+88h]; this
0x140004f0d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140004f14  mov     ebx, 80070057h
0x140004f19  mov     edx, 0BFh; void *
0x140004f1e  mov     r9d, ebx; char *
0x140004f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004f26  mov     eax, ebx
0x140004f28  jmp     short loc_140004FA8
0x140004f2a  xor     edx, edx; Val
0x140004f2c  lea     rcx, [rsp+88h+var_48]; void *
0x140004f31  lea     r8d, [rdx+40h]; Size
0x140004f35  call    memset_0
0x140004f3a  lea     rax, aComMicrosoftMd; "com.microsoft:mdm.refresh"
0x140004f41  mov     [rsp+88h+var_48], 40h ; '@'
0x140004f49  mov     [rsp+88h+var_40], rax
0x140004f4e  mov     [rsp+88h+var_44], 4CAh
0x140004f56  call    _anonymous_namespace___IsAutomaticRedeploymentBoot
0x140004f5b  lea     rdx, a1; "1"
0x140004f62  mov     [rsp+88h+var_58], 9
0x140004f6a  test    al, al
0x140004f6c  mov     [rsp+88h+var_60], 0
0x140004f75  lea     rcx, a2; "2"
0x140004f7c  mov     [rsp+88h+var_28], 0
0x140004f84  cmovz   rcx, rdx
0x140004f88  lea     r9, [rsp+88h+var_48]
0x140004f8d  mov     edx, 1
0x140004f92  mov     [rsp+88h+var_30], rcx
0x140004f97  mov     rcx, rbx
0x140004f9a  mov     [rsp+88h+var_68], edx
0x140004f9e  lea     r8d, [rdx+1]
0x140004fa2  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x140004fa8  add     rsp, 80h
0x140004faf  pop     rbx
0x140004fb0  retn
```

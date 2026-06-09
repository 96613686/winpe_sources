# _anonymous_namespace_::AlertServerForRefresh

- ea: `0x140004fa8`
- end: `0x14000506f`
- name: `_anonymous_namespace_::AlertServerForRefresh`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x14000353c`
- `0x140004fa8`
- `0x1400060c8`
- `0x140006bf4`

## import_xrefs

- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x140005059`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x140005059`

## string_xrefs

- `0x140004fc1`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140004ff1`: `com.microsoft:mdm.refresh`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::AlertServerForRefresh(__int64 a1)
{
  bool IsAutomaticRedeploymentBoot; // al
  const wchar_t *v4; // rcx
  int v5; // [rsp+20h] [rbp-68h]
  _DWORD v6[2]; // [rsp+40h] [rbp-48h] BYREF
  const wchar_t *v7; // [rsp+48h] [rbp-40h]
  const wchar_t *v8; // [rsp+58h] [rbp-30h]
  int v9; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a1 )
  {
    memset_0(v6, 0, 0x40u);
    v6[0] = 64;
    v7 = L"com.microsoft:mdm.refresh";
    v6[1] = 1226;
    IsAutomaticRedeploymentBoot = anonymous_namespace_::IsAutomaticRedeploymentBoot();
    v4 = L"2";
    v9 = 0;
    if ( !IsAutomaticRedeploymentBoot )
      v4 = L"1";
    v8 = v4;
    return OmaDmInitiateSessionAsDevice(a1, 1, 2, v6, 1, 0, 9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140004fa8  push    rbx
0x140004faa  sub     rsp, 80h
0x140004fb1  mov     rbx, rcx
0x140004fb4  test    rcx, rcx
0x140004fb7  jnz     short loc_140004FE1
0x140004fb9  mov     rcx, [rsp+88h]; this
0x140004fc1  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140004fc8  mov     ebx, 80070057h
0x140004fcd  mov     edx, 0BFh; void *
0x140004fd2  mov     r9d, ebx; char *
0x140004fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004fda  mov     eax, ebx
0x140004fdc  jmp     loc_140005065
0x140004fe1  xor     edx, edx; Val
0x140004fe3  lea     rcx, [rsp+88h+var_48]; void *
0x140004fe8  lea     r8d, [rdx+40h]; Size
0x140004fec  call    memset_0
0x140004ff1  lea     rax, aComMicrosoftMd; "com.microsoft:mdm.refresh"
0x140004ff8  mov     [rsp+88h+var_48], 40h ; '@'
0x140005000  mov     [rsp+88h+var_40], rax
0x140005005  mov     [rsp+88h+var_44], 4CAh
0x14000500d  call    _anonymous_namespace___IsAutomaticRedeploymentBoot
0x140005012  lea     rdx, a1; "1"
0x140005019  mov     [rsp+88h+var_58], 9
0x140005021  test    al, al
0x140005023  mov     [rsp+88h+var_60], 0
0x14000502c  lea     rcx, a2; "2"
0x140005033  mov     [rsp+88h+var_28], 0
0x14000503b  cmovz   rcx, rdx
0x14000503f  lea     r9, [rsp+88h+var_48]
0x140005044  mov     edx, 1
0x140005049  mov     [rsp+88h+var_30], rcx
0x14000504e  mov     rcx, rbx
0x140005051  mov     [rsp+88h+var_68], edx
0x140005055  lea     r8d, [rdx+1]
0x140005059  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x140005060  nop     dword ptr [rax+rax+00h]
0x140005065  add     rsp, 80h
0x14000506c  pop     rbx
0x14000506d  retn
```

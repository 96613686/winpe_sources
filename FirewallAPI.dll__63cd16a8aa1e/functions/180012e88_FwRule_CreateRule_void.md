# FwRule::CreateRule(void)

- ea: `0x180012e88`
- end: `0x180012f32`
- name: `?CreateRule@FwRule@@AEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(FwRule *__hidden this)`
- caller_count: `40`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011c20`
- `0x180011e50`
- `0x180012030`
- `0x180012260`
- `0x180012440`
- `0x1800125a0`
- `0x180013230`
- `0x180013450`
- `0x180013860`
- `0x180013a90`
- `0x180013c80`
- `0x180015850`
- `0x180015a40`
- `0x180015cd0`
- `0x180016330`
- `0x1800176a0`
- `0x180018950`
- `0x180018be0`
- `0x180018ce0`
- `0x180018e00`
- `0x180019f20`
- `0x18001a8b0`
- `0x18001ba10`
- `0x18001bff0`
- `0x18001d8b0`
- `0x180020a00`
- `0x180020b00`
- `0x1800210f0`
- `0x18003e720`
- `0x18003eaa0`
- `0x18003ec90`
- `0x18003ee80`
- `0x18003f0b0`
- `0x18003f280`
- `0x18003f450`
- `0x18003f620`
- `0x18003f850`
- `0x18003fa20`
- `0x18003fc60`
- `0x18003fe30`

## callees

- `0x180012e88`
- `0x18003104c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180012f19`
- `fwbase!FwReportReturnError` at `0x180012f28`
- `fwbase!FwReportReturnError` at `0x180012f19`
- `fwbase!FwReportReturnError` at `0x180012f28`
- `FWPolicyIOMgr!CreateDefaultRule` at `0x180012eb1`
- `FWPolicyIOMgr!CreateDefaultRule` at `0x180012eb1`

## string_xrefs

- `0x180012f12`: `FwRule::CreateRule`
- `0x180012f21`: `FwRule::CreateRule`

## pseudocode

```c
__int64 __fastcall FwRule::CreateRule(FwRule *this)
{
  int DefaultRule; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  DefaultRule = CreateDefaultRule((char *)this + 80, 0x7FFFFFFF);
  v3 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    FwReportReturnError("FwRule::CreateRule", (unsigned int)DefaultRule);
    return (unsigned int)FwReportReturnError("FwRule::CreateRule", v3);
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 10) + 288LL) = 3;
    *(_WORD *)(*((_QWORD *)this + 10) + 292LL) &= ~1u;
    *(_DWORD *)(*((_QWORD *)this + 10) + 44LL) = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180012e88  mov     [rsp+arg_0], rbx
0x180012e8d  push    rdi
0x180012e8e  sub     rsp, 20h
0x180012e92  mov     rdi, rcx
0x180012e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e9c  lea     rax, WPP_GLOBAL_Control
0x180012ea3  cmp     rcx, rax
0x180012ea6  jnz     short loc_180012EF3
0x180012ea8  mov     edx, 7FFFFFFFh
0x180012ead  lea     rcx, [rdi+50h]
0x180012eb1  call    cs:__imp_?CreateDefaultRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180012eb7  mov     ebx, eax
0x180012eb9  test    eax, eax
0x180012ebb  js      short loc_180012F10
0x180012ebd  mov     rax, [rdi+50h]
0x180012ec1  mov     ecx, 0FFFEh
0x180012ec6  mov     dword ptr [rax+120h], 3
0x180012ed0  mov     rax, [rdi+50h]
0x180012ed4  and     [rax+124h], cx
0x180012edb  mov     rax, [rdi+50h]
0x180012edf  mov     dword ptr [rax+2Ch], 1
0x180012ee6  mov     eax, ebx
0x180012ee8  mov     rbx, [rsp+28h+arg_0]
0x180012eed  add     rsp, 20h
0x180012ef1  pop     rdi
0x180012ef2  retn
0x180012ef3  test    byte ptr [rcx+1Ch], 8
0x180012ef7  jz      short loc_180012EA8
0x180012ef9  mov     rcx, [rcx+10h]
0x180012efd  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180012f04  mov     edx, 5Dh ; ']'
0x180012f09  call    WPP_SF_
0x180012f0e  jmp     short loc_180012EA8
0x180012f10  mov     edx, ebx
0x180012f12  lea     rcx, aFwruleCreateru; "FwRule::CreateRule"
0x180012f19  call    cs:__imp_FwReportReturnError
0x180012f1f  mov     edx, ebx
0x180012f21  lea     rcx, aFwruleCreateru; "FwRule::CreateRule"
0x180012f28  call    cs:__imp_FwReportReturnError
0x180012f2e  mov     ebx, eax
0x180012f30  jmp     short loc_180012EE6
```

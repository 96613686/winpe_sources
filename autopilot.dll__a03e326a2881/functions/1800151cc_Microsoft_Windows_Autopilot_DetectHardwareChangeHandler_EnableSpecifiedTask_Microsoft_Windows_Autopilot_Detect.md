# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)

- ea: `0x1800151cc`
- end: `0x1800152b9`
- name: `?EnableSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@@Z`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017100`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013370`
- `0x180013a40`
- `0x180014da4`
- `0x1800151cc`
- `0x180015978`
- `0x1800174f0`
- `0x18001d634`

## string_xrefs

- `0x18001527b`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask()
{
  const wchar_t *TaskNameForType; // rax
  __int64 v1; // rcx
  __int64 v2; // r8
  unsigned int v3; // ebx
  char *v5; // [rsp+20h] [rbp-50h] BYREF
  const wchar_t *v6; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v7[2]; // [rsp+30h] [rbp-40h] BYREF
  char v8; // [rsp+40h] [rbp-30h]
  _OWORD v9[2]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  TaskNameForType = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType();
  v6 = TaskNameForType;
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v1, AutopilotDetectHardwareChangeTaskEnableStarted, TaskNameForType);
    TaskNameForType = v6;
  }
  LODWORD(v5) = -2147467263;
  v7[0] = &v5;
  v7[1] = &v6;
  v8 = 1;
  memset(v9, 0, sizeof(v9));
  v2 = -1;
  do
    ++v2;
  while ( TaskNameForType[v2] );
  std::wstring::_Construct<1,unsigned short const *>(v9, TaskNameForType, v2);
  LODWORD(v5) = Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(v9);
  std::wstring::_Tidy_deallocate(v9);
  v3 = (unsigned int)v5;
  if ( (int)v5 >= 0 )
    v3 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
      (const char *)(unsigned int)v5,
      (int)v5);
  wil::details::lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___::_lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___(v7);
  return v3;
}

```

## disassembly

```asm
0x1800151cc  mov     [rsp-8+arg_0], rbx
0x1800151d1  mov     [rsp-8+arg_8], rdi
0x1800151d6  push    rbp
0x1800151d7  mov     rbp, rsp
0x1800151da  sub     rsp, 70h
0x1800151de  mov     rax, cs:__security_cookie
0x1800151e5  xor     rax, rsp
0x1800151e8  mov     [rbp+var_8], rax
0x1800151ec  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x1800151f1  mov     [rbp+var_48], rax
0x1800151f5  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800151fc  jz      short loc_180015211
0x1800151fe  mov     r8, rax
0x180015201  lea     rdx, AutopilotDetectHardwareChangeTaskEnableStarted
0x180015208  call    McTemplateU0z_EventWriteTransfer
0x18001520d  mov     rax, [rbp+var_48]
0x180015211  mov     dword ptr [rbp+var_50], 80004001h
0x180015218  lea     rcx, [rbp+var_50]
0x18001521c  mov     [rbp+var_40], rcx
0x180015220  lea     rcx, [rbp+var_48]
0x180015224  mov     [rbp+var_38], rcx
0x180015228  mov     [rbp+var_30], 1
0x18001522c  xorps   xmm0, xmm0
0x18001522f  movups  [rbp+var_28], xmm0
0x180015233  xorps   xmm1, xmm1
0x180015236  movdqu  [rbp+var_18], xmm1
0x18001523b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001523f  xor     edi, edi
0x180015241  inc     r8
0x180015244  cmp     [rax+r8*2], di
0x180015249  jnz     short loc_180015241
0x18001524b  mov     rdx, rax
0x18001524e  lea     rcx, [rbp+var_28]
0x180015252  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180015257  nop
0x180015258  lea     rcx, [rbp+var_28]
0x18001525c  call    ?EnableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(std::wstring const &)
0x180015261  mov     dword ptr [rbp+var_50], eax
0x180015264  lea     rcx, [rbp+var_28]
0x180015268  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001526d  mov     ebx, dword ptr [rbp+var_50]
0x180015270  test    ebx, ebx
0x180015272  jns     short loc_18001528E
0x180015274  mov     rcx, [rbp+8]; this
0x180015278  mov     r9d, ebx; char *
0x18001527b  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015282  mov     edx, 0D2h; void *
0x180015287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001528c  jmp     short loc_180015290
0x18001528e  mov     ebx, edi
0x180015290  lea     rcx, [rbp+var_40]
0x180015294  call    wil__details__lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3______lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___
0x180015299  mov     eax, ebx
0x18001529b  mov     rcx, [rbp+var_8]
0x18001529f  xor     rcx, rsp; StackCookie
0x1800152a2  call    __security_check_cookie
0x1800152a7  lea     r11, [rsp+70h+var_s0]
0x1800152ac  mov     rbx, [r11+10h]
0x1800152b0  mov     rdi, [r11+18h]
0x1800152b4  mov     rsp, r11
0x1800152b7  pop     rbp
0x1800152b8  retn
```

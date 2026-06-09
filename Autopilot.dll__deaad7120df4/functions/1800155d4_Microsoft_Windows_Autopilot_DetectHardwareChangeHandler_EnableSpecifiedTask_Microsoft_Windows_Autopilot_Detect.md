# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)

- ea: `0x1800155d4`
- end: `0x1800156c2`
- name: `?EnableSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@@Z`
- size: `238`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017620`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013618`
- `0x180013de4`
- `0x18001519c`
- `0x1800155d4`
- `0x180015db4`
- `0x180017a20`
- `0x18001ddcc`

## string_xrefs

- `0x180015683`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask()
{
  __int64 TaskNameForType; // rax
  __int64 v1; // rcx
  __int64 v2; // r8
  unsigned int v3; // ebx
  char *v5; // [rsp+20h] [rbp-50h] BYREF
  __int64 v6; // [rsp+28h] [rbp-48h] BYREF
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
  while ( *(_WORD *)(TaskNameForType + 2 * v2) );
  std::wstring::_Construct<1,unsigned short const *>(v9, TaskNameForType);
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
0x1800155d4  mov     [rsp-8+arg_0], rbx
0x1800155d9  mov     [rsp-8+arg_8], rdi
0x1800155de  push    rbp
0x1800155df  mov     rbp, rsp
0x1800155e2  sub     rsp, 70h
0x1800155e6  mov     rax, cs:__security_cookie
0x1800155ed  xor     rax, rsp
0x1800155f0  mov     [rbp+var_8], rax
0x1800155f4  call    ?GetTaskNameForType@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@CAQEBGW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::GetTaskNameForType(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x1800155f9  mov     [rbp+var_48], rax
0x1800155fd  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180015604  jz      short loc_180015619
0x180015606  mov     r8, rax
0x180015609  lea     rdx, AutopilotDetectHardwareChangeTaskEnableStarted
0x180015610  call    McTemplateU0z_EventWriteTransfer
0x180015615  mov     rax, [rbp+var_48]
0x180015619  mov     dword ptr [rbp+var_50], 80004001h
0x180015620  lea     rcx, [rbp+var_50]
0x180015624  mov     [rbp+var_40], rcx
0x180015628  lea     rcx, [rbp+var_48]
0x18001562c  mov     [rbp+var_38], rcx
0x180015630  mov     [rbp+var_30], 1
0x180015634  xorps   xmm0, xmm0
0x180015637  movups  [rbp+var_28], xmm0
0x18001563b  xorps   xmm1, xmm1
0x18001563e  movdqu  [rbp+var_18], xmm1
0x180015643  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015647  xor     edi, edi
0x180015649  inc     r8
0x18001564c  cmp     [rax+r8*2], di
0x180015651  jnz     short loc_180015649
0x180015653  mov     rdx, rax
0x180015656  lea     rcx, [rbp+var_28]
0x18001565a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001565f  nop
0x180015660  lea     rcx, [rbp+var_28]
0x180015664  call    ?EnableNamedTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotTasks::EnableNamedTask(std::wstring const &)
0x180015669  mov     dword ptr [rbp+var_50], eax
0x18001566c  lea     rcx, [rbp+var_28]
0x180015670  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015675  mov     ebx, dword ptr [rbp+var_50]
0x180015678  test    ebx, ebx
0x18001567a  jns     short loc_180015696
0x18001567c  mov     rcx, [rbp+8]; this
0x180015680  mov     r9d, ebx; char *
0x180015683  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001568a  mov     edx, 0D2h; void *
0x18001568f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015694  jmp     short loc_180015698
0x180015696  mov     ebx, edi
0x180015698  lea     rcx, [rbp+var_40]
0x18001569c  call    wil__details__lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3______lambda_call__lambda_de5c2bf1323d93bf076ad149540127c3___
0x1800156a1  mov     eax, ebx
0x1800156a3  mov     rcx, [rbp+var_8]
0x1800156a7  xor     rcx, rsp; StackCookie
0x1800156aa  call    __security_check_cookie
0x1800156af  lea     r11, [rsp+70h+var_s0]
0x1800156b4  mov     rbx, [r11+10h]
0x1800156b8  mov     rdi, [r11+18h]
0x1800156bc  mov     rsp, r11
0x1800156bf  pop     rbp
0x1800156c0  retn
```

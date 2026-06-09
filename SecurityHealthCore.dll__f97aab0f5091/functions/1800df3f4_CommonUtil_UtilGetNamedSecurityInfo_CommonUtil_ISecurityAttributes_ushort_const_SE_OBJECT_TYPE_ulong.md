# CommonUtil::UtilGetNamedSecurityInfo(CommonUtil::ISecurityAttributes * *,ushort const *,_SE_OBJECT_TYPE,ulong)

- ea: `0x1800df3f4`
- end: `0x1800df596`
- name: `?UtilGetNamedSecurityInfo@CommonUtil@@YAJPEAPEAUISecurityAttributes@1@PEBGW4_SE_OBJECT_TYPE@@K@Z`
- size: `418`
- prototype: `int(CommonUtil *__hidden this, struct CommonUtil::ISecurityAttributes **, const unsigned __int16 *, enum _SE_OBJECT_TYPE, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010650`
- `0x1800cee78`

## callees

- `0x180004b64`
- `0x18000f058`
- `0x1800159a0`
- `0x1800de548`
- `0x1800de7c0`
- `0x1800df3f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800df4c4`
- `KERNEL32!LocalFree` at `0x1800df53b`
- `KERNEL32!LocalFree` at `0x1800df578`
- `KERNEL32!LocalFree` at `0x1800df4c4`
- `KERNEL32!LocalFree` at `0x1800df53b`
- `KERNEL32!LocalFree` at `0x1800df578`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800df46d`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800df46d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CommonUtil::UtilGetNamedSecurityInfo(
        CommonUtil *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        SECURITY_INFORMATION a4,
        unsigned int a5)
{
  int v5; // r14d
  signed int NamedSecurityInfoW; // eax
  unsigned int v8; // edi
  _QWORD *v10; // rdi
  CommonUtil *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // [rsp+0h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+48h] [rbp-40h] BYREF
  PACL v16; // [rsp+50h] [rbp-38h] BYREF
  PACL v17; // [rsp+58h] [rbp-30h] BYREF
  PSID v18; // [rsp+60h] [rbp-28h] BYREF
  PSID v19[2]; // [rsp+68h] [rbp-20h] BYREF
  const std::exception *v20; // [rsp+78h] [rbp-10h] BYREF

  v5 = (int)a2;
  hMem = 0;
  v19[0] = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_REGISTRY_KEY, a4, v19, &v18, &v17, &v16, &hMem);
  v8 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW )
  {
    if ( NamedSecurityInfoW > 0 )
      v8 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids,
        v5,
        v8);
    if ( hMem )
      LocalFree(hMem);
    return v8;
  }
  else
  {
    try
    {
      v15 = 0;
      v10 = operator new(0x40u);
      v19[1] = v10;
      CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(
        (CommonUtil::CSecurityAttributesHolder *)v10,
        hMem);
      *v10 = &CommonUtil::CSecurityAttributesAlloc<CommonUtil::CAutoLocalPtr<void *>>::`vftable';
      hMem = 0;
      CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::operator=(&v15, v10);
    }
    catch ( const std::exception *v20 )
    {
      CommonUtil::HrFromStdException(v11, (const struct std::exception *)&v13);
    }
    v12 = v15;
    v15 = 0;
    *(_QWORD *)this = v12;
    CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v15);
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x1800df3f4  mov     rax, rsp
0x1800df3f7  mov     [rax+10h], rsi
0x1800df3fb  mov     [rax+20h], rdi
0x1800df3ff  mov     [rax+18h], r8d
0x1800df403  mov     [rax+8], rcx
0x1800df407  push    r14
0x1800df409  sub     rsp, 80h
0x1800df410  mov     r8d, r9d; SecurityInfo
0x1800df413  mov     r14, rdx
0x1800df416  mov     rsi, rcx
0x1800df419  mov     qword ptr [rax-48h], 0
0x1800df421  mov     qword ptr [rax-20h], 0
0x1800df429  mov     qword ptr [rax-28h], 0
0x1800df431  mov     qword ptr [rax-30h], 0
0x1800df439  mov     qword ptr [rax-38h], 0
0x1800df441  lea     rcx, [rax-48h]
0x1800df445  mov     [rax-50h], rcx
0x1800df449  lea     rcx, [rax-38h]
0x1800df44d  mov     [rax-58h], rcx
0x1800df451  lea     rcx, [rax-30h]
0x1800df455  mov     [rax-60h], rcx
0x1800df459  lea     rcx, [rax-28h]
0x1800df45d  mov     [rax-68h], rcx
0x1800df461  lea     r9, [rax-20h]; ppsidOwner
0x1800df465  mov     edx, 4; ObjectType
0x1800df46a  mov     rcx, r14; pObjectName
0x1800df46d  call    cs:__imp_GetNamedSecurityInfoW
0x1800df473  mov     edi, eax
0x1800df475  test    eax, eax
0x1800df477  jz      short loc_1800DF4D1
0x1800df479  jle     short loc_1800DF484
0x1800df47b  movzx   edi, ax
0x1800df47e  or      edi, 80070000h
0x1800df484  lea     rax, WPP_GLOBAL_Control
0x1800df48b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800df492  cmp     rcx, rax
0x1800df495  jz      short loc_1800DF4BA
0x1800df497  test    byte ptr [rcx+1Ch], 1
0x1800df49b  jz      short loc_1800DF4BA
0x1800df49d  mov     edx, 14h
0x1800df4a2  mov     [rsp+88h+var_68], edi
0x1800df4a6  mov     r9, r14
0x1800df4a9  lea     r8, WPP_ee4acfd975e835558bdcbd8589408d45_Traceguids
0x1800df4b0  mov     rcx, [rcx+10h]
0x1800df4b4  call    WPP_SF_Sd
0x1800df4b9  nop
0x1800df4ba  mov     rcx, [rsp+88h+hMem]; hMem
0x1800df4bf  test    rcx, rcx
0x1800df4c2  jz      short loc_1800DF4CA
0x1800df4c4  call    cs:__imp_LocalFree
0x1800df4ca  mov     eax, edi
0x1800df4cc  jmp     loc_1800DF580
0x1800df4d1  mov     [rsp+88h+var_40], 0
0x1800df4da  mov     ecx, 40h ; '@'; Size
0x1800df4df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800df4e4  mov     rdi, rax
0x1800df4e7  mov     [rsp+88h+var_18], rax
0x1800df4ec  mov     rdx, [rsp+88h+hMem]; void *
0x1800df4f1  mov     rcx, rax; this
0x1800df4f4  call    ??0CSecurityAttributesHolder@CommonUtil@@IEAA@PEAX@Z; CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(void *)
0x1800df4f9  lea     rax, ??_7?$CSecurityAttributesAlloc@U?$CAutoLocalPtr@PEAX@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CSecurityAttributesAlloc<CommonUtil::CAutoLocalPtr<void *>>::`vftable'
0x1800df500  mov     [rdi], rax
0x1800df503  mov     [rsp+88h+hMem], 0
0x1800df50c  mov     rdx, rdi
0x1800df50f  lea     rcx, [rsp+88h+var_40]
0x1800df514  call    ??4?$AutoRef@UISecurityAttributes@CommonUtil@@@CommonUtil@@QEAAAEAV01@PEAUISecurityAttributes@1@@Z; CommonUtil::AutoRef<CommonUtil::ISecurityAttributes>::operator=(CommonUtil::ISecurityAttributes *)
0x1800df519  nop
0x1800df51a  jmp     short loc_1800DF552
0x1800df51c  cmp     [rsp+88h+arg_10], 0
0x1800df524  jge     short loc_1800DF54A
0x1800df526  lea     rcx, [rsp+88h+var_40]
0x1800df52b  call    ??1?$AutoRef@VUpdateMonitorTask@UpdateMonitor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(void)
0x1800df530  nop
0x1800df531  mov     rcx, [rsp+88h+hMem]; hMem
0x1800df536  test    rcx, rcx
0x1800df539  jz      short loc_1800DF541
0x1800df53b  call    cs:__imp_LocalFree
0x1800df541  mov     eax, [rsp+88h+arg_10]
0x1800df548  jmp     short loc_1800DF580
0x1800df54a  mov     rsi, [rsp+88h+arg_0]
0x1800df552  mov     rax, [rsp+88h+var_40]
0x1800df557  mov     [rsp+88h+var_40], 0
0x1800df560  mov     [rsi], rax
0x1800df563  lea     rcx, [rsp+88h+var_40]
0x1800df568  call    ??1?$AutoRef@VUpdateMonitorTask@UpdateMonitor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(void)
0x1800df56d  nop
0x1800df56e  mov     rcx, [rsp+88h+hMem]; hMem
0x1800df573  test    rcx, rcx
0x1800df576  jz      short loc_1800DF57E
0x1800df578  call    cs:__imp_LocalFree
0x1800df57e  xor     eax, eax
0x1800df580  lea     r11, [rsp+88h+var_8]
0x1800df588  mov     rsi, [r11+18h]
0x1800df58c  mov     rdi, [r11+28h]
0x1800df590  mov     rsp, r11
0x1800df593  pop     r14
0x1800df595  retn
```

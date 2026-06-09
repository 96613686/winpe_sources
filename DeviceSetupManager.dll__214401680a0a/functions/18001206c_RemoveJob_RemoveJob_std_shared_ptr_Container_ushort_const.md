# RemoveJob::RemoveJob(std::shared_ptr<Container>,ushort const *)

- ea: `0x18001206c`
- end: `0x18001223e`
- name: `??0RemoveJob@@QEAA@V?$shared_ptr@VContainer@@@std@@PEBG@Z`
- size: `466`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, const OLECHAR *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180032fcc`

## callees

- `0x18001206c`
- `0x18001370c`
- `0x180013864`
- `0x180013c1c`
- `0x180015eec`
- `0x1800179e8`
- `0x180017a10`
- `0x180018170`
- `0x1800181a8`
- `0x18001a6a8`
- `0x18001af70`
- `0x180032d80`
- `0x180032db8`
- `0x1800330e0`
- `0x180033148`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180012111`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180012111`

## string_xrefs

- `0x180012122`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
_QWORD *__fastcall RemoveJob::RemoveJob(_QWORD *a1, _QWORD *a2, const OLECHAR *a3, __int64 a4)
{
  __int64 v7; // rax
  _QWORD *v8; // r14
  HRESULT v9; // eax
  __int64 v10; // rcx
  __int64 *ContainerSetupRecorder; // rax
  __int64 v12; // r15
  std::_Ref_count_base *v13; // rbx
  __int64 ContainerSetupTask; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  std::_Ref_count_base *v17; // rcx
  _BYTE v19[8]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v20[8]; // [rsp+48h] [rbp-41h] BYREF
  std::_Ref_count_base *v21; // [rsp+50h] [rbp-39h]
  int v22; // [rsp+58h] [rbp-31h] BYREF
  _QWORD *v23; // [rsp+60h] [rbp-29h]
  _QWORD *v24; // [rsp+68h] [rbp-21h]
  __int64 v25; // [rsp+70h] [rbp-19h]
  std::_Ref_count_base *v26; // [rsp+78h] [rbp-11h]
  _BYTE v27[8]; // [rsp+80h] [rbp-9h] BYREF
  std::_Ref_count_base *v28; // [rsp+88h] [rbp-1h]
  GUID iid; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v23 = a1;
  v24 = a2;
  v7 = std::shared_ptr<Container>::shared_ptr<Container>(v20, a2, a3, a4);
  Job::Job(a1, v7, 1, 0);
  *a1 = &RemoveJob::`vftable';
  v8 = a1 + 16;
  a1[16] = 0;
  a1[17] = 0;
  a1[18] = 0;
  a1[19] = 0;
  iid = 0;
  v9 = IIDFromString(a3, &iid);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5FF,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)v9,
      (int)a3);
  v10 = *a2;
  v22 = *(_DWORD *)(*a2 + 44LL);
  v19[0] = *(_BYTE *)(v10 + 40);
  ContainerSetupRecorder = (__int64 *)Container::GetContainerSetupRecorder(v10, v27);
  v12 = *ContainerSetupRecorder;
  v25 = *ContainerSetupRecorder;
  v13 = (std::_Ref_count_base *)ContainerSetupRecorder[1];
  v26 = v13;
  *ContainerSetupRecorder = 0;
  ContainerSetupRecorder[1] = 0;
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  ContainerSetupTask = Container::GetContainerSetupTask(*a2, v20);
  std::shared_ptr<CDsmTask>::operator=(a1 + 16, ContainerSetupTask);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  v15 = std::make_unique<CDsmMetadataTask,_GUID &,enum DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &,0>(
          v20,
          &iid,
          &v22,
          v19,
          *v8,
          v12);
  std::unique_ptr<CDsmMetadataTask>::operator=<std::default_delete<CDsmMetadataTask>,0>(a1 + 18, v15);
  std::unique_ptr<CDsmMetadataTask>::~unique_ptr<CDsmMetadataTask>(v20);
  v16 = std::make_unique<CDsmDeviceTask,_GUID &,CDsmTask &,0>(v20, &iid, *v8);
  std::unique_ptr<CDsmDeviceTask>::operator=<std::default_delete<CDsmDeviceTask>,0>(a1 + 19, v16);
  std::unique_ptr<CDsmDeviceTask>::~unique_ptr<CDsmDeviceTask>(v20);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v17 = (std::_Ref_count_base *)a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return a1;
}

```

## disassembly

```asm
0x18001206c  mov     [rsp-8+arg_18], rbx
0x180012071  push    rbp
0x180012072  push    rsi
0x180012073  push    rdi
0x180012074  push    r12
0x180012076  push    r13
0x180012078  push    r14
0x18001207a  push    r15
0x18001207c  lea     rbp, [rsp-27h]
0x180012081  sub     rsp, 0B0h
0x180012088  mov     rax, cs:__security_cookie
0x18001208f  xor     rax, rsp
0x180012092  mov     [rbp+57h+var_40], rax
0x180012096  mov     rbx, r8
0x180012099  mov     rdi, rdx
0x18001209c  mov     rsi, rcx
0x18001209f  mov     [rbp+57h+var_80], rcx
0x1800120a3  mov     [rbp+57h+var_78], rdx
0x1800120a7  lea     rcx, [rbp+57h+var_98]
0x1800120ab  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x1800120b0  xor     r15d, r15d
0x1800120b3  mov     [rsp+0E0h+var_B0], r15
0x1800120b8  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x1800120bd  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x1800120c2  xor     r9d, r9d
0x1800120c5  lea     r8d, [r15+1]
0x1800120c9  mov     rdx, rax
0x1800120cc  mov     rcx, rsi
0x1800120cf  call    ??0Job@@QEAA@V?$shared_ptr@VContainer@@@std@@W4JobType@@W4JobObjectType@@PEBGW4JobAttributes@@3@Z; Job::Job(std::shared_ptr<Container>,JobType,JobObjectType,ushort const *,JobAttributes,ushort const *)
0x1800120d4  nop
0x1800120d5  lea     rax, ??_7RemoveJob@@6B@; const RemoveJob::`vftable'
0x1800120dc  mov     [rsi], rax
0x1800120df  lea     r14, [rsi+80h]
0x1800120e6  mov     [r14], r15
0x1800120e9  mov     [r14+8], r15
0x1800120ed  lea     r12, [rsi+90h]
0x1800120f4  mov     [r12], r15
0x1800120f8  lea     r13, [rsi+98h]
0x1800120ff  mov     [r13+0], r15
0x180012103  xorps   xmm0, xmm0
0x180012106  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18001210a  lea     rdx, [rbp+57h+iid]; lpiid
0x18001210e  mov     rcx, rbx; lpsz
0x180012111  call    cs:__imp_IIDFromString
0x180012117  mov     rcx, [rbp+5Fh]; this
0x18001211b  test    eax, eax
0x18001211d  jns     short loc_180012134
0x18001211f  mov     r9d, eax; char *
0x180012122  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180012129  mov     edx, 5FFh; void *
0x18001212e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012134  mov     rcx, [rdi]
0x180012137  mov     eax, [rcx+2Ch]
0x18001213a  mov     [rbp+57h+var_88], eax
0x18001213d  mov     al, [rcx+28h]
0x180012140  mov     [rbp+57h+var_A0], al
0x180012143  lea     rdx, [rbp+57h+var_60]
0x180012147  call    ?GetContainerSetupRecorder@Container@@QEAA?AV?$shared_ptr@VDsmSetupRecorder@@@std@@XZ; Container::GetContainerSetupRecorder(void)
0x18001214c  mov     r15, [rax]
0x18001214f  mov     [rbp+57h+var_70], r15
0x180012153  mov     rbx, [rax+8]
0x180012157  mov     [rbp+57h+var_68], rbx
0x18001215b  mov     qword ptr [rax], 0
0x180012162  mov     qword ptr [rax+8], 0
0x18001216a  mov     rcx, [rbp+57h+var_58]; this
0x18001216e  test    rcx, rcx
0x180012171  jz      short loc_180012178
0x180012173  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012178  lea     rdx, [rbp+57h+var_98]
0x18001217c  mov     rcx, [rdi]
0x18001217f  call    ?GetContainerSetupTask@Container@@QEAA?AV?$shared_ptr@VCDsmTask@@@std@@XZ; Container::GetContainerSetupTask(void)
0x180012184  mov     rdx, rax
0x180012187  mov     rcx, r14
0x18001218a  call    ??4?$shared_ptr@VCDsmTask@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CDsmTask>::operator=(std::shared_ptr<CDsmTask> &&)
0x18001218f  mov     rcx, [rbp+57h+var_90]; this
0x180012193  test    rcx, rcx
0x180012196  jz      short loc_18001219D
0x180012198  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001219d  mov     [rsp+0E0h+var_B8], r15
0x1800121a2  mov     rax, [r14]
0x1800121a5  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800121aa  lea     r9, [rbp+57h+var_A0]
0x1800121ae  lea     r8, [rbp+57h+var_88]
0x1800121b2  lea     rdx, [rbp+57h+iid]
0x1800121b6  lea     rcx, [rbp+57h+var_98]
0x1800121ba  call    ??$make_unique@VCDsmMetadataTask@@AEAU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEA_NAEAVCDsmTask@@AEAVDsmSetupRecorder@@$0A@@std@@YA?AV?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@0@AEAU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEA_NAEAVCDsmTask@@AEAVDsmSetupRecorder@@@Z; std::make_unique<CDsmMetadataTask,_GUID &,DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &,0>(_GUID &,DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &)
0x1800121bf  mov     rdx, rax
0x1800121c2  mov     rcx, r12
0x1800121c5  call    ??$?4U?$default_delete@VCDsmMetadataTask@@@std@@$0A@@?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CDsmMetadataTask>::operator=<std::default_delete<CDsmMetadataTask>,0>(std::unique_ptr<CDsmMetadataTask> &&)
0x1800121ca  lea     rcx, [rbp+57h+var_98]
0x1800121ce  call    ??1?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDsmMetadataTask>::~unique_ptr<CDsmMetadataTask>(void)
0x1800121d3  mov     r8, [r14]
0x1800121d6  lea     rdx, [rbp+57h+iid]
0x1800121da  lea     rcx, [rbp+57h+var_98]
0x1800121de  call    ??$make_unique@VCDsmDeviceTask@@AEAU_GUID@@AEAVCDsmTask@@$0A@@std@@YA?AV?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@0@AEAU_GUID@@AEAVCDsmTask@@@Z; std::make_unique<CDsmDeviceTask,_GUID &,CDsmTask &,0>(_GUID &,CDsmTask &)
0x1800121e3  mov     rdx, rax
0x1800121e6  mov     rcx, r13
0x1800121e9  call    ??$?4U?$default_delete@VCDsmDeviceTask@@@std@@$0A@@?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CDsmDeviceTask>::operator=<std::default_delete<CDsmDeviceTask>,0>(std::unique_ptr<CDsmDeviceTask> &&)
0x1800121ee  lea     rcx, [rbp+57h+var_98]
0x1800121f2  call    ??1?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDsmDeviceTask>::~unique_ptr<CDsmDeviceTask>(void)
0x1800121f7  nop
0x1800121f8  test    rbx, rbx
0x1800121fb  jz      short loc_180012206
0x1800121fd  mov     rcx, rbx; this
0x180012200  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012205  nop
0x180012206  mov     rcx, [rdi+8]; this
0x18001220a  test    rcx, rcx
0x18001220d  jz      short loc_180012214
0x18001220f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012214  mov     rax, rsi
0x180012217  mov     rcx, [rbp+57h+var_40]
0x18001221b  xor     rcx, rsp; StackCookie
0x18001221e  call    __security_check_cookie
0x180012223  mov     rbx, [rsp+0E0h+arg_18]
0x18001222b  add     rsp, 0B0h
0x180012232  pop     r15
0x180012234  pop     r14
0x180012236  pop     r13
0x180012238  pop     r12
0x18001223a  pop     rdi
0x18001223b  pop     rsi
0x18001223c  pop     rbp
0x18001223d  retn
```

# MetadataJob::MetadataJob(std::shared_ptr<Container>,ushort const *,JobAttributes,ushort const *)

- ea: `0x180014198`
- end: `0x1800143d9`
- name: `??0MetadataJob@@QEAA@V?$shared_ptr@VContainer@@@std@@PEBGW4JobAttributes@@1@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180032e8c`

## callees

- `0x18000e064`
- `0x18001370c`
- `0x180013864`
- `0x180013c1c`
- `0x180014198`
- `0x180015eec`
- `0x1800179e8`
- `0x180017a10`
- `0x180018170`
- `0x1800181a8`
- `0x18001a6a8`
- `0x18001a8ec`
- `0x18001af70`
- `0x180032d80`
- `0x180032db8`
- `0x1800330e0`
- `0x180033148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001432c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001432c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014342`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014239`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180014239`

## string_xrefs

- `0x18001424a`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x18001435f`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
MetadataJob *__fastcall MetadataJob::MetadataJob(
        MetadataJob *this,
        _QWORD *a2,
        const OLECHAR *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rax
  _QWORD *v9; // r15
  char *v10; // r12
  HRESULT v11; // eax
  __int64 v12; // rcx
  __int64 *ContainerSetupRecorder; // rax
  std::_Ref_count_base *v14; // rbx
  __int64 ContainerSetupTask; // rax
  __int64 v16; // rax
  __int64 v17; // rsi
  signed int LastError; // eax
  HANDLE EventW; // rax
  __int64 v20; // rax
  std::_Ref_count_base *v21; // rcx
  int v23[2]; // [rsp+20h] [rbp-81h]
  _BYTE v24[8]; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-59h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-51h]
  int v27; // [rsp+58h] [rbp-49h] BYREF
  MetadataJob *v28; // [rsp+60h] [rbp-41h]
  _QWORD *v29; // [rsp+68h] [rbp-39h]
  __int64 v30; // [rsp+70h] [rbp-31h]
  std::_Ref_count_base *v31; // [rsp+78h] [rbp-29h]
  _BYTE v32[8]; // [rsp+80h] [rbp-21h] BYREF
  std::_Ref_count_base *v33; // [rsp+88h] [rbp-19h]
  GUID iid; // [rsp+90h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v28 = this;
  v29 = a2;
  v8 = std::shared_ptr<Container>::shared_ptr<Container>(v25, a2);
  Job::Job(this, v8, 4);
  *(_QWORD *)this = &MetadataJob::`vftable';
  v9 = (_QWORD *)((char *)this + 128);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v10 = (char *)this + 144;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  iid = 0;
  v11 = IIDFromString(a3, &iid);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x448,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)v11,
      (int)a3);
  v12 = *a2;
  v27 = *(_DWORD *)(*a2 + 44LL);
  v24[0] = *(_BYTE *)(v12 + 40);
  ContainerSetupRecorder = (__int64 *)Container::GetContainerSetupRecorder(v12, v32);
  v30 = *ContainerSetupRecorder;
  v14 = (std::_Ref_count_base *)ContainerSetupRecorder[1];
  v31 = v14;
  *ContainerSetupRecorder = 0;
  ContainerSetupRecorder[1] = 0;
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  ContainerSetupTask = Container::GetContainerSetupTask(*a2, v25);
  std::shared_ptr<CDsmTask>::operator=((char *)this + 128, ContainerSetupTask);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  *(_QWORD *)v23 = *v9;
  v16 = std::make_unique<CDsmMetadataTask,_GUID &,enum DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &,0>(
          v25,
          &iid,
          &v27,
          v24);
  std::unique_ptr<CDsmMetadataTask>::operator=<std::default_delete<CDsmMetadataTask>,0>((char *)this + 144, v16);
  std::unique_ptr<CDsmMetadataTask>::~unique_ptr<CDsmMetadataTask>(v25);
  if ( !a5 )
    Job::_PopulateDefaultLanguages(this);
  v17 = *(_QWORD *)v10;
  LastError = CComPropVariant::Copy(
                (CComPropVariant *)(*(_QWORD *)v10 + 128LL),
                (const struct tagPROPVARIANT *)((char *)this + 80));
  if ( LastError >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)(v17 + 152) = EventW;
    if ( EventW )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)LastError,
      v23[0]);
  v20 = std::make_unique<CDsmDeviceTask,_GUID &,CDsmTask &,0>(v25, &iid, *v9);
  std::unique_ptr<CDsmDeviceTask>::operator=<std::default_delete<CDsmDeviceTask>,0>((char *)this + 152, v20);
  std::unique_ptr<CDsmDeviceTask>::~unique_ptr<CDsmDeviceTask>(v25);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  v21 = (std::_Ref_count_base *)a2[1];
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  return this;
}

```

## disassembly

```asm
0x180014198  push    rbp
0x18001419a  push    rbx
0x18001419b  push    rsi
0x18001419c  push    rdi
0x18001419d  push    r12
0x18001419f  push    r13
0x1800141a1  push    r14
0x1800141a3  push    r15
0x1800141a5  lea     rbp, [rsp-17h]
0x1800141aa  sub     rsp, 0B8h
0x1800141b1  mov     rax, cs:__security_cookie
0x1800141b8  xor     rax, rsp
0x1800141bb  mov     [rbp+4Fh+var_50], rax
0x1800141bf  mov     rbx, r8
0x1800141c2  mov     r14, rdx
0x1800141c5  mov     rdi, rcx
0x1800141c8  mov     [rbp+4Fh+var_90], rcx
0x1800141cc  mov     [rbp+4Fh+var_88], rdx
0x1800141d0  mov     r13, [rbp+4Fh+arg_20]
0x1800141d4  lea     rcx, [rbp+4Fh+var_A8]
0x1800141d8  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x1800141dd  mov     [rsp+0F0h+var_C0], r13
0x1800141e2  mov     dword ptr [rsp+0F0h+var_C8], r9d
0x1800141e7  mov     qword ptr [rsp+0F0h+var_D0], rbx; int
0x1800141ec  xor     r9d, r9d
0x1800141ef  lea     r8d, [r9+4]
0x1800141f3  mov     rdx, rax
0x1800141f6  mov     rcx, rdi
0x1800141f9  call    ??0Job@@QEAA@V?$shared_ptr@VContainer@@@std@@W4JobType@@W4JobObjectType@@PEBGW4JobAttributes@@3@Z; Job::Job(std::shared_ptr<Container>,JobType,JobObjectType,ushort const *,JobAttributes,ushort const *)
0x1800141fe  nop
0x1800141ff  lea     rax, ??_7MetadataJob@@6B@; const MetadataJob::`vftable'
0x180014206  mov     [rdi], rax
0x180014209  lea     r15, [rdi+80h]
0x180014210  xor     esi, esi
0x180014212  mov     [r15], rsi
0x180014215  mov     [r15+8], rsi
0x180014219  lea     r12, [rdi+90h]
0x180014220  mov     [r12], rsi
0x180014224  mov     [rdi+98h], rsi
0x18001422b  xorps   xmm0, xmm0
0x18001422e  movups  xmmword ptr [rbp+4Fh+iid.Data1], xmm0
0x180014232  lea     rdx, [rbp+4Fh+iid]; lpiid
0x180014236  mov     rcx, rbx; lpsz
0x180014239  call    cs:__imp_IIDFromString
0x18001423f  mov     rcx, [rbp+57h]; this
0x180014243  test    eax, eax
0x180014245  jns     short loc_18001425C
0x180014247  mov     r9d, eax; char *
0x18001424a  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180014251  mov     edx, 448h; void *
0x180014256  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001425c  mov     rcx, [r14]
0x18001425f  mov     eax, [rcx+2Ch]
0x180014262  mov     [rbp+4Fh+var_98], eax
0x180014265  mov     al, [rcx+28h]
0x180014268  mov     [rbp+4Fh+var_B0], al
0x18001426b  lea     rdx, [rbp+4Fh+var_70]
0x18001426f  call    ?GetContainerSetupRecorder@Container@@QEAA?AV?$shared_ptr@VDsmSetupRecorder@@@std@@XZ; Container::GetContainerSetupRecorder(void)
0x180014274  mov     rsi, [rax]
0x180014277  mov     [rbp+4Fh+var_80], rsi
0x18001427b  mov     rbx, [rax+8]
0x18001427f  mov     [rbp+4Fh+var_78], rbx
0x180014283  mov     qword ptr [rax], 0
0x18001428a  mov     qword ptr [rax+8], 0
0x180014292  mov     rcx, [rbp+4Fh+var_68]; this
0x180014296  test    rcx, rcx
0x180014299  jz      short loc_1800142A0
0x18001429b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800142a0  lea     rdx, [rbp+4Fh+var_A8]
0x1800142a4  mov     rcx, [r14]
0x1800142a7  call    ?GetContainerSetupTask@Container@@QEAA?AV?$shared_ptr@VCDsmTask@@@std@@XZ; Container::GetContainerSetupTask(void)
0x1800142ac  mov     rdx, rax
0x1800142af  mov     rcx, r15
0x1800142b2  call    ??4?$shared_ptr@VCDsmTask@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CDsmTask>::operator=(std::shared_ptr<CDsmTask> &&)
0x1800142b7  mov     rcx, [rbp+4Fh+var_A0]; this
0x1800142bb  test    rcx, rcx
0x1800142be  jz      short loc_1800142C5
0x1800142c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800142c5  mov     [rsp+0F0h+var_C8], rsi
0x1800142ca  mov     rax, [r15]
0x1800142cd  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x1800142d2  lea     r9, [rbp+4Fh+var_B0]
0x1800142d6  lea     r8, [rbp+4Fh+var_98]
0x1800142da  lea     rdx, [rbp+4Fh+iid]
0x1800142de  lea     rcx, [rbp+4Fh+var_A8]
0x1800142e2  call    ??$make_unique@VCDsmMetadataTask@@AEAU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEA_NAEAVCDsmTask@@AEAVDsmSetupRecorder@@$0A@@std@@YA?AV?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@0@AEAU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEA_NAEAVCDsmTask@@AEAVDsmSetupRecorder@@@Z; std::make_unique<CDsmMetadataTask,_GUID &,DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &,0>(_GUID &,DSM_INSTALL_BEHAVIOR_FLAGS &,bool &,CDsmTask &,DsmSetupRecorder &)
0x1800142e7  mov     rdx, rax
0x1800142ea  mov     rcx, r12
0x1800142ed  call    ??$?4U?$default_delete@VCDsmMetadataTask@@@std@@$0A@@?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CDsmMetadataTask>::operator=<std::default_delete<CDsmMetadataTask>,0>(std::unique_ptr<CDsmMetadataTask> &&)
0x1800142f2  lea     rcx, [rbp+4Fh+var_A8]
0x1800142f6  call    ??1?$unique_ptr@VCDsmMetadataTask@@U?$default_delete@VCDsmMetadataTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDsmMetadataTask>::~unique_ptr<CDsmMetadataTask>(void)
0x1800142fb  test    r13, r13
0x1800142fe  jnz     short loc_180014308
0x180014300  mov     rcx, rdi; this
0x180014303  call    ?_PopulateDefaultLanguages@Job@@IEAAXXZ; Job::_PopulateDefaultLanguages(void)
0x180014308  mov     rsi, [r12]
0x18001430c  lea     rdx, [rdi+50h]; struct tagPROPVARIANT *
0x180014310  lea     rcx, [rsi+80h]; this
0x180014317  call    ?Copy@CComPropVariant@@QEAAJAEBUtagPROPVARIANT@@@Z; CComPropVariant::Copy(tagPROPVARIANT const &)
0x18001431c  test    eax, eax
0x18001431e  js      short loc_180014354
0x180014320  xor     r9d, r9d; lpName
0x180014323  xor     r8d, r8d; bInitialState
0x180014326  lea     edx, [r9+1]; bManualReset
0x18001432a  xor     ecx, ecx; lpEventAttributes
0x18001432c  call    cs:__imp_CreateEventW
0x180014332  mov     [rsi+98h], rax
0x180014339  test    rax, rax
0x18001433c  jz      short loc_180014342
0x18001433e  xor     eax, eax
0x180014340  jmp     short loc_180014354
0x180014342  call    cs:__imp_GetLastError
0x180014348  test    eax, eax
0x18001434a  jle     short loc_180014354
0x18001434c  movzx   eax, ax
0x18001434f  or      eax, 80070000h
0x180014354  mov     rcx, [rbp+57h]; this
0x180014358  test    eax, eax
0x18001435a  jns     short loc_180014371
0x18001435c  mov     r9d, eax; char *
0x18001435f  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180014366  mov     edx, 45Ch; void *
0x18001436b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014371  mov     r8, [r15]
0x180014374  lea     rdx, [rbp+4Fh+iid]
0x180014378  lea     rcx, [rbp+4Fh+var_A8]
0x18001437c  call    ??$make_unique@VCDsmDeviceTask@@AEAU_GUID@@AEAVCDsmTask@@$0A@@std@@YA?AV?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@0@AEAU_GUID@@AEAVCDsmTask@@@Z; std::make_unique<CDsmDeviceTask,_GUID &,CDsmTask &,0>(_GUID &,CDsmTask &)
0x180014381  mov     rdx, rax
0x180014384  lea     rcx, [rdi+98h]
0x18001438b  call    ??$?4U?$default_delete@VCDsmDeviceTask@@@std@@$0A@@?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<CDsmDeviceTask>::operator=<std::default_delete<CDsmDeviceTask>,0>(std::unique_ptr<CDsmDeviceTask> &&)
0x180014390  lea     rcx, [rbp+4Fh+var_A8]
0x180014394  call    ??1?$unique_ptr@VCDsmDeviceTask@@U?$default_delete@VCDsmDeviceTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDsmDeviceTask>::~unique_ptr<CDsmDeviceTask>(void)
0x180014399  nop
0x18001439a  test    rbx, rbx
0x18001439d  jz      short loc_1800143A8
0x18001439f  mov     rcx, rbx; this
0x1800143a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800143a7  nop
0x1800143a8  mov     rcx, [r14+8]; this
0x1800143ac  test    rcx, rcx
0x1800143af  jz      short loc_1800143B6
0x1800143b1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800143b6  mov     rax, rdi
0x1800143b9  mov     rcx, [rbp+4Fh+var_50]
0x1800143bd  xor     rcx, rsp; StackCookie
0x1800143c0  call    __security_check_cookie
0x1800143c5  add     rsp, 0B8h
0x1800143cc  pop     r15
0x1800143ce  pop     r14
0x1800143d0  pop     r13
0x1800143d2  pop     r12
0x1800143d4  pop     rdi
0x1800143d5  pop     rsi
0x1800143d6  pop     rbx
0x1800143d7  pop     rbp
0x1800143d8  retn
```

# Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource::GetDiagnosticData(IStream * *)

- ea: `0x180104870`
- end: `0x180104962`
- name: `?GetDiagnosticData@EnrollmentDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@UEAAJPEAPEAUIStream@@@Z`
- size: `242`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f7f10`
- `0x1800f8680`
- `0x180104870`
- `0x180122018`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1801048a9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104901`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1801048a9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180104901`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104898`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180104898`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104914`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180104914`

## string_xrefs

- `0x1801048b6`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="OSDataEnrollments">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\OSData\Software\Microsoft\Enrollments\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>Altitude</Name>\n        <ValueRepresentation>Altitude</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>EnrollmentState</Name>\n        <ValueRepresentation>EnrollmentState</ValueRepresentat`
- `0x1801048af`: `<?xml version="1.0" encoding="utf-16"?>\n<DiagData>\n  <DataSource name="Enrollments">\n    <Key>\n      <Category>Enrollment</Category>\n      <Path>HKLM\Software\Microsoft\Enrollments\*</Path>\n      <Representation>EnrollmentId</Representation>\n      <Value>\n        <Name>Altitude</Name>\n        <ValueRepresentation>Altitude</ValueRepresentation>\n      </Value>\n      <Value>\n        <Name>EnrollmentState</Name>\n        <ValueRepresentation>EnrollmentState</ValueRepresentation>\n      <`
- `0x1801048f3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\enrollmentdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource::GetDiagnosticData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::EnrollmentDiagDataSource *this,
        struct IStream **a2)
{
  HRESULT StreamOnHGlobal; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  char IsStateSeparationEnabled; // al
  const BYTE *v7; // rdi
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  IStream *v10; // rax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IStream *v14; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 cbInit; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  cbInit = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a2);
  v4 = StreamOnHGlobal;
  if ( StreamOnHGlobal >= 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v7 = (const BYTE *)aXmlVersion10En_5;
    v8 = aXmlVersion10En_5;
    if ( !IsStateSeparationEnabled )
      v8 = (const wchar_t *)aXmlVersion10En_21;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    StreamOnHGlobal = ULongLongMult(v9 + 1, (unsigned __int64)v8, &cbInit);
    v4 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        v7 = aXmlVersion10En_21;
      v10 = SHCreateMemStream(v7, cbInit);
      Microsoft::WRL::ComPtr<IStream>::operator=(&v14, v10);
      StreamOnHGlobal = CreateDiagnosticData(v14, *a2);
      v4 = StreamOnHGlobal;
      if ( StreamOnHGlobal >= 0 )
      {
        v4 = 0;
        goto LABEL_15;
      }
      v5 = 55;
    }
    else
    {
      v5 = 50;
    }
  }
  else
  {
    v5 = 49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\enrollmentdiagdata.cpp",
    (const char *)(unsigned int)StreamOnHGlobal,
    v12);
LABEL_15:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v14);
  return v4;
}

```

## disassembly

```asm
0x180104870  mov     rax, rsp
0x180104873  mov     [rax+8], rbx
0x180104877  mov     [rax+10h], rbp
0x18010487b  push    rsi
0x18010487c  push    rdi
0x18010487d  push    r14; int
0x18010487f  sub     rsp, 20h
0x180104883  mov     rsi, rdx
0x180104886  xor     ebp, ebp
0x180104888  mov     [rax+18h], rbp
0x18010488c  mov     [rax+20h], rbp
0x180104890  mov     r8, rdx; ppstm
0x180104893  lea     edx, [rbp+1]; fDeleteOnRelease
0x180104896  xor     ecx, ecx; hGlobal
0x180104898  call    cs:__imp_CreateStreamOnHGlobal
0x18010489e  mov     ebx, eax
0x1801048a0  test    eax, eax
0x1801048a2  jns     short loc_1801048A9
0x1801048a4  lea     edx, [rbp+31h]
0x1801048a7  jmp     short loc_1801048EB
0x1801048a9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1801048af  lea     r14, aXmlVersion10En_21; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801048b6  lea     rdi, aXmlVersion10En_5; "<?xml version=\"1.0\" encoding=\"utf-16"...
0x1801048bd  mov     rdx, rdi
0x1801048c0  test    al, al
0x1801048c2  cmovz   rdx, r14; unsigned __int64
0x1801048c6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801048ca  inc     rcx
0x1801048cd  cmp     [rdx+rcx*2], bp
0x1801048d1  jnz     short loc_1801048CA
0x1801048d3  inc     rcx; unsigned __int64
0x1801048d6  lea     r8, [rsp+38h+cbInit]; unsigned __int64 *
0x1801048db  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801048e0  mov     ebx, eax
0x1801048e2  test    eax, eax
0x1801048e4  jns     short loc_180104901
0x1801048e6  mov     edx, 32h ; '2'; void *
0x1801048eb  mov     rcx, [rsp+38h]; this
0x1801048f0  mov     r9d, eax; char *
0x1801048f3  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801048fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801048ff  jmp     short loc_180104943
0x180104901  call    cs:__imp_RtlIsStateSeparationEnabled
0x180104907  test    al, al
0x180104909  cmovz   rdi, r14
0x18010490d  mov     edx, dword ptr [rsp+38h+cbInit]; cbInit
0x180104911  mov     rcx, rdi; pInit
0x180104914  call    cs:__imp_SHCreateMemStream
0x18010491a  mov     rdx, rax
0x18010491d  lea     rcx, [rsp+38h+arg_10]
0x180104922  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@PEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(IStream *)
0x180104927  mov     rdx, [rsi]; struct IStream *
0x18010492a  mov     rcx, [rsp+38h+arg_10]; struct IStream *
0x18010492f  call    ?CreateDiagnosticData@@YAJPEAUIStream@@0@Z; CreateDiagnosticData(IStream *,IStream *)
0x180104934  mov     ebx, eax
0x180104936  test    eax, eax
0x180104938  jns     short loc_180104941
0x18010493a  mov     edx, 37h ; '7'
0x18010493f  jmp     short loc_1801048EB
0x180104941  mov     ebx, ebp
0x180104943  lea     rcx, [rsp+38h+arg_10]
0x180104948  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010494d  mov     eax, ebx
0x18010494f  mov     rbx, [rsp+38h+arg_0]
0x180104954  mov     rbp, [rsp+38h+arg_8]
0x180104959  add     rsp, 20h
0x18010495d  pop     r14
0x18010495f  pop     rdi
0x180104960  pop     rsi
0x180104961  retn
```

# AnalysisThreadModelTypeFromName(char const *)

- ea: `0x18304f850`
- end: `0x18304f9b2`
- name: `?AnalysisThreadModelTypeFromName@@YA?AW4CxAnalysisThreadModel@@PEBD@Z`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x182dcc8c0`
- `0x18304f850`
- `0x183052e40`
- `0x183053010`
- `0x1830536a0`
- `0x1832ce3b0`

## string_xrefs

- `0x18304f91a`: `NoSpecialThreading`
- `0x18304f888`: `ReadAndProcess`
- `0x18304f8a1`: `readVsProcess`
- `0x18304f8ba`: `ComputeSummaries`
- `0x18304f8d3`: `readAndProcess`
- `0x18304f905`: `readThenProcess`
- `0x18304f944`: `UseDefaultThreadModel`
- `0x18304f96e`: `The specified threading sThreadModelName was not recognized. Valid sThreadModelNames are: 'None', 'ComputeSummaries', 'ReadAndProcess', 'Process', 'Default', or\n'NoSpecialThreading', 'ThreadComputeSummaries', 'ThreadReadAndProcess', 'ThreadProcessData', 'UseDefaultThreadModel'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AnalysisThreadModelTypeFromName(const char *a1)
{
  unsigned int v1; // ebx
  __int64 v3; // [rsp+28h] [rbp-20h] BYREF

  v3 = 0;
  CxString::CxString((CxString *)&v3, a1);
  v1 = 3;
  if ( !(unsigned __int8)operator==(&v3, "ReadAndProcess") && !(unsigned __int8)operator==(&v3, "readVsProcess") )
  {
    if ( (unsigned __int8)operator==(&v3, "ComputeSummaries") || (unsigned __int8)operator==(&v3, "readAndProcess") )
    {
      v1 = 1;
    }
    else if ( (unsigned __int8)operator==(&v3, "ProcessData") || (unsigned __int8)operator==(&v3, "readThenProcess") )
    {
      v1 = 2;
    }
    else if ( (unsigned __int8)operator==(&v3, "NoSpecialThreading") || (unsigned __int8)operator==(&v3, "none") )
    {
      v1 = 0;
    }
    else if ( (unsigned __int8)operator==(&v3, "UseDefaultThreadModel") || (unsigned __int8)operator==(&v3, "default") )
    {
      v1 = 4;
    }
    else
    {
      CxReportWarning(
        "The specified threading sThreadModelName was not recognized. Valid sThreadModelNames are: 'None', 'ComputeSummar"
        "ies', 'ReadAndProcess', 'Process', 'Default', or\n"
        "'NoSpecialThreading', 'ThreadComputeSummaries', 'ThreadReadAndProcess', 'ThreadProcessData', 'UseDefaultThreadModel'.");
    }
  }
  CxString::~CxString((CxString *)&v3);
  return v1;
}

```

## disassembly

```asm
0x18304f850  push    rbx
0x18304f852  sub     rsp, 40h
0x18304f856  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18304f85f  mov     rax, cs:__security_cookie
0x18304f866  xor     rax, rsp
0x18304f869  mov     [rsp+48h+var_18], rax
0x18304f86e  xor     eax, eax
0x18304f870  mov     [rsp+48h+var_20], rax
0x18304f875  mov     rdx, rcx; char *
0x18304f878  lea     rcx, [rsp+48h+var_20]; this
0x18304f87d  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x18304f882  nop
0x18304f883  mov     ebx, 3
0x18304f888  lea     rdx, aReadandprocess; "ReadAndProcess"
0x18304f88f  lea     rcx, [rsp+48h+var_20]
0x18304f894  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f899  test    al, al
0x18304f89b  jnz     loc_18304F993
0x18304f8a1  lea     rdx, aReadvsprocess; "readVsProcess"
0x18304f8a8  lea     rcx, [rsp+48h+var_20]
0x18304f8ad  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f8b2  test    al, al
0x18304f8b4  jnz     loc_18304F993
0x18304f8ba  lea     rdx, aComputesummari_2; "ComputeSummaries"
0x18304f8c1  lea     rcx, [rsp+48h+var_20]
0x18304f8c6  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f8cb  test    al, al
0x18304f8cd  jnz     loc_18304F98E
0x18304f8d3  lea     rdx, aReadandprocess_0; "readAndProcess"
0x18304f8da  lea     rcx, [rsp+48h+var_20]
0x18304f8df  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f8e4  test    al, al
0x18304f8e6  jnz     loc_18304F98E
0x18304f8ec  lea     rdx, aProcessdata; "ProcessData"
0x18304f8f3  lea     rcx, [rsp+48h+var_20]
0x18304f8f8  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f8fd  test    al, al
0x18304f8ff  jnz     loc_18304F987
0x18304f905  lea     rdx, aReadthenproces; "readThenProcess"
0x18304f90c  lea     rcx, [rsp+48h+var_20]
0x18304f911  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f916  test    al, al
0x18304f918  jnz     short loc_18304F987
0x18304f91a  lea     rdx, aNospecialthrea; "NoSpecialThreading"
0x18304f921  lea     rcx, [rsp+48h+var_20]
0x18304f926  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f92b  test    al, al
0x18304f92d  jnz     short loc_18304F983
0x18304f92f  lea     rdx, aNone_0; "none"
0x18304f936  lea     rcx, [rsp+48h+var_20]
0x18304f93b  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f940  test    al, al
0x18304f942  jnz     short loc_18304F983
0x18304f944  lea     rdx, aUsedefaultthre; "UseDefaultThreadModel"
0x18304f94b  lea     rcx, [rsp+48h+var_20]
0x18304f950  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f955  test    al, al
0x18304f957  jnz     short loc_18304F97C
0x18304f959  lea     rdx, aDefault; "default"
0x18304f960  lea     rcx, [rsp+48h+var_20]
0x18304f965  call    ??8@YA_NAEBVCxString@@PEBD@Z; operator==(CxString const &,char const *)
0x18304f96a  test    al, al
0x18304f96c  jnz     short loc_18304F97C
0x18304f96e  lea     rcx, aTheSpecifiedTh; "The specified threading sThreadModelNam"...
0x18304f975  call    ?CxReportWarning@@YAXPEBDZZ; CxReportWarning(char const *,...)
0x18304f97a  jmp     short loc_18304F993
0x18304f97c  mov     ebx, 4
0x18304f981  jmp     short loc_18304F993
0x18304f983  xor     ebx, ebx
0x18304f985  jmp     short loc_18304F993
0x18304f987  mov     ebx, 2
0x18304f98c  jmp     short loc_18304F993
0x18304f98e  mov     ebx, 1
0x18304f993  lea     rcx, [rsp+48h+var_20]; this
0x18304f998  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x18304f99d  mov     eax, ebx
0x18304f99f  mov     rcx, [rsp+48h+var_18]
0x18304f9a4  xor     rcx, rsp; StackCookie
0x18304f9a7  call    __security_check_cookie
0x18304f9ac  add     rsp, 40h
0x18304f9b0  pop     rbx
0x18304f9b1  retn
```

# ConnectToTaskScheduler

- ea: `0x180048920`
- end: `0x180048a3a`
- name: `ConnectToTaskScheduler`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047da0`

## callees

- `0x18000aa7c`
- `0x180047620`
- `0x180048920`
- `0x180050010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180048a1d`
- `OLEAUT32!__imp_VariantClear` at `0x180048a1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048968`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048968`

## string_xrefs

- `0x1800489dc`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall ConnectToTaskScheduler(LPVOID *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *); // rax
  LPVOID v7; // rcx
  int *ppv; // [rsp+20h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-49h] BYREF
  int v11[4]; // [rsp+50h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-19h]
  VARIANTARG v13; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v14; // [rsp+90h] [rbp+17h] BYREF
  VARIANTARG v15; // [rsp+B0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID v17; // [rsp+E0h] [rbp+67h] BYREF

  *a1 = 0;
  pvarg.vt = 0;
  v17 = 0;
  v2 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 31;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v2,
      (int)ppv);
    goto LABEL_10;
  }
  ppv = v11;
  *(_OWORD *)v11 = *(_OWORD *)&pvarg.vt;
  v5 = *(_QWORD *)v17;
  pRecInfo = pvarg.pRecInfo;
  v13 = pvarg;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(v5 + 80);
  v14 = pvarg;
  v15 = pvarg;
  v2 = v6(v17, &v15, &v14, &v13);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 32;
    goto LABEL_5;
  }
  v7 = v17;
  if ( v17 )
  {
    *a1 = v17;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 8LL))(v7);
  }
  else
  {
    *a1 = 0;
  }
  v3 = 0;
LABEL_10:
  wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v17);
  VariantClear(&pvarg);
  return v3;
}

```

## disassembly

```asm
0x180048920  mov     [rsp-8+arg_8], rbx
0x180048925  mov     [rsp-8+arg_10], rdi
0x18004892a  push    rbp
0x18004892b  lea     rbp, [rsp-57h]
0x180048930  sub     rsp, 0D0h
0x180048937  xor     eax, eax
0x180048939  mov     qword ptr [rcx], 0
0x180048940  xor     edx, edx; pUnkOuter
0x180048942  mov     word ptr [rbp+57h+pvarg], ax
0x180048946  mov     [rbp+57h+arg_0], rax
0x18004894a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180048951  mov     rdi, rcx
0x180048954  lea     rax, [rbp+57h+arg_0]
0x180048958  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x18004895f  mov     [rsp+0D0h+ppv], rax; ppv
0x180048964  lea     r8d, [rdx+1]; dwClsContext
0x180048968  call    cs:__imp_CoCreateInstance
0x18004896e  mov     ebx, eax
0x180048970  test    eax, eax
0x180048972  jns     short loc_18004897B
0x180048974  mov     edx, 1Fh
0x180048979  jmp     short loc_1800489D8
0x18004897b  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18004897f  lea     rdx, [rbp+57h+var_80]
0x180048983  mov     rcx, [rbp+57h+arg_0]
0x180048987  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18004898c  lea     r9, [rbp+57h+var_60]
0x180048990  mov     [rsp+0D0h+ppv], rdx; int
0x180048995  lea     r8, [rbp+57h+var_40]
0x180048999  lea     rdx, [rbp+57h+var_20]
0x18004899d  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x1800489a1  mov     rax, [rcx]
0x1800489a4  movsd   [rbp+57h+var_70], xmm0
0x1800489a9  movaps  [rbp+57h+var_60], xmm1
0x1800489ad  movsd   [rbp+57h+var_50], xmm0
0x1800489b2  mov     rax, [rax+50h]
0x1800489b6  movaps  [rbp+57h+var_40], xmm1
0x1800489ba  movsd   [rbp+57h+var_30], xmm0
0x1800489bf  movaps  [rbp+57h+var_20], xmm1
0x1800489c3  movsd   [rbp+57h+var_10], xmm0
0x1800489c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489cd  mov     ebx, eax
0x1800489cf  test    eax, eax
0x1800489d1  jns     short loc_1800489ED
0x1800489d3  mov     edx, 20h ; ' '; void *
0x1800489d8  mov     rcx, [rbp+5Fh]; this
0x1800489dc  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800489e3  mov     r9d, eax; char *
0x1800489e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800489eb  jmp     short loc_180048A10
0x1800489ed  mov     rcx, [rbp+57h+arg_0]
0x1800489f1  test    rcx, rcx
0x1800489f4  jz      short loc_180048A07
0x1800489f6  mov     [rdi], rcx
0x1800489f9  mov     rax, [rcx]
0x1800489fc  mov     rax, [rax+8]
0x180048a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a05  jmp     short loc_180048A0E
0x180048a07  mov     qword ptr [rdi], 0
0x180048a0e  xor     ebx, ebx
0x180048a10  lea     rcx, [rbp+57h+arg_0]
0x180048a14  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180048a19  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180048a1d  call    cs:__imp_VariantClear
0x180048a23  lea     r11, [rsp+0D0h+var_s0]
0x180048a2b  mov     eax, ebx
0x180048a2d  mov     rbx, [r11+18h]
0x180048a31  mov     rdi, [r11+20h]
0x180048a35  mov     rsp, r11
0x180048a38  pop     rbp
0x180048a39  retn
```

# Windows::Service::Task::TaskService(void)

- ea: `0x18005e98c`
- end: `0x18005eb4e`
- name: `?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `450`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005b6e4`
- `0x18005bbac`
- `0x18005cc28`
- `0x18005d944`

## callees

- `0x1800209fc`
- `0x18005e98c`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18005ea19`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea30`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea49`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea60`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea19`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea30`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea49`
- `OLEAUT32!__imp_VariantInit` at `0x18005ea60`
- `OLEAUT32!__imp_VariantClear` at `0x18005eaca`
- `OLEAUT32!__imp_VariantClear` at `0x18005ead6`
- `OLEAUT32!__imp_VariantClear` at `0x18005eae2`
- `OLEAUT32!__imp_VariantClear` at `0x18005eaed`
- `OLEAUT32!__imp_VariantClear` at `0x18005eaca`
- `OLEAUT32!__imp_VariantClear` at `0x18005ead6`
- `OLEAUT32!__imp_VariantClear` at `0x18005eae2`
- `OLEAUT32!__imp_VariantClear` at `0x18005eaed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e9f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005e9f6`

## string_xrefs

- `0x18005eb27`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005eb3c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LPVOID *__fastcall Windows::Service::Task::TaskService(LPVOID *a1)
{
  HRESULT Instance; // eax
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v5; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v7; // xmm8
  __int64 v8; // xmm9_8
  __int128 v9; // xmm6
  __int64 v10; // xmm7_8
  int v11; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  VARIANTARG v14; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG v15; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v16; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+80h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  int v19[4]; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v20; // [rsp+B8h] [rbp-50h]
  __int128 v21; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v22; // [rsp+D8h] [rbp-30h]
  __int128 v23; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-10h]
  __int128 v25; // [rsp+108h] [rbp+0h] BYREF
  __int64 v26; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+1B0h] [rbp+A8h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
  VariantInit(&pvarg);
  v5 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v16.decVal.8);
  v7 = *(_OWORD *)&v16.decVal.Lo32;
  v8 = v17;
  VariantInit((VARIANTARG *)&v15.decVal.8);
  v9 = *(_OWORD *)&v15.decVal.Lo32;
  v10 = *(_QWORD *)&v16.vt;
  VariantInit((VARIANTARG *)&v14.decVal.8);
  *(_OWORD *)v19 = v5;
  v20 = pRecInfo;
  v21 = v7;
  v22 = v8;
  v23 = v9;
  v24 = v10;
  v25 = *(_OWORD *)&v14.decVal.Lo32;
  v26 = *(_QWORD *)&v15.vt;
  v11 = v4(v3, &v25, &v23, &v21);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v11,
      (int)v19);
  VariantClear((VARIANTARG *)&v14.decVal.8);
  VariantClear((VARIANTARG *)&v15.decVal.8);
  VariantClear((VARIANTARG *)&v16.decVal.8);
  VariantClear(&pvarg);
  return a1;
}

```

## disassembly

```asm
0x18005e98c  mov     rax, rsp
0x18005e98f  mov     [rax+8], rcx
0x18005e993  push    rbp
0x18005e994  push    rbx
0x18005e995  push    rsi
0x18005e996  push    rdi
0x18005e997  lea     rbp, [rax-0A8h]
0x18005e99e  sub     rsp, 188h
0x18005e9a5  movaps  xmmword ptr [rax-38h], xmm6
0x18005e9a9  movaps  xmmword ptr [rax-48h], xmm7
0x18005e9ad  movaps  xmmword ptr [rax-58h], xmm8
0x18005e9b2  movaps  xmmword ptr [rax-68h], xmm9
0x18005e9b7  movaps  xmmword ptr [rax-78h], xmm10
0x18005e9bc  movaps  xmmword ptr [rax-88h], xmm11
0x18005e9c4  mov     rsi, rcx
0x18005e9c7  mov     dword ptr [rsp+1A0h+var_170], 0
0x18005e9cf  mov     r8d, 1; dwClsContext
0x18005e9d5  mov     dword ptr [rsp+1A0h+var_170], r8d
0x18005e9da  mov     qword ptr [rcx], 0
0x18005e9e1  mov     qword ptr [rsp+1A0h+ppv], rcx; int
0x18005e9e6  lea     r9, IID_ITaskService; riid
0x18005e9ed  xor     edx, edx; pUnkOuter
0x18005e9ef  lea     rcx, CLSID_TaskScheduler; rclsid
0x18005e9f6  call    cs:__imp_CoCreateInstance
0x18005e9fc  mov     rcx, [rbp+0A8h]; this
0x18005ea03  test    eax, eax
0x18005ea05  js      loc_18005EB39
0x18005ea0b  mov     rdi, [rsi]
0x18005ea0e  mov     rax, [rdi]
0x18005ea11  mov     rbx, [rax+50h]
0x18005ea15  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18005ea19  call    cs:__imp_VariantInit
0x18005ea1f  nop
0x18005ea20  movups  xmm10, xmmword ptr [rbp+0A0h+pvarg]
0x18005ea25  movsd   xmm11, qword ptr [rbp+0A0h+pvarg+10h]
0x18005ea2b  lea     rcx, [rsp+1A0h+var_140+8]; pvarg
0x18005ea30  call    cs:__imp_VariantInit
0x18005ea36  nop
0x18005ea37  movups  xmm8, xmmword ptr [rsp+1A0h+var_140+8]
0x18005ea3d  movsd   xmm9, [rsp+1A0h+var_128]
0x18005ea44  lea     rcx, [rsp+1A0h+var_158+8]; pvarg
0x18005ea49  call    cs:__imp_VariantInit
0x18005ea4f  nop
0x18005ea50  movups  xmm6, xmmword ptr [rsp+1A0h+var_158+8]
0x18005ea55  movsd   xmm7, qword ptr [rsp+1A0h+var_140]
0x18005ea5b  lea     rcx, [rsp+1A0h+var_170+8]; pvarg
0x18005ea60  call    cs:__imp_VariantInit
0x18005ea66  nop
0x18005ea67  movups  xmm0, xmmword ptr [rsp+1A0h+var_170+8]
0x18005ea6c  movsd   xmm1, qword ptr [rsp+1A0h+var_158]
0x18005ea72  movaps  xmmword ptr [rbp+0A0h+var_100], xmm10
0x18005ea77  movsd   [rbp+0A0h+var_F0], xmm11
0x18005ea7d  movaps  [rbp+0A0h+var_E0], xmm8
0x18005ea82  movsd   [rbp+0A0h+var_D0], xmm9
0x18005ea88  movaps  [rbp+0A0h+var_C0], xmm6
0x18005ea8c  movsd   [rbp+0A0h+var_B0], xmm7
0x18005ea91  movaps  [rbp+0A0h+var_A0], xmm0
0x18005ea95  movsd   [rbp+0A0h+var_90], xmm1
0x18005ea9a  lea     rax, [rbp+0A0h+var_100]
0x18005ea9e  mov     qword ptr [rsp+1A0h+ppv], rax; int
0x18005eaa3  lea     r9, [rbp+0A0h+var_E0]
0x18005eaa7  lea     r8, [rbp+0A0h+var_C0]
0x18005eaab  lea     rdx, [rbp+0A0h+var_A0]
0x18005eaaf  mov     rcx, rdi
0x18005eab2  mov     rax, rbx
0x18005eab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eaba  mov     rcx, [rbp+0A8h]; this
0x18005eac1  test    eax, eax
0x18005eac3  js      short loc_18005EB24
0x18005eac5  lea     rcx, [rsp+1A0h+var_170+8]; pvarg
0x18005eaca  call    cs:__imp_VariantClear
0x18005ead0  nop
0x18005ead1  lea     rcx, [rsp+1A0h+var_158+8]; pvarg
0x18005ead6  call    cs:__imp_VariantClear
0x18005eadc  nop
0x18005eadd  lea     rcx, [rsp+1A0h+var_140+8]; pvarg
0x18005eae2  call    cs:__imp_VariantClear
0x18005eae8  nop
0x18005eae9  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x18005eaed  call    cs:__imp_VariantClear
0x18005eaf3  mov     rax, rsi
0x18005eaf6  lea     r11, [rsp+1A0h+var_18]
0x18005eafe  movaps  xmm6, xmmword ptr [r11-18h]
0x18005eb03  movaps  xmm7, xmmword ptr [r11-28h]
0x18005eb08  movaps  xmm8, xmmword ptr [r11-38h]
0x18005eb0d  movaps  xmm9, xmmword ptr [r11-48h]
0x18005eb12  movaps  xmm10, xmmword ptr [r11-58h]
0x18005eb17  movaps  xmm11, xmmword ptr [r11-68h]
0x18005eb1c  mov     rsp, r11
0x18005eb1f  pop     rdi
0x18005eb20  pop     rsi
0x18005eb21  pop     rbx
0x18005eb22  pop     rbp
0x18005eb23  retn
0x18005eb24  mov     r9d, eax; char *
0x18005eb27  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005eb2e  mov     edx, 15h; void *
0x18005eb33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005eb39  mov     r9d, eax; char *
0x18005eb3c  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005eb43  mov     edx, 0Fh; void *
0x18005eb48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

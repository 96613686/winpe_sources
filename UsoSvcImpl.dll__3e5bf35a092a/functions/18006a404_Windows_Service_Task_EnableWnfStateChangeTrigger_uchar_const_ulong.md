# Windows::Service::Task::EnableWnfStateChangeTrigger(uchar const *,ulong)

- ea: `0x18006a404`
- end: `0x18006a725`
- name: `?EnableWnfStateChangeTrigger@Task@Service@Windows@@QEAAXPEBEK@Z`
- size: `801`
- prototype: `void(Windows::Service::Task *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c0a0`

## callees

- `0x1800112d0`
- `0x18006a404`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e5190`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18006a519`
- `OLEAUT32!__imp_VariantInit` at `0x18006a519`
- `OLEAUT32!__imp_VariantClear` at `0x18006a572`
- `OLEAUT32!__imp_VariantClear` at `0x18006a645`
- `OLEAUT32!__imp_VariantClear` at `0x18006a572`
- `OLEAUT32!__imp_VariantClear` at `0x18006a645`

## string_xrefs

- `0x18006a713`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x18006a680`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a695`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a6aa`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a6bf`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a6d4`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a6e9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x18006a6fe`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Service::Task::EnableWnfStateChangeTrigger(
        Windows::Service::Task *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v3; // rdi
  int v6; // eax
  int v7; // eax
  int i; // ebx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-50h] BYREF
  __int16 v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  int v19; // [rsp+48h] [rbp-28h] BYREF
  int v20; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 *v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v3 = a3;
  v21 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, &v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v6,
      *(int *)&pvarg.vt);
  v19 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v21 + 56))(v21, &v19);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v7,
      *(int *)&pvarg.vt);
  for ( i = 1; i <= v19; ++i )
  {
    v18 = 0;
    v9 = *v21;
    v18 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v9 + 64))(v21, (unsigned int)i, &v18);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v10,
        *(int *)&pvarg.vt);
    v20 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v20);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x147,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v11,
        *(int *)&pvarg.vt);
    if ( v20 == 12 )
    {
      v22 = 0;
      v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
              v18,
              &GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f,
              &v22);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C96,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v12,
          *(int *)&pvarg.vt);
      VariantInit(&pvarg);
      pvarg.vt = 27;
      v13 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v22 + 176LL))(v22, &pvarg.cyVal);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
          (const char *)(unsigned int)v13,
          *(int *)&pvarg.vt);
      if ( *pvarg.bstrVal == 1
        && *(_DWORD *)(pvarg.llVal + 24) == (_DWORD)v3
        && !memcmp(a2, *(const void **)(pvarg.llVal + 16), v3) )
      {
        v17 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v18 + 144LL))(v18, &v17);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
            (const char *)(unsigned int)v14,
            *(int *)&pvarg.vt);
        if ( !v17 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 152LL))(v18, 0xFFFFFFFFLL);
          if ( v15 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x157,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
              (const char *)(unsigned int)v15,
              *(int *)&pvarg.vt);
          *((_BYTE *)this + 40) = 1;
        }
        VariantClear(&pvarg);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        break;
      }
      VariantClear(&pvarg);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
}

```

## disassembly

```asm
0x18006a404  mov     [rsp-28h+arg_8], rbx
0x18006a409  mov     [rsp-28h+arg_10], rsi
0x18006a40e  push    rbp
0x18006a40f  push    rdi
0x18006a410  push    r12
0x18006a412  push    r14
0x18006a414  push    r15
0x18006a416  mov     rbp, rsp
0x18006a419  sub     rsp, 70h
0x18006a41d  mov     rax, cs:__security_cookie
0x18006a424  xor     rax, rsp
0x18006a427  mov     [rbp+var_10], rax
0x18006a42b  mov     edi, r8d
0x18006a42e  mov     r14, rdx
0x18006a431  mov     rsi, rcx
0x18006a434  xor     r15d, r15d
0x18006a437  mov     [rbp+var_20], r15
0x18006a43b  mov     rcx, [rcx]
0x18006a43e  mov     rax, [rcx]
0x18006a441  mov     [rbp+var_20], r15
0x18006a445  lea     rdx, [rbp+var_20]
0x18006a449  mov     rax, [rax+48h]
0x18006a44d  call    _guard_dispatch_icall
0x18006a452  mov     rcx, [rbp+28h]; this
0x18006a456  test    eax, eax
0x18006a458  js      loc_18006A6A7
0x18006a45e  mov     [rbp+var_28], r15d
0x18006a462  mov     rcx, [rbp+var_20]
0x18006a466  mov     rax, [rcx]
0x18006a469  lea     rdx, [rbp+var_28]
0x18006a46d  mov     rax, [rax+38h]
0x18006a471  call    _guard_dispatch_icall
0x18006a476  mov     rcx, [rbp+28h]; this
0x18006a47a  test    eax, eax
0x18006a47c  js      loc_18006A6BC
0x18006a482  lea     r12d, [r15+1]
0x18006a486  mov     ebx, r12d
0x18006a489  cmp     [rbp+var_28], r12d
0x18006a48d  jl      loc_18006A5B1
0x18006a493  mov     [rbp+var_30], r15
0x18006a497  mov     rcx, [rbp+var_20]
0x18006a49b  mov     rax, [rcx]
0x18006a49e  mov     [rbp+var_30], r15
0x18006a4a2  lea     r8, [rbp+var_30]
0x18006a4a6  mov     edx, ebx
0x18006a4a8  mov     rax, [rax+40h]
0x18006a4ac  call    _guard_dispatch_icall
0x18006a4b1  mov     rcx, [rbp+28h]; this
0x18006a4b5  test    eax, eax
0x18006a4b7  js      loc_18006A692
0x18006a4bd  mov     [rbp+var_24], r15d
0x18006a4c1  mov     rcx, [rbp+var_30]
0x18006a4c5  mov     rax, [rcx]
0x18006a4c8  lea     rdx, [rbp+var_24]
0x18006a4cc  mov     rax, [rax+38h]
0x18006a4d0  call    _guard_dispatch_icall
0x18006a4d5  mov     rcx, [rbp+28h]; this
0x18006a4d9  test    eax, eax
0x18006a4db  js      loc_18006A67D
0x18006a4e1  cmp     [rbp+var_24], 0Ch
0x18006a4e5  jnz     loc_18006A58F
0x18006a4eb  mov     rcx, [rbp+var_30]
0x18006a4ef  mov     [rbp+var_18], r15
0x18006a4f3  mov     rax, [rcx]
0x18006a4f6  lea     r8, [rbp+var_18]
0x18006a4fa  lea     rdx, _GUID_2d92bf38_0538_477b_b4d4_6c8e1dc9484f
0x18006a501  mov     rax, [rax]
0x18006a504  call    _guard_dispatch_icall
0x18006a509  mov     rcx, [rbp+28h]; this
0x18006a50d  test    eax, eax
0x18006a50f  js      loc_18006A710
0x18006a515  lea     rcx, [rbp+pvarg]; pvarg
0x18006a519  call    cs:__imp_VariantInit
0x18006a51f  nop
0x18006a520  mov     eax, 1Bh
0x18006a525  mov     word ptr [rbp+pvarg], ax
0x18006a529  mov     rcx, [rbp+var_18]
0x18006a52d  mov     rax, [rcx]
0x18006a530  lea     rdx, [rbp+pvarg+8]
0x18006a534  mov     rax, [rax+0B0h]
0x18006a53b  call    _guard_dispatch_icall
0x18006a540  mov     rcx, [rbp+28h]; this
0x18006a544  test    eax, eax
0x18006a546  js      loc_18006A6FB
0x18006a54c  mov     rdx, qword ptr [rbp+pvarg+8]
0x18006a550  cmp     [rdx], r12w
0x18006a554  jnz     short loc_18006A56E
0x18006a556  cmp     [rdx+18h], edi
0x18006a559  jnz     short loc_18006A56E
0x18006a55b  mov     r8, rdi; Size
0x18006a55e  mov     rdx, [rdx+10h]; Buf2
0x18006a562  mov     rcx, r14; Buf1
0x18006a565  call    memcmp
0x18006a56a  test    eax, eax
0x18006a56c  jz      short loc_18006A5EC
0x18006a56e  lea     rcx, [rbp+pvarg]; pvarg
0x18006a572  call    cs:__imp_VariantClear
0x18006a578  nop
0x18006a579  mov     rcx, [rbp+var_18]
0x18006a57d  test    rcx, rcx
0x18006a580  jz      short loc_18006A58F
0x18006a582  mov     rax, [rcx]
0x18006a585  mov     rax, [rax+10h]
0x18006a589  call    _guard_dispatch_icall
0x18006a58e  nop
0x18006a58f  mov     rcx, [rbp+var_30]
0x18006a593  test    rcx, rcx
0x18006a596  jz      short loc_18006A5A5
0x18006a598  mov     rax, [rcx]
0x18006a59b  mov     rax, [rax+10h]
0x18006a59f  call    _guard_dispatch_icall
0x18006a5a4  nop
0x18006a5a5  add     ebx, r12d
0x18006a5a8  cmp     ebx, [rbp+var_28]
0x18006a5ab  jle     loc_18006A493
0x18006a5b1  mov     rcx, [rbp+var_20]
0x18006a5b5  test    rcx, rcx
0x18006a5b8  jz      short loc_18006A5C7
0x18006a5ba  mov     rax, [rcx]
0x18006a5bd  mov     rax, [rax+10h]
0x18006a5c1  call    _guard_dispatch_icall
0x18006a5c6  nop
0x18006a5c7  mov     rcx, [rbp+var_10]
0x18006a5cb  xor     rcx, rsp; StackCookie
0x18006a5ce  call    __security_check_cookie
0x18006a5d3  lea     r11, [rsp+70h+var_s0]
0x18006a5d8  mov     rbx, [r11+38h]
0x18006a5dc  mov     rsi, [r11+40h]
0x18006a5e0  mov     rsp, r11
0x18006a5e3  pop     r15
0x18006a5e5  pop     r14
0x18006a5e7  pop     r12
0x18006a5e9  pop     rdi
0x18006a5ea  pop     rbp
0x18006a5eb  retn
0x18006a5ec  mov     [rbp+var_38], r15w
0x18006a5f1  mov     rcx, [rbp+var_30]
0x18006a5f5  mov     rax, [rcx]
0x18006a5f8  lea     rdx, [rbp+var_38]
0x18006a5fc  mov     rax, [rax+90h]
0x18006a603  call    _guard_dispatch_icall
0x18006a608  mov     rcx, [rbp+28h]; this
0x18006a60c  test    eax, eax
0x18006a60e  js      loc_18006A6D1
0x18006a614  cmp     [rbp+var_38], r15w
0x18006a619  jnz     short loc_18006A641
0x18006a61b  or      edx, 0FFFFFFFFh
0x18006a61e  mov     rcx, [rbp+var_30]
0x18006a622  mov     rax, [rcx]
0x18006a625  mov     rax, [rax+98h]
0x18006a62c  call    _guard_dispatch_icall
0x18006a631  mov     rcx, [rbp+28h]; this
0x18006a635  test    eax, eax
0x18006a637  js      loc_18006A6E6
0x18006a63d  mov     [rsi+28h], r12b
0x18006a641  lea     rcx, [rbp+pvarg]; pvarg
0x18006a645  call    cs:__imp_VariantClear
0x18006a64b  nop
0x18006a64c  mov     rcx, [rbp+var_18]
0x18006a650  test    rcx, rcx
0x18006a653  jz      short loc_18006A662
0x18006a655  mov     rax, [rcx]
0x18006a658  mov     rax, [rax+10h]
0x18006a65c  call    _guard_dispatch_icall
0x18006a661  nop
0x18006a662  mov     rcx, [rbp+var_30]
0x18006a666  test    rcx, rcx
0x18006a669  jz      short loc_18006A678
0x18006a66b  mov     rax, [rcx]
0x18006a66e  mov     rax, [rax+10h]
0x18006a672  call    _guard_dispatch_icall
0x18006a677  nop
0x18006a678  jmp     loc_18006A5B1
0x18006a67d  mov     r9d, eax; char *
0x18006a680  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a687  mov     edx, 147h; void *
0x18006a68c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a692  mov     r9d, eax; char *
0x18006a695  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a69c  mov     edx, 144h; void *
0x18006a6a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a6a7  mov     r9d, eax; char *
0x18006a6aa  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a6b1  mov     edx, 13Ch; void *
0x18006a6b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a6bc  mov     r9d, eax; char *
0x18006a6bf  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a6c6  mov     edx, 13Fh; void *
0x18006a6cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a6d1  mov     r9d, eax; char *
0x18006a6d4  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a6db  mov     edx, 154h; void *
0x18006a6e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a6e6  mov     r9d, eax; char *
0x18006a6e9  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a6f0  mov     edx, 157h; void *
0x18006a6f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a6fb  mov     r9d, eax; char *
0x18006a6fe  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006a705  mov     edx, 14Eh; void *
0x18006a70a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a710  mov     r9d, eax; char *
0x18006a713  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18006a71a  mov     edx, 1C96h; void *
0x18006a71f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

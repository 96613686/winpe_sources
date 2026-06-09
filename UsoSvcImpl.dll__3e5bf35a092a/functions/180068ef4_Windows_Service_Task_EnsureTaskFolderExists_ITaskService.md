# Windows::Service::Task::EnsureTaskFolderExists(ITaskService *)

- ea: `0x180068ef4`
- end: `0x1800690ca`
- name: `?EnsureTaskFolderExists@Task@Service@Windows@@CAXPEAUITaskService@@@Z`
- size: `470`
- prototype: `void __fastcall(struct ITaskService *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180069948`
- `0x18006a178`

## callees

- `0x1800112d0`
- `0x18002bbc0`
- `0x180041480`
- `0x180068ef4`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180068f35`
- `OLEAUT32!__imp_SysAllocString` at `0x180068f35`
- `OLEAUT32!__imp_SysFreeString` at `0x180069036`
- `OLEAUT32!__imp_SysFreeString` at `0x18006905c`
- `OLEAUT32!__imp_SysFreeString` at `0x180069036`
- `OLEAUT32!__imp_SysFreeString` at `0x18006905c`
- `OLEAUT32!__imp_VariantInit` at `0x180068f27`
- `OLEAUT32!__imp_VariantInit` at `0x180068f27`
- `OLEAUT32!__imp_VariantClear` at `0x180069067`
- `OLEAUT32!__imp_VariantClear` at `0x180069067`

## string_xrefs

- `0x1800690a3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180068fab`: `Microsoft\Windows\UpdateOrchestrator`
- `0x180069091`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1800690b8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Windows::Service::Task::EnsureTaskFolderExists(struct ITaskService *a1)
{
  BSTR v2; // rax
  const char *v3; // r9
  char v4; // bl
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v6; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-29h]
  VARIANTARG v10; // [rsp+40h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp+17h] BYREF
  __int64 v12; // [rsp+78h] [rbp+2Fh] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+37h] BYREF
  __int64 *v14; // [rsp+88h] [rbp+3Fh] BYREF
  BSTR v15; // [rsp+90h] [rbp+47h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  VariantInit(&pvarg);
  v2 = SysAllocString(L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)");
  v4 = 1;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  pvarg.llVal = (LONGLONG)v2;
  pvarg.vt = 8;
  v15 = 0;
  wil::make_bstr(&v15, L"\\");
  lpVtbl = a1->lpVtbl;
  v14 = 0;
  v6 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 **))lpVtbl->GetFolder)(a1, v15, &v14);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v6,
      v9);
  bstrString = 0;
  wil::make_bstr(&bstrString, L"Microsoft\\Windows\\UpdateOrchestrator");
  v12 = 0;
  v7 = *v14;
  v12 = 0;
  v10 = pvarg;
  v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, VARIANTARG *, __int64 *))(v7 + 88))(v14, bstrString, &v10, &v12);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024713 )
    v4 = 0;
  if ( v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)v8,
      v9);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  if ( v15 )
    SysFreeString(v15);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x180068ef4  mov     [rsp-8+arg_8], rbx
0x180068ef9  mov     [rsp-8+arg_10], rdi
0x180068efe  push    rbp
0x180068eff  lea     rbp, [rsp-57h]
0x180068f04  sub     rsp, 0A0h
0x180068f0b  mov     rax, cs:__security_cookie
0x180068f12  xor     rax, rsp
0x180068f15  mov     [rbp+57h+var_8], rax
0x180068f19  mov     rdi, rcx
0x180068f1c  mov     [rbp+57h+var_70], 0
0x180068f23  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180068f27  call    cs:__imp_VariantInit
0x180068f2d  nop
0x180068f2e  lea     rcx, psz; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x180068f35  call    cs:__imp_SysAllocString
0x180068f3b  mov     [rbp+57h+var_68], rax
0x180068f3f  mov     ebx, 1
0x180068f44  mov     [rbp+57h+var_70], ebx
0x180068f47  mov     rcx, [rbp+5Fh]; this
0x180068f4b  test    rax, rax
0x180068f4e  jz      loc_1800690A3
0x180068f54  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180068f58  lea     eax, [rbx+7]
0x180068f5b  mov     word ptr [rbp+57h+pvarg], ax
0x180068f5f  mov     [rbp+57h+var_10], 0
0x180068f67  lea     rdx, asc_180121108; "\\"
0x180068f6e  lea     rcx, [rbp+57h+var_10]
0x180068f72  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180068f77  nop
0x180068f78  mov     rax, [rdi]
0x180068f7b  mov     [rbp+57h+var_18], 0
0x180068f83  lea     r8, [rbp+57h+var_18]
0x180068f87  mov     rdx, [rbp+57h+var_10]
0x180068f8b  mov     rcx, rdi
0x180068f8e  mov     rax, [rax+38h]
0x180068f92  call    _guard_dispatch_icall
0x180068f97  mov     rcx, [rbp+5Fh]; this
0x180068f9b  test    eax, eax
0x180068f9d  js      loc_1800690B5
0x180068fa3  mov     [rbp+57h+bstrString], 0
0x180068fab  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x180068fb2  lea     rcx, [rbp+57h+bstrString]
0x180068fb6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x180068fbb  nop
0x180068fbc  mov     [rbp+57h+var_28], 0
0x180068fc4  mov     rcx, [rbp+57h+var_18]
0x180068fc8  mov     rax, [rcx]
0x180068fcb  mov     [rbp+57h+var_28], 0
0x180068fd3  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180068fd7  movaps  [rbp+57h+var_60], xmm0
0x180068fdb  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180068fe0  movsd   [rbp+57h+var_50], xmm1
0x180068fe5  lea     r9, [rbp+57h+var_28]
0x180068fe9  lea     r8, [rbp+57h+var_60]
0x180068fed  mov     rdx, [rbp+57h+bstrString]
0x180068ff1  mov     rax, [rax+58h]
0x180068ff5  call    _guard_dispatch_icall
0x180068ffa  mov     edx, 80000000h
0x180068fff  lea     ecx, [rax+rdx]
0x180069002  test    edx, ecx
0x180069004  jnz     short loc_18006900D
0x180069006  cmp     eax, 800700B7h
0x18006900b  jnz     short loc_18006900F
0x18006900d  xor     bl, bl
0x18006900f  mov     rcx, [rbp+5Fh]; this
0x180069013  test    bl, bl
0x180069015  jnz     short loc_18006908E
0x180069017  mov     rcx, [rbp+57h+var_28]
0x18006901b  test    rcx, rcx
0x18006901e  jz      short loc_18006902D
0x180069020  mov     rax, [rcx]
0x180069023  mov     rax, [rax+10h]
0x180069027  call    _guard_dispatch_icall
0x18006902c  nop
0x18006902d  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180069031  test    rcx, rcx
0x180069034  jz      short loc_18006903D
0x180069036  call    cs:__imp_SysFreeString
0x18006903c  nop
0x18006903d  mov     rcx, [rbp+57h+var_18]
0x180069041  test    rcx, rcx
0x180069044  jz      short loc_180069053
0x180069046  mov     rax, [rcx]
0x180069049  mov     rax, [rax+10h]
0x18006904d  call    _guard_dispatch_icall
0x180069052  nop
0x180069053  mov     rcx, [rbp+57h+var_10]; bstrString
0x180069057  test    rcx, rcx
0x18006905a  jz      short loc_180069063
0x18006905c  call    cs:__imp_SysFreeString
0x180069062  nop
0x180069063  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180069067  call    cs:__imp_VariantClear
0x18006906d  mov     rcx, [rbp+57h+var_8]
0x180069071  xor     rcx, rsp; StackCookie
0x180069074  call    __security_check_cookie
0x180069079  lea     r11, [rsp+0A0h+var_s0]
0x180069081  mov     rbx, [r11+18h]
0x180069085  mov     rdi, [r11+20h]
0x180069089  mov     rsp, r11
0x18006908c  pop     rbp
0x18006908d  retn
0x18006908e  mov     r9d, eax; char *
0x180069091  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180069098  mov     edx, 29h ; ')'; void *
0x18006909d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800690a3  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800690aa  mov     edx, 138Dh; void *
0x1800690af  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800690b5  mov     r9d, eax; char *
0x1800690b8  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800690bf  mov     edx, 23h ; '#'; void *
0x1800690c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

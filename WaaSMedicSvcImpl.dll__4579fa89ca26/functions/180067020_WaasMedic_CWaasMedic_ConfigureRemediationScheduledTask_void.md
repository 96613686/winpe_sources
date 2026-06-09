# WaasMedic::CWaasMedic::ConfigureRemediationScheduledTask(void)

- ea: `0x180067020`
- end: `0x18006713b`
- name: `?ConfigureRemediationScheduledTask@CWaasMedic@WaasMedic@@AEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(WaasMedic::CWaasMedic *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180068100`

## callees

- `0x18002e81c`
- `0x18002ff7c`
- `0x180032b08`
- `0x180032c94`
- `0x180032f6c`
- `0x1800639bc`
- `0x180067020`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180067033`
- `OLEAUT32!__imp_VariantInit` at `0x180067033`
- `OLEAUT32!__imp_VariantClear` at `0x18006711e`
- `OLEAUT32!__imp_VariantClear` at `0x18006711e`

## string_xrefs

- `0x180067086`: `MedicTaskProtected`
- `0x1800670d3`: `MedicTaskProtected`
- `0x180067067`: `Failed to initialize TasksHelper object! hr = 0x%08x`
- `0x1800670fe`: `Failed to enable %ws task! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CWaasMedic::ConfigureRemediationScheduledTask(WaasMedic::CWaasMedic *this)
{
  int v2; // eax
  int v3; // ebx
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  HRESULT v6; // eax
  LPVOID ppv[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v9 = 0;
  *(_OWORD *)ppv = 0;
  v2 = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\WaaSMedic");
  v3 = v2;
  if ( v2 < 0 )
  {
    LogLevelW(2u, L"Failed to initialize TasksHelper object! hr = 0x%08x", (unsigned int)v2);
    goto LABEL_9;
  }
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 3) + 16LL))(
         *((_QWORD *)this + 3),
         0,
         L"MedicTaskProtected",
         &pvarg) >= 0
    && !pvarg.vt )
  {
    v3 = WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(
           (WaasMedic::TasksHelper *)ppv,
           L"D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;;BA)");
    if ( v3 < 0 )
      goto LABEL_9;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 3) + 24LL))(
      *((_QWORD *)this + 3),
      0,
      L"MedicTaskProtected",
      &pvarg);
  }
  v5 = WaasMedic::TasksHelper::EnableTask((WaasMedic::TasksHelper *)ppv, v4);
  v3 = v5;
  if ( v5 < 0 )
    LogLevelW(2u, L"Failed to enable %ws task! hr = 0x%08x", L"PerformRemediation", (unsigned int)v5);
LABEL_9:
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  v6 = VariantClear(&pvarg);
  if ( v6 < 0 )
    _com_issue_error(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180067020  push    rbp
0x180067022  push    rbx
0x180067023  push    rsi
0x180067024  push    rdi
0x180067025  mov     rbp, rsp
0x180067028  sub     rsp, 68h
0x18006702c  mov     rdi, rcx
0x18006702f  lea     rcx, [rbp+pvarg]; pvarg
0x180067033  call    cs:__imp_VariantInit
0x180067039  nop
0x18006703a  xor     eax, eax
0x18006703c  mov     [rbp+var_28], rax
0x180067040  xorps   xmm1, xmm1
0x180067043  movdqu  xmmword ptr [rbp+ppv], xmm1
0x180067048  xor     esi, esi
0x18006704a  mov     word ptr [rbp+var_28], si
0x18006704e  lea     rdx, aMicrosoftWindo_4; "Microsoft\\Windows\\WaaSMedic"
0x180067055  lea     rcx, [rbp+ppv]; ppv
0x180067059  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x18006705e  mov     ebx, eax
0x180067060  test    eax, eax
0x180067062  jns     short loc_18006707B
0x180067064  mov     r8d, eax
0x180067067  lea     rdx, aFailedToInitia_3; "Failed to initialize TasksHelper object"...
0x18006706e  lea     ecx, [rsi+2]; unsigned __int8
0x180067071  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180067076  jmp     loc_180067110
0x18006707b  mov     rcx, [rdi+18h]
0x18006707f  mov     rax, [rcx]
0x180067082  lea     r9, [rbp+pvarg]
0x180067086  lea     r8, aMedictaskprote; "MedicTaskProtected"
0x18006708d  xor     edx, edx
0x18006708f  mov     rax, [rax+10h]
0x180067093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067098  test    eax, eax
0x18006709a  js      short loc_1800670E5
0x18006709c  cmp     word ptr [rbp+pvarg], si
0x1800670a0  jnz     short loc_1800670E5
0x1800670a2  lea     rdx, aDPAFaSyAFrfxLs_0; "D:P(A;;FA;;;SY)(A;;FRFX;;;LS)(A;;FRFX;;"...
0x1800670a9  lea     rcx, [rbp+ppv]; this
0x1800670ad  call    ?SetTaskFolderSecurityDescriptor@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::SetTaskFolderSecurityDescriptor(ushort const *)
0x1800670b2  mov     ebx, eax
0x1800670b4  test    eax, eax
0x1800670b6  js      short loc_180067110
0x1800670b8  mov     eax, 0Bh
0x1800670bd  mov     word ptr [rbp+pvarg], ax
0x1800670c1  or      eax, 0FFFFFFFFh
0x1800670c4  mov     word ptr [rbp+pvarg+8], ax
0x1800670c8  mov     rcx, [rdi+18h]
0x1800670cc  mov     rax, [rcx]
0x1800670cf  lea     r9, [rbp+pvarg]
0x1800670d3  lea     r8, aMedictaskprote; "MedicTaskProtected"
0x1800670da  xor     edx, edx
0x1800670dc  mov     rax, [rax+18h]
0x1800670e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670e5  lea     rcx, [rbp+ppv]; this
0x1800670e9  call    ?EnableTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::EnableTask(ushort const *)
0x1800670ee  mov     ebx, eax
0x1800670f0  test    eax, eax
0x1800670f2  jns     short loc_180067110
0x1800670f4  mov     r9d, eax
0x1800670f7  lea     r8, aPerformremedia; "PerformRemediation"
0x1800670fe  lea     rdx, aFailedToEnable_1; "Failed to enable %ws task! hr = 0x%08x"
0x180067105  mov     ecx, 2; unsigned __int8
0x18006710a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18006710f  nop
0x180067110  lea     rcx, [rbp+ppv]; this
0x180067114  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x180067119  nop
0x18006711a  lea     rcx, [rbp+pvarg]; pvarg
0x18006711e  call    cs:__imp_VariantClear
0x180067124  test    eax, eax
0x180067126  js      short loc_180067133
0x180067128  mov     eax, ebx
0x18006712a  add     rsp, 68h
0x18006712e  pop     rdi
0x18006712f  pop     rsi
0x180067130  pop     rbx
0x180067131  pop     rbp
0x180067132  retn
0x180067133  mov     ecx, eax; int
0x180067135  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

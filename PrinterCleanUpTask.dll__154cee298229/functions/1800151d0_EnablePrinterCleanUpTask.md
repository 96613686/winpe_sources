# EnablePrinterCleanUpTask

- ea: `0x1800151d0`
- end: `0x1800153f3`
- name: `EnablePrinterCleanUpTask`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011d8c`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180008b30`
- `0x180010438`
- `0x1800151d0`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180015223`
- `OLEAUT32!__imp_VariantInit` at `0x180015223`
- `OLEAUT32!__imp_VariantClear` at `0x1800153b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800153b8`

## string_xrefs

- `0x180015322`: `PrinterCleanupTask`
- `0x1800152b5`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x1800152fb`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x180015341`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x18001537b`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall EnablePrinterCleanUpTask(unsigned __int8 a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  __int64 v7; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+40h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B0h] BYREF
  VARIANTARG v11; // [rsp+60h] [rbp-98h] BYREF
  VARIANTARG v12; // [rsp+80h] [rbp-78h] BYREF
  VARIANTARG v13; // [rsp+A0h] [rbp-58h] BYREF
  VARIANTARG v14; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)&v14.vt = 0x4CFCA4E50F87369FLL;
  v14.llVal = 0xDD724515E6733EBDuLL;
  winrt::create_instance<ITaskService>(&v9, &v14);
  VariantInit(&pvarg);
  v14 = pvarg;
  v11 = pvarg;
  v12 = pvarg;
  v13 = pvarg;
  v2 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v9 + 80LL))(
         v9,
         &v13,
         &v12,
         &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v2,
      (int)&v14);
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v9 + 56LL))(
         v9,
         L"\\Microsoft\\Windows\\Printing",
         &v8);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v3,
      (int)&v14);
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 104LL))(
         v8,
         L"PrinterCleanupTask",
         &v7);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v4,
      (int)&v14);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 88LL))(v7, (unsigned __int16)((a1 ^ 1) - 1));
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
      (const char *)(unsigned int)v5,
      (int)&v14);
  if ( v7 )
    winrt::com_ptr<ITaskService>::unconditional_release_ref(&v7);
  if ( v8 )
    winrt::com_ptr<ITaskService>::unconditional_release_ref(&v8);
  VariantClear(&pvarg);
  if ( v9 )
    winrt::com_ptr<ITaskService>::unconditional_release_ref(&v9);
  return 0;
}

```

## disassembly

```asm
0x1800151d0  mov     r11, rsp
0x1800151d3  push    rbx
0x1800151d4  sub     rsp, 0F0h
0x1800151db  mov     rax, cs:__security_cookie
0x1800151e2  xor     rax, rsp
0x1800151e5  mov     [rsp+0F8h+var_18], rax
0x1800151ed  mov     bl, cl
0x1800151ef  mov     dword ptr [r11-38h], 0F87369Fh
0x1800151f7  mov     dword ptr [r11-34h], 4CFCA4E5h
0x1800151ff  mov     dword ptr [r11-30h], 0E6733EBDh
0x180015207  mov     dword ptr [r11-2Ch], 0DD724515h
0x18001520f  lea     rdx, [r11-38h]
0x180015213  lea     rcx, [rsp+0F8h+var_B8]
0x180015218  call    ??$create_instance@UITaskService@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x18001521d  nop
0x18001521e  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180015223  call    cs:__imp_VariantInit
0x180015229  nop
0x18001522a  mov     rcx, [rsp+0F8h+var_B8]
0x18001522f  movups  xmm1, xmmword ptr [rsp+0F8h+pvarg]
0x180015234  movsd   xmm0, qword ptr [rsp+0F8h+pvarg+10h]
0x18001523a  movaps  xmmword ptr [rsp+0F8h+var_38], xmm1
0x180015242  movsd   [rsp+0F8h+var_28], xmm0
0x18001524b  movaps  [rsp+0F8h+var_98], xmm1
0x180015250  movsd   [rsp+0F8h+var_88], xmm0
0x180015256  movaps  [rsp+0F8h+var_78], xmm1
0x18001525e  movsd   [rsp+0F8h+var_68], xmm0
0x180015267  movaps  [rsp+0F8h+var_58], xmm1
0x18001526f  movsd   [rsp+0F8h+var_48], xmm0
0x180015278  mov     rax, [rcx]
0x18001527b  lea     rdx, [rsp+0F8h+var_38]
0x180015283  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180015288  lea     r9, [rsp+0F8h+var_98]
0x18001528d  lea     r8, [rsp+0F8h+var_78]
0x180015295  lea     rdx, [rsp+0F8h+var_58]
0x18001529d  mov     rax, [rax+50h]
0x1800152a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a6  mov     rcx, [rsp+0F8h]; this
0x1800152ae  test    eax, eax
0x1800152b0  jns     short loc_1800152C6
0x1800152b2  mov     r9d, eax; char *
0x1800152b5  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800152bc  mov     edx, 157h; void *
0x1800152c1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800152c6  mov     [rsp+0F8h+var_C0], 0
0x1800152cf  mov     rcx, [rsp+0F8h+var_B8]
0x1800152d4  mov     rax, [rcx]
0x1800152d7  lea     r8, [rsp+0F8h+var_C0]
0x1800152dc  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Printing"
0x1800152e3  mov     rax, [rax+38h]
0x1800152e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ec  mov     rcx, [rsp+0F8h]; this
0x1800152f4  test    eax, eax
0x1800152f6  jns     short loc_18001530C
0x1800152f8  mov     r9d, eax; char *
0x1800152fb  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015302  mov     edx, 15Ah; void *
0x180015307  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001530c  mov     [rsp+0F8h+var_C8], 0
0x180015315  mov     rcx, [rsp+0F8h+var_C0]
0x18001531a  mov     rax, [rcx]
0x18001531d  lea     r8, [rsp+0F8h+var_C8]
0x180015322  lea     rdx, aPrintercleanup_1; "PrinterCleanupTask"
0x180015329  mov     rax, [rax+68h]
0x18001532d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015332  mov     rcx, [rsp+0F8h]; this
0x18001533a  test    eax, eax
0x18001533c  jns     short loc_180015352
0x18001533e  mov     r9d, eax; char *
0x180015341  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015348  mov     edx, 15Dh; void *
0x18001534d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015352  mov     rcx, [rsp+0F8h+var_C8]
0x180015357  mov     rax, [rcx]
0x18001535a  xor     bl, 1
0x18001535d  movzx   edx, bl
0x180015360  dec     dx
0x180015363  mov     rax, [rax+58h]
0x180015367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001536c  mov     rcx, [rsp+0F8h]; this
0x180015374  test    eax, eax
0x180015376  jns     short loc_18001538D
0x180015378  mov     r9d, eax; char *
0x18001537b  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180015382  mov     edx, 15Eh; void *
0x180015387  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001538d  cmp     [rsp+0F8h+var_C8], 0
0x180015393  jz      short loc_1800153A0
0x180015395  lea     rcx, [rsp+0F8h+var_C8]
0x18001539a  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x18001539f  nop
0x1800153a0  cmp     [rsp+0F8h+var_C0], 0
0x1800153a6  jz      short loc_1800153B3
0x1800153a8  lea     rcx, [rsp+0F8h+var_C0]
0x1800153ad  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x1800153b2  nop
0x1800153b3  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800153b8  call    cs:__imp_VariantClear
0x1800153be  nop
0x1800153bf  cmp     [rsp+0F8h+var_B8], 0
0x1800153c5  jz      short loc_1800153D1
0x1800153c7  lea     rcx, [rsp+0F8h+var_B8]
0x1800153cc  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x1800153d1  xor     eax, eax
0x1800153d3  jmp     short loc_1800153D9
0x1800153d5  mov     eax, dword ptr [rsp+0F8h+var_C8]
0x1800153d9  mov     rcx, [rsp+0F8h+var_18]
0x1800153e1  xor     rcx, rsp; StackCookie
0x1800153e4  call    __security_check_cookie
0x1800153e9  add     rsp, 0F0h
0x1800153f0  pop     rbx
0x1800153f1  retn
```

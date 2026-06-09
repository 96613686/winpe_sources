# EnablePrintJobCleanupTask

- ea: `0x180010470`
- end: `0x180010693`
- name: `EnablePrintJobCleanupTask`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aeb4`
- `0x18000eee4`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180008b30`
- `0x180010438`
- `0x180010470`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800104c3`
- `OLEAUT32!__imp_VariantInit` at `0x1800104c3`
- `OLEAUT32!__imp_VariantClear` at `0x180010658`
- `OLEAUT32!__imp_VariantClear` at `0x180010658`

## string_xrefs

- `0x1800105c2`: `PrintJobCleanupTask`
- `0x180010555`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18001059b`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x1800105e1`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18001061b`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall EnablePrintJobCleanupTask(unsigned __int8 a1)
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
      (void *)0x16A,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
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
      (void *)0x16D,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)(unsigned int)v3,
      (int)&v14);
  v7 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v8 + 104LL))(
         v8,
         L"PrintJobCleanupTask",
         &v7);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)(unsigned int)v4,
      (int)&v14);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 88LL))(v7, (unsigned __int16)((a1 ^ 1) - 1));
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
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
0x180010470  mov     r11, rsp
0x180010473  push    rbx
0x180010474  sub     rsp, 0F0h
0x18001047b  mov     rax, cs:__security_cookie
0x180010482  xor     rax, rsp
0x180010485  mov     [rsp+0F8h+var_18], rax
0x18001048d  mov     bl, cl
0x18001048f  mov     dword ptr [r11-38h], 0F87369Fh
0x180010497  mov     dword ptr [r11-34h], 4CFCA4E5h
0x18001049f  mov     dword ptr [r11-30h], 0E6733EBDh
0x1800104a7  mov     dword ptr [r11-2Ch], 0DD724515h
0x1800104af  lea     rdx, [r11-38h]
0x1800104b3  lea     rcx, [rsp+0F8h+var_B8]
0x1800104b8  call    ??$create_instance@UITaskService@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x1800104bd  nop
0x1800104be  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800104c3  call    cs:__imp_VariantInit
0x1800104c9  nop
0x1800104ca  mov     rcx, [rsp+0F8h+var_B8]
0x1800104cf  movups  xmm1, xmmword ptr [rsp+0F8h+pvarg]
0x1800104d4  movsd   xmm0, qword ptr [rsp+0F8h+pvarg+10h]
0x1800104da  movaps  xmmword ptr [rsp+0F8h+var_38], xmm1
0x1800104e2  movsd   [rsp+0F8h+var_28], xmm0
0x1800104eb  movaps  [rsp+0F8h+var_98], xmm1
0x1800104f0  movsd   [rsp+0F8h+var_88], xmm0
0x1800104f6  movaps  [rsp+0F8h+var_78], xmm1
0x1800104fe  movsd   [rsp+0F8h+var_68], xmm0
0x180010507  movaps  [rsp+0F8h+var_58], xmm1
0x18001050f  movsd   [rsp+0F8h+var_48], xmm0
0x180010518  mov     rax, [rcx]
0x18001051b  lea     rdx, [rsp+0F8h+var_38]
0x180010523  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180010528  lea     r9, [rsp+0F8h+var_98]
0x18001052d  lea     r8, [rsp+0F8h+var_78]
0x180010535  lea     rdx, [rsp+0F8h+var_58]
0x18001053d  mov     rax, [rax+50h]
0x180010541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010546  mov     rcx, [rsp+0F8h]; this
0x18001054e  test    eax, eax
0x180010550  jns     short loc_180010566
0x180010552  mov     r9d, eax; char *
0x180010555  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18001055c  mov     edx, 16Ah; void *
0x180010561  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010566  mov     [rsp+0F8h+var_C0], 0
0x18001056f  mov     rcx, [rsp+0F8h+var_B8]
0x180010574  mov     rax, [rcx]
0x180010577  lea     r8, [rsp+0F8h+var_C0]
0x18001057c  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Printing"
0x180010583  mov     rax, [rax+38h]
0x180010587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001058c  mov     rcx, [rsp+0F8h]; this
0x180010594  test    eax, eax
0x180010596  jns     short loc_1800105AC
0x180010598  mov     r9d, eax; char *
0x18001059b  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x1800105a2  mov     edx, 16Dh; void *
0x1800105a7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800105ac  mov     [rsp+0F8h+var_C8], 0
0x1800105b5  mov     rcx, [rsp+0F8h+var_C0]
0x1800105ba  mov     rax, [rcx]
0x1800105bd  lea     r8, [rsp+0F8h+var_C8]
0x1800105c2  lea     rdx, aPrintjobcleanu; "PrintJobCleanupTask"
0x1800105c9  mov     rax, [rax+68h]
0x1800105cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d2  mov     rcx, [rsp+0F8h]; this
0x1800105da  test    eax, eax
0x1800105dc  jns     short loc_1800105F2
0x1800105de  mov     r9d, eax; char *
0x1800105e1  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x1800105e8  mov     edx, 170h; void *
0x1800105ed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800105f2  mov     rcx, [rsp+0F8h+var_C8]
0x1800105f7  mov     rax, [rcx]
0x1800105fa  xor     bl, 1
0x1800105fd  movzx   edx, bl
0x180010600  dec     dx
0x180010603  mov     rax, [rax+58h]
0x180010607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001060c  mov     rcx, [rsp+0F8h]; this
0x180010614  test    eax, eax
0x180010616  jns     short loc_18001062D
0x180010618  mov     r9d, eax; char *
0x18001061b  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x180010622  mov     edx, 171h; void *
0x180010627  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001062d  cmp     [rsp+0F8h+var_C8], 0
0x180010633  jz      short loc_180010640
0x180010635  lea     rcx, [rsp+0F8h+var_C8]
0x18001063a  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x18001063f  nop
0x180010640  cmp     [rsp+0F8h+var_C0], 0
0x180010646  jz      short loc_180010653
0x180010648  lea     rcx, [rsp+0F8h+var_C0]
0x18001064d  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x180010652  nop
0x180010653  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180010658  call    cs:__imp_VariantClear
0x18001065e  nop
0x18001065f  cmp     [rsp+0F8h+var_B8], 0
0x180010665  jz      short loc_180010671
0x180010667  lea     rcx, [rsp+0F8h+var_B8]
0x18001066c  call    ?unconditional_release_ref@?$com_ptr@UITaskService@@@winrt@@AEAAXXZ; winrt::com_ptr<ITaskService>::unconditional_release_ref(void)
0x180010671  xor     eax, eax
0x180010673  jmp     short loc_180010679
0x180010675  mov     eax, dword ptr [rsp+0F8h+var_C8]
0x180010679  mov     rcx, [rsp+0F8h+var_18]
0x180010681  xor     rcx, rsp; StackCookie
0x180010684  call    __security_check_cookie
0x180010689  add     rsp, 0F0h
0x180010690  pop     rbx
0x180010691  retn
```

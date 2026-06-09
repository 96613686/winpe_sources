# TextInputMethodFormatter::SendVersionToRemote(uint,uint)

- ea: `0x1800109b0`
- end: `0x180010bd1`
- name: `?SendVersionToRemote@TextInputMethodFormatter@@UEAAJII@Z`
- size: `545`
- prototype: `__int64 __fastcall(TextInputMethodFormatter *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180013890`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x18000a830`
- `0x18000c454`
- `0x180010540`
- `0x1800109b0`
- `0x180012074`
- `0x180058010`

## string_xrefs

- `0x180010baa`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x180010bbf`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TextInputMethodFormatter::SendVersionToRemote(
        TextInputMethodFormatter *this,
        unsigned int a2,
        unsigned int a3)
{
  unsigned int v6; // r8d
  int v7; // eax
  int v8; // eax
  int v10[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v11; // [rsp+48h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v6 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
  if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
  {
    v11 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
                       this,
                       &v11);
    v6 = v11;
  }
  v10[0] = 0;
  LOWORD(v10[1]) = 3;
  wil::details::ReportUsageToService(&unk_1800827F8, 42936120, (v6 >> 10) & 1, (v6 >> 11) & 1);
  *(_QWORD *)v10 = 0;
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, int *))this + 18))(
         *((_QWORD *)this + 18),
         &GUID_6f8cc13f_4dc0_4ed7_8f31_0a6a48c00cdb,
         v10);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v7,
      (int)v10);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v10 + 24LL))(*(_QWORD *)v10, a2, a3);
  v8 = TextInputMethodFormatter::EnableRemoteKeyRouting(this, 1, a2, a3);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x310,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v8,
      (int)v10);
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, byte_180074D59, 0, 0, 2u, &v12);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 14) + 8LL))(*((_QWORD *)this + 14), a2, a3);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(*((_QWORD *)this + 15), a2, a3);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 8LL))(*((_QWORD *)this + 17), a2, a3);
  *((_DWORD *)this + 60) = a2;
  *((_DWORD *)this + 61) = a3;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 24LL))(*((_QWORD *)this + 20));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 32LL))(*((_QWORD *)this + 8));
  if ( *(_QWORD *)v10 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 16LL))(*(_QWORD *)v10);
  return 0;
}

```

## disassembly

```asm
0x1800109b0  mov     [rsp-18h+arg_18], rbx
0x1800109b5  push    rbp
0x1800109b6  push    rsi
0x1800109b7  push    rdi
0x1800109b8  mov     rbp, rsp
0x1800109bb  sub     rsp, 80h
0x1800109c2  mov     rax, cs:__security_cookie
0x1800109c9  xor     rax, rsp
0x1800109cc  mov     [rbp+var_10], rax
0x1800109d0  mov     esi, r8d
0x1800109d3  mov     edi, edx
0x1800109d5  mov     rbx, rcx
0x1800109d8  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x1800109df  mov     r8d, [rax]
0x1800109e2  test    r8b, 4
0x1800109e6  jnz     short loc_1800109FB
0x1800109e8  lea     rdx, [rbp+var_38]
0x1800109ec  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x1800109f1  mov     rcx, [rax]
0x1800109f4  mov     [rbp+var_38], rcx
0x1800109f8  mov     r8d, ecx
0x1800109fb  xor     eax, eax
0x1800109fd  mov     [rbp+var_40], eax
0x180010a00  mov     word ptr [rbp+var_40+4], 3
0x180010a06  mov     r9d, r8d
0x180010a09  shr     r9d, 0Bh
0x180010a0d  and     r9d, 1
0x180010a11  shr     r8d, 0Ah
0x180010a15  and     r8d, 1
0x180010a19  mov     [rsp+80h+var_50], 3
0x180010a21  mov     dword ptr [rsp+80h+var_58], 1
0x180010a29  lea     rax, [rbp+var_40]
0x180010a2d  mov     qword ptr [rsp+80h+var_60], rax; int
0x180010a32  mov     edx, 28F2738h
0x180010a37  lea     rcx, unk_1800827F8
0x180010a3e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010a43  nop
0x180010a44  mov     qword ptr [rbp+var_40], 0
0x180010a4c  mov     rcx, [rbx+90h]
0x180010a53  mov     rax, [rcx]
0x180010a56  lea     r8, [rbp+var_40]
0x180010a5a  lea     rdx, _GUID_6f8cc13f_4dc0_4ed7_8f31_0a6a48c00cdb
0x180010a61  mov     rax, [rax]
0x180010a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a69  mov     rcx, [rbp+18h]; this
0x180010a6d  test    eax, eax
0x180010a6f  js      loc_180010BBC
0x180010a75  mov     rcx, qword ptr [rbp+var_40]
0x180010a79  mov     rax, [rcx]
0x180010a7c  mov     r8d, esi
0x180010a7f  mov     edx, edi
0x180010a81  mov     rax, [rax+18h]
0x180010a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a8a  mov     r9d, esi; unsigned int
0x180010a8d  mov     r8d, edi; unsigned int
0x180010a90  mov     dl, 1; bool
0x180010a92  mov     rcx, rbx; this
0x180010a95  call    ?EnableRemoteKeyRouting@TextInputMethodFormatter@@AEAAJ_NII@Z; TextInputMethodFormatter::EnableRemoteKeyRouting(bool,uint,uint)
0x180010a9a  mov     rcx, [rbp+18h]; this
0x180010a9e  test    eax, eax
0x180010aa0  js      loc_180010BA7
0x180010aa6  mov     eax, cs:dword_180082080
0x180010aac  cmp     eax, 5
0x180010aaf  jbe     short loc_180010AFE
0x180010ab1  mov     rcx, cs:qword_180082098
0x180010ab8  mov     rax, cs:qword_180082090
0x180010abf  mov     edx, 400000h
0x180010ac4  test    rdx, rax
0x180010ac7  jz      short loc_180010AFE
0x180010ac9  mov     rax, rcx
0x180010acc  and     rax, rdx
0x180010acf  cmp     rax, rcx
0x180010ad2  jnz     short loc_180010AFE
0x180010ad4  lea     rax, [rbp+var_30]
0x180010ad8  mov     [rsp+80h+var_58], rax
0x180010add  mov     [rsp+80h+var_60], 2
0x180010ae5  xor     r9d, r9d
0x180010ae8  xor     r8d, r8d
0x180010aeb  lea     rdx, byte_180074D59
0x180010af2  lea     rcx, dword_180082080
0x180010af9  call    _tlgWriteTransfer_EventWriteTransfer
0x180010afe  mov     rcx, [rbx+70h]
0x180010b02  mov     rax, [rcx]
0x180010b05  mov     r8d, esi
0x180010b08  mov     edx, edi
0x180010b0a  mov     rax, [rax+8]
0x180010b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b13  mov     rcx, [rbx+78h]
0x180010b17  mov     rax, [rcx]
0x180010b1a  mov     r8d, esi
0x180010b1d  mov     edx, edi
0x180010b1f  mov     rax, [rax+8]
0x180010b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b28  mov     rcx, [rbx+88h]
0x180010b2f  mov     rax, [rcx]
0x180010b32  mov     r8d, esi
0x180010b35  mov     edx, edi
0x180010b37  mov     rax, [rax+8]
0x180010b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b40  mov     [rbx+0F0h], edi
0x180010b46  mov     [rbx+0F4h], esi
0x180010b4c  mov     rcx, [rbx+0A0h]
0x180010b53  mov     rax, [rcx]
0x180010b56  mov     rax, [rax+18h]
0x180010b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b5f  mov     rcx, [rbx+40h]
0x180010b63  mov     rax, [rcx]
0x180010b66  mov     rax, [rax+20h]
0x180010b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b6f  nop
0x180010b70  mov     rcx, qword ptr [rbp+var_40]
0x180010b74  test    rcx, rcx
0x180010b77  jz      short loc_180010B86
0x180010b79  mov     rax, [rcx]
0x180010b7c  mov     rax, [rax+10h]
0x180010b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b85  nop
0x180010b86  xor     eax, eax
0x180010b88  mov     rcx, [rbp+var_10]
0x180010b8c  xor     rcx, rsp; StackCookie
0x180010b8f  call    __security_check_cookie
0x180010b94  mov     rbx, [rsp+80h+arg_18]
0x180010b9c  add     rsp, 80h
0x180010ba3  pop     rdi
0x180010ba4  pop     rsi
0x180010ba5  pop     rbp
0x180010ba6  retn
0x180010ba7  mov     r9d, eax; char *
0x180010baa  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x180010bb1  mov     edx, 310h; void *
0x180010bb6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010bbc  mov     r9d, eax; char *
0x180010bbf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010bc6  mov     edx, 1CBEh; void *
0x180010bcb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

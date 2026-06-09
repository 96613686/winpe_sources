# ReadBoolFromReg

- ea: `0x1400ac3dc`
- end: `0x1400ac4a6`
- name: `ReadBoolFromReg`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400ac178`

## callees

- `0x140078080`
- `0x1400ac3dc`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ac45f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ac45f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac44f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac44f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400ac47d`

## string_xrefs

- `0x1400ac420`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall ReadBoolFromReg(bool *a1, __int64 a2, __int64 a3)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-49h] BYREF
  __int64 v8; // [rsp+40h] [rbp-39h] BYREF
  int v9; // [rsp+48h] [rbp-31h]
  const wchar_t *v10; // [rsp+50h] [rbp-29h]
  int *v11; // [rsp+58h] [rbp-21h]
  int v12; // [rsp+60h] [rbp-19h]
  __int64 v13; // [rsp+68h] [rbp-11h]
  int v14; // [rsp+70h] [rbp-9h]
  __int64 v15; // [rsp+78h] [rbp-1h]
  int v16; // [rsp+80h] [rbp+7h]
  __int64 v17; // [rsp+88h] [rbp+Fh]
  __int64 v18; // [rsp+90h] [rbp+17h]
  int v19; // [rsp+98h] [rbp+1Fh]
  __int64 v20; // [rsp+A0h] [rbp+27h]
  int v21; // [rsp+A8h] [rbp+2Fh]
  int v22; // [rsp+F0h] [rbp+77h] BYREF
  int v23; // [rsp+F4h] [rbp+7Bh]

  v23 = HIDWORD(a3);
  v9 = 36;
  v22 = 0;
  v10 = L"IsVisible";
  v8 = 0;
  v11 = &v22;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  result = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(3, a2, &v8, 0, 0);
  if ( (int)result >= 0 )
    *a1 = v22 != 0;
  return result;
}

```

## disassembly

```asm
0x1400ac3dc  mov     [rsp-8+arg_10], r8
0x1400ac3e1  push    rbp
0x1400ac3e2  push    rbx
0x1400ac3e3  push    rsi
0x1400ac3e4  push    rdi
0x1400ac3e5  lea     rbp, [rsp-3Fh]
0x1400ac3ea  sub     rsp, 0B8h
0x1400ac3f1  xor     esi, esi
0x1400ac3f3  mov     [rbp+57h+var_88], 24h ; '$'
0x1400ac3fa  lea     rax, aIsvisible; "IsVisible"
0x1400ac401  mov     dword ptr [rbp+57h+arg_10], esi
0x1400ac404  mov     [rbp+57h+var_80], rax
0x1400ac408  mov     rbx, rdx
0x1400ac40b  lea     rax, [rbp+57h+arg_10]
0x1400ac40f  mov     [rbp+57h+var_90], rsi
0x1400ac413  mov     rdi, rcx
0x1400ac416  mov     [rbp+57h+var_78], rax
0x1400ac41a  xorps   xmm0, xmm0
0x1400ac41d  mov     [rbp+57h+var_70], esi
0x1400ac420  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400ac427  mov     [rbp+57h+var_68], rsi
0x1400ac42b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400ac42f  mov     [rbp+57h+var_60], esi
0x1400ac432  mov     [rbp+57h+var_58], rsi
0x1400ac436  mov     [rbp+57h+var_50], esi
0x1400ac439  mov     [rbp+57h+var_48], rsi
0x1400ac43d  mov     [rbp+57h+var_40], rsi
0x1400ac441  mov     [rbp+57h+var_38], esi
0x1400ac444  mov     [rbp+57h+var_30], rsi
0x1400ac448  mov     [rbp+57h+var_28], esi
0x1400ac44b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400ac44f  call    cs:__imp_RtlInitUnicodeString
0x1400ac456  nop     dword ptr [rax+rax+00h]
0x1400ac45b  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400ac45f  call    cs:__imp_MmGetSystemRoutineAddress
0x1400ac466  nop     dword ptr [rax+rax+00h]
0x1400ac46b  lea     r8, [rbp+57h+var_90]
0x1400ac46f  mov     [rsp+0D0h+var_B0], rsi
0x1400ac474  test    rax, rax
0x1400ac477  lea     ecx, [rsi+3]
0x1400ac47a  mov     rdx, rbx
0x1400ac47d  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400ac485  xor     r9d, r9d
0x1400ac488  call    _guard_dispatch_icall
0x1400ac48d  test    eax, eax
0x1400ac48f  js      short loc_1400AC499
0x1400ac491  cmp     dword ptr [rbp+57h+arg_10], esi
0x1400ac494  setnz   cl
0x1400ac497  mov     [rdi], cl
0x1400ac499  add     rsp, 0B8h
0x1400ac4a0  pop     rdi
0x1400ac4a1  pop     rsi
0x1400ac4a2  pop     rbx
0x1400ac4a3  pop     rbp
0x1400ac4a4  retn
```

# ReadGuidFromReg

- ea: `0x1400ac4ac`
- end: `0x1400ac587`
- name: `ReadGuidFromReg`
- size: `219`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400ac218`

## callees

- `0x140078080`
- `0x1400ac4ac`
- `0x1400ac590`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ac52f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ac52f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac51f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ac51f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400ac551`

## string_xrefs

- `0x1400ac4e1`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall ReadGuidFromReg(GUID *Guid)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-39h] BYREF
  PCWSTR Source[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v6; // [rsp+50h] [rbp-19h] BYREF
  int v7; // [rsp+58h] [rbp-11h]
  const wchar_t *v8; // [rsp+60h] [rbp-9h]
  PCWSTR *v9; // [rsp+68h] [rbp-1h]
  int v10; // [rsp+70h] [rbp+7h]
  __int64 v11; // [rsp+78h] [rbp+Fh]
  int v12; // [rsp+80h] [rbp+17h]
  __int64 v13; // [rsp+88h] [rbp+1Fh]
  int v14; // [rsp+90h] [rbp+27h]
  __int64 v15; // [rsp+98h] [rbp+2Fh]
  __int64 v16; // [rsp+A0h] [rbp+37h]
  int v17; // [rsp+A8h] [rbp+3Fh]
  __int64 v18; // [rsp+B0h] [rbp+47h]
  int v19; // [rsp+B8h] [rbp+4Fh]

  v7 = 36;
  v6 = 0;
  v10 = 0;
  v8 = L"Profile";
  v11 = 0;
  v9 = Source;
  v12 = 0;
  *(_OWORD *)Source = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  result = ((__int64 (__fastcall *)(__int64, const WCHAR *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
             3,
             L"Containers\\Policy",
             &v6,
             0,
             0);
  if ( (int)result >= 0 )
    return StringToGuid(Source[1], Guid);
  return result;
}

```

## disassembly

```asm
0x1400ac4ac  mov     [rsp-8+arg_0], rbx
0x1400ac4b1  mov     [rsp-8+arg_8], rdi
0x1400ac4b6  push    rbp
0x1400ac4b7  lea     rbp, [rsp-57h]
0x1400ac4bc  sub     rsp, 0C0h
0x1400ac4c3  xor     edi, edi
0x1400ac4c5  mov     [rbp+57h+var_68], 24h ; '$'
0x1400ac4cc  xorps   xmm0, xmm0
0x1400ac4cf  mov     [rbp+57h+var_70], rdi
0x1400ac4d3  lea     rax, aProfile; "Profile"
0x1400ac4da  mov     [rbp+57h+var_50], edi
0x1400ac4dd  mov     [rbp+57h+var_60], rax
0x1400ac4e1  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400ac4e8  lea     rax, [rbp+57h+Source]
0x1400ac4ec  mov     [rbp+57h+var_48], rdi
0x1400ac4f0  mov     rbx, rcx
0x1400ac4f3  mov     [rbp+57h+var_58], rax
0x1400ac4f7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400ac4fb  mov     [rbp+57h+var_40], edi
0x1400ac4fe  movups  xmmword ptr [rbp+57h+Source], xmm0
0x1400ac502  mov     [rbp+57h+var_38], rdi
0x1400ac506  mov     [rbp+57h+var_30], edi
0x1400ac509  mov     [rbp+57h+var_28], rdi
0x1400ac50d  mov     [rbp+57h+var_20], rdi
0x1400ac511  mov     [rbp+57h+var_18], edi
0x1400ac514  mov     [rbp+57h+var_10], rdi
0x1400ac518  mov     [rbp+57h+var_8], edi
0x1400ac51b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400ac51f  call    cs:__imp_RtlInitUnicodeString
0x1400ac526  nop     dword ptr [rax+rax+00h]
0x1400ac52b  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400ac52f  call    cs:__imp_MmGetSystemRoutineAddress
0x1400ac536  nop     dword ptr [rax+rax+00h]
0x1400ac53b  lea     r8, [rbp+57h+var_70]
0x1400ac53f  mov     [rsp+0C0h+var_A0], rdi
0x1400ac544  test    rax, rax
0x1400ac547  lea     rdx, Source; "Containers\\Policy"
0x1400ac54e  lea     ecx, [rdi+3]
0x1400ac551  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400ac559  xor     r9d, r9d
0x1400ac55c  call    _guard_dispatch_icall
0x1400ac561  test    eax, eax
0x1400ac563  js      short loc_1400AC571
0x1400ac565  mov     rcx, [rbp+57h+Source+8]; Source
0x1400ac569  mov     rdx, rbx; Guid
0x1400ac56c  call    StringToGuid
0x1400ac571  lea     r11, [rsp+0C0h+var_s0]
0x1400ac579  mov     rbx, [r11+10h]
0x1400ac57d  mov     rdi, [r11+18h]
0x1400ac581  mov     rsp, r11
0x1400ac584  pop     rbp
0x1400ac585  retn
```

# _lambda_3488f218c18fd8ea74c439b67efbc39f_::operator()

- ea: `0x18002bb4c`
- end: `0x18002bc66`
- name: `_lambda_3488f218c18fd8ea74c439b67efbc39f_::operator()`
- size: `282`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002967c`
- `0x180029764`
- `0x180029854`
- `0x180029a34`

## callees

- `0x18002bb4c`
- `0x18002c520`
- `0x18004a7cc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall lambda_3488f218c18fd8ea74c439b67efbc39f_::operator()(
        int **a1,
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *a2,
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *a3)
{
  int v5; // r10d
  double v6; // xmm0_8
  int v7; // r10d
  double v8; // xmm1_8
  void (__fastcall *v10)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, HSTRING *); // rbx
  void (__fastcall *v11)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, HSTRING *); // rbx
  HSTRING v12; // r8
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  HSTRING v14; // [rsp+48h] [rbp+28h] BYREF

  v5 = **a1;
  if ( v5 == 3 )
    goto LABEL_11;
  v6 = 0.0;
  string = 0;
  v14 = 0;
  if ( (int)SystemSettings::BatteryUsageHandlers::AppListEntry2::GetAppEnergyUsage(a2, v5, (double *)&string) >= 0 )
    v8 = *(double *)&string;
  else
    v8 = 0.0;
  if ( (int)SystemSettings::BatteryUsageHandlers::AppListEntry2::GetAppEnergyUsage(a3, v7, (double *)&v14) >= 0 )
    v6 = *(double *)&v14;
  if ( v6 > v8 )
    return 0;
  if ( v8 > v6 )
    return 1;
LABEL_11:
  v14 = 0;
  string = 0;
  v10 = *(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, HSTRING *))(*(_QWORD *)a2 + 88LL);
  WindowsDeleteString(0);
  v14 = 0;
  v10(a2, &v14);
  v11 = *(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, HSTRING *))(*(_QWORD *)a3 + 88LL);
  WindowsDeleteString(string);
  string = 0;
  v11(a3, &string);
  LOBYTE(v11) = (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                (Microsoft::WRL::Wrappers::Details *)v14,
                                string,
                                v12) == -1;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v14);
  return (char)v11;
}

```

## disassembly

```asm
0x18002bb4c  mov     [rsp-18h+arg_10], rbx
0x18002bb51  push    rbp
0x18002bb52  push    rsi
0x18002bb53  push    rdi
0x18002bb54  mov     rbp, rsp
0x18002bb57  sub     rsp, 20h
0x18002bb5b  mov     rsi, r8
0x18002bb5e  mov     rdi, rdx
0x18002bb61  mov     rax, [rcx]
0x18002bb64  mov     r10d, [rax]
0x18002bb67  cmp     r10d, 3
0x18002bb6b  jz      short loc_18002BBC9
0x18002bb6d  xorps   xmm0, xmm0
0x18002bb70  movsd   [rbp+string], xmm0
0x18002bb75  movsd   [rbp+arg_8], xmm0
0x18002bb7a  lea     r8, [rbp+string]; double *
0x18002bb7e  mov     edx, r10d; int
0x18002bb81  mov     rcx, rdi; this
0x18002bb84  call    ?GetAppEnergyUsage@AppListEntry2@BatteryUsageHandlers@SystemSettings@@QEAAJHPEAN@Z; SystemSettings::BatteryUsageHandlers::AppListEntry2::GetAppEnergyUsage(int,double *)
0x18002bb89  test    eax, eax
0x18002bb8b  jns     short loc_18002BB92
0x18002bb8d  xorps   xmm1, xmm1
0x18002bb90  jmp     short loc_18002BB97
0x18002bb92  movsd   xmm1, [rbp+string]
0x18002bb97  lea     r8, [rbp+arg_8]; double *
0x18002bb9b  mov     edx, r10d; int
0x18002bb9e  mov     rcx, rsi; this
0x18002bba1  call    ?GetAppEnergyUsage@AppListEntry2@BatteryUsageHandlers@SystemSettings@@QEAAJHPEAN@Z; SystemSettings::BatteryUsageHandlers::AppListEntry2::GetAppEnergyUsage(int,double *)
0x18002bba6  test    eax, eax
0x18002bba8  js      short loc_18002BBAF
0x18002bbaa  movsd   xmm0, [rbp+arg_8]
0x18002bbaf  comisd  xmm0, xmm1
0x18002bbb3  jbe     short loc_18002BBBC
0x18002bbb5  xor     al, al
0x18002bbb7  jmp     loc_18002BC59
0x18002bbbc  comisd  xmm1, xmm0
0x18002bbc0  jbe     short loc_18002BBC9
0x18002bbc2  mov     al, 1
0x18002bbc4  jmp     loc_18002BC59
0x18002bbc9  mov     [rbp+arg_8], 0
0x18002bbd1  mov     [rbp+string], 0
0x18002bbd9  mov     rax, [rdi]
0x18002bbdc  mov     rbx, [rax+58h]
0x18002bbe0  xor     ecx, ecx; string
0x18002bbe2  call    cs:__imp_WindowsDeleteString
0x18002bbe8  mov     [rbp+arg_8], 0
0x18002bbf0  lea     rdx, [rbp+arg_8]
0x18002bbf4  mov     rcx, rdi
0x18002bbf7  mov     rax, rbx
0x18002bbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbff  mov     rax, [rsi]
0x18002bc02  mov     rbx, [rax+58h]
0x18002bc06  mov     rcx, [rbp+string]; string
0x18002bc0a  call    cs:__imp_WindowsDeleteString
0x18002bc10  mov     [rbp+string], 0
0x18002bc18  lea     rdx, [rbp+string]
0x18002bc1c  mov     rcx, rsi
0x18002bc1f  mov     rax, rbx
0x18002bc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc27  mov     rdx, [rbp+string]; HSTRING
0x18002bc2b  mov     rcx, [rbp+arg_8]; this
0x18002bc2f  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18002bc34  nop
0x18002bc35  cmp     eax, 0FFFFFFFFh
0x18002bc38  setz    bl
0x18002bc3b  mov     rcx, [rbp+string]; string
0x18002bc3f  call    cs:__imp_WindowsDeleteString
0x18002bc45  mov     [rbp+string], 0
0x18002bc4d  mov     rcx, [rbp+arg_8]; string
0x18002bc51  call    cs:__imp_WindowsDeleteString
0x18002bc57  mov     al, bl
0x18002bc59  mov     rbx, [rsp+20h+arg_10]
0x18002bc5e  add     rsp, 20h
0x18002bc62  pop     rdi
0x18002bc63  pop     rsi
0x18002bc64  pop     rbp
0x18002bc65  retn
```

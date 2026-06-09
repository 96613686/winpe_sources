# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140004ae0`
- end: `0x140004b61`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003690`

## callees

- `0x140004ae0`
- `0x140004b68`
- `0x140004ecc`
- `0x1400138a0`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  unsigned __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v4 = a2 & 1;
  v5 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     v6,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v4, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004ae0  mov     [rsp+arg_0], rbx
0x140004ae5  mov     [rsp+arg_10], r8d
0x140004aea  push    rdi
0x140004aeb  sub     rsp, 50h
0x140004aef  mov     edi, edx
0x140004af1  mov     r9, rdx
0x140004af4  mov     rbx, rcx
0x140004af7  and     edi, 1
0x140004afa  mov     edx, edi
0x140004afc  mov     ecx, r8d
0x140004aff  call    wil_details_MapReportingKind
0x140004b04  mov     r8d, eax
0x140004b07  mov     rdx, r9
0x140004b0a  mov     rcx, rbx
0x140004b0d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140004b12  test    eax, eax
0x140004b14  jz      short loc_140004B55
0x140004b16  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140004b1d  test    rax, rax
0x140004b20  jz      short loc_140004B55
0x140004b22  mov     rdx, [rbx+10h]
0x140004b26  lea     rcx, [rsp+58h+arg_10]
0x140004b2b  mov     [rsp+58h+var_20], 1
0x140004b34  mov     r9d, edi
0x140004b37  mov     [rsp+58h+var_28], 0
0x140004b3c  xor     r8d, r8d
0x140004b3f  mov     [rsp+58h+var_30], 0
0x140004b48  mov     [rsp+58h+var_38], rcx
0x140004b4d  mov     ecx, [rbx+18h]
0x140004b50  call    _guard_dispatch_icall
0x140004b55  mov     rbx, [rsp+58h+arg_0]
0x140004b5a  add     rsp, 50h
0x140004b5e  pop     rdi
0x140004b5f  retn
```

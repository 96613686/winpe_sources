# DpspRunTask(IRegisteredTask *,ulong,void *)

- ea: `0x180016c7c`
- end: `0x180016d9d`
- name: `?DpspRunTask@@YAJPEAUIRegisteredTask@@KPEAX@Z`
- size: `289`
- prototype: `int(struct IRegisteredTask *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008990`

## callees

- `0x180009090`
- `0x180016c7c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016cd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d74`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180016cc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180016cc7`
- `OLEAUT32!__imp_VariantInit` at `0x180016cb2`
- `OLEAUT32!__imp_VariantInit` at `0x180016cb2`
- `OLEAUT32!__imp_VariantClear` at `0x180016d6a`
- `OLEAUT32!__imp_VariantClear` at `0x180016d6a`

## string_xrefs

- `0x180016d5a`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180016d53`: `DpspRunTask`

## pseudocode

```c
__int64 __fastcall DpspRunTask(struct IRegisteredTask *a1, unsigned int a2, void *a3)
{
  signed int LastError; // eax
  signed int Args; // ebx
  HRESULT (__stdcall *RunEx)(IRegisteredTask *, VARIANT, LONG, LONG, BSTR, IRunningTask **); // rax
  int v9; // eax
  __int64 v11; // [rsp+40h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-1h] BYREF
  VARIANTARG v13; // [rsp+60h] [rbp+17h] BYREF
  LPWSTR StringSid; // [rsp+C8h] [rbp+7Fh] BYREF

  v11 = 0;
  StringSid = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  if ( ConvertSidToStringSidW(a3, &StringSid) )
    goto LABEL_6;
  LastError = GetLastError();
  Args = LastError;
  if ( LastError > 0 )
    Args = (unsigned __int16)LastError | 0x80070000;
  if ( Args >= 0 )
  {
LABEL_6:
    RunEx = a1->lpVtbl->RunEx;
    v13 = pvarg;
    v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, VARIANTARG *, __int64, _QWORD, LPWSTR, __int64 *))RunEx)(
           a1,
           &v13,
           12,
           a2,
           StringSid,
           &v11);
    Args = v9;
    if ( v9 < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
        (int)L"DpspRunTask",
        252,
        (int)L"Error = %d",
        v9);
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (int)L"DpspRunTask",
      244,
      (int)L"Error = %d",
      Args);
  }
  VariantClear(&pvarg);
  LocalFree(StringSid);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180016c7c  push    rbp
0x180016c7e  push    rbx
0x180016c7f  push    rsi
0x180016c80  push    rdi
0x180016c81  lea     rbp, [rsp-3Fh]
0x180016c86  sub     rsp, 88h
0x180016c8d  xor     eax, eax
0x180016c8f  mov     [rbp+57h+var_60], 0
0x180016c97  mov     rdi, rcx
0x180016c9a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180016c9e  xorps   xmm0, xmm0
0x180016ca1  mov     [rbp+57h+StringSid], rax
0x180016ca5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016ca9  mov     rbx, r8
0x180016cac  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180016cb0  mov     esi, edx
0x180016cb2  call    cs:__imp_VariantInit
0x180016cb8  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180016cbc  mov     qword ptr [rbp+57h+pvarg+8], 0
0x180016cc4  mov     rcx, rbx; Sid
0x180016cc7  call    cs:__imp_ConvertSidToStringSidW
0x180016ccd  test    eax, eax
0x180016ccf  jnz     short loc_180016CF9
0x180016cd1  call    cs:__imp_GetLastError
0x180016cd7  mov     ebx, eax
0x180016cd9  test    eax, eax
0x180016cdb  jle     short loc_180016CE6
0x180016cdd  movzx   ebx, ax
0x180016ce0  or      ebx, 80070000h
0x180016ce6  test    ebx, ebx
0x180016ce8  jns     short loc_180016CF9
0x180016cea  movzx   eax, bx
0x180016ced  mov     r8d, 0F4h
0x180016cf3  mov     dword ptr [rsp+0A0h+Args], eax
0x180016cf7  jmp     short loc_180016D4C
0x180016cf9  mov     rax, [rdi]
0x180016cfc  lea     rcx, [rbp+57h+var_60]
0x180016d00  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180016d04  lea     rdx, [rbp+57h+var_40]
0x180016d08  mov     [rsp+0A0h+var_78], rcx
0x180016d0d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180016d12  mov     r9d, esi
0x180016d15  mov     rcx, [rbp+57h+StringSid]
0x180016d19  mov     r8d, 0Ch
0x180016d1f  mov     rax, [rax+68h]
0x180016d23  mov     qword ptr [rsp+0A0h+Args], rcx
0x180016d28  mov     rcx, rdi
0x180016d2b  movaps  [rbp+57h+var_40], xmm0
0x180016d2f  movsd   [rbp+57h+var_30], xmm1
0x180016d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d39  mov     ebx, eax
0x180016d3b  test    eax, eax
0x180016d3d  jns     short loc_180016D66
0x180016d3f  movzx   ecx, ax
0x180016d42  mov     r8d, 0FCh; int
0x180016d48  mov     dword ptr [rsp+0A0h+Args], ecx; Args
0x180016d4c  lea     r9, aErrorD; "Error = %d"
0x180016d53  lea     rdx, aDpspruntask; "DpspRunTask"
0x180016d5a  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016d61  call    WdipTraceError
0x180016d66  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180016d6a  call    cs:__imp_VariantClear
0x180016d70  mov     rcx, [rbp+57h+StringSid]; hMem
0x180016d74  call    cs:__imp_LocalFree
0x180016d7a  mov     rcx, [rbp+57h+var_60]
0x180016d7e  test    rcx, rcx
0x180016d81  jz      short loc_180016D8F
0x180016d83  mov     rax, [rcx]
0x180016d86  mov     rax, [rax+10h]
0x180016d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d8f  mov     eax, ebx
0x180016d91  add     rsp, 88h
0x180016d98  pop     rdi
0x180016d99  pop     rsi
0x180016d9a  pop     rbx
0x180016d9b  pop     rbp
0x180016d9c  retn
```

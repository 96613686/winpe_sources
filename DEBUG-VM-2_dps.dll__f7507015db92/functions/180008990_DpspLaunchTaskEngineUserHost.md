# DpspLaunchTaskEngineUserHost

- ea: `0x180008990`
- end: `0x180008aaf`
- name: `DpspLaunchTaskEngineUserHost`
- size: `287`
- prototype: `__int64 __fastcall(unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b484`

## callees

- `0x180008990`
- `0x180009090`
- `0x180016bd4`
- `0x180016c7c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008a04`
- `OLEAUT32!__imp_SysAllocString` at `0x180008a04`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a88`
- `OLEAUT32!__imp_SysFreeString` at `0x180008a88`

## string_xrefs

- `0x1800089cd`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180008a79`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x1800089c6`: `DpspLaunchTaskEngineUserHost`
- `0x180008a72`: `DpspLaunchTaskEngineUserHost`

## pseudocode

```c
__int64 __fastcall DpspLaunchTaskEngineUserHost(unsigned int a1, void *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  unsigned __int16 *v6; // rax
  OLECHAR *v7; // rdi
  int RegisteredTask; // eax
  int v9; // r8d
  int v10; // eax
  int Args; // [rsp+20h] [rbp-38h]
  char Argsa[4]; // [rsp+20h] [rbp-38h]
  struct IRegisteredTask *v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    Args = 87;
    v5 = 403;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (__int64)L"DpspLaunchTaskEngineUserHost",
      v5,
      (const wchar_t *)L"Error = %d",
      Args);
    goto LABEL_14;
  }
  if ( !g_pTaskService )
  {
    v4 = -2147467259;
    Args = 16389;
    v5 = 405;
    goto LABEL_3;
  }
  v6 = SysAllocString(L"ResolutionHost");
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    Args = 14;
    v5 = 408;
    goto LABEL_3;
  }
  RegisteredTask = DpspGetRegisteredTask(v6, &v14);
  v4 = RegisteredTask;
  if ( RegisteredTask < 0 )
  {
    v9 = 413;
    *(_DWORD *)Argsa = (unsigned __int16)RegisteredTask;
LABEL_12:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (__int64)L"DpspLaunchTaskEngineUserHost",
      v9,
      (const wchar_t *)L"Error = %d",
      *(_DWORD *)Argsa);
    goto LABEL_13;
  }
  v10 = DpspRunTask(v14, a1, a2);
  v4 = v10;
  if ( v10 < 0 )
  {
    v9 = 419;
    *(_DWORD *)Argsa = (unsigned __int16)v10;
    goto LABEL_12;
  }
LABEL_13:
  SysFreeString(v7);
LABEL_14:
  if ( v14 )
    ((void (__fastcall *)(struct IRegisteredTask *))v14->lpVtbl->Release)(v14);
  return v4;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  push    rbp
0x180008993  push    rsi
0x180008994  push    rdi
0x180008995  sub     rsp, 38h
0x180008999  mov     [rsp+58h+arg_8], 0
0x1800089a2  mov     rsi, rdx
0x1800089a5  mov     ebp, ecx
0x1800089a7  test    rdx, rdx
0x1800089aa  jnz     short loc_1800089DE
0x1800089ac  mov     ebx, 80070057h
0x1800089b1  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800089b9  mov     r8d, 193h; int
0x1800089bf  lea     r9, aErrorD; "Error = %d"
0x1800089c6  lea     rdx, aDpsplaunchtask; "DpspLaunchTaskEngineUserHost"
0x1800089cd  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800089d4  call    WdipTraceError
0x1800089d9  jmp     loc_180008A8E
0x1800089de  cmp     cs:g_pTaskService, 0
0x1800089e6  jnz     short loc_1800089FD
0x1800089e8  mov     ebx, 80004005h
0x1800089ed  mov     dword ptr [rsp+58h+Args], 4005h
0x1800089f5  mov     r8d, 195h
0x1800089fb  jmp     short loc_1800089BF
0x1800089fd  lea     rcx, psz; "ResolutionHost"
0x180008a04  call    cs:__imp_SysAllocString
0x180008a0a  mov     rdi, rax
0x180008a0d  test    rax, rax
0x180008a10  jnz     short loc_180008A27
0x180008a12  mov     ebx, 8007000Eh
0x180008a17  mov     dword ptr [rsp+58h+Args], 0Eh
0x180008a1f  mov     r8d, 198h
0x180008a25  jmp     short loc_1800089BF
0x180008a27  lea     rdx, [rsp+58h+arg_8]; struct IRegisteredTask **
0x180008a2c  mov     rcx, rdi; unsigned __int16 *
0x180008a2f  call    ?DpspGetRegisteredTask@@YAJPEAGPEAPEAUIRegisteredTask@@@Z; DpspGetRegisteredTask(ushort *,IRegisteredTask * *)
0x180008a34  mov     ebx, eax
0x180008a36  test    eax, eax
0x180008a38  jns     short loc_180008A49
0x180008a3a  movzx   ecx, ax
0x180008a3d  mov     r8d, 19Dh
0x180008a43  mov     dword ptr [rsp+58h+Args], ecx
0x180008a47  jmp     short loc_180008A6B
0x180008a49  mov     rcx, [rsp+58h+arg_8]; struct IRegisteredTask *
0x180008a4e  mov     r8, rsi; void *
0x180008a51  mov     edx, ebp; unsigned int
0x180008a53  call    ?DpspRunTask@@YAJPEAUIRegisteredTask@@KPEAX@Z; DpspRunTask(IRegisteredTask *,ulong,void *)
0x180008a58  mov     ebx, eax
0x180008a5a  test    eax, eax
0x180008a5c  jns     short loc_180008A85
0x180008a5e  movzx   eax, ax
0x180008a61  mov     r8d, 1A3h; int
0x180008a67  mov     dword ptr [rsp+58h+Args], eax; Args
0x180008a6b  lea     r9, aErrorD; "Error = %d"
0x180008a72  lea     rdx, aDpsplaunchtask; "DpspLaunchTaskEngineUserHost"
0x180008a79  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180008a80  call    WdipTraceError
0x180008a85  mov     rcx, rdi; bstrString
0x180008a88  call    cs:__imp_SysFreeString
0x180008a8e  mov     rcx, [rsp+58h+arg_8]
0x180008a93  test    rcx, rcx
0x180008a96  jz      short loc_180008AA4
0x180008a98  mov     rax, [rcx]
0x180008a9b  mov     rax, [rax+10h]
0x180008a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa4  mov     eax, ebx
0x180008aa6  add     rsp, 38h
0x180008aaa  pop     rdi
0x180008aab  pop     rsi
0x180008aac  pop     rbp
0x180008aad  pop     rbx
0x180008aae  retn
```

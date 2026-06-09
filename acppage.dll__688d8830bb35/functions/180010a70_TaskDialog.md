# TaskDialog

- ea: `0x180010a70`
- end: `0x180010b04`
- name: `TaskDialog`
- size: `148`
- prototype: `HRESULT __stdcall(HWND hwndOwner, HINSTANCE hInstance, PCWSTR pszWindowTitle, PCWSTR pszMainInstruction, PCWSTR pszContent, TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons, PCWSTR pszIcon, int *pnButton)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b4d0`

## callees

- `0x180010a70`
- `0x180010b0c`
- `0x180017010`

## string_xrefs

- `0x180010a92`: `TaskDialog`

## pseudocode

```c
HRESULT __stdcall TaskDialog(
        HWND hwndOwner,
        HINSTANCE hInstance,
        PCWSTR pszWindowTitle,
        PCWSTR pszMainInstruction,
        PCWSTR pszContent,
        TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons,
        PCWSTR pszIcon,
        int *pnButton)
{
  __int64 (__fastcall *v8)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *); // rax

  v8 = (__int64 (__fastcall *)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *))qword_1800203F8;
  if ( qword_1800203F8 == -1 )
  {
    GetProcFromComCtl32(&qword_1800203F8, "TaskDialog");
    v8 = (__int64 (__fastcall *)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *))qword_1800203F8;
  }
  if ( v8 )
    return v8(hwndOwner, hInstance, pszWindowTitle, pszMainInstruction, pszContent, dwCommonButtons, pszIcon, pnButton);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180010a70  push    rbx
0x180010a72  push    rbp
0x180010a73  push    rsi
0x180010a74  push    rdi
0x180010a75  sub     rsp, 58h
0x180010a79  mov     rax, cs:qword_1800203F8
0x180010a80  mov     rbx, r9
0x180010a83  mov     rdi, r8
0x180010a86  mov     rsi, rdx
0x180010a89  mov     rbp, rcx
0x180010a8c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010a90  jnz     short loc_180010AAC
0x180010a92  lea     rdx, aTaskdialog; "TaskDialog"
0x180010a99  lea     rcx, qword_1800203F8
0x180010aa0  call    _GetProcFromComCtl32
0x180010aa5  mov     rax, cs:qword_1800203F8
0x180010aac  test    rax, rax
0x180010aaf  jz      short loc_180010AF6
0x180010ab1  mov     rcx, [rsp+78h+pnButton]
0x180010ab9  mov     r9, rbx
0x180010abc  mov     [rsp+78h+var_40], rcx
0x180010ac1  mov     r8, rdi
0x180010ac4  mov     rcx, [rsp+78h+pszIcon]
0x180010acc  mov     rdx, rsi
0x180010acf  mov     [rsp+78h+var_48], rcx
0x180010ad4  mov     ecx, [rsp+78h+dwCommonButtons]
0x180010adb  mov     [rsp+78h+var_50], ecx
0x180010adf  mov     rcx, [rsp+78h+pszContent]
0x180010ae7  mov     [rsp+78h+var_58], rcx
0x180010aec  mov     rcx, rbp
0x180010aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010af4  jmp     short loc_180010AFB
0x180010af6  mov     eax, 80004005h
0x180010afb  add     rsp, 58h
0x180010aff  pop     rdi
0x180010b00  pop     rsi
0x180010b01  pop     rbp
0x180010b02  pop     rbx
0x180010b03  retn
```

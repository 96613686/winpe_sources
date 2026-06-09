# TelemetryData_CreateReport

- ea: `0x1400578e0`
- end: `0x140057a54`
- name: `TelemetryData_CreateReport`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140042d88`

## callees

- `0x140045064`
- `0x1400578e0`
- `0x140059970`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057a09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a1d`
- `ntoskrnl!ExAllocatePool2` at `0x14005792c`
- `ntoskrnl!ExAllocatePool2` at `0x140057964`
- `ntoskrnl!ExAllocatePool2` at `0x14005792c`
- `ntoskrnl!ExAllocatePool2` at `0x140057964`
- `ntoskrnl!RtlCaptureContext` at `0x1400579a4`
- `ntoskrnl!RtlCaptureContext` at `0x1400579a4`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x1400579e7`
- `ntoskrnl!KeCapturePersistentThreadState` at `0x1400579e7`

## pseudocode

```c
__int64 *__fastcall TelemetryData_CreateReport(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 *Pool2; // rax
  __int64 *v9; // rbx
  __int64 v10; // rax
  int v11; // eax
  CONTEXT ContextRecord; // [rsp+40h] [rbp-4E8h] BYREF

  memset(&ContextRecord, 0, sizeof(ContextRecord));
  Pool2 = (__int64 *)ExAllocatePool2(64, 1256, 1952531540);
  v9 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x4E8u);
    v10 = ExAllocatePool2(64, 0x40000, 1952531540);
    *v9 = v10;
    if ( v10
      && RtlStringCbPrintfW((NTSTRSAFE_PWSTR)v9 + 312, 0x20u, L"%ws", L"USBXHCI") >= 0
      && (RtlCaptureContext(&ContextRecord),
          (v11 = KeCapturePersistentThreadState(&ContextRecord, 0, 324, a3, a4, a5, a6, *v9)) != 0) )
    {
      *((_DWORD *)v9 + 2) = v11;
    }
    else
    {
      if ( *v9 )
        ExFreePoolWithTag((PVOID)*v9, 0x74614454u);
      ExFreePoolWithTag(v9, 0x74614454u);
      return 0;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1400578e0  mov     [rsp+arg_0], rbx
0x1400578e5  mov     [rsp+arg_8], rsi
0x1400578ea  push    rdi
0x1400578eb  sub     rsp, 520h
0x1400578f2  mov     rax, cs:__security_cookie
0x1400578f9  xor     rax, rsp
0x1400578fc  mov     [rsp+528h+var_18], rax
0x140057904  mov     rdi, r8
0x140057907  lea     rcx, [rsp+528h+ContextRecord]; void *
0x14005790c  mov     r8d, 4D0h; Size
0x140057912  xor     edx, edx; Val
0x140057914  mov     rsi, r9
0x140057917  call    memset
0x14005791c  mov     edx, 4E8h
0x140057921  mov     ecx, 40h ; '@'
0x140057926  mov     r8d, 74614454h
0x14005792c  call    cs:__imp_ExAllocatePool2
0x140057933  nop     dword ptr [rax+rax+00h]
0x140057938  mov     rbx, rax
0x14005793b  test    rax, rax
0x14005793e  jz      loc_140057A2B
0x140057944  xor     edx, edx; Val
0x140057946  mov     r8d, 4E8h; Size
0x14005794c  mov     rcx, rax; void *
0x14005794f  call    memset
0x140057954  mov     edx, 40000h
0x140057959  mov     ecx, 40h ; '@'
0x14005795e  mov     r8d, 74614454h
0x140057964  call    cs:__imp_ExAllocatePool2
0x14005796b  nop     dword ptr [rax+rax+00h]
0x140057970  mov     [rbx], rax
0x140057973  test    rax, rax
0x140057976  jz      loc_1400579FC
0x14005797c  lea     rcx, [rbx+270h]; pszDest
0x140057983  mov     edx, 20h ; ' '; cbDest
0x140057988  lea     r9, aUsbxhci; "USBXHCI"
0x14005798f  lea     r8, aWs; "%ws"
0x140057996  call    RtlStringCbPrintfW
0x14005799b  test    eax, eax
0x14005799d  js      short loc_1400579FC
0x14005799f  lea     rcx, [rsp+528h+ContextRecord]; ContextRecord
0x1400579a4  call    cs:__imp_RtlCaptureContext
0x1400579ab  nop     dword ptr [rax+rax+00h]
0x1400579b0  mov     rax, [rbx]
0x1400579b3  lea     rcx, [rsp+528h+ContextRecord]
0x1400579b8  mov     [rsp+528h+var_4F0], rax
0x1400579bd  mov     r9, rdi
0x1400579c0  mov     rax, [rsp+528h+arg_28]
0x1400579c8  xor     edx, edx
0x1400579ca  mov     [rsp+528h+var_4F8], rax
0x1400579cf  mov     r8d, 144h
0x1400579d5  mov     rax, [rsp+528h+arg_20]
0x1400579dd  mov     [rsp+528h+var_500], rax
0x1400579e2  mov     [rsp+528h+var_508], rsi
0x1400579e7  call    cs:__imp_KeCapturePersistentThreadState
0x1400579ee  nop     dword ptr [rax+rax+00h]
0x1400579f3  test    eax, eax
0x1400579f5  jz      short loc_1400579FC
0x1400579f7  mov     [rbx+8], eax
0x1400579fa  jmp     short loc_140057A2B
0x1400579fc  mov     rcx, [rbx]; P
0x1400579ff  test    rcx, rcx
0x140057a02  jz      short loc_140057A15
0x140057a04  mov     edx, 74614454h; Tag
0x140057a09  call    cs:__imp_ExFreePoolWithTag
0x140057a10  nop     dword ptr [rax+rax+00h]
0x140057a15  mov     edx, 74614454h; Tag
0x140057a1a  mov     rcx, rbx; P
0x140057a1d  call    cs:__imp_ExFreePoolWithTag
0x140057a24  nop     dword ptr [rax+rax+00h]
0x140057a29  xor     ebx, ebx
0x140057a2b  mov     rax, rbx
0x140057a2e  mov     rcx, [rsp+528h+var_18]
0x140057a36  xor     rcx, rsp; StackCookie
0x140057a39  call    __security_check_cookie
0x140057a3e  lea     r11, [rsp+528h+var_8]
0x140057a46  mov     rbx, [r11+10h]
0x140057a4a  mov     rsi, [r11+18h]
0x140057a4e  mov     rsp, r11
0x140057a51  pop     rdi
0x140057a52  retn
```

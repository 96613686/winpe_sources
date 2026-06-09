# BfspValidateDeviceOptions

- ea: `0x140009528`
- end: `0x140009651`
- name: `BfspValidateDeviceOptions`
- size: `297`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140009170`

## callees

- `0x140006a14`
- `0x140009170`
- `0x140009528`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009616`
- `KERNEL32!HeapFree` at `0x14000962f`
- `KERNEL32!HeapFree` at `0x140009616`
- `KERNEL32!HeapFree` at `0x14000962f`
- `KERNEL32!GetProcessHeap` at `0x140009607`
- `KERNEL32!GetProcessHeap` at `0x140009621`
- `KERNEL32!GetProcessHeap` at `0x140009607`
- `KERNEL32!GetProcessHeap` at `0x140009621`

## string_xrefs

- `0x1400095e6`: `OVERLAY_CONFIG_PATH missing`

## pseudocode

```c
__int64 __fastcall BfspValidateDeviceOptions(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  void *v4; // rdi
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  HANDLE Handle; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-20h] BYREF
  LPVOID v12[3]; // [rsp+40h] [rbp-18h] BYREF
  int v13; // [rsp+98h] [rbp+40h] BYREF

  v13 = 0;
  v4 = 0;
  Handle = 0;
  v12[0] = 0;
  lpMem = 0;
  if ( (int)BcdOpenObject(a1, a2, &Handle) < 0 )
  {
    v6 = 0;
    goto LABEL_13;
  }
  if ( (int)BfspGetBcdElementData((__int64)Handle, 0x31000024u, &lpMem, &v13) < 0 )
    goto LABEL_8;
  if ( (int)BfspGetBcdElementData((__int64)Handle, 0x32000025u, v12, &v13) < 0 || !v13 )
  {
    BfspLogMessage(2, L"OVERLAY_CONFIG_PATH missing");
    *a3 = 0;
    v4 = v12[0];
LABEL_8:
    v6 = 0;
    goto LABEL_9;
  }
  v4 = v12[0];
  v6 = BfspValidateDevice(a1, (__int64)Handle, (__int64)lpMem, (__int64)v12[0], a3);
  BfspLogMessage(2, L"Done validating device options. Valid=%c", *a3 != 0 ? 89 : 78);
LABEL_9:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v4 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v4);
  }
LABEL_13:
  if ( Handle )
    BcdCloseObject(Handle);
  return v6;
}

```

## disassembly

```asm
0x140009528  push    rbp
0x14000952a  push    rbx
0x14000952b  push    rdi
0x14000952c  push    r15
0x14000952e  mov     rbp, rsp
0x140009531  sub     rsp, 58h
0x140009535  mov     r15, r8
0x140009538  mov     [rbp+arg_18], 0
0x14000953f  xor     edi, edi
0x140009541  mov     [rbp+Handle], 0
0x140009549  lea     r8, [rbp+Handle]
0x14000954d  mov     [rbp+var_18], rdi
0x140009551  mov     rbx, rcx
0x140009554  mov     [rbp+lpMem], 0
0x14000955c  call    BcdOpenObject
0x140009561  test    eax, eax
0x140009563  jns     short loc_14000956C
0x140009565  xor     ebx, ebx
0x140009567  jmp     loc_140009635
0x14000956c  mov     rcx, [rbp+Handle]
0x140009570  lea     r9, [rbp+arg_18]
0x140009574  lea     r8, [rbp+lpMem]
0x140009578  mov     edx, 31000024h
0x14000957d  call    BfspGetBcdElementData
0x140009582  test    eax, eax
0x140009584  js      short loc_1400095FE
0x140009586  mov     rcx, [rbp+Handle]
0x14000958a  lea     r9, [rbp+arg_18]
0x14000958e  lea     r8, [rbp+var_18]
0x140009592  mov     edx, 32000025h
0x140009597  call    BfspGetBcdElementData
0x14000959c  test    eax, eax
0x14000959e  js      short loc_1400095E6
0x1400095a0  cmp     [rbp+arg_18], edi
0x1400095a3  jz      short loc_1400095E6
0x1400095a5  mov     rdi, [rbp+var_18]
0x1400095a9  mov     rcx, rbx
0x1400095ac  mov     r8, [rbp+lpMem]
0x1400095b0  mov     r9, rdi
0x1400095b3  mov     rdx, [rbp+Handle]
0x1400095b7  mov     [rsp+58h+var_38], r15
0x1400095bc  call    BfspValidateDevice
0x1400095c1  mov     ecx, [r15]
0x1400095c4  lea     rdx, aDoneValidating; "Done validating device options. Valid=%"...
0x1400095cb  neg     ecx
0x1400095cd  mov     ebx, eax
0x1400095cf  mov     ecx, 2
0x1400095d4  sbb     r8d, r8d
0x1400095d7  and     r8d, 0Bh
0x1400095db  add     r8d, 4Eh ; 'N'
0x1400095df  call    BfspLogMessage
0x1400095e4  jmp     short loc_140009600
0x1400095e6  lea     rdx, aOverlayConfigP; "OVERLAY_CONFIG_PATH missing"
0x1400095ed  mov     ecx, 2
0x1400095f2  call    BfspLogMessage
0x1400095f7  mov     [r15], edi
0x1400095fa  mov     rdi, [rbp+var_18]
0x1400095fe  xor     ebx, ebx
0x140009600  cmp     [rbp+lpMem], 0
0x140009605  jz      short loc_14000961C
0x140009607  call    cs:__imp_GetProcessHeap
0x14000960d  mov     r8, [rbp+lpMem]; lpMem
0x140009611  xor     edx, edx; dwFlags
0x140009613  mov     rcx, rax; hHeap
0x140009616  call    cs:__imp_HeapFree
0x14000961c  test    rdi, rdi
0x14000961f  jz      short loc_140009635
0x140009621  call    cs:__imp_GetProcessHeap
0x140009627  mov     r8, rdi; lpMem
0x14000962a  xor     edx, edx; dwFlags
0x14000962c  mov     rcx, rax; hHeap
0x14000962f  call    cs:__imp_HeapFree
0x140009635  cmp     [rbp+Handle], 0
0x14000963a  jz      short loc_140009645
0x14000963c  mov     rcx, [rbp+Handle]; Handle
0x140009640  call    BcdCloseObject
0x140009645  mov     eax, ebx
0x140009647  add     rsp, 58h
0x14000964b  pop     r15
0x14000964d  pop     rdi
0x14000964e  pop     rbx
0x14000964f  pop     rbp
0x140009650  retn
```

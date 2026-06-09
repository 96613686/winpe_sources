# VfsPreWriteEx

- ea: `0x1400017e0`
- end: `0x1400018bb`
- name: `VfsPreWriteEx`
- size: `219`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001090`
- `0x1400017e0`
- `0x14000b1f0`
- `0x14000f124`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14000181b`
- `ntoskrnl!EtwActivityIdControl` at `0x14000181b`

## pseudocode

```c
__int64 __fastcall VfsPreWriteEx(PFLT_CALLBACK_DATA Data, __int64 a2, PFILE_OBJECT *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  GUID ActivityId; // [rsp+30h] [rbp-38h] BYREF

  ActivityId = GUID_NULL;
  if ( EtwActivityIdControl(1u, &ActivityId) < 0 )
    ActivityId = GUID_NULL;
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)VFSC_PreWriteStart, &ActivityId);
  v7 = 1;
  if ( (unsigned __int8)VfsDecodeFileObject(*(_QWORD *)(a2 + 32), 0, 0) )
    v7 = VfsWriteWorker(Data, a2, a3, 1, 0);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)VFSC_PreWriteFinish, &ActivityId);
  return v7;
}

```

## disassembly

```asm
0x1400017e0  mov     [rsp+arg_18], rbx
0x1400017e5  push    rbp
0x1400017e6  push    rsi
0x1400017e7  push    rdi
0x1400017e8  sub     rsp, 50h
0x1400017ec  mov     rax, cs:__security_cookie
0x1400017f3  xor     rax, rsp
0x1400017f6  mov     [rsp+68h+var_28], rax
0x1400017fb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001802  mov     rdi, rdx
0x140001805  mov     rsi, rcx
0x140001808  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x14000180d  mov     ecx, 1; ControlCode
0x140001812  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x140001818  mov     rbp, r8
0x14000181b  call    cs:__imp_EtwActivityIdControl
0x140001822  nop     dword ptr [rax+rax+00h]
0x140001827  test    eax, eax
0x140001829  jns     short loc_140001838
0x14000182b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001832  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x140001838  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000183f  jz      short loc_140001852
0x140001841  lea     r8, [rsp+68h+ActivityId]
0x140001846  lea     rdx, VFSC_PreWriteStart
0x14000184d  call    McTemplateK0_EtwWriteTransfer
0x140001852  mov     rcx, [rdi+20h]
0x140001856  xor     r8d, r8d
0x140001859  xor     edx, edx
0x14000185b  mov     ebx, 1
0x140001860  call    VfsDecodeFileObject
0x140001865  test    al, al
0x140001867  jz      short loc_140001881
0x140001869  mov     r9b, bl
0x14000186c  mov     [rsp+68h+var_48], 0; char
0x140001871  mov     r8, rbp
0x140001874  mov     rdx, rdi
0x140001877  mov     rcx, rsi; Data
0x14000187a  call    VfsWriteWorker
0x14000187f  mov     ebx, eax
0x140001881  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140001888  jz      short loc_14000189B
0x14000188a  lea     r8, [rsp+68h+ActivityId]
0x14000188f  lea     rdx, VFSC_PreWriteFinish
0x140001896  call    McTemplateK0_EtwWriteTransfer
0x14000189b  mov     eax, ebx
0x14000189d  mov     rcx, [rsp+68h+var_28]
0x1400018a2  xor     rcx, rsp; StackCookie
0x1400018a5  call    __security_check_cookie
0x1400018aa  mov     rbx, [rsp+68h+arg_18]
0x1400018b2  add     rsp, 50h
0x1400018b6  pop     rdi
0x1400018b7  pop     rsi
0x1400018b8  pop     rbp
0x1400018b9  retn
```

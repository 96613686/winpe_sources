# SmPreCleanup

- ea: `0x140007270`
- end: `0x140007355`
- name: `SmPreCleanup`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007270`

## import_xrefs

- `ntoskrnl!ZwDeviceIoControlFile` at `0x140007322`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140007322`
- `FLTMGR!FltGetStreamHandleContext` at `0x140007297`
- `FLTMGR!FltGetStreamHandleContext` at `0x140007297`
- `FLTMGR!FltReleaseContext` at `0x140007332`
- `FLTMGR!FltReleaseContext` at `0x140007332`

## pseudocode

```c
__int64 __fastcall SmPreCleanup(__int64 a1, __int64 a2)
{
  int v3; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  _QWORD InputBuffer[3]; // [rsp+60h] [rbp-20h] BYREF
  int v7; // [rsp+78h] [rbp-8h]
  int v8; // [rsp+7Ch] [rbp-4h]
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp+28h] BYREF

  Context = 0;
  if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)Context, 0, 0) )
    {
      InputBuffer[0] = *(_QWORD *)(a2 + 24);
      InputBuffer[1] = *(_QWORD *)(a2 + 32);
      InputBuffer[2] = &off_140004000;
      IoStatusBlock = 0;
      v3 = *((_DWORD *)Context + 1);
      v8 = 0;
      v7 = v3;
      ZwDeviceIoControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x22A018u, InputBuffer, 0x20u, 0, 0);
    }
    FltReleaseContext(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x140007270  mov     [rsp-8+arg_0], rbx
0x140007275  push    rbp
0x140007276  mov     rbp, rsp
0x140007279  sub     rsp, 80h
0x140007280  mov     rbx, rdx
0x140007283  mov     [rbp+Context], 0
0x14000728b  mov     rdx, [rdx+20h]; FileObject
0x14000728f  lea     r8, [rbp+Context]; Context
0x140007293  mov     rcx, [rbx+18h]; Instance
0x140007297  call    cs:__imp_FltGetStreamHandleContext
0x14000729e  nop     dword ptr [rax+rax+00h]
0x1400072a3  test    eax, eax
0x1400072a5  js      loc_14000733E
0x1400072ab  mov     rcx, [rbp+Context]
0x1400072af  xor     edx, edx; Event
0x1400072b1  xor     eax, eax
0x1400072b3  lock cmpxchg [rcx], edx
0x1400072b7  jz      short loc_14000732E
0x1400072b9  mov     rax, [rbx+18h]
0x1400072bd  xorps   xmm0, xmm0
0x1400072c0  mov     [rbp+var_20], rax
0x1400072c4  xor     r9d, r9d; ApcContext
0x1400072c7  mov     rax, [rbx+20h]
0x1400072cb  xor     r8d, r8d; ApcRoutine
0x1400072ce  mov     [rbp+var_18], rax
0x1400072d2  lea     rax, off_140004000
0x1400072d9  mov     [rbp+var_10], rax
0x1400072dd  mov     rax, [rbp+Context]
0x1400072e1  movups  xmmword ptr [rbp+var_30], xmm0
0x1400072e5  mov     ecx, [rax+4]
0x1400072e8  xor     eax, eax
0x1400072ea  mov     [rsp+80h+OutputBufferLength], eax; OutputBufferLength
0x1400072ee  mov     [rsp+80h+OutputBuffer], rax; OutputBuffer
0x1400072f3  mov     [rbp+var_4], eax
0x1400072f6  lea     rax, [rbp+var_20]
0x1400072fa  mov     [rsp+80h+InputBufferLength], 20h ; ' '; InputBufferLength
0x140007302  mov     [rsp+80h+InputBuffer], rax; InputBuffer
0x140007307  lea     rax, [rbp+var_30]
0x14000730b  mov     [rbp+var_8], ecx
0x14000730e  mov     rcx, cs:Handle; FileHandle
0x140007315  mov     [rsp+80h+IoControlCode], 22A018h; IoControlCode
0x14000731d  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x140007322  call    cs:__imp_ZwDeviceIoControlFile
0x140007329  nop     dword ptr [rax+rax+00h]
0x14000732e  mov     rcx, [rbp+Context]; Context
0x140007332  call    cs:__imp_FltReleaseContext
0x140007339  nop     dword ptr [rax+rax+00h]
0x14000733e  mov     rbx, [rsp+80h+arg_0]
0x140007346  mov     eax, 1
0x14000734b  add     rsp, 80h
0x140007352  pop     rbp
0x140007353  retn
```

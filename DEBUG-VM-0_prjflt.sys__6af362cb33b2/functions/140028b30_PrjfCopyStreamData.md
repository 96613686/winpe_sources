# PrjfCopyStreamData

- ea: `0x140028b30`
- end: `0x140028d94`
- name: `PrjfCopyStreamData`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029650`

## callees

- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14000d754`
- `0x140028b30`
- `0x1400349fc`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140028bb1`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140028bb1`
- `ntoskrnl!ObfReferenceObject` at `0x140028c6b`
- `ntoskrnl!ObfReferenceObject` at `0x140028c6b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140028d30`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140028d30`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140028d4f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140028d4f`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140028b8d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140028d1d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140028b8d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140028d1d`
- `FLTMGR!FltReleaseResource` at `0x140028bc9`
- `FLTMGR!FltReleaseResource` at `0x140028c7a`
- `FLTMGR!FltReleaseResource` at `0x140028d5e`
- `FLTMGR!FltReleaseResource` at `0x140028bc9`
- `FLTMGR!FltReleaseResource` at `0x140028c7a`
- `FLTMGR!FltReleaseResource` at `0x140028d5e`

## pseudocode

```c
__int64 __fastcall PrjfCopyStreamData(
        PFLT_INSTANCE Instance,
        __int64 a2,
        __int64 a3,
        struct _FILE_OBJECT *a4,
        __int64 a5,
        __int128 *a6)
{
  __int128 v9; // xmm0
  struct _ERESOURCE *v10; // rdi
  PVOID *inserted; // rax
  int v12; // edx
  int v13; // r8d
  int FileStreamCommand; // ebx
  PVOID v15; // rcx
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-69h]
  unsigned __int8 NewElement[8]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v22; // [rsp+68h] [rbp-21h]
  __int128 Buffer; // [rsp+70h] [rbp-19h] BYREF
  PVOID Object; // [rsp+80h] [rbp-9h]
  __int64 v25; // [rsp+88h] [rbp-1h]

  v25 = 0;
  NewElement[0] = 0;
  v9 = *a6;
  v10 = (struct _ERESOURCE *)(a5 + 96);
  Object = a4;
  Buffer = v9;
  FltAcquireResourceExclusive((PERESOURCE)(a5 + 96));
  inserted = (PVOID *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a5 + 200), &Buffer, 0x20u, NewElement);
  if ( inserted )
  {
    if ( NewElement[0] )
    {
      v15 = Object;
      if ( Object != inserted[2] )
      {
        MicrosoftTelemetryAssertTriggeredNoArgsKM(Object);
        v15 = Object;
      }
      ObfReferenceObject(v15);
    }
    FltReleaseResource(v10);
    v22 = a2;
    FileStreamCommand = PrjfSendGetFileStreamCommand(Instance, a4, v20);
    if ( FileStreamCommand < 0
      && ((BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 4;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        522,
        v16,
        v17,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        16,
        (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        127,
        FileStreamCommand,
        (__int64)&a4->FileName);
    }
    FltAcquireResourceExclusive(v10);
    if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a5 + 200), &Buffer) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v18);
    if ( NewElement[0] )
      ObDereferenceObjectDeferDelete(Object);
    FltReleaseResource(v10);
  }
  else
  {
    FltReleaseResource(v10);
    FileStreamCommand = -1073741670;
    if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 4;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        522,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        15,
        (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        90,
        154);
    }
  }
  return (unsigned int)FileStreamCommand;
}

```

## disassembly

```asm
0x140028b30  mov     [rsp-8+arg_8], rbx
0x140028b35  push    rbp
0x140028b36  push    rsi
0x140028b37  push    rdi
0x140028b38  push    r12
0x140028b3a  push    r13
0x140028b3c  push    r14
0x140028b3e  push    r15
0x140028b40  lea     rbp, [rsp-17h]
0x140028b45  sub     rsp, 0A0h
0x140028b4c  mov     rax, cs:__security_cookie
0x140028b53  xor     rax, rsp
0x140028b56  mov     [rbp+47h+var_40], rax
0x140028b5a  mov     rax, [rbp+47h+arg_28]
0x140028b5e  mov     r13, rcx
0x140028b61  mov     rbx, [rbp+47h+arg_20]
0x140028b65  mov     rsi, r9
0x140028b68  mov     r15d, r8d
0x140028b6b  mov     [rbp+47h+var_48], 0
0x140028b73  mov     r12, rdx
0x140028b76  mov     [rbp+47h+NewElement], 0
0x140028b7a  movaps  xmm0, xmmword ptr [rax]
0x140028b7d  lea     rdi, [rbx+60h]
0x140028b81  mov     [rbp+47h+Object], r9
0x140028b85  mov     rcx, rdi; Resource
0x140028b88  movdqu  [rbp+47h+Buffer], xmm0
0x140028b8d  call    cs:__imp_FltAcquireResourceExclusive
0x140028b94  nop     dword ptr [rax+rax+00h]
0x140028b99  lea     r14, [rbx+0C8h]
0x140028ba0  mov     r8d, 20h ; ' '; BufferSize
0x140028ba6  mov     rcx, r14; Table
0x140028ba9  lea     r9, [rbp+47h+NewElement]; NewElement
0x140028bad  lea     rdx, [rbp+47h+Buffer]; Buffer
0x140028bb1  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140028bb8  nop     dword ptr [rax+rax+00h]
0x140028bbd  test    rax, rax
0x140028bc0  jnz     loc_140028C52
0x140028bc6  mov     rcx, rdi; Resource
0x140028bc9  call    cs:__imp_FltReleaseResource
0x140028bd0  nop     dword ptr [rax+rax+00h]
0x140028bd5  mov     ebx, 0C000009Ah
0x140028bda  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140028be0  lea     rax, WPP_RECORDER_INITIALIZED
0x140028be7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028bee  setnz   r8b
0x140028bf2  and     dl, 4
0x140028bf5  jnz     short loc_140028C00
0x140028bf7  test    r8b, r8b
0x140028bfa  jz      loc_140028D6A
0x140028c00  mov     r9, cs:WPP_GLOBAL_Control
0x140028c07  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140028c0e  mov     [rsp+0D0h+var_80], ebx
0x140028c12  mov     ecx, 20Ah
0x140028c17  mov     [rsp+0D0h+var_88], 35Ah
0x140028c1f  mov     [rsp+0D0h+var_90], rax
0x140028c24  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140028c2b  mov     r9, [r9+40h]
0x140028c2f  mov     [rsp+0D0h+var_98], rax
0x140028c34  mov     [rsp+0D0h+var_A0], 0Fh
0x140028c3b  mov     [rsp+0D0h+var_A8], 0Ah
0x140028c43  mov     [rsp+0D0h+var_B0], 2
0x140028c48  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140028c4d  jmp     loc_140028D6A
0x140028c52  cmp     [rbp+47h+NewElement], 0
0x140028c56  jz      short loc_140028C77
0x140028c58  mov     rcx, [rbp+47h+Object]
0x140028c5c  cmp     rcx, [rax+10h]
0x140028c60  jz      short loc_140028C6B
0x140028c62  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140028c67  mov     rcx, [rbp+47h+Object]; Object
0x140028c6b  call    cs:__imp_ObfReferenceObject
0x140028c72  nop     dword ptr [rax+rax+00h]
0x140028c77  mov     rcx, rdi; Resource
0x140028c7a  call    cs:__imp_FltReleaseResource
0x140028c81  nop     dword ptr [rax+rax+00h]
0x140028c86  mov     r9d, r15d
0x140028c89  mov     [rbp+47h+var_68], r12
0x140028c8d  lea     r8, [rbp+47h+var_68]
0x140028c91  mov     rdx, rsi; FileObject
0x140028c94  mov     rcx, r13; Instance
0x140028c97  call    PrjfSendGetFileStreamCommand
0x140028c9c  mov     ebx, eax
0x140028c9e  test    eax, eax
0x140028ca0  jns     short loc_140028D1A
0x140028ca2  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140028ca8  lea     rax, WPP_RECORDER_INITIALIZED
0x140028caf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140028cb6  setnz   r8b
0x140028cba  and     dl, 4
0x140028cbd  jnz     short loc_140028CC4
0x140028cbf  test    r8b, r8b
0x140028cc2  jz      short loc_140028D1A
0x140028cc4  mov     r9, cs:WPP_GLOBAL_Control
0x140028ccb  lea     rax, [rsi+58h]
0x140028ccf  mov     [rsp+0D0h+var_78], rax
0x140028cd4  mov     ecx, 20Ah
0x140028cd9  mov     [rsp+0D0h+var_80], ebx
0x140028cdd  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140028ce4  mov     [rsp+0D0h+var_88], 37Fh
0x140028cec  mov     r9, [r9+40h]
0x140028cf0  mov     [rsp+0D0h+var_90], rax
0x140028cf5  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140028cfc  mov     [rsp+0D0h+var_98], rax
0x140028d01  mov     [rsp+0D0h+var_A0], 10h
0x140028d08  mov     [rsp+0D0h+var_A8], 0Ah
0x140028d10  mov     [rsp+0D0h+var_B0], 2
0x140028d15  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140028d1a  mov     rcx, rdi; Resource
0x140028d1d  call    cs:__imp_FltAcquireResourceExclusive
0x140028d24  nop     dword ptr [rax+rax+00h]
0x140028d29  lea     rdx, [rbp+47h+Buffer]; Buffer
0x140028d2d  mov     rcx, r14; Table
0x140028d30  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140028d37  nop     dword ptr [rax+rax+00h]
0x140028d3c  test    al, al
0x140028d3e  jnz     short loc_140028D45
0x140028d40  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140028d45  cmp     [rbp+47h+NewElement], 0
0x140028d49  jz      short loc_140028D5B
0x140028d4b  mov     rcx, [rbp+47h+Object]; Object
0x140028d4f  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140028d56  nop     dword ptr [rax+rax+00h]
0x140028d5b  mov     rcx, rdi; Resource
0x140028d5e  call    cs:__imp_FltReleaseResource
0x140028d65  nop     dword ptr [rax+rax+00h]
0x140028d6a  mov     eax, ebx
0x140028d6c  mov     rcx, [rbp+47h+var_40]
0x140028d70  xor     rcx, rsp; StackCookie
0x140028d73  call    __security_check_cookie
0x140028d78  mov     rbx, [rsp+0D0h+arg_8]
0x140028d80  add     rsp, 0A0h
0x140028d87  pop     r15
0x140028d89  pop     r14
0x140028d8b  pop     r13
0x140028d8d  pop     r12
0x140028d8f  pop     rdi
0x140028d90  pop     rsi
0x140028d91  pop     rbp
0x140028d92  retn
```

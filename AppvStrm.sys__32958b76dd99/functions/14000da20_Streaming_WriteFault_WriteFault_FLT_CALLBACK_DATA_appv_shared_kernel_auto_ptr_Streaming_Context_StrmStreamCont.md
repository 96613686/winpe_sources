# Streaming::WriteFault::WriteFault(_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,long &)

- ea: `0x14000da20`
- end: `0x14000db17`
- name: `??0WriteFault@Streaming@@QEAA@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@AEAJ@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, PFLT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000de2c`

## callees

- `0x14000a1ac`
- `0x14000da20`
- `0x140014c40`
- `0x1400153c4`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14000da4b`
- `ntoskrnl!EtwActivityIdControl` at `0x14000da4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da8d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000da8d`
- `FLTMGR!FltReferenceContext` at `0x14000da9c`
- `FLTMGR!FltReferenceContext` at `0x14000da9c`
- `FLTMGR!FltReleaseContext` at `0x14000dab3`
- `FLTMGR!FltReleaseContext` at `0x14000dab3`

## string_xrefs

- `0x14000dae7`: `Failed to retrieve directory context. Directory path %s, error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::WriteFault::WriteFault(
        __int64 a1,
        struct _FLT_CALLBACK_DATA *a2,
        PFLT_CONTEXT *a3,
        int *a4)
{
  PFLT_CONTEXT v8; // rsi
  int ProcessAndUserNotSystem; // eax
  _OWORD *v10; // rcx
  int v12; // [rsp+20h] [rbp-58h]
  _OWORD v13[4]; // [rsp+30h] [rbp-48h] BYREF

  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)a1 = 0;
  EtwActivityIdControl(3u, (LPGUID)(a1 + 16));
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_LOAD_FILE_START,
      a1 + 16);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 48), 0);
  FltReferenceContext(*a3);
  v8 = *a3;
  if ( *(_QWORD *)a1 )
    FltReleaseContext(*(PFLT_CONTEXT *)a1);
  *(_QWORD *)a1 = v8;
  ProcessAndUserNotSystem = Streaming::Utils::GetProcessAndUserNotSystem(a2);
  *a4 = ProcessAndUserNotSystem;
  if ( ProcessAndUserNotSystem < 0 )
  {
    v10 = *(_OWORD **)a1;
    v12 = ProcessAndUserNotSystem;
    v13[0] = *(_OWORD *)(*(_QWORD *)a1 + 16LL);
    v13[1] = v10[2];
    LogWrite(2, 0, L"Failed to retrieve directory context. Directory path %s, error code 0x%08X.", v13, v12);
  }
  return a1;
}

```

## disassembly

```asm
0x14000da20  push    rbx
0x14000da22  push    rbp
0x14000da23  push    rsi
0x14000da24  push    rdi
0x14000da25  push    r14
0x14000da27  sub     rsp, 50h
0x14000da2b  mov     [rcx+8], rdx
0x14000da2f  mov     rbp, rdx
0x14000da32  lea     rdx, [rcx+10h]; ActivityId
0x14000da36  mov     qword ptr [rcx], 0
0x14000da3d  mov     rbx, rcx
0x14000da40  mov     r14, r9
0x14000da43  mov     ecx, 3; ControlCode
0x14000da48  mov     rsi, r8
0x14000da4b  call    cs:__imp_EtwActivityIdControl
0x14000da52  nop     dword ptr [rax+rax+00h]
0x14000da57  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000da5e  jz      short loc_14000DA77
0x14000da60  lea     r8, [rbx+10h]
0x14000da64  lea     rdx, StrmFlt_LOAD_FILE_START
0x14000da6b  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000da72  call    McTemplateK0_EtwWriteTransfer
0x14000da77  lea     rcx, [rbx+30h]; DestinationString
0x14000da7b  mov     qword ptr [rbx+20h], 0
0x14000da83  xor     edx, edx; SourceString
0x14000da85  mov     qword ptr [rbx+28h], 0
0x14000da8d  call    cs:__imp_RtlInitUnicodeString
0x14000da94  nop     dword ptr [rax+rax+00h]
0x14000da99  mov     rcx, [rsi]; Context
0x14000da9c  call    cs:__imp_FltReferenceContext
0x14000daa3  nop     dword ptr [rax+rax+00h]
0x14000daa8  mov     rcx, [rbx]; Context
0x14000daab  mov     rsi, [rsi]
0x14000daae  test    rcx, rcx
0x14000dab1  jz      short loc_14000DABF
0x14000dab3  call    cs:__imp_FltReleaseContext
0x14000daba  nop     dword ptr [rax+rax+00h]
0x14000dabf  lea     r8, [rbx+40h]
0x14000dac3  mov     [rbx], rsi
0x14000dac6  lea     rdx, [rbx+20h]
0x14000daca  mov     rcx, rbp; CallbackData
0x14000dacd  call    ?GetProcessAndUserNotSystem@Utils@Streaming@@YAJAEAU_FLT_CALLBACK_DATA@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z; Streaming::Utils::GetProcessAndUserNotSystem(_FLT_CALLBACK_DATA &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)
0x14000dad2  mov     [r14], eax
0x14000dad5  test    eax, eax
0x14000dad7  jns     short loc_14000DB08
0x14000dad9  mov     rcx, [rbx]
0x14000dadc  lea     r9, [rsp+78h+var_48]
0x14000dae1  xor     edx, edx
0x14000dae3  mov     [rsp+78h+var_58], eax
0x14000dae7  lea     r8, aFailedToRetrie; "Failed to retrieve directory context. D"...
0x14000daee  movups  xmm0, xmmword ptr [rcx+10h]
0x14000daf2  movaps  [rsp+78h+var_48], xmm0
0x14000daf7  movups  xmm1, xmmword ptr [rcx+20h]
0x14000dafb  lea     ecx, [rdx+2]
0x14000dafe  movaps  [rsp+78h+var_38], xmm1
0x14000db03  call    LogWrite
0x14000db08  mov     rax, rbx
0x14000db0b  add     rsp, 50h
0x14000db0f  pop     r14
0x14000db11  pop     rdi
0x14000db12  pop     rsi
0x14000db13  pop     rbp
0x14000db14  pop     rbx
0x14000db15  retn
```

# StreamFaultBuffer::StreamFaultBuffer(_FLT_CALLBACK_DATA_QUEUE *,_IO_CSQ_IRP_CONTEXT *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,ulong,long &)

- ea: `0x14000bfe4`
- end: `0x14000c1ce`
- name: `??0StreamFaultBuffer@@QEAA@PEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_IO_CSQ_IRP_CONTEXT@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@456@KAEAJ@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c4ac`

## callees

- `0x1400010b0`
- `0x14000bfe4`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c113`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c113`
- `FLTMGR!FltLockUserBuffer` at `0x14000c0cc`
- `FLTMGR!FltLockUserBuffer` at `0x14000c0cc`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000c031`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000c031`

## pseudocode

```c
__int64 __fastcall StreamFaultBuffer::StreamFaultBuffer(
        __int64 a1,
        struct _FLT_CALLBACK_DATA_QUEUE *a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        NTSTATUS *a7)
{
  PFLT_CALLBACK_DATA v8; // rax
  __int64 v9; // rbx
  __int64 *CurrentActivityID; // rax
  NTSTATUS v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  PVOID v14; // rax
  _BYTE v16[16]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-28h] BYREF

  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = a6;
  *(_DWORD *)(a1 + 12) = a6;
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = a4;
  *(_QWORD *)(a1 + 40) = a5;
  v8 = FltCbdqRemoveNextIo(a2, a3);
  if ( v8 )
  {
    *(_QWORD *)a1 = v8;
    *a7 = 0;
    if ( v8->Iopb->Parameters.Create.EaBuffer
      || (v8->Flags & 8) != 0
      || (v11 = FltLockUserBuffer(v8), *a7 = v11, v11 >= 0) )
    {
      v12 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
      v13 = *(_QWORD *)(v12 + 56);
      if ( v13 )
      {
        if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
          v14 = *(PVOID *)(v13 + 24);
        else
          v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x10u);
      }
      else
      {
        v14 = *(PVOID *)(v12 + 48);
      }
      *(_QWORD *)(a1 + 24) = v14;
      if ( !v14 )
        *a7 = -1073741670;
    }
  }
  else
  {
    v9 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v17, *(_QWORD *)(a1 + 40) + 16LL);
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v16);
    LogWrite(
      2,
      *CurrentActivityID,
      L"StreamFaultBuffer::StreamFaultBuffer() - Stream fault was cancelled. File name: %s, Offset: %lld, Length %ld, Status 0x%08X.",
      v9,
      0,
      0,
      -1073741536);
    kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(v16);
    kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(v17);
    *a7 = -1073741536;
  }
  return a1;
}

```

## disassembly

```asm
0x14000bfe4  mov     [rsp+arg_8], rbx
0x14000bfe9  mov     [rsp+arg_10], rsi
0x14000bfee  mov     [rsp+arg_0], rcx
0x14000bff3  push    rdi
0x14000bff4  push    r14
0x14000bff6  push    r15
0x14000bff8  sub     rsp, 60h
0x14000bffc  mov     r10, rdx
0x14000bfff  mov     r15, rcx
0x14000c002  xor     esi, esi
0x14000c004  mov     [rcx], rsi
0x14000c007  mov     eax, [rsp+78h+arg_28]
0x14000c00e  mov     [rcx+8], eax
0x14000c011  mov     [rcx+0Ch], eax
0x14000c014  mov     [rcx+10h], esi
0x14000c017  mov     [rcx+18h], rsi
0x14000c01b  mov     [rcx+20h], r9
0x14000c01f  mov     rax, [rsp+78h+arg_20]
0x14000c027  mov     [rcx+28h], rax
0x14000c02b  mov     rdx, r8; PeekContext
0x14000c02e  mov     rcx, r10; Cbdq
0x14000c031  call    cs:__imp_FltCbdqRemoveNextIo
0x14000c038  nop     dword ptr [rax+rax+00h]
0x14000c03d  mov     rcx, rax; CallbackData
0x14000c040  test    rax, rax
0x14000c043  jnz     short loc_14000C0AF
0x14000c045  mov     rdx, [r15+28h]
0x14000c049  add     rdx, 10h
0x14000c04d  lea     rcx, [rsp+78h+var_28]
0x14000c052  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000c057  mov     rbx, [rax]
0x14000c05a  lea     rcx, [rsp+78h+var_38]
0x14000c05f  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000c064  mov     edi, 0C0000120h
0x14000c069  mov     [rsp+78h+var_48], edi
0x14000c06d  mov     qword ptr [rsp+78h+Priority], rsi
0x14000c072  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi
0x14000c077  mov     r9, rbx
0x14000c07a  lea     r8, aStreamfaultbuf_0; "StreamFaultBuffer::StreamFaultBuffer() "...
0x14000c081  mov     rdx, [rax]
0x14000c084  lea     ecx, [rsi+2]
0x14000c087  call    LogWrite
0x14000c08c  lea     rcx, [rsp+78h+var_38]
0x14000c091  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000c096  lea     rcx, [rsp+78h+var_28]
0x14000c09b  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000c0a0  mov     rax, [rsp+78h+arg_30]
0x14000c0a8  mov     [rax], edi
0x14000c0aa  jmp     loc_14000C1B4
0x14000c0af  mov     [r15], rcx
0x14000c0b2  mov     rbx, [rsp+78h+arg_30]
0x14000c0ba  mov     [rbx], esi
0x14000c0bc  mov     rax, [rax+10h]
0x14000c0c0  cmp     [rax+38h], rsi
0x14000c0c4  jnz     short loc_14000C0E2
0x14000c0c6  mov     eax, [rcx]
0x14000c0c8  test    al, 8
0x14000c0ca  jnz     short loc_14000C0E2
0x14000c0cc  call    cs:__imp_FltLockUserBuffer
0x14000c0d3  nop     dword ptr [rax+rax+00h]
0x14000c0d8  mov     [rbx], eax
0x14000c0da  test    eax, eax
0x14000c0dc  js      loc_14000C1B4
0x14000c0e2  mov     rax, [r15]
0x14000c0e5  mov     rax, [rax+10h]
0x14000c0e9  mov     rcx, [rax+38h]; MemoryDescriptorList
0x14000c0ed  test    rcx, rcx
0x14000c0f0  jz      short loc_14000C121
0x14000c0f2  test    byte ptr [rcx+0Ah], 5
0x14000c0f6  jz      short loc_14000C0FE
0x14000c0f8  mov     rax, [rcx+18h]
0x14000c0fc  jmp     short loc_14000C125
0x14000c0fe  mov     [rsp+78h+Priority], 10h; Priority
0x14000c106  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14000c10a  xor     r9d, r9d; RequestedAddress
0x14000c10d  xor     edx, edx; AccessMode
0x14000c10f  lea     r8d, [r9+1]; CacheType
0x14000c113  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c11a  nop     dword ptr [rax+rax+00h]
0x14000c11f  jmp     short loc_14000C125
0x14000c121  mov     rax, [rax+30h]
0x14000c125  mov     [r15+18h], rax
0x14000c129  test    rax, rax
0x14000c12c  jnz     short loc_14000C136
0x14000c12e  mov     dword ptr [rbx], 0C000009Ah
0x14000c134  jmp     short loc_14000C1B4
0x14000c136  jmp     short loc_14000C1B4
0x14000c138  mov     r14d, eax
0x14000c13b  mov     rcx, [rsp+78h+arg_30]
0x14000c143  mov     [rcx], eax
0x14000c145  mov     r15, [rsp+78h+arg_0]
0x14000c14d  mov     rcx, [r15]
0x14000c150  mov     rdx, [rcx+10h]
0x14000c154  mov     esi, [rdx+18h]
0x14000c157  mov     rdi, [rdx+28h]
0x14000c15b  mov     rdx, [r15+28h]
0x14000c15f  add     rdx, 10h
0x14000c163  lea     rcx, [rsp+78h+var_38]
0x14000c168  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000c16d  mov     rbx, [rax]
0x14000c170  lea     rcx, [rsp+78h+var_28]
0x14000c175  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000c17a  mov     [rsp+78h+var_48], r14d
0x14000c17f  mov     [rsp+78h+Priority], esi
0x14000c183  mov     qword ptr [rsp+78h+BugCheckOnFailure], rdi
0x14000c188  mov     r9, rbx
0x14000c18b  lea     r8, aStreamfaultbuf_2; "StreamFaultBuffer::StreamFaultBuffer() "...
0x14000c192  mov     rdx, [rax]
0x14000c195  mov     ecx, 2
0x14000c19a  call    LogWrite
0x14000c19f  lea     rcx, [rsp+78h+var_28]
0x14000c1a4  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000c1a9  lea     rcx, [rsp+78h+var_38]
0x14000c1ae  call    ??1?$shared_ptr@U_GUID@@@kernel_std@@QEAA@XZ; kernel_std::shared_ptr<_GUID>::~shared_ptr<_GUID>(void)
0x14000c1b3  nop
0x14000c1b4  mov     rax, r15
0x14000c1b7  lea     r11, [rsp+78h+var_18]
0x14000c1bc  mov     rbx, [r11+28h]
0x14000c1c0  mov     rsi, [r11+30h]
0x14000c1c4  mov     rsp, r11
0x14000c1c7  pop     r15
0x14000c1c9  pop     r14
0x14000c1cb  pop     rdi
0x14000c1cc  retn
```

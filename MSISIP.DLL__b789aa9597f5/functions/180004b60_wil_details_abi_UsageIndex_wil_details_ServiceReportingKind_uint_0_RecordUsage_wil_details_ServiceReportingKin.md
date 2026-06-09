# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180004b60`
- end: `0x180004c53`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `243`
- prototype: `__int64 __fastcall(wil::details_abi::RawUsageIndex *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000bef0`

## callees

- `0x180004b60`
- `0x180004c5c`
- `0x1800056fc`
- `0x180005950`
- `0x180008344`
- `0x1800085dc`

## pseudocode

```c
char __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        int a2,
        int a3)
{
  void *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v6; // [rsp+40h] [rbp-18h] BYREF
  int v7; // [rsp+68h] [rbp+10h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF

  v8 = a3;
  v7 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &v7, 4u, &v8, 4u, 1u) )
    return 1;
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), 0x28u);
  }
  else
  {
    *(_OWORD *)v5 = 0;
    v6 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v5, 0x32u) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(this, v5[0], 0, v6 - (unsigned __int64)v5[0]);
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=((char *)this + 48, (char *)&v6 + 8);
      *((_BYTE *)this + 58) = 1;
    }
    wistd::unique_ptr<void,wil::process_heap_deleter>::reset((void **)&v6 + 1, 0);
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &v7, 4u, &v8, 4u, 1u);
}

```

## disassembly

```asm
0x180004b60  mov     [rsp+arg_10], r8d
0x180004b65  mov     [rsp+arg_8], edx
0x180004b69  push    rbx
0x180004b6a  sub     rsp, 50h
0x180004b6e  mov     [rsp+58h+var_30], 1; unsigned int
0x180004b76  lea     r9, [rsp+58h+arg_10]; void *
0x180004b7b  mov     r8d, 4; unsigned __int64
0x180004b81  mov     [rsp+58h+var_38], 4; unsigned __int64
0x180004b8a  lea     rdx, [rsp+58h+arg_8]; void *
0x180004b8f  mov     rbx, rcx
0x180004b92  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180004b97  test    al, al
0x180004b99  jz      short loc_180004BA3
0x180004b9b  mov     al, 1
0x180004b9d  add     rsp, 50h
0x180004ba1  pop     rbx
0x180004ba2  retn
0x180004ba3  cmp     qword ptr [rbx+18h], 0
0x180004ba8  mov     [rsp+58h+arg_0], rdi
0x180004bad  jnz     short loc_180004C0C
0x180004baf  xorps   xmm0, xmm0
0x180004bb2  lea     rcx, [rsp+58h+var_28]; this
0x180004bb7  xorps   xmm1, xmm1
0x180004bba  mov     edx, 32h ; '2'; unsigned __int64
0x180004bbf  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x180004bc5  movdqu  [rsp+58h+var_18], xmm1
0x180004bcb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180004bd0  test    al, al
0x180004bd2  jz      short loc_180004BFE
0x180004bd4  mov     rdx, [rsp+58h+var_28]; void *
0x180004bd9  xor     r8d, r8d; unsigned __int64
0x180004bdc  mov     r9, qword ptr [rsp+58h+var_18]
0x180004be1  mov     rcx, rbx; this
0x180004be4  sub     r9, rdx; unsigned __int64
0x180004be7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180004bec  lea     rcx, [rbx+30h]
0x180004bf0  lea     rdx, [rsp+58h+var_18+8]
0x180004bf5  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180004bfa  mov     byte ptr [rbx+3Ah], 1
0x180004bfe  xor     edx, edx
0x180004c00  lea     rcx, [rsp+58h+var_18+8]
0x180004c05  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x180004c0a  jmp     short loc_180004C20
0x180004c0c  cmp     byte ptr [rbx+3Ah], 0
0x180004c10  jz      short loc_180004C20
0x180004c12  mov     edx, 28h ; '('; unsigned __int64
0x180004c17  lea     rcx, [rbx+18h]; this
0x180004c1b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180004c20  mov     [rsp+58h+var_30], 1; unsigned int
0x180004c28  lea     r9, [rsp+58h+arg_10]; void *
0x180004c2d  mov     r8d, 4; unsigned __int64
0x180004c33  mov     [rsp+58h+var_38], 4; unsigned __int64
0x180004c3c  lea     rdx, [rsp+58h+arg_8]; void *
0x180004c41  mov     rcx, rbx; this
0x180004c44  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180004c49  mov     rdi, [rsp+58h+arg_0]
0x180004c4e  jmp     loc_180004B9D
```

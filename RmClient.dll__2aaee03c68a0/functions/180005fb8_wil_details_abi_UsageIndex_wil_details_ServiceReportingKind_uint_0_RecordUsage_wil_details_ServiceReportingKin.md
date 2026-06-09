# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180005fb8`
- end: `0x18000611f`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `359`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180011650`

## callees

- `0x180004cd0`
- `0x180005e60`
- `0x180005fb8`
- `0x180006390`
- `0x180006818`
- `0x180007910`
- `0x180007a34`
- `0x18000de80`
- `0x1800130a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800060fe`
- `msvcrt!memcpy_s` at `0x1800060fe`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        int a2,
        int a3)
{
  char v3; // di
  char *v5; // rax
  char *v6; // rsi
  char *v7; // r12
  char v8; // r15
  char *v9; // r14
  void *v10; // rdx
  wil::details *v11; // rsi
  wil::details *v13; // rcx
  char v14[8]; // [rsp+30h] [rbp-30h] BYREF
  void *v15[2]; // [rsp+38h] [rbp-28h]
  wil::details *v16[2]; // [rsp+48h] [rbp-18h] BYREF
  int Buf1; // [rsp+A8h] [rbp+48h] BYREF
  int v18; // [rsp+B0h] [rbp+50h] BYREF

  v18 = a3;
  Buf1 = a2;
  v3 = 1;
  if ( !wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &Buf1, 4u, &v18, 4u, 1u) )
  {
    if ( *((_QWORD *)this + 3) )
    {
      if ( *((_BYTE *)this + 58) )
        wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), 0x28u);
    }
    else
    {
      *(_OWORD *)v15 = 0;
      *(_OWORD *)v16 = 0;
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      v5 = (char *)wil::details::ProcessHeapAlloc(0, 0x40u);
      v6 = v5;
      if ( v5 )
      {
        memcpy_s(v5, 0x40u, 0, 0);
        wistd::unique_ptr<void,wil::process_heap_deleter>::reset(&v16[1], v6);
        v7 = v6;
        v9 = v6 + 64;
        v8 = 1;
      }
      else
      {
        v7 = (char *)v15[0];
        v8 = 0;
        v9 = 0;
      }
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
      if ( v8 )
      {
        wil::details_abi::RawUsageIndex::SetBuffer(this, v7, 0, v9 - v6);
        v13 = (wil::details *)*((_QWORD *)this + 6);
        v11 = 0;
        *((wil::details **)this + 6) = v16[1];
        if ( v13 )
          wil::details::FreeProcessHeap(v13, v10);
        *((_BYTE *)this + 58) = 1;
      }
      else
      {
        v11 = v16[1];
      }
      if ( v11 )
        wil::details::FreeProcessHeap(v11, v10);
    }
    return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &Buf1, 4u, &v18, 4u, 1u);
  }
  return v3;
}

```

## disassembly

```asm
0x180005fb8  mov     rax, rsp
0x180005fbb  mov     [rax+8], rbx
0x180005fbf  mov     [rax+18h], r8d
0x180005fc3  mov     [rax+10h], edx
0x180005fc6  push    rbp
0x180005fc7  push    rsi
0x180005fc8  push    rdi
0x180005fc9  push    r12
0x180005fcb  push    r13
0x180005fcd  push    r14
0x180005fcf  push    r15
0x180005fd1  mov     rbp, rsp
0x180005fd4  sub     rsp, 60h
0x180005fd8  mov     edi, 1
0x180005fdd  lea     r9, [rbp+arg_10]; void *
0x180005fe1  mov     [rax-70h], edi
0x180005fe4  lea     rdx, [rbp+Buf1]; Buf1
0x180005fe8  mov     rbx, rcx
0x180005feb  lea     r13d, [rdi+3]
0x180005fef  mov     r8d, r13d; Size
0x180005ff2  mov     [rax-78h], r13
0x180005ff6  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005ffb  test    al, al
0x180005ffd  jnz     loc_180006084
0x180006003  lea     rcx, [rbx+18h]; this
0x180006007  cmp     qword ptr [rcx], 0
0x18000600b  jnz     loc_1800060CC
0x180006011  xorps   xmm0, xmm0
0x180006014  lea     rcx, [rbp+var_30]; this
0x180006018  xorps   xmm1, xmm1
0x18000601b  movdqu  xmmword ptr [rbp+var_28], xmm0
0x180006020  movdqu  xmmword ptr [rbp+var_18], xmm1
0x180006025  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000602a  lea     r14d, [rdi+3Fh]
0x18000602e  xor     ecx, ecx; dwFlags
0x180006030  mov     edx, r14d; dwBytes
0x180006033  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006038  mov     rsi, rax
0x18000603b  test    rax, rax
0x18000603e  jnz     loc_1800060F2
0x180006044  mov     r12, [rbp+var_28]
0x180006048  xor     r15b, r15b
0x18000604b  xor     r14d, r14d
0x18000604e  lea     rcx, [rbp+var_30]; this
0x180006052  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006057  test    r15b, r15b
0x18000605a  jnz     short loc_18000609F
0x18000605c  mov     rsi, [rbp+var_18+8]
0x180006060  test    rsi, rsi
0x180006063  jnz     short loc_1800060DE
0x180006065  mov     [rsp+60h+var_38], edi; unsigned int
0x180006069  lea     r9, [rbp+arg_10]; void *
0x18000606d  mov     r8, r13; Size
0x180006070  mov     [rsp+60h+var_40], r13; unsigned __int64
0x180006075  lea     rdx, [rbp+Buf1]; Buf1
0x180006079  mov     rcx, rbx; this
0x18000607c  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006081  mov     dil, al
0x180006084  mov     rbx, [rsp+60h+arg_0]
0x18000608c  mov     al, dil
0x18000608f  add     rsp, 60h
0x180006093  pop     r15
0x180006095  pop     r14
0x180006097  pop     r13
0x180006099  pop     r12
0x18000609b  pop     rdi
0x18000609c  pop     rsi
0x18000609d  pop     rbp
0x18000609e  retn
0x18000609f  sub     r14, rsi
0x1800060a2  xor     r8d, r8d; unsigned __int64
0x1800060a5  mov     r9, r14; unsigned __int64
0x1800060a8  mov     rdx, r12; void *
0x1800060ab  mov     rcx, rbx; this
0x1800060ae  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800060b3  mov     rcx, [rbx+30h]; this
0x1800060b7  xor     esi, esi
0x1800060b9  mov     rax, [rbp+var_18+8]
0x1800060bd  mov     [rbx+30h], rax
0x1800060c1  test    rcx, rcx
0x1800060c4  jnz     short loc_1800060EB
0x1800060c6  mov     [rbx+3Ah], dil
0x1800060ca  jmp     short loc_180006060
0x1800060cc  cmp     byte ptr [rbx+3Ah], 0
0x1800060d0  jz      short loc_180006065
0x1800060d2  mov     edx, 28h ; '('; unsigned __int64
0x1800060d7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800060dc  jmp     short loc_180006065
0x1800060de  mov     rcx, rsi; this
0x1800060e1  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800060e6  jmp     loc_180006065
0x1800060eb  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800060f0  jmp     short loc_1800060C6
0x1800060f2  xor     r9d, r9d; SourceSize
0x1800060f5  xor     r8d, r8d; Source
0x1800060f8  mov     rdx, r14; DestinationSize
0x1800060fb  mov     rcx, rsi; Destination
0x1800060fe  call    cs:__imp_memcpy_s
0x180006104  mov     rdx, rsi
0x180006107  lea     rcx, [rbp+var_18+8]
0x18000610b  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x180006110  mov     r12, rsi
0x180006113  lea     r14, [rsi+40h]
0x180006117  mov     r15b, dil
0x18000611a  jmp     loc_18000604E
```

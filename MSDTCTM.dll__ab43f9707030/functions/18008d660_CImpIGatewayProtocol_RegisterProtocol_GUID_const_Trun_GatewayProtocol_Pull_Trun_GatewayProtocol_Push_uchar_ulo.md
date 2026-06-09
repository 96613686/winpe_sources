# CImpIGatewayProtocol::RegisterProtocol(_GUID const &,_Trun_GatewayProtocol_Pull,_Trun_GatewayProtocol_Push,uchar *,ulong)

- ea: `0x18008d660`
- end: `0x18008d7ff`
- name: `?RegisterProtocol@CImpIGatewayProtocol@@UEAAJAEBU_GUID@@W4_Trun_GatewayProtocol_Pull@@W4_Trun_GatewayProtocol_Push@@PEAEK@Z`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x180025104`
- `0x18008d660`
- `0x1800995ac`
- `0x180099dbc`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008d720`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008d720`

## string_xrefs

- `0x18008d6ab`: `com\complus\dtc\dtc\mapper_igatewaytx\src\mapper_igatewayprotocol.cpp`
- `0x18008d74e`: `com\complus\dtc\dtc\mapper_igatewaytx\src\mapper_igatewayprotocol.cpp`
- `0x18008d7cb`: `com\complus\dtc\dtc\mapper_igatewaytx\src\mapper_igatewayprotocol.cpp`
- `0x18008d695`: `CImpIGatewayProtocol::RegisterProtocol`
- `0x18008d73f`: `CImpIGatewayProtocol::RegisterProtocol`
- `0x18008d7a9`: `CImpIGatewayProtocol::RegisterProtocol`

## pseudocode

```c
__int64 __fastcall CImpIGatewayProtocol::RegisterProtocol(
        __int64 a1,
        __int128 *a2,
        int a3,
        int a4,
        void *Src,
        unsigned int Size)
{
  char *v10; // rax
  void *v11; // rbx
  unsigned int v12; // edi
  __int128 v13; // xmm0
  __int64 v15; // [rsp+28h] [rbp-60h]

  TraceStringInline(
    4,
    6,
    L"com\\complus\\dtc\\dtc\\mapper_igatewaytx\\src\\mapper_igatewayprotocol.cpp",
    69,
    L"CImpIGatewayProtocol::RegisterProtocol",
    0,
    L"In");
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 152LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(a1 + 8)
                                                                                                + 152LL));
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 160LL) + 8LL))(*(_QWORD *)(*(_QWORD *)(a1 + 8)
                                                                                                + 160LL));
  CCmMapper::Connect(
    (CCmMapper *)(*(_QWORD *)(a1 + 8) + 24LL),
    *(struct IConnectionDispenser **)(*(_QWORD *)(a1 + 8) + 152LL),
    *(struct INameObject **)(*(_QWORD *)(a1 + 8) + 160LL),
    0x47u);
  v10 = (char *)CoTaskMemAlloc(4 * (unsigned int)(((unsigned __int64)Size + 3) >> 2) + 28);
  v11 = v10;
  if ( v10 )
  {
    v13 = *a2;
    *((_DWORD *)v10 + 4) = a3;
    *(_OWORD *)v10 = v13;
    *((_DWORD *)v10 + 5) = a4;
    *((_DWORD *)v10 + 6) = Size;
    memcpy_0(v10 + 28, Src, Size);
    v12 = CCmMapper::Send(
            (CCmMapper *)(*(_QWORD *)(a1 + 8) + 24LL),
            0x5601u,
            v11,
            4 * (unsigned int)(((unsigned __int64)Size + 3) >> 2) + 28);
  }
  else
  {
    v12 = -2147024882;
    LODWORD(v15) = -2147024882;
    TraceStringInline(
      4,
      1,
      L"com\\complus\\dtc\\dtc\\mapper_igatewaytx\\src\\mapper_igatewayprotocol.cpp",
      91,
      L"CImpIGatewayProtocol::RegisterProtocol",
      v15,
      L"Out of memory allocating register message");
  }
  CoTaskMemFree(v11);
  TraceStringInline(
    4,
    6,
    L"com\\complus\\dtc\\dtc\\mapper_igatewaytx\\src\\mapper_igatewayprotocol.cpp",
    114,
    L"CImpIGatewayProtocol::RegisterProtocol",
    0,
    L"Out");
  return v12;
}

```

## disassembly

```asm
0x18008d660  push    rbx
0x18008d662  push    rbp
0x18008d663  push    rsi
0x18008d664  push    rdi
0x18008d665  push    r12
0x18008d667  push    r13
0x18008d669  push    r14
0x18008d66b  push    r15
0x18008d66d  sub     rsp, 48h
0x18008d671  mov     r15d, r9d
0x18008d674  lea     rax, aIn_0; "In"
0x18008d67b  mov     [rsp+88h+var_58], rax
0x18008d680  mov     r9d, 45h ; 'E'
0x18008d686  mov     r13, rdx
0x18008d689  mov     [rsp+88h+var_60], 0
0x18008d692  mov     r12d, r8d
0x18008d695  lea     rax, aCimpigatewaypr; "CImpIGatewayProtocol::RegisterProtocol"
0x18008d69c  mov     rdi, rcx
0x18008d69f  mov     [rsp+88h+var_68], rax
0x18008d6a4  lea     edx, [r9-3Fh]
0x18008d6a8  lea     ecx, [rdx-2]
0x18008d6ab  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\mapper_igateway"...
0x18008d6b2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008d6b7  mov     rax, [rdi+8]
0x18008d6bb  mov     rcx, [rax+98h]
0x18008d6c2  mov     rax, [rcx]
0x18008d6c5  mov     rax, [rax+8]
0x18008d6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6ce  mov     rax, [rdi+8]
0x18008d6d2  mov     rcx, [rax+0A0h]
0x18008d6d9  mov     rax, [rcx]
0x18008d6dc  mov     rax, [rax+8]
0x18008d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6e5  mov     rdx, [rdi+8]
0x18008d6e9  mov     r9d, 47h ; 'G'; unsigned int
0x18008d6ef  mov     r8, [rdx+0A0h]; struct INameObject *
0x18008d6f6  lea     rcx, [rdx+18h]; this
0x18008d6fa  mov     rdx, [rdx+98h]; struct IConnectionDispenser *
0x18008d701  call    ?Connect@CCmMapper@@QEAAXPEAUIConnectionDispenser@@PEAUINameObject@@K@Z; CCmMapper::Connect(IConnectionDispenser *,INameObject *,ulong)
0x18008d706  mov     esi, dword ptr [rsp+88h+Size]
0x18008d70d  lea     rax, [rsi+3]
0x18008d711  shr     rax, 2
0x18008d715  lea     r14d, ds:1Ch[rax*4]
0x18008d71d  mov     ecx, r14d; cb
0x18008d720  call    cs:__imp_CoTaskMemAlloc
0x18008d726  mov     rbx, rax
0x18008d729  test    rax, rax
0x18008d72c  jnz     short loc_18008D767
0x18008d72e  lea     rax, aOutOfMemoryAll_0; "Out of memory allocating register messa"...
0x18008d735  mov     edi, 8007000Eh
0x18008d73a  mov     [rsp+88h+var_58], rax
0x18008d73f  lea     rsi, aCimpigatewaypr; "CImpIGatewayProtocol::RegisterProtocol"
0x18008d746  mov     dword ptr [rsp+88h+var_60], edi
0x18008d74a  lea     r9d, [rbx+5Bh]
0x18008d74e  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\mapper_igateway"...
0x18008d755  mov     [rsp+88h+var_68], rsi
0x18008d75a  lea     edx, [rbx+1]
0x18008d75d  lea     ecx, [rbx+4]
0x18008d760  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008d765  jmp     short loc_18008D7B0
0x18008d767  movups  xmm0, xmmword ptr [r13+0]
0x18008d76c  mov     rdx, [rsp+88h+Src]; Src
0x18008d774  lea     rcx, [rax+1Ch]; void *
0x18008d778  mov     [rax+10h], r12d
0x18008d77c  mov     r8, rsi; Size
0x18008d77f  movdqu  xmmword ptr [rax], xmm0
0x18008d783  mov     [rax+14h], r15d
0x18008d787  mov     [rax+18h], esi
0x18008d78a  call    memcpy_0
0x18008d78f  mov     rcx, [rdi+8]
0x18008d793  mov     r9d, r14d; unsigned int
0x18008d796  add     rcx, 18h; this
0x18008d79a  mov     r8, rbx; void *
0x18008d79d  mov     edx, 5601h; unsigned int
0x18008d7a2  call    ?Send@CCmMapper@@QEAAJKPEAXK@Z; CCmMapper::Send(ulong,void *,ulong)
0x18008d7a7  mov     edi, eax
0x18008d7a9  lea     rsi, aCimpigatewaypr; "CImpIGatewayProtocol::RegisterProtocol"
0x18008d7b0  mov     rcx, rbx; pv
0x18008d7b3  call    cs:__imp_CoTaskMemFree
0x18008d7b9  mov     r9d, 72h ; 'r'
0x18008d7bf  lea     rax, aOut; "Out"
0x18008d7c6  mov     [rsp+88h+var_58], rax
0x18008d7cb  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\mapper_igateway"...
0x18008d7d2  mov     [rsp+88h+var_60], 0
0x18008d7db  mov     [rsp+88h+var_68], rsi
0x18008d7e0  lea     edx, [r9-6Ch]
0x18008d7e4  lea     ecx, [rdx-2]
0x18008d7e7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008d7ec  mov     eax, edi
0x18008d7ee  add     rsp, 48h
0x18008d7f2  pop     r15
0x18008d7f4  pop     r14
0x18008d7f6  pop     r13
0x18008d7f8  pop     r12
0x18008d7fa  pop     rdi
0x18008d7fb  pop     rsi
0x18008d7fc  pop     rbp
0x18008d7fd  pop     rbx
0x18008d7fe  retn
```

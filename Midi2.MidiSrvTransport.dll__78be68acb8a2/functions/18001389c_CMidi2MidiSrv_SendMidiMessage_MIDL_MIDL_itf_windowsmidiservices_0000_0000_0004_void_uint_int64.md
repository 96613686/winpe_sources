# CMidi2MidiSrv::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18001389c`
- end: `0x1800138f1`
- name: `?SendMidiMessage@CMidi2MidiSrv@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000baa0`
- `0x18000beb0`

## callees

- `0x180007e24`
- `0x180010094`
- `0x18001389c`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrv::SendMidiMessage(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        LARGE_INTEGER a5)
{
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = *(_QWORD *)(a1 + 16);
  if ( !v5 )
  {
    v6 = -2147467260;
    v7 = 281;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\midi2\\libs\\midisrvtransportlib\\midisrvtransport.cpp",
      (const char *)(unsigned int)v6,
      v9);
    return (unsigned int)v6;
  }
  v6 = CMidiXProc::SendMidiMessage(v5, a2, a3, a4, a5);
  if ( v6 < 0 )
  {
    v7 = 283;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001389c  push    rbx
0x18001389e  sub     rsp, 30h
0x1800138a2  mov     rcx, [rcx+10h]
0x1800138a6  test    rcx, rcx
0x1800138a9  jnz     short loc_1800138CD
0x1800138ab  mov     ebx, 80004004h
0x1800138b0  mov     edx, 119h; void *
0x1800138b5  mov     rcx, [rsp+38h]; this
0x1800138ba  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midisrvtransportli"...
0x1800138c1  mov     r9d, ebx; char *
0x1800138c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138c9  mov     eax, ebx
0x1800138cb  jmp     short loc_1800138EB
0x1800138cd  mov     rax, [rsp+38h+arg_20]
0x1800138d2  mov     qword ptr [rsp+38h+var_18], rax
0x1800138d7  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x1800138dc  mov     ebx, eax
0x1800138de  test    eax, eax
0x1800138e0  jns     short loc_1800138E9
0x1800138e2  mov     edx, 11Bh
0x1800138e7  jmp     short loc_1800138B5
0x1800138e9  xor     eax, eax
0x1800138eb  add     rsp, 30h
0x1800138ef  pop     rbx
0x1800138f0  retn
```

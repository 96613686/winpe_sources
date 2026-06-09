# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x14000dff0`
- end: `0x14000e05f`
- name: `??1_Reallocation_guard@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000da28`

## callees

- `0x14000d9b0`
- `0x14000dff0`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000e058`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000e058`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  _QWORD *v2; // rcx

  if ( a1[1] )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(a1[3], a1[4]);
    v2 = (_QWORD *)a1[1];
    if ( (unsigned __int64)(16LL * a1[2]) >= 0x1000 )
    {
      if ( (unsigned __int64)v2 - *(v2 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v2 = (_QWORD *)*(v2 - 1);
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x14000dff0  push    rbx
0x14000dff2  sub     rsp, 30h
0x14000dff6  cmp     qword ptr [rcx+8], 0
0x14000dffb  mov     rbx, rcx
0x14000dffe  jz      short loc_14000E03F
0x14000e000  mov     rdx, [rcx+20h]
0x14000e004  mov     rcx, [rcx+18h]
0x14000e008  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000e00d  mov     rdx, [rbx+10h]
0x14000e011  mov     rcx, [rbx+8]
0x14000e015  shl     rdx, 4
0x14000e019  cmp     rdx, 1000h
0x14000e020  jb      short loc_14000E03A
0x14000e022  mov     rax, [rcx-8]
0x14000e026  add     rdx, 27h ; '''
0x14000e02a  sub     rcx, rax
0x14000e02d  sub     rcx, 8
0x14000e031  cmp     rcx, 1Fh
0x14000e035  ja      short loc_14000E045
0x14000e037  mov     rcx, rax; Block
0x14000e03a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e03f  add     rsp, 30h
0x14000e043  pop     rbx
0x14000e044  retn
0x14000e045  xor     r9d, r9d; LineNo
0x14000e048  mov     [rsp+38h+Reserved], 0; Reserved
0x14000e051  xor     r8d, r8d; FileName
0x14000e054  xor     edx, edx; FunctionName
0x14000e056  xor     ecx, ecx; Expression
0x14000e058  call    cs:__imp__invoke_watson
```

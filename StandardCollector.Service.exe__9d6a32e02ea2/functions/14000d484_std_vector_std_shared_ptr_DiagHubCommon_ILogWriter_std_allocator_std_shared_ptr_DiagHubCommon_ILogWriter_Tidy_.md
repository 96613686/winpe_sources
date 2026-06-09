# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Tidy(void)

- ea: `0x14000d484`
- end: `0x14000d50c`
- name: `?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000a298`
- `0x14000a40c`
- `0x14000a42c`
- `0x14000b81c`
- `0x14000d7fc`

## callees

- `0x14000d484`
- `0x14000d9b0`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000d505`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000d505`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(__int64 *a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rcx

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(v2, a1[1]);
    v3 = (_QWORD *)*a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14000d484  push    rbx
0x14000d486  sub     rsp, 30h
0x14000d48a  mov     rbx, rcx
0x14000d48d  mov     rcx, [rcx]
0x14000d490  test    rcx, rcx
0x14000d493  jz      short loc_14000D4EC
0x14000d495  mov     rdx, [rbx+8]
0x14000d499  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000d49e  mov     rcx, [rbx]
0x14000d4a1  mov     rdx, [rbx+10h]
0x14000d4a5  sub     rdx, rcx
0x14000d4a8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000d4ac  cmp     rdx, 1000h
0x14000d4b3  jb      short loc_14000D4D0
0x14000d4b5  lfence
0x14000d4b8  mov     rax, [rcx-8]
0x14000d4bc  add     rdx, 27h ; '''
0x14000d4c0  sub     rcx, rax
0x14000d4c3  sub     rcx, 8
0x14000d4c7  cmp     rcx, 1Fh
0x14000d4cb  ja      short loc_14000D4F2
0x14000d4cd  mov     rcx, rax; Block
0x14000d4d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d4d5  mov     qword ptr [rbx], 0
0x14000d4dc  mov     qword ptr [rbx+8], 0
0x14000d4e4  mov     qword ptr [rbx+10h], 0
0x14000d4ec  add     rsp, 30h
0x14000d4f0  pop     rbx
0x14000d4f1  retn
0x14000d4f2  xor     r9d, r9d; LineNo
0x14000d4f5  mov     [rsp+38h+Reserved], 0; Reserved
0x14000d4fe  xor     r8d, r8d; FileName
0x14000d501  xor     edx, edx; FunctionName
0x14000d503  xor     ecx, ecx; Expression
0x14000d505  call    cs:__imp__invoke_watson
```

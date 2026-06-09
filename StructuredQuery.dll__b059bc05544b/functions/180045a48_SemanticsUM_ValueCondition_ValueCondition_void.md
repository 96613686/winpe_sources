# SemanticsUM::ValueCondition::~ValueCondition(void)

- ea: `0x180045a48`
- end: `0x180045ac4`
- name: `??1ValueCondition@SemanticsUM@@UEAA@XZ`
- size: `124`
- prototype: `void __fastcall(SemanticsUM::ValueCondition *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800459f4`

## callees

- `0x180045c7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045ab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SemanticsUM::ValueCondition::~ValueCondition(SemanticsUM::ValueCondition *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  *((_QWORD *)this - 14) = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::SemanticCondition'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 13) + 4LL) - 104) = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::ISemanticCondition'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 13) + 8LL) - 104) = &SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::IValueCondition'};
  v2 = *(int *)(*((_QWORD *)this - 13) + 4LL);
  *(_DWORD *)((char *)this + v2 - 108) = v2 - 104;
  v3 = *(int *)(*((_QWORD *)this - 13) + 8LL);
  *(_DWORD *)((char *)this + v3 - 108) = v3 - 120;
  CoTaskMemFree(*((LPVOID *)this - 5));
  CoTaskMemFree(*((LPVOID *)this - 3));
  SemanticsUM::SemanticCondition::~SemanticCondition((SemanticsUM::ValueCondition *)((char *)this - 32));
}

```

## disassembly

```asm
0x180045a48  push    rbx
0x180045a4a  sub     rsp, 20h
0x180045a4e  mov     rbx, rcx
0x180045a51  lea     rax, ??_7ValueCondition@SemanticsUM@@6BSemanticCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::SemanticCondition'}
0x180045a58  mov     [rcx-70h], rax
0x180045a5c  mov     rax, [rcx-68h]
0x180045a60  movsxd  rdx, dword ptr [rax+4]
0x180045a64  lea     rax, ??_7ValueCondition@SemanticsUM@@6BISemanticCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::ISemanticCondition'}
0x180045a6b  mov     [rdx+rcx-68h], rax
0x180045a70  mov     rax, [rcx-68h]
0x180045a74  movsxd  rdx, dword ptr [rax+8]
0x180045a78  lea     rax, ??_7ValueCondition@SemanticsUM@@6BIValueCondition@1@@; const SemanticsUM::ValueCondition::`vftable'{for `SemanticsUM::IValueCondition'}
0x180045a7f  mov     [rdx+rcx-68h], rax
0x180045a84  mov     rax, [rcx-68h]
0x180045a88  movsxd  rdx, dword ptr [rax+4]
0x180045a8c  lea     ecx, [rdx-68h]
0x180045a8f  mov     [rdx+rbx-6Ch], ecx
0x180045a93  mov     rax, [rbx-68h]
0x180045a97  movsxd  rcx, dword ptr [rax+8]
0x180045a9b  lea     edx, [rcx-78h]
0x180045a9e  mov     [rcx+rbx-6Ch], edx
0x180045aa2  mov     rcx, [rbx-28h]; pv
0x180045aa6  call    cs:__imp_CoTaskMemFree
0x180045aac  mov     rcx, [rbx-18h]; pv
0x180045ab0  call    cs:__imp_CoTaskMemFree
0x180045ab6  lea     rcx, [rbx-20h]; this
0x180045aba  add     rsp, 20h
0x180045abe  pop     rbx
0x180045abf  jmp     ??1SemanticCondition@SemanticsUM@@UEAA@XZ; SemanticsUM::SemanticCondition::~SemanticCondition(void)
```

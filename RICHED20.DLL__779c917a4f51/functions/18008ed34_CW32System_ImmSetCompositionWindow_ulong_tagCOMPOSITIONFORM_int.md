# CW32System::ImmSetCompositionWindow(ulong,tagCOMPOSITIONFORM *,int)

- ea: `0x18008ed34`
- end: `0x18008eda7`
- name: `?ImmSetCompositionWindow@CW32System@@SAHKPEAUtagCOMPOSITIONFORM@@H@Z`
- size: `115`
- prototype: `__int64 __fastcall(unsigned int, struct tagCOMPOSITIONFORM *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180065080`
- `0x180065d38`

## callees

- `0x18008ed34`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008ed76`: `ImmSetCompositionWindow`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionWindow(unsigned int a1, struct tagCOMPOSITIONFORM *a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, struct tagCOMPOSITIONFORM *); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, struct tagCOMPOSITIONFORM *))(*(_QWORD *)qword_1800A44B8 + 424LL))(
             qword_1800A44B8,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, struct tagCOMPOSITIONFORM *))qword_1800A4110;
  if ( !qword_1800A4110 )
  {
    SetIMEProcAddr(&qword_1800A4110, 0, "ImmSetCompositionWindow");
    v6 = (__int64 (__fastcall *)(_QWORD, struct tagCOMPOSITIONFORM *))qword_1800A4110;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x18008ed34  mov     [rsp+arg_0], rbx
0x18008ed39  push    rdi
0x18008ed3a  sub     rsp, 20h
0x18008ed3e  mov     rbx, rdx
0x18008ed41  mov     edi, ecx
0x18008ed43  test    r8d, r8d
0x18008ed46  jz      short loc_18008ED6A
0x18008ed48  mov     rcx, cs:qword_1800A44B8
0x18008ed4f  mov     r8, rdx
0x18008ed52  mov     edx, edi
0x18008ed54  mov     rax, [rcx]
0x18008ed57  mov     rax, [rax+1A8h]
0x18008ed5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ed63  not     eax
0x18008ed65  shr     eax, 1Fh
0x18008ed68  jmp     short loc_18008ED9C
0x18008ed6a  mov     rax, cs:qword_1800A4110
0x18008ed71  test    rax, rax
0x18008ed74  jnz     short loc_18008ED92
0x18008ed76  lea     r8, aImmsetcomposit_1; "ImmSetCompositionWindow"
0x18008ed7d  xor     edx, edx
0x18008ed7f  lea     rcx, qword_1800A4110
0x18008ed86  call    SetIMEProcAddr
0x18008ed8b  mov     rax, cs:qword_1800A4110
0x18008ed92  mov     rdx, rbx
0x18008ed95  mov     ecx, edi
0x18008ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ed9c  mov     rbx, [rsp+28h+arg_0]
0x18008eda1  add     rsp, 20h
0x18008eda5  pop     rdi
0x18008eda6  retn
```

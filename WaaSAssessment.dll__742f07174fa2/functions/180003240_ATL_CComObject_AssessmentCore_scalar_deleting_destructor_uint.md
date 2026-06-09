# ATL::CComObject<AssessmentCore>::`scalar deleting destructor'(uint)

- ea: `0x180003240`
- end: `0x180003270`
- name: `??_G?$CComObject@VAssessmentCore@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ffc`
- `0x180003240`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000325c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000325c`

## pseudocode

```c
void *__fastcall ATL::CComObject<AssessmentCore>::`scalar deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<AssessmentCore>::~CComObject<AssessmentCore>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003240  mov     [rsp+arg_0], rbx
0x180003245  push    rdi
0x180003246  sub     rsp, 20h
0x18000324a  mov     ebx, edx
0x18000324c  mov     rdi, rcx
0x18000324f  call    ??1?$CComObject@VAssessmentCore@@@ATL@@UEAA@XZ; ATL::CComObject<AssessmentCore>::~CComObject<AssessmentCore>(void)
0x180003254  test    bl, 1
0x180003257  jz      short loc_180003262
0x180003259  mov     rcx, rdi
0x18000325c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003262  mov     rbx, [rsp+28h+arg_0]
0x180003267  mov     rax, rdi
0x18000326a  add     rsp, 20h
0x18000326e  pop     rdi
0x18000326f  retn
```

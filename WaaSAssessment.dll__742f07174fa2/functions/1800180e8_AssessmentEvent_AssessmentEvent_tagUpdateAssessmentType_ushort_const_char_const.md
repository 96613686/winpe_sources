# AssessmentEvent::AssessmentEvent(tagUpdateAssessmentType,ushort const *,char const *)

- ea: `0x1800180e8`
- end: `0x180018128`
- name: `??0AssessmentEvent@@QEAA@W4tagUpdateAssessmentType@@PEBGPEBD@Z`
- size: `64`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007aa0`
- `0x180008220`
- `0x180008310`
- `0x1800086e0`

## callees

- `0x1800170c8`
- `0x1800180e8`
- `0x180018234`

## pseudocode

```c
__int64 __fastcall AssessmentEvent::AssessmentEvent(__int64 a1, int a2, _WORD *a3, char *a4)
{
  unsigned int v5; // r8d
  const unsigned __int16 *v6; // rdx

  if ( (int)AssessmentEvent::InitializeInternal(a1, a2, a3, a4) < 0 )
  {
    *(_DWORD *)a1 = 0;
  }
  else
  {
    v5 = *(_DWORD *)(a1 + 156);
    v6 = *(const unsigned __int16 **)(a1 + 144);
    *(_DWORD *)a1 = 1;
    LogAssessmentStart((const char *)(a1 + 8), v6, v5);
  }
  return a1;
}

```

## disassembly

```asm
0x1800180e8  push    rbx
0x1800180ea  sub     rsp, 20h
0x1800180ee  mov     rbx, rcx
0x1800180f1  call    ?InitializeInternal@AssessmentEvent@@AEAAJW4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::InitializeInternal(tagUpdateAssessmentType,ushort const *,char const *)
0x1800180f6  test    eax, eax
0x1800180f8  js      short loc_180018119
0x1800180fa  mov     r8d, [rbx+9Ch]; unsigned int
0x180018101  lea     rcx, [rbx+8]; char *
0x180018105  mov     rdx, [rbx+90h]; unsigned __int16 *
0x18001810c  mov     dword ptr [rbx], 1
0x180018112  call    ?LogAssessmentStart@@YAXPEBDPEBGK@Z; LogAssessmentStart(char const *,ushort const *,ulong)
0x180018117  jmp     short loc_18001811F
0x180018119  mov     dword ptr [rbx], 0
0x18001811f  mov     rax, rbx
0x180018122  add     rsp, 20h
0x180018126  pop     rbx
0x180018127  retn
```

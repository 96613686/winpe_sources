# CommonUtil::TrDuplicateStringW(wchar_t const *)

- ea: `0x14000309c`
- end: `0x1400030da`
- name: `?TrDuplicateStringW@CommonUtil@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEA_W@CommonUtil@@@CommonUtil@@@1@PEB_W@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001d464`

## callees

- `0x140002e74`
- `0x140003054`
- `0x14000309c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CommonUtil::TrDuplicateStringW(_QWORD *a1, wchar_t **a2, const wchar_t *a3)
{
  int v4; // eax
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v4 = CommonUtil::HrDuplicateStringW((CommonUtil *)&v6, a2, a3);
  if ( v4 < 0 )
    CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)v4);
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x14000309c  push    rbx
0x14000309e  sub     rsp, 30h
0x1400030a2  mov     rbx, rcx
0x1400030a5  mov     [rsp+38h+arg_10], 0
0x1400030ae  lea     rcx, [rsp+38h+arg_10]; this
0x1400030b3  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x1400030b8  mov     edx, eax
0x1400030ba  shr     edx, 1Fh; int
0x1400030bd  test    dl, dl
0x1400030bf  jnz     short loc_1400030D2
0x1400030c1  mov     rax, [rsp+38h+arg_10]
0x1400030c6  mov     [rbx], rax
0x1400030c9  mov     rax, rbx
0x1400030cc  add     rsp, 30h
0x1400030d0  pop     rbx
0x1400030d1  retn
0x1400030d2  mov     ecx, eax; this
0x1400030d4  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```

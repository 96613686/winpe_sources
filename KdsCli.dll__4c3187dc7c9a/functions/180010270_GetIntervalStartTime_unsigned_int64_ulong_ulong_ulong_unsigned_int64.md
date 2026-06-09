# GetIntervalStartTime(unsigned __int64,ulong,ulong,ulong,unsigned __int64 *)

- ea: `0x180010270`
- end: `0x1800102e3`
- name: `?GetIntervalStartTime@@YAJ_KKKKPEA_K@Z`
- size: `115`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`
- `0x18000c1fc`
- `0x180017310`

## callees

- `0x180010270`
- `0x18001a450`

## string_xrefs

- `0x1800102c8`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall GetIntervalStartTime(
        unsigned __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 *a5)
{
  unsigned int v5; // ebx
  char v6; // r9
  char v7; // cl

  if ( a3 > 0x1F || a4 > 0x1F )
  {
    v5 = -2147024809;
    v6 = -89;
    v7 = 87;
    goto LABEL_7;
  }
  v5 = 0;
  if ( !is_mul_ok(a4 + 32 * (a3 + 32 * a2), a1) )
  {
    v5 = -2147024362;
    v6 = -75;
    v7 = 22;
LABEL_7:
    SidKeyDebugTraceError(v7, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v6);
    return v5;
  }
  *a5 = (a4 + 32 * (a3 + 32 * a2)) * a1;
  return v5;
}

```

## disassembly

```asm
0x180010270  push    rbx
0x180010272  sub     rsp, 30h
0x180010276  mov     rax, rcx
0x180010279  cmp     r8d, 1Fh
0x18001027d  ja      short loc_1800102B8
0x18001027f  cmp     r9d, 1Fh
0x180010283  ja      short loc_1800102B8
0x180010285  shl     edx, 5
0x180010288  xor     ebx, ebx
0x18001028a  lea     ecx, [r8+rdx]
0x18001028e  shl     ecx, 5
0x180010291  add     ecx, r9d
0x180010294  mul     rcx
0x180010297  test    rdx, rdx
0x18001029a  jnz     short loc_1800102A6
0x18001029c  mov     rcx, [rsp+38h+arg_20]
0x1800102a1  mov     [rcx], rax
0x1800102a4  jmp     short loc_1800102DB
0x1800102a6  mov     ebx, 80070216h
0x1800102ab  mov     r9d, 1B5h
0x1800102b1  mov     ecx, 80070216h
0x1800102b6  jmp     short loc_1800102C8
0x1800102b8  mov     ebx, 80070057h
0x1800102bd  mov     r9d, 1A7h; unsigned int
0x1800102c3  mov     ecx, 80070057h; unsigned int
0x1800102c8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800102cf  lea     rdx, aHr; "hr"
0x1800102d6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800102db  mov     eax, ebx
0x1800102dd  add     rsp, 30h
0x1800102e1  pop     rbx
0x1800102e2  retn
```

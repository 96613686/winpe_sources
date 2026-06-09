# CommonUtil::MpUtilMicrosoftCertCheck(ushort const *,ulong,void *)

- ea: `0x14001088c`
- end: `0x1400108f0`
- name: `?MpUtilMicrosoftCertCheck@CommonUtil@@YAJPEBGKPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, __int64, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004588`
- `0x140007538`

## callees

- `0x1400104e4`
- `0x14001088c`
- `0x1400108f8`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpUtilMicrosoftCertCheck(void **this, const unsigned __int16 *a2, __int64 a3, void *a4)
{
  __int64 v4; // r8
  unsigned int v6; // ebx
  __int64 result; // rax

  v4 = 1;
  if ( (_DWORD)a2 )
    v4 = (unsigned int)a2;
  v6 = v4 | 3;
  if ( (v4 & 4) == 0 )
    v6 = v4;
  if ( (v6 & 1) == 0
    || (result = CommonUtil::MpUtilMicrosoftSelfCertCheck(this, v6, v4, a4), (_DWORD)result == -2146762496)
    && (v6 & 4) != 0 )
  {
    if ( (v6 & 2) != 0 )
      return CommonUtil::MpUtilMicrosoftCatalogCertCheck(this, v6);
    else
      return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x14001088c  mov     [rsp+arg_0], rbx
0x140010891  push    rdi
0x140010892  sub     rsp, 20h
0x140010896  test    edx, edx
0x140010898  mov     r8d, 1
0x14001089e  mov     rdi, rcx
0x1400108a1  cmovnz  r8d, edx
0x1400108a5  mov     ebx, r8d
0x1400108a8  or      ebx, 3
0x1400108ab  test    r8b, 4
0x1400108af  cmovz   ebx, r8d
0x1400108b3  test    bl, 1
0x1400108b6  jz      short loc_1400108CF
0x1400108b8  mov     edx, ebx
0x1400108ba  call    CommonUtil__MpUtilMicrosoftSelfCertCheck
0x1400108bf  test    eax, eax
0x1400108c1  jns     short loc_1400108E5
0x1400108c3  cmp     eax, 800B0100h
0x1400108c8  jnz     short loc_1400108E5
0x1400108ca  test    bl, 4
0x1400108cd  jz      short loc_1400108E5
0x1400108cf  test    bl, 2
0x1400108d2  jz      short loc_1400108E0
0x1400108d4  mov     edx, ebx
0x1400108d6  mov     rcx, rdi; void **
0x1400108d9  call    CommonUtil__MpUtilMicrosoftCatalogCertCheck
0x1400108de  jmp     short loc_1400108E5
0x1400108e0  mov     eax, 80070057h
0x1400108e5  mov     rbx, [rsp+28h+arg_0]
0x1400108ea  add     rsp, 20h
0x1400108ee  pop     rdi
0x1400108ef  retn
```

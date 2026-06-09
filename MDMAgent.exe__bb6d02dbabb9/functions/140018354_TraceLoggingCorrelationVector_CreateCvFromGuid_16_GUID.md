# TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)

- ea: `0x140018354`
- end: `0x1400183c1`
- name: `??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400183c8`

## callees

- `0x1400029c0`
- `0x14000353c`
- `0x140018274`

## pseudocode

```c
__int64 __fastcall TraceLoggingCorrelationVector::CreateCvFromGuid<16>(__int64 a1, __int128 *a2)
{
  __int128 v2; // xmm0
  __int64 v4; // rdx
  __int64 result; // rax
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF

  v2 = *a2;
  *(_BYTE *)(a1 + 129) = 23;
  *(_QWORD *)(a1 + 136) = 0x1900000000LL;
  v6 = v2;
  memset_0((void *)a1, 0, 0x81u);
  result = TLV::Base64Encode<129>(&v6, v4, a1);
  *(_WORD *)(a1 + 22) = 46;
  return result;
}

```

## disassembly

```asm
0x140018354  push    rbx
0x140018356  sub     rsp, 40h
0x14001835a  mov     rax, cs:__security_cookie
0x140018361  xor     rax, rsp
0x140018364  mov     [rsp+48h+var_18], rax
0x140018369  movups  xmm0, xmmword ptr [rdx]
0x14001836c  mov     rax, 1900000000h
0x140018376  mov     byte ptr [rcx+81h], 17h
0x14001837d  xor     edx, edx; Val
0x14001837f  mov     [rcx+88h], rax
0x140018386  mov     r8d, 81h; Size
0x14001838c  mov     rbx, rcx
0x14001838f  movdqu  [rsp+48h+var_28], xmm0
0x140018395  call    memset_0
0x14001839a  mov     r8, rbx
0x14001839d  lea     rcx, [rsp+48h+var_28]
0x1400183a2  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1400183a7  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1400183ad  mov     rcx, [rsp+48h+var_18]
0x1400183b2  xor     rcx, rsp; StackCookie
0x1400183b5  call    __security_check_cookie
0x1400183ba  add     rsp, 40h
0x1400183be  pop     rbx
0x1400183bf  retn
```

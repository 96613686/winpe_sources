# TraceLoggingCorrelationVector::CreateCvFromGuid<16>(_GUID)

- ea: `0x140017680`
- end: `0x1400176ec`
- name: `??$CreateCvFromGuid@$0BA@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400176f4`

## callees

- `0x140002930`
- `0x14000349c`
- `0x1400175a0`

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
0x140017680  push    rbx
0x140017682  sub     rsp, 40h
0x140017686  mov     rax, cs:__security_cookie
0x14001768d  xor     rax, rsp
0x140017690  mov     [rsp+48h+var_18], rax
0x140017695  movups  xmm0, xmmword ptr [rdx]
0x140017698  mov     rax, 1900000000h
0x1400176a2  mov     byte ptr [rcx+81h], 17h
0x1400176a9  xor     edx, edx; Val
0x1400176ab  mov     [rcx+88h], rax
0x1400176b2  mov     r8d, 81h; Size
0x1400176b8  mov     rbx, rcx
0x1400176bb  movdqu  [rsp+48h+var_28], xmm0
0x1400176c1  call    memset_0
0x1400176c6  mov     r8, rbx
0x1400176c9  lea     rcx, [rsp+48h+var_28]
0x1400176ce  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1400176d3  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1400176d9  mov     rcx, [rsp+48h+var_18]
0x1400176de  xor     rcx, rsp; StackCookie
0x1400176e1  call    __security_check_cookie
0x1400176e6  add     rsp, 40h
0x1400176ea  pop     rbx
0x1400176eb  retn
```

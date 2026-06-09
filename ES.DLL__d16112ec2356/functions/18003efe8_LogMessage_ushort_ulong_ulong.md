# LogMessage(ushort,ulong,ulong,...)

- ea: `0x18003efe8`
- end: `0x18003f078`
- name: `?LogMessage@@YAXGKKZZ`
- size: `144`
- prototype: `void(unsigned __int16, unsigned int, unsigned int, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009498`
- `0x1800140c0`
- `0x18001af70`
- `0x180029b50`

## callees

- `0x18003eeb8`
- `0x18003efe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f069`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f069`

## pseudocode

```c
void LogMessage(unsigned __int16 a1, DWORD a2, unsigned int a3, ...)
{
  va_list v3; // rdi
  LPVOID v5; // rax
  void *v6; // rbx
  __int64 i; // r8
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  va_copy(v3, va);
  v5 = CoTaskMemAlloc(saturated_mul(a3, 8u));
  v6 = v5;
  if ( v5 )
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v3 += 8;
      *((_QWORD *)v5 + i) = *((_QWORD *)v3 - 1);
    }
    LogEventMessage(a2);
    CoTaskMemFree(v6);
  }
}

```

## disassembly

```asm
0x18003efe8  mov     rax, rsp
0x18003efeb  mov     [rax+18h], r8d
0x18003efef  mov     [rax+20h], r9
0x18003eff3  push    rbx
0x18003eff4  push    rbp
0x18003eff5  push    rsi
0x18003eff6  push    rdi
0x18003eff7  sub     rsp, 38h
0x18003effb  mov     qword ptr [rax-38h], 0
0x18003f003  lea     rdi, [rax+20h]
0x18003f007  movzx   ebp, cx
0x18003f00a  mov     r8d, r8d
0x18003f00d  mov     esi, edx
0x18003f00f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003f016  mov     eax, 8
0x18003f01b  mul     r8
0x18003f01e  cmovb   rax, rcx
0x18003f022  mov     rcx, rax; cb
0x18003f025  call    cs:__imp_CoTaskMemAlloc
0x18003f02b  mov     rbx, rax
0x18003f02e  test    rax, rax
0x18003f031  jz      short loc_18003F06F
0x18003f033  xor     r8d, r8d
0x18003f036  cmp     [rsp+58h+arg_10], r8d
0x18003f03b  jbe     short loc_18003F053
0x18003f03d  lea     rdi, [rdi+8]
0x18003f041  mov     rcx, [rdi-8]
0x18003f045  mov     [rax+r8*8], rcx
0x18003f049  inc     r8d
0x18003f04c  cmp     r8d, [rsp+58h+arg_10]
0x18003f051  jb      short loc_18003F03D
0x18003f053  movzx   r9d, word ptr [rsp+58h+arg_10]
0x18003f059  mov     r8, rbx
0x18003f05c  movzx   edx, bp
0x18003f05f  mov     ecx, esi; dwEventID
0x18003f061  call    LogEventMessage
0x18003f066  mov     rcx, rbx; pv
0x18003f069  call    cs:__imp_CoTaskMemFree
0x18003f06f  add     rsp, 38h
0x18003f073  pop     rdi
0x18003f074  pop     rsi
0x18003f075  pop     rbp
0x18003f076  pop     rbx
0x18003f077  retn
```

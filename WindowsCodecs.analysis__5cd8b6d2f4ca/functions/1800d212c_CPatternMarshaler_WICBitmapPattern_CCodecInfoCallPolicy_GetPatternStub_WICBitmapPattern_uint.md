# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatternStub(WICBitmapPattern * *,uint *)

- ea: `0x1800d212c`
- end: `0x1800d2286`
- name: `?GetPatternStub@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@QEAAJPEAPEAUWICBitmapPattern@@PEAI@Z`
- size: `346`
- prototype: `__int64 __fastcall(CCodecInfoCallPolicy *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180192b80`

## callees

- `0x1800bd9d4`
- `0x1800d212c`
- `0x1800d2484`
- `0x1800d250c`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d21fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d21fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2231`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatternStub(
        CCodecInfoCallPolicy *a1,
        _QWORD *a2,
        _DWORD *a3)
{
  unsigned int v5; // ebx
  int Patterns; // eax

  if ( a2 && a3 )
  {
    *a3 = 0;
    *a2 = 0;
    Patterns = CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(a1);
    v5 = Patterns;
    if ( Patterns >= 0 )
    {
      *a3 = 0;
      *a2 = 0;
    }
    else if ( (_DWORD)g_doStackCaptures )
    {
      DoStackCapture(Patterns);
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024809);
  }
  CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(0);
  return v5;
}

```

## disassembly

```asm
0x1800d212c  mov     [rsp-38h+arg_0], rbx
0x1800d2131  push    rbp
0x1800d2132  push    rsi
0x1800d2133  push    rdi
0x1800d2134  push    r12
0x1800d2136  push    r13
0x1800d2138  push    r14
0x1800d213a  push    r15
0x1800d213c  mov     rbp, rsp
0x1800d213f  sub     rsp, 30h
0x1800d2143  xor     r14d, r14d
0x1800d2146  mov     r12, r8
0x1800d2149  mov     [rbp+var_10], r14
0x1800d214d  mov     r13, rdx
0x1800d2150  mov     [rbp+arg_18], r14d
0x1800d2154  mov     edi, r14d
0x1800d2157  mov     dword ptr [rbp+arg_8], r14d
0x1800d215b  mov     esi, r14d
0x1800d215e  test    rdx, rdx
0x1800d2161  jnz     short loc_1800D217A
0x1800d2163  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800d216a  mov     ebx, 80070057h
0x1800d216f  jz      short loc_1800D21B3
0x1800d2171  mov     ecx, ebx; int
0x1800d2173  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2178  jmp     short loc_1800D21B3
0x1800d217a  test    r12, r12
0x1800d217d  jz      short loc_1800D2163
0x1800d217f  mov     [r8], r14d
0x1800d2182  lea     r9, [rbp+arg_18]
0x1800d2186  mov     [rdx], r14
0x1800d2189  lea     r8, [rbp+arg_8]
0x1800d218d  lea     rdx, [rbp+var_10]
0x1800d2191  call    ?GetPatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@AEAAJPEAPEAUWICBitmapPattern@@PEAI1@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(WICBitmapPattern * *,uint *,uint *)
0x1800d2196  mov     ebx, eax
0x1800d2198  test    eax, eax
0x1800d219a  jns     short loc_1800D21DD
0x1800d219c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800d21a3  jz      short loc_1800D21D9
0x1800d21a5  mov     ecx, eax; int
0x1800d21a7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d21ac  mov     esi, dword ptr [rbp+arg_8]
0x1800d21af  mov     rdi, [rbp+var_10]
0x1800d21b3  mov     r8d, [rbp+arg_18]
0x1800d21b7  mov     edx, esi
0x1800d21b9  mov     rcx, rdi; pv
0x1800d21bc  call    ?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)
0x1800d21c1  mov     eax, ebx
0x1800d21c3  mov     rbx, [rsp+30h+arg_0]
0x1800d21c8  add     rsp, 30h
0x1800d21cc  pop     r15
0x1800d21ce  pop     r14
0x1800d21d0  pop     r13
0x1800d21d2  pop     r12
0x1800d21d4  pop     rdi
0x1800d21d5  pop     rsi
0x1800d21d6  pop     rbp
0x1800d21d7  retn
0x1800d21d9  test    eax, eax
0x1800d21db  js      short loc_1800D21AC
0x1800d21dd  mov     rdi, [rbp+var_10]
0x1800d21e1  mov     r15d, r14d
0x1800d21e4  mov     esi, dword ptr [rbp+arg_8]
0x1800d21e7  cmp     r15d, esi
0x1800d21ea  jnb     loc_1800D2277
0x1800d21f0  mov     eax, r15d
0x1800d21f3  lea     r14, [rax+rax*4]
0x1800d21f7  mov     ecx, [rdi+r14*8+8]; cb
0x1800d21fc  call    cs:__imp_CoTaskMemAlloc
0x1800d2203  nop     dword ptr [rax+rax+00h]
0x1800d2208  mov     [rbp+arg_8], rax
0x1800d220c  test    rax, rax
0x1800d220f  jz      short loc_1800D2266
0x1800d2211  mov     r8d, [rdi+r14*8+8]; Size
0x1800d2216  mov     rcx, rax; void *
0x1800d2219  mov     rdx, [rdi+r14*8+10h]; Src
0x1800d221e  call    memcpy_0
0x1800d2223  mov     rax, [rbp+arg_8]
0x1800d2227  mov     [rdi+r14*8+10h], rax
0x1800d222c  mov     ecx, [rdi+r14*8+8]; cb
0x1800d2231  call    cs:__imp_CoTaskMemAlloc
0x1800d2238  nop     dword ptr [rax+rax+00h]
0x1800d223d  mov     [rbp+arg_8], rax
0x1800d2241  test    rax, rax
0x1800d2244  jz      short loc_1800D2266
0x1800d2246  mov     r8d, [rdi+r14*8+8]; Size
0x1800d224b  mov     rcx, rax; void *
0x1800d224e  mov     rdx, [rdi+r14*8+18h]; Src
0x1800d2253  call    memcpy_0
0x1800d2258  mov     rax, [rbp+arg_8]
0x1800d225c  inc     r15d
0x1800d225f  mov     [rdi+r14*8+18h], rax
0x1800d2264  jmp     short loc_1800D21E7
0x1800d2266  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d226d  mov     ebx, 8007000Eh
0x1800d2272  jmp     loc_1800D216F
0x1800d2277  mov     [r12], esi
0x1800d227b  mov     [r13+0], rdi
0x1800d227f  xor     edi, edi
0x1800d2281  jmp     loc_1800D21B3
```

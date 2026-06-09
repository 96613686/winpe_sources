# CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatternStub(WICMetadataPattern * *,uint *)

- ea: `0x1800da788`
- end: `0x1800da8e2`
- name: `?GetPatternStub@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@QEAAJPEAPEAUWICMetadataPattern@@PEAI@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180192cf0`

## callees

- `0x1800bd9d4`
- `0x1800d2484`
- `0x1800da788`
- `0x1800daae8`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800da88d`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatternStub(
        CMetadataRenderInfoPolicy *a1,
        _QWORD *a2,
        _DWORD *a3)
{
  unsigned int v5; // ebx
  int Patterns; // eax

  if ( a2 && a3 )
  {
    *a3 = 0;
    *a2 = 0;
    Patterns = CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(a1);
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
  CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(0, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x1800da788  mov     [rsp-38h+arg_0], rbx
0x1800da78d  push    rbp
0x1800da78e  push    rsi
0x1800da78f  push    rdi
0x1800da790  push    r12
0x1800da792  push    r13
0x1800da794  push    r14
0x1800da796  push    r15
0x1800da798  mov     rbp, rsp
0x1800da79b  sub     rsp, 30h
0x1800da79f  xor     r14d, r14d
0x1800da7a2  mov     r12, r8
0x1800da7a5  mov     [rbp+var_10], r14
0x1800da7a9  mov     r13, rdx
0x1800da7ac  mov     [rbp+arg_18], r14d
0x1800da7b0  mov     edi, r14d
0x1800da7b3  mov     dword ptr [rbp+arg_8], r14d
0x1800da7b7  mov     esi, r14d
0x1800da7ba  test    rdx, rdx
0x1800da7bd  jnz     short loc_1800DA7D6
0x1800da7bf  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800da7c6  mov     ebx, 80070057h
0x1800da7cb  jz      short loc_1800DA80F
0x1800da7cd  mov     ecx, ebx; int
0x1800da7cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800da7d4  jmp     short loc_1800DA80F
0x1800da7d6  test    r12, r12
0x1800da7d9  jz      short loc_1800DA7BF
0x1800da7db  mov     [r8], r14d
0x1800da7de  lea     r9, [rbp+arg_18]
0x1800da7e2  mov     [rdx], r14
0x1800da7e5  lea     r8, [rbp+arg_8]
0x1800da7e9  lea     rdx, [rbp+var_10]
0x1800da7ed  call    ?GetPatterns@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@AEAAJPEAPEAUWICMetadataPattern@@PEAI1@Z; CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(WICMetadataPattern * *,uint *,uint *)
0x1800da7f2  mov     ebx, eax
0x1800da7f4  test    eax, eax
0x1800da7f6  jns     short loc_1800DA839
0x1800da7f8  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800da7ff  jz      short loc_1800DA835
0x1800da801  mov     ecx, eax; int
0x1800da803  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800da808  mov     esi, dword ptr [rbp+arg_8]
0x1800da80b  mov     rdi, [rbp+var_10]
0x1800da80f  mov     r8d, [rbp+arg_18]
0x1800da813  mov     edx, esi
0x1800da815  mov     rcx, rdi; pv
0x1800da818  call    ?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)
0x1800da81d  mov     eax, ebx
0x1800da81f  mov     rbx, [rsp+30h+arg_0]
0x1800da824  add     rsp, 30h
0x1800da828  pop     r15
0x1800da82a  pop     r14
0x1800da82c  pop     r13
0x1800da82e  pop     r12
0x1800da830  pop     rdi
0x1800da831  pop     rsi
0x1800da832  pop     rbp
0x1800da833  retn
0x1800da835  test    eax, eax
0x1800da837  js      short loc_1800DA808
0x1800da839  mov     rdi, [rbp+var_10]
0x1800da83d  mov     r15d, r14d
0x1800da840  mov     esi, dword ptr [rbp+arg_8]
0x1800da843  cmp     r15d, esi
0x1800da846  jnb     loc_1800DA8D3
0x1800da84c  mov     eax, r15d
0x1800da84f  lea     r14, [rax+rax*4]
0x1800da853  mov     ecx, [rdi+r14*8+8]; cb
0x1800da858  call    cs:__imp_CoTaskMemAlloc
0x1800da85f  nop     dword ptr [rax+rax+00h]
0x1800da864  mov     [rbp+arg_8], rax
0x1800da868  test    rax, rax
0x1800da86b  jz      short loc_1800DA8C2
0x1800da86d  mov     r8d, [rdi+r14*8+8]; Size
0x1800da872  mov     rcx, rax; void *
0x1800da875  mov     rdx, [rdi+r14*8+10h]; Src
0x1800da87a  call    memcpy_0
0x1800da87f  mov     rax, [rbp+arg_8]
0x1800da883  mov     [rdi+r14*8+10h], rax
0x1800da888  mov     ecx, [rdi+r14*8+8]; cb
0x1800da88d  call    cs:__imp_CoTaskMemAlloc
0x1800da894  nop     dword ptr [rax+rax+00h]
0x1800da899  mov     [rbp+arg_8], rax
0x1800da89d  test    rax, rax
0x1800da8a0  jz      short loc_1800DA8C2
0x1800da8a2  mov     r8d, [rdi+r14*8+8]; Size
0x1800da8a7  mov     rcx, rax; void *
0x1800da8aa  mov     rdx, [rdi+r14*8+18h]; Src
0x1800da8af  call    memcpy_0
0x1800da8b4  mov     rax, [rbp+arg_8]
0x1800da8b8  inc     r15d
0x1800da8bb  mov     [rdi+r14*8+18h], rax
0x1800da8c0  jmp     short loc_1800DA843
0x1800da8c2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800da8c9  mov     ebx, 8007000Eh
0x1800da8ce  jmp     loc_1800DA7CB
0x1800da8d3  mov     [r12], esi
0x1800da8d7  mov     [r13+0], rdi
0x1800da8db  xor     edi, edi
0x1800da8dd  jmp     loc_1800DA80F
```

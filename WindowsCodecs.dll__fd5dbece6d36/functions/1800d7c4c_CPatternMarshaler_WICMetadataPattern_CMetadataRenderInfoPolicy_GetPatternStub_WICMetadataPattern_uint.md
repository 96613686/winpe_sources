# CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatternStub(WICMetadataPattern * *,uint *)

- ea: `0x1800d7c4c`
- end: `0x1800d7d95`
- name: `?GetPatternStub@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@QEAAJPEAPEAUWICMetadataPattern@@PEAI@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18018fdd0`

## callees

- `0x1800bb784`
- `0x1800cfbd8`
- `0x1800d7c4c`
- `0x1800d7f98`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7d46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7d46`

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
0x1800d7c4c  mov     [rsp-38h+arg_0], rbx
0x1800d7c51  push    rbp
0x1800d7c52  push    rsi
0x1800d7c53  push    rdi
0x1800d7c54  push    r12
0x1800d7c56  push    r13
0x1800d7c58  push    r14
0x1800d7c5a  push    r15
0x1800d7c5c  mov     rbp, rsp
0x1800d7c5f  sub     rsp, 30h
0x1800d7c63  xor     r14d, r14d
0x1800d7c66  mov     r12, r8
0x1800d7c69  mov     [rbp+var_10], r14
0x1800d7c6d  mov     r13, rdx
0x1800d7c70  mov     [rbp+arg_18], r14d
0x1800d7c74  mov     edi, r14d
0x1800d7c77  mov     dword ptr [rbp+arg_8], r14d
0x1800d7c7b  mov     esi, r14d
0x1800d7c7e  test    rdx, rdx
0x1800d7c81  jnz     short loc_1800D7C9A
0x1800d7c83  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800d7c8a  mov     ebx, 80070057h
0x1800d7c8f  jz      short loc_1800D7CD3
0x1800d7c91  mov     ecx, ebx; int
0x1800d7c93  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d7c98  jmp     short loc_1800D7CD3
0x1800d7c9a  test    r12, r12
0x1800d7c9d  jz      short loc_1800D7C83
0x1800d7c9f  mov     [r8], r14d
0x1800d7ca2  lea     r9, [rbp+arg_18]
0x1800d7ca6  mov     [rdx], r14
0x1800d7ca9  lea     r8, [rbp+arg_8]
0x1800d7cad  lea     rdx, [rbp+var_10]
0x1800d7cb1  call    ?GetPatterns@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@AEAAJPEAPEAUWICMetadataPattern@@PEAI1@Z; CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(WICMetadataPattern * *,uint *,uint *)
0x1800d7cb6  mov     ebx, eax
0x1800d7cb8  test    eax, eax
0x1800d7cba  jns     short loc_1800D7CFC
0x1800d7cbc  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800d7cc3  jz      short loc_1800D7CF8
0x1800d7cc5  mov     ecx, eax; int
0x1800d7cc7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d7ccc  mov     esi, dword ptr [rbp+arg_8]
0x1800d7ccf  mov     rdi, [rbp+var_10]
0x1800d7cd3  mov     r8d, [rbp+arg_18]
0x1800d7cd7  mov     edx, esi
0x1800d7cd9  mov     rcx, rdi; pv
0x1800d7cdc  call    ?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)
0x1800d7ce1  mov     eax, ebx
0x1800d7ce3  mov     rbx, [rsp+30h+arg_0]
0x1800d7ce8  add     rsp, 30h
0x1800d7cec  pop     r15
0x1800d7cee  pop     r14
0x1800d7cf0  pop     r13
0x1800d7cf2  pop     r12
0x1800d7cf4  pop     rdi
0x1800d7cf5  pop     rsi
0x1800d7cf6  pop     rbp
0x1800d7cf7  retn
0x1800d7cf8  test    eax, eax
0x1800d7cfa  js      short loc_1800D7CCC
0x1800d7cfc  mov     rdi, [rbp+var_10]
0x1800d7d00  mov     r15d, r14d
0x1800d7d03  mov     esi, dword ptr [rbp+arg_8]
0x1800d7d06  cmp     r15d, esi
0x1800d7d09  jnb     short loc_1800D7D86
0x1800d7d0b  mov     eax, r15d
0x1800d7d0e  lea     r14, [rax+rax*4]
0x1800d7d12  mov     ecx, [rdi+r14*8+8]; cb
0x1800d7d17  call    cs:__imp_CoTaskMemAlloc
0x1800d7d1d  mov     [rbp+arg_8], rax
0x1800d7d21  test    rax, rax
0x1800d7d24  jz      short loc_1800D7D75
0x1800d7d26  mov     r8d, [rdi+r14*8+8]; Size
0x1800d7d2b  mov     rcx, rax; void *
0x1800d7d2e  mov     rdx, [rdi+r14*8+10h]; Src
0x1800d7d33  call    memcpy_0
0x1800d7d38  mov     rax, [rbp+arg_8]
0x1800d7d3c  mov     [rdi+r14*8+10h], rax
0x1800d7d41  mov     ecx, [rdi+r14*8+8]; cb
0x1800d7d46  call    cs:__imp_CoTaskMemAlloc
0x1800d7d4c  mov     [rbp+arg_8], rax
0x1800d7d50  test    rax, rax
0x1800d7d53  jz      short loc_1800D7D75
0x1800d7d55  mov     r8d, [rdi+r14*8+8]; Size
0x1800d7d5a  mov     rcx, rax; void *
0x1800d7d5d  mov     rdx, [rdi+r14*8+18h]; Src
0x1800d7d62  call    memcpy_0
0x1800d7d67  mov     rax, [rbp+arg_8]
0x1800d7d6b  inc     r15d
0x1800d7d6e  mov     [rdi+r14*8+18h], rax
0x1800d7d73  jmp     short loc_1800D7D06
0x1800d7d75  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7d7c  mov     ebx, 8007000Eh
0x1800d7d81  jmp     loc_1800D7C8F
0x1800d7d86  mov     [r12], esi
0x1800d7d8a  mov     [r13+0], rdi
0x1800d7d8e  xor     edi, edi
0x1800d7d90  jmp     loc_1800D7CD3
```

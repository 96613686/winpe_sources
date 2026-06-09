# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatternStub(WICBitmapPattern * *,uint *)

- ea: `0x1800cf898`
- end: `0x1800cf9e1`
- name: `?GetPatternStub@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@QEAAJPEAPEAUWICBitmapPattern@@PEAI@Z`
- size: `329`
- prototype: `__int64 __fastcall(CCodecInfoCallPolicy *, struct WICBitmapPattern **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18018fc60`

## callees

- `0x1800bb784`
- `0x1800cf898`
- `0x1800cfbd8`
- `0x1800cfc4c`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cf992`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatternStub(
        CCodecInfoCallPolicy *a1,
        struct WICBitmapPattern **a2,
        unsigned int *a3)
{
  struct WICBitmapPattern *v5; // rdi
  bool v6; // zf
  unsigned int v7; // ebx
  int Patterns; // eax
  unsigned int v10; // r15d
  unsigned int v11; // esi
  __int64 v12; // r14
  BYTE *v13; // rax
  BYTE *v14; // rax
  struct WICBitmapPattern *v15; // [rsp+20h] [rbp-10h] BYREF
  BYTE *v16; // [rsp+78h] [rbp+48h] BYREF
  int v17; // [rsp+88h] [rbp+58h] BYREF

  v15 = 0;
  v17 = 0;
  v5 = 0;
  LODWORD(v16) = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    *a2 = 0;
    Patterns = CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(
                 a1,
                 &v15,
                 (unsigned int *)&v16,
                 &v17);
    v7 = Patterns;
    if ( Patterns >= 0 )
    {
      v5 = v15;
      v10 = 0;
      v11 = (unsigned int)v16;
      while ( v10 < v11 )
      {
        v12 = v10;
        v13 = (BYTE *)CoTaskMemAlloc(v5[v10].Length);
        v16 = v13;
        if ( !v13
          || (memcpy_0(v13, v5[v10].Pattern, v5[v10].Length),
              v5[v10].Pattern = v16,
              v14 = (BYTE *)CoTaskMemAlloc(v5[v10].Length),
              (v16 = v14) == 0) )
        {
          v6 = (_DWORD)g_doStackCaptures == 0;
          v7 = -2147024882;
          goto LABEL_3;
        }
        memcpy_0(v14, v5[v10].Mask, v5[v10].Length);
        ++v10;
        v5[v12].Mask = v16;
      }
      *a3 = v11;
      *a2 = v5;
      v5 = 0;
    }
    else
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(Patterns);
      v5 = v15;
    }
  }
  else
  {
    v6 = (_DWORD)g_doStackCaptures == 0;
    v7 = -2147024809;
LABEL_3:
    if ( !v6 )
      DoStackCapture(v7);
  }
  CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(v5);
  return v7;
}

```

## disassembly

```asm
0x1800cf898  mov     [rsp-38h+arg_0], rbx
0x1800cf89d  push    rbp
0x1800cf89e  push    rsi
0x1800cf89f  push    rdi
0x1800cf8a0  push    r12
0x1800cf8a2  push    r13
0x1800cf8a4  push    r14
0x1800cf8a6  push    r15
0x1800cf8a8  mov     rbp, rsp
0x1800cf8ab  sub     rsp, 30h
0x1800cf8af  xor     r14d, r14d
0x1800cf8b2  mov     r12, r8
0x1800cf8b5  mov     [rbp+var_10], r14
0x1800cf8b9  mov     r13, rdx
0x1800cf8bc  mov     [rbp+arg_18], r14d
0x1800cf8c0  mov     edi, r14d
0x1800cf8c3  mov     dword ptr [rbp+arg_8], r14d
0x1800cf8c7  mov     esi, r14d
0x1800cf8ca  test    rdx, rdx
0x1800cf8cd  jnz     short loc_1800CF8E6
0x1800cf8cf  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800cf8d6  mov     ebx, 80070057h
0x1800cf8db  jz      short loc_1800CF91F
0x1800cf8dd  mov     ecx, ebx; int
0x1800cf8df  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cf8e4  jmp     short loc_1800CF91F
0x1800cf8e6  test    r12, r12
0x1800cf8e9  jz      short loc_1800CF8CF
0x1800cf8eb  mov     [r8], r14d
0x1800cf8ee  lea     r9, [rbp+arg_18]
0x1800cf8f2  mov     [rdx], r14
0x1800cf8f5  lea     r8, [rbp+arg_8]
0x1800cf8f9  lea     rdx, [rbp+var_10]
0x1800cf8fd  call    ?GetPatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@AEAAJPEAPEAUWICBitmapPattern@@PEAI1@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(WICBitmapPattern * *,uint *,uint *)
0x1800cf902  mov     ebx, eax
0x1800cf904  test    eax, eax
0x1800cf906  jns     short loc_1800CF948
0x1800cf908  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800cf90f  jz      short loc_1800CF944
0x1800cf911  mov     ecx, eax; int
0x1800cf913  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cf918  mov     esi, dword ptr [rbp+arg_8]
0x1800cf91b  mov     rdi, [rbp+var_10]
0x1800cf91f  mov     r8d, [rbp+arg_18]
0x1800cf923  mov     edx, esi
0x1800cf925  mov     rcx, rdi; pv
0x1800cf928  call    ?FreePatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@CAXPEAUWICBitmapPattern@@II@Z; CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::FreePatterns(WICBitmapPattern *,uint,uint)
0x1800cf92d  mov     eax, ebx
0x1800cf92f  mov     rbx, [rsp+30h+arg_0]
0x1800cf934  add     rsp, 30h
0x1800cf938  pop     r15
0x1800cf93a  pop     r14
0x1800cf93c  pop     r13
0x1800cf93e  pop     r12
0x1800cf940  pop     rdi
0x1800cf941  pop     rsi
0x1800cf942  pop     rbp
0x1800cf943  retn
0x1800cf944  test    eax, eax
0x1800cf946  js      short loc_1800CF918
0x1800cf948  mov     rdi, [rbp+var_10]
0x1800cf94c  mov     r15d, r14d
0x1800cf94f  mov     esi, dword ptr [rbp+arg_8]
0x1800cf952  cmp     r15d, esi
0x1800cf955  jnb     short loc_1800CF9D2
0x1800cf957  mov     eax, r15d
0x1800cf95a  lea     r14, [rax+rax*4]
0x1800cf95e  mov     ecx, [rdi+r14*8+8]; cb
0x1800cf963  call    cs:__imp_CoTaskMemAlloc
0x1800cf969  mov     [rbp+arg_8], rax
0x1800cf96d  test    rax, rax
0x1800cf970  jz      short loc_1800CF9C1
0x1800cf972  mov     r8d, [rdi+r14*8+8]; Size
0x1800cf977  mov     rcx, rax; void *
0x1800cf97a  mov     rdx, [rdi+r14*8+10h]; Src
0x1800cf97f  call    memcpy_0
0x1800cf984  mov     rax, [rbp+arg_8]
0x1800cf988  mov     [rdi+r14*8+10h], rax
0x1800cf98d  mov     ecx, [rdi+r14*8+8]; cb
0x1800cf992  call    cs:__imp_CoTaskMemAlloc
0x1800cf998  mov     [rbp+arg_8], rax
0x1800cf99c  test    rax, rax
0x1800cf99f  jz      short loc_1800CF9C1
0x1800cf9a1  mov     r8d, [rdi+r14*8+8]; Size
0x1800cf9a6  mov     rcx, rax; void *
0x1800cf9a9  mov     rdx, [rdi+r14*8+18h]; Src
0x1800cf9ae  call    memcpy_0
0x1800cf9b3  mov     rax, [rbp+arg_8]
0x1800cf9b7  inc     r15d
0x1800cf9ba  mov     [rdi+r14*8+18h], rax
0x1800cf9bf  jmp     short loc_1800CF952
0x1800cf9c1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cf9c8  mov     ebx, 8007000Eh
0x1800cf9cd  jmp     loc_1800CF8DB
0x1800cf9d2  mov     [r12], esi
0x1800cf9d6  mov     [r13+0], rdi
0x1800cf9da  xor     edi, edi
0x1800cf9dc  jmp     loc_1800CF91F
```

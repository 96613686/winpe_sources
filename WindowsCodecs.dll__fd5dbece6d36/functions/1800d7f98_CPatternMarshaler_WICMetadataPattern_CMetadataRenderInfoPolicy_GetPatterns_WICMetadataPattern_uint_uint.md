# CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(WICMetadataPattern * *,uint *,uint *)

- ea: `0x1800d7f98`
- end: `0x1800d8088`
- name: `?GetPatterns@?$CPatternMarshaler@UWICMetadataPattern@@VCMetadataRenderInfoPolicy@@@@AEAAJPEAPEAUWICMetadataPattern@@PEAI1@Z`
- size: `240`
- prototype: `__int64 __fastcall(CMetadataRenderInfoPolicy *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7c4c`

## callees

- `0x1800bb784`
- `0x1800d7f98`
- `0x1800d8090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d7ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8073`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICMetadataPattern,CMetadataRenderInfoPolicy>::GetPatterns(
        CMetadataRenderInfoPolicy *this,
        struct WICMetadataPattern **a2,
        unsigned int *a3,
        _DWORD *a4)
{
  int Patterns; // eax
  unsigned int v9; // ebx
  struct WICMetadataPattern *v10; // rdi
  int v11; // ecx
  int v12; // eax
  unsigned int v14[18]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(cb) = 0;
  v14[0] = 0;
  Patterns = CMetadataRenderInfoPolicy::GetPatterns(this, 0, 0, 0, (unsigned int *)&cb);
  v9 = Patterns;
  if ( Patterns < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(Patterns);
    goto LABEL_13;
  }
  v10 = (struct WICMetadataPattern *)CoTaskMemAlloc((unsigned int)cb);
  if ( v10 )
  {
    v12 = CMetadataRenderInfoPolicy::GetPatterns(this, cb, v10, v14, (unsigned int *)&cb);
    v9 = v12;
    if ( v12 >= 0 )
    {
      *a3 = v14[0];
      *a4 = cb;
      *a2 = v10;
LABEL_13:
      v10 = 0;
      goto LABEL_14;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_14;
    v11 = v12;
    goto LABEL_7;
  }
  v9 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
  {
    v11 = -2147024882;
LABEL_7:
    DoStackCapture(v11);
  }
LABEL_14:
  CoTaskMemFree(v10);
  return v9;
}

```

## disassembly

```asm
0x1800d7f98  mov     rax, rsp
0x1800d7f9b  push    rbx
0x1800d7f9c  push    rbp
0x1800d7f9d  push    rsi
0x1800d7f9e  push    rdi
0x1800d7f9f  push    r14
0x1800d7fa1  push    r15
0x1800d7fa3  sub     rsp, 48h
0x1800d7fa7  mov     dword ptr [rax+8], 0
0x1800d7fae  mov     r14, r9
0x1800d7fb1  mov     dword ptr [rax-48h], 0
0x1800d7fb8  lea     rax, [rax+8]
0x1800d7fbc  mov     r15, r8
0x1800d7fbf  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800d7fc4  mov     rbp, rdx
0x1800d7fc7  xor     r9d, r9d; unsigned int *
0x1800d7fca  xor     r8d, r8d; struct WICMetadataPattern *
0x1800d7fcd  xor     edx, edx; unsigned int
0x1800d7fcf  mov     rsi, rcx
0x1800d7fd2  call    ?GetPatterns@CMetadataRenderInfoPolicy@@QEAAJIPEAUWICMetadataPattern@@PEAI1@Z; CMetadataRenderInfoPolicy::GetPatterns(uint,WICMetadataPattern *,uint *,uint *)
0x1800d7fd7  mov     ebx, eax
0x1800d7fd9  test    eax, eax
0x1800d7fdb  jns     short loc_1800D7FF3
0x1800d7fdd  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d7fe4  jz      loc_1800D806E
0x1800d7fea  mov     ecx, eax; int
0x1800d7fec  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d7ff1  jmp     short loc_1800D806E
0x1800d7ff3  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x1800d7ffa  call    cs:__imp_CoTaskMemAlloc
0x1800d8000  mov     rdi, rax
0x1800d8003  test    rax, rax
0x1800d8006  jnz     short loc_1800D801E
0x1800d8008  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d800e  mov     ebx, 8007000Eh
0x1800d8013  jz      short loc_1800D8070
0x1800d8015  mov     ecx, ebx; int
0x1800d8017  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d801c  jmp     short loc_1800D8070
0x1800d801e  mov     edx, dword ptr [rsp+78h+cb]; unsigned int
0x1800d8025  lea     rax, [rsp+78h+cb]
0x1800d802d  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800d8032  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800d8037  mov     r8, rdi; struct WICMetadataPattern *
0x1800d803a  mov     rcx, rsi; this
0x1800d803d  call    ?GetPatterns@CMetadataRenderInfoPolicy@@QEAAJIPEAUWICMetadataPattern@@PEAI1@Z; CMetadataRenderInfoPolicy::GetPatterns(uint,WICMetadataPattern *,uint *,uint *)
0x1800d8042  mov     ebx, eax
0x1800d8044  test    eax, eax
0x1800d8046  jns     short loc_1800D8059
0x1800d8048  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d804f  jz      short loc_1800D8055
0x1800d8051  mov     ecx, eax
0x1800d8053  jmp     short loc_1800D8017
0x1800d8055  test    eax, eax
0x1800d8057  js      short loc_1800D8070
0x1800d8059  mov     ecx, [rsp+78h+var_48]
0x1800d805d  mov     [r15], ecx
0x1800d8060  mov     ecx, dword ptr [rsp+78h+cb]
0x1800d8067  mov     [r14], ecx
0x1800d806a  mov     [rbp+0], rdi
0x1800d806e  xor     edi, edi
0x1800d8070  mov     rcx, rdi; pv
0x1800d8073  call    cs:__imp_CoTaskMemFree
0x1800d8079  mov     eax, ebx
0x1800d807b  add     rsp, 48h
0x1800d807f  pop     r15
0x1800d8081  pop     r14
0x1800d8083  pop     rdi
0x1800d8084  pop     rsi
0x1800d8085  pop     rbp
0x1800d8086  pop     rbx
0x1800d8087  retn
```

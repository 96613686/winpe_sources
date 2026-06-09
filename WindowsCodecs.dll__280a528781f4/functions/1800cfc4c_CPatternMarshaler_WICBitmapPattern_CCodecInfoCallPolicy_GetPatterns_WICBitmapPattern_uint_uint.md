# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(WICBitmapPattern * *,uint *,uint *)

- ea: `0x1800cfc4c`
- end: `0x1800cfd3c`
- name: `?GetPatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@AEAAJPEAPEAUWICBitmapPattern@@PEAI1@Z`
- size: `240`
- prototype: `__int64 __fastcall(CCodecInfoCallPolicy *this, struct WICBitmapPattern **, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cf898`

## callees

- `0x1800bb784`
- `0x1800cfc4c`
- `0x1800cfd44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cfcae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cfcae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfd27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cfd27`

## pseudocode

```c
__int64 __fastcall CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(
        CCodecInfoCallPolicy *this,
        struct WICBitmapPattern **a2,
        unsigned int *a3,
        _DWORD *a4)
{
  int Patterns; // eax
  unsigned int v9; // ebx
  struct WICBitmapPattern *v10; // rdi
  int v11; // ecx
  int v12; // eax
  unsigned int v14[18]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(cb) = 0;
  v14[0] = 0;
  Patterns = CCodecInfoCallPolicy::GetPatterns(this, 0, 0, 0, (unsigned int *)&cb);
  v9 = Patterns;
  if ( Patterns < 0 )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(Patterns);
    goto LABEL_13;
  }
  v10 = (struct WICBitmapPattern *)CoTaskMemAlloc((unsigned int)cb);
  if ( v10 )
  {
    v12 = CCodecInfoCallPolicy::GetPatterns(this, cb, v10, v14, (unsigned int *)&cb);
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
0x1800cfc4c  mov     rax, rsp
0x1800cfc4f  push    rbx
0x1800cfc50  push    rbp
0x1800cfc51  push    rsi
0x1800cfc52  push    rdi
0x1800cfc53  push    r14
0x1800cfc55  push    r15
0x1800cfc57  sub     rsp, 48h
0x1800cfc5b  mov     dword ptr [rax+8], 0
0x1800cfc62  mov     r14, r9
0x1800cfc65  mov     dword ptr [rax-48h], 0
0x1800cfc6c  lea     rax, [rax+8]
0x1800cfc70  mov     r15, r8
0x1800cfc73  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800cfc78  mov     rbp, rdx
0x1800cfc7b  xor     r9d, r9d; unsigned int *
0x1800cfc7e  xor     r8d, r8d; struct WICBitmapPattern *
0x1800cfc81  xor     edx, edx; unsigned int
0x1800cfc83  mov     rsi, rcx
0x1800cfc86  call    ?GetPatterns@CCodecInfoCallPolicy@@QEAAJIPEAUWICBitmapPattern@@PEAI1@Z; CCodecInfoCallPolicy::GetPatterns(uint,WICBitmapPattern *,uint *,uint *)
0x1800cfc8b  mov     ebx, eax
0x1800cfc8d  test    eax, eax
0x1800cfc8f  jns     short loc_1800CFCA7
0x1800cfc91  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cfc98  jz      loc_1800CFD22
0x1800cfc9e  mov     ecx, eax; int
0x1800cfca0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cfca5  jmp     short loc_1800CFD22
0x1800cfca7  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x1800cfcae  call    cs:__imp_CoTaskMemAlloc
0x1800cfcb4  mov     rdi, rax
0x1800cfcb7  test    rax, rax
0x1800cfcba  jnz     short loc_1800CFCD2
0x1800cfcbc  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800cfcc2  mov     ebx, 8007000Eh
0x1800cfcc7  jz      short loc_1800CFD24
0x1800cfcc9  mov     ecx, ebx; int
0x1800cfccb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cfcd0  jmp     short loc_1800CFD24
0x1800cfcd2  mov     edx, dword ptr [rsp+78h+cb]; unsigned int
0x1800cfcd9  lea     rax, [rsp+78h+cb]
0x1800cfce1  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800cfce6  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800cfceb  mov     r8, rdi; struct WICBitmapPattern *
0x1800cfcee  mov     rcx, rsi; this
0x1800cfcf1  call    ?GetPatterns@CCodecInfoCallPolicy@@QEAAJIPEAUWICBitmapPattern@@PEAI1@Z; CCodecInfoCallPolicy::GetPatterns(uint,WICBitmapPattern *,uint *,uint *)
0x1800cfcf6  mov     ebx, eax
0x1800cfcf8  test    eax, eax
0x1800cfcfa  jns     short loc_1800CFD0D
0x1800cfcfc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cfd03  jz      short loc_1800CFD09
0x1800cfd05  mov     ecx, eax
0x1800cfd07  jmp     short loc_1800CFCCB
0x1800cfd09  test    eax, eax
0x1800cfd0b  js      short loc_1800CFD24
0x1800cfd0d  mov     ecx, [rsp+78h+var_48]
0x1800cfd11  mov     [r15], ecx
0x1800cfd14  mov     ecx, dword ptr [rsp+78h+cb]
0x1800cfd1b  mov     [r14], ecx
0x1800cfd1e  mov     [rbp+0], rdi
0x1800cfd22  xor     edi, edi
0x1800cfd24  mov     rcx, rdi; pv
0x1800cfd27  call    cs:__imp_CoTaskMemFree
0x1800cfd2d  mov     eax, ebx
0x1800cfd2f  add     rsp, 48h
0x1800cfd33  pop     r15
0x1800cfd35  pop     r14
0x1800cfd37  pop     rdi
0x1800cfd38  pop     rsi
0x1800cfd39  pop     rbp
0x1800cfd3a  pop     rbx
0x1800cfd3b  retn
```

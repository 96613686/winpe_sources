# CPatternMarshaler<WICBitmapPattern,CCodecInfoCallPolicy>::GetPatterns(WICBitmapPattern * *,uint *,uint *)

- ea: `0x1800d250c`
- end: `0x1800d260c`
- name: `?GetPatterns@?$CPatternMarshaler@UWICBitmapPattern@@VCCodecInfoCallPolicy@@@@AEAAJPEAPEAUWICBitmapPattern@@PEAI1@Z`
- size: `256`
- prototype: `__int64 __fastcall(CCodecInfoCallPolicy *this, struct WICBitmapPattern **, unsigned int *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d212c`

## callees

- `0x1800bd9d4`
- `0x1800d250c`
- `0x1800d2614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d2571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d25f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d25f0`

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
0x1800d250c  mov     rax, rsp
0x1800d250f  push    rbx
0x1800d2510  push    rbp
0x1800d2511  push    rsi
0x1800d2512  push    rdi
0x1800d2513  push    r14
0x1800d2515  push    r15
0x1800d2517  sub     rsp, 48h
0x1800d251b  mov     dword ptr [rax+8], 0
0x1800d2522  mov     r14, r9
0x1800d2525  mov     dword ptr [rax-48h], 0
0x1800d252c  lea     rax, [rax+8]
0x1800d2530  mov     r15, r8
0x1800d2533  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800d2538  mov     rbp, rdx
0x1800d253b  xor     r9d, r9d; unsigned int *
0x1800d253e  xor     r8d, r8d; struct WICBitmapPattern *
0x1800d2541  xor     edx, edx; unsigned int
0x1800d2543  mov     rsi, rcx
0x1800d2546  call    ?GetPatterns@CCodecInfoCallPolicy@@QEAAJIPEAUWICBitmapPattern@@PEAI1@Z; CCodecInfoCallPolicy::GetPatterns(uint,WICBitmapPattern *,uint *,uint *)
0x1800d254b  mov     ebx, eax
0x1800d254d  test    eax, eax
0x1800d254f  jns     short loc_1800D256A
0x1800d2551  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d2558  jz      loc_1800D25EB
0x1800d255e  mov     ecx, eax; int
0x1800d2560  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2565  jmp     loc_1800D25EB
0x1800d256a  mov     ecx, dword ptr [rsp+78h+cb]; cb
0x1800d2571  call    cs:__imp_CoTaskMemAlloc
0x1800d2578  nop     dword ptr [rax+rax+00h]
0x1800d257d  mov     rdi, rax
0x1800d2580  test    rax, rax
0x1800d2583  jnz     short loc_1800D259B
0x1800d2585  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d258b  mov     ebx, 8007000Eh
0x1800d2590  jz      short loc_1800D25ED
0x1800d2592  mov     ecx, ebx; int
0x1800d2594  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2599  jmp     short loc_1800D25ED
0x1800d259b  mov     edx, dword ptr [rsp+78h+cb]; unsigned int
0x1800d25a2  lea     rax, [rsp+78h+cb]
0x1800d25aa  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800d25af  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800d25b4  mov     r8, rdi; struct WICBitmapPattern *
0x1800d25b7  mov     rcx, rsi; this
0x1800d25ba  call    ?GetPatterns@CCodecInfoCallPolicy@@QEAAJIPEAUWICBitmapPattern@@PEAI1@Z; CCodecInfoCallPolicy::GetPatterns(uint,WICBitmapPattern *,uint *,uint *)
0x1800d25bf  mov     ebx, eax
0x1800d25c1  test    eax, eax
0x1800d25c3  jns     short loc_1800D25D6
0x1800d25c5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d25cc  jz      short loc_1800D25D2
0x1800d25ce  mov     ecx, eax
0x1800d25d0  jmp     short loc_1800D2594
0x1800d25d2  test    eax, eax
0x1800d25d4  js      short loc_1800D25ED
0x1800d25d6  mov     ecx, [rsp+78h+var_48]
0x1800d25da  mov     [r15], ecx
0x1800d25dd  mov     ecx, dword ptr [rsp+78h+cb]
0x1800d25e4  mov     [r14], ecx
0x1800d25e7  mov     [rbp+0], rdi
0x1800d25eb  xor     edi, edi
0x1800d25ed  mov     rcx, rdi; pv
0x1800d25f0  call    cs:__imp_CoTaskMemFree
0x1800d25f7  nop     dword ptr [rax+rax+00h]
0x1800d25fc  mov     eax, ebx
0x1800d25fe  add     rsp, 48h
0x1800d2602  pop     r15
0x1800d2604  pop     r14
0x1800d2606  pop     rdi
0x1800d2607  pop     rsi
0x1800d2608  pop     rbp
0x1800d2609  pop     rbx
0x1800d260a  retn
```

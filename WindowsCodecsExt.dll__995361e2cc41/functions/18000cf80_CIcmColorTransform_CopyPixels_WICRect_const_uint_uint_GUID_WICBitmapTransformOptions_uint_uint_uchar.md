# CIcmColorTransform::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x18000cf80`
- end: `0x18000d149`
- name: `?CopyPixels@CIcmColorTransform@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `457`
- prototype: `__int64 __fastcall(CIcmColorTransform *__hidden this, const struct WICRect *, unsigned int, unsigned int, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000cf80`
- `0x1800171c4`
- `0x180021a30`
- `0x180022644`
- `0x180022650`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CopyPixels(
        CIcmColorTransform *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        struct _GUID *a5,
        enum WICBitmapTransformOptions a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int8 *a9)
{
  char *v9; // rbx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // esi
  int v20; // ecx
  __int64 v21; // rax
  __int128 v22; // [rsp+50h] [rbp-68h] BYREF

  v9 = (char *)this - 88;
  if ( *((_BYTE *)this - 40) )
    EnterCriticalSection_0((LPCRITICAL_SECTION)(v9 + 8));
  if ( !a9 )
  {
LABEL_21:
    v18 = -2147024809;
    if ( !g_doStackCaptures )
      goto LABEL_17;
    goto LABEL_22;
  }
  if ( *((_DWORD *)this + 32) )
  {
    v14 = *((_QWORD *)this + 17);
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, _QWORD, _QWORD, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *))(*(_QWORD *)v14 + 24LL))(
              v14,
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9);
      goto LABEL_15;
    }
  }
  if ( a6 || a3 != *((_DWORD *)this + 26) || a4 != *((_DWORD *)this + 27) )
  {
    v18 = -2147024809;
    if ( !g_doStackCaptures )
      goto LABEL_17;
LABEL_22:
    v20 = -2147024809;
    goto LABEL_30;
  }
  if ( !a5 )
  {
LABEL_14:
    v15 = (*(__int64 (__fastcall **)(char *, const struct WICRect *, _QWORD, _QWORD, unsigned __int8 *))(*((_QWORD *)this - 4) + 56LL))(
            (char *)this - 32,
            a2,
            a7,
            a8,
            a9);
LABEL_15:
    v18 = v15;
    if ( v15 >= 0 || !g_doStackCaptures )
      goto LABEL_17;
    v20 = v15;
LABEL_30:
    DoStackCapture(v20);
    goto LABEL_17;
  }
  v16 = *((_QWORD *)this - 4);
  v22 = 0;
  v17 = (*(__int64 (__fastcall **)(char *, __int128 *))(v16 + 32))((char *)this - 32, &v22);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v21 = v22 - *(_QWORD *)&a5->Data1;
    if ( (_QWORD)v22 == *(_QWORD *)&a5->Data1 )
      v21 = *((_QWORD *)&v22 + 1) - *(_QWORD *)a5->Data4;
    if ( !v21 )
      goto LABEL_14;
    goto LABEL_21;
  }
  if ( g_doStackCaptures )
    DoStackCapture(v17);
LABEL_17:
  if ( v9 && v9[48] )
    LeaveCriticalSection_0((LPCRITICAL_SECTION)(v9 + 8));
  return v18;
}

```

## disassembly

```asm
0x18000cf80  push    rbx
0x18000cf82  push    rbp
0x18000cf83  push    rsi
0x18000cf84  push    rdi
0x18000cf85  push    r12
0x18000cf87  push    r13
0x18000cf89  push    r14
0x18000cf8b  push    r15
0x18000cf8d  sub     rsp, 78h
0x18000cf91  mov     rax, cs:__security_cookie
0x18000cf98  xor     rax, rsp
0x18000cf9b  mov     [rsp+0B8h+var_58], rax
0x18000cfa0  cmp     byte ptr [rcx-28h], 0
0x18000cfa4  lea     rbx, [rcx-58h]
0x18000cfa8  mov     r15, [rsp+0B8h+arg_20]
0x18000cfb0  mov     r12d, r9d
0x18000cfb3  mov     r14, [rsp+0B8h+arg_40]
0x18000cfbb  mov     esi, r8d
0x18000cfbe  mov     r13, rdx
0x18000cfc1  mov     rbp, rcx
0x18000cfc4  jz      short loc_18000CFCF
0x18000cfc6  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cfca  call    EnterCriticalSection_0
0x18000cfcf  test    r14, r14
0x18000cfd2  jz      loc_18000D101
0x18000cfd8  cmp     dword ptr [rbp+80h], 0
0x18000cfdf  jz      short loc_18000D035
0x18000cfe1  mov     rcx, [rbp+88h]
0x18000cfe8  test    rcx, rcx
0x18000cfeb  jz      short loc_18000D035
0x18000cfed  mov     rax, [rcx]
0x18000cff0  mov     r9d, r12d
0x18000cff3  mov     [rsp+0B8h+var_78], r14
0x18000cff8  mov     r8d, esi
0x18000cffb  mov     rdx, r13
0x18000cffe  mov     r10, [rax+18h]
0x18000d002  mov     eax, [rsp+0B8h+arg_38]
0x18000d009  mov     [rsp+0B8h+var_80], eax
0x18000d00d  mov     eax, [rsp+0B8h+arg_30]
0x18000d014  mov     [rsp+0B8h+var_88], eax
0x18000d018  mov     eax, [rsp+0B8h+arg_28]
0x18000d01f  mov     [rsp+0B8h+var_90], eax
0x18000d023  mov     rax, r10
0x18000d026  mov     [rsp+0B8h+var_98], r15
0x18000d02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d030  jmp     loc_18000D0BE
0x18000d035  cmp     [rsp+0B8h+arg_28], 0
0x18000d03d  jnz     loc_18000D130
0x18000d043  cmp     esi, [rbp+68h]
0x18000d046  jnz     loc_18000D130
0x18000d04c  cmp     r12d, [rbp+6Ch]
0x18000d050  jnz     loc_18000D130
0x18000d056  test    r15, r15
0x18000d059  jz      short loc_18000D095
0x18000d05b  mov     rax, [rbp-20h]
0x18000d05f  lea     rcx, [rbp-20h]
0x18000d063  xorps   xmm0, xmm0
0x18000d066  lea     rdx, [rsp+0B8h+var_68]
0x18000d06b  movups  [rsp+0B8h+var_68], xmm0
0x18000d070  mov     rax, [rax+20h]
0x18000d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d079  mov     esi, eax
0x18000d07b  test    eax, eax
0x18000d07d  jns     loc_18000D113
0x18000d083  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000d08a  jz      short loc_18000D0CD
0x18000d08c  mov     ecx, eax; int
0x18000d08e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d093  jmp     short loc_18000D0CD
0x18000d095  mov     rax, [rbp-20h]
0x18000d099  lea     rcx, [rbp-20h]
0x18000d09d  mov     r9d, [rsp+0B8h+arg_38]
0x18000d0a5  mov     rdx, r13
0x18000d0a8  mov     r8d, [rsp+0B8h+arg_30]
0x18000d0b0  mov     [rsp+0B8h+var_98], r14
0x18000d0b5  mov     rax, [rax+38h]
0x18000d0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0be  mov     esi, eax
0x18000d0c0  test    eax, eax
0x18000d0c2  jns     short loc_18000D0CD
0x18000d0c4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000d0cb  jnz     short loc_18000D140
0x18000d0cd  test    rbx, rbx
0x18000d0d0  jz      short loc_18000D0E1
0x18000d0d2  cmp     byte ptr [rbx+30h], 0
0x18000d0d6  jz      short loc_18000D0E1
0x18000d0d8  lea     rcx, [rbx+8]; lpCriticalSection
0x18000d0dc  call    LeaveCriticalSection_0
0x18000d0e1  mov     eax, esi
0x18000d0e3  mov     rcx, [rsp+0B8h+var_58]
0x18000d0e8  xor     rcx, rsp; StackCookie
0x18000d0eb  call    __security_check_cookie
0x18000d0f0  add     rsp, 78h
0x18000d0f4  pop     r15
0x18000d0f6  pop     r14
0x18000d0f8  pop     r13
0x18000d0fa  pop     r12
0x18000d0fc  pop     rdi
0x18000d0fd  pop     rsi
0x18000d0fe  pop     rbp
0x18000d0ff  pop     rbx
0x18000d100  retn
0x18000d101  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000d108  mov     esi, 80070057h
0x18000d10d  jz      short loc_18000D0CD
0x18000d10f  mov     ecx, esi
0x18000d111  jmp     short loc_18000D142
0x18000d113  mov     rax, qword ptr [rsp+0B8h+var_68]
0x18000d118  sub     rax, [r15]
0x18000d11b  jnz     short loc_18000D126
0x18000d11d  mov     rax, qword ptr [rsp+0B8h+var_68+8]
0x18000d122  sub     rax, [r15+8]
0x18000d126  test    rax, rax
0x18000d129  jnz     short loc_18000D101
0x18000d12b  jmp     loc_18000D095
0x18000d130  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000d137  mov     esi, 80070057h
0x18000d13c  jz      short loc_18000D0CD
0x18000d13e  jmp     short loc_18000D10F
0x18000d140  mov     ecx, eax; int
0x18000d142  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000d147  jmp     short loc_18000D0CD
```

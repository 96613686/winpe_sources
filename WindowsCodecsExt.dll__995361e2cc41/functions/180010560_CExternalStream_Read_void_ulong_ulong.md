# CExternalStream::Read(void *,ulong,ulong *)

- ea: `0x180010560`
- end: `0x18001072d`
- name: `?Read@CExternalStream@@UEAAJPEAXKPEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(CExternalStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010560`
- `0x1800124c8`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CExternalStream::Read(CExternalStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  int v8; // esi
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // eax
  _DWORD v13[18]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+88h] [rbp+10h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+18h]
  unsigned int *v16; // [rsp+98h] [rbp+20h]

  v16 = a4;
  v15 = a3;
  (*(void (__fastcall **)(CExternalStream *))(*(_QWORD *)this + 112LL))(this);
  v14 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !g_doStackCaptures )
      goto LABEL_21;
LABEL_23:
    DoStackCapture(v8);
    goto LABEL_21;
  }
  v8 = 0;
  if ( !*((_QWORD *)this + 12) )
    v8 = -2003292404;
  if ( v8 < 0 )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_21;
  }
  v13[0] = _mm_getcsr();
  v9 = v13[0];
  v10 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, unsigned int *))(**((_QWORD **)this + 12) + 24LL))(
          *((_QWORD *)this + 12),
          a2,
          a3,
          &v14);
  v8 = v10;
  if ( v10 < 0 && g_doStackCaptures )
    DoStackCapture(v10);
  v13[2] = v8;
  if ( v8 < 0 )
  {
    v13[0] = _mm_getcsr();
    if ( (((unsigned __int16)v9 ^ LOWORD(v13[0])) & 0xFF80) != 0 )
    {
      v13[0] = v9 & 0xFFFFFFC0;
      _mm_setcsr(v9 & 0xFFFFFFC0);
    }
  }
  else
  {
    v13[0] = _mm_getcsr();
    if ( (((unsigned __int16)v9 ^ LOWORD(v13[0])) & 0xFF80) != 0 )
    {
      v13[0] = v9 & 0xFFFFFFC0;
      _mm_setcsr(v9 & 0xFFFFFFC0);
    }
    v11 = v14;
    if ( a4 )
      *a4 = v14;
    if ( a3 != v11 && !a4 )
    {
      v13[0] = _mm_getcsr();
      (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
        *((_QWORD *)this + 12),
        -(__int64)v11,
        1,
        0);
      FPUStateSandboxSSE::~FPUStateSandboxSSE((FPUStateSandboxSSE *)v13);
      v8 = -2003292304;
      if ( g_doStackCaptures )
        goto LABEL_23;
    }
  }
LABEL_21:
  (*(void (__fastcall **)(CExternalStream *))(*(_QWORD *)this + 120LL))(this);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010560  mov     [rsp+arg_18], r9
0x180010565  mov     [rsp+arg_10], r8d
0x18001056a  mov     [rsp+arg_0], rcx
0x18001056f  push    rbx
0x180010570  push    rsi
0x180010571  push    rdi
0x180010572  push    r12
0x180010574  push    r14
0x180010576  push    r15
0x180010578  sub     rsp, 48h
0x18001057c  mov     r14, r9
0x18001057f  mov     r15d, r8d
0x180010582  mov     r12, rdx
0x180010585  mov     rdi, rcx
0x180010588  mov     rax, [rcx]
0x18001058b  mov     rax, [rax+70h]
0x18001058f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010594  mov     [rsp+78h+arg_8], 0
0x18001059f  test    r12, r12
0x1800105a2  jz      loc_1800106C1
0x1800105a8  xor     esi, esi
0x1800105aa  mov     eax, 88982F0Ch
0x1800105af  cmp     [rdi+60h], rsi
0x1800105b3  cmovz   esi, eax
0x1800105b6  test    esi, esi
0x1800105b8  jns     short loc_1800105CF
0x1800105ba  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800105c1  jnz     loc_1800106B5
0x1800105c7  test    esi, esi
0x1800105c9  js      loc_180010696
0x1800105cf  stmxcsr [rsp+78h+var_48]
0x1800105d4  mov     ebx, [rsp+78h+var_48]
0x1800105d8  mov     rax, [rdi+60h]
0x1800105dc  mov     rdx, [rax]
0x1800105df  mov     rax, [rdx+18h]
0x1800105e3  lea     r9, [rsp+78h+arg_8]
0x1800105eb  mov     r8d, r15d
0x1800105ee  mov     rdx, r12
0x1800105f1  mov     rcx, [rdi+60h]
0x1800105f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fa  mov     esi, eax
0x1800105fc  test    eax, eax
0x1800105fe  jns     short loc_180010609
0x180010600  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010607  jnz     short loc_180010631
0x180010609  mov     [rsp+78h+var_40], esi
0x18001060d  test    esi, esi
0x18001060f  js      short loc_18001063A
0x180010611  stmxcsr [rsp+78h+var_48]
0x180010616  mov     eax, [rsp+78h+var_48]
0x18001061a  xor     eax, ebx
0x18001061c  test    eax, 0FF80h
0x180010621  jz      short loc_18001065A
0x180010623  and     ebx, 0FFFFFFC0h
0x180010626  mov     [rsp+78h+var_48], ebx
0x18001062a  ldmxcsr [rsp+78h+var_48]
0x18001062f  jmp     short loc_18001065A
0x180010631  mov     ecx, esi; int
0x180010633  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010638  jmp     short loc_180010609
0x18001063a  stmxcsr [rsp+78h+var_48]
0x18001063f  mov     eax, [rsp+78h+var_48]
0x180010643  xor     eax, ebx
0x180010645  test    eax, 0FF80h
0x18001064a  jz      short loc_180010658
0x18001064c  and     ebx, 0FFFFFFC0h
0x18001064f  mov     [rsp+78h+var_48], ebx
0x180010653  ldmxcsr [rsp+78h+var_48]
0x180010658  jmp     short loc_180010696
0x18001065a  jmp     short loc_18001067D
0x18001065c  mov     esi, 80004005h
0x180010661  mov     [rsp+78h+var_40], esi
0x180010665  mov     rdi, [rsp+78h+arg_0]
0x18001066d  mov     r14, [rsp+78h+arg_18]
0x180010675  mov     r15d, [rsp+78h+arg_10]
0x18001067d  mov     eax, [rsp+78h+arg_8]
0x180010684  test    r14, r14
0x180010687  jz      short loc_18001068C
0x180010689  mov     [r14], eax
0x18001068c  cmp     r15d, eax
0x18001068f  jz      short loc_180010696
0x180010691  test    r14, r14
0x180010694  jz      short loc_1800106E8
0x180010696  mov     rcx, [rdi]
0x180010699  mov     rax, [rcx+78h]
0x18001069d  mov     rcx, rdi
0x1800106a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106a5  mov     eax, esi
0x1800106a7  add     rsp, 48h
0x1800106ab  pop     r15
0x1800106ad  pop     r14
0x1800106af  pop     r12
0x1800106b1  pop     rdi
0x1800106b2  pop     rsi
0x1800106b3  pop     rbx
0x1800106b4  retn
0x1800106b5  mov     ecx, esi; int
0x1800106b7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800106bc  jmp     loc_1800105C7
0x1800106c1  mov     esi, 80070057h
0x1800106c6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800106cd  jz      short loc_180010696
0x1800106cf  mov     ecx, esi; int
0x1800106d1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800106d6  jmp     short loc_180010696
0x1800106d8  mov     esi, 88982F70h
0x1800106dd  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800106e4  jz      short loc_180010696
0x1800106e6  jmp     short loc_1800106CF
0x1800106e8  mov     edx, eax
0x1800106ea  neg     rdx
0x1800106ed  stmxcsr [rsp+78h+var_48]
0x1800106f2  mov     eax, [rsp+78h+var_48]
0x1800106f6  mov     [rsp+78h+var_48], eax
0x1800106fa  mov     rax, [rdi+60h]
0x1800106fe  mov     r8, [rax]
0x180010701  mov     rax, [r8+28h]
0x180010705  xor     r9d, r9d
0x180010708  mov     r8d, 1
0x18001070e  mov     rcx, [rdi+60h]
0x180010712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010717  lea     rcx, [rsp+78h+var_48]; this
0x18001071c  call    ??1FPUStateSandboxSSE@@QEAA@XZ; FPUStateSandboxSSE::~FPUStateSandboxSSE(void)
0x180010721  jmp     short loc_1800106D8
0x180010723  mov     rdi, [rsp+78h+arg_0]
0x18001072b  jmp     short loc_1800106D8
```

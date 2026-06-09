# COMMAND_PROCESSOR::MatchObject(ICommandObject *,ICommandParameterList *,int *)

- ea: `0x18000b0c0`
- end: `0x18000b3eb`
- name: `?MatchObject@COMMAND_PROCESSOR@@UEAAJPEAVICommandObject@@PEAVICommandParameterList@@PEAH@Z`
- size: `811`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct ICommandObject *, struct ICommandParameterList *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180009aac`
- `0x18000b0c0`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::MatchObject(
        COMMAND_PROCESSOR *this,
        struct ICommandObject *a2,
        struct ICommandParameterList *a3,
        int *a4)
{
  int v8; // ebx
  unsigned int i; // edi
  int v10; // eax
  int SetConfigPropertyInternal; // eax
  int v12; // eax
  __int64 v14; // [rsp+20h] [rbp-E0h]
  wchar_t *v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  struct INativeConfigurationElement *v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v23; // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  __int16 v25; // [rsp+9Ch] [rbp-64h]
  int v26; // [rsp+A0h] [rbp-60h]
  __int128 v27; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-48h]
  __int16 v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[510]; // [rsp+C2h] [rbp-3Eh] BYREF

  v16 = 0;
  v15 = 0;
  v21 = 0;
  v20 = 0;
  memset_0(v30, 0, sizeof(v30));
  v24 = 512;
  v23 = &v29;
  v25 = 256;
  v26 = 0;
  v29 = 0;
  v18 = 0;
  v28 = 0;
  v19 = 0;
  v17 = 1;
  v27 = 0;
  if ( a2 && a3 && a4 )
  {
    *a4 = 0;
    v8 = (*(__int64 (__fastcall **)(struct ICommandObject *, struct INativeConfigurationElement **))(*(_QWORD *)a2 + 48LL))(
           a2,
           &v18);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024894 )
    {
      v8 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)a3 + 24LL))(a3, &v16);
      if ( v8 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v16 )
          {
            *a4 = 1;
            v8 = 0;
            goto LABEL_29;
          }
          v8 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, wchar_t **, __int64 *))(*(_QWORD *)a3 + 32LL))(
                 a3,
                 i,
                 &v15,
                 &v21);
          if ( v8 < 0 )
            goto LABEL_29;
          v10 = (*(__int64 (__fastcall **)(struct ICommandObject *, wchar_t *, unsigned __int16 **))(*(_QWORD *)a2 + 80LL))(
                  a2,
                  v15,
                  &v20);
          v8 = v10;
          if ( v10 >= 0 )
            break;
          if ( v10 != -2147023483 )
            goto LABEL_29;
          if ( v18 )
          {
            SetConfigPropertyInternal = COMMAND_PROCESSOR::GetSetConfigPropertyInternal(
                                          (COMMAND_PROCESSOR *)((char *)this - 8),
                                          0,
                                          v18,
                                          (unsigned __int16 *)&Str,
                                          v15,
                                          (STRU *)v22,
                                          0);
            v8 = SetConfigPropertyInternal;
            if ( SetConfigPropertyInternal != -2147023483 )
              goto LABEL_18;
            if ( v18
              && (*(int (__fastcall **)(char *, __int64 *))(*((_QWORD *)this - 1) + 56LL))((char *)this - 8, &v19) >= 0 )
            {
              goto LABEL_29;
            }
          }
          if ( ((*(__int64 (__fastcall **)(COMMAND_PROCESSOR *))(*(_QWORD *)this + 32LL))(this) & 2) == 0
            || (v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a3 + 96LL))(
                        a3,
                        v15,
                        0,
                        0),
                v8 = v12,
                v12 == -2147023728) )
          {
            *(_QWORD *)&v27 = v15;
            v8 = -2147023483;
            LODWORD(v14) = 0;
            (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int64, __int128 *, __int64))(*(_QWORD *)this + 144LL))(
              this,
              2147943813LL,
              3221226523LL,
              &v27,
              v14);
            goto LABEL_29;
          }
          if ( v12 < 0 )
            goto LABEL_29;
LABEL_25:
          ;
        }
        SetConfigPropertyInternal = STRU::Copy((STRU *)v22, (const unsigned __int8 *)v20);
        v8 = SetConfigPropertyInternal;
LABEL_18:
        if ( SetConfigPropertyInternal < 0 )
          goto LABEL_29;
        v8 = (*(__int64 (__fastcall **)(COMMAND_PROCESSOR *, wchar_t *, __int64, __int16 *, int *))(*(_QWORD *)this
                                                                                                  + 160LL))(
               this,
               v15,
               v21,
               v23,
               &v17);
        if ( v8 < 0 || !v17 )
          goto LABEL_29;
        goto LABEL_25;
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
LABEL_29:
  if ( v18 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b0c0  push    rbp
0x18000b0c2  push    rbx
0x18000b0c3  push    rsi
0x18000b0c4  push    rdi
0x18000b0c5  push    r12
0x18000b0c7  push    r13
0x18000b0c9  push    r14
0x18000b0cb  push    r15
0x18000b0cd  lea     rbp, [rsp-1D8h]
0x18000b0d5  sub     rsp, 2D8h
0x18000b0dc  mov     rax, cs:__security_cookie
0x18000b0e3  xor     rax, rsp
0x18000b0e6  mov     [rbp+210h+var_50], rax
0x18000b0ed  xor     r15d, r15d
0x18000b0f0  mov     rsi, r8
0x18000b0f3  mov     r13, rdx
0x18000b0f6  mov     [rsp+310h+var_2C8], r15d
0x18000b0fb  mov     r14, rcx
0x18000b0fe  mov     [rsp+310h+var_2D0], r15
0x18000b103  xor     edx, edx; Val
0x18000b105  mov     [rsp+310h+var_2A8], r15
0x18000b10a  mov     r8d, 1FEh; Size
0x18000b110  mov     [rsp+310h+var_2B0], r15
0x18000b115  lea     rcx, [rbp+210h+var_24E]; void *
0x18000b119  mov     r12, r9
0x18000b11c  call    memset_0
0x18000b121  lea     rax, [rbp+210h+var_250]
0x18000b125  mov     [rbp+210h+var_278], 200h
0x18000b12c  mov     [rbp+210h+var_280], rax
0x18000b130  xorps   xmm0, xmm0
0x18000b133  xor     eax, eax
0x18000b135  mov     [rbp+210h+var_274], 100h
0x18000b13b  mov     [rbp+210h+var_270], r15d
0x18000b13f  mov     [rbp+210h+var_250], r15w
0x18000b144  mov     [rsp+310h+var_2C0], r15
0x18000b149  mov     [rbp+210h+var_258], rax
0x18000b14d  mov     [rsp+310h+var_2B8], r15
0x18000b152  mov     [rsp+310h+var_2C4], 1
0x18000b15a  movups  [rbp+210h+var_268], xmm0
0x18000b15e  test    r13, r13
0x18000b161  jz      loc_18000B381
0x18000b167  test    rsi, rsi
0x18000b16a  jz      loc_18000B381
0x18000b170  test    r12, r12
0x18000b173  jz      loc_18000B381
0x18000b179  mov     [r12], r15d
0x18000b17d  lea     rdx, [rsp+310h+var_2C0]
0x18000b182  mov     rax, [r13+0]
0x18000b186  mov     rcx, r13
0x18000b189  mov     rax, [rax+30h]
0x18000b18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b192  mov     ebx, eax
0x18000b194  mov     eax, 80000000h
0x18000b199  lea     ecx, [rbx+rax]
0x18000b19c  test    eax, ecx
0x18000b19e  jnz     short loc_18000B1AC
0x18000b1a0  cmp     ebx, 80070002h
0x18000b1a6  jnz     loc_18000B386
0x18000b1ac  mov     rax, [rsi]
0x18000b1af  lea     rdx, [rsp+310h+var_2C8]
0x18000b1b4  mov     rcx, rsi
0x18000b1b7  mov     rax, [rax+18h]
0x18000b1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c0  mov     ebx, eax
0x18000b1c2  test    eax, eax
0x18000b1c4  js      loc_18000B386
0x18000b1ca  mov     edi, r15d
0x18000b1cd  cmp     edi, [rsp+310h+var_2C8]
0x18000b1d1  jnb     loc_18000B374
0x18000b1d7  mov     rax, [rsi]
0x18000b1da  lea     r9, [rsp+310h+var_2A8]
0x18000b1df  lea     r8, [rsp+310h+var_2D0]
0x18000b1e4  mov     edx, edi
0x18000b1e6  mov     rcx, rsi
0x18000b1e9  mov     rax, [rax+20h]
0x18000b1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f2  mov     ebx, eax
0x18000b1f4  test    eax, eax
0x18000b1f6  js      loc_18000B386
0x18000b1fc  mov     rax, [r13+0]
0x18000b200  lea     r8, [rsp+310h+var_2B0]
0x18000b205  mov     rdx, [rsp+310h+var_2D0]
0x18000b20a  mov     rcx, r13
0x18000b20d  mov     rax, [rax+50h]
0x18000b211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b216  mov     ebx, eax
0x18000b218  test    eax, eax
0x18000b21a  js      short loc_18000B232
0x18000b21c  mov     rdx, [rsp+310h+var_2B0]; unsigned __int16 *
0x18000b221  lea     rcx, [rsp+310h+var_2A0]; this
0x18000b226  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b22b  mov     ebx, eax
0x18000b22d  jmp     loc_18000B2B2
0x18000b232  cmp     eax, 80070585h
0x18000b237  jnz     loc_18000B386
0x18000b23d  mov     r8, [rsp+310h+var_2C0]
0x18000b242  test    r8, r8
0x18000b245  jz      loc_18000B2FE
0x18000b24b  lea     rax, [rsp+310h+var_2A0]
0x18000b250  mov     [rsp+310h+var_2E0], 0
0x18000b259  mov     [rsp+310h+var_2E8], rax
0x18000b25e  lea     r15, [r14-8]
0x18000b262  mov     rax, [rsp+310h+var_2D0]
0x18000b267  lea     r9, Str
0x18000b26e  xor     edx, edx
0x18000b270  mov     [rsp+310h+var_2F0], rax
0x18000b275  mov     rcx, r15
0x18000b278  call    ?GetSetConfigPropertyInternal@COMMAND_PROCESSOR@@AEAAJW4CONFIG_OPERATION_TYPE@@PEAVINativeConfigurationElement@@PEBG2PEAVSTRU@@PEAH@Z; COMMAND_PROCESSOR::GetSetConfigPropertyInternal(CONFIG_OPERATION_TYPE,INativeConfigurationElement *,ushort const *,ushort const *,STRU *,int *)
0x18000b27d  mov     ebx, eax
0x18000b27f  cmp     eax, 80070585h
0x18000b284  jnz     short loc_18000B2AF
0x18000b286  cmp     [rsp+310h+var_2C0], 0
0x18000b28c  jz      short loc_18000B2FB
0x18000b28e  mov     rax, [r15]
0x18000b291  lea     rdx, [rsp+310h+var_2B8]
0x18000b296  mov     rcx, r15
0x18000b299  mov     rax, [rax+38h]
0x18000b29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a2  xor     r15d, r15d
0x18000b2a5  test    eax, eax
0x18000b2a7  jns     loc_18000B386
0x18000b2ad  jmp     short loc_18000B2FE
0x18000b2af  xor     r15d, r15d
0x18000b2b2  test    eax, eax
0x18000b2b4  js      loc_18000B386
0x18000b2ba  mov     rax, [r14]
0x18000b2bd  lea     rcx, [rsp+310h+var_2C4]
0x18000b2c2  mov     r9, [rbp+210h+var_280]
0x18000b2c6  mov     r8, [rsp+310h+var_2A8]
0x18000b2cb  mov     rdx, [rsp+310h+var_2D0]
0x18000b2d0  mov     rax, [rax+0A0h]
0x18000b2d7  mov     [rsp+310h+var_2F0], rcx
0x18000b2dc  mov     rcx, r14
0x18000b2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e4  mov     ebx, eax
0x18000b2e6  test    eax, eax
0x18000b2e8  js      loc_18000B386
0x18000b2ee  cmp     [rsp+310h+var_2C4], r15d
0x18000b2f3  jz      loc_18000B386
0x18000b2f9  jmp     short loc_18000B338
0x18000b2fb  xor     r15d, r15d
0x18000b2fe  mov     rax, [r14]
0x18000b301  mov     rcx, r14
0x18000b304  mov     rax, [rax+20h]
0x18000b308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30d  test    al, 2
0x18000b30f  jz      short loc_18000B33F
0x18000b311  mov     rax, [rsi]
0x18000b314  xor     r9d, r9d
0x18000b317  mov     rdx, [rsp+310h+var_2D0]
0x18000b31c  xor     r8d, r8d
0x18000b31f  mov     rcx, rsi
0x18000b322  mov     rax, [rax+60h]
0x18000b326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32b  mov     ebx, eax
0x18000b32d  cmp     eax, 80070490h
0x18000b332  jz      short loc_18000B33F
0x18000b334  test    eax, eax
0x18000b336  js      short loc_18000B386
0x18000b338  inc     edi
0x18000b33a  jmp     loc_18000B1CD
0x18000b33f  mov     rax, [rsp+310h+var_2D0]
0x18000b344  lea     r9, [rbp+210h+var_268]
0x18000b348  mov     qword ptr [rbp+210h+var_268], rax
0x18000b34c  mov     ecx, 80070585h
0x18000b351  mov     rax, [r14]
0x18000b354  mov     ebx, ecx
0x18000b356  mov     edx, ecx
0x18000b358  mov     dword ptr [rsp+310h+var_2F0], r15d
0x18000b35d  mov     r8d, 0C000041Bh
0x18000b363  mov     rcx, r14
0x18000b366  mov     rax, [rax+90h]
0x18000b36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b372  jmp     short loc_18000B386
0x18000b374  mov     dword ptr [r12], 1
0x18000b37c  mov     ebx, r15d
0x18000b37f  jmp     short loc_18000B386
0x18000b381  mov     ebx, 80070057h
0x18000b386  mov     rcx, [rsp+310h+var_2C0]
0x18000b38b  test    rcx, rcx
0x18000b38e  jz      short loc_18000B3A1
0x18000b390  mov     rax, [rcx]
0x18000b393  mov     rax, [rax+10h]
0x18000b397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b39c  mov     [rsp+310h+var_2C0], r15
0x18000b3a1  mov     rcx, [rsp+310h+var_2B8]
0x18000b3a6  test    rcx, rcx
0x18000b3a9  jz      short loc_18000B3BC
0x18000b3ab  mov     rax, [rcx]
0x18000b3ae  mov     rax, [rax+10h]
0x18000b3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b7  mov     [rsp+310h+var_2B8], r15
0x18000b3bc  lea     rcx, [rsp+310h+var_2A0]; this
0x18000b3c1  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b3c6  mov     eax, ebx
0x18000b3c8  mov     rcx, [rbp+210h+var_50]
0x18000b3cf  xor     rcx, rsp; StackCookie
0x18000b3d2  call    __security_check_cookie
0x18000b3d7  add     rsp, 2D8h
0x18000b3de  pop     r15
0x18000b3e0  pop     r14
0x18000b3e2  pop     r13
0x18000b3e4  pop     r12
0x18000b3e6  pop     rdi
0x18000b3e7  pop     rsi
0x18000b3e8  pop     rbx
0x18000b3e9  pop     rbp
0x18000b3ea  retn
```

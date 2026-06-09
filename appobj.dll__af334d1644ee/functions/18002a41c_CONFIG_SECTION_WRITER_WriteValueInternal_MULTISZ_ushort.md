# CONFIG_SECTION_WRITER::WriteValueInternal(MULTISZ *,ushort *)

- ea: `0x18002a41c`
- end: `0x18002a6c6`
- name: `?WriteValueInternal@CONFIG_SECTION_WRITER@@AEAAJPEAVMULTISZ@@PEAG@Z`
- size: `682`
- prototype: `int(CONFIG_SECTION_WRITER *__hidden this, struct MULTISZ *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a250`

## callees

- `0x180001fb0`
- `0x180004560`
- `0x18001b140`
- `0x180029bf8`
- `0x18002a0b8`
- `0x18002a41c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall CONFIG_SECTION_WRITER::WriteValueInternal(
        CONFIG_SECTION_WRITER *this,
        struct MULTISZ *a2,
        unsigned __int16 *a3)
{
  struct INativeConfigurationElement *v5; // rbx
  unsigned __int16 *v6; // r12
  unsigned int v7; // edx
  struct INativeConfigurationElement *v8; // r14
  int v9; // edi
  unsigned __int16 *v10; // rsi
  CONFIG_SECTION_WRITER *i; // rcx
  struct INativeConfigurationElement *v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  CONFIG_SECTION_WRITER *v21; // [rsp+58h] [rbp-A8h]
  _BYTE v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+88h] [rbp-78h]
  __int16 v25; // [rsp+8Ch] [rbp-74h]
  int v26; // [rsp+90h] [rbp-70h]
  __int16 v27; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[510]; // [rsp+A2h] [rbp-5Eh] BYREF

  v21 = this;
  v5 = 0;
  v19 = 0;
  memset_0(v28, 0, sizeof(v28));
  v25 = 256;
  v26 = 0;
  v6 = (unsigned __int16 *)&v27;
  v23 = (unsigned __int16 *)&v27;
  v7 = 512;
  v24 = 512;
  v27 = 0;
  v18 = 0;
  if ( a2 && *((_DWORD *)a2 + 13) )
  {
    v8 = 0;
    v9 = 0;
    v10 = (unsigned __int16 *)(*((_QWORD *)a2 + 4) & -(__int64)(**((_WORD **)a2 + 4) != 0));
    for ( i = 0; ; i = (CONFIG_SECTION_WRITER *)(unsigned int)(v20 + 1) )
    {
      v20 = (int)i;
      if ( !v10 )
        break;
      if ( v8 )
        v12 = v8;
      else
        v12 = (struct INativeConfigurationElement *)*((_QWORD *)v21 + 1);
      if ( *v10 == 123 )
      {
        v13 = CONFIG_SECTION_WRITER::CreateCollectionElement(i, v12, v10, &v19);
      }
      else if ( (_DWORD)i == *((_DWORD *)a2 + 13) - 1 )
      {
        if ( !a3 )
        {
          v18 = v7;
          v15 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 88LL))(
                  v12,
                  v10,
                  v6,
                  &v18,
                  0,
                  0);
          v9 = v15;
          if ( v15 < 0 )
          {
            if ( v15 != -2147024774
              || (v9 = STRA::Resize((STRA *)v22, v18), v9 < 0)
              || (v6 = v23,
                  v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 88LL))(
                         v12,
                         v10,
                         v23,
                         &v18,
                         0,
                         0),
                  v9 < 0) )
            {
LABEL_29:
              v5 = v19;
              break;
            }
          }
          a3 = v6;
        }
        if ( (unsigned int)CONFIG_OBJECT_EXTENSION::IsBuiltInAttribute(v10) )
          v13 = CONFIG_SECTION_WRITER::WriteBuiltInAttribute(v12, v10, a3);
        else
          v13 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, unsigned __int16 *, _QWORD))(*(_QWORD *)v12 + 160LL))(
                  v12,
                  v10,
                  a3,
                  0);
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v12 + 32LL))(
                v12,
                v10,
                &v19);
      }
      v9 = v13;
      if ( v13 < 0 )
        goto LABEL_29;
      v5 = v19;
      if ( v19 )
      {
        if ( v8 )
        {
          (*(void (__fastcall **)(struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v8 + 16LL))(
            v8,
            v14,
            0);
          v5 = v19;
        }
        v8 = v5;
        v5 = 0;
        v19 = 0;
      }
      v16 = -1;
      do
        ++v16;
      while ( v10[v16] );
      v7 = v24;
      v10 = (unsigned __int16 *)((unsigned __int64)&v10[v16 + 1] & -(__int64)(v10[v16 + 1] != 0));
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v8 + 16LL))(v8);
      v5 = v19;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v5 + 16LL))(v5);
    v19 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002a41c  mov     [rsp-8+arg_18], rbx
0x18002a421  push    rbp
0x18002a422  push    rsi
0x18002a423  push    rdi
0x18002a424  push    r12
0x18002a426  push    r13
0x18002a428  push    r14
0x18002a42a  push    r15
0x18002a42c  lea     rbp, [rsp-1B0h]
0x18002a434  sub     rsp, 2B0h
0x18002a43b  mov     rax, cs:__security_cookie
0x18002a442  xor     rax, rsp
0x18002a445  mov     [rbp+1E0h+var_40], rax
0x18002a44c  mov     [rsp+2E0h+var_288], rcx
0x18002a451  mov     r15, r8
0x18002a454  xor     ecx, ecx
0x18002a456  mov     r13, rdx
0x18002a459  mov     ebx, ecx
0x18002a45b  mov     [rsp+2E0h+var_298], rcx
0x18002a460  lea     rcx, [rbp+1E0h+var_23E]; void *
0x18002a464  xor     edx, edx; Val
0x18002a466  mov     r8d, 1FEh; Size
0x18002a46c  call    memset_0
0x18002a471  xor     r8d, r8d
0x18002a474  mov     [rbp+1E0h+var_254], 100h
0x18002a47a  mov     [rbp+1E0h+var_250], r8d
0x18002a47e  lea     r12, [rbp+1E0h+var_240]
0x18002a482  mov     [rbp+1E0h+var_260], r12
0x18002a486  mov     edx, 200h
0x18002a48b  mov     [rbp+1E0h+var_258], edx
0x18002a48e  mov     [rbp+1E0h+var_240], r8w
0x18002a493  mov     [rsp+2E0h+var_2A0], r8d
0x18002a498  test    r13, r13
0x18002a49b  jz      loc_18002A670
0x18002a4a1  cmp     [r13+34h], r8d
0x18002a4a5  jz      loc_18002A670
0x18002a4ab  mov     rcx, [r13+20h]
0x18002a4af  mov     r14d, r8d
0x18002a4b2  mov     edi, r8d
0x18002a4b5  movzx   eax, word ptr [rcx]
0x18002a4b8  neg     ax
0x18002a4bb  sbb     rsi, rsi
0x18002a4be  and     rsi, rcx
0x18002a4c1  mov     ecx, r8d; this
0x18002a4c4  mov     [rsp+2E0h+var_290], ecx
0x18002a4c8  test    rsi, rsi
0x18002a4cb  jz      loc_18002A655
0x18002a4d1  test    r14, r14
0x18002a4d4  jnz     short loc_18002A4E1
0x18002a4d6  mov     rax, [rsp+2E0h+var_288]
0x18002a4db  mov     rbx, [rax+8]
0x18002a4df  jmp     short loc_18002A4E4
0x18002a4e1  mov     rbx, r14
0x18002a4e4  cmp     word ptr [rsi], 7Bh ; '{'
0x18002a4e8  jnz     short loc_18002A4FF
0x18002a4ea  lea     r9, [rsp+2E0h+var_298]; struct INativeConfigurationElement **
0x18002a4ef  mov     r8, rsi; unsigned __int16 *
0x18002a4f2  mov     rdx, rbx; struct INativeConfigurationElement *
0x18002a4f5  call    ?CreateCollectionElement@CONFIG_SECTION_WRITER@@AEAAJPEAVINativeConfigurationElement@@PEAGPEAPEAV2@@Z; CONFIG_SECTION_WRITER::CreateCollectionElement(INativeConfigurationElement *,ushort *,INativeConfigurationElement * *)
0x18002a4fa  jmp     loc_18002A5E6
0x18002a4ff  mov     eax, [r13+34h]
0x18002a503  dec     eax
0x18002a505  cmp     ecx, eax
0x18002a507  jnz     loc_18002A5CF
0x18002a50d  test    r15, r15
0x18002a510  jnz     loc_18002A59F
0x18002a516  mov     [rsp+2E0h+var_2A0], edx
0x18002a51a  lea     r9, [rsp+2E0h+var_2A0]
0x18002a51f  mov     rax, [rbx]
0x18002a522  mov     rdx, rsi
0x18002a525  mov     [rsp+2E0h+var_2B8], r8
0x18002a52a  mov     rcx, rbx
0x18002a52d  mov     [rsp+2E0h+var_2C0], r8
0x18002a532  mov     r8, r12
0x18002a535  mov     rax, [rax+58h]
0x18002a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a53e  mov     edi, eax
0x18002a540  test    eax, eax
0x18002a542  jns     short loc_18002A59C
0x18002a544  cmp     eax, 8007007Ah
0x18002a549  jnz     loc_18002A650
0x18002a54f  mov     edx, [rsp+2E0h+var_2A0]; unsigned int
0x18002a553  lea     rcx, [rsp+2E0h+var_280]; this
0x18002a558  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18002a55d  xor     r8d, r8d
0x18002a560  mov     edi, eax
0x18002a562  test    eax, eax
0x18002a564  js      loc_18002A650
0x18002a56a  mov     rax, [rbx]
0x18002a56d  lea     r9, [rsp+2E0h+var_2A0]
0x18002a572  mov     r12, [rbp+1E0h+var_260]
0x18002a576  mov     rdx, rsi
0x18002a579  mov     [rsp+2E0h+var_2B8], r8
0x18002a57e  mov     rcx, rbx
0x18002a581  mov     [rsp+2E0h+var_2C0], r8
0x18002a586  mov     r8, r12
0x18002a589  mov     rax, [rax+58h]
0x18002a58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a592  mov     edi, eax
0x18002a594  test    eax, eax
0x18002a596  js      loc_18002A650
0x18002a59c  mov     r15, r12
0x18002a59f  mov     rcx, rsi; unsigned __int16 *
0x18002a5a2  call    ?IsBuiltInAttribute@CONFIG_OBJECT_EXTENSION@@SAHPEAG@Z; CONFIG_OBJECT_EXTENSION::IsBuiltInAttribute(ushort *)
0x18002a5a7  mov     r8, r15; unsigned __int16 *
0x18002a5aa  mov     rdx, rsi; unsigned __int16 *
0x18002a5ad  mov     rcx, rbx; struct INativeConfigurationElement *
0x18002a5b0  test    eax, eax
0x18002a5b2  jz      short loc_18002A5BB
0x18002a5b4  call    ?WriteBuiltInAttribute@CONFIG_SECTION_WRITER@@SAJPEAVINativeConfigurationElement@@PEAG1@Z; CONFIG_SECTION_WRITER::WriteBuiltInAttribute(INativeConfigurationElement *,ushort *,ushort *)
0x18002a5b9  jmp     short loc_18002A5E6
0x18002a5bb  mov     rax, [rbx]
0x18002a5be  xor     r9d, r9d
0x18002a5c1  mov     rax, [rax+0A0h]
0x18002a5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5cd  jmp     short loc_18002A5E6
0x18002a5cf  mov     rax, [rbx]
0x18002a5d2  lea     r8, [rsp+2E0h+var_298]
0x18002a5d7  mov     rdx, rsi
0x18002a5da  mov     rcx, rbx
0x18002a5dd  mov     rax, [rax+20h]
0x18002a5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5e6  xor     r8d, r8d
0x18002a5e9  mov     edi, eax
0x18002a5eb  test    eax, eax
0x18002a5ed  js      short loc_18002A650
0x18002a5ef  mov     rbx, [rsp+2E0h+var_298]
0x18002a5f4  test    rbx, rbx
0x18002a5f7  jz      short loc_18002A620
0x18002a5f9  test    r14, r14
0x18002a5fc  jz      short loc_18002A615
0x18002a5fe  mov     rax, [r14]
0x18002a601  mov     rcx, r14
0x18002a604  mov     rax, [rax+10h]
0x18002a608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a60d  mov     rbx, [rsp+2E0h+var_298]
0x18002a612  xor     r8d, r8d
0x18002a615  mov     r14, rbx
0x18002a618  mov     rbx, r8
0x18002a61b  mov     [rsp+2E0h+var_298], rbx
0x18002a620  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a624  inc     rax
0x18002a627  cmp     [rsi+rax*2], r8w
0x18002a62c  jnz     short loc_18002A624
0x18002a62e  mov     edx, [rbp+1E0h+var_258]
0x18002a631  lea     rcx, [rsi+2]
0x18002a635  lea     rcx, [rcx+rax*2]
0x18002a639  movzx   eax, word ptr [rcx]
0x18002a63c  neg     ax
0x18002a63f  sbb     rsi, rsi
0x18002a642  and     rsi, rcx
0x18002a645  mov     ecx, [rsp+2E0h+var_290]
0x18002a649  inc     ecx
0x18002a64b  jmp     loc_18002A4C4
0x18002a650  mov     rbx, [rsp+2E0h+var_298]
0x18002a655  test    r14, r14
0x18002a658  jz      short loc_18002A675
0x18002a65a  mov     rax, [r14]
0x18002a65d  mov     rcx, r14
0x18002a660  mov     rax, [rax+10h]
0x18002a664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a669  mov     rbx, [rsp+2E0h+var_298]
0x18002a66e  jmp     short loc_18002A675
0x18002a670  mov     edi, 80070057h
0x18002a675  test    rbx, rbx
0x18002a678  jz      short loc_18002A690
0x18002a67a  mov     rax, [rbx]
0x18002a67d  mov     rcx, rbx
0x18002a680  mov     rax, [rax+10h]
0x18002a684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a689  xor     ecx, ecx
0x18002a68b  mov     [rsp+2E0h+var_298], rcx
0x18002a690  lea     rcx, [rsp+2E0h+var_280]; this
0x18002a695  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a69a  mov     eax, edi
0x18002a69c  mov     rcx, [rbp+1E0h+var_40]
0x18002a6a3  xor     rcx, rsp; StackCookie
0x18002a6a6  call    __security_check_cookie
0x18002a6ab  mov     rbx, [rsp+2E0h+arg_18]
0x18002a6b3  add     rsp, 2B0h
0x18002a6ba  pop     r15
0x18002a6bc  pop     r14
0x18002a6be  pop     r13
0x18002a6c0  pop     r12
0x18002a6c2  pop     rdi
0x18002a6c3  pop     rsi
0x18002a6c4  pop     rbp
0x18002a6c5  retn
```

# WriteSafeArrayToStream(tagSAFEARRAY *,ushort,ISequentialStream *)

- ea: `0x180003028`
- end: `0x180003240`
- name: `?WriteSafeArrayToStream@@YAJPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16, struct ISequentialStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003390`

## callees

- `0x180003028`
- `0x180003574`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000308f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000308f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180003073`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180003073`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180003220`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180003220`

## pseudocode

```c
__int64 __fastcall WriteSafeArrayToStream(SAFEARRAY *psa, __int16 a2, struct ISequentialStream *a3)
{
  HRESULT UBound; // ebx
  struct ISequentialStreamVtbl *lpVtbl; // rax
  __int64 v8; // rcx
  struct ISequentialStreamVtbl *v9; // rax
  int v10; // esi
  __int64 v11; // r15
  __int64 v12; // rdx
  _WORD *v13; // rax
  __int64 v14; // rcx
  struct ISequentialStreamVtbl *v15; // rax
  __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  int v19; // [rsp+80h] [rbp+40h] BYREF
  LONG plUbound; // [rsp+98h] [rbp+58h] BYREF

  ppvData = 0;
  plUbound = 0;
  v17 = 0;
  v19 = 0;
  if ( psa && a3 )
  {
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound >= 0 )
      {
        lpVtbl = a3->lpVtbl;
        ++plUbound;
        UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, LONG *, __int64, int *))lpVtbl->Write)(
                   a3,
                   &plUbound,
                   4,
                   &v19);
        if ( UBound >= 0 )
        {
          if ( v19 == 4 )
          {
            if ( a2 == 8 )
            {
              v10 = 0;
              if ( plUbound > 0 )
              {
                while ( 1 )
                {
                  v19 = 0;
                  v11 = *((_QWORD *)ppvData + v10);
                  if ( !v11 )
                    break;
                  v12 = 0x7FFFFFFF;
                  v13 = (_WORD *)*((_QWORD *)ppvData + v10);
                  do
                  {
                    if ( !*v13 )
                      break;
                    ++v13;
                    --v12;
                  }
                  while ( v12 );
                  v17 = 0;
                  UBound = v12 == 0 ? 0x80070057 : 0;
                  if ( v12 )
                  {
                    v14 = -1;
                    if ( is_mul_ok(0x7FFFFFFF - v12, 2u) )
                      v14 = 2 * (0x7FFFFFFF - v12);
                    v15 = a3->lpVtbl;
                    v17 = v14;
                    UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, __int64 *, __int64, int *))v15->Write)(
                               a3,
                               &v17,
                               8,
                               &v19);
                    if ( UBound >= 0 )
                    {
                      if ( v19 != 8 )
                        goto LABEL_14;
                      UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, __int64, _QWORD, int *))a3->lpVtbl->Write)(
                                 a3,
                                 v11,
                                 (unsigned int)v17,
                                 &v19);
                      if ( UBound >= 0 )
                      {
                        if ( v19 != v17 )
                          goto LABEL_14;
                        if ( ++v10 < plUbound )
                          continue;
                      }
                    }
                  }
                  goto LABEL_30;
                }
                UBound = -2147024809;
              }
            }
            else if ( a2 == 17 )
            {
              v9 = a3->lpVtbl;
              v17 = plUbound;
              UBound = ((__int64 (__fastcall *)(struct ISequentialStream *, void *, _QWORD, int *))v9->Write)(
                         a3,
                         ppvData,
                         plUbound,
                         &v19);
              if ( UBound >= 0 && v19 != v17 )
LABEL_14:
                UBound = -2147418113;
            }
            else
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v8);
            }
          }
          else
          {
            UBound = -2147467259;
          }
        }
      }
    }
LABEL_30:
    if ( ppvData )
      SafeArrayUnaccessData(psa);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180003028  mov     [rsp-38h+arg_8], rbx
0x18000302d  push    rbp
0x18000302e  push    rsi
0x18000302f  push    rdi
0x180003030  push    r12
0x180003032  push    r13
0x180003034  push    r14
0x180003036  push    r15
0x180003038  mov     rbp, rsp
0x18000303b  sub     rsp, 40h
0x18000303f  xor     r12d, r12d
0x180003042  mov     rdi, r8
0x180003045  mov     [rbp+ppvData], r12
0x180003049  movzx   esi, dx
0x18000304c  mov     [rbp+plUbound], r12d
0x180003050  mov     r14, rcx
0x180003053  mov     [rbp+var_10], r12
0x180003057  mov     [rbp+arg_0], r12d
0x18000305b  test    rcx, rcx
0x18000305e  jnz     short loc_18000306A
0x180003060  mov     ebx, 80004003h
0x180003065  jmp     loc_180003226
0x18000306a  test    rdi, rdi
0x18000306d  jz      short loc_180003060
0x18000306f  lea     rdx, [rbp+ppvData]; ppvData
0x180003073  call    cs:__imp_SafeArrayAccessData
0x180003079  mov     ebx, eax
0x18000307b  test    eax, eax
0x18000307d  js      loc_180003217
0x180003083  lea     r8, [rbp+plUbound]; plUbound
0x180003087  mov     edx, 1; nDim
0x18000308c  mov     rcx, r14; psa
0x18000308f  call    cs:__imp_SafeArrayGetUBound
0x180003095  mov     ebx, eax
0x180003097  test    eax, eax
0x180003099  js      loc_180003217
0x18000309f  mov     rax, [rdi]
0x1800030a2  lea     r9, [rbp+arg_0]
0x1800030a6  inc     [rbp+plUbound]
0x1800030a9  lea     rdx, [rbp+plUbound]
0x1800030ad  mov     r8d, 4
0x1800030b3  mov     rcx, rdi
0x1800030b6  mov     rax, [rax+20h]
0x1800030ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bf  mov     ebx, eax
0x1800030c1  test    eax, eax
0x1800030c3  js      loc_180003217
0x1800030c9  cmp     [rbp+arg_0], 4
0x1800030cd  jz      short loc_1800030D9
0x1800030cf  mov     ebx, 80004005h
0x1800030d4  jmp     loc_180003217
0x1800030d9  mov     r13d, 8
0x1800030df  cmp     si, r13w
0x1800030e3  jz      short loc_180003135
0x1800030e5  cmp     si, 11h
0x1800030e9  jz      short loc_1800030F5
0x1800030eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800030f0  jmp     loc_180003217
0x1800030f5  mov     rax, [rdi]
0x1800030f8  lea     r9, [rbp+arg_0]
0x1800030fc  movsxd  r8, [rbp+plUbound]
0x180003100  mov     rcx, rdi
0x180003103  mov     rdx, [rbp+ppvData]
0x180003107  mov     [rbp+var_10], r8
0x18000310b  mov     rax, [rax+20h]
0x18000310f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003114  mov     ebx, eax
0x180003116  test    eax, eax
0x180003118  js      loc_180003217
0x18000311e  mov     eax, [rbp+arg_0]
0x180003121  cmp     rax, [rbp+var_10]
0x180003125  jz      loc_180003217
0x18000312b  mov     ebx, 8000FFFFh
0x180003130  jmp     loc_180003217
0x180003135  mov     esi, r12d
0x180003138  cmp     [rbp+plUbound], r12d
0x18000313c  jle     loc_180003217
0x180003142  mov     rax, [rbp+ppvData]
0x180003146  movsxd  rcx, esi
0x180003149  mov     [rbp+arg_0], r12d
0x18000314d  mov     r15, [rax+rcx*8]
0x180003151  test    r15, r15
0x180003154  jz      loc_180003212
0x18000315a  mov     edx, 7FFFFFFFh
0x18000315f  mov     rax, r15
0x180003162  cmp     [rax], r12w
0x180003166  jz      short loc_180003172
0x180003168  add     rax, 2
0x18000316c  sub     rdx, 1
0x180003170  jnz     short loc_180003162
0x180003172  mov     rax, rdx
0x180003175  mov     [rbp+var_10], r12
0x180003179  neg     rax
0x18000317c  sbb     ebx, ebx
0x18000317e  not     ebx
0x180003180  and     ebx, 80070057h
0x180003186  test    rdx, rdx
0x180003189  jz      loc_180003217
0x18000318f  mov     ecx, 7FFFFFFFh
0x180003194  lea     r9, [rbp+arg_0]
0x180003198  sub     rcx, rdx
0x18000319b  mov     eax, 2
0x1800031a0  mul     rcx
0x1800031a3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800031a7  mov     r8d, r13d
0x1800031aa  test    rdx, rdx
0x1800031ad  lea     rdx, [rbp+var_10]
0x1800031b1  cmovz   rcx, rax
0x1800031b5  mov     rax, [rdi]
0x1800031b8  mov     [rbp+var_10], rcx
0x1800031bc  mov     rcx, rdi
0x1800031bf  mov     rax, [rax+20h]
0x1800031c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c8  mov     ebx, eax
0x1800031ca  test    eax, eax
0x1800031cc  js      short loc_180003217
0x1800031ce  cmp     [rbp+arg_0], r13d
0x1800031d2  jnz     loc_18000312B
0x1800031d8  mov     rax, [rdi]
0x1800031db  lea     r9, [rbp+arg_0]
0x1800031df  mov     r8d, dword ptr [rbp+var_10]
0x1800031e3  mov     rdx, r15
0x1800031e6  mov     rcx, rdi
0x1800031e9  mov     rax, [rax+20h]
0x1800031ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f2  mov     ebx, eax
0x1800031f4  test    eax, eax
0x1800031f6  js      short loc_180003217
0x1800031f8  mov     eax, [rbp+arg_0]
0x1800031fb  cmp     rax, [rbp+var_10]
0x1800031ff  jnz     loc_18000312B
0x180003205  inc     esi
0x180003207  cmp     esi, [rbp+plUbound]
0x18000320a  jl      loc_180003142
0x180003210  jmp     short loc_180003217
0x180003212  mov     ebx, 80070057h
0x180003217  cmp     [rbp+ppvData], r12
0x18000321b  jz      short loc_180003226
0x18000321d  mov     rcx, r14; psa
0x180003220  call    cs:__imp_SafeArrayUnaccessData
0x180003226  mov     eax, ebx
0x180003228  mov     rbx, [rsp+40h+arg_8]
0x180003230  add     rsp, 40h
0x180003234  pop     r15
0x180003236  pop     r14
0x180003238  pop     r13
0x18000323a  pop     r12
0x18000323c  pop     rdi
0x18000323d  pop     rsi
0x18000323e  pop     rbp
0x18000323f  retn
```

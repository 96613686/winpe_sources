# CreateCodecAggregateValues<CreateEncoderInternalProperties>::LogTelemetry(void)

- ea: `0x180089410`
- end: `0x180089587`
- name: `?LogTelemetry@?$CreateCodecAggregateValues@UCreateEncoderInternalProperties@@@@UEAAXXZ`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180089410`
- `0x180089710`
- `0x1800bb784`
- `0x1800e2b88`
- `0x1800e2b94`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008951f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008951f`
- `ntdll!RtlDllShutdownInProgress` at `0x180089424`
- `ntdll!RtlDllShutdownInProgress` at `0x180089424`

## pseudocode

```c
void __fastcall CreateCodecAggregateValues<CreateEncoderInternalProperties>::LogTelemetry(__int64 a1)
{
  void *v2; // rsi
  void *v3; // r14
  void *v4; // rbp
  unsigned __int64 v5; // r15
  void *v6; // rax
  bool v7; // zf
  int v8; // ecx
  void *v9; // rax
  void *v10; // rax
  int ArraysFromCLSIDMap; // eax
  __int64 v12; // rbx
  ULONGLONG TickCount64; // rax

  if ( !RtlDllShutdownInProgress() )
  {
    v2 = 0;
    v3 = 0;
    v4 = 0;
    if ( *(_DWORD *)(a1 + 16) + *(_DWORD *)(a1 + 20) )
    {
      v5 = *(int *)(a1 + 40);
      v6 = operator new[](saturated_mul(v5, 0x10u));
      v2 = v6;
      if ( v6 && (memset_0(v6, 0, 16 * v5), v9 = operator new[](saturated_mul(v5, 4u)), (v3 = v9) != 0) )
      {
        memset_0(v9, 0, 4 * v5);
        v10 = operator new[](saturated_mul(v5, 4u));
        v4 = v10;
        if ( v10 )
        {
          memset_0(v10, 0, 4 * v5);
          ArraysFromCLSIDMap = CreateComponentAggregateValues<CreateEncoderInternalProperties>::GetArraysFromCLSIDMap(
                                 a1 + 32,
                                 a1 + 80,
                                 v2,
                                 v3,
                                 v4,
                                 v5);
          if ( ArraysFromCLSIDMap >= 0 )
          {
            v12 = *(_QWORD *)(a1 + 8);
            TickCount64 = GetTickCount64();
            ArraysFromCLSIDMap = (*(__int64 (__fastcall **)(__int64, ULONGLONG, void *, void *, void *, _DWORD))(*(_QWORD *)a1 + 56LL))(
                                   a1,
                                   TickCount64 - v12,
                                   v2,
                                   v3,
                                   v4,
                                   v5);
            if ( ArraysFromCLSIDMap >= 0 )
              goto LABEL_15;
          }
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_15;
          v8 = ArraysFromCLSIDMap;
          goto LABEL_14;
        }
        v7 = (_DWORD)g_doStackCaptures == 0;
      }
      else
      {
        v7 = (_DWORD)g_doStackCaptures == 0;
      }
      if ( !v7 )
      {
        v8 = -2147024882;
LABEL_14:
        DoStackCapture(v8);
      }
    }
LABEL_15:
    operator delete(v2);
    operator delete(v3);
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x180089410  push    rbx
0x180089412  push    rbp
0x180089413  push    rsi
0x180089414  push    rdi
0x180089415  push    r12
0x180089417  push    r13
0x180089419  push    r14
0x18008941b  push    r15
0x18008941d  sub     rsp, 48h
0x180089421  mov     rdi, rcx
0x180089424  call    cs:__imp_RtlDllShutdownInProgress
0x18008942a  test    al, al
0x18008942c  jnz     loc_180089576
0x180089432  mov     eax, [rdi+14h]
0x180089435  xor     esi, esi
0x180089437  xor     r14d, r14d
0x18008943a  xor     ebp, ebp
0x18008943c  add     eax, [rdi+10h]
0x18008943f  jz      loc_18008955E
0x180089445  movsxd  r15, dword ptr [rdi+28h]
0x180089449  lea     eax, [rsi+10h]
0x18008944c  mul     r15
0x18008944f  lea     r12, [rsi-1]
0x180089453  mov     rbx, r15
0x180089456  cmovb   rax, r12
0x18008945a  mov     rcx, rax; unsigned __int64
0x18008945d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089462  mov     rsi, rax
0x180089465  test    rax, rax
0x180089468  jnz     short loc_180089480
0x18008946a  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180089470  jz      loc_18008955E
0x180089476  mov     ecx, 8007000Eh
0x18008947b  jmp     loc_180089559
0x180089480  mov     r8, rbx
0x180089483  xor     edx, edx; Val
0x180089485  shl     r8, 4; Size
0x180089489  mov     rcx, rsi; void *
0x18008948c  call    memset_0
0x180089491  mov     eax, 4
0x180089496  mul     rbx
0x180089499  cmovb   rax, r12
0x18008949d  mov     rcx, rax; unsigned __int64
0x1800894a0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800894a5  mov     r14, rax
0x1800894a8  test    rax, rax
0x1800894ab  jz      short loc_18008946A
0x1800894ad  lea     r12, ds:0[r15*4]
0x1800894b5  xor     edx, edx; Val
0x1800894b7  mov     r8, r12; Size
0x1800894ba  mov     rcx, rax; void *
0x1800894bd  call    memset_0
0x1800894c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800894c9  mov     eax, 4
0x1800894ce  mul     rbx
0x1800894d1  cmovb   rax, rcx
0x1800894d5  mov     rcx, rax; unsigned __int64
0x1800894d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800894dd  mov     rbp, rax
0x1800894e0  test    rax, rax
0x1800894e3  jnz     short loc_1800894ED
0x1800894e5  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800894eb  jmp     short loc_180089470
0x1800894ed  mov     r8, r12; Size
0x1800894f0  xor     edx, edx; Val
0x1800894f2  mov     rcx, rbp; void *
0x1800894f5  call    memset_0
0x1800894fa  lea     rdx, [rdi+50h]
0x1800894fe  mov     [rsp+88h+var_60], r15d
0x180089503  mov     r9, r14
0x180089506  mov     [rsp+88h+var_68], rbp
0x18008950b  mov     r8, rsi
0x18008950e  lea     rcx, [rdi+20h]
0x180089512  call    ?GetArraysFromCLSIDMap@?$CreateComponentAggregateValues@UCreateEncoderInternalProperties@@@@KAJAEAV?$CMap@U_GUID@@IV?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@I@@@@0PEAU_GUID@@PEAI2I@Z; CreateComponentAggregateValues<CreateEncoderInternalProperties>::GetArraysFromCLSIDMap(CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,_GUID *,uint *,uint *,uint)
0x180089517  test    eax, eax
0x180089519  js      short loc_18008954E
0x18008951b  mov     rbx, [rdi+8]
0x18008951f  call    cs:__imp_GetTickCount64
0x180089525  mov     [rsp+88h+var_60], r15d
0x18008952a  mov     r9, r14
0x18008952d  mov     rdx, rax
0x180089530  mov     [rsp+88h+var_68], rbp
0x180089535  mov     rax, [rdi]
0x180089538  sub     rdx, rbx
0x18008953b  mov     r8, rsi
0x18008953e  mov     rcx, rdi
0x180089541  mov     rax, [rax+38h]
0x180089545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008954a  test    eax, eax
0x18008954c  jns     short loc_18008955E
0x18008954e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180089555  jz      short loc_18008955E
0x180089557  mov     ecx, eax; int
0x180089559  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008955e  mov     rcx, rsi; Block
0x180089561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089566  mov     rcx, r14; Block
0x180089569  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008956e  mov     rcx, rbp; Block
0x180089571  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089576  add     rsp, 48h
0x18008957a  pop     r15
0x18008957c  pop     r14
0x18008957e  pop     r13
0x180089580  pop     r12
0x180089582  pop     rdi
0x180089583  pop     rsi
0x180089584  pop     rbp
0x180089585  pop     rbx
0x180089586  retn
```

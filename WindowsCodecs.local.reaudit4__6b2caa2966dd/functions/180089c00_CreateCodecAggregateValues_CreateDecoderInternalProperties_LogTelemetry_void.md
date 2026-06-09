# CreateCodecAggregateValues<CreateDecoderInternalProperties>::LogTelemetry(void)

- ea: `0x180089c00`
- end: `0x180089d84`
- name: `?LogTelemetry@?$CreateCodecAggregateValues@UCreateDecoderInternalProperties@@@@UEAAXXZ`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180089c00`
- `0x180089f1c`
- `0x1800bd9d4`
- `0x1800e5a58`
- `0x1800e5a64`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180089d15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180089d15`
- `ntdll!RtlDllShutdownInProgress` at `0x180089c14`
- `ntdll!RtlDllShutdownInProgress` at `0x180089c14`

## pseudocode

```c
void __fastcall CreateCodecAggregateValues<CreateDecoderInternalProperties>::LogTelemetry(__int64 a1)
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
          ArraysFromCLSIDMap = CreateComponentAggregateValues<CreateDecoderInternalProperties>::GetArraysFromCLSIDMap(
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
0x180089c00  push    rbx
0x180089c02  push    rbp
0x180089c03  push    rsi
0x180089c04  push    rdi
0x180089c05  push    r12
0x180089c07  push    r13
0x180089c09  push    r14
0x180089c0b  push    r15
0x180089c0d  sub     rsp, 48h
0x180089c11  mov     rdi, rcx
0x180089c14  call    cs:__imp_RtlDllShutdownInProgress
0x180089c1b  nop     dword ptr [rax+rax+00h]
0x180089c20  test    al, al
0x180089c22  jnz     loc_180089D72
0x180089c28  mov     eax, [rdi+14h]
0x180089c2b  xor     esi, esi
0x180089c2d  xor     r14d, r14d
0x180089c30  xor     ebp, ebp
0x180089c32  add     eax, [rdi+10h]
0x180089c35  jz      loc_180089D5A
0x180089c3b  movsxd  r15, dword ptr [rdi+28h]
0x180089c3f  lea     eax, [rsi+10h]
0x180089c42  mul     r15
0x180089c45  lea     r12, [rsi-1]
0x180089c49  mov     rbx, r15
0x180089c4c  cmovb   rax, r12
0x180089c50  mov     rcx, rax; unsigned __int64
0x180089c53  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089c58  mov     rsi, rax
0x180089c5b  test    rax, rax
0x180089c5e  jnz     short loc_180089C76
0x180089c60  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180089c66  jz      loc_180089D5A
0x180089c6c  mov     ecx, 8007000Eh
0x180089c71  jmp     loc_180089D55
0x180089c76  mov     r8, rbx
0x180089c79  xor     edx, edx; Val
0x180089c7b  shl     r8, 4; Size
0x180089c7f  mov     rcx, rsi; void *
0x180089c82  call    memset_0
0x180089c87  mov     eax, 4
0x180089c8c  mul     rbx
0x180089c8f  cmovb   rax, r12
0x180089c93  mov     rcx, rax; unsigned __int64
0x180089c96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089c9b  mov     r14, rax
0x180089c9e  test    rax, rax
0x180089ca1  jz      short loc_180089C60
0x180089ca3  lea     r12, ds:0[r15*4]
0x180089cab  xor     edx, edx; Val
0x180089cad  mov     r8, r12; Size
0x180089cb0  mov     rcx, rax; void *
0x180089cb3  call    memset_0
0x180089cb8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180089cbf  mov     eax, 4
0x180089cc4  mul     rbx
0x180089cc7  cmovb   rax, rcx
0x180089ccb  mov     rcx, rax; unsigned __int64
0x180089cce  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089cd3  mov     rbp, rax
0x180089cd6  test    rax, rax
0x180089cd9  jnz     short loc_180089CE3
0x180089cdb  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180089ce1  jmp     short loc_180089C66
0x180089ce3  mov     r8, r12; Size
0x180089ce6  xor     edx, edx; Val
0x180089ce8  mov     rcx, rbp; void *
0x180089ceb  call    memset_0
0x180089cf0  lea     rdx, [rdi+50h]
0x180089cf4  mov     [rsp+88h+var_60], r15d
0x180089cf9  mov     r9, r14
0x180089cfc  mov     [rsp+88h+var_68], rbp
0x180089d01  mov     r8, rsi
0x180089d04  lea     rcx, [rdi+20h]
0x180089d08  call    ?GetArraysFromCLSIDMap@?$CreateComponentAggregateValues@UCreateDecoderInternalProperties@@@@KAJAEAV?$CMap@U_GUID@@IV?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@I@@@@0PEAU_GUID@@PEAI2I@Z; CreateComponentAggregateValues<CreateDecoderInternalProperties>::GetArraysFromCLSIDMap(CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,_GUID *,uint *,uint *,uint)
0x180089d0d  test    eax, eax
0x180089d0f  js      short loc_180089D4A
0x180089d11  mov     rbx, [rdi+8]
0x180089d15  call    cs:__imp_GetTickCount64
0x180089d1c  nop     dword ptr [rax+rax+00h]
0x180089d21  mov     [rsp+88h+var_60], r15d
0x180089d26  mov     r9, r14
0x180089d29  mov     rdx, rax
0x180089d2c  mov     [rsp+88h+var_68], rbp
0x180089d31  mov     rax, [rdi]
0x180089d34  sub     rdx, rbx
0x180089d37  mov     r8, rsi
0x180089d3a  mov     rcx, rdi
0x180089d3d  mov     rax, [rax+38h]
0x180089d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d46  test    eax, eax
0x180089d48  jns     short loc_180089D5A
0x180089d4a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180089d51  jz      short loc_180089D5A
0x180089d53  mov     ecx, eax; int
0x180089d55  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180089d5a  mov     rcx, rsi; Block
0x180089d5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089d62  mov     rcx, r14; Block
0x180089d65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089d6a  mov     rcx, rbp; Block
0x180089d6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089d72  add     rsp, 48h
0x180089d76  pop     r15
0x180089d78  pop     r14
0x180089d7a  pop     r13
0x180089d7c  pop     r12
0x180089d7e  pop     rdi
0x180089d7f  pop     rsi
0x180089d80  pop     rbp
0x180089d81  pop     rbx
0x180089d82  retn
```

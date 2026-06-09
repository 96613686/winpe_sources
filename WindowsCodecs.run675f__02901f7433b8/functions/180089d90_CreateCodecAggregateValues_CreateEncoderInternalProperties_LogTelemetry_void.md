# CreateCodecAggregateValues<CreateEncoderInternalProperties>::LogTelemetry(void)

- ea: `0x180089d90`
- end: `0x180089f14`
- name: `?LogTelemetry@?$CreateCodecAggregateValues@UCreateEncoderInternalProperties@@@@UEAAXXZ`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180089d90`
- `0x18008a090`
- `0x1800bd9d4`
- `0x1800e5a58`
- `0x1800e5a64`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180089ea5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180089ea5`
- `ntdll!RtlDllShutdownInProgress` at `0x180089da4`
- `ntdll!RtlDllShutdownInProgress` at `0x180089da4`

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
0x180089d90  push    rbx
0x180089d92  push    rbp
0x180089d93  push    rsi
0x180089d94  push    rdi
0x180089d95  push    r12
0x180089d97  push    r13
0x180089d99  push    r14
0x180089d9b  push    r15
0x180089d9d  sub     rsp, 48h
0x180089da1  mov     rdi, rcx
0x180089da4  call    cs:__imp_RtlDllShutdownInProgress
0x180089dab  nop     dword ptr [rax+rax+00h]
0x180089db0  test    al, al
0x180089db2  jnz     loc_180089F02
0x180089db8  mov     eax, [rdi+14h]
0x180089dbb  xor     esi, esi
0x180089dbd  xor     r14d, r14d
0x180089dc0  xor     ebp, ebp
0x180089dc2  add     eax, [rdi+10h]
0x180089dc5  jz      loc_180089EEA
0x180089dcb  movsxd  r15, dword ptr [rdi+28h]
0x180089dcf  lea     eax, [rsi+10h]
0x180089dd2  mul     r15
0x180089dd5  lea     r12, [rsi-1]
0x180089dd9  mov     rbx, r15
0x180089ddc  cmovb   rax, r12
0x180089de0  mov     rcx, rax; unsigned __int64
0x180089de3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089de8  mov     rsi, rax
0x180089deb  test    rax, rax
0x180089dee  jnz     short loc_180089E06
0x180089df0  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180089df6  jz      loc_180089EEA
0x180089dfc  mov     ecx, 8007000Eh
0x180089e01  jmp     loc_180089EE5
0x180089e06  mov     r8, rbx
0x180089e09  xor     edx, edx; Val
0x180089e0b  shl     r8, 4; Size
0x180089e0f  mov     rcx, rsi; void *
0x180089e12  call    memset_0
0x180089e17  mov     eax, 4
0x180089e1c  mul     rbx
0x180089e1f  cmovb   rax, r12
0x180089e23  mov     rcx, rax; unsigned __int64
0x180089e26  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089e2b  mov     r14, rax
0x180089e2e  test    rax, rax
0x180089e31  jz      short loc_180089DF0
0x180089e33  lea     r12, ds:0[r15*4]
0x180089e3b  xor     edx, edx; Val
0x180089e3d  mov     r8, r12; Size
0x180089e40  mov     rcx, rax; void *
0x180089e43  call    memset_0
0x180089e48  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180089e4f  mov     eax, 4
0x180089e54  mul     rbx
0x180089e57  cmovb   rax, rcx
0x180089e5b  mov     rcx, rax; unsigned __int64
0x180089e5e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089e63  mov     rbp, rax
0x180089e66  test    rax, rax
0x180089e69  jnz     short loc_180089E73
0x180089e6b  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180089e71  jmp     short loc_180089DF6
0x180089e73  mov     r8, r12; Size
0x180089e76  xor     edx, edx; Val
0x180089e78  mov     rcx, rbp; void *
0x180089e7b  call    memset_0
0x180089e80  lea     rdx, [rdi+50h]
0x180089e84  mov     [rsp+88h+var_60], r15d
0x180089e89  mov     r9, r14
0x180089e8c  mov     [rsp+88h+var_68], rbp
0x180089e91  mov     r8, rsi
0x180089e94  lea     rcx, [rdi+20h]
0x180089e98  call    ?GetArraysFromCLSIDMap@?$CreateComponentAggregateValues@UCreateEncoderInternalProperties@@@@KAJAEAV?$CMap@U_GUID@@IV?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@I@@@@0PEAU_GUID@@PEAI2I@Z; CreateComponentAggregateValues<CreateEncoderInternalProperties>::GetArraysFromCLSIDMap(CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,_GUID *,uint *,uint *,uint)
0x180089e9d  test    eax, eax
0x180089e9f  js      short loc_180089EDA
0x180089ea1  mov     rbx, [rdi+8]
0x180089ea5  call    cs:__imp_GetTickCount64
0x180089eac  nop     dword ptr [rax+rax+00h]
0x180089eb1  mov     [rsp+88h+var_60], r15d
0x180089eb6  mov     r9, r14
0x180089eb9  mov     rdx, rax
0x180089ebc  mov     [rsp+88h+var_68], rbp
0x180089ec1  mov     rax, [rdi]
0x180089ec4  sub     rdx, rbx
0x180089ec7  mov     r8, rsi
0x180089eca  mov     rcx, rdi
0x180089ecd  mov     rax, [rax+38h]
0x180089ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089ed6  test    eax, eax
0x180089ed8  jns     short loc_180089EEA
0x180089eda  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180089ee1  jz      short loc_180089EEA
0x180089ee3  mov     ecx, eax; int
0x180089ee5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180089eea  mov     rcx, rsi; Block
0x180089eed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089ef2  mov     rcx, r14; Block
0x180089ef5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089efa  mov     rcx, rbp; Block
0x180089efd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089f02  add     rsp, 48h
0x180089f06  pop     r15
0x180089f08  pop     r14
0x180089f0a  pop     r13
0x180089f0c  pop     r12
0x180089f0e  pop     rdi
0x180089f0f  pop     rsi
0x180089f10  pop     rbp
0x180089f11  pop     rbx
0x180089f12  retn
```

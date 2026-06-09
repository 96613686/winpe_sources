# CreateCodecAggregateValues<CreateDecoderInternalProperties>::LogTelemetry(void)

- ea: `0x180089290`
- end: `0x180089407`
- name: `?LogTelemetry@?$CreateCodecAggregateValues@UCreateDecoderInternalProperties@@@@UEAAXXZ`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180089290`
- `0x180089590`
- `0x1800bb784`
- `0x1800e2b88`
- `0x1800e2b94`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008939f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008939f`
- `ntdll!RtlDllShutdownInProgress` at `0x1800892a4`
- `ntdll!RtlDllShutdownInProgress` at `0x1800892a4`

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
0x180089290  push    rbx
0x180089292  push    rbp
0x180089293  push    rsi
0x180089294  push    rdi
0x180089295  push    r12
0x180089297  push    r13
0x180089299  push    r14
0x18008929b  push    r15
0x18008929d  sub     rsp, 48h
0x1800892a1  mov     rdi, rcx
0x1800892a4  call    cs:__imp_RtlDllShutdownInProgress
0x1800892aa  test    al, al
0x1800892ac  jnz     loc_1800893F6
0x1800892b2  mov     eax, [rdi+14h]
0x1800892b5  xor     esi, esi
0x1800892b7  xor     r14d, r14d
0x1800892ba  xor     ebp, ebp
0x1800892bc  add     eax, [rdi+10h]
0x1800892bf  jz      loc_1800893DE
0x1800892c5  movsxd  r15, dword ptr [rdi+28h]
0x1800892c9  lea     eax, [rsi+10h]
0x1800892cc  mul     r15
0x1800892cf  lea     r12, [rsi-1]
0x1800892d3  mov     rbx, r15
0x1800892d6  cmovb   rax, r12
0x1800892da  mov     rcx, rax; unsigned __int64
0x1800892dd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800892e2  mov     rsi, rax
0x1800892e5  test    rax, rax
0x1800892e8  jnz     short loc_180089300
0x1800892ea  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800892f0  jz      loc_1800893DE
0x1800892f6  mov     ecx, 8007000Eh
0x1800892fb  jmp     loc_1800893D9
0x180089300  mov     r8, rbx
0x180089303  xor     edx, edx; Val
0x180089305  shl     r8, 4; Size
0x180089309  mov     rcx, rsi; void *
0x18008930c  call    memset_0
0x180089311  mov     eax, 4
0x180089316  mul     rbx
0x180089319  cmovb   rax, r12
0x18008931d  mov     rcx, rax; unsigned __int64
0x180089320  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180089325  mov     r14, rax
0x180089328  test    rax, rax
0x18008932b  jz      short loc_1800892EA
0x18008932d  lea     r12, ds:0[r15*4]
0x180089335  xor     edx, edx; Val
0x180089337  mov     r8, r12; Size
0x18008933a  mov     rcx, rax; void *
0x18008933d  call    memset_0
0x180089342  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180089349  mov     eax, 4
0x18008934e  mul     rbx
0x180089351  cmovb   rax, rcx
0x180089355  mov     rcx, rax; unsigned __int64
0x180089358  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008935d  mov     rbp, rax
0x180089360  test    rax, rax
0x180089363  jnz     short loc_18008936D
0x180089365  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18008936b  jmp     short loc_1800892F0
0x18008936d  mov     r8, r12; Size
0x180089370  xor     edx, edx; Val
0x180089372  mov     rcx, rbp; void *
0x180089375  call    memset_0
0x18008937a  lea     rdx, [rdi+50h]
0x18008937e  mov     [rsp+88h+var_60], r15d
0x180089383  mov     r9, r14
0x180089386  mov     [rsp+88h+var_68], rbp
0x18008938b  mov     r8, rsi
0x18008938e  lea     rcx, [rdi+20h]
0x180089392  call    ?GetArraysFromCLSIDMap@?$CreateComponentAggregateValues@UCreateDecoderInternalProperties@@@@KAJAEAV?$CMap@U_GUID@@IV?$CDefaultTraits@U_GUID@@@@V?$CDefaultTraits@I@@@@0PEAU_GUID@@PEAI2I@Z; CreateComponentAggregateValues<CreateDecoderInternalProperties>::GetArraysFromCLSIDMap(CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,CMap<_GUID,uint,CDefaultTraits<_GUID>,CDefaultTraits<uint>> &,_GUID *,uint *,uint *,uint)
0x180089397  test    eax, eax
0x180089399  js      short loc_1800893CE
0x18008939b  mov     rbx, [rdi+8]
0x18008939f  call    cs:__imp_GetTickCount64
0x1800893a5  mov     [rsp+88h+var_60], r15d
0x1800893aa  mov     r9, r14
0x1800893ad  mov     rdx, rax
0x1800893b0  mov     [rsp+88h+var_68], rbp
0x1800893b5  mov     rax, [rdi]
0x1800893b8  sub     rdx, rbx
0x1800893bb  mov     r8, rsi
0x1800893be  mov     rcx, rdi
0x1800893c1  mov     rax, [rax+38h]
0x1800893c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893ca  test    eax, eax
0x1800893cc  jns     short loc_1800893DE
0x1800893ce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800893d5  jz      short loc_1800893DE
0x1800893d7  mov     ecx, eax; int
0x1800893d9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800893de  mov     rcx, rsi; Block
0x1800893e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800893e6  mov     rcx, r14; Block
0x1800893e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800893ee  mov     rcx, rbp; Block
0x1800893f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800893f6  add     rsp, 48h
0x1800893fa  pop     r15
0x1800893fc  pop     r14
0x1800893fe  pop     r13
0x180089400  pop     r12
0x180089402  pop     rdi
0x180089403  pop     rsi
0x180089404  pop     rbp
0x180089405  pop     rbx
0x180089406  retn
```

# DeleteFilterFromIndex

- ea: `0x1800364ac`
- end: `0x180036729`
- name: `DeleteFilterFromIndex`
- size: `637`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x180036450`
- `0x18007d180`
- `0x18007d43c`
- `0x18007d820`

## callees

- `0x180012b54`
- `0x1800145e0`
- `0x180016bf0`
- `0x180018b74`
- `0x180025870`
- `0x18002bad0`
- `0x1800343f0`
- `0x1800364ac`
- `0x180037d40`
- `0x180037e34`
- `0x180054310`
- `0x180078b54`
- `0x180078bfc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800366b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366d0`

## string_xrefs

- `0x18003652e`: `DeleteFilterFromIndex`
- `0x18003662e`: `DeleteFilterFromIndex`
- `0x180036708`: `DeleteFilterFromIndex`

## pseudocode

```c
__int64 __fastcall DeleteFilterFromIndex(__int64 a1, unsigned int a2, unsigned __int64 a3, int a4, __int64 a5)
{
  __int64 v6; // rbp
  unsigned __int16 v8; // r14
  int LayerStringFromLayerId; // eax
  __int64 v10; // r10
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rbx
  __int64 IntFilter; // rax
  __int64 v15; // rdi
  int v16; // edx
  int v17; // ebx
  int v18; // r8d
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rsi
  const char *v22; // rdx
  _QWORD v24[9]; // [rsp+50h] [rbp-48h] BYREF

  v6 = a2;
  v8 = a1;
  v24[0] = 0;
  a5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LayerStringFromLayerId = WfpGetLayerStringFromLayerId((unsigned __int16)a1);
    WPP_SF_sddI(*(_QWORD *)(v10 + 16), v11, v12, LayerStringFromLayerId, v8, v6, v12);
  }
  if ( a4 && (_DWORD)v6 )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "DeleteFilterFromIndex", 3221225485LL);
    goto LABEL_32;
  }
  IntFilter = FindIntFilter(v8, a3, &a5);
  v15 = a5;
  v13 = IntFilter;
  if ( IntFilter )
    goto LABEL_30;
  v17 = WfpGetLayerStringFromLayerId(v8);
  if ( *(__int64 *)(v15 + 16) <= 2 )
    goto LABEL_14;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_19;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_sddIqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v18, v17, v8, v6, a3, v15, *(_DWORD *)(v15 + 16));
LABEL_14:
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && *((_BYTE *)v19 + 25) >= 5u && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_sddIq(v19[2], v16, v18, v17, v8, v6, a3, v15);
LABEL_19:
  v13 = GetLayerFromIdRead(v8, v24);
  if ( !v13 )
  {
    v21 = v24[0];
    if ( a4 || !*(_QWORD *)(v24[0] + 96LL) || (_DWORD)v6 )
    {
      if ( (unsigned int)IsValidIndex(v24[0], (unsigned int)v6) )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(56LL * *(int *)(*(_QWORD *)(v21 + 144) + 16 * v6 + 8)
                                                         + MEMORY[0x1800EF368][58]
                                                         + 160))(
                *(_QWORD *)(*(_QWORD *)(v21 + 144) + 16 * v6),
                v15);
        if ( !v13 )
        {
          *(_BYTE *)(MEMORY[0x1800EF368][58] + 1076LL) = AreAllIpv4InLayersEmpty();
          EnterCriticalSection((LPCRITICAL_SECTION)&MEMORY[0x1800EF368][83]);
          *(_QWORD *)(v21 + 136) -= *(_QWORD *)(v15 + 80);
          _InterlockedDecrement((volatile signed __int32 *)(v21 + 152));
          LeaveCriticalSection((LPCRITICAL_SECTION)&MEMORY[0x1800EF368][83]);
          v13 = RemoveFilterFromFilterHashtable(v8, a3);
          if ( !v13 )
            HandleFilterDeref(v15, 0);
        }
        goto LABEL_30;
      }
      v22 = "IsValidIndex";
    }
    else
    {
      v22 = "DeleteFilterFromIndex";
    }
    v13 = WfpReportSysErrorAsNtStatus(v20, v22, 3221225485LL);
  }
LABEL_30:
  if ( v15 )
    HandleFilterDeref(v15, 0);
LABEL_32:
  if ( v13 )
    WfpReportError(v13, "DeleteFilterFromIndex");
  return v13;
}

```

## disassembly

```asm
0x1800364ac  mov     rax, rsp
0x1800364af  push    rbx
0x1800364b0  push    rbp
0x1800364b1  push    rsi
0x1800364b2  push    rdi
0x1800364b3  push    r12
0x1800364b5  push    r14
0x1800364b7  push    r15
0x1800364b9  sub     rsp, 60h
0x1800364bd  mov     r12d, r9d
0x1800364c0  mov     ebp, edx
0x1800364c2  mov     r15, r8
0x1800364c5  movzx   r14d, cx
0x1800364c9  mov     qword ptr [rax-48h], 0
0x1800364d1  mov     qword ptr [rax+28h], 0
0x1800364d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800364e0  lea     rax, WPP_GLOBAL_Control
0x1800364e7  mov     sil, 8
0x1800364ea  cmp     r10, rax
0x1800364ed  jz      short loc_18003651F
0x1800364ef  cmp     byte ptr [r10+19h], 5
0x1800364f4  jb      short loc_18003651F
0x1800364f6  test    [r10+1Ch], sil
0x1800364fa  jz      short loc_18003651F
0x1800364fc  movzx   ecx, r14w
0x180036500  call    WfpGetLayerStringFromLayerId
0x180036505  mov     rcx, [r10+10h]
0x180036509  mov     r9, rax
0x18003650c  mov     [rsp+98h+var_68], r8
0x180036511  mov     [rsp+98h+var_70], ebp
0x180036515  mov     [rsp+98h+var_78], r14d
0x18003651a  call    WPP_SF_sddI
0x18003651f  test    r12d, r12d
0x180036522  jz      short loc_180036542
0x180036524  test    ebp, ebp
0x180036526  jz      short loc_180036542
0x180036528  mov     r8d, 0C000000Dh
0x18003652e  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x180036535  call    WfpReportSysErrorAsNtStatus
0x18003653a  mov     rbx, rax
0x18003653d  jmp     loc_180036703
0x180036542  lea     r8, [rsp+98h+arg_20]
0x18003654a  mov     rdx, r15
0x18003654d  movzx   ecx, r14w
0x180036551  call    FindIntFilter
0x180036556  mov     rdi, [rsp+98h+arg_20]
0x18003655e  mov     rbx, rax
0x180036561  test    rax, rax
0x180036564  jnz     loc_1800366F4
0x18003656a  movzx   ecx, r14w
0x18003656e  call    WfpGetLayerStringFromLayerId
0x180036573  cmp     qword ptr [rdi+10h], 2
0x180036578  mov     rbx, rax
0x18003657b  jle     short loc_1800365C2
0x18003657d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036584  lea     rax, WPP_GLOBAL_Control
0x18003658b  cmp     rcx, rax
0x18003658e  jz      short loc_180036600
0x180036590  cmp     byte ptr [rcx+19h], 3
0x180036594  jb      short loc_1800365D0
0x180036596  test    [rcx+1Ch], sil
0x18003659a  jz      short loc_1800365D0
0x18003659c  mov     eax, [rdi+10h]
0x18003659f  mov     r9, rbx
0x1800365a2  mov     rcx, [rcx+10h]
0x1800365a6  mov     [rsp+98h+var_58], eax
0x1800365aa  mov     [rsp+98h+var_60], rdi
0x1800365af  mov     [rsp+98h+var_68], r15
0x1800365b4  mov     [rsp+98h+var_70], ebp
0x1800365b8  mov     [rsp+98h+var_78], r14d
0x1800365bd  call    WPP_SF_sddIqd
0x1800365c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365c9  lea     rax, WPP_GLOBAL_Control
0x1800365d0  cmp     rcx, rax
0x1800365d3  jz      short loc_180036600
0x1800365d5  cmp     byte ptr [rcx+19h], 5
0x1800365d9  jb      short loc_180036600
0x1800365db  test    [rcx+1Ch], sil
0x1800365df  jz      short loc_180036600
0x1800365e1  mov     rcx, [rcx+10h]
0x1800365e5  mov     r9, rbx
0x1800365e8  mov     [rsp+98h+var_60], rdi
0x1800365ed  mov     [rsp+98h+var_68], r15
0x1800365f2  mov     [rsp+98h+var_70], ebp
0x1800365f6  mov     [rsp+98h+var_78], r14d
0x1800365fb  call    WPP_SF_sddIq
0x180036600  lea     rdx, [rsp+98h+var_48]
0x180036605  movzx   ecx, r14w
0x180036609  call    GetLayerFromIdRead
0x18003660e  mov     rbx, rax
0x180036611  test    rax, rax
0x180036614  jnz     loc_1800366F4
0x18003661a  mov     rsi, [rsp+98h+var_48]
0x18003661f  test    r12d, r12d
0x180036622  jnz     short loc_180036648
0x180036624  cmp     [rsi+60h], rax
0x180036628  jz      short loc_180036648
0x18003662a  test    ebp, ebp
0x18003662c  jnz     short loc_180036648
0x18003662e  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x180036635  mov     r8d, 0C000000Dh
0x18003663b  call    WfpReportSysErrorAsNtStatus
0x180036640  mov     rbx, rax
0x180036643  jmp     loc_1800366F4
0x180036648  mov     edx, ebp
0x18003664a  mov     rcx, rsi
0x18003664d  call    IsValidIndex
0x180036652  test    eax, eax
0x180036654  jnz     short loc_18003665F
0x180036656  lea     rdx, aIsvalidindex; "IsValidIndex"
0x18003665d  jmp     short loc_180036635
0x18003665f  mov     r8, [rsi+90h]
0x180036666  mov     r9, rbp
0x180036669  add     r9, r9
0x18003666c  mov     rdx, rdi
0x18003666f  movsxd  rax, dword ptr [r8+r9*8+8]
0x180036674  imul    rcx, rax, 38h ; '8'
0x180036678  mov     rax, cs:1800EF538h
0x18003667f  mov     rax, [rcx+rax+0A0h]
0x180036687  mov     rcx, [r8+r9*8]
0x18003668b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036690  mov     rbx, rax
0x180036693  test    rax, rax
0x180036696  jnz     short loc_1800366F4
0x180036698  call    AreAllIpv4InLayersEmpty
0x18003669d  mov     rcx, cs:1800EF538h
0x1800366a4  mov     [rcx+434h], al
0x1800366aa  lea     rcx, cs:1800EF600h; lpCriticalSection
0x1800366b1  call    cs:__imp_EnterCriticalSection
0x1800366b7  mov     rax, [rdi+50h]
0x1800366bb  lea     rcx, cs:1800EF600h; lpCriticalSection
0x1800366c2  sub     [rsi+88h], rax
0x1800366c9  lock dec dword ptr [rsi+98h]
0x1800366d0  call    cs:__imp_LeaveCriticalSection
0x1800366d6  mov     rdx, r15
0x1800366d9  movzx   ecx, r14w
0x1800366dd  call    RemoveFilterFromFilterHashtable
0x1800366e2  mov     rbx, rax
0x1800366e5  test    rax, rax
0x1800366e8  jnz     short loc_1800366F4
0x1800366ea  xor     edx, edx
0x1800366ec  mov     rcx, rdi
0x1800366ef  call    HandleFilterDeref
0x1800366f4  test    rdi, rdi
0x1800366f7  jz      short loc_180036703
0x1800366f9  xor     edx, edx
0x1800366fb  mov     rcx, rdi
0x1800366fe  call    HandleFilterDeref
0x180036703  test    rbx, rbx
0x180036706  jz      short loc_180036717
0x180036708  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x18003670f  mov     rcx, rbx
0x180036712  call    WfpReportError
0x180036717  mov     rax, rbx
0x18003671a  add     rsp, 60h
0x18003671e  pop     r15
0x180036720  pop     r14
0x180036722  pop     r12
0x180036724  pop     rdi
0x180036725  pop     rsi
0x180036726  pop     rbp
0x180036727  pop     rbx
0x180036728  retn
```

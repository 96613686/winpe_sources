# CGrepConditionEvaluator::DoesContentMatchCondition(TRIBIT *)

- ea: `0x1800275d4`
- end: `0x18002782b`
- name: `?DoesContentMatchCondition@CGrepConditionEvaluator@@QEAAJPEAW4TRIBIT@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(CGrepConditionEvaluator *__hidden this, enum TRIBIT *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024c40`
- `0x1800261e0`

## callees

- `0x180006ca8`
- `0x18001e4c4`
- `0x1800275d4`
- `0x180027834`
- `0x1800278d8`
- `0x180027a74`
- `0x180027da0`
- `0x180029690`
- `0x180047ae0`
- `0x18005c50c`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18002767b`
- `SHCORE!IUnknown_Set` at `0x18002767b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027778`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002776b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002776b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002770b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027715`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002770b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027715`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027667`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180027667`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGrepConditionEvaluator::DoesContentMatchCondition(
        CGrepConditionEvaluator *this,
        enum TRIBIT *a2,
        int a3)
{
  int v5; // ecx
  HRESULT inited; // ebx
  int v7; // r8d
  __int64 v9; // rcx
  int i; // esi
  struct _DPA *v11; // rcx
  int v12; // eax
  struct ICondition *Ptr; // r14
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v15[3]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17[33]; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv[2]; // [rsp+150h] [rbp+50h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start,
      a3,
      1,
      (__int64)ppv);
  *(_DWORD *)a2 = 0;
  inited = CGrepConditionEvaluator::_InitFilter(this);
  if ( !inited )
  {
    ppv[0] = 0;
    inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, ppv);
    if ( inited >= 0 )
    {
      IUnknown_Set((IUnknown **)this + 1, (IUnknown *)ppv[0]);
      v14 = 0;
      CGrep::CGrep((CGrep *)&v16, *((struct IFilter **)this + 13), *((struct IQueryContinue **)this + 23));
LABEL_10:
      if ( !inited )
      {
        while ( v14 != 1 )
        {
          v9 = *((_QWORD *)this + 23);
          if ( v9 )
            inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
          if ( inited )
            break;
          inited = CGrepConditionEvaluator::_GetNextChunk(this);
          if ( inited )
            break;
          if ( (*((_BYTE *)this + 120) & 1) != 0 )
          {
            inited = CGrep::GrepText(
                       (CGrep *)&v16,
                       (const struct tagSTAT_CHUNK *)((char *)this + 112),
                       this,
                       (enum TRIBIT *)&v14);
            goto LABEL_10;
          }
          if ( (*((_BYTE *)this + 120) & 2) != 0 )
          {
            for ( i = 0; ; ++i )
            {
              v11 = (struct _DPA *)*((_QWORD *)this + 10);
              v12 = v11 ? *(_DWORD *)v11 : 0;
              if ( i >= v12 || inited < 0 || v14 == 1 )
                break;
              Ptr = (struct ICondition *)g_pfn_DPA_GetPtr(v11, i);
              v15[0] = 0;
              inited = GetEvalStateEx(Ptr, L"ES", v15);
              if ( inited >= 0 && !v15[0] )
                inited = CGrepConditionEvaluator::EvalValueChunk(this, Ptr, (enum TRIBIT *)&v14);
            }
            PropVariantClear(*((PROPVARIANT **)this + 25));
            CoTaskMemFree(*((LPVOID *)this + 25));
            *((_QWORD *)this + 25) = 0;
            goto LABEL_10;
          }
        }
      }
      *(_DWORD *)a2 = v14;
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      SafeRelease<IShellItemArray>(v17);
      LocalFree((HLOCAL)v17[17]);
      LocalFree((HLOCAL)v17[20]);
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x200000) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v5,
      (unsigned int)ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop,
      v7,
      1,
      (__int64)ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800275d4  mov     [rsp-8+arg_10], rbx
0x1800275d9  push    rbp
0x1800275da  push    rsi
0x1800275db  push    rdi
0x1800275dc  push    r14
0x1800275de  push    r15
0x1800275e0  lea     rbp, [rsp-70h]
0x1800275e5  sub     rsp, 170h
0x1800275ec  mov     rax, cs:__security_cookie
0x1800275f3  xor     rax, rsp
0x1800275f6  mov     [rbp+90h+var_30], rax
0x1800275fa  mov     r15, rdx
0x1800275fd  mov     rdi, rcx
0x180027600  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x180027607  jnz     loc_180027792
0x18002760d  mov     dword ptr [r15], 0
0x180027614  mov     rcx, rdi; this
0x180027617  call    ?_InitFilter@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_InitFilter(void)
0x18002761c  mov     ebx, eax
0x18002761e  test    eax, eax
0x180027620  jz      short loc_180027654
0x180027622  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 20h
0x180027629  jnz     loc_18002780B
0x18002762f  mov     eax, ebx
0x180027631  mov     rcx, [rbp+90h+var_30]
0x180027635  xor     rcx, rsp; StackCookie
0x180027638  call    __security_check_cookie
0x18002763d  mov     rbx, [rsp+190h+arg_10]
0x180027645  add     rsp, 170h
0x18002764c  pop     r15
0x18002764e  pop     r14
0x180027650  pop     rdi
0x180027651  pop     rsi
0x180027652  pop     rbp
0x180027653  retn
0x180027654  mov     [rbp+90h+ppv], 0
0x18002765c  lea     rdx, [rbp+90h+ppv]; ppv
0x180027660  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180027667  call    cs:__imp_PSCreateMemoryPropertyStore
0x18002766d  mov     ebx, eax
0x18002766f  test    eax, eax
0x180027671  js      short loc_180027622
0x180027673  lea     rcx, [rdi+8]; ppunk
0x180027677  mov     rdx, [rbp+90h+ppv]; punk
0x18002767b  call    cs:__imp_IUnknown_Set
0x180027681  mov     [rsp+190h+var_160], 0
0x180027689  mov     r8, [rdi+0B8h]; struct IQueryContinue *
0x180027690  mov     rdx, [rdi+68h]; struct IFilter *
0x180027694  lea     rcx, [rsp+190h+var_150]; this
0x180027699  call    ??0CGrep@@QEAA@PEAUIFilter@@PEAUIQueryContinue@@@Z; CGrep::CGrep(IFilter *,IQueryContinue *)
0x18002769e  nop
0x18002769f  jmp     short loc_1800276B9
0x1800276a1  lea     r9, [rsp+190h+var_160]; enum TRIBIT *
0x1800276a6  mov     r8, rdi; struct CConditionEvaluator *
0x1800276a9  lea     rdx, [rdi+70h]; struct tagSTAT_CHUNK *
0x1800276ad  lea     rcx, [rsp+190h+var_150]; this
0x1800276b2  call    ?GrepText@CGrep@@QEAAJAEBUtagSTAT_CHUNK@@PEAVCConditionEvaluator@@PEAW4TRIBIT@@@Z; CGrep::GrepText(tagSTAT_CHUNK const &,CConditionEvaluator *,TRIBIT *)
0x1800276b7  mov     ebx, eax
0x1800276b9  test    ebx, ebx
0x1800276bb  jnz     short loc_1800276D4
0x1800276bd  cmp     [rsp+190h+var_160], 1
0x1800276c2  jz      short loc_1800276D4
0x1800276c4  mov     rcx, [rdi+0B8h]
0x1800276cb  test    rcx, rcx
0x1800276ce  jnz     short loc_180027721
0x1800276d0  test    ebx, ebx
0x1800276d2  jz      short loc_180027731
0x1800276d4  mov     eax, [rsp+190h+var_160]
0x1800276d8  mov     [r15], eax
0x1800276db  mov     rcx, [rbp+90h+ppv]
0x1800276df  mov     rax, [rcx]
0x1800276e2  mov     rax, [rax+10h]
0x1800276e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276eb  nop
0x1800276ec  mov     rcx, [rsp+190h+var_150]
0x1800276f1  mov     rax, [rcx]
0x1800276f4  mov     rax, [rax+10h]
0x1800276f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276fd  lea     rcx, [rsp+190h+var_148]
0x180027702  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180027707  mov     rcx, [rbp+90h+hMem]; hMem
0x18002770b  call    cs:__imp_LocalFree
0x180027711  mov     rcx, [rbp+90h+var_A8]; hMem
0x180027715  call    cs:__imp_LocalFree
0x18002771b  nop
0x18002771c  jmp     loc_180027622
0x180027721  mov     rax, [rcx]
0x180027724  mov     rax, [rax+18h]
0x180027728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002772d  mov     ebx, eax
0x18002772f  jmp     short loc_1800276D0
0x180027731  mov     rcx, rdi; this
0x180027734  call    ?_GetNextChunk@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_GetNextChunk(void)
0x180027739  mov     ebx, eax
0x18002773b  test    eax, eax
0x18002773d  jnz     short loc_1800276D4
0x18002773f  test    byte ptr [rdi+78h], 1
0x180027743  jnz     loc_1800276A1
0x180027749  test    byte ptr [rdi+78h], 2
0x18002774d  jz      loc_1800276BD
0x180027753  xor     esi, esi
0x180027755  mov     rcx, [rdi+50h]; hdpa
0x180027759  test    rcx, rcx
0x18002775c  jz      short loc_18002778E
0x18002775e  mov     eax, [rcx]
0x180027760  cmp     esi, eax
0x180027762  jl      short loc_1800277B2
0x180027764  mov     rcx, [rdi+0C8h]; pvar
0x18002776b  call    cs:__imp_PropVariantClear
0x180027771  mov     rcx, [rdi+0C8h]; pv
0x180027778  call    cs:__imp_CoTaskMemFree
0x18002777e  mov     qword ptr [rdi+0C8h], 0
0x180027789  jmp     loc_1800276B9
0x18002778e  xor     eax, eax
0x180027790  jmp     short loc_180027760
0x180027792  lea     rax, [rbp+90h+ppv]
0x180027796  mov     [rsp+190h+var_170], rax
0x18002779b  mov     r9d, 1
0x1800277a1  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start
0x1800277a8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800277ad  jmp     loc_18002760D
0x1800277b2  test    ebx, ebx
0x1800277b4  js      short loc_180027764
0x1800277b6  cmp     [rsp+190h+var_160], 1
0x1800277bb  jz      short loc_180027764
0x1800277bd  movsxd  rdx, esi; i
0x1800277c0  call    cs:g_pfn_DPA_GetPtr
0x1800277c6  mov     r14, rax
0x1800277c9  mov     [rsp+190h+var_15C], 0
0x1800277d1  lea     r8, [rsp+190h+var_15C]
0x1800277d6  lea     rdx, aEs; "ES"
0x1800277dd  mov     rcx, rax
0x1800277e0  call    GetEvalStateEx
0x1800277e5  mov     ebx, eax
0x1800277e7  test    eax, eax
0x1800277e9  js      short loc_180027804
0x1800277eb  cmp     [rsp+190h+var_15C], 0
0x1800277f0  jnz     short loc_180027804
0x1800277f2  lea     r8, [rsp+190h+var_160]; enum TRIBIT *
0x1800277f7  mov     rdx, r14; struct ICondition *
0x1800277fa  mov     rcx, rdi; this
0x1800277fd  call    ?EvalValueChunk@CGrepConditionEvaluator@@AEAAJPEAUICondition@@PEAW4TRIBIT@@@Z; CGrepConditionEvaluator::EvalValueChunk(ICondition *,TRIBIT *)
0x180027802  mov     ebx, eax
0x180027804  inc     esi
0x180027806  jmp     loc_180027755
0x18002780b  lea     rax, [rbp+90h+ppv]
0x18002780f  mov     [rsp+190h+var_170], rax
0x180027814  mov     r9d, 1
0x18002781a  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop
0x180027821  call    McGenEventWrite_EtwEventWriteTransfer
0x180027826  jmp     loc_18002762F
```

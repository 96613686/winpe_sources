# CGrepConditionEvaluator::DoesContentMatchCondition(TRIBIT *)

- ea: `0x180063bfc`
- end: `0x180063eb7`
- name: `?DoesContentMatchCondition@CGrepConditionEvaluator@@QEAAJPEAW4TRIBIT@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(CGrepConditionEvaluator *__hidden this, enum TRIBIT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065114`

## callees

- `0x180043c30`
- `0x1800446fc`
- `0x180062bc8`
- `0x180063bfc`
- `0x180063f7c`
- `0x1800652b0`
- `0x180068e50`
- `0x18006a858`
- `0x18006a998`
- `0x18006b2a0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e25`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180063e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063e32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063e32`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180063c7a`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180063c7a`
- `SHCORE!IUnknown_Set` at `0x180063c92`
- `SHCORE!IUnknown_Set` at `0x180063c92`

## pseudocode

```c
__int64 __fastcall CGrepConditionEvaluator::DoesContentMatchCondition(
        CGrepConditionEvaluator *this,
        enum TRIBIT *a2,
        int a3,
        int a4)
{
  HRESULT inited; // ebx
  int v7; // r8d
  int v8; // r9d
  __int64 *v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  void (__fastcall *v12)(__int64 *); // rax
  __int64 v13; // rcx
  HRESULT v14; // eax
  int i; // esi
  struct _DPA *v16; // rcx
  int v17; // eax
  struct ICondition *Ptr; // rax
  struct ICondition *v19; // r14
  ULONGLONG v20; // rcx
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v23[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v24[17]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+C8h] [rbp-38h]
  __int64 v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  __int64 v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR ppv; // [rsp+150h] [rbp+50h] BYREF

  if ( (byte_180091FC2 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (int)&Microsoft_Windows_Shell_Core_Provider_Context,
      (int)&ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start,
      a3,
      a4,
      &ppv);
  *(_DWORD *)a2 = 0;
  inited = CGrepConditionEvaluator::_InitFilter(this);
  if ( !inited )
  {
    ppv.Ptr = 0;
    inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)&ppv);
    if ( inited >= 0 )
    {
      IUnknown_Set((IUnknown **)this + 1, (IUnknown *)ppv.Ptr);
      v9 = (__int64 *)*((_QWORD *)this + 13);
      v10 = *((_QWORD *)this + 23);
      v22 = 0;
      v24[0] = v9;
      v11 = *v9;
      v24[1] = v10;
      v24[8] = 0;
      v25 = 1;
      v12 = *(void (__fastcall **)(__int64 *))(v11 + 8);
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v12(v9);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
LABEL_34:
      if ( !inited )
      {
        while ( v22 != 1 )
        {
          v13 = *((_QWORD *)this + 23);
          if ( v13 )
            inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
          if ( inited )
            break;
          while ( 1 )
          {
            memset_0((char *)this + 112, 0, 0x40u);
            v14 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 32LL))(
                    *((_QWORD *)this + 13),
                    (char *)this + 112);
            inited = v14;
            if ( v14 )
              break;
            if ( (*((_DWORD *)this + 30) & 3) != 0 )
            {
              ++*((_DWORD *)this + 44);
              goto LABEL_18;
            }
          }
          if ( (unsigned int)(v14 + 2147215609) <= 1 || v14 == -2147215616 || v14 == 268036 )
            inited = 1;
LABEL_18:
          if ( inited )
            break;
          if ( (*((_BYTE *)this + 120) & 1) != 0 )
          {
            inited = CGrep::GrepText(
                       (CGrep *)v24,
                       (const struct tagSTAT_CHUNK *)((char *)this + 112),
                       this,
                       (enum TRIBIT *)&v22);
            goto LABEL_34;
          }
          if ( (*((_BYTE *)this + 120) & 2) != 0 )
          {
            for ( i = 0; ; ++i )
            {
              v16 = (struct _DPA *)*((_QWORD *)this + 10);
              v17 = v16 ? *(_DWORD *)v16 : 0;
              if ( i >= v17 || inited < 0 || v22 == 1 )
                break;
              Ptr = (struct ICondition *)g_pfn_DPA_GetPtr(v16, i);
              v23[0] = 0;
              v19 = Ptr;
              inited = GetEvalStateEx(Ptr, L"ES", v23);
              if ( inited >= 0 && !v23[0] )
                inited = CGrepConditionEvaluator::EvalValueChunk(this, v19, (enum TRIBIT *)&v22);
            }
            PropVariantClear(*((PROPVARIANT **)this + 25));
            CoTaskMemFree(*((LPVOID *)this + 25));
            *((_QWORD *)this + 25) = 0;
            goto LABEL_34;
          }
        }
      }
      v20 = ppv.Ptr;
      *(_DWORD *)a2 = v22;
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v20 + 16LL))(v20);
      CGrep::~CGrep((CGrep *)v24);
    }
  }
  if ( (byte_180091FC2 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (int)&Microsoft_Windows_Shell_Core_Provider_Context,
      (int)&ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop,
      v7,
      v8,
      &ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180063bfc  mov     [rsp-8+arg_10], rbx
0x180063c01  mov     [rsp-8+arg_18], rsi
0x180063c06  push    rbp
0x180063c07  push    rdi
0x180063c08  push    r12
0x180063c0a  push    r14
0x180063c0c  push    r15
0x180063c0e  lea     rbp, [rsp-70h]
0x180063c13  sub     rsp, 170h
0x180063c1a  mov     rax, cs:__security_cookie
0x180063c21  xor     rax, rsp
0x180063c24  mov     [rbp+90h+var_30], rax
0x180063c28  test    cs:byte_180091FC2, 20h
0x180063c2f  mov     r15, rdx
0x180063c32  mov     rdi, rcx
0x180063c35  jz      short loc_180063C53
0x180063c37  lea     rax, [rbp+90h+ppv]
0x180063c3b  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start; int
0x180063c42  mov     [rsp+190h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x180063c47  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context; int
0x180063c4e  call    McGenEventWrite_EventWriteTransfer
0x180063c53  xor     r12d, r12d
0x180063c56  mov     rcx, rdi; this
0x180063c59  mov     [r15], r12d
0x180063c5c  call    ?_InitFilter@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_InitFilter(void)
0x180063c61  mov     ebx, eax
0x180063c63  test    eax, eax
0x180063c65  jnz     loc_180063E68
0x180063c6b  lea     rdx, [rbp+90h+ppv]; ppv
0x180063c6f  mov     qword ptr [rbp+90h+ppv], r12
0x180063c73  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180063c7a  call    cs:__imp_PSCreateMemoryPropertyStore
0x180063c80  mov     ebx, eax
0x180063c82  test    eax, eax
0x180063c84  js      loc_180063E68
0x180063c8a  mov     rdx, qword ptr [rbp+90h+ppv]; punk
0x180063c8e  lea     rcx, [rdi+8]; ppunk
0x180063c92  call    cs:__imp_IUnknown_Set
0x180063c98  mov     rcx, [rdi+68h]
0x180063c9c  mov     rsi, [rdi+0B8h]
0x180063ca3  mov     [rsp+190h+var_160], r12d
0x180063ca8  mov     [rsp+190h+var_150], rcx
0x180063cad  mov     rax, [rcx]
0x180063cb0  mov     [rsp+190h+var_148], rsi
0x180063cb5  mov     [rbp+90h+var_110], r12
0x180063cb9  mov     [rbp+90h+var_C8], 1
0x180063cc0  mov     rax, [rax+8]
0x180063cc4  mov     [rbp+90h+var_C0], r12
0x180063cc8  mov     [rbp+90h+var_B8], r12
0x180063ccc  mov     [rbp+90h+var_B0], r12
0x180063cd0  mov     [rbp+90h+var_A8], r12
0x180063cd4  mov     [rbp+90h+var_A0], r12
0x180063cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cdd  test    rsi, rsi
0x180063ce0  jz      loc_180063E3F
0x180063ce6  mov     rax, [rsi]
0x180063ce9  mov     rcx, rsi
0x180063cec  mov     rax, [rax+8]
0x180063cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cf5  jmp     loc_180063E3F
0x180063cfa  cmp     [rsp+190h+var_160], 1
0x180063cff  jz      loc_180063E47
0x180063d05  mov     rcx, [rdi+0B8h]
0x180063d0c  test    rcx, rcx
0x180063d0f  jz      short loc_180063D1F
0x180063d11  mov     rax, [rcx]
0x180063d14  mov     rax, [rax+18h]
0x180063d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d1d  mov     ebx, eax
0x180063d1f  test    ebx, ebx
0x180063d21  jnz     loc_180063E47
0x180063d27  lea     rsi, [rdi+70h]
0x180063d2b  xor     edx, edx; Val
0x180063d2d  mov     rcx, rsi; void *
0x180063d30  lea     r8d, [rdx+40h]; Size
0x180063d34  call    memset_0
0x180063d39  mov     rcx, [rdi+68h]
0x180063d3d  mov     rdx, rsi
0x180063d40  mov     rax, [rcx]
0x180063d43  mov     rax, [rax+20h]
0x180063d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d4c  mov     ebx, eax
0x180063d4e  test    eax, eax
0x180063d50  jnz     short loc_180063D61
0x180063d52  mov     eax, [rdi+78h]
0x180063d55  test    al, 3
0x180063d57  jz      short loc_180063D2B
0x180063d59  inc     dword ptr [rdi+0B0h]
0x180063d5f  jmp     short loc_180063D80
0x180063d61  add     eax, 7FFBE8F9h
0x180063d66  cmp     eax, 1
0x180063d69  jbe     short loc_180063D7B
0x180063d6b  cmp     ebx, 80041700h
0x180063d71  jz      short loc_180063D7B
0x180063d73  cmp     ebx, 41704h
0x180063d79  jnz     short loc_180063D80
0x180063d7b  mov     ebx, 1
0x180063d80  test    ebx, ebx
0x180063d82  jnz     loc_180063E47
0x180063d88  test    byte ptr [rdi+78h], 1
0x180063d8c  jz      short loc_180063DAA
0x180063d8e  lea     r9, [rsp+190h+var_160]; enum TRIBIT *
0x180063d93  mov     r8, rdi; struct CConditionEvaluator *
0x180063d96  mov     rdx, rsi; struct tagSTAT_CHUNK *
0x180063d99  lea     rcx, [rsp+190h+var_150]; this
0x180063d9e  call    ?GrepText@CGrep@@QEAAJAEBUtagSTAT_CHUNK@@PEAVCConditionEvaluator@@PEAW4TRIBIT@@@Z; CGrep::GrepText(tagSTAT_CHUNK const &,CConditionEvaluator *,TRIBIT *)
0x180063da3  mov     ebx, eax
0x180063da5  jmp     loc_180063E3F
0x180063daa  test    byte ptr [rsi+8], 2
0x180063dae  jz      loc_180063CFA
0x180063db4  mov     esi, r12d
0x180063db7  mov     rcx, [rdi+50h]; hdpa
0x180063dbb  test    rcx, rcx
0x180063dbe  jz      short loc_180063DC4
0x180063dc0  mov     eax, [rcx]
0x180063dc2  jmp     short loc_180063DC7
0x180063dc4  mov     eax, r12d
0x180063dc7  cmp     esi, eax
0x180063dc9  jge     short loc_180063E1E
0x180063dcb  test    ebx, ebx
0x180063dcd  js      short loc_180063E1E
0x180063dcf  cmp     [rsp+190h+var_160], 1
0x180063dd4  jz      short loc_180063E1E
0x180063dd6  movsxd  rdx, esi; i
0x180063dd9  call    cs:g_pfn_DPA_GetPtr
0x180063ddf  lea     r8, [rsp+190h+var_15C]
0x180063de4  mov     [rsp+190h+var_15C], r12d
0x180063de9  mov     rcx, rax
0x180063dec  lea     rdx, aEs; "ES"
0x180063df3  mov     r14, rax
0x180063df6  call    GetEvalStateEx
0x180063dfb  mov     ebx, eax
0x180063dfd  test    eax, eax
0x180063dff  js      short loc_180063E1A
0x180063e01  cmp     [rsp+190h+var_15C], r12d
0x180063e06  jnz     short loc_180063E1A
0x180063e08  lea     r8, [rsp+190h+var_160]; enum TRIBIT *
0x180063e0d  mov     rdx, r14; struct ICondition *
0x180063e10  mov     rcx, rdi; this
0x180063e13  call    ?EvalValueChunk@CGrepConditionEvaluator@@AEAAJPEAUICondition@@PEAW4TRIBIT@@@Z; CGrepConditionEvaluator::EvalValueChunk(ICondition *,TRIBIT *)
0x180063e18  mov     ebx, eax
0x180063e1a  inc     esi
0x180063e1c  jmp     short loc_180063DB7
0x180063e1e  mov     rcx, [rdi+0C8h]; pvar
0x180063e25  call    cs:__imp_PropVariantClear
0x180063e2b  mov     rcx, [rdi+0C8h]; pv
0x180063e32  call    cs:__imp_CoTaskMemFree
0x180063e38  mov     [rdi+0C8h], r12
0x180063e3f  test    ebx, ebx
0x180063e41  jz      loc_180063CFA
0x180063e47  mov     eax, [rsp+190h+var_160]
0x180063e4b  mov     rcx, qword ptr [rbp+90h+ppv]
0x180063e4f  mov     [r15], eax
0x180063e52  mov     rax, [rcx]
0x180063e55  mov     rax, [rax+10h]
0x180063e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e5e  lea     rcx, [rsp+190h+var_150]; this
0x180063e63  call    ??1CGrep@@QEAA@XZ; CGrep::~CGrep(void)
0x180063e68  test    cs:byte_180091FC2, 20h
0x180063e6f  jz      short loc_180063E8D
0x180063e71  lea     rax, [rbp+90h+ppv]
0x180063e75  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop; int
0x180063e7c  mov     [rsp+190h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x180063e81  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context; int
0x180063e88  call    McGenEventWrite_EventWriteTransfer
0x180063e8d  mov     eax, ebx
0x180063e8f  mov     rcx, [rbp+90h+var_30]
0x180063e93  xor     rcx, rsp; StackCookie
0x180063e96  call    __security_check_cookie
0x180063e9b  lea     r11, [rsp+190h+var_20]
0x180063ea3  mov     rbx, [r11+40h]
0x180063ea7  mov     rsi, [r11+48h]
0x180063eab  mov     rsp, r11
0x180063eae  pop     r15
0x180063eb0  pop     r14
0x180063eb2  pop     r12
0x180063eb4  pop     rdi
0x180063eb5  pop     rbp
0x180063eb6  retn
```

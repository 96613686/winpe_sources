# CGrepConditionEvaluator::DoesContentMatchCondition(TRIBIT *)

- ea: `0x180044cfc`
- end: `0x180044fbc`
- name: `?DoesContentMatchCondition@CGrepConditionEvaluator@@QEAAJPEAW4TRIBIT@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(CGrepConditionEvaluator *__hidden this, enum TRIBIT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800463a4`

## callees

- `0x1800030b6`
- `0x18000340e`
- `0x1800127ac`
- `0x180043ec8`
- `0x180044cfc`
- `0x18004508c`
- `0x18004654c`
- `0x180049da4`
- `0x18004bc88`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f35`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044f28`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180044f28`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044d81`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044d81`
- `COMCTL32!__imp_DPA_GetPtr` at `0x180044edb`
- `COMCTL32!__imp_DPA_GetPtr` at `0x180044edb`

## pseudocode

```c
__int64 __fastcall CGrepConditionEvaluator::DoesContentMatchCondition(
        CGrepConditionEvaluator *this,
        enum TRIBIT *a2,
        __int64 a3)
{
  HRESULT inited; // ebx
  __int64 v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  void (__fastcall *v10)(__int64 *); // rax
  __int64 v11; // rcx
  HRESULT v12; // eax
  int i; // esi
  struct _DPA *v14; // rcx
  int v15; // eax
  struct ICondition *Ptr; // rax
  struct ICondition *v17; // r14
  void *v18; // rcx
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v21[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v22[17]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+C8h] [rbp-38h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  __int64 v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  void *ppv[2]; // [rsp+150h] [rbp+50h] BYREF

  if ( (byte_1800AA742 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start,
      a3,
      1,
      ppv);
  *(_DWORD *)a2 = 0;
  inited = CGrepConditionEvaluator::_InitFilter(this);
  if ( !inited )
  {
    ppv[0] = 0;
    inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, ppv);
    if ( inited >= 0 )
    {
      IUnknown_Set_0((IUnknown **)this + 1, (IUnknown *)ppv[0]);
      v7 = (__int64 *)*((_QWORD *)this + 13);
      v8 = *((_QWORD *)this + 23);
      v20 = 0;
      v22[0] = v7;
      v9 = *v7;
      v22[1] = v8;
      v22[8] = 0;
      v23 = 1;
      v10 = *(void (__fastcall **)(__int64 *))(v9 + 8);
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v10(v7);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_34:
      if ( !inited )
      {
        while ( v20 != 1 )
        {
          v11 = *((_QWORD *)this + 23);
          if ( v11 )
            inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
          if ( inited )
            break;
          while ( 1 )
          {
            memset_0((char *)this + 112, 0, 0x40u);
            v12 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 32LL))(
                    *((_QWORD *)this + 13),
                    (char *)this + 112);
            inited = v12;
            if ( v12 )
              break;
            if ( (*((_DWORD *)this + 30) & 3) != 0 )
            {
              ++*((_DWORD *)this + 44);
              goto LABEL_18;
            }
          }
          if ( (unsigned int)(v12 + 2147215609) <= 1 || v12 == -2147215616 || v12 == 268036 )
            inited = 1;
LABEL_18:
          if ( inited )
            break;
          if ( (*((_BYTE *)this + 120) & 1) != 0 )
          {
            inited = CGrep::GrepText(
                       (CGrep *)v22,
                       (const struct tagSTAT_CHUNK *)((char *)this + 112),
                       this,
                       (enum TRIBIT *)&v20);
            goto LABEL_34;
          }
          if ( (*((_BYTE *)this + 120) & 2) != 0 )
          {
            for ( i = 0; ; ++i )
            {
              v14 = (struct _DPA *)*((_QWORD *)this + 10);
              v15 = v14 ? *(_DWORD *)v14 : 0;
              if ( i >= v15 || inited < 0 || v20 == 1 )
                break;
              Ptr = (struct ICondition *)DPA_GetPtr(v14, i);
              v21[0] = 0;
              v17 = Ptr;
              inited = GetEvalStateEx(Ptr, L"ES", v21);
              if ( inited >= 0 && !v21[0] )
                inited = CGrepConditionEvaluator::EvalValueChunk(this, v17, (enum TRIBIT *)&v20);
            }
            PropVariantClear(*((PROPVARIANT **)this + 25));
            CoTaskMemFree(*((LPVOID *)this + 25));
            *((_QWORD *)this + 25) = 0;
            goto LABEL_34;
          }
        }
      }
      v18 = ppv[0];
      *(_DWORD *)a2 = v20;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
      CGrep::~CGrep((CGrep *)v22);
    }
  }
  if ( (byte_1800AA742 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop,
      v6,
      1,
      ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180044cfc  mov     [rsp-8+arg_10], rbx
0x180044d01  push    rbp
0x180044d02  push    rsi
0x180044d03  push    rdi
0x180044d04  push    r12
0x180044d06  push    r13
0x180044d08  push    r14
0x180044d0a  push    r15
0x180044d0c  lea     rbp, [rsp-70h]
0x180044d11  sub     rsp, 170h
0x180044d18  mov     rax, cs:__security_cookie
0x180044d1f  xor     rax, rsp
0x180044d22  mov     [rbp+0A0h+var_40], rax
0x180044d26  test    cs:byte_1800AA742, 20h
0x180044d2d  mov     r15, rdx
0x180044d30  mov     rdi, rcx
0x180044d33  mov     r13d, 1
0x180044d39  jz      short loc_180044D5A
0x180044d3b  lea     rax, [rbp+0A0h+ppv]
0x180044d3f  mov     r9d, r13d
0x180044d42  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start
0x180044d49  mov     [rsp+1A0h+var_180], rax
0x180044d4e  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180044d55  call    McGenEventWrite_EventWriteTransfer
0x180044d5a  xor     r12d, r12d
0x180044d5d  mov     rcx, rdi; this
0x180044d60  mov     [r15], r12d
0x180044d63  call    ?_InitFilter@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_InitFilter(void)
0x180044d68  mov     ebx, eax
0x180044d6a  test    eax, eax
0x180044d6c  jnz     loc_180044F6B
0x180044d72  lea     rdx, [rbp+0A0h+ppv]; ppv
0x180044d76  mov     [rbp+0A0h+ppv], r12
0x180044d7a  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180044d81  call    cs:__imp_PSCreateMemoryPropertyStore
0x180044d87  mov     ebx, eax
0x180044d89  test    eax, eax
0x180044d8b  js      loc_180044F6B
0x180044d91  mov     rdx, [rbp+0A0h+ppv]; punk
0x180044d95  lea     rcx, [rdi+8]; ppunk
0x180044d99  call    IUnknown_Set_0
0x180044d9e  mov     rcx, [rdi+68h]
0x180044da2  mov     rsi, [rdi+0B8h]
0x180044da9  mov     [rsp+1A0h+var_170], r12d
0x180044dae  mov     [rsp+1A0h+var_160], rcx
0x180044db3  mov     rax, [rcx]
0x180044db6  mov     [rsp+1A0h+var_158], rsi
0x180044dbb  mov     [rbp+0A0h+var_120], r12
0x180044dbf  mov     [rbp+0A0h+var_D8], r13d
0x180044dc3  mov     rax, [rax+8]
0x180044dc7  mov     [rbp+0A0h+var_D0], r12
0x180044dcb  mov     [rbp+0A0h+var_C8], r12
0x180044dcf  mov     [rbp+0A0h+var_C0], r12
0x180044dd3  mov     [rbp+0A0h+var_B8], r12
0x180044dd7  mov     [rbp+0A0h+var_B0], r12
0x180044ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044de0  test    rsi, rsi
0x180044de3  jz      loc_180044F42
0x180044de9  mov     rax, [rsi]
0x180044dec  mov     rcx, rsi
0x180044def  mov     rax, [rax+8]
0x180044df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044df8  jmp     loc_180044F42
0x180044dfd  cmp     [rsp+1A0h+var_170], r13d
0x180044e02  jz      loc_180044F4A
0x180044e08  mov     rcx, [rdi+0B8h]
0x180044e0f  test    rcx, rcx
0x180044e12  jz      short loc_180044E22
0x180044e14  mov     rax, [rcx]
0x180044e17  mov     rax, [rax+18h]
0x180044e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e20  mov     ebx, eax
0x180044e22  test    ebx, ebx
0x180044e24  jnz     loc_180044F4A
0x180044e2a  lea     rsi, [rdi+70h]
0x180044e2e  xor     edx, edx; Val
0x180044e30  mov     rcx, rsi; void *
0x180044e33  lea     r8d, [rdx+40h]; Size
0x180044e37  call    memset_0
0x180044e3c  mov     rcx, [rdi+68h]
0x180044e40  mov     rdx, rsi
0x180044e43  mov     rax, [rcx]
0x180044e46  mov     rax, [rax+20h]
0x180044e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e4f  mov     ebx, eax
0x180044e51  test    eax, eax
0x180044e53  jnz     short loc_180044E65
0x180044e55  mov     eax, [rdi+78h]
0x180044e58  test    al, 3
0x180044e5a  jz      short loc_180044E2E
0x180044e5c  add     [rdi+0B0h], r13d
0x180044e63  jmp     short loc_180044E82
0x180044e65  add     eax, 7FFBE8F9h
0x180044e6a  cmp     eax, r13d
0x180044e6d  jbe     short loc_180044E7F
0x180044e6f  cmp     ebx, 80041700h
0x180044e75  jz      short loc_180044E7F
0x180044e77  cmp     ebx, 41704h
0x180044e7d  jnz     short loc_180044E82
0x180044e7f  mov     ebx, r13d
0x180044e82  test    ebx, ebx
0x180044e84  jnz     loc_180044F4A
0x180044e8a  test    [rdi+78h], r13b
0x180044e8e  jz      short loc_180044EAC
0x180044e90  lea     r9, [rsp+1A0h+var_170]; enum TRIBIT *
0x180044e95  mov     r8, rdi; struct CConditionEvaluator *
0x180044e98  mov     rdx, rsi; struct tagSTAT_CHUNK *
0x180044e9b  lea     rcx, [rsp+1A0h+var_160]; this
0x180044ea0  call    ?GrepText@CGrep@@QEAAJAEBUtagSTAT_CHUNK@@PEAVCConditionEvaluator@@PEAW4TRIBIT@@@Z; CGrep::GrepText(tagSTAT_CHUNK const &,CConditionEvaluator *,TRIBIT *)
0x180044ea5  mov     ebx, eax
0x180044ea7  jmp     loc_180044F42
0x180044eac  test    byte ptr [rsi+8], 2
0x180044eb0  jz      loc_180044DFD
0x180044eb6  mov     esi, r12d
0x180044eb9  mov     rcx, [rdi+50h]; hdpa
0x180044ebd  test    rcx, rcx
0x180044ec0  jz      short loc_180044EC6
0x180044ec2  mov     eax, [rcx]
0x180044ec4  jmp     short loc_180044EC9
0x180044ec6  mov     eax, r12d
0x180044ec9  cmp     esi, eax
0x180044ecb  jge     short loc_180044F21
0x180044ecd  test    ebx, ebx
0x180044ecf  js      short loc_180044F21
0x180044ed1  cmp     [rsp+1A0h+var_170], r13d
0x180044ed6  jz      short loc_180044F21
0x180044ed8  movsxd  rdx, esi; i
0x180044edb  call    cs:__imp_DPA_GetPtr
0x180044ee1  lea     r8, [rsp+1A0h+var_16C]
0x180044ee6  mov     [rsp+1A0h+var_16C], r12d
0x180044eeb  mov     rcx, rax
0x180044eee  lea     rdx, aEs; "ES"
0x180044ef5  mov     r14, rax
0x180044ef8  call    GetEvalStateEx
0x180044efd  mov     ebx, eax
0x180044eff  test    eax, eax
0x180044f01  js      short loc_180044F1C
0x180044f03  cmp     [rsp+1A0h+var_16C], r12d
0x180044f08  jnz     short loc_180044F1C
0x180044f0a  lea     r8, [rsp+1A0h+var_170]; enum TRIBIT *
0x180044f0f  mov     rdx, r14; struct ICondition *
0x180044f12  mov     rcx, rdi; this
0x180044f15  call    ?EvalValueChunk@CGrepConditionEvaluator@@AEAAJPEAUICondition@@PEAW4TRIBIT@@@Z; CGrepConditionEvaluator::EvalValueChunk(ICondition *,TRIBIT *)
0x180044f1a  mov     ebx, eax
0x180044f1c  add     esi, r13d
0x180044f1f  jmp     short loc_180044EB9
0x180044f21  mov     rcx, [rdi+0C8h]; pvar
0x180044f28  call    cs:__imp_PropVariantClear
0x180044f2e  mov     rcx, [rdi+0C8h]; pv
0x180044f35  call    cs:__imp_CoTaskMemFree
0x180044f3b  mov     [rdi+0C8h], r12
0x180044f42  test    ebx, ebx
0x180044f44  jz      loc_180044DFD
0x180044f4a  mov     eax, [rsp+1A0h+var_170]
0x180044f4e  mov     rcx, [rbp+0A0h+ppv]
0x180044f52  mov     [r15], eax
0x180044f55  mov     rax, [rcx]
0x180044f58  mov     rax, [rax+10h]
0x180044f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f61  lea     rcx, [rsp+1A0h+var_160]; this
0x180044f66  call    ??1CGrep@@QEAA@XZ; CGrep::~CGrep(void)
0x180044f6b  test    cs:byte_1800AA742, 20h
0x180044f72  jz      short loc_180044F93
0x180044f74  lea     rax, [rbp+0A0h+ppv]
0x180044f78  mov     r9d, r13d
0x180044f7b  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop
0x180044f82  mov     [rsp+1A0h+var_180], rax
0x180044f87  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180044f8e  call    McGenEventWrite_EventWriteTransfer
0x180044f93  mov     eax, ebx
0x180044f95  mov     rcx, [rbp+0A0h+var_40]
0x180044f99  xor     rcx, rsp; StackCookie
0x180044f9c  call    __security_check_cookie
0x180044fa1  mov     rbx, [rsp+1A0h+arg_10]
0x180044fa9  add     rsp, 170h
0x180044fb0  pop     r15
0x180044fb2  pop     r14
0x180044fb4  pop     r13
0x180044fb6  pop     r12
0x180044fb8  pop     rdi
0x180044fb9  pop     rsi
0x180044fba  pop     rbp
0x180044fbb  retn
```

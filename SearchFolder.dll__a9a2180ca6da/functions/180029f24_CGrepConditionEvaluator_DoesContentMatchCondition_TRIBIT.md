# CGrepConditionEvaluator::DoesContentMatchCondition(TRIBIT *)

- ea: `0x180029f24`
- end: `0x18002a1d8`
- name: `?DoesContentMatchCondition@CGrepConditionEvaluator@@QEAAJPEAW4TRIBIT@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(CGrepConditionEvaluator *__hidden this, enum TRIBIT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d230`

## callees

- `0x180003790`
- `0x180006900`
- `0x1800076dc`
- `0x180021ca4`
- `0x180021e64`
- `0x180027cc4`
- `0x180029f24`
- `0x18002a290`
- `0x18002d3c0`
- `0x180036008`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180029fb3`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180029fb3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a14c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a159`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180029f9b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180029f9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGrepConditionEvaluator::DoesContentMatchCondition(
        CGrepConditionEvaluator *this,
        enum TRIBIT *a2,
        int a3,
        int a4)
{
  int v6; // ecx
  HRESULT inited; // ebx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rsi
  __int64 v11; // rcx
  int i; // esi
  struct _DPA *v13; // rcx
  int v14; // eax
  struct ICondition *Ptr; // r14
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v18[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v19[17]; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+C8h] [rbp-38h]
  __int64 v21; // [rsp+D0h] [rbp-30h]
  __int64 v22; // [rsp+D8h] [rbp-28h]
  __int64 v23; // [rsp+E0h] [rbp-20h]
  __int64 v24; // [rsp+E8h] [rbp-18h]
  __int64 v25; // [rsp+F0h] [rbp-10h]
  void *ppv[2]; // [rsp+150h] [rbp+50h] BYREF

  if ( (byte_180069A02 & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start,
      a3,
      a4,
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
      v17 = 0;
      v10 = *((_QWORD *)this + 23);
      v19[0] = *((_QWORD *)this + 13);
      v19[1] = v10;
      v19[8] = 0;
      v20 = 1;
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 8LL))(v19[0]);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
LABEL_36:
      if ( !inited )
      {
        while ( v17 != 1 )
        {
          v11 = *((_QWORD *)this + 23);
          if ( v11 )
            inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
          if ( inited )
            break;
          do
          {
            memset_0((char *)this + 112, 0, 0x40u);
            inited = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 32LL))(
                       *((_QWORD *)this + 13),
                       (char *)this + 112);
          }
          while ( !inited && (*((_DWORD *)this + 30) & 3) == 0 );
          if ( (unsigned int)(inited + 2147215609) <= 1 || inited == -2147215616 || inited == 268036 )
          {
            inited = 1;
          }
          else
          {
            if ( inited )
              break;
            ++*((_DWORD *)this + 44);
          }
          if ( inited )
            break;
          if ( (*((_BYTE *)this + 120) & 1) != 0 )
          {
            inited = CGrep::GrepText(
                       (CGrep *)v19,
                       (const struct tagSTAT_CHUNK *)((char *)this + 112),
                       this,
                       (enum TRIBIT *)&v17);
            goto LABEL_36;
          }
          if ( (*((_BYTE *)this + 120) & 2) != 0 )
          {
            for ( i = 0; ; ++i )
            {
              v13 = (struct _DPA *)*((_QWORD *)this + 10);
              v14 = v13 ? *(_DWORD *)v13 : 0;
              if ( i >= v14 || inited < 0 || v17 == 1 )
                break;
              Ptr = (struct ICondition *)g_pfn_DPA_GetPtr(v13, i);
              v18[0] = 0;
              inited = GetEvalStateEx(Ptr, L"ES", v18);
              if ( inited >= 0 && !v18[0] )
                inited = CGrepConditionEvaluator::EvalValueChunk(this, Ptr, (enum TRIBIT *)&v17);
            }
            PropVariantClear(*((PROPVARIANT **)this + 25));
            CoTaskMemFree(*((LPVOID *)this + 25));
            *((_QWORD *)this + 25) = 0;
            goto LABEL_36;
          }
        }
      }
      *(_DWORD *)a2 = v17;
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      CGrep::~CGrep((CGrep *)v19);
    }
  }
  if ( (byte_180069A02 & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v6,
      (unsigned int)ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop,
      v8,
      v9,
      (__int64)ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180029f24  mov     [rsp-8+arg_10], rbx
0x180029f29  mov     [rsp-8+arg_18], rsi
0x180029f2e  push    rbp
0x180029f2f  push    rdi
0x180029f30  push    r12
0x180029f32  push    r14
0x180029f34  push    r15
0x180029f36  lea     rbp, [rsp-70h]
0x180029f3b  sub     rsp, 170h
0x180029f42  mov     rax, cs:__security_cookie
0x180029f49  xor     rax, rsp
0x180029f4c  mov     [rbp+90h+var_30], rax
0x180029f50  mov     r15, rdx
0x180029f53  mov     rdi, rcx
0x180029f56  test    cs:byte_180069A02, 20h
0x180029f5d  jz      short loc_180029F74
0x180029f5f  lea     rax, [rbp+90h+ppv]
0x180029f63  mov     [rsp+190h+var_170], rax
0x180029f68  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start
0x180029f6f  call    McGenEventWrite_EtwEventWriteTransfer
0x180029f74  xor     r12d, r12d
0x180029f77  mov     [r15], r12d
0x180029f7a  mov     rcx, rdi; this
0x180029f7d  call    ?_InitFilter@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_InitFilter(void)
0x180029f82  mov     ebx, eax
0x180029f84  test    eax, eax
0x180029f86  jnz     loc_18002A190
0x180029f8c  mov     [rbp+90h+ppv], r12
0x180029f90  lea     rdx, [rbp+90h+ppv]; ppv
0x180029f94  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180029f9b  call    cs:__imp_PSCreateMemoryPropertyStore
0x180029fa1  mov     ebx, eax
0x180029fa3  test    eax, eax
0x180029fa5  js      loc_18002A190
0x180029fab  lea     rcx, [rdi+8]; ppunk
0x180029faf  mov     rdx, [rbp+90h+ppv]; punk
0x180029fb3  call    cs:__imp_IUnknown_Set
0x180029fb9  mov     [rsp+190h+var_160], r12d
0x180029fbe  mov     rsi, [rdi+0B8h]
0x180029fc5  mov     rcx, [rdi+68h]
0x180029fc9  mov     [rsp+190h+var_150], rcx
0x180029fce  mov     [rsp+190h+var_148], rsi
0x180029fd3  mov     [rbp+90h+var_110], r12
0x180029fd7  mov     [rbp+90h+var_C8], 1
0x180029fde  mov     [rbp+90h+var_C0], r12
0x180029fe2  mov     [rbp+90h+var_B8], r12
0x180029fe6  mov     [rbp+90h+var_B0], r12
0x180029fea  mov     [rbp+90h+var_A8], r12
0x180029fee  mov     [rbp+90h+var_A0], r12
0x180029ff2  mov     rax, [rcx]
0x180029ff5  mov     rax, [rax+8]
0x180029ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ffe  test    rsi, rsi
0x18002a001  jz      short loc_18002A013
0x18002a003  mov     rax, [rsi]
0x18002a006  mov     rcx, rsi
0x18002a009  mov     rax, [rax+8]
0x18002a00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a012  nop
0x18002a013  jmp     loc_18002A166
0x18002a018  cmp     [rsp+190h+var_160], 1
0x18002a01d  jz      loc_18002A16E
0x18002a023  mov     rcx, [rdi+0B8h]
0x18002a02a  test    rcx, rcx
0x18002a02d  jz      short loc_18002A03D
0x18002a02f  mov     rax, [rcx]
0x18002a032  mov     rax, [rax+18h]
0x18002a036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a03b  mov     ebx, eax
0x18002a03d  test    ebx, ebx
0x18002a03f  jnz     loc_18002A16E
0x18002a045  lea     rsi, [rdi+70h]
0x18002a049  xor     edx, edx; Val
0x18002a04b  lea     r8d, [rdx+40h]; Size
0x18002a04f  mov     rcx, rsi; void *
0x18002a052  call    memset_0
0x18002a057  mov     rcx, [rdi+68h]
0x18002a05b  mov     rax, [rcx]
0x18002a05e  mov     rdx, rsi
0x18002a061  mov     rax, [rax+20h]
0x18002a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a06a  mov     ebx, eax
0x18002a06c  test    eax, eax
0x18002a06e  jnz     short loc_18002A077
0x18002a070  mov     eax, [rdi+78h]
0x18002a073  test    al, 3
0x18002a075  jz      short loc_18002A049
0x18002a077  lea     eax, [rbx+7FFBE8F9h]
0x18002a07d  cmp     eax, 1
0x18002a080  jbe     short loc_18002A0A2
0x18002a082  cmp     ebx, 80041700h
0x18002a088  jz      short loc_18002A0A2
0x18002a08a  cmp     ebx, 41704h
0x18002a090  jz      short loc_18002A0A2
0x18002a092  test    ebx, ebx
0x18002a094  jnz     loc_18002A16E
0x18002a09a  inc     dword ptr [rdi+0B0h]
0x18002a0a0  jmp     short loc_18002A0A7
0x18002a0a2  mov     ebx, 1
0x18002a0a7  test    ebx, ebx
0x18002a0a9  jnz     loc_18002A16E
0x18002a0af  test    byte ptr [rsi+8], 1
0x18002a0b3  jz      short loc_18002A0D1
0x18002a0b5  lea     r9, [rsp+190h+var_160]; enum TRIBIT *
0x18002a0ba  mov     r8, rdi; struct CConditionEvaluator *
0x18002a0bd  mov     rdx, rsi; struct tagSTAT_CHUNK *
0x18002a0c0  lea     rcx, [rsp+190h+var_150]; this
0x18002a0c5  call    ?GrepText@CGrep@@QEAAJAEBUtagSTAT_CHUNK@@PEAVCConditionEvaluator@@PEAW4TRIBIT@@@Z; CGrep::GrepText(tagSTAT_CHUNK const &,CConditionEvaluator *,TRIBIT *)
0x18002a0ca  mov     ebx, eax
0x18002a0cc  jmp     loc_18002A166
0x18002a0d1  test    byte ptr [rsi+8], 2
0x18002a0d5  jz      loc_18002A018
0x18002a0db  mov     esi, r12d
0x18002a0de  mov     rcx, [rdi+50h]; hdpa
0x18002a0e2  test    rcx, rcx
0x18002a0e5  jz      short loc_18002A0EB
0x18002a0e7  mov     eax, [rcx]
0x18002a0e9  jmp     short loc_18002A0EE
0x18002a0eb  mov     eax, r12d
0x18002a0ee  cmp     esi, eax
0x18002a0f0  jge     short loc_18002A145
0x18002a0f2  test    ebx, ebx
0x18002a0f4  js      short loc_18002A145
0x18002a0f6  cmp     [rsp+190h+var_160], 1
0x18002a0fb  jz      short loc_18002A145
0x18002a0fd  movsxd  rdx, esi; i
0x18002a100  call    cs:g_pfn_DPA_GetPtr
0x18002a106  mov     r14, rax
0x18002a109  mov     [rsp+190h+var_15C], r12d
0x18002a10e  lea     r8, [rsp+190h+var_15C]
0x18002a113  lea     rdx, aEs; "ES"
0x18002a11a  mov     rcx, rax
0x18002a11d  call    GetEvalStateEx
0x18002a122  mov     ebx, eax
0x18002a124  test    eax, eax
0x18002a126  js      short loc_18002A141
0x18002a128  cmp     [rsp+190h+var_15C], r12d
0x18002a12d  jnz     short loc_18002A141
0x18002a12f  lea     r8, [rsp+190h+var_160]; enum TRIBIT *
0x18002a134  mov     rdx, r14; struct ICondition *
0x18002a137  mov     rcx, rdi; this
0x18002a13a  call    ?EvalValueChunk@CGrepConditionEvaluator@@AEAAJPEAUICondition@@PEAW4TRIBIT@@@Z; CGrepConditionEvaluator::EvalValueChunk(ICondition *,TRIBIT *)
0x18002a13f  mov     ebx, eax
0x18002a141  inc     esi
0x18002a143  jmp     short loc_18002A0DE
0x18002a145  mov     rcx, [rdi+0C8h]; pvar
0x18002a14c  call    cs:__imp_PropVariantClear
0x18002a152  mov     rcx, [rdi+0C8h]; pv
0x18002a159  call    cs:__imp_CoTaskMemFree
0x18002a15f  mov     [rdi+0C8h], r12
0x18002a166  test    ebx, ebx
0x18002a168  jz      loc_18002A018
0x18002a16e  mov     eax, [rsp+190h+var_160]
0x18002a172  mov     [r15], eax
0x18002a175  mov     rcx, [rbp+90h+ppv]
0x18002a179  mov     rax, [rcx]
0x18002a17c  mov     rax, [rax+10h]
0x18002a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a185  nop
0x18002a186  lea     rcx, [rsp+190h+var_150]; this
0x18002a18b  call    ??1CGrep@@QEAA@XZ; CGrep::~CGrep(void)
0x18002a190  test    cs:byte_180069A02, 20h
0x18002a197  jz      short loc_18002A1AE
0x18002a199  lea     rax, [rbp+90h+ppv]
0x18002a19d  mov     [rsp+190h+var_170], rax
0x18002a1a2  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop
0x18002a1a9  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a1ae  mov     eax, ebx
0x18002a1b0  mov     rcx, [rbp+90h+var_30]
0x18002a1b4  xor     rcx, rsp; StackCookie
0x18002a1b7  call    __security_check_cookie
0x18002a1bc  lea     r11, [rsp+190h+var_20]
0x18002a1c4  mov     rbx, [r11+40h]
0x18002a1c8  mov     rsi, [r11+48h]
0x18002a1cc  mov     rsp, r11
0x18002a1cf  pop     r15
0x18002a1d1  pop     r14
0x18002a1d3  pop     r12
0x18002a1d5  pop     rdi
0x18002a1d6  pop     rbp
0x18002a1d7  retn
```

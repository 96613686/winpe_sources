# Projection::ObjectAsIPropertyValue::GetUInt32Array(uint *,uint * *)

- ea: `0x1802336d0`
- end: `0x180233958`
- name: `?GetUInt32Array@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAI@Z`
- size: `648`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, unsigned int **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180233960`

## callees

- `0x180024810`
- `0x180024b80`
- `0x180024cd0`
- `0x1800257dc`
- `0x180026f10`
- `0x18002bde8`
- `0x18002c348`
- `0x180130b04`
- `0x180146f40`
- `0x1801c8120`
- `0x1801c8178`
- `0x180230340`
- `0x1802336d0`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180233701`
- `KERNEL32!GetCurrentThreadId` at `0x180233701`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233892`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233892`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetUInt32Array(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        unsigned int **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  unsigned __int64 v11; // rdx
  unsigned __int8 *v12; // rbx
  unsigned int *v13; // rax
  __int64 i; // r8
  struct Js::RecyclableObject *v15; // rbx
  unsigned __int64 v16; // [rsp+28h] [rbp-E0h]
  int Value; // [rsp+40h] [rbp-C8h]
  ScriptSite *v18; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v19; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v20[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+80h] [rbp-88h]
  _BYTE v22[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v23[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v24[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  v18 = (ScriptSite *)v5;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v24, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v23,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v20, 0, sizeof(v20));
    v21 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v22,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v20,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v7 = *((_QWORD *)this + 11);
      if ( *(_BYTE *)(v7 + 88) && (v8 = *(_QWORD *)(v7 + 112), **(_DWORD **)(v8 + 8) == 12) )
      {
        v9 = *(unsigned int *)(v8 + 16);
        v10 = (unsigned __int8 *)operator new[](saturated_mul(v9, 4u));
        v12 = v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    v10,
                    0,
                    0,
                    v16,
                    0);
          if ( Value >= 0 )
          {
            v13 = (unsigned int *)CoTaskMemAlloc(4 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = *(_DWORD *)&v12[4 * i];
              *a2 = v9;
            }
            else
            {
              Value = -2147024882;
            }
          }
          operator delete[](v12);
        }
        else
        {
          Value = -2147024882;
        }
      }
      else
      {
        Value = -2147316576;
      }
    }
    else
    {
      Value = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v22);
  }
  catch ( Js::JavascriptExceptionObject *v19 )
  {
    v15 = *v19;
    if ( *v19
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v19) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v15) == 11) )
    {
      Value = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v15, 0);
      if ( Js::JavascriptErrorDebug::Is(v15) )
        Js::JavascriptErrorDebug::SetErrorInfo(v15);
    }
    else
    {
      Value = -2147467259;
    }
  }
  catch ( Js::InternalErrorException )
  {
    Value = -2147467259;
  }
  catch ( Js::OutOfMemoryException )
  {
    Value = -2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    Value = -2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    Value = -2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    Value = -2147467260;
  }
  catch ( ... )
  {
    Value = -2147467259;
  }
  ScriptSite::Release(v18);
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v23);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v24);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1802336d0  mov     rax, rsp
0x1802336d3  mov     [rax+18h], r8
0x1802336d7  mov     [rax+10h], rdx
0x1802336db  mov     [rax+8], rcx
0x1802336df  push    rsi
0x1802336e0  push    rdi
0x1802336e1  push    r12
0x1802336e3  push    r14
0x1802336e5  push    r15
0x1802336e7  sub     rsp, 0E0h
0x1802336ee  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1802336f7  mov     [rax+20h], rbx
0x1802336fb  mov     rax, rcx
0x1802336fe  mov     ebx, [rcx+48h]
0x180233701  call    cs:__imp_GetCurrentThreadId
0x180233707  cmp     ebx, eax
0x180233709  jz      short loc_180233715
0x18023370b  mov     eax, 8001010Eh
0x180233710  jmp     loc_180233940
0x180233715  mov     rax, [rsp+108h+arg_0]
0x18023371d  mov     rbx, [rax+20h]
0x180233721  test    rbx, rbx
0x180233724  jnz     short loc_180233730
0x180233726  mov     eax, 80070005h
0x18023372b  jmp     loc_180233940
0x180233730  lock inc dword ptr [rbx]
0x180233733  mov     rax, [rsp+108h+arg_0]
0x18023373b  mov     rcx, [rax+28h]
0x18023373f  mov     rdi, [rcx+70h]
0x180233743  mov     edx, 450h; unsigned __int64
0x180233748  mov     rcx, [rdi+4A0h]; this
0x18023374f  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180233754  test    al, al
0x180233756  jnz     short loc_180233762
0x180233758  mov     eax, 800703E9h
0x18023375d  jmp     loc_180233940
0x180233762  mov     [rsp+108h+var_C0], rbx
0x180233767  mov     r15, [rsp+108h+arg_0]
0x18023376f  mov     rcx, r15; this
0x180233772  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180233777  xor     r8d, r8d; struct IUnknown *
0x18023377a  mov     rdx, rbx; struct ScriptSite *
0x18023377d  lea     rcx, [rsp+108h+var_50]; this
0x180233785  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x18023378a  nop
0x18023378b  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x180233792  mov     rdx, rbx; struct ScriptSite *
0x180233795  lea     rcx, [rsp+108h+var_68]; this
0x18023379d  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802337a2  nop
0x1802337a3  xorps   xmm0, xmm0
0x1802337a6  xor     eax, eax
0x1802337a8  movups  [rsp+108h+var_A8], xmm0
0x1802337ad  movups  [rsp+108h+var_98], xmm0
0x1802337b2  mov     [rsp+108h+var_88], rax
0x1802337ba  mov     r9, [rsp+108h]; void *
0x1802337c2  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802337c6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802337cb  mov     [rsp+108h+var_E8], 1; bool
0x1802337d0  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802337d5  mov     rdx, rdi; struct Js::ScriptContext *
0x1802337d8  lea     rcx, [rsp+108h+var_80]; this
0x1802337e0  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x1802337e5  nop
0x1802337e6  mov     r9b, 1; bool
0x1802337e9  mov     r8b, [rdi+0C40h]; bool
0x1802337f0  mov     dl, r9b; bool
0x1802337f3  mov     rcx, rdi; this
0x1802337f6  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x1802337fb  mov     rdi, [rsp+108h+arg_10]
0x180233803  test    rdi, rdi
0x180233806  jz      loc_1802338E5
0x18023380c  mov     r14, [rsp+108h+arg_8]
0x180233814  test    r14, r14
0x180233817  jz      loc_1802338E5
0x18023381d  mov     rax, [r15+58h]
0x180233821  cmp     byte ptr [rax+58h], 0
0x180233825  jz      loc_1802338DB
0x18023382b  mov     rcx, [rax+70h]
0x18023382f  mov     rax, [rcx+8]
0x180233833  cmp     dword ptr [rax], 0Ch
0x180233836  jnz     loc_1802338DB
0x18023383c  mov     esi, [rcx+10h]
0x18023383f  mov     eax, 4
0x180233844  mul     rsi
0x180233847  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18023384e  cmovb   rax, rcx
0x180233852  mov     rcx, rax; unsigned __int64
0x180233855  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18023385a  mov     rbx, rax
0x18023385d  test    rax, rax
0x180233860  jz      short loc_1802338D1
0x180233862  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x18023386b  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180233873  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180233876  mov     r8, rax; unsigned __int8 *
0x180233879  mov     rcx, [r15+58h]; this
0x18023387d  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x180233882  mov     [rsp+108h+var_C8], eax
0x180233886  test    eax, eax
0x180233888  js      short loc_1802338C7
0x18023388a  lea     rcx, ds:0[rsi*4]; cb
0x180233892  call    cs:__imp_CoTaskMemAlloc
0x180233898  mov     [rdi], rax
0x18023389b  test    rax, rax
0x18023389e  jz      short loc_1802338BF
0x1802338a0  xor     r8d, r8d
0x1802338a3  test    esi, esi
0x1802338a5  jz      short loc_1802338BA
0x1802338a7  mov     rcx, [rdi]
0x1802338aa  mov     eax, [rbx+r8*4]
0x1802338ae  mov     [rcx+r8*4], eax
0x1802338b2  inc     r8d
0x1802338b5  cmp     r8d, esi
0x1802338b8  jb      short loc_1802338A7
0x1802338ba  mov     [r14], esi
0x1802338bd  jmp     short loc_1802338C7
0x1802338bf  mov     [rsp+108h+var_C8], 8007000Eh
0x1802338c7  mov     rcx, rbx; void *
0x1802338ca  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1802338cf  jmp     short loc_1802338ED
0x1802338d1  mov     [rsp+108h+var_C8], 8007000Eh
0x1802338d9  jmp     short loc_1802338ED
0x1802338db  mov     [rsp+108h+var_C8], 80028CA0h
0x1802338e3  jmp     short loc_1802338ED
0x1802338e5  mov     [rsp+108h+var_C8], 80004003h
0x1802338ed  lea     rcx, [rsp+108h+var_80]; this
0x1802338f5  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802338fa  nop
0x1802338fb  jmp     short loc_180233909
0x1802338fd  jmp     short loc_180233909
0x1802338ff  jmp     short loc_180233909
0x180233901  jmp     short loc_180233909
0x180233903  jmp     short loc_180233909
0x180233905  jmp     short loc_180233909
0x180233907  jmp     short $+2
0x180233909  mov     rcx, [rsp+108h+var_C0]; this
0x18023390e  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180233913  mov     rcx, [rsp+108h+arg_0]; this
0x18023391b  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180233920  nop
0x180233921  lea     rcx, [rsp+108h+var_68]; this
0x180233929  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x18023392e  nop
0x18023392f  lea     rcx, [rsp+108h+var_50]; this
0x180233937  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x18023393c  mov     eax, [rsp+108h+var_C8]
0x180233940  mov     rbx, [rsp+108h+arg_18]
0x180233948  add     rsp, 0E0h
0x18023394f  pop     r15
0x180233951  pop     r14
0x180233953  pop     r12
0x180233955  pop     rdi
0x180233956  pop     rsi
0x180233957  retn
```

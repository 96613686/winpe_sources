# Projection::ObjectAsIPropertyValue::GetSingleArray(uint *,float * *)

- ea: `0x180232810`
- end: `0x180232a9a`
- name: `?GetSingleArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAM@Z`
- size: `650`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, float **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x180232aa0`

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
- `0x180232810`
- `0x180233f50`
- `0x180234b74`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180232841`
- `KERNEL32!GetCurrentThreadId` at `0x180232841`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802329d2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802329d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetSingleArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        float **a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  unsigned __int8 *v10; // rax
  unsigned __int64 v11; // rdx
  int *v12; // rbx
  float *v13; // rax
  __int64 i; // rdx
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
        v12 = (int *)v10;
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
            v13 = (float *)CoTaskMemAlloc(4 * v9);
            *a3 = v13;
            if ( v13 )
            {
              for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
                (*a3)[i] = (float)v12[i];
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
0x180232810  mov     rax, rsp
0x180232813  mov     [rax+18h], r8
0x180232817  mov     [rax+10h], rdx
0x18023281b  mov     [rax+8], rcx
0x18023281f  push    rsi
0x180232820  push    rdi
0x180232821  push    r12
0x180232823  push    r14
0x180232825  push    r15
0x180232827  sub     rsp, 0E0h
0x18023282e  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180232837  mov     [rax+20h], rbx
0x18023283b  mov     rax, rcx
0x18023283e  mov     ebx, [rcx+48h]
0x180232841  call    cs:__imp_GetCurrentThreadId
0x180232847  cmp     ebx, eax
0x180232849  jz      short loc_180232855
0x18023284b  mov     eax, 8001010Eh
0x180232850  jmp     loc_180232A82
0x180232855  mov     rax, [rsp+108h+arg_0]
0x18023285d  mov     rbx, [rax+20h]
0x180232861  test    rbx, rbx
0x180232864  jnz     short loc_180232870
0x180232866  mov     eax, 80070005h
0x18023286b  jmp     loc_180232A82
0x180232870  lock inc dword ptr [rbx]
0x180232873  mov     rax, [rsp+108h+arg_0]
0x18023287b  mov     rcx, [rax+28h]
0x18023287f  mov     rdi, [rcx+70h]
0x180232883  mov     edx, 450h; unsigned __int64
0x180232888  mov     rcx, [rdi+4A0h]; this
0x18023288f  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180232894  test    al, al
0x180232896  jnz     short loc_1802328A2
0x180232898  mov     eax, 800703E9h
0x18023289d  jmp     loc_180232A82
0x1802328a2  mov     [rsp+108h+var_C0], rbx
0x1802328a7  mov     r15, [rsp+108h+arg_0]
0x1802328af  mov     rcx, r15; this
0x1802328b2  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x1802328b7  xor     r8d, r8d; struct IUnknown *
0x1802328ba  mov     rdx, rbx; struct ScriptSite *
0x1802328bd  lea     rcx, [rsp+108h+var_50]; this
0x1802328c5  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802328ca  nop
0x1802328cb  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802328d2  mov     rdx, rbx; struct ScriptSite *
0x1802328d5  lea     rcx, [rsp+108h+var_68]; this
0x1802328dd  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802328e2  nop
0x1802328e3  xorps   xmm0, xmm0
0x1802328e6  xor     eax, eax
0x1802328e8  movups  [rsp+108h+var_A8], xmm0
0x1802328ed  movups  [rsp+108h+var_98], xmm0
0x1802328f2  mov     [rsp+108h+var_88], rax
0x1802328fa  mov     r9, [rsp+108h]; void *
0x180232902  mov     byte ptr [rsp+108h+var_D8], al; bool
0x180232906  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x18023290b  mov     [rsp+108h+var_E8], 1; bool
0x180232910  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x180232915  mov     rdx, rdi; struct Js::ScriptContext *
0x180232918  lea     rcx, [rsp+108h+var_80]; this
0x180232920  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180232925  nop
0x180232926  mov     r9b, 1; bool
0x180232929  mov     r8b, [rdi+0C40h]; bool
0x180232930  mov     dl, r9b; bool
0x180232933  mov     rcx, rdi; this
0x180232936  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x18023293b  mov     rdi, [rsp+108h+arg_10]
0x180232943  test    rdi, rdi
0x180232946  jz      loc_180232A27
0x18023294c  mov     r14, [rsp+108h+arg_8]
0x180232954  test    r14, r14
0x180232957  jz      loc_180232A27
0x18023295d  mov     rax, [r15+58h]
0x180232961  cmp     byte ptr [rax+58h], 0
0x180232965  jz      loc_180232A1D
0x18023296b  mov     rcx, [rax+70h]
0x18023296f  mov     rax, [rcx+8]
0x180232973  cmp     dword ptr [rax], 0Ch
0x180232976  jnz     loc_180232A1D
0x18023297c  mov     esi, [rcx+10h]
0x18023297f  mov     eax, 4
0x180232984  mul     rsi
0x180232987  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18023298e  cmovb   rax, rcx
0x180232992  mov     rcx, rax; unsigned __int64
0x180232995  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18023299a  mov     rbx, rax
0x18023299d  test    rax, rax
0x1802329a0  jz      short loc_180232A13
0x1802329a2  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x1802329ab  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x1802329b3  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x1802329b6  mov     r8, rax; unsigned __int8 *
0x1802329b9  mov     rcx, [r15+58h]; this
0x1802329bd  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802329c2  mov     [rsp+108h+var_C8], eax
0x1802329c6  test    eax, eax
0x1802329c8  js      short loc_180232A09
0x1802329ca  lea     rcx, ds:0[rsi*4]; cb
0x1802329d2  call    cs:__imp_CoTaskMemAlloc
0x1802329d8  mov     [rdi], rax
0x1802329db  test    rax, rax
0x1802329de  jz      short loc_180232A01
0x1802329e0  xor     edx, edx
0x1802329e2  test    esi, esi
0x1802329e4  jz      short loc_1802329FC
0x1802329e6  movd    xmm0, dword ptr [rbx+rdx*4]
0x1802329eb  cvtdq2ps xmm0, xmm0
0x1802329ee  mov     rax, [rdi]
0x1802329f1  movss   dword ptr [rax+rdx*4], xmm0
0x1802329f6  inc     edx
0x1802329f8  cmp     edx, esi
0x1802329fa  jb      short loc_1802329E6
0x1802329fc  mov     [r14], esi
0x1802329ff  jmp     short loc_180232A09
0x180232a01  mov     [rsp+108h+var_C8], 8007000Eh
0x180232a09  mov     rcx, rbx; void *
0x180232a0c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180232a11  jmp     short loc_180232A2F
0x180232a13  mov     [rsp+108h+var_C8], 8007000Eh
0x180232a1b  jmp     short loc_180232A2F
0x180232a1d  mov     [rsp+108h+var_C8], 80028CA0h
0x180232a25  jmp     short loc_180232A2F
0x180232a27  mov     [rsp+108h+var_C8], 80004003h
0x180232a2f  lea     rcx, [rsp+108h+var_80]; this
0x180232a37  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x180232a3c  nop
0x180232a3d  jmp     short loc_180232A4B
0x180232a3f  jmp     short loc_180232A4B
0x180232a41  jmp     short loc_180232A4B
0x180232a43  jmp     short loc_180232A4B
0x180232a45  jmp     short loc_180232A4B
0x180232a47  jmp     short loc_180232A4B
0x180232a49  jmp     short $+2
0x180232a4b  mov     rcx, [rsp+108h+var_C0]; this
0x180232a50  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x180232a55  mov     rcx, [rsp+108h+arg_0]; this
0x180232a5d  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180232a62  nop
0x180232a63  lea     rcx, [rsp+108h+var_68]; this
0x180232a6b  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180232a70  nop
0x180232a71  lea     rcx, [rsp+108h+var_50]; this
0x180232a79  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180232a7e  mov     eax, [rsp+108h+var_C8]
0x180232a82  mov     rbx, [rsp+108h+arg_18]
0x180232a8a  add     rsp, 0E0h
0x180232a91  pop     r15
0x180232a93  pop     r14
0x180232a95  pop     r12
0x180232a97  pop     rdi
0x180232a98  pop     rsi
0x180232a99  retn
```

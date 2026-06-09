# Projection::ObjectAsIPropertyValue::GetTimeSpanArray(uint *,Windows::Foundation::TimeSpan * *)

- ea: `0x1802331f0`
- end: `0x180233438`
- name: `?GetTimeSpanArray@ObjectAsIPropertyValue@Projection@@UEAAJPEAIPEAPEAUTimeSpan@Foundation@Windows@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(Projection::ObjectAsIPropertyValue *__hidden this, unsigned int *, struct Windows::Foundation::TimeSpan **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x180233440`

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
- `0x180230340`
- `0x1802331f0`
- `0x180233f50`
- `0x18023473c`
- `0x180234b74`
- `0x180341b99`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18023321c`
- `KERNEL32!GetCurrentThreadId` at `0x18023321c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233372`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180233372`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802333ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1802333ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Projection::ObjectAsIPropertyValue::GetTimeSpanArray(
        Projection::ObjectAsIPropertyValue *this,
        unsigned int *a2,
        LPVOID *a3)
{
  int v3; // ebx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdi
  Projection::ObjectAsIReference *v7; // rcx
  const wchar_t *FullElementTypeName; // rax
  unsigned int v9; // r14d
  struct Windows::Foundation::TimeSpan *v10; // rax
  unsigned __int64 v11; // rdx
  int Value; // edi
  struct Js::RecyclableObject *v13; // rbx
  unsigned __int64 v14; // [rsp+28h] [rbp-E0h]
  unsigned int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-C8h]
  ScriptSite *v16; // [rsp+48h] [rbp-C0h]
  struct Js::RecyclableObject **v17; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+80h] [rbp-88h]
  _BYTE v20[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v21[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v22[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v3 = *((_DWORD *)this + 18);
  if ( v3 != GetCurrentThreadId() )
    return 2147549454LL;
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  v16 = (ScriptSite *)v5;
  if ( !v5 )
    return 2147942405LL;
  _InterlockedIncrement(v5);
  v6 = *(_QWORD *)(*((_QWORD *)this + 5) + 112LL);
  if ( !ThreadContext::IsStackAvailableNoThrow(*(ThreadContext **)(v6 + 1184), 0x450u) )
    return 2147943401LL;
  Projection::ObjectAsIPropertyValue::AddRef(this);
  AutoCallerPointer::AutoCallerPointer((AutoCallerPointer *)v22, (struct ScriptSite *)v5, 0);
  AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(
    (AutoHostScriptContextStackPointer *)v21,
    (struct ScriptSite *)v5,
    *(struct HostScriptContext **)(v6 + 2680));
  try
  {
    memset(v18, 0, sizeof(v18));
    v19 = 0;
    Js::EnterScriptObject::EnterScriptObject(
      (Js::EnterScriptObject *)v20,
      (struct Js::ScriptContext *)v6,
      (struct Js::ScriptEntryExitRecord *)v18,
      retaddr,
      1,
      1,
      0);
    Js::ScriptContext::OnScriptStart((Js::ScriptContext *)v6, 1, *(_BYTE *)(v6 + 3136), 1);
    if ( a3 && a2 )
    {
      v7 = (Projection::ObjectAsIReference *)*((_QWORD *)this + 11);
      if ( *((_BYTE *)v7 + 88)
        && (FullElementTypeName = Projection::ObjectAsIReference::GetFullElementTypeName(v7),
            !wcscmp_0(FullElementTypeName, L"Windows.Foundation.TimeSpan")) )
      {
        v9 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 112LL) + 16LL);
        v10 = (struct Windows::Foundation::TimeSpan *)CoTaskMemAlloc(8LL * v9);
        *a3 = v10;
        if ( v10 )
        {
          Value = Projection::ObjectAsIReference::get_Value(
                    *((Projection::ObjectAsIReference **)this + 11),
                    v11,
                    (unsigned __int8 *)v10,
                    0,
                    0,
                    v14,
                    0);
          if ( Value < 0 )
            CoTaskMemFree(*a3);
          else
            *a2 = v9;
          RuntimeErrorWithScriptEnter = Value;
        }
        else
        {
          RuntimeErrorWithScriptEnter = -2147024882;
        }
      }
      else
      {
        RuntimeErrorWithScriptEnter = -2147316576;
      }
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467261;
    }
    Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v20);
  }
  catch ( Js::JavascriptExceptionObject *v17 )
  {
    v13 = *v17;
    if ( *v17
      && ((unsigned int)Js::JavascriptOperators::GetTypeId(*v17) == 23
       || (unsigned int)Js::JavascriptOperators::GetTypeId(v13) == 11) )
    {
      RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v13, 0);
      if ( Js::JavascriptErrorDebug::Is(v13) )
        Js::JavascriptErrorDebug::SetErrorInfo(v13);
    }
    else
    {
      RuntimeErrorWithScriptEnter = -2147467259;
    }
  }
  catch ( Js::InternalErrorException )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  catch ( Js::OutOfMemoryException )
  {
    RuntimeErrorWithScriptEnter = -2147024882;
  }
  catch ( Js::StackOverflowException )
  {
    RuntimeErrorWithScriptEnter = -2146828260;
  }
  catch ( Js::NotImplementedException )
  {
    RuntimeErrorWithScriptEnter = -2147467263;
  }
  catch ( Js::ScriptAbortException )
  {
    RuntimeErrorWithScriptEnter = -2147467260;
  }
  catch ( ... )
  {
    RuntimeErrorWithScriptEnter = -2147467259;
  }
  ScriptSite::Release(v16);
  Projection::ObjectAsIPropertyValue::Release(this);
  AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer((AutoHostScriptContextStackPointer *)v21);
  AutoCallerPointer::~AutoCallerPointer((AutoCallerPointer *)v22);
  return RuntimeErrorWithScriptEnter;
}

```

## disassembly

```asm
0x1802331f0  mov     rax, rsp
0x1802331f3  mov     [rax+18h], r8
0x1802331f7  mov     [rax+10h], rdx
0x1802331fb  mov     [rax+8], rcx
0x1802331ff  push    rbx
0x180233200  push    rsi
0x180233201  push    rdi
0x180233202  push    r14
0x180233204  push    r15
0x180233206  sub     rsp, 0E0h
0x18023320d  mov     [rsp+108h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180233216  mov     rax, rcx
0x180233219  mov     ebx, [rcx+48h]
0x18023321c  call    cs:__imp_GetCurrentThreadId
0x180233222  cmp     ebx, eax
0x180233224  jz      short loc_180233230
0x180233226  mov     eax, 8001010Eh
0x18023322b  jmp     loc_180233429
0x180233230  mov     rax, [rsp+108h+arg_0]
0x180233238  mov     rbx, [rax+20h]
0x18023323c  mov     [rsp+108h+var_C0], rbx
0x180233241  test    rbx, rbx
0x180233244  jnz     short loc_180233250
0x180233246  mov     eax, 80070005h
0x18023324b  jmp     loc_180233429
0x180233250  mov     rax, rbx
0x180233253  lock inc dword ptr [rax]
0x180233256  mov     rax, [rsp+108h+arg_0]
0x18023325e  mov     rcx, [rax+28h]
0x180233262  mov     rdi, [rcx+70h]
0x180233266  mov     edx, 450h; unsigned __int64
0x18023326b  mov     rcx, [rdi+4A0h]; this
0x180233272  call    ?IsStackAvailableNoThrow@ThreadContext@@QEAA_N_K@Z; ThreadContext::IsStackAvailableNoThrow(unsigned __int64)
0x180233277  test    al, al
0x180233279  jnz     short loc_180233285
0x18023327b  mov     eax, 800703E9h
0x180233280  jmp     loc_180233429
0x180233285  mov     r15, [rsp+108h+arg_0]
0x18023328d  mov     rcx, r15; this
0x180233290  call    ?AddRef@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::AddRef(void)
0x180233295  xor     r8d, r8d; struct IUnknown *
0x180233298  mov     rdx, rbx; struct ScriptSite *
0x18023329b  lea     rcx, [rsp+108h+var_50]; this
0x1802332a3  call    ??0AutoCallerPointer@@QEAA@PEAVScriptSite@@PEAUIUnknown@@@Z; AutoCallerPointer::AutoCallerPointer(ScriptSite *,IUnknown *)
0x1802332a8  nop
0x1802332a9  mov     r8, [rdi+0A78h]; struct HostScriptContext *
0x1802332b0  mov     rdx, [rsp+108h+var_C0]; struct ScriptSite *
0x1802332b5  lea     rcx, [rsp+108h+var_68]; this
0x1802332bd  call    ??0AutoHostScriptContextStackPointer@@QEAA@PEAVScriptSite@@PEAVHostScriptContext@@@Z; AutoHostScriptContextStackPointer::AutoHostScriptContextStackPointer(ScriptSite *,HostScriptContext *)
0x1802332c2  nop
0x1802332c3  xorps   xmm0, xmm0
0x1802332c6  xor     eax, eax
0x1802332c8  movups  [rsp+108h+var_A8], xmm0
0x1802332cd  movups  [rsp+108h+var_98], xmm0
0x1802332d2  mov     [rsp+108h+var_88], rax
0x1802332da  mov     r9, [rsp+108h]; void *
0x1802332e2  mov     byte ptr [rsp+108h+var_D8], al; bool
0x1802332e6  mov     byte ptr [rsp+108h+var_E0], 1; unsigned __int64
0x1802332eb  mov     [rsp+108h+var_E8], 1; bool
0x1802332f0  lea     r8, [rsp+108h+var_A8]; struct Js::ScriptEntryExitRecord *
0x1802332f5  mov     rdx, rdi; struct Js::ScriptContext *
0x1802332f8  lea     rcx, [rsp+108h+var_80]; this
0x180233300  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,bool,bool,bool)
0x180233305  nop
0x180233306  mov     r9b, 1; bool
0x180233309  mov     r8b, [rdi+0C40h]; bool
0x180233310  mov     dl, r9b; bool
0x180233313  mov     rcx, rdi; this
0x180233316  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N00@Z; Js::ScriptContext::OnScriptStart(bool,bool,bool)
0x18023331b  mov     rbx, [rsp+108h+arg_10]
0x180233323  test    rbx, rbx
0x180233326  jz      loc_1802333CE
0x18023332c  mov     rsi, [rsp+108h+arg_8]
0x180233334  test    rsi, rsi
0x180233337  jz      loc_1802333CE
0x18023333d  mov     rcx, [r15+58h]; this
0x180233341  cmp     byte ptr [rcx+58h], 0
0x180233345  jz      short loc_1802333C4
0x180233347  call    ?GetFullElementTypeName@ObjectAsIReference@Projection@@QEAAPEBGXZ; Projection::ObjectAsIReference::GetFullElementTypeName(void)
0x18023334c  lea     rdx, aWindowsFoundat_7; "Windows.Foundation.TimeSpan"
0x180233353  mov     rcx, rax; String1
0x180233356  call    wcscmp_0
0x18023335b  test    eax, eax
0x18023335d  jnz     short loc_1802333C4
0x18023335f  mov     rax, [r15+58h]
0x180233363  mov     rcx, [rax+70h]
0x180233367  mov     r14d, [rcx+10h]
0x18023336b  mov     ecx, r14d
0x18023336e  shl     rcx, 3; cb
0x180233372  call    cs:__imp_CoTaskMemAlloc
0x180233378  mov     [rbx], rax
0x18023337b  test    rax, rax
0x18023337e  jz      short loc_1802333BA
0x180233380  mov     [rsp+108h+var_D8], 0; unsigned __int8 *
0x180233389  mov     dword ptr [rsp+108h+var_E8], 0; unsigned int
0x180233391  xor     r9d, r9d; struct ProjectionModel::ConcreteType *
0x180233394  mov     r8, rax; unsigned __int8 *
0x180233397  mov     rcx, [r15+58h]; this
0x18023339b  call    ?get_Value@ObjectAsIReference@Projection@@QEAAJ_KPEAEPEBUConcreteType@ProjectionModel@@I01@Z; Projection::ObjectAsIReference::get_Value(unsigned __int64,uchar *,ProjectionModel::ConcreteType const *,uint,unsigned __int64,uchar *)
0x1802333a0  mov     edi, eax
0x1802333a2  test    eax, eax
0x1802333a4  js      short loc_1802333AB
0x1802333a6  mov     [rsi], r14d
0x1802333a9  jmp     short loc_1802333B4
0x1802333ab  mov     rcx, [rbx]; pv
0x1802333ae  call    cs:__imp_CoTaskMemFree
0x1802333b4  mov     [rsp+108h+var_C8], edi
0x1802333b8  jmp     short loc_1802333D6
0x1802333ba  mov     [rsp+108h+var_C8], 8007000Eh
0x1802333c2  jmp     short loc_1802333D6
0x1802333c4  mov     [rsp+108h+var_C8], 80028CA0h
0x1802333cc  jmp     short loc_1802333D6
0x1802333ce  mov     [rsp+108h+var_C8], 80004003h
0x1802333d6  lea     rcx, [rsp+108h+var_80]; this
0x1802333de  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x1802333e3  nop
0x1802333e4  jmp     short loc_1802333F2
0x1802333e6  jmp     short loc_1802333F2
0x1802333e8  jmp     short loc_1802333F2
0x1802333ea  jmp     short loc_1802333F2
0x1802333ec  jmp     short loc_1802333F2
0x1802333ee  jmp     short loc_1802333F2
0x1802333f0  jmp     short $+2
0x1802333f2  mov     rcx, [rsp+108h+var_C0]; this
0x1802333f7  call    ?Release@ScriptSite@@QEAAXXZ; ScriptSite::Release(void)
0x1802333fc  mov     rcx, [rsp+108h+arg_0]; this
0x180233404  call    ?Release@ObjectAsIPropertyValue@Projection@@UEAAKXZ; Projection::ObjectAsIPropertyValue::Release(void)
0x180233409  nop
0x18023340a  lea     rcx, [rsp+108h+var_68]; this
0x180233412  call    ??1AutoHostScriptContextStackPointer@@QEAA@XZ; AutoHostScriptContextStackPointer::~AutoHostScriptContextStackPointer(void)
0x180233417  nop
0x180233418  lea     rcx, [rsp+108h+var_50]; this
0x180233420  call    ??1AutoCallerPointer@@QEAA@XZ; AutoCallerPointer::~AutoCallerPointer(void)
0x180233425  mov     eax, [rsp+108h+var_C8]
0x180233429  add     rsp, 0E0h
0x180233430  pop     r15
0x180233432  pop     r14
0x180233434  pop     rdi
0x180233435  pop     rsi
0x180233436  pop     rbx
0x180233437  retn
```

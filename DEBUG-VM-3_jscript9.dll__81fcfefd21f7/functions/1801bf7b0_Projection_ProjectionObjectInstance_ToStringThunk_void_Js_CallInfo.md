# Projection::ProjectionObjectInstance::ToStringThunk(void *,Js::CallInfo,...)

- ea: `0x1801bf7b0`
- end: `0x1801bf9c6`
- name: `?ToStringThunk@ProjectionObjectInstance@Projection@@SAPEAXPEAXUCallInfo@Js@@ZZ`
- size: `534`
- prototype: `void *__high(struct Js::RecyclableObject *, struct Js::CallInfo, ...)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180016010`
- `0x180021e18`
- `0x180022508`
- `0x180068c64`
- `0x18010e730`
- `0x180145f38`
- `0x1801abd20`
- `0x1801baa4c`
- `0x1801bf7b0`
- `0x1801bf9cc`
- `0x180243bd0`
- `0x1802af0b0`
- `0x1802b1ae0`
- `0x18035e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801bf8af`
- `KERNEL32!LoadLibraryExW` at `0x1801bf974`
- `KERNEL32!LoadLibraryExW` at `0x1801bf8af`
- `KERNEL32!LoadLibraryExW` at `0x1801bf974`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct Js::JavascriptString *Projection::ProjectionObjectInstance::ToStringThunk(__int64 a1, ...)
{
  ThreadContext **v1; // rdi
  Js::GlobalObject **v2; // rsi
  void *v3; // rdx
  struct Projection::ProjectionObjectInstance *ProjectionObjectInstanceFromVarNoThrow; // rax
  struct Projection::ProjectionObjectInstance *v5; // rbx
  Js::GlobalObject *v6; // rcx
  int (__fastcall ***v8)(_QWORD, GUID *, char *); // rcx
  __int64 v9; // r14
  __int64 v10; // rsi
  const WCHAR *v11; // rax
  int v12; // ebx
  __int64 v13; // rbx
  const WCHAR *v14; // rax
  unsigned __int16 *v15; // rax
  struct Js::JavascriptString *v16; // rbx
  unsigned int v17; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  Projection **v20; // [rsp+40h] [rbp-30h]
  _BYTE v21[40]; // [rsp+48h] [rbp-28h] BYREF
  void *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v24; // [rsp+A8h] [rbp+38h] BYREF
  va_list va; // [rsp+A8h] [rbp+38h]
  va_list va1; // [rsp+B0h] [rbp+40h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v24 = va_arg(va1, _QWORD);
  v18[1] = -2;
  v18[0] = 0;
  Js::ArgumentReader::ArgumentReader((Js::ArgumentReader *)&v19, (struct Js::CallInfo *)va, (void **)va1);
  v1 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  v2 = v20;
  ProjectionObjectInstanceFromVarNoThrow = Projection::GetProjectionObjectInstanceFromVarNoThrow(*v20, v3);
  v5 = ProjectionObjectInstanceFromVarNoThrow;
  if ( !ProjectionObjectInstanceFromVarNoThrow )
  {
    v6 = *v2;
    return (struct Js::JavascriptString *)Js::JavascriptObject::ToStringHelper(v6, (struct Js::ScriptContext *)v1);
  }
  v8 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)ProjectionObjectInstanceFromVarNoThrow + 7);
  if ( !v8 )
    Js::JavascriptError::ThrowReferenceError((struct Js::ScriptContext *)v1, -2146823179, 0);
  v9 = *((_QWORD *)ProjectionObjectInstanceFromVarNoThrow + 12);
  if ( !*((_BYTE *)ProjectionObjectInstanceFromVarNoThrow + 112) )
  {
    if ( (**v8)(v8, &GUID_96369f54_8eb6_48f0_abce_c1b211e627c3, (char *)ProjectionObjectInstanceFromVarNoThrow + 104) < 0 )
      *((_QWORD *)v5 + 13) = 0;
    *((_BYTE *)v5 + 112) = 1;
  }
  if ( !*((_QWORD *)v5 + 13) )
  {
    v6 = v5;
    return (struct Js::JavascriptString *)Js::JavascriptObject::ToStringHelper(v6, (struct Js::ScriptContext *)v1);
  }
  v10 = *(_QWORD *)(v9 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 8424LL) )
  {
    v11 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v9 + 96) + 8408LL);
    *(_QWORD *)(v10 + 8) = LoadLibraryExW(v11, 0, 0x800u);
    *(_BYTE *)(v10 + 16) = 1;
  }
  v19 = 0;
  v20 = (Projection **)v10;
  v17 = 0;
  v18[0] = 0;
  Js::JavascriptErrorDebug::ClearErrorInfo((struct Js::ScriptContext *)v1);
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v21, v1, retaddr);
  MarkerForExternalDebugStep();
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v5 + 13) + 48LL))(*((_QWORD *)v5 + 13), v18);
  if ( v1 )
    ThreadContext::DisposeOnLeaveScript(v1[148]);
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v21);
  if ( v12 < 0 )
    Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo((struct Js::ScriptContext *)v1, v12);
  v19 = v18[0];
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, 0);
  v13 = *(_QWORD *)(v9 + 96) + 8408LL;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 96) + 8424LL) )
  {
    v14 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(*(_QWORD *)(v9 + 96) + 8408LL);
    *(_QWORD *)(v13 + 8) = LoadLibraryExW(v14, 0, 0x800u);
    *(_BYTE *)(v13 + 16) = 1;
  }
  v15 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v13 + 40LL))(
                              v13,
                              v18[0],
                              &v17);
  v16 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(v15, v17, v1);
  AutoHSTRING::~AutoHSTRING((AutoHSTRING *)&v19);
  return v16;
}

```

## disassembly

```asm
0x1801bf7b0  mov     rax, rsp
0x1801bf7b3  mov     [rax+10h], rdx
0x1801bf7b7  mov     [rax+8], rcx
0x1801bf7bb  mov     [rax+18h], r8
0x1801bf7bf  mov     [rax+20h], r9
0x1801bf7c3  push    rbp
0x1801bf7c4  push    rbx
0x1801bf7c5  push    rsi
0x1801bf7c6  push    rdi
0x1801bf7c7  push    r14
0x1801bf7c9  mov     rbp, rsp
0x1801bf7cc  sub     rsp, 70h
0x1801bf7d0  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1801bf7d8  mov     [rbp+var_48], 0
0x1801bf7e0  lea     r8, [rbp+arg_10]; void **
0x1801bf7e4  lea     rdx, [rbp+arg_8]; struct Js::CallInfo *
0x1801bf7e8  lea     rcx, [rbp+var_38]; this
0x1801bf7ec  call    ??0ArgumentReader@Js@@QEAA@PEAUCallInfo@1@PEAPEAX@Z; Js::ArgumentReader::ArgumentReader(Js::CallInfo *,void * *)
0x1801bf7f1  mov     r10, [rbp+arg_0]
0x1801bf7f5  mov     rax, [r10+8]
0x1801bf7f9  mov     rcx, [rax+8]
0x1801bf7fd  mov     rdi, [rcx+430h]
0x1801bf804  mov     rsi, [rbp+var_30]
0x1801bf808  mov     rcx, [rsi]; this
0x1801bf80b  call    ?GetProjectionObjectInstanceFromVarNoThrow@Projection@@YAPEAVProjectionObjectInstance@1@PEAX@Z; Projection::GetProjectionObjectInstanceFromVarNoThrow(void *)
0x1801bf810  mov     rbx, rax
0x1801bf813  test    rax, rax
0x1801bf816  jnz     short loc_1801BF82E
0x1801bf818  mov     rcx, [rsi]; this
0x1801bf81b  mov     rdx, rdi; struct Js::ScriptContext *
0x1801bf81e  call    ?ToStringHelper@JavascriptObject@Js@@CAPEAXPEAXPEAVScriptContext@2@@Z; Js::JavascriptObject::ToStringHelper(void *,Js::ScriptContext *)
0x1801bf823  add     rsp, 70h
0x1801bf827  pop     r14
0x1801bf829  pop     rdi
0x1801bf82a  pop     rsi
0x1801bf82b  pop     rbx
0x1801bf82c  pop     rbp
0x1801bf82d  retn
0x1801bf82e  mov     rcx, [rax+38h]
0x1801bf832  test    rcx, rcx
0x1801bf835  jnz     short loc_1801BF848
0x1801bf837  xor     r8d, r8d; unsigned __int16 *
0x1801bf83a  mov     edx, 800A13F5h; int
0x1801bf83f  mov     rcx, rdi; struct Js::ScriptContext *
0x1801bf842  call    ?ThrowReferenceError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowReferenceError(Js::ScriptContext *,long,ushort const *)
0x1801bf848  mov     r14, [rax+60h]
0x1801bf84c  cmp     byte ptr [rax+70h], 0
0x1801bf850  jnz     short loc_1801BF878
0x1801bf852  mov     rax, [rcx]
0x1801bf855  lea     r8, [rbx+68h]
0x1801bf859  lea     rdx, _GUID_96369f54_8eb6_48f0_abce_c1b211e627c3
0x1801bf860  mov     rax, [rax]
0x1801bf863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf868  test    eax, eax
0x1801bf86a  jns     short loc_1801BF874
0x1801bf86c  mov     qword ptr [rbx+68h], 0
0x1801bf874  mov     byte ptr [rbx+70h], 1
0x1801bf878  cmp     qword ptr [rbx+68h], 0
0x1801bf87d  jnz     short loc_1801BF884
0x1801bf87f  mov     rcx, rbx
0x1801bf882  jmp     short loc_1801BF81B
0x1801bf884  mov     rsi, [r14+60h]
0x1801bf888  add     rsi, 20D8h
0x1801bf88f  cmp     byte ptr [rsi+10h], 0
0x1801bf893  jnz     short loc_1801BF8BD
0x1801bf895  mov     rax, [rsi]
0x1801bf898  mov     rcx, rsi
0x1801bf89b  mov     rax, [rax+8]
0x1801bf89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf8a4  mov     rcx, rax; lpLibFileName
0x1801bf8a7  xor     edx, edx; hFile
0x1801bf8a9  mov     r8d, 800h; dwFlags
0x1801bf8af  call    cs:__imp_LoadLibraryExW
0x1801bf8b5  mov     [rsi+8], rax
0x1801bf8b9  mov     byte ptr [rsi+10h], 1
0x1801bf8bd  mov     [rbp+var_38], 0
0x1801bf8c5  mov     [rbp+var_30], rsi
0x1801bf8c9  mov     [rbp+var_50], 0
0x1801bf8d0  mov     [rbp+var_48], 0
0x1801bf8d8  mov     rcx, rdi; struct Js::ScriptContext *
0x1801bf8db  call    ?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z; Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)
0x1801bf8e0  mov     r8, [rbp+28h]
0x1801bf8e4  mov     rdx, rdi
0x1801bf8e7  lea     rcx, [rbp+var_28]
0x1801bf8eb  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x1801bf8f0  nop
0x1801bf8f1  call    MarkerForExternalDebugStep
0x1801bf8f6  mov     rcx, [rbx+68h]
0x1801bf8fa  mov     rax, [rcx]
0x1801bf8fd  lea     rdx, [rbp+var_48]
0x1801bf901  mov     rax, [rax+30h]
0x1801bf905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf90a  mov     ebx, eax
0x1801bf90c  test    rdi, rdi
0x1801bf90f  jz      short loc_1801BF91E
0x1801bf911  mov     rcx, [rdi+4A0h]; this
0x1801bf918  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x1801bf91d  nop
0x1801bf91e  lea     rcx, [rbp+var_28]
0x1801bf922  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x1801bf927  test    ebx, ebx
0x1801bf929  js      loc_1801BF9BB
0x1801bf92f  mov     rax, [rbp+var_48]
0x1801bf933  mov     [rbp+var_38], rax
0x1801bf937  mov     rax, [rsi]
0x1801bf93a  xor     edx, edx
0x1801bf93c  mov     rcx, rsi
0x1801bf93f  mov     rax, [rax+20h]
0x1801bf943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf948  nop
0x1801bf949  mov     rbx, [r14+60h]
0x1801bf94d  add     rbx, 20D8h
0x1801bf954  cmp     byte ptr [rbx+10h], 0
0x1801bf958  jnz     short loc_1801BF982
0x1801bf95a  mov     rax, [rbx]
0x1801bf95d  mov     rcx, rbx
0x1801bf960  mov     rax, [rax+8]
0x1801bf964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf969  mov     rcx, rax; lpLibFileName
0x1801bf96c  xor     edx, edx; hFile
0x1801bf96e  mov     r8d, 800h; dwFlags
0x1801bf974  call    cs:__imp_LoadLibraryExW
0x1801bf97a  mov     [rbx+8], rax
0x1801bf97e  mov     byte ptr [rbx+10h], 1
0x1801bf982  mov     rax, [rbx]
0x1801bf985  lea     r8, [rbp+var_50]
0x1801bf989  mov     rdx, [rbp+var_48]
0x1801bf98d  mov     rcx, rbx
0x1801bf990  mov     rax, [rax+28h]
0x1801bf994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bf999  mov     edx, [rbp+var_50]
0x1801bf99c  mov     r8, rdi
0x1801bf99f  mov     rcx, rax
0x1801bf9a2  call    ??$NewWithBufferT@VLiteralString@Js@@$00@JavascriptString@Js@@CAPEAV01@PEBG_KPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,1>(ushort const *,unsigned __int64,Js::ScriptContext *)
0x1801bf9a7  mov     rbx, rax
0x1801bf9aa  lea     rcx, [rbp+var_38]; this
0x1801bf9ae  call    ??1AutoHSTRING@@QEAA@XZ; AutoHSTRING::~AutoHSTRING(void)
0x1801bf9b3  mov     rax, rbx
0x1801bf9b6  jmp     loc_1801BF823
0x1801bf9bb  mov     edx, ebx; int
0x1801bf9bd  mov     rcx, rdi; struct Js::ScriptContext *
0x1801bf9c0  call    ?MapAndThrowErrorWithInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptErrorDebug::MapAndThrowErrorWithInfo(Js::ScriptContext *,long)
```

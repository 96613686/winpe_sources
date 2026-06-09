# Projection::CreateWinrtConstructorObjectElement(ActiveScriptProfilerHeapEnum *,Js::RecyclableObject *)

- ea: `0x180249ea4`
- end: `0x18024a0af`
- name: `?CreateWinrtConstructorObjectElement@Projection@@YAPEAUHostProfilerHeapObject@@PEAVActiveScriptProfilerHeapEnum@@PEAVRecyclableObject@Js@@@Z`
- size: `523`
- prototype: `struct HostProfilerHeapObject *__fastcall(Projection *__hidden this, struct ActiveScriptProfilerHeapEnum *, struct Js::RecyclableObject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1801d3a1c`

## callees

- `0x1801a8a70`
- `0x1801ba704`
- `0x1801c989b`
- `0x180227edc`
- `0x180228074`
- `0x180228640`
- `0x18022e3b8`
- `0x180249ea4`
- `0x18035e010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249f40`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249f6b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249ff0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249f40`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249f6b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180249ff0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024a01e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024a02d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024a01e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024a02d`

## pseudocode

```c
struct HostProfilerHeapObject *__fastcall Projection::CreateWinrtConstructorObjectElement(
        Projection *this,
        struct ActiveScriptProfilerHeapEnum *a2,
        struct Js::RecyclableObject *a3)
{
  _QWORD *v3; // rdi
  unsigned __int16 v4; // r15
  struct Js::ScriptContext *v5; // r12
  __int64 v6; // rsi
  struct Projection::EventProjectionHandler *v7; // rdx
  unsigned int EventAndEventHandlerCount; // ebp
  __int64 v9; // rcx
  SIZE_T v10; // rbp
  int v11; // ebx
  _QWORD *v12; // rax
  void *v13; // rax
  struct Projection::EventProjectionHandler *v14; // r8
  struct _PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST *v15; // r9
  char *v16; // rax
  char *v17; // rbx
  __int64 i; // rsi
  void *v19; // rcx
  __int64 v20; // r9
  __int64 v22[7]; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = *(struct Js::ScriptContext **)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) + 1072LL);
  v6 = *(_QWORD *)(*((_QWORD *)a2 + 8) + 24LL);
  if ( Projection::ThisInfo::CanHoldEventCookies((Projection::ThisInfo *)v6) )
    EventAndEventHandlerCount = Projection::GetEventAndEventHandlerCount((Projection *)(v6 + 48), v7);
  else
    EventAndEventHandlerCount = 0;
  v22[0] = 0;
  v9 = *(_QWORD *)(v6 + 40);
  if ( v9 )
  {
    v11 = IUnknown::QueryInterface<IUnknown>(v9, v22);
    if ( v11 < 0 )
      goto LABEL_17;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
    v12 = CoTaskMemAlloc(8u);
    v3 = v12;
    if ( !v12 )
    {
      v11 = -2147024882;
      goto LABEL_23;
    }
    v4 = 1;
    *v12 = 0;
    v13 = CoTaskMemAlloc(16 * (EventAndEventHandlerCount + 4));
    *v3 = v13;
    if ( !v13 )
    {
      v11 = -2147024882;
LABEL_18:
      for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
      {
        v19 = (void *)v3[i];
        if ( v19 )
          CoTaskMemFree(v19);
      }
      CoTaskMemFree(v3);
LABEL_23:
      Js::JavascriptError::MapAndThrowError(v5, v11);
    }
    memset_0(v13, 0, 16 * (EventAndEventHandlerCount + 4));
    *(_QWORD *)(*v3 + 8LL) = v22[0];
    *(_DWORD *)(*v3 + 16LL) = *(_DWORD *)(v6 + 32);
    *(_DWORD *)(*v3 + 20LL) = 1424;
    *(_WORD *)(*v3 + 40LL) = 1;
    *(_DWORD *)(*v3 + 48LL) = 10;
    if ( Projection::ThisInfo::CanHoldEventCookies((Projection::ThisInfo *)v6) )
      Projection::PopulateProfilerEventInfo(this, (struct ActiveScriptProfilerHeapEnum *)(v6 + 48), v14, v15);
    else
      *(_DWORD *)v14 = 0;
    v10 = 72;
  }
  else
  {
    v10 = 48;
  }
  v16 = (char *)CoTaskMemAlloc(v10);
  v17 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
LABEL_17:
    if ( !v3 )
      goto LABEL_23;
    goto LABEL_18;
  }
  memset_0(v16, 0, v10);
  *((_DWORD *)v17 + 4) = *(_DWORD *)(v6 + 32);
  *((_DWORD *)v17 + 5) = 1024;
  if ( v22[0] )
  {
    *((_WORD *)v17 + 20) = 1;
    *((_DWORD *)v17 + 12) = 4;
    *((_DWORD *)v17 + 14) = -1;
    ActiveScriptProfilerHeapEnum::SetRelationshipInfo(
      this,
      (struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *)(v17 + 56),
      PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT);
    *((_QWORD *)v17 + 8) = v20;
    *((_WORD *)v17 + 13) = v4;
    *((_QWORD *)v17 + 4) = v3;
  }
  return (struct HostProfilerHeapObject *)v17;
}

```

## disassembly

```asm
0x180249ea4  mov     rax, rsp
0x180249ea7  mov     [rax+18h], rbx
0x180249eab  mov     [rax+20h], rbp
0x180249eaf  mov     [rax+10h], rdx
0x180249eb3  mov     [rax+8], rcx
0x180249eb7  push    rsi
0x180249eb8  push    rdi
0x180249eb9  push    r12
0x180249ebb  push    r14
0x180249ebd  push    r15
0x180249ebf  sub     rsp, 30h
0x180249ec3  mov     rax, [rdx+8]
0x180249ec7  xor     edi, edi
0x180249ec9  xor     r15d, r15d
0x180249ecc  mov     rcx, [rax+8]
0x180249ed0  mov     rax, [rdx+40h]
0x180249ed4  mov     r12, [rcx+430h]
0x180249edb  mov     rsi, [rax+18h]
0x180249edf  mov     rcx, rsi; this
0x180249ee2  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x180249ee7  test    al, al
0x180249ee9  jnz     short loc_180249EEF
0x180249eeb  xor     ebp, ebp
0x180249eed  jmp     short loc_180249EFA
0x180249eef  lea     rcx, [rsi+30h]; this
0x180249ef3  call    ?GetEventAndEventHandlerCount@Projection@@YAIPEAVEventProjectionHandler@1@@Z; Projection::GetEventAndEventHandlerCount(Projection::EventProjectionHandler *)
0x180249ef8  mov     ebp, eax
0x180249efa  mov     [rsp+58h+var_38], rdi
0x180249eff  mov     r14d, 1
0x180249f05  mov     rcx, [rsi+28h]
0x180249f09  test    rcx, rcx
0x180249f0c  jnz     short loc_180249F16
0x180249f0e  lea     ebp, [rcx+30h]
0x180249f11  jmp     loc_180249FED
0x180249f16  lea     rdx, [rsp+58h+var_38]
0x180249f1b  call    ??$QueryInterface@UIUnknown@@@IUnknown@@QEAAJPEAPEAU0@@Z; IUnknown::QueryInterface<IUnknown>(IUnknown * *)
0x180249f20  mov     ebx, eax
0x180249f22  test    eax, eax
0x180249f24  js      loc_18024A003
0x180249f2a  mov     rcx, [rsp+58h+var_38]
0x180249f2f  mov     rax, [rcx]
0x180249f32  mov     rax, [rax+10h]
0x180249f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180249f3b  mov     ecx, 8; cb
0x180249f40  call    cs:__imp_CoTaskMemAlloc
0x180249f46  mov     rdi, rax
0x180249f49  test    rax, rax
0x180249f4c  jnz     short loc_180249F58
0x180249f4e  mov     ebx, 8007000Eh
0x180249f53  jmp     loc_18024A033
0x180249f58  xor     eax, eax
0x180249f5a  movzx   r15d, r14w
0x180249f5e  mov     [rdi], rax
0x180249f61  lea     eax, [rbp+4]
0x180249f64  shl     eax, 4
0x180249f67  mov     ecx, eax; cb
0x180249f69  mov     ebx, eax
0x180249f6b  call    cs:__imp_CoTaskMemAlloc
0x180249f71  mov     [rdi], rax
0x180249f74  test    rax, rax
0x180249f77  jnz     short loc_180249F83
0x180249f79  mov     ebx, 8007000Eh
0x180249f7e  jmp     loc_18024A008
0x180249f83  mov     r8, rbx; Size
0x180249f86  xor     edx, edx; Val
0x180249f88  mov     rcx, rax; void *
0x180249f8b  call    memset_0
0x180249f90  mov     rax, [rsp+58h+var_38]
0x180249f95  mov     rcx, [rdi]
0x180249f98  mov     [rcx+8], rax
0x180249f9c  mov     rcx, [rdi]
0x180249f9f  mov     eax, [rsi+20h]
0x180249fa2  mov     [rcx+10h], eax
0x180249fa5  mov     rcx, rsi; this
0x180249fa8  mov     rax, [rdi]
0x180249fab  mov     dword ptr [rax+14h], 590h
0x180249fb2  mov     rax, [rdi]
0x180249fb5  mov     [rax+28h], r14w
0x180249fba  mov     rax, [rdi]
0x180249fbd  mov     dword ptr [rax+30h], 0Ah
0x180249fc4  lea     r8, [rax+38h]
0x180249fc8  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x180249fcd  test    al, al
0x180249fcf  jnz     short loc_180249FDA
0x180249fd1  mov     dword ptr [r8], 0
0x180249fd8  jmp     short loc_180249FE8
0x180249fda  mov     rcx, [rsp+58h+arg_0]; this
0x180249fdf  lea     rdx, [rsi+30h]; struct ActiveScriptProfilerHeapEnum *
0x180249fe3  call    ?PopulateProfilerEventInfo@Projection@@YAXPEAVActiveScriptProfilerHeapEnum@@PEAVEventProjectionHandler@1@PEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST@@@Z; Projection::PopulateProfilerEventInfo(ActiveScriptProfilerHeapEnum *,Projection::EventProjectionHandler *,_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST *)
0x180249fe8  mov     ebp, 48h ; 'H'
0x180249fed  mov     rcx, rbp; cb
0x180249ff0  call    cs:__imp_CoTaskMemAlloc
0x180249ff6  mov     rbx, rax
0x180249ff9  test    rax, rax
0x180249ffc  jnz     short loc_18024A03E
0x180249ffe  mov     ebx, 8007000Eh
0x18024a003  test    rdi, rdi
0x18024a006  jz      short loc_18024A033
0x18024a008  movzx   ebp, r15w
0x18024a00c  xor     esi, esi
0x18024a00e  mov     r14, rdi
0x18024a011  test    ebp, ebp
0x18024a013  jz      short loc_18024A02A
0x18024a015  mov     rcx, [r14+rsi*8]; pv
0x18024a019  test    rcx, rcx
0x18024a01c  jz      short loc_18024A024
0x18024a01e  call    cs:__imp_CoTaskMemFree
0x18024a024  inc     esi
0x18024a026  cmp     esi, ebp
0x18024a028  jb      short loc_18024A015
0x18024a02a  mov     rcx, rdi; pv
0x18024a02d  call    cs:__imp_CoTaskMemFree
0x18024a033  mov     edx, ebx; int
0x18024a035  mov     rcx, r12; struct Js::ScriptContext *
0x18024a038  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x18024a03e  mov     r8, rbp; Size
0x18024a041  xor     edx, edx; Val
0x18024a043  mov     rcx, rbx; void *
0x18024a046  call    memset_0
0x18024a04b  mov     eax, [rsi+20h]
0x18024a04e  mov     [rbx+10h], eax
0x18024a051  mov     dword ptr [rbx+14h], 400h
0x18024a058  cmp     [rsp+58h+var_38], 0
0x18024a05e  jz      short loc_18024A095
0x18024a060  mov     rcx, [rsp+58h+arg_0]; this
0x18024a065  lea     rdx, [rbx+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x18024a069  mov     [rbx+28h], r14w
0x18024a06e  mov     r8d, 4; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x18024a074  mov     r9, [rsp+58h+var_38]
0x18024a079  mov     [rbx+30h], r8d
0x18024a07d  mov     dword ptr [rdx], 0FFFFFFFFh
0x18024a083  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x18024a088  mov     [rbx+40h], r9
0x18024a08c  mov     [rbx+1Ah], r15w
0x18024a091  mov     [rbx+20h], rdi
0x18024a095  mov     rbp, [rsp+58h+arg_18]
0x18024a09a  mov     rax, rbx
0x18024a09d  mov     rbx, [rsp+58h+arg_10]
0x18024a0a2  add     rsp, 30h
0x18024a0a6  pop     r15
0x18024a0a8  pop     r14
0x18024a0aa  pop     r12
0x18024a0ac  pop     rdi
0x18024a0ad  pop     rsi
0x18024a0ae  retn
```

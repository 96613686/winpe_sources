# Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(HostProfilerHeapObject * *,HeapObjectInfoReturnResult *)

- ea: `0x1802517b0`
- end: `0x180251982`
- name: `?GetFullHeapObjectInfo@ProjectionObjectInstance@Projection@@QEAAJPEAPEAUHostProfilerHeapObject@@PEAW4HeapObjectInfoReturnResult@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(Projection::ProjectionObjectInstance *__hidden this, struct HostProfilerHeapObject **, enum HeapObjectInfoReturnResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18022f480`

## callees

- `0x1801ba704`
- `0x1801c09d0`
- `0x1801c989b`
- `0x1802435f0`
- `0x18024b168`
- `0x1802517b0`
- `0x18035e010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802517d1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802517ef`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180251823`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802517d1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1802517ef`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180251823`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180251834`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18025183d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180251834`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18025183d`

## pseudocode

```c
__int64 __fastcall Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(
        Projection::ProjectionObjectInstance *this,
        struct HostProfilerHeapObject **a2,
        enum HeapObjectInfoReturnResult *a3)
{
  char *v3; // rax
  char *v4; // rdi
  __int64 *v5; // rax
  __int64 *v6; // rbx
  SIZE_T v7; // rbp
  void *v8; // rax
  ActiveScriptProfilerHeapEnum *v10; // rbp
  __int64 v11; // r9
  __int16 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rax
  Projection::ProjectionWriter *ProjectionWriter; // rax
  int v16; // edx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // r8
  struct Projection::RuntimeClassTypeInformation *v20; // [rsp+20h] [rbp-28h] BYREF
  void *v21; // [rsp+28h] [rbp-20h] BYREF

  v3 = (char *)CoTaskMemAlloc(0x48u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_6;
  memset_0(v3, 0, 0x48u);
  v5 = (__int64 *)CoTaskMemAlloc(8u);
  v6 = v5;
  if ( !v5 )
  {
LABEL_5:
    CoTaskMemFree(v4);
LABEL_6:
    *(_DWORD *)a3 = 1;
    return 2147942414LL;
  }
  *v5 = 0;
  v7 = 16
     * ((*(unsigned int (__fastcall **)(Projection::ProjectionObjectInstance *))(*(_QWORD *)this + 776LL))(this) + 4);
  v8 = CoTaskMemAlloc(v7);
  *v6 = (__int64)v8;
  if ( !v8 )
  {
    CoTaskMemFree(v6);
    goto LABEL_5;
  }
  memset_0(v8, 0, v7);
  *((_DWORD *)v4 + 5) = 512;
  *((_WORD *)v4 + 20) = 1;
  v10 = *(ActiveScriptProfilerHeapEnum **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 1072LL)
                                                     + 1184LL)
                                         + 24LL);
  *((_DWORD *)v4 + 12) = 4;
  *((_DWORD *)v4 + 14) = -1;
  ActiveScriptProfilerHeapEnum::SetRelationshipInfo(
    v10,
    (struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *)(v4 + 56),
    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT);
  *((_QWORD *)v4 + 8) = v11;
  *((_WORD *)v4 + 13) = v12;
  *((_QWORD *)v4 + 4) = v6;
  v13 = *v6;
  v14 = *((_QWORD *)this + 7);
  v20 = 0;
  *(_QWORD *)(v13 + 8) = v14;
  *(_DWORD *)(*v6 + 16) = *(_DWORD *)(*((_QWORD *)this + 1) + 64LL);
  *(_DWORD *)(*v6 + 20) = 784;
  *(_WORD *)(*v6 + 40) = v12;
  ProjectionWriter = Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 12));
  Projection::ProjectionWriter::GetRuntimeClassTypeInformation(ProjectionWriter, *(_DWORD *)(*v6 + 16), &v21, &v20);
  *(_DWORD *)*v6 = Projection::GetApproximateSizeForGCPressure((Projection *)*((unsigned int *)v20 + 11), v16);
  v17 = *(_DWORD *)(*v6 + 20);
  if ( *(_DWORD *)*v6 )
    v18 = v17 | 0x40;
  else
    v18 = v17 | 0x80;
  *(_DWORD *)(*v6 + 20) = v18;
  v19 = *v6;
  *(_DWORD *)(v19 + 48) = 10;
  (*(void (__fastcall **)(Projection::ProjectionObjectInstance *, ActiveScriptProfilerHeapEnum *, __int64))(*(_QWORD *)this + 784LL))(
    this,
    v10,
    v19 + 56);
  *a2 = (struct HostProfilerHeapObject *)v4;
  *(_DWORD *)a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x1802517b0  mov     rax, rsp
0x1802517b3  mov     [rax+20h], rbx
0x1802517b7  mov     [rax+18h], r8
0x1802517bb  mov     [rax+10h], rdx
0x1802517bf  mov     [rax+8], rcx
0x1802517c3  push    rbp
0x1802517c4  push    rsi
0x1802517c5  push    rdi
0x1802517c6  sub     rsp, 30h
0x1802517ca  mov     ebx, 48h ; 'H'
0x1802517cf  mov     ecx, ebx; cb
0x1802517d1  call    cs:__imp_CoTaskMemAlloc
0x1802517d7  mov     rdi, rax
0x1802517da  test    rax, rax
0x1802517dd  jz      short loc_180251843
0x1802517df  mov     r8d, ebx; Size
0x1802517e2  xor     edx, edx; Val
0x1802517e4  mov     rcx, rax; void *
0x1802517e7  call    memset_0
0x1802517ec  lea     ecx, [rbx-40h]; cb
0x1802517ef  call    cs:__imp_CoTaskMemAlloc
0x1802517f5  mov     rbx, rax
0x1802517f8  test    rax, rax
0x1802517fb  jz      short loc_18025183A
0x1802517fd  mov     rsi, [rsp+48h+arg_0]
0x180251802  xor     eax, eax
0x180251804  mov     [rbx], rax
0x180251807  mov     rcx, [rsi]
0x18025180a  mov     rax, [rcx+308h]
0x180251811  mov     rcx, rsi
0x180251814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180251819  add     eax, 4
0x18025181c  shl     eax, 4
0x18025181f  mov     ecx, eax; cb
0x180251821  mov     ebp, eax
0x180251823  call    cs:__imp_CoTaskMemAlloc
0x180251829  mov     [rbx], rax
0x18025182c  test    rax, rax
0x18025182f  jnz     short loc_180251860
0x180251831  mov     rcx, rbx; pv
0x180251834  call    cs:__imp_CoTaskMemFree
0x18025183a  mov     rcx, rdi; pv
0x18025183d  call    cs:__imp_CoTaskMemFree
0x180251843  mov     rax, [rsp+48h+arg_10]
0x180251848  mov     dword ptr [rax], 1
0x18025184e  mov     eax, 8007000Eh
0x180251853  mov     rbx, [rsp+48h+arg_18]
0x180251858  add     rsp, 30h
0x18025185c  pop     rdi
0x18025185d  pop     rsi
0x18025185e  pop     rbp
0x18025185f  retn
0x180251860  mov     r8, rbp; Size
0x180251863  xor     edx, edx; Val
0x180251865  mov     rcx, rax; void *
0x180251868  call    memset_0
0x18025186d  mov     dword ptr [rdi+14h], 200h
0x180251874  lea     rdx, [rdi+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x180251878  mov     r10d, 1
0x18025187e  mov     [rdi+28h], r10w
0x180251883  mov     rax, [rsi+8]
0x180251887  mov     r9, [rsi+38h]
0x18025188b  lea     r8d, [r10+3]; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x18025188f  mov     rcx, [rax+8]
0x180251893  mov     rax, [rcx+430h]
0x18025189a  mov     rcx, [rax+4A0h]
0x1802518a1  mov     rbp, [rcx+18h]
0x1802518a5  mov     rcx, rbp; this
0x1802518a8  mov     dword ptr [rdi+30h], 4
0x1802518af  mov     dword ptr [rdx], 0FFFFFFFFh
0x1802518b5  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x1802518ba  mov     [rdi+40h], r9
0x1802518be  mov     [rdi+1Ah], r10w
0x1802518c3  mov     [rdi+20h], rbx
0x1802518c7  mov     rcx, [rbx]
0x1802518ca  mov     rax, [rsi+38h]
0x1802518ce  mov     [rsp+48h+var_28], 0
0x1802518d7  mov     [rcx+8], rax
0x1802518db  mov     rax, [rsi+8]
0x1802518df  mov     rcx, [rbx]
0x1802518e2  mov     eax, [rax+40h]
0x1802518e5  mov     [rcx+10h], eax
0x1802518e8  mov     rax, [rbx]
0x1802518eb  mov     dword ptr [rax+14h], 310h
0x1802518f2  mov     rax, [rbx]
0x1802518f5  mov     [rax+28h], r10w
0x1802518fa  mov     rcx, [rsi+60h]; this
0x1802518fe  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x180251903  mov     rdx, [rbx]
0x180251906  lea     r9, [rsp+48h+var_28]; struct Projection::RuntimeClassTypeInformation **
0x18025190b  lea     r8, [rsp+48h+var_20]; void **
0x180251910  mov     rcx, rax; this
0x180251913  mov     edx, [rdx+10h]; int
0x180251916  call    ?GetRuntimeClassTypeInformation@ProjectionWriter@Projection@@QEAA_NHPEAPEAXPEAPEAVRuntimeClassTypeInformation@2@@Z; Projection::ProjectionWriter::GetRuntimeClassTypeInformation(int,void * *,Projection::RuntimeClassTypeInformation * *)
0x18025191b  mov     rcx, [rsp+48h+var_28]
0x180251920  mov     ecx, [rcx+2Ch]; this
0x180251923  call    ?GetApproximateSizeForGCPressure@Projection@@YA_KH@Z; Projection::GetApproximateSizeForGCPressure(int)
0x180251928  mov     rcx, [rbx]
0x18025192b  mov     [rcx], eax
0x18025192d  mov     rax, [rbx]
0x180251930  cmp     dword ptr [rax], 0
0x180251933  mov     ecx, [rax+14h]
0x180251936  jnz     short loc_18025193E
0x180251938  bts     ecx, 7
0x18025193c  jmp     short loc_180251941
0x18025193e  or      ecx, 40h
0x180251941  mov     [rax+14h], ecx
0x180251944  mov     rdx, rbp
0x180251947  mov     r8, [rbx]
0x18025194a  mov     rcx, rsi
0x18025194d  mov     dword ptr [r8+30h], 0Ah
0x180251955  add     r8, 38h ; '8'
0x180251959  mov     rax, [rsi]
0x18025195c  mov     rax, [rax+310h]
0x180251963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180251968  mov     rax, [rsp+48h+arg_8]
0x18025196d  mov     [rax], rdi
0x180251970  mov     rax, [rsp+48h+arg_10]
0x180251975  mov     dword ptr [rax], 0
0x18025197b  xor     eax, eax
0x18025197d  jmp     loc_180251853
```

# ServiceManager::EnsureCatalogLoaded(void)

- ea: `0x1800157e0`
- end: `0x18001588f`
- name: `?EnsureCatalogLoaded@ServiceManager@@AEAAJXZ`
- size: `175`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180009c88`
- `0x18000ec18`
- `0x180012cf0`
- `0x1800157e0`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MosStorage!MosQueryCatalogExists` at `0x180015826`
- `MosStorage!MosQueryCatalogExists` at `0x180015826`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015842`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015842`

## string_xrefs

- `0x180015839`: `ServiceManager::EnsureCatalogLoaded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::EnsureCatalogLoaded(ServiceManager *this)
{
  int v2; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF
  char v7; // [rsp+50h] [rbp+8h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v6);
  if ( PackageManager::AreMapsRegistered((ServiceManager *)((char *)this + 3568))
    || ClientsTracker::HasClientsRequiringServiceInitialized((LPCRITICAL_SECTION)((char *)this + 3816)) )
  {
    goto LABEL_9;
  }
  v7 = 0;
  v2 = MosQueryCatalogExists(&v7, 0);
  if ( v2 >= 0 )
  {
    if ( !v7 )
    {
      v2 = ServiceManager::AttachClient((__int64)this, 2u, 1, 0, 0);
      if ( v2 < 0 )
      {
        v3 = 1916;
        goto LABEL_5;
      }
    }
LABEL_9:
    v4 = 0;
    goto LABEL_10;
  }
  v3 = 1911;
LABEL_5:
  v4 = ZTraceReportPropagation(v2, "ServiceManager::EnsureCatalogLoaded", v3, this);
LABEL_10:
  RelockableGate::~RelockableGate((RelockableGate *)v6);
  return v4;
}

```

## disassembly

```asm
0x1800157e0  push    rbx
0x1800157e2  sub     rsp, 40h
0x1800157e6  mov     rbx, rcx
0x1800157e9  add     rcx, 0D48h
0x1800157f0  lea     rdx, [rsp+48h+var_18]
0x1800157f5  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800157fa  nop
0x1800157fb  lea     rcx, [rbx+0DF0h]; this
0x180015802  call    ?AreMapsRegistered@PackageManager@@QEAA_NXZ; PackageManager::AreMapsRegistered(void)
0x180015807  test    al, al
0x180015809  jnz     short loc_18001587B
0x18001580b  lea     rcx, [rbx+0EE8h]; lpCriticalSection
0x180015812  call    ?HasClientsRequiringServiceInitialized@ClientsTracker@@QEAA_NXZ; ClientsTracker::HasClientsRequiringServiceInitialized(void)
0x180015817  test    al, al
0x180015819  jnz     short loc_18001587B
0x18001581b  mov     [rsp+48h+arg_0], al
0x18001581f  xor     edx, edx
0x180015821  lea     rcx, [rsp+48h+arg_0]
0x180015826  call    cs:__imp_?MosQueryCatalogExists@@YAJPEA_NW4StackMode@@@Z; MosQueryCatalogExists(bool *,StackMode)
0x18001582c  test    eax, eax
0x18001582e  jns     short loc_18001584C
0x180015830  mov     r8d, 777h
0x180015836  mov     r9, rbx
0x180015839  lea     rdx, aServicemanager_33; "ServiceManager::EnsureCatalogLoaded"
0x180015840  mov     ecx, eax
0x180015842  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015848  mov     ebx, eax
0x18001584a  jmp     short loc_18001587D
0x18001584c  cmp     [rsp+48h+arg_0], 0
0x180015851  jnz     short loc_18001587B
0x180015853  mov     [rsp+48h+var_28], 0
0x18001585c  xor     r9d, r9d
0x18001585f  lea     edx, [r9+2]
0x180015863  lea     r8d, [r9+1]
0x180015867  mov     rcx, rbx
0x18001586a  call    ?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z; ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)
0x18001586f  test    eax, eax
0x180015871  jns     short loc_18001587B
0x180015873  mov     r8d, 77Ch
0x180015879  jmp     short loc_180015836
0x18001587b  xor     ebx, ebx
0x18001587d  lea     rcx, [rsp+48h+var_18]; this
0x180015882  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015887  mov     eax, ebx
0x180015889  add     rsp, 40h
0x18001588d  pop     rbx
0x18001588e  retn
```

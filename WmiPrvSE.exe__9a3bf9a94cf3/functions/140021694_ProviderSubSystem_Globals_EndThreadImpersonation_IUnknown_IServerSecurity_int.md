# ProviderSubSystem_Globals::EndThreadImpersonation(IUnknown *,IServerSecurity *,int)

- ea: `0x140021694`
- end: `0x1400217c0`
- name: `?EndThreadImpersonation@ProviderSubSystem_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IServerSecurity *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140020e40`
- `0x140020fc0`
- `0x140021130`
- `0x1400212a0`
- `0x140021434`
- `0x140021520`

## callees

- `0x140021694`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140021783`
- `wbemcomn!GetMemLogObject` at `0x140021783`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002178e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002178e`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1400216b7`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1400216b7`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Globals::EndThreadImpersonation(
        struct IUnknown *a1,
        struct IServerSecurity *a2,
        int a3)
{
  HRESULT v6; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  IUnknown *ppOldObject; // [rsp+58h] [rbp+20h] BYREF

  ppOldObject = 0;
  v6 = CoSwitchCallContext(a1, &ppOldObject);
  if ( v6 < 0 )
  {
    v6 = -2147217402;
  }
  else
  {
    if ( a1 )
    {
      if ( a3 )
      {
        lpVtbl = a1->lpVtbl;
        v10 = 0;
        v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               a1,
               &IID_IServerSecurity,
               &v10);
        if ( v6 >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
    if ( a2 )
      ((void (__fastcall *)(struct IServerSecurity *))a2->lpVtbl->Release)(a2);
  }
  if ( a1 )
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021694  mov     [rsp+arg_8], rbx
0x140021699  push    rbp
0x14002169a  push    rsi
0x14002169b  push    rdi
0x14002169c  sub     rsp, 20h
0x1400216a0  mov     rsi, rdx
0x1400216a3  mov     [rsp+38h+ppOldObject], 0
0x1400216ac  lea     rdx, [rsp+38h+ppOldObject]; ppOldObject
0x1400216b1  mov     ebp, r8d
0x1400216b4  mov     rdi, rcx
0x1400216b7  call    cs:__imp_CoSwitchCallContext
0x1400216bd  mov     ebx, eax
0x1400216bf  test    eax, eax
0x1400216c1  js      short loc_140021728
0x1400216c3  test    rdi, rdi
0x1400216c6  jz      short loc_1400216CC
0x1400216c8  test    ebp, ebp
0x1400216ca  jnz     short loc_14002172F
0x1400216cc  test    rsi, rsi
0x1400216cf  jz      short loc_1400216E0
0x1400216d1  mov     rax, [rsi]
0x1400216d4  mov     rcx, rsi
0x1400216d7  mov     rax, [rax+10h]
0x1400216db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400216e0  test    rdi, rdi
0x1400216e3  jz      short loc_1400216F4
0x1400216e5  mov     rax, [rdi]
0x1400216e8  mov     rcx, rdi
0x1400216eb  mov     rax, [rax+10h]
0x1400216ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400216f4  test    ebx, ebx
0x1400216f6  js      loc_140021783
0x1400216fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140021703  lea     rax, WPP_GLOBAL_Control
0x14002170a  cmp     rcx, rax
0x14002170d  jz      short loc_140021719
0x14002170f  test    byte ptr [rcx+1Ch], 4
0x140021713  jnz     loc_140021799
0x140021719  mov     eax, ebx
0x14002171b  mov     rbx, [rsp+38h+arg_8]
0x140021720  add     rsp, 20h
0x140021724  pop     rdi
0x140021725  pop     rsi
0x140021726  pop     rbp
0x140021727  retn
0x140021728  mov     ebx, 80041006h
0x14002172d  jmp     short loc_1400216E0
0x14002172f  mov     rax, [rdi]
0x140021732  lea     r8, [rsp+38h+arg_0]
0x140021737  lea     rdx, IID_IServerSecurity
0x14002173e  mov     [rsp+38h+arg_0], 0
0x140021747  mov     rcx, rdi
0x14002174a  mov     rax, [rax]
0x14002174d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021752  mov     ebx, eax
0x140021754  test    eax, eax
0x140021756  js      loc_1400216CC
0x14002175c  mov     rcx, [rsp+38h+arg_0]
0x140021761  mov     rax, [rcx]
0x140021764  mov     rax, [rax+20h]
0x140021768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002176d  mov     rcx, [rsp+38h+arg_0]
0x140021772  mov     rax, [rcx]
0x140021775  mov     rax, [rax+10h]
0x140021779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002177e  jmp     loc_1400216CC
0x140021783  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140021789  mov     rcx, rax
0x14002178c  mov     edx, ebx
0x14002178e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140021794  jmp     loc_1400216FC
0x140021799  cmp     byte ptr [rcx+19h], 2
0x14002179d  jb      loc_140021719
0x1400217a3  mov     rcx, [rcx+10h]
0x1400217a7  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x1400217ae  mov     edx, 16h
0x1400217b3  mov     r9d, ebx
0x1400217b6  call    WPP_SF_d
0x1400217bb  jmp     loc_140021719
```

# StaTask_Create::UnMarshalContext(void)

- ea: `0x140001494`
- end: `0x1400015b4`
- name: `?UnMarshalContext@StaTask_Create@@QEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(StaTask_Create *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001270`

## callees

- `0x140001024`
- `0x140001494`
- `0x1400015bc`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000159e`
- `wbemcomn!GetMemLogObject` at `0x14000159e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400015a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400015a9`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400014c1`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x140001544`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400014c1`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x140001544`

## pseudocode

```c
__int64 __fastcall StaTask_Create::UnMarshalContext(StaTask_Create *this)
{
  HRESULT InterfaceAndReleaseStream; // ebx
  IStream *v3; // rcx
  HRESULT v4; // eax
  IStream *v6; // rcx
  CMemoryLog *MemLogObject; // rax
  struct IWbemContext *v8; // [rsp+30h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp+10h] BYREF

  InterfaceAndReleaseStream = 0;
  v3 = (IStream *)*((_QWORD *)this + 13);
  v8 = 0;
  ppv = 0;
  if ( !v3
    || (v4 = CoGetInterfaceAndReleaseStream(v3, &IID_IWbemContext, (LPVOID *)&v8),
        *((_QWORD *)this + 13) = 0,
        InterfaceAndReleaseStream = v4,
        v4 >= 0) )
  {
    v6 = (IStream *)*((_QWORD *)this + 14);
    if ( v6 )
    {
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v6, &IID_IWbemServices, &ppv);
      *((_QWORD *)this + 14) = 0;
    }
  }
  if ( v8 )
  {
    CServerObject_StaThread::SetContext(*((CServerObject_StaThread **)this + 9), v8);
    ((void (__fastcall *)(struct IWbemContext *))v8->lpVtbl->Release)(v8);
  }
  if ( ppv )
  {
    CServerObject_StaThread::SetRepository(*((CServerObject_StaThread **)this + 9), (struct IWbemServices *)ppv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( InterfaceAndReleaseStream < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, InterfaceAndReleaseStream);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids,
      (unsigned int)InterfaceAndReleaseStream);
  }
  return (unsigned int)InterfaceAndReleaseStream;
}

```

## disassembly

```asm
0x140001494  mov     rax, rsp
0x140001497  mov     [rax+18h], rbx
0x14000149b  push    rdi
0x14000149c  sub     rsp, 20h
0x1400014a0  xor     ebx, ebx
0x1400014a2  mov     rdi, rcx
0x1400014a5  mov     rcx, [rcx+68h]; pStm
0x1400014a9  mov     [rax+8], rbx
0x1400014ad  mov     [rax+10h], rbx
0x1400014b1  test    rcx, rcx
0x1400014b4  jz      short loc_14000152F
0x1400014b6  lea     r8, [rax+8]; ppv
0x1400014ba  lea     rdx, IID_IWbemContext; iid
0x1400014c1  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1400014c7  mov     qword ptr [rdi+68h], 0
0x1400014cf  mov     ebx, eax
0x1400014d1  test    eax, eax
0x1400014d3  jns     short loc_14000152F
0x1400014d5  mov     rdx, [rsp+28h+arg_0]; struct IWbemContext *
0x1400014da  test    rdx, rdx
0x1400014dd  jnz     loc_14000157F
0x1400014e3  mov     rdx, [rsp+28h+ppv]; struct IWbemServices *
0x1400014e8  test    rdx, rdx
0x1400014eb  jz      short loc_140001507
0x1400014ed  mov     rcx, [rdi+48h]; this
0x1400014f1  call    ?SetRepository@CServerObject_StaThread@@QEAAJPEAUIWbemServices@@@Z; CServerObject_StaThread::SetRepository(IWbemServices *)
0x1400014f6  mov     rcx, [rsp+28h+ppv]
0x1400014fb  mov     rax, [rcx]
0x1400014fe  mov     rax, [rax+10h]
0x140001502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001507  test    ebx, ebx
0x140001509  js      loc_14000159E
0x14000150f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001516  lea     rax, WPP_GLOBAL_Control
0x14000151d  cmp     rcx, rax
0x140001520  jnz     short loc_140001559
0x140001522  mov     eax, ebx
0x140001524  mov     rbx, [rsp+28h+arg_10]
0x140001529  add     rsp, 20h
0x14000152d  pop     rdi
0x14000152e  retn
0x14000152f  mov     rcx, [rdi+70h]; pStm
0x140001533  test    rcx, rcx
0x140001536  jz      short loc_1400014D5
0x140001538  lea     r8, [rsp+28h+ppv]; ppv
0x14000153d  lea     rdx, IID_IWbemServices; iid
0x140001544  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x14000154a  mov     ebx, eax
0x14000154c  mov     qword ptr [rdi+70h], 0
0x140001554  jmp     loc_1400014D5
0x140001559  test    byte ptr [rcx+1Ch], 4
0x14000155d  jz      short loc_140001522
0x14000155f  cmp     byte ptr [rcx+19h], 2
0x140001563  jb      short loc_140001522
0x140001565  mov     rcx, [rcx+10h]
0x140001569  lea     r8, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids
0x140001570  mov     edx, 0Bh
0x140001575  mov     r9d, ebx
0x140001578  call    WPP_SF_d
0x14000157d  jmp     short loc_140001522
0x14000157f  mov     rcx, [rdi+48h]; this
0x140001583  call    ?SetContext@CServerObject_StaThread@@QEAAJPEAUIWbemContext@@@Z; CServerObject_StaThread::SetContext(IWbemContext *)
0x140001588  mov     rcx, [rsp+28h+arg_0]
0x14000158d  mov     rax, [rcx]
0x140001590  mov     rax, [rax+10h]
0x140001594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001599  jmp     loc_1400014E3
0x14000159e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400015a4  mov     rcx, rax
0x1400015a7  mov     edx, ebx
0x1400015a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400015af  jmp     loc_14000150F
```

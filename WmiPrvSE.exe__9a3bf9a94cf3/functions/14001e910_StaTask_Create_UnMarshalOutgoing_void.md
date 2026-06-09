# StaTask_Create::UnMarshalOutgoing(void)

- ea: `0x14001e910`
- end: `0x14001e9cb`
- name: `?UnMarshalOutgoing@StaTask_Create@@QEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(StaTask_Create *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001e268`

## callees

- `0x14001e910`
- `0x140020570`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001e992`
- `wbemcomn!GetMemLogObject` at `0x14001e992`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e99d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e99d`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14001e939`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14001e939`

## pseudocode

```c
__int64 __fastcall StaTask_Create::UnMarshalOutgoing(StaTask_Create *this)
{
  int v1; // ebx
  IStream *v3; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  CMemoryLog *MemLogObject; // rax
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v3 = (IStream *)*((_QWORD *)this + 15);
  ppv = 0;
  if ( v3 )
  {
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v3, &IID_IUnknown, &ppv);
    *((_QWORD *)this + 15) = 0;
    v1 = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream < 0
      || (v1 = CServerObject_StaThread::SetProviderService(
                 *((CServerObject_StaThread **)this + 9),
                 (struct IUnknown *)ppv),
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv),
          v1 < 0) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v1);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids, (unsigned int)v1);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001e910  mov     [rsp+arg_8], rbx
0x14001e915  push    rdi
0x14001e916  sub     rsp, 20h
0x14001e91a  xor     ebx, ebx
0x14001e91c  mov     rdi, rcx
0x14001e91f  mov     rcx, [rcx+78h]; pStm
0x14001e923  mov     [rsp+28h+ppv], rbx
0x14001e928  test    rcx, rcx
0x14001e92b  jz      short loc_14001E972
0x14001e92d  lea     r8, [rsp+28h+ppv]; ppv
0x14001e932  lea     rdx, IID_IUnknown; iid
0x14001e939  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x14001e93f  mov     qword ptr [rdi+78h], 0
0x14001e947  mov     ebx, eax
0x14001e949  test    eax, eax
0x14001e94b  js      short loc_14001E992
0x14001e94d  mov     rdx, [rsp+28h+ppv]; struct IUnknown *
0x14001e952  mov     rcx, [rdi+48h]; this
0x14001e956  call    ?SetProviderService@CServerObject_StaThread@@QEAAJPEAUIUnknown@@@Z; CServerObject_StaThread::SetProviderService(IUnknown *)
0x14001e95b  mov     rcx, [rsp+28h+ppv]
0x14001e960  mov     ebx, eax
0x14001e962  mov     rax, [rcx]
0x14001e965  mov     rax, [rax+10h]
0x14001e969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e96e  test    ebx, ebx
0x14001e970  js      short loc_14001E992
0x14001e972  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e979  lea     rax, WPP_GLOBAL_Control
0x14001e980  cmp     rcx, rax
0x14001e983  jnz     short loc_14001E9A5
0x14001e985  mov     eax, ebx
0x14001e987  mov     rbx, [rsp+28h+arg_8]
0x14001e98c  add     rsp, 20h
0x14001e990  pop     rdi
0x14001e991  retn
0x14001e992  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001e998  mov     rcx, rax
0x14001e99b  mov     edx, ebx
0x14001e99d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001e9a3  jmp     short loc_14001E972
0x14001e9a5  test    byte ptr [rcx+1Ch], 4
0x14001e9a9  jz      short loc_14001E985
0x14001e9ab  cmp     byte ptr [rcx+19h], 2
0x14001e9af  jb      short loc_14001E985
0x14001e9b1  mov     rcx, [rcx+10h]
0x14001e9b5  lea     r8, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids
0x14001e9bc  mov     edx, 0Dh
0x14001e9c1  mov     r9d, ebx
0x14001e9c4  call    WPP_SF_d
0x14001e9c9  jmp     short loc_14001E985
```

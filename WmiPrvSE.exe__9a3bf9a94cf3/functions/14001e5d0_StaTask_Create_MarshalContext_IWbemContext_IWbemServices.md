# StaTask_Create::MarshalContext(IWbemContext *,IWbemServices *)

- ea: `0x14001e5d0`
- end: `0x14001e680`
- name: `?MarshalContext@StaTask_Create@@QEAAJPEAUIWbemContext@@PEAUIWbemServices@@@Z`
- size: `176`
- prototype: `int(StaTask_Create *__hidden this, struct IWbemContext *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001e268`

## callees

- `0x14001e5d0`
- `0x1400234b8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14001e603`
- `wbemcomn!GetMemLogObject` at `0x14001e603`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e60e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001e60e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001e5f7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001e672`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001e5f7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x14001e672`

## pseudocode

```c
__int64 __fastcall StaTask_Create::MarshalContext(LPSTREAM *this, IUnknown *a2, IUnknown *a3)
{
  HRESULT v3; // ebx
  CMemoryLog *MemLogObject; // rax

  v3 = 0;
  if ( a2 && (v3 = CoMarshalInterThreadInterfaceInStream(&IID_IWbemContext, a2, this + 13), v3 < 0)
    || a3 && (v3 = CoMarshalInterThreadInterfaceInStream(&IID_IWbemServices, a3, this + 14), v3 < 0) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v3);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids, (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001e5d0  mov     [rsp+arg_0], rbx
0x14001e5d5  mov     [rsp+arg_8], rsi
0x14001e5da  push    rdi
0x14001e5db  sub     rsp, 20h
0x14001e5df  xor     ebx, ebx
0x14001e5e1  mov     rdi, r8
0x14001e5e4  mov     rsi, rcx
0x14001e5e7  test    rdx, rdx
0x14001e5ea  jz      short loc_14001E65F
0x14001e5ec  lea     r8, [rcx+68h]; ppStm
0x14001e5f0  lea     rcx, IID_IWbemContext; riid
0x14001e5f7  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x14001e5fd  mov     ebx, eax
0x14001e5ff  test    eax, eax
0x14001e601  jns     short loc_14001E65F
0x14001e603  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001e609  mov     rcx, rax
0x14001e60c  mov     edx, ebx
0x14001e60e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001e614  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e61b  lea     rax, WPP_GLOBAL_Control
0x14001e622  cmp     rcx, rax
0x14001e625  jnz     short loc_14001E639
0x14001e627  mov     rsi, [rsp+28h+arg_8]
0x14001e62c  mov     eax, ebx
0x14001e62e  mov     rbx, [rsp+28h+arg_0]
0x14001e633  add     rsp, 20h
0x14001e637  pop     rdi
0x14001e638  retn
0x14001e639  test    byte ptr [rcx+1Ch], 4
0x14001e63d  jz      short loc_14001E627
0x14001e63f  cmp     byte ptr [rcx+19h], 2
0x14001e643  jb      short loc_14001E627
0x14001e645  mov     rcx, [rcx+10h]
0x14001e649  lea     r8, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids
0x14001e650  mov     edx, 0Ah
0x14001e655  mov     r9d, ebx
0x14001e658  call    WPP_SF_d
0x14001e65d  jmp     short loc_14001E627
0x14001e65f  test    rdi, rdi
0x14001e662  jz      short loc_14001E614
0x14001e664  lea     r8, [rsi+70h]; ppStm
0x14001e668  mov     rdx, rdi; pUnk
0x14001e66b  lea     rcx, IID_IWbemServices; riid
0x14001e672  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x14001e678  mov     ebx, eax
0x14001e67a  test    eax, eax
0x14001e67c  jns     short loc_14001E614
0x14001e67e  jmp     short loc_14001E603
```

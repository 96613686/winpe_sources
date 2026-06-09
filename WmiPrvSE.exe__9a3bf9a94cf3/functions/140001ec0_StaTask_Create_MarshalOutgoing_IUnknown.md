# StaTask_Create::MarshalOutgoing(IUnknown *)

- ea: `0x140001ec0`
- end: `0x140001f38`
- name: `?MarshalOutgoing@StaTask_Create@@QEAAJPEAUIUnknown@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(StaTask_Create *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140001270`

## callees

- `0x140001ec0`
- `0x1400234b8`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140001f05`
- `wbemcomn!GetMemLogObject` at `0x140001f05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140001f10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140001f10`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140001ed8`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140001ed8`

## pseudocode

```c
__int64 __fastcall StaTask_Create::MarshalOutgoing(LPSTREAM *this, struct IUnknown *a2)
{
  HRESULT v2; // ebx
  CMemoryLog *MemLogObject; // rax

  v2 = 0;
  if ( a2 )
  {
    v2 = CoMarshalInterThreadInterfaceInStream(&IID_IUnknown, a2, this + 15);
    if ( v2 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v2);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids, (unsigned int)v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140001ec0  push    rbx
0x140001ec2  sub     rsp, 20h
0x140001ec6  xor     ebx, ebx
0x140001ec8  test    rdx, rdx
0x140001ecb  jz      short loc_140001EE4
0x140001ecd  lea     r8, [rcx+78h]; ppStm
0x140001ed1  lea     rcx, IID_IUnknown; riid
0x140001ed8  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x140001ede  mov     ebx, eax
0x140001ee0  test    eax, eax
0x140001ee2  js      short loc_140001F05
0x140001ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140001eeb  lea     rax, WPP_GLOBAL_Control
0x140001ef2  cmp     rcx, rax
0x140001ef5  jz      short loc_140001EFD
0x140001ef7  test    byte ptr [rcx+1Ch], 4
0x140001efb  jnz     short loc_140001F18
0x140001efd  mov     eax, ebx
0x140001eff  add     rsp, 20h
0x140001f03  pop     rbx
0x140001f04  retn
0x140001f05  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140001f0b  mov     rcx, rax
0x140001f0e  mov     edx, ebx
0x140001f10  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140001f16  jmp     short loc_140001EE4
0x140001f18  cmp     byte ptr [rcx+19h], 2
0x140001f1c  jb      short loc_140001EFD
0x140001f1e  mov     rcx, [rcx+10h]
0x140001f22  lea     r8, WPP_37fedaccbb8e36cbf733adeb2410ab4c_Traceguids
0x140001f29  mov     edx, 0Ch
0x140001f2e  mov     r9d, ebx
0x140001f31  call    WPP_SF_d
0x140001f36  jmp     short loc_140001EFD
```

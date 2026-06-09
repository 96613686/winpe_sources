# _PROG_RESOURCES::CreateContextSwitcher(void)

- ea: `0x180009b18`
- end: `0x180009b9b`
- name: `?CreateContextSwitcher@_PROG_RESOURCES@@QEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(_PROG_RESOURCES *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800098a0`

## callees

- `0x180009b18`
- `0x180012c34`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009b52`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009b52`
- `wbemcomn!GetMemLogObject` at `0x180009b47`
- `wbemcomn!GetMemLogObject` at `0x180009b47`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009b3b`

## pseudocode

```c
__int64 __fastcall _PROG_RESOURCES::CreateContextSwitcher(LPVOID *this)
{
  HRESULT Instance; // ebx
  CMemoryLog *MemLogObject; // rax

  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &IID_IContextCallback, this + 5);
  if ( Instance >= 0 )
    return 0;
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, Instance);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_2716f4bd31e130f967505b342dce5479_Traceguids,
      (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180009b18  push    rbx
0x180009b1a  sub     rsp, 30h
0x180009b1e  lea     rax, [rcx+28h]
0x180009b22  xor     edx, edx; pUnkOuter
0x180009b24  lea     r9, IID_IContextCallback; riid
0x180009b2b  mov     [rsp+38h+ppv], rax; ppv
0x180009b30  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180009b37  lea     r8d, [rdx+1]; dwClsContext
0x180009b3b  call    cs:__imp_CoCreateInstance
0x180009b41  mov     ebx, eax
0x180009b43  test    eax, eax
0x180009b45  jns     short loc_180009B93
0x180009b47  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009b4d  mov     rcx, rax
0x180009b50  mov     edx, ebx
0x180009b52  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b5f  lea     rax, WPP_GLOBAL_Control
0x180009b66  cmp     rcx, rax
0x180009b69  jz      short loc_180009B8F
0x180009b6b  test    byte ptr [rcx+1Ch], 1
0x180009b6f  jz      short loc_180009B8F
0x180009b71  cmp     byte ptr [rcx+19h], 2
0x180009b75  jb      short loc_180009B8F
0x180009b77  mov     rcx, [rcx+10h]
0x180009b7b  lea     r8, WPP_2716f4bd31e130f967505b342dce5479_Traceguids
0x180009b82  mov     edx, 0Ah
0x180009b87  mov     r9d, ebx
0x180009b8a  call    WPP_SF_d
0x180009b8f  mov     eax, ebx
0x180009b91  jmp     short loc_180009B95
0x180009b93  xor     eax, eax
0x180009b95  add     rsp, 30h
0x180009b99  pop     rbx
0x180009b9a  retn
```

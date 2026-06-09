# _CForwardFactory::CreateInstance_::_1_::catch$2

- ea: `0x18001d980`
- end: `0x18001d9ed`
- name: `_CForwardFactory::CreateInstance_::_1_::catch$2`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b648`
- `0x18001d980`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d99b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d99b`
- `wbemcomn!GetMemLogObject` at `0x18001d98d`
- `wbemcomn!GetMemLogObject` at `0x18001d98d`

## pseudocode

```c
__int64 __fastcall CForwardFactory::CreateInstance_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CMemoryLog *MemLogObject; // rax

  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids);
  }
  *(_DWORD *)(a2 + 48) = -2147467262;
  return 0;
}

```

## disassembly

```asm
0x18001d980  mov     [rsp+arg_8], rdx
0x18001d985  push    rbp
0x18001d986  sub     rsp, 30h
0x18001d98a  mov     rbp, rdx
0x18001d98d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d993  mov     edx, 0FFFFFFFFh
0x18001d998  mov     rcx, rax
0x18001d99b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d9a1  lea     rax, WPP_GLOBAL_Control
0x18001d9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9af  cmp     rcx, rax
0x18001d9b2  jz      short loc_18001D9D5
0x18001d9b4  test    byte ptr [rcx+1Ch], 1
0x18001d9b8  jz      short loc_18001D9D5
0x18001d9ba  cmp     byte ptr [rcx+19h], 2
0x18001d9be  jb      short loc_18001D9D5
0x18001d9c0  mov     edx, 0Eh
0x18001d9c5  lea     r8, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids
0x18001d9cc  mov     rcx, [rcx+10h]
0x18001d9d0  call    WPP_SF_
0x18001d9d5  mov     dword ptr [rbp+30h], 80004002h
0x18001d9dc  mov     rax, 0
0x18001d9e6  add     rsp, 30h
0x18001d9ea  pop     rbp
0x18001d9eb  retn
```

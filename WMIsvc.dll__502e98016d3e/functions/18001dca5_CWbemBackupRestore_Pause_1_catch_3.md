# _CWbemBackupRestore::Pause_::_1_::catch$3

- ea: `0x18001dca5`
- end: `0x18001dd23`
- name: `_CWbemBackupRestore::Pause_::_1_::catch$3`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014d24`
- `0x18001dca5`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dcd2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dcd2`
- `wbemcomn!GetMemLogObject` at `0x18001dcc4`
- `wbemcomn!GetMemLogObject` at `0x18001dcc4`

## pseudocode

```c
__int64 __fastcall CWbemBackupRestore::Pause_::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  CMemoryLog *MemLogObject; // rax
  __int64 v4; // r8

  v2 = *(_QWORD *)(a2 + 136);
  _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 64), 0, 1);
  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -2147217402);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v4, v2, -2147217402);
  }
  return 0;
}

```

## disassembly

```asm
0x18001dca5  mov     [rsp+arg_8], rdx
0x18001dcaa  push    rbx
0x18001dcab  push    rbp
0x18001dcac  sub     rsp, 48h
0x18001dcb0  mov     rbp, rdx
0x18001dcb3  mov     rbx, [rbp+88h]
0x18001dcba  xor     ecx, ecx
0x18001dcbc  lea     eax, [rcx+1]
0x18001dcbf  lock cmpxchg [rbx+40h], ecx
0x18001dcc4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001dcca  mov     edx, 80041006h
0x18001dccf  mov     rcx, rax
0x18001dcd2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001dcd8  lea     rax, WPP_GLOBAL_Control
0x18001dcdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dce6  cmp     rcx, rax
0x18001dce9  jz      short loc_18001DD11
0x18001dceb  test    byte ptr [rcx+1Ch], 1
0x18001dcef  jz      short loc_18001DD11
0x18001dcf1  cmp     byte ptr [rcx+19h], 2
0x18001dcf5  jb      short loc_18001DD11
0x18001dcf7  mov     edx, 1Eh
0x18001dcfc  mov     [rsp+58h+var_38], 80041006h
0x18001dd04  mov     r9, rbx
0x18001dd07  mov     rcx, [rcx+10h]
0x18001dd0b  call    WPP_SF_qD
0x18001dd10  nop
0x18001dd11  mov     rax, 0
0x18001dd1b  add     rsp, 48h
0x18001dd1f  pop     rbp
0x18001dd20  pop     rbx
0x18001dd21  retn
```

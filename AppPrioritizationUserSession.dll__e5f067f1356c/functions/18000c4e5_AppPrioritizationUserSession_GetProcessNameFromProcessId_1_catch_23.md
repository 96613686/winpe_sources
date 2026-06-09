# _AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::catch$23

- ea: `0x18000c4e5`
- end: `0x18000c52d`
- name: `_AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::catch$23`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800080c0`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::catch_23(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 56);
  *(_OWORD *)v2 = 0;
  *(_QWORD *)(v2 + 16) = 0;
  *(_QWORD *)(v2 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(v2, &dword_18000EE34, 0);
  return 0;
}

```

## disassembly

```asm
0x18000c4e5  mov     [rsp+arg_8], rdx
0x18000c4ea  push    rbp
0x18000c4eb  sub     rsp, 30h
0x18000c4ef  mov     rbp, rdx
0x18000c4f2  xorps   xmm0, xmm0
0x18000c4f5  mov     rcx, [rbp+38h]
0x18000c4f9  movups  xmmword ptr [rcx], xmm0
0x18000c4fc  mov     qword ptr [rcx+10h], 0
0x18000c504  mov     qword ptr [rcx+18h], 0
0x18000c50c  xor     r8d, r8d
0x18000c50f  lea     rdx, dword_18000EE34
0x18000c516  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c51b  nop
0x18000c51c  mov     rax, 0
0x18000c526  add     rsp, 30h
0x18000c52a  pop     rbp
0x18000c52b  retn
```

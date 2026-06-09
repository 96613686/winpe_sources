# sub_18004FCDC

- ea: `0x18004fcdc`
- end: `0x18004fdb9`
- name: `sub_18004FCDC`
- size: `221`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001fefc`
- `0x18004f780`

## callees

- `0x180002b24`
- `0x18004fcdc`
- `0x18004fdc0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004fd51`
- `KERNEL32!GetCurrentThreadId` at `0x18004fd51`
- `KERNEL32!LeaveCriticalSection` at `0x18004fda4`
- `KERNEL32!LeaveCriticalSection` at `0x18004fda4`
- `KERNEL32!EnterCriticalSection` at `0x18004fd42`
- `KERNEL32!EnterCriticalSection` at `0x18004fd42`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18004fd79`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18004fd79`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall sub_18004FCDC(LPCRITICAL_SECTION lpCriticalSection, __int64 *a2)
{
  __int64 v4; // rax
  struct _RTL_AVL_TABLE *v5; // rcx
  PVOID v6; // rax
  PVOID RestartKey; // [rsp+50h] [rbp+8h] BYREF
  __int64 *v10; // [rsp+58h] [rbp+10h]

  v10 = a2;
  *a2 = 0;
  a2[1] = 0;
  v4 = sub_180002B24(152);
  *(_QWORD *)v4 = v4;
  *(_QWORD *)(v4 + 8) = v4;
  *(_QWORD *)(v4 + 16) = v4;
  *(_WORD *)(v4 + 24) = 257;
  *a2 = v4;
  EnterCriticalSection(lpCriticalSection);
  if ( ++LODWORD(lpCriticalSection[1].DebugInfo) == 1 )
    HIDWORD(lpCriticalSection[1].DebugInfo) = GetCurrentThreadId();
  RestartKey = 0;
  while ( 1 )
  {
    v5 = **(struct _RTL_AVL_TABLE ***)&lpCriticalSection[1].LockCount;
    if ( !v5 )
      break;
    v6 = RtlEnumerateGenericTableWithoutSplayingAvl(v5, &RestartKey);
    if ( !v6 )
      break;
    sub_18004FDC0(lpCriticalSection, v6, a2);
  }
  if ( LODWORD(lpCriticalSection[1].DebugInfo)-- == 1 )
    HIDWORD(lpCriticalSection[1].DebugInfo) = 0;
  LeaveCriticalSection(lpCriticalSection);
  return a2;
}

```

## disassembly

```asm
0x18004fcdc  mov     [rsp+arg_10], rbx
0x18004fce1  mov     [rsp+arg_8], rdx
0x18004fce6  push    rdi
0x18004fce7  sub     rsp, 40h
0x18004fceb  mov     rdi, rdx
0x18004fcee  mov     rbx, rcx
0x18004fcf1  mov     [rsp+48h+var_28], 0
0x18004fcf9  mov     qword ptr [rdx], 0
0x18004fd00  mov     qword ptr [rdx+8], 0
0x18004fd08  mov     ecx, 98h
0x18004fd0d  call    sub_180002B24
0x18004fd12  mov     [rax], rax
0x18004fd15  mov     [rax+8], rax
0x18004fd19  mov     [rax+10h], rax
0x18004fd1d  mov     word ptr [rax+18h], 101h
0x18004fd23  mov     [rdi], rax
0x18004fd26  mov     [rsp+48h+var_28], 1
0x18004fd2e  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x18004fd35  mov     [rsp+48h+var_20], rax
0x18004fd3a  mov     [rsp+48h+var_10], rbx
0x18004fd3f  mov     rcx, rbx; lpCriticalSection
0x18004fd42  call    cs:EnterCriticalSection
0x18004fd48  inc     dword ptr [rbx+28h]
0x18004fd4b  cmp     dword ptr [rbx+28h], 1
0x18004fd4f  jnz     short loc_18004FD5A
0x18004fd51  call    cs:GetCurrentThreadId
0x18004fd57  mov     [rbx+2Ch], eax
0x18004fd5a  mov     [rsp+48h+var_18], 1
0x18004fd5f  mov     [rsp+48h+RestartKey], 0
0x18004fd68  mov     rax, [rbx+30h]
0x18004fd6c  mov     rcx, [rax]; Table
0x18004fd6f  test    rcx, rcx
0x18004fd72  jz      short loc_18004FD94
0x18004fd74  lea     rdx, [rsp+48h+RestartKey]; RestartKey
0x18004fd79  call    cs:RtlEnumerateGenericTableWithoutSplayingAvl
0x18004fd7f  test    rax, rax
0x18004fd82  jz      short loc_18004FD94
0x18004fd84  mov     r8, rdi
0x18004fd87  mov     rdx, rax
0x18004fd8a  mov     rcx, rbx
0x18004fd8d  call    sub_18004FDC0
0x18004fd92  jmp     short loc_18004FD68
0x18004fd94  sub     dword ptr [rbx+28h], 1
0x18004fd98  jnz     short loc_18004FDA1
0x18004fd9a  mov     dword ptr [rbx+2Ch], 0
0x18004fda1  mov     rcx, rbx; lpCriticalSection
0x18004fda4  call    cs:LeaveCriticalSection
0x18004fdaa  mov     rax, rdi
0x18004fdad  mov     rbx, [rsp+48h+arg_10]
0x18004fdb2  add     rsp, 40h
0x18004fdb6  pop     rdi
0x18004fdb7  retn
```

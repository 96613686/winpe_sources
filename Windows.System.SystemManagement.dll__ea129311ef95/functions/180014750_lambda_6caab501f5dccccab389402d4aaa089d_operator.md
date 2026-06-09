# _lambda_6caab501f5dccccab389402d4aaa089d_::operator()

- ea: `0x180014750`
- end: `0x18001480a`
- name: `_lambda_6caab501f5dccccab389402d4aaa089d_::operator()`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180016bf0`

## callees

- `0x180014750`
- `0x18001c6a8`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800147a0`
- `ntdll!RtlAcquirePrivilege` at `0x1800147a0`
- `ntdll!RtlReleasePrivilege` at `0x1800147f2`
- `ntdll!RtlReleasePrivilege` at `0x1800147f2`
- `tzautoupdate!AttemptToUpdateTimeZone` at `0x1800147c3`
- `tzautoupdate!AttemptToUpdateTimeZone` at `0x1800147c3`

## pseudocode

```c
__int64 __fastcall lambda_6caab501f5dccccab389402d4aaa089d_::operator()(_QWORD *a1, __int64 a2)
{
  int HasSystemManagementCapability; // ebx
  NTSTATUS v5; // eax
  PVOID ReturnedState; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 v8; // [rsp+50h] [rbp+18h] BYREF
  ULONG Privilege; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  Privilege = 34;
  ReturnedState = 0;
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability(&v8);
  if ( HasSystemManagementCapability >= 0 )
  {
    if ( v8 )
    {
      v5 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
      HasSystemManagementCapability = v5 | 0x10000000;
      if ( v5 >= 0 )
      {
        HasSystemManagementCapability = AttemptToUpdateTimeZone((unsigned int)(*a1 / 0x989680uLL));
        if ( HasSystemManagementCapability < 0 )
          *(_DWORD *)(a2 + 16) = (HasSystemManagementCapability != -2147024638) + 1;
        else
          *(_DWORD *)(a2 + 16) = 0;
      }
    }
  }
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x180014750  mov     rax, rsp
0x180014753  mov     [rax+8], rbx
0x180014757  mov     [rax+10h], rsi
0x18001475b  push    rdi
0x18001475c  sub     rsp, 30h
0x180014760  mov     rsi, rcx
0x180014763  mov     byte ptr [rax+18h], 0
0x180014767  lea     rcx, [rax+18h]; unsigned __int8 *
0x18001476b  mov     dword ptr [rax+20h], 22h ; '"'
0x180014772  mov     rdi, rdx
0x180014775  mov     qword ptr [rax-18h], 0
0x18001477d  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x180014782  mov     ebx, eax
0x180014784  test    eax, eax
0x180014786  js      short loc_1800147E8
0x180014788  cmp     [rsp+38h+arg_10], 0
0x18001478d  jz      short loc_1800147E8
0x18001478f  xor     r8d, r8d; Flags
0x180014792  lea     r9, [rsp+38h+ReturnedState]; ReturnedState
0x180014797  lea     rcx, [rsp+38h+Privilege]; Privilege
0x18001479c  lea     edx, [r8+1]; NumPriv
0x1800147a0  call    cs:__imp_RtlAcquirePrivilege
0x1800147a6  mov     ebx, eax
0x1800147a8  or      ebx, 10000000h
0x1800147ae  jl      short loc_1800147E8
0x1800147b0  mov     rax, 0D6BF94D5E57A42BDh
0x1800147ba  mul     qword ptr [rsi]
0x1800147bd  shr     rdx, 17h
0x1800147c1  mov     ecx, edx
0x1800147c3  call    cs:__imp_AttemptToUpdateTimeZone
0x1800147c9  mov     ebx, eax
0x1800147cb  test    eax, eax
0x1800147cd  js      short loc_1800147D8
0x1800147cf  mov     dword ptr [rdi+10h], 0
0x1800147d6  jmp     short loc_1800147E8
0x1800147d8  xor     eax, eax
0x1800147da  cmp     ebx, 80070102h
0x1800147e0  setnz   al
0x1800147e3  inc     eax
0x1800147e5  mov     [rdi+10h], eax
0x1800147e8  mov     rcx, [rsp+38h+ReturnedState]; ReturnedState
0x1800147ed  test    rcx, rcx
0x1800147f0  jz      short loc_1800147F8
0x1800147f2  call    cs:__imp_RtlReleasePrivilege
0x1800147f8  mov     rsi, [rsp+38h+arg_8]
0x1800147fd  mov     eax, ebx
0x1800147ff  mov     rbx, [rsp+38h+arg_0]
0x180014804  add     rsp, 30h
0x180014808  pop     rdi
0x180014809  retn
```

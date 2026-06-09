# UbpmpDeleteAppContainerImpersonated

- ea: `0x18003e9bc`
- end: `0x18003ea57`
- name: `UbpmpDeleteAppContainerImpersonated`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001eaf4`
- `0x18003e8b0`

## callees

- `0x18000fbf0`
- `0x1800103c0`
- `0x18003e9bc`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ea31`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003ea31`
- `USERENV!DeleteAppContainerProfile` at `0x18003e9ec`
- `USERENV!DeleteAppContainerProfile` at `0x18003e9ec`

## pseudocode

```c
__int64 __fastcall UbpmpDeleteAppContainerImpersonated(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  _QWORD *v7; // rax

  v1 = *(_QWORD **)a1;
  result = _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)a1 + 16LL), 0xFFFFFFFFFFFFFFFFuLL);
  if ( result == 1 )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_ContainerProfilesListLock);
    DeleteAppContainerProfile(v1 + 4);
    v6 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v7 = (_QWORD *)v1[1], (_QWORD *)*v7 != v1) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    v1[1] = v1;
    *v1 = v1;
    UBPM_MIDL_user_free(v1, v6, v4, v5);
    dword_1800500A0 = 0;
    result = RtlReleaseSRWLockExclusive(&g_ContainerProfilesListLock);
    *(_QWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003e9bc  mov     [rsp+arg_0], rbx
0x18003e9c1  push    rdi
0x18003e9c2  sub     rsp, 20h
0x18003e9c6  mov     rbx, [rcx]
0x18003e9c9  mov     rdi, rcx
0x18003e9cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003e9d0  lock xadd [rbx+10h], rax
0x18003e9d6  cmp     rax, 1
0x18003e9da  jnz     short loc_18003EA44
0x18003e9dc  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x18003e9e3  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18003e9e8  lea     rcx, [rbx+20h]
0x18003e9ec  call    cs:__imp_DeleteAppContainerProfile
0x18003e9f3  nop     dword ptr [rax+rax+00h]
0x18003e9f8  mov     rdx, [rbx]
0x18003e9fb  cmp     [rdx+8], rbx
0x18003e9ff  jnz     short loc_18003EA50
0x18003ea01  mov     rax, [rbx+8]
0x18003ea05  cmp     [rax], rbx
0x18003ea08  jnz     short loc_18003EA50
0x18003ea0a  mov     [rax], rdx
0x18003ea0d  mov     rcx, rbx
0x18003ea10  mov     [rdx+8], rax
0x18003ea14  mov     [rbx+8], rbx
0x18003ea18  mov     [rbx], rbx
0x18003ea1b  call    UBPM_MIDL_user_free
0x18003ea20  lea     rcx, ?g_ContainerProfilesListLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_ContainerProfilesListLock
0x18003ea27  mov     cs:dword_1800500A0, 0
0x18003ea31  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003ea38  nop     dword ptr [rax+rax+00h]
0x18003ea3d  mov     qword ptr [rdi], 0
0x18003ea44  mov     rbx, [rsp+28h+arg_0]
0x18003ea49  add     rsp, 20h
0x18003ea4d  pop     rdi
0x18003ea4e  retn
0x18003ea50  mov     ecx, 3
0x18003ea55  int     29h; Win8: RtlFailFast(ecx)
```

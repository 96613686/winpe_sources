# SeComRouterLookup

- ea: `0x1800252c8`
- end: `0x1800253ae`
- name: `SeComRouterLookup`
- size: `230`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024ab0`
- `0x180024c10`
- `0x180024d70`
- `0x180024de0`
- `0x180024e90`
- `0x180025150`
- `0x1800254c8`
- `0x1800575b0`

## callees

- `0x18000f114`
- `0x1800252c8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002539b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002539b`
- `ntdll!RtlEnterCriticalSection` at `0x1800252e5`
- `ntdll!RtlEnterCriticalSection` at `0x1800252e5`

## string_xrefs

- `0x180025378`: `SeComRouterLookup`
- `0x18002536b`: `Shim COM mechanism failed to find hook %p`

## pseudocode

```c
__int64 __fastcall SeComRouterLookup(PRTL_CRITICAL_SECTION CriticalSection, _QWORD *a2, const void *a3)
{
  __int64 v6; // rbx
  unsigned __int64 i; // r8
  unsigned __int64 v8; // rax
  _QWORD *v9; // rcx

  v6 = 0;
  RtlEnterCriticalSection(CriticalSection);
  for ( i = 0; (HANDLE)i < CriticalSection[2].LockSemaphore; ++i )
  {
    if ( !is_mul_ok((unsigned __int64)CriticalSection[2].OwningThread, i)
      || (v8 = *(_QWORD *)&CriticalSection[3].LockCount,
          v9 = (_QWORD *)(v8 + (unsigned __int64)CriticalSection[2].OwningThread * i),
          (unsigned __int64)v9 < v8) )
    {
      v9 = 0;
    }
    if ( *v9 == *a2 && (const void *)v9[3] == a3 )
    {
      v6 = v9[2];
      break;
    }
  }
  if ( !v6 )
    AslLogCallPrintf(1, "SeComRouterLookup", 1529, "Shim COM mechanism failed to find hook %p", a3);
  RtlLeaveCriticalSection(CriticalSection);
  return v6;
}

```

## disassembly

```asm
0x1800252c8  push    rbx
0x1800252ca  push    rsi
0x1800252cb  push    rdi
0x1800252cc  push    r14
0x1800252ce  sub     rsp, 58h
0x1800252d2  mov     r14, r8
0x1800252d5  mov     rsi, rdx
0x1800252d8  mov     rdi, rcx
0x1800252db  mov     [rsp+78h+arg_0], rcx
0x1800252e3  xor     ebx, ebx
0x1800252e5  call    cs:__imp_RtlEnterCriticalSection
0x1800252eb  nop
0x1800252ec  mov     r9, [rsi]
0x1800252ef  xor     r8d, r8d
0x1800252f2  mov     [rsp+78h+var_40], r8
0x1800252f7  cmp     r8, [rdi+68h]
0x1800252fb  jnb     short loc_180025361
0x1800252fd  mov     [rsp+78h+var_48], 0
0x180025306  mov     [rsp+78h+var_48], 0
0x18002530f  mov     [rsp+78h+var_30], 0
0x180025318  mov     rax, r8
0x18002531b  mul     qword ptr [rdi+60h]
0x18002531f  mov     rcx, rax
0x180025322  test    rdx, rdx
0x180025325  jnz     short loc_18002533F
0x180025327  mov     rax, [rdi+80h]
0x18002532e  add     rcx, rax
0x180025331  cmp     rcx, rax
0x180025334  jnb     short loc_180025341
0x180025336  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x18002533f  xor     ecx, ecx
0x180025341  mov     [rsp+78h+var_48], rcx
0x180025346  cmp     [rcx], r9
0x180025349  jnz     short loc_18002535C
0x18002534b  cmp     [rcx+18h], r14
0x18002534f  jnz     short loc_18002535C
0x180025351  mov     rbx, [rcx+10h]
0x180025355  mov     [rsp+78h+var_38], rbx
0x18002535a  jmp     short loc_180025361
0x18002535c  inc     r8
0x18002535f  jmp     short loc_1800252F2
0x180025361  test    rbx, rbx
0x180025364  jnz     short loc_180025387
0x180025366  mov     [rsp+78h+var_58], r14
0x18002536b  lea     r9, aShimComMechani; "Shim COM mechanism failed to find hook "...
0x180025372  mov     r8d, 5F9h
0x180025378  lea     rdx, aSecomrouterloo; "SeComRouterLookup"
0x18002537f  lea     ecx, [rbx+1]
0x180025382  call    AslLogCallPrintf
0x180025387  jmp     short loc_180025398
0x180025389  xor     ebx, ebx
0x18002538b  mov     [rsp+78h+var_38], rbx
0x180025390  mov     rdi, [rsp+78h+arg_0]
0x180025398  mov     rcx, rdi; CriticalSection
0x18002539b  call    cs:__imp_RtlLeaveCriticalSection
0x1800253a1  mov     rax, rbx
0x1800253a4  add     rsp, 58h
0x1800253a8  pop     r14
0x1800253aa  pop     rdi
0x1800253ab  pop     rsi
0x1800253ac  pop     rbx
0x1800253ad  retn
```

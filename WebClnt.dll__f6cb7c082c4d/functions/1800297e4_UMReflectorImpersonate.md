# UMReflectorImpersonate

- ea: `0x1800297e4`
- end: `0x180029864`
- name: `UMReflectorImpersonate`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800148b4`
- `0x18001507c`
- `0x180016d24`
- `0x180017624`
- `0x18001832c`
- `0x1800196d0`
- `0x18001a5a0`
- `0x18001ca70`
- `0x18001dfc0`
- `0x18001ead0`
- `0x18001f190`
- `0x180021f00`
- `0x180023360`
- `0x180023960`
- `0x180024190`

## callees

- `0x18000b89c`
- `0x1800297e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002982f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002982f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800297fd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800297fd`

## pseudocode

```c
__int64 __fastcall UMReflectorImpersonate(__int64 a1, void *a2)
{
  DWORD LastError; // edi
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax

  if ( !a1 || !a2 )
    return 87;
  LastError = 0;
  if ( !ImpersonateLoggedOnUser(a2) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_Dd(v3, 10, WPP_d029d038bd7c30031ccc84c87485d96e_Traceguids, CurrentThreadId, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800297e4  mov     [rsp+arg_0], rbx
0x1800297e9  push    rdi
0x1800297ea  sub     rsp, 30h
0x1800297ee  test    rcx, rcx
0x1800297f1  jz      short loc_180029854
0x1800297f3  test    rdx, rdx
0x1800297f6  jz      short loc_180029854
0x1800297f8  mov     rcx, rdx; hToken
0x1800297fb  xor     edi, edi
0x1800297fd  call    cs:__imp_ImpersonateLoggedOnUser
0x180029803  test    eax, eax
0x180029805  jnz     short loc_180029850
0x180029807  call    cs:__imp_GetLastError
0x18002980d  mov     edi, eax
0x18002980f  mov     rbx, cs:WPP_GLOBAL_Control
0x180029816  lea     rax, WPP_GLOBAL_Control
0x18002981d  cmp     rbx, rax
0x180029820  jz      short loc_180029850
0x180029822  test    dword ptr [rbx+1Ch], 1000h
0x180029829  jz      short loc_180029850
0x18002982b  mov     rbx, [rbx+10h]
0x18002982f  call    cs:__imp_GetCurrentThreadId
0x180029835  mov     edx, 0Ah
0x18002983a  mov     [rsp+38h+var_18], edi
0x18002983e  mov     r9d, eax
0x180029841  lea     r8, WPP_d029d038bd7c30031ccc84c87485d96e_Traceguids
0x180029848  mov     rcx, rbx
0x18002984b  call    WPP_SF_Dd
0x180029850  mov     eax, edi
0x180029852  jmp     short loc_180029859
0x180029854  mov     eax, 57h ; 'W'
0x180029859  mov     rbx, [rsp+38h+arg_0]
0x18002985e  add     rsp, 30h
0x180029862  pop     rdi
0x180029863  retn
```

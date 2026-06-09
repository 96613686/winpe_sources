# CPersistDSO::GetClassID(_GUID *)

- ea: `0x180014300`
- end: `0x180014384`
- name: `?GetClassID@CPersistDSO@@UEAAJPEAU_GUID@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180014300`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001431f`
- `KERNEL32!GetCurrentThreadId` at `0x18001431f`
- `KERNEL32!LeaveCriticalSection` at `0x180014373`
- `KERNEL32!LeaveCriticalSection` at `0x180014373`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014332`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014332`
- `MSDART!UMSEnterCSWraper` at `0x180014313`
- `MSDART!UMSEnterCSWraper` at `0x180014313`

## pseudocode

```c
__int64 __fastcall CPersistDSO::GetClassID(CPersistDSO *this, struct _GUID *a2)
{
  __int64 v5; // rcx

  UMSEnterCSWraper((char *)this + 40);
  if ( !*((_DWORD *)this + 13) )
    *((_DWORD *)this + 12) = GetCurrentThreadId();
  ++*((_DWORD *)this + 13);
  ++*((_DWORD *)this + 14);
  SetErrorInfo(0, 0);
  *((_DWORD *)this + 1051) = 0;
  *(GUID *)((char *)this + 88) = IID_IPersist;
  *a2 = CLSID_MSPersist;
  --*((_DWORD *)this + 14);
  if ( (*((_DWORD *)this + 13))-- == 1 )
    *((_DWORD *)this + 12) = -1;
  v5 = *((_QWORD *)this + 5);
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return 0;
}

```

## disassembly

```asm
0x180014300  push    rbx
0x180014302  push    rbp
0x180014303  push    rsi
0x180014304  push    rdi
0x180014305  sub     rsp, 28h
0x180014309  mov     rsi, rcx
0x18001430c  mov     rbp, rdx
0x18001430f  add     rcx, 28h ; '('
0x180014313  call    cs:__imp_UMSEnterCSWraper
0x180014319  cmp     dword ptr [rsi+34h], 0
0x18001431d  jnz     short loc_180014328
0x18001431f  call    cs:__imp_GetCurrentThreadId
0x180014325  mov     [rsi+30h], eax
0x180014328  inc     dword ptr [rsi+34h]
0x18001432b  xor     edx, edx; perrinfo
0x18001432d  inc     dword ptr [rsi+38h]
0x180014330  xor     ecx, ecx; dwReserved
0x180014332  call    cs:__imp_SetErrorInfo
0x180014338  movups  xmm0, xmmword ptr cs:IID_IPersist.Data1
0x18001433f  mov     dword ptr [rsi+106Ch], 0
0x180014349  or      ecx, 0FFFFFFFFh
0x18001434c  movdqu  xmmword ptr [rsi+58h], xmm0
0x180014351  movups  xmm1, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x180014358  movdqu  xmmword ptr [rbp+0], xmm1
0x18001435d  add     [rsi+38h], ecx
0x180014360  add     [rsi+34h], ecx
0x180014363  jnz     short loc_180014368
0x180014365  mov     [rsi+30h], ecx
0x180014368  mov     rcx, [rsi+28h]
0x18001436c  dec     dword ptr [rcx+30h]
0x18001436f  add     rcx, 8; lpCriticalSection
0x180014373  call    cs:__imp_LeaveCriticalSection
0x180014379  xor     eax, eax
0x18001437b  add     rsp, 28h
0x18001437f  pop     rdi
0x180014380  pop     rsi
0x180014381  pop     rbp
0x180014382  pop     rbx
0x180014383  retn
```

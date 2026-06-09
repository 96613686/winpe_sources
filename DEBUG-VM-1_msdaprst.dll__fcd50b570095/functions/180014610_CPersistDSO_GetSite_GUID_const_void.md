# CPersistDSO::GetSite(_GUID const &,void * *)

- ea: `0x180014610`
- end: `0x1800146bb`
- name: `?GetSite@CPersistDSO@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `171`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014610`
- `0x1800292d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180014641`
- `KERNEL32!GetCurrentThreadId` at `0x180014641`
- `KERNEL32!LeaveCriticalSection` at `0x1800146a0`
- `KERNEL32!LeaveCriticalSection` at `0x1800146a0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014659`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014659`
- `MSDART!UMSEnterCSWraper` at `0x180014635`
- `MSDART!UMSEnterCSWraper` at `0x180014635`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetSite(CPersistDSO *this, const struct _GUID *a2, void **a3)
{
  char *v6; // rbx
  unsigned int Site; // esi
  __int64 v9; // rcx

  v6 = (char *)this - 4488;
  UMSEnterCSWraper((char *)this - 4488);
  if ( !*((_DWORD *)v6 + 3) )
    *((_DWORD *)v6 + 2) = GetCurrentThreadId();
  ++*((_DWORD *)v6 + 3);
  ++*((_DWORD *)v6 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4440) = IID_IObjectWithSite;
  *((_DWORD *)this - 81) = 0;
  Site = CImpIADOSecurity::GetSite(this, a2, a3);
  --*((_DWORD *)v6 + 4);
  if ( (*((_DWORD *)v6 + 3))-- == 1 )
    *((_DWORD *)v6 + 2) = -1;
  v9 = *(_QWORD *)v6;
  --*(_DWORD *)(v9 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
  return Site;
}

```

## disassembly

```asm
0x180014610  mov     [rsp+arg_8], rbx
0x180014615  mov     [rsp+arg_10], rbp
0x18001461a  push    rsi
0x18001461b  push    rdi
0x18001461c  push    r14
0x18001461e  sub     rsp, 20h
0x180014622  mov     rbp, r8
0x180014625  mov     r14, rdx
0x180014628  mov     rsi, rcx
0x18001462b  lea     rbx, [rcx-1188h]
0x180014632  mov     rcx, rbx
0x180014635  call    cs:__imp_UMSEnterCSWraper
0x18001463b  cmp     dword ptr [rbx+0Ch], 0
0x18001463f  jnz     short loc_18001464A
0x180014641  call    cs:__imp_GetCurrentThreadId
0x180014647  mov     [rbx+8], eax
0x18001464a  inc     dword ptr [rbx+0Ch]
0x18001464d  inc     dword ptr [rbx+10h]
0x180014650  mov     [rsp+38h+arg_0], rbx
0x180014655  xor     edx, edx; perrinfo
0x180014657  xor     ecx, ecx; dwReserved
0x180014659  call    cs:__imp_SetErrorInfo
0x18001465f  movups  xmm0, xmmword ptr cs:IID_IObjectWithSite.Data1
0x180014666  movdqu  xmmword ptr [rsi-1158h], xmm0
0x18001466e  mov     dword ptr [rsi-144h], 0
0x180014678  mov     r8, rbp; void **
0x18001467b  mov     rdx, r14; struct _GUID *
0x18001467e  mov     rcx, rsi; this
0x180014681  call    ?GetSite@CImpIADOSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z; CImpIADOSecurity::GetSite(_GUID const &,void * *)
0x180014686  mov     esi, eax
0x180014688  or      eax, 0FFFFFFFFh
0x18001468b  add     [rbx+10h], eax
0x18001468e  add     [rbx+0Ch], eax
0x180014691  jnz     short loc_180014696
0x180014693  mov     [rbx+8], eax
0x180014696  mov     rcx, [rbx]
0x180014699  dec     dword ptr [rcx+30h]
0x18001469c  add     rcx, 8; lpCriticalSection
0x1800146a0  call    cs:__imp_LeaveCriticalSection
0x1800146a6  mov     eax, esi
0x1800146a8  mov     rbx, [rsp+38h+arg_8]
0x1800146ad  mov     rbp, [rsp+38h+arg_10]
0x1800146b2  add     rsp, 20h
0x1800146b6  pop     r14
0x1800146b8  pop     rdi
0x1800146b9  pop     rsi
0x1800146ba  retn
```

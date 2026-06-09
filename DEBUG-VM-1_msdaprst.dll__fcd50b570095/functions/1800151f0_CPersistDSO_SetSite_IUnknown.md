# CPersistDSO::SetSite(IUnknown *)

- ea: `0x1800151f0`
- end: `0x180015282`
- name: `?SetSite@CPersistDSO@@UEAAJPEAUIUnknown@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800151f0`
- `0x180029930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015215`
- `KERNEL32!GetCurrentThreadId` at `0x180015215`
- `KERNEL32!LeaveCriticalSection` at `0x180015271`
- `KERNEL32!LeaveCriticalSection` at `0x180015271`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001522d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001522d`
- `MSDART!UMSEnterCSWraper` at `0x180015209`
- `MSDART!UMSEnterCSWraper` at `0x180015209`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::SetSite(CPersistDSO *this, struct IUnknown *a2)
{
  char *v4; // rbx
  unsigned int v5; // esi
  __int64 v7; // rcx

  v4 = (char *)this - 4488;
  UMSEnterCSWraper((char *)this - 4488);
  if ( !*((_DWORD *)v4 + 3) )
    *((_DWORD *)v4 + 2) = GetCurrentThreadId();
  ++*((_DWORD *)v4 + 3);
  ++*((_DWORD *)v4 + 4);
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4440) = IID_IObjectWithSite;
  *((_DWORD *)this - 81) = 0;
  v5 = CImpIADOSecurity::SetSite(this, a2);
  --*((_DWORD *)v4 + 4);
  if ( (*((_DWORD *)v4 + 3))-- == 1 )
    *((_DWORD *)v4 + 2) = -1;
  v7 = *(_QWORD *)v4;
  --*(_DWORD *)(v7 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  return v5;
}

```

## disassembly

```asm
0x1800151f0  push    rbx
0x1800151f2  push    rbp
0x1800151f3  push    rsi
0x1800151f4  push    rdi
0x1800151f5  sub     rsp, 28h
0x1800151f9  mov     rbp, rdx
0x1800151fc  mov     rsi, rcx
0x1800151ff  lea     rbx, [rcx-1188h]
0x180015206  mov     rcx, rbx
0x180015209  call    cs:__imp_UMSEnterCSWraper
0x18001520f  cmp     dword ptr [rbx+0Ch], 0
0x180015213  jnz     short loc_18001521E
0x180015215  call    cs:__imp_GetCurrentThreadId
0x18001521b  mov     [rbx+8], eax
0x18001521e  inc     dword ptr [rbx+0Ch]
0x180015221  inc     dword ptr [rbx+10h]
0x180015224  mov     [rsp+48h+arg_0], rbx
0x180015229  xor     edx, edx; perrinfo
0x18001522b  xor     ecx, ecx; dwReserved
0x18001522d  call    cs:__imp_SetErrorInfo
0x180015233  movups  xmm0, xmmword ptr cs:IID_IObjectWithSite.Data1
0x18001523a  movdqu  xmmword ptr [rsi-1158h], xmm0
0x180015242  mov     dword ptr [rsi-144h], 0
0x18001524c  mov     rdx, rbp; struct IUnknown *
0x18001524f  mov     rcx, rsi; this
0x180015252  call    ?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z; CImpIADOSecurity::SetSite(IUnknown *)
0x180015257  mov     esi, eax
0x180015259  or      eax, 0FFFFFFFFh
0x18001525c  add     [rbx+10h], eax
0x18001525f  add     [rbx+0Ch], eax
0x180015262  jnz     short loc_180015267
0x180015264  mov     [rbx+8], eax
0x180015267  mov     rcx, [rbx]
0x18001526a  dec     dword ptr [rcx+30h]
0x18001526d  add     rcx, 8; lpCriticalSection
0x180015271  call    cs:__imp_LeaveCriticalSection
0x180015277  mov     eax, esi
0x180015279  add     rsp, 28h
0x18001527d  pop     rdi
0x18001527e  pop     rsi
0x18001527f  pop     rbp
0x180015280  pop     rbx
0x180015281  retn
```

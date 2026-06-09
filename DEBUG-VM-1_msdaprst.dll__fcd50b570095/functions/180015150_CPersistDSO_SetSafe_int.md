# CPersistDSO::SetSafe(int)

- ea: `0x180015150`
- end: `0x1800151db`
- name: `?SetSafe@CPersistDSO@@UEAAJH@Z`
- size: `139`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015150`
- `0x1800298f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015174`
- `KERNEL32!GetCurrentThreadId` at `0x180015174`
- `KERNEL32!LeaveCriticalSection` at `0x1800151ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800151ca`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015187`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180015187`
- `MSDART!UMSEnterCSWraper` at `0x180015168`
- `MSDART!UMSEnterCSWraper` at `0x180015168`

## pseudocode

```c
__int64 __fastcall CPersistDSO::SetSafe(GUID *this, int a2)
{
  GUID *v2; // rbx
  unsigned int v5; // esi
  __int64 v7; // rcx

  v2 = this - 280;
  UMSEnterCSWraper(&this[-280]);
  if ( !*(_DWORD *)&v2->Data4[4] )
    *(_DWORD *)v2->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)&v2->Data4[4];
  ++v2[1].Data1;
  SetErrorInfo(0, 0);
  *(_DWORD *)&this[-20].Data2 = 0;
  this[-277] = IID_IADOSecurity;
  v5 = CImpIADOSecurity::SetSafe((CImpIADOSecurity *)this, a2);
  --v2[1].Data1;
  if ( (*(_DWORD *)&v2->Data4[4])-- == 1 )
    *(_DWORD *)v2->Data4 = -1;
  v7 = *(_QWORD *)&v2->Data1;
  --*(_DWORD *)(v7 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
  return v5;
}

```

## disassembly

```asm
0x180015150  push    rbx
0x180015152  push    rbp
0x180015153  push    rsi
0x180015154  push    rdi
0x180015155  sub     rsp, 28h
0x180015159  lea     rbx, [rcx-1180h]
0x180015160  mov     rsi, rcx
0x180015163  mov     rcx, rbx
0x180015166  mov     ebp, edx
0x180015168  call    cs:__imp_UMSEnterCSWraper
0x18001516e  cmp     dword ptr [rbx+0Ch], 0
0x180015172  jnz     short loc_18001517D
0x180015174  call    cs:__imp_GetCurrentThreadId
0x18001517a  mov     [rbx+8], eax
0x18001517d  inc     dword ptr [rbx+0Ch]
0x180015180  xor     edx, edx; perrinfo
0x180015182  inc     dword ptr [rbx+10h]
0x180015185  xor     ecx, ecx; dwReserved
0x180015187  call    cs:__imp_SetErrorInfo
0x18001518d  movups  xmm0, xmmword ptr cs:IID_IADOSecurity.Data1
0x180015194  mov     edx, ebp; int
0x180015196  mov     dword ptr [rsi-13Ch], 0
0x1800151a0  mov     rcx, rsi; this
0x1800151a3  movdqu  xmmword ptr [rsi-1150h], xmm0
0x1800151ab  call    ?SetSafe@CImpIADOSecurity@@UEAAJH@Z; CImpIADOSecurity::SetSafe(int)
0x1800151b0  mov     esi, eax
0x1800151b2  or      eax, 0FFFFFFFFh
0x1800151b5  add     [rbx+10h], eax
0x1800151b8  add     [rbx+0Ch], eax
0x1800151bb  jnz     short loc_1800151C0
0x1800151bd  mov     [rbx+8], eax
0x1800151c0  mov     rcx, [rbx]
0x1800151c3  dec     dword ptr [rcx+30h]
0x1800151c6  add     rcx, 8; lpCriticalSection
0x1800151ca  call    cs:__imp_LeaveCriticalSection
0x1800151d0  mov     eax, esi
0x1800151d2  add     rsp, 28h
0x1800151d6  pop     rdi
0x1800151d7  pop     rsi
0x1800151d8  pop     rbp
0x1800151d9  pop     rbx
0x1800151da  retn
```

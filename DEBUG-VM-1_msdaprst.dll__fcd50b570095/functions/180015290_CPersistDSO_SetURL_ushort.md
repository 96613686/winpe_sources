# CPersistDSO::SetURL(ushort *)

- ea: `0x180015290`
- end: `0x18001531d`
- name: `?SetURL@CPersistDSO@@UEAAJPEAG@Z`
- size: `141`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015290`
- `0x1800299a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800152b5`
- `KERNEL32!GetCurrentThreadId` at `0x1800152b5`
- `KERNEL32!LeaveCriticalSection` at `0x18001530c`
- `KERNEL32!LeaveCriticalSection` at `0x18001530c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800152c8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800152c8`
- `MSDART!UMSEnterCSWraper` at `0x1800152a9`
- `MSDART!UMSEnterCSWraper` at `0x1800152a9`

## pseudocode

```c
__int64 __fastcall CPersistDSO::SetURL(GUID *this, unsigned __int16 *a2)
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
  v5 = CImpIADOSecurity::SetURL((CImpIADOSecurity *)this, a2);
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
0x180015290  push    rbx
0x180015292  push    rbp
0x180015293  push    rsi
0x180015294  push    rdi
0x180015295  sub     rsp, 28h
0x180015299  lea     rbx, [rcx-1180h]
0x1800152a0  mov     rsi, rcx
0x1800152a3  mov     rcx, rbx
0x1800152a6  mov     rbp, rdx
0x1800152a9  call    cs:__imp_UMSEnterCSWraper
0x1800152af  cmp     dword ptr [rbx+0Ch], 0
0x1800152b3  jnz     short loc_1800152BE
0x1800152b5  call    cs:__imp_GetCurrentThreadId
0x1800152bb  mov     [rbx+8], eax
0x1800152be  inc     dword ptr [rbx+0Ch]
0x1800152c1  xor     edx, edx; perrinfo
0x1800152c3  inc     dword ptr [rbx+10h]
0x1800152c6  xor     ecx, ecx; dwReserved
0x1800152c8  call    cs:__imp_SetErrorInfo
0x1800152ce  movups  xmm0, xmmword ptr cs:IID_IADOSecurity.Data1
0x1800152d5  mov     rdx, rbp; unsigned __int16 *
0x1800152d8  mov     dword ptr [rsi-13Ch], 0
0x1800152e2  mov     rcx, rsi; this
0x1800152e5  movdqu  xmmword ptr [rsi-1150h], xmm0
0x1800152ed  call    ?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z; CImpIADOSecurity::SetURL(ushort *)
0x1800152f2  mov     esi, eax
0x1800152f4  or      eax, 0FFFFFFFFh
0x1800152f7  add     [rbx+10h], eax
0x1800152fa  add     [rbx+0Ch], eax
0x1800152fd  jnz     short loc_180015302
0x1800152ff  mov     [rbx+8], eax
0x180015302  mov     rcx, [rbx]
0x180015305  dec     dword ptr [rcx+30h]
0x180015308  add     rcx, 8; lpCriticalSection
0x18001530c  call    cs:__imp_LeaveCriticalSection
0x180015312  mov     eax, esi
0x180015314  add     rsp, 28h
0x180015318  pop     rdi
0x180015319  pop     rsi
0x18001531a  pop     rbp
0x18001531b  pop     rbx
0x18001531c  retn
```

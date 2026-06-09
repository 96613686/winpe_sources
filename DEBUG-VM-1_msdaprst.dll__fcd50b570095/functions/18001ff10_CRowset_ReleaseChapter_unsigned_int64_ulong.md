# CRowset::ReleaseChapter(unsigned __int64,ulong *)

- ea: `0x18001ff10`
- end: `0x18001ff98`
- name: `?ReleaseChapter@CRowset@@UEAAJ_KPEAK@Z`
- size: `136`
- prototype: `__int64 __fastcall(CRowset *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001ff10`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001ff40`
- `KERNEL32!GetCurrentThreadId` at `0x18001ff40`
- `KERNEL32!LeaveCriticalSection` at `0x18001ff86`
- `KERNEL32!LeaveCriticalSection` at `0x18001ff86`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ff58`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ff58`
- `MSDART!UMSEnterCSWraper` at `0x18001ff2a`
- `MSDART!UMSEnterCSWraper` at `0x18001ff2a`

## pseudocode

```c
__int64 __fastcall CRowset::ReleaseChapter(CRowset *this, __int64 a2, unsigned int *a3)
{
  __int64 *v3; // r14
  DWORD *v6; // rdi
  __int64 v8; // rcx

  v3 = (__int64 *)((char *)this + 128);
  UMSEnterCSWraper((char *)this + 128);
  v6 = (DWORD *)((char *)this + 136);
  if ( !*((_DWORD *)this + 35) )
    *v6 = GetCurrentThreadId();
  ++*((_DWORD *)this + 35);
  ++*((_DWORD *)this + 36);
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  --*((_DWORD *)this + 36);
  if ( (*((_DWORD *)this + 35))-- == 1 )
    *v6 = -1;
  v8 = *v3;
  --*(_DWORD *)(v8 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  return 0;
}

```

## disassembly

```asm
0x18001ff10  push    rbx
0x18001ff12  push    rsi
0x18001ff13  push    rdi
0x18001ff14  push    r14
0x18001ff16  sub     rsp, 28h
0x18001ff1a  lea     r14, [rcx+80h]
0x18001ff21  mov     rbx, rcx
0x18001ff24  mov     rcx, r14
0x18001ff27  mov     rsi, r8
0x18001ff2a  call    cs:__imp_UMSEnterCSWraper
0x18001ff30  cmp     dword ptr [rbx+8Ch], 0
0x18001ff37  lea     rdi, [rbx+88h]
0x18001ff3e  jnz     short loc_18001FF48
0x18001ff40  call    cs:__imp_GetCurrentThreadId
0x18001ff46  mov     [rdi], eax
0x18001ff48  inc     dword ptr [rbx+8Ch]
0x18001ff4e  xor     edx, edx; perrinfo
0x18001ff50  inc     dword ptr [rbx+90h]
0x18001ff56  xor     ecx, ecx; dwReserved
0x18001ff58  call    cs:__imp_SetErrorInfo
0x18001ff5e  test    rsi, rsi
0x18001ff61  jz      short loc_18001FF69
0x18001ff63  mov     dword ptr [rsi], 0
0x18001ff69  or      ecx, 0FFFFFFFFh
0x18001ff6c  add     [rbx+90h], ecx
0x18001ff72  add     [rbx+8Ch], ecx
0x18001ff78  jnz     short loc_18001FF7C
0x18001ff7a  mov     [rdi], ecx
0x18001ff7c  mov     rcx, [r14]
0x18001ff7f  dec     dword ptr [rcx+30h]
0x18001ff82  add     rcx, 8; lpCriticalSection
0x18001ff86  call    cs:__imp_LeaveCriticalSection
0x18001ff8c  xor     eax, eax
0x18001ff8e  add     rsp, 28h
0x18001ff92  pop     r14
0x18001ff94  pop     rdi
0x18001ff95  pop     rsi
0x18001ff96  pop     rbx
0x18001ff97  retn
```

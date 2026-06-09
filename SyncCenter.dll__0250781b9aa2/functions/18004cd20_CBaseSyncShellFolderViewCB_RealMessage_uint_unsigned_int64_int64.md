# CBaseSyncShellFolderViewCB::RealMessage(uint,unsigned __int64,__int64)

- ea: `0x18004cd20`
- end: `0x18004ce0d`
- name: `?RealMessage@CBaseSyncShellFolderViewCB@@UEAAJI_K_J@Z`
- size: `237`
- prototype: `int(CBaseSyncShellFolderViewCB *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043830`
- `0x180047100`
- `0x180047340`
- `0x18004b940`
- `0x18004daa0`

## callees

- `0x180005660`
- `0x18004cd20`
- `0x18004ce60`
- `0x1800510cc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cd9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cd9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cddd`

## pseudocode

```c
__int64 __fastcall CBaseSyncShellFolderViewCB::RealMessage(
        const unsigned __int16 **this,
        int a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  int v8; // esi
  __int64 v9; // r8
  void *v10; // [rsp+20h] [rbp-48h]
  LPVOID pv[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 == 17 )
    return (*((__int64 (__fastcall **)(const unsigned __int16 **, _QWORD))*this + 5))(this, 0);
  if ( a2 == 46 )
  {
    CBaseSyncShellFolderViewCB::_OnHwndMain((CBaseSyncShellFolderViewCB *)this, (HWND)a4);
    return 2147500037LL;
  }
  if ( a2 != 54 )
  {
    if ( a2 == 63 )
      return StringCchCopyW(a4 + 260, 0x104u, this[32]);
    if ( a2 == 94 )
    {
      if ( a4 )
        *(_OWORD *)a4 = FOLDERTYPEID_Sync;
      return 0;
    }
    return 2147500037LL;
  }
  v8 = 0;
  if ( *((_DWORD *)this + 66) )
  {
    pv[0] = 0;
    CoTaskMemFree(0);
    v8 = TResourceStringAllocCopyEx<unsigned short *>(
           g_hmodThisDll,
           *((unsigned int *)this + 66),
           v9,
           (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
           v10,
           (char *)pv);
    if ( v8 >= 0 )
      StringCchCopyW(a4, a3, (const unsigned __int16 *)pv[0]);
    CoTaskMemFree(pv[0]);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004cd20  push    rbx
0x18004cd22  push    rbp
0x18004cd23  push    rsi
0x18004cd24  push    rdi
0x18004cd25  sub     rsp, 48h
0x18004cd29  mov     rbx, r9
0x18004cd2c  mov     rbp, r8
0x18004cd2f  mov     rdi, rcx
0x18004cd32  cmp     edx, 11h
0x18004cd35  jz      loc_18004CDF6
0x18004cd3b  cmp     edx, 2Eh ; '.'
0x18004cd3e  jz      loc_18004CDE7
0x18004cd44  cmp     edx, 36h ; '6'
0x18004cd47  jz      short loc_18004CD89
0x18004cd49  cmp     edx, 3Fh ; '?'
0x18004cd4c  jz      short loc_18004CD6F
0x18004cd4e  cmp     edx, 5Eh ; '^'
0x18004cd51  jnz     loc_18004CDEF
0x18004cd57  test    rbx, rbx
0x18004cd5a  jz      short loc_18004CD68
0x18004cd5c  movups  xmm0, cs:FOLDERTYPEID_Sync
0x18004cd63  movdqu  xmmword ptr [r9], xmm0
0x18004cd68  xor     eax, eax
0x18004cd6a  jmp     loc_18004CE04
0x18004cd6f  mov     r8, [rdi+100h]; unsigned __int16 *
0x18004cd76  lea     rcx, [r9+208h]; unsigned __int16 *
0x18004cd7d  mov     edx, 104h; unsigned __int64
0x18004cd82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004cd87  jmp     short loc_18004CE04
0x18004cd89  xor     esi, esi
0x18004cd8b  cmp     [rcx+108h], esi
0x18004cd91  jz      short loc_18004CDE3
0x18004cd93  xor     ecx, ecx; pv
0x18004cd95  mov     [rsp+68h+pv], rsi
0x18004cd9a  call    cs:__imp_CoTaskMemFree
0x18004cda0  mov     edx, [rdi+108h]; int
0x18004cda6  lea     rax, [rsp+68h+pv]
0x18004cdab  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; int
0x18004cdb2  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18004cdb9  mov     [rsp+68h+var_40], rax; void *
0x18004cdbe  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18004cdc3  mov     esi, eax
0x18004cdc5  test    eax, eax
0x18004cdc7  js      short loc_18004CDD8
0x18004cdc9  mov     r8, [rsp+68h+pv]; unsigned __int16 *
0x18004cdce  mov     rcx, rbx; unsigned __int16 *
0x18004cdd1  mov     edx, ebp; unsigned __int64
0x18004cdd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004cdd8  mov     rcx, [rsp+68h+pv]; pv
0x18004cddd  call    cs:__imp_CoTaskMemFree
0x18004cde3  mov     eax, esi
0x18004cde5  jmp     short loc_18004CE04
0x18004cde7  mov     rdx, rbx; HWND
0x18004cdea  call    ?_OnHwndMain@CBaseSyncShellFolderViewCB@@AEAAXPEAUHWND__@@@Z; CBaseSyncShellFolderViewCB::_OnHwndMain(HWND__ *)
0x18004cdef  mov     eax, 80004005h
0x18004cdf4  jmp     short loc_18004CE04
0x18004cdf6  mov     rax, [rcx]
0x18004cdf9  xor     edx, edx
0x18004cdfb  mov     rax, [rax+28h]
0x18004cdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce04  add     rsp, 48h
0x18004ce08  pop     rdi
0x18004ce09  pop     rsi
0x18004ce0a  pop     rbp
0x18004ce0b  pop     rbx
0x18004ce0c  retn
```

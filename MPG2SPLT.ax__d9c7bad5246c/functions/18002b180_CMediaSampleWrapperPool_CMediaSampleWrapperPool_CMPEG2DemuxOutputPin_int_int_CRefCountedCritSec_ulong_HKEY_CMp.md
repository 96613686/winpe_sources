# CMediaSampleWrapperPool::CMediaSampleWrapperPool(CMPEG2DemuxOutputPin *,int,int,CRefCountedCritSec *,ulong,HKEY__ *,CMpeg2Stats *,long *)

- ea: `0x18002b180`
- end: `0x18002b266`
- name: `??0CMediaSampleWrapperPool@@QEAA@PEAVCMPEG2DemuxOutputPin@@HHPEAVCRefCountedCritSec@@KPEAUHKEY__@@PEAVCMpeg2Stats@@PEAJ@Z`
- size: `230`
- prototype: `CMediaSampleWrapperPool *__fastcall(CMediaSampleWrapperPool *__hidden this, struct CMPEG2DemuxOutputPin *, int, int, struct CRefCountedCritSec *, unsigned int, HKEY, struct CMpeg2Stats *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020a34`

## callees

- `0x18002b180`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b23d`
- `KERNEL32!GetLastError` at `0x18002b23d`
- `KERNEL32!CreateEventW` at `0x18002b22e`
- `KERNEL32!CreateEventW` at `0x18002b22e`
- `KERNEL32!InitializeCriticalSection` at `0x18002b1fd`
- `KERNEL32!InitializeCriticalSection` at `0x18002b1fd`

## pseudocode

```c
CMediaSampleWrapperPool *__fastcall CMediaSampleWrapperPool::CMediaSampleWrapperPool(
        CMediaSampleWrapperPool *this,
        struct CMPEG2DemuxOutputPin *a2,
        int a3,
        int a4,
        struct CRefCountedCritSec *a5,
        unsigned int a6,
        HKEY a7,
        struct CMpeg2Stats *a8,
        int *a9)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v12; // ecx

  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &CBufferSource::`vftable';
  *((_QWORD *)this + 2) = a8;
  *((_DWORD *)this + 6) = 1;
  _InterlockedIncrement((volatile signed __int32 *)a8 + 10);
  *((_DWORD *)this + 12) = 0;
  *(_QWORD *)this = &CMediaSampleWrapperPool::`vftable';
  *((_DWORD *)this + 13) = a6;
  *((_QWORD *)this + 16) = a5;
  *((_QWORD *)this + 5) = (char *)this + 32;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = a2;
  *((_DWORD *)this + 30) = a3;
  *((_DWORD *)this + 31) = a4;
  *((_QWORD *)this + 4) = (char *)this + 32;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 16) + 40LL));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 14) + 24LL) + 8LL))(*((_QWORD *)this + 14) + 24LL);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 12) = EventW;
  if ( EventW )
  {
    v12 = 0;
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
  }
  *a9 = v12;
  return this;
}

```

## disassembly

```asm
0x18002b180  push    rbx
0x18002b182  sub     rsp, 20h
0x18002b186  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002b18d  mov     qword ptr [rcx+8], 1
0x18002b195  mov     [rcx], rax
0x18002b198  mov     rbx, rcx
0x18002b19b  mov     rax, [rsp+28h+arg_38]
0x18002b1a0  mov     [rcx+10h], rax
0x18002b1a4  mov     dword ptr [rcx+18h], 1
0x18002b1ab  lock inc dword ptr [rax+28h]
0x18002b1af  lea     rax, ??_7CMediaSampleWrapperPool@@6B@; const CMediaSampleWrapperPool::`vftable'
0x18002b1b6  mov     dword ptr [rcx+30h], 0
0x18002b1bd  mov     [rcx], rax
0x18002b1c0  mov     eax, [rsp+28h+arg_28]
0x18002b1c4  mov     [rcx+34h], eax
0x18002b1c7  mov     rax, [rsp+28h+arg_20]
0x18002b1cc  mov     [rcx+80h], rax
0x18002b1d3  lea     rax, [rcx+20h]
0x18002b1d7  mov     [rcx+28h], rax
0x18002b1db  mov     qword ptr [rcx+60h], 0
0x18002b1e3  mov     dword ptr [rcx+68h], 0
0x18002b1ea  mov     [rcx+70h], rdx
0x18002b1ee  mov     [rcx+78h], r8d
0x18002b1f2  mov     [rcx+7Ch], r9d
0x18002b1f6  add     rcx, 38h ; '8'; lpCriticalSection
0x18002b1fa  mov     [rax], rax
0x18002b1fd  call    cs:__imp_InitializeCriticalSection
0x18002b203  mov     rax, [rbx+80h]
0x18002b20a  lock inc dword ptr [rax+28h]
0x18002b20e  mov     rcx, [rbx+70h]
0x18002b212  add     rcx, 18h
0x18002b216  mov     rax, [rcx]
0x18002b219  mov     rax, [rax+8]
0x18002b21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b222  xor     r9d, r9d; lpName
0x18002b225  xor     r8d, r8d; bInitialState
0x18002b228  xor     ecx, ecx; lpEventAttributes
0x18002b22a  lea     edx, [r9+1]; bManualReset
0x18002b22e  call    cs:__imp_CreateEventW
0x18002b234  mov     [rbx+60h], rax
0x18002b238  test    rax, rax
0x18002b23b  jnz     short loc_18002B254
0x18002b23d  call    cs:__imp_GetLastError
0x18002b243  mov     ecx, eax
0x18002b245  test    eax, eax
0x18002b247  jle     short loc_18002B256
0x18002b249  movzx   ecx, ax
0x18002b24c  or      ecx, 80070000h
0x18002b252  jmp     short loc_18002B256
0x18002b254  xor     ecx, ecx
0x18002b256  mov     rax, [rsp+28h+arg_40]
0x18002b25b  mov     [rax], ecx
0x18002b25d  mov     rax, rbx
0x18002b260  add     rsp, 20h
0x18002b264  pop     rbx
0x18002b265  retn
```

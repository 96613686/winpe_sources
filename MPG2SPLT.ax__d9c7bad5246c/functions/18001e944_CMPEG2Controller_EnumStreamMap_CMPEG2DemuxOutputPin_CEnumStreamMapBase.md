# CMPEG2Controller::EnumStreamMap(CMPEG2DemuxOutputPin *,CEnumStreamMapBase *)

- ea: `0x18001e944`
- end: `0x18001ea5a`
- name: `?EnumStreamMap@CMPEG2Controller@@QEAAJPEAVCMPEG2DemuxOutputPin@@PEAVCEnumStreamMapBase@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CMPEG2Controller *__hidden this, struct CMPEG2DemuxOutputPin *, struct CEnumStreamMapBase *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001c2b0`
- `0x18001c3a0`

## callees

- `0x18001e944`
- `0x1800279d0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001ea3d`
- `KERNEL32!LeaveCriticalSection` at `0x18001ea3d`
- `KERNEL32!EnterCriticalSection` at `0x18001e970`
- `KERNEL32!EnterCriticalSection` at `0x18001e970`
- `ole32!CoTaskMemFree` at `0x18001ea1b`
- `ole32!CoTaskMemFree` at `0x18001ea1b`

## pseudocode

```c
__int64 __fastcall CMPEG2Controller::EnumStreamMap(
        CMPEG2Controller *this,
        struct CMPEG2DemuxOutputPin *a2,
        struct CEnumStreamMapBase *a3)
{
  CMPEG2Controller *v3; // rsi
  unsigned int v5; // r14d
  int v6; // ebx
  __int64 v7; // r15
  __int64 v8; // rdi
  __int64 v9; // r8
  __int64 v10; // r8
  void *Src; // rbx
  int v12; // r12d
  int v13; // r13d
  __int64 v14; // rcx
  LPVOID pv; // [rsp+88h] [rbp+20h] BYREF

  v3 = this;
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(*((_QWORD *)this + 15) + 80LL));
  v5 = *((_DWORD *)v3 + 6);
  v6 = 0;
  v7 = *((_QWORD *)v3 + 2);
  v8 = 0;
  if ( v5 )
  {
    do
    {
      v9 = 8 * v8;
      if ( !a2 || a2 == *(struct CMPEG2DemuxOutputPin **)(*(_QWORD *)(v9 + v7) + 16LL) )
      {
        v10 = *(_QWORD *)(v9 + v7);
        pv = 0;
        Src = *(void **)(v10 + 24);
        v12 = *(_DWORD *)(v10 + 12);
        v13 = *(_DWORD *)(v10 + 8);
        v14 = (*(_QWORD *)(v10 + 16) + 24LL) & -(__int64)(*(_QWORD *)(v10 + 16) != 0);
        if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 80LL))(v14, &pv) >= 0 )
        {
          v6 = CEnumStreamMapBase::AddStreamMap(a3, v13, (const unsigned __int16 *)pv, v12, Src);
          CoTaskMemFree(pv);
        }
        else
        {
          v6 = -2147024882;
        }
      }
      if ( v6 < 0 )
        break;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v5 );
    v3 = this;
  }
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(*((_QWORD *)v3 + 15) + 80LL));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e944  mov     [rsp+arg_8], rbx
0x18001e949  mov     [rsp+arg_10], r8
0x18001e94e  mov     [rsp+arg_0], rcx
0x18001e953  push    rbp
0x18001e954  push    rsi
0x18001e955  push    rdi
0x18001e956  push    r12
0x18001e958  push    r13
0x18001e95a  push    r14
0x18001e95c  push    r15
0x18001e95e  sub     rsp, 30h
0x18001e962  mov     rsi, rcx
0x18001e965  mov     rbp, rdx
0x18001e968  mov     rcx, [rcx+78h]
0x18001e96c  mov     rcx, [rcx+50h]; lpCriticalSection
0x18001e970  call    cs:__imp_EnterCriticalSection
0x18001e976  mov     r14d, [rsi+18h]
0x18001e97a  xor     ebx, ebx
0x18001e97c  mov     r15, [rsi+10h]
0x18001e980  xor     edi, edi
0x18001e982  test    r14d, r14d
0x18001e985  jz      loc_18001EA35
0x18001e98b  mov     rsi, [rsp+68h+arg_10]
0x18001e993  lea     r8, ds:0[rdi*8]
0x18001e99b  test    rbp, rbp
0x18001e99e  jz      short loc_18001E9AA
0x18001e9a0  mov     rax, [r8+r15]
0x18001e9a4  cmp     rbp, [rax+10h]
0x18001e9a8  jnz     short loc_18001EA21
0x18001e9aa  mov     r8, [r8+r15]
0x18001e9ae  mov     [rsp+68h+pv], 0
0x18001e9ba  mov     rax, [r8+10h]
0x18001e9be  mov     rbx, [r8+18h]
0x18001e9c2  mov     r12d, [r8+0Ch]
0x18001e9c6  mov     r13d, [r8+8]
0x18001e9ca  lea     rdx, [rax+18h]
0x18001e9ce  neg     rax
0x18001e9d1  sbb     rcx, rcx
0x18001e9d4  and     rcx, rdx
0x18001e9d7  lea     rdx, [rsp+68h+pv]
0x18001e9df  mov     rax, [rcx]
0x18001e9e2  mov     rax, [rax+50h]
0x18001e9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9eb  test    eax, eax
0x18001e9ed  jns     short loc_18001E9F6
0x18001e9ef  mov     ebx, 8007000Eh
0x18001e9f4  jmp     short loc_18001EA21
0x18001e9f6  mov     r8, [rsp+68h+pv]; unsigned __int16 *
0x18001e9fe  mov     r9d, r12d; unsigned int
0x18001ea01  mov     edx, r13d; unsigned int
0x18001ea04  mov     [rsp+68h+Src], rbx; Src
0x18001ea09  mov     rcx, rsi; this
0x18001ea0c  call    ?AddStreamMap@CEnumStreamMapBase@@QEAAJKPEBGKPEAX@Z; CEnumStreamMapBase::AddStreamMap(ulong,ushort const *,ulong,void *)
0x18001ea11  mov     rcx, [rsp+68h+pv]; pv
0x18001ea19  mov     ebx, eax
0x18001ea1b  call    cs:__imp_CoTaskMemFree
0x18001ea21  test    ebx, ebx
0x18001ea23  js      short loc_18001EA30
0x18001ea25  inc     edi
0x18001ea27  cmp     edi, r14d
0x18001ea2a  jb      loc_18001E993
0x18001ea30  mov     rsi, [rsp+68h+arg_0]
0x18001ea35  mov     rcx, [rsi+78h]
0x18001ea39  mov     rcx, [rcx+50h]; lpCriticalSection
0x18001ea3d  call    cs:__imp_LeaveCriticalSection
0x18001ea43  mov     eax, ebx
0x18001ea45  mov     rbx, [rsp+68h+arg_8]
0x18001ea4a  add     rsp, 30h
0x18001ea4e  pop     r15
0x18001ea50  pop     r14
0x18001ea52  pop     r13
0x18001ea54  pop     r12
0x18001ea56  pop     rdi
0x18001ea57  pop     rsi
0x18001ea58  pop     rbp
0x18001ea59  retn
```

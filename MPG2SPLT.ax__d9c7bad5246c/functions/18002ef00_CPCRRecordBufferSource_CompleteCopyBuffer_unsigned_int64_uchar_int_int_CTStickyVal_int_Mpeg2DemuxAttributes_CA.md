# CPCRRecordBufferSource::CompleteCopyBuffer(unsigned __int64,uchar *,int,int,CTStickyVal<int> *,Mpeg2DemuxAttributes::CAttributeList *)

- ea: `0x18002ef00`
- end: `0x18002efca`
- name: `?CompleteCopyBuffer@CPCRRecordBufferSource@@UEAAJ_KPEAEHHPEAV?$CTStickyVal@H@@PEAVCAttributeList@Mpeg2DemuxAttributes@@@Z`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002ef00`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002efb7`
- `KERNEL32!LeaveCriticalSection` at `0x18002efb7`
- `KERNEL32!EnterCriticalSection` at `0x18002ef34`
- `KERNEL32!EnterCriticalSection` at `0x18002ef34`

## pseudocode

```c
__int64 __fastcall CPCRRecordBufferSource::CompleteCopyBuffer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  int v9; // esi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int64); // rdi
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int64); // rcx

  if ( a7 && *(int *)(a7 + 160) > 0 )
    return 2147549183LL;
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v10 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int64))(a1 + 40);
  if ( v10 )
  {
    v9 = (**v10)(*(_QWORD *)(a1 + 40), *(unsigned int *)(a1 + 96), *(_QWORD *)(a1 + 88), a5, *(_DWORD *)(a1 + 100), a6);
    if ( v9 >= 0 )
    {
      v11 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int64))(a1 + 40);
      if ( v10 != v11 )
      {
        if ( v11 )
          v9 = (**v11)(v11, *(unsigned int *)(a1 + 96), *(_QWORD *)(a1 + 88), a5, *(_DWORD *)(a1 + 100), a6);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002ef00  push    rbx
0x18002ef02  push    rbp
0x18002ef03  push    rsi
0x18002ef04  push    rdi
0x18002ef05  push    r14
0x18002ef07  sub     rsp, 40h
0x18002ef0b  mov     rax, [rsp+68h+arg_30]
0x18002ef13  mov     rbx, rcx
0x18002ef16  test    rax, rax
0x18002ef19  jz      short loc_18002EF2E
0x18002ef1b  cmp     dword ptr [rax+0A0h], 0
0x18002ef22  jle     short loc_18002EF2E
0x18002ef24  mov     eax, 8000FFFFh
0x18002ef29  jmp     loc_18002EFBF
0x18002ef2e  add     rcx, 30h ; '0'; lpCriticalSection
0x18002ef32  xor     esi, esi
0x18002ef34  call    cs:__imp_EnterCriticalSection
0x18002ef3a  mov     rdi, [rbx+28h]
0x18002ef3e  test    rdi, rdi
0x18002ef41  jz      short loc_18002EFB3
0x18002ef43  mov     rax, [rdi]
0x18002ef46  mov     rcx, rdi
0x18002ef49  mov     r14, [rsp+68h+arg_28]
0x18002ef51  mov     r9d, [rsp+68h+arg_20]
0x18002ef59  mov     r8, [rbx+58h]
0x18002ef5d  mov     r10, [rax]
0x18002ef60  mov     eax, [rbx+64h]
0x18002ef63  mov     edx, [rbx+60h]
0x18002ef66  mov     [rsp+68h+var_40], r14
0x18002ef6b  mov     [rsp+68h+var_48], eax
0x18002ef6f  mov     rax, r10
0x18002ef72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef77  mov     esi, eax
0x18002ef79  test    eax, eax
0x18002ef7b  js      short loc_18002EFB3
0x18002ef7d  mov     rcx, [rbx+28h]
0x18002ef81  cmp     rdi, rcx
0x18002ef84  jz      short loc_18002EFB3
0x18002ef86  test    rcx, rcx
0x18002ef89  jz      short loc_18002EFB3
0x18002ef8b  mov     edx, [rbx+64h]
0x18002ef8e  mov     rax, [rcx]
0x18002ef91  mov     r9d, [rsp+68h+arg_20]
0x18002ef99  mov     r8, [rbx+58h]
0x18002ef9d  mov     [rsp+68h+var_40], r14
0x18002efa2  mov     rax, [rax]
0x18002efa5  mov     [rsp+68h+var_48], edx
0x18002efa9  mov     edx, [rbx+60h]
0x18002efac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb1  mov     esi, eax
0x18002efb3  lea     rcx, [rbx+30h]; lpCriticalSection
0x18002efb7  call    cs:__imp_LeaveCriticalSection
0x18002efbd  mov     eax, esi
0x18002efbf  add     rsp, 40h
0x18002efc3  pop     r14
0x18002efc5  pop     rdi
0x18002efc6  pop     rsi
0x18002efc7  pop     rbp
0x18002efc8  pop     rbx
0x18002efc9  retn
```

# TGenericMap<unsigned __int64,ulong,0,5,19>::RemoveFirst(unsigned __int64 *)

- ea: `0x180030668`
- end: `0x1800306f1`
- name: `?RemoveFirst@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJPEA_K@Z`
- size: `137`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ecc0`
- `0x1800306f8`
- `0x180030990`
- `0x180030c68`

## callees

- `0x18003034c`
- `0x180030668`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800306d9`
- `KERNEL32!LeaveCriticalSection` at `0x1800306d9`
- `KERNEL32!EnterCriticalSection` at `0x180030687`
- `KERNEL32!EnterCriticalSection` at `0x180030687`

## pseudocode

```c
__int64 __fastcall TGenericMap<unsigned __int64,unsigned long,0,5,19>::RemoveFirst(__int64 a1, _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 *v5; // r9
  __int64 v6; // r8
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rax
  unsigned int v10; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 384);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  v5 = *(__int64 **)(a1 + 368);
  if ( v5 == (__int64 *)(a1 + 368) )
  {
    v10 = -2147467259;
  }
  else
  {
    v6 = v5[2];
    *a2 = *(v5 - 2);
    v7 = (_QWORD *)v5[3];
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    v8 = *v5;
    v9 = (__int64 *)v5[1];
    *v9 = *v5;
    *(_QWORD *)(v8 + 8) = v9;
    ObjectPool<TGenericMap<unsigned __int64,unsigned long,0,5,19>::TABLE_ENTRY,5>::Recycle(a1 + 8);
    v10 = 0;
  }
  LeaveCriticalSection(v2);
  return v10;
}

```

## disassembly

```asm
0x180030668  mov     [rsp+arg_0], rbx
0x18003066d  mov     [rsp+arg_8], rsi
0x180030672  push    rdi
0x180030673  sub     rsp, 20h
0x180030677  lea     rdi, [rcx+180h]
0x18003067e  mov     rbx, rcx
0x180030681  mov     rcx, rdi; lpCriticalSection
0x180030684  mov     rsi, rdx
0x180030687  call    cs:__imp_EnterCriticalSection
0x18003068d  lea     rax, [rbx+170h]
0x180030694  mov     r9, [rax]
0x180030697  cmp     r9, rax
0x18003069a  jz      short loc_1800306D1
0x18003069c  lea     rdx, [r9-18h]
0x1800306a0  mov     rax, [rdx+8]
0x1800306a4  mov     r8, [rdx+28h]
0x1800306a8  mov     [rsi], rax
0x1800306ab  mov     rax, [rdx+30h]
0x1800306af  mov     [rax], r8
0x1800306b2  mov     [r8+8], rax
0x1800306b6  mov     rcx, [r9]
0x1800306b9  mov     rax, [r9+8]
0x1800306bd  mov     [rax], rcx
0x1800306c0  mov     [rcx+8], rax
0x1800306c4  lea     rcx, [rbx+8]
0x1800306c8  call    ?Recycle@?$ObjectPool@UTABLE_ENTRY@?$TGenericMap@_KK$0A@$04$0BD@@@$04@@QEAAXPEAUTABLE_ENTRY@?$TGenericMap@_KK$0A@$04$0BD@@@@Z; ObjectPool<TGenericMap<unsigned __int64,ulong,0,5,19>::TABLE_ENTRY,5>::Recycle(TGenericMap<unsigned __int64,ulong,0,5,19>::TABLE_ENTRY *)
0x1800306cd  xor     ebx, ebx
0x1800306cf  jmp     short loc_1800306D6
0x1800306d1  mov     ebx, 80004005h
0x1800306d6  mov     rcx, rdi; lpCriticalSection
0x1800306d9  call    cs:__imp_LeaveCriticalSection
0x1800306df  mov     rsi, [rsp+28h+arg_8]
0x1800306e4  mov     eax, ebx
0x1800306e6  mov     rbx, [rsp+28h+arg_0]
0x1800306eb  add     rsp, 20h
0x1800306ef  pop     rdi
0x1800306f0  retn
```

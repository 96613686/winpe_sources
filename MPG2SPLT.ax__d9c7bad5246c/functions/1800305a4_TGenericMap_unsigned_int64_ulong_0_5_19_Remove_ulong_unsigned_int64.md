# TGenericMap<unsigned __int64,ulong,0,5,19>::Remove(ulong,unsigned __int64 *)

- ea: `0x1800305a4`
- end: `0x180030662`
- name: `?Remove@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800306f8`
- `0x180030990`

## callees

- `0x18003034c`
- `0x1800305a4`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180030619`
- `KERNEL32!LeaveCriticalSection` at `0x180030619`
- `KERNEL32!EnterCriticalSection` at `0x1800305eb`
- `KERNEL32!EnterCriticalSection` at `0x1800305eb`

## pseudocode

```c
__int64 __fastcall TGenericMap<unsigned __int64,unsigned long,0,5,19>::Remove(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v6; // rbx
  _QWORD **v7; // rax
  _QWORD *i; // rcx
  _QWORD *v9; // rdx
  unsigned int v10; // ebx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax

  v6 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) % 0x13;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  v7 = (_QWORD **)(a1 + 16 * (v6 + 4));
  for ( i = *v7; ; i = (_QWORD *)*i )
  {
    if ( i == v7 )
      goto LABEL_5;
    v9 = i - 5;
    if ( *((_DWORD *)i - 10) == a2 )
      break;
  }
  if ( i == (_QWORD *)40 )
  {
LABEL_5:
    v10 = -2147467259;
    goto LABEL_6;
  }
  v12 = *i;
  *a3 = v9[1];
  v13 = (_QWORD *)v9[6];
  *v13 = v12;
  *(_QWORD *)(v12 + 8) = v13;
  v14 = v9[3];
  v15 = (_QWORD *)v9[4];
  *v15 = v14;
  *(_QWORD *)(v14 + 8) = v15;
  ObjectPool<TGenericMap<unsigned __int64,unsigned long,0,5,19>::TABLE_ENTRY,5>::Recycle(a1 + 8);
  v10 = 0;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
  return v10;
}

```

## disassembly

```asm
0x1800305a4  push    rbx
0x1800305a6  push    rbp
0x1800305a7  push    rsi
0x1800305a8  push    rdi
0x1800305a9  push    r14
0x1800305ab  sub     rsp, 20h
0x1800305af  mov     rax, [rcx]
0x1800305b2  mov     r14, r8
0x1800305b5  mov     ebp, edx
0x1800305b7  mov     rdi, rcx
0x1800305ba  mov     rax, [rax+8]
0x1800305be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305c3  mov     r9d, eax
0x1800305c6  lea     rsi, [rdi+180h]
0x1800305cd  mov     rax, 0D79435E50D79435Fh
0x1800305d7  mov     rcx, rsi; lpCriticalSection
0x1800305da  mul     r9
0x1800305dd  shr     rdx, 4
0x1800305e1  imul    rax, rdx, 13h
0x1800305e5  sub     r9, rax
0x1800305e8  mov     ebx, r9d
0x1800305eb  call    cs:__imp_EnterCriticalSection
0x1800305f1  lea     rax, [rbx+4]
0x1800305f5  shl     rax, 4
0x1800305f9  add     rax, rdi
0x1800305fc  mov     rcx, [rax]
0x1800305ff  jmp     short loc_18003060C
0x180030601  lea     rdx, [rcx-28h]
0x180030605  cmp     [rdx], ebp
0x180030607  jz      short loc_18003062C
0x180030609  mov     rcx, [rcx]
0x18003060c  cmp     rcx, rax
0x18003060f  jnz     short loc_180030601
0x180030611  mov     ebx, 80004005h
0x180030616  mov     rcx, rsi; lpCriticalSection
0x180030619  call    cs:__imp_LeaveCriticalSection
0x18003061f  mov     eax, ebx
0x180030621  add     rsp, 20h
0x180030625  pop     r14
0x180030627  pop     rdi
0x180030628  pop     rsi
0x180030629  pop     rbp
0x18003062a  pop     rbx
0x18003062b  retn
0x18003062c  test    rdx, rdx
0x18003062f  jz      short loc_180030611
0x180030631  mov     rax, [rdx+8]
0x180030635  mov     rcx, [rcx]
0x180030638  mov     [r14], rax
0x18003063b  mov     rax, [rdx+30h]
0x18003063f  mov     [rax], rcx
0x180030642  mov     [rcx+8], rax
0x180030646  mov     rcx, [rdx+18h]
0x18003064a  mov     rax, [rdx+20h]
0x18003064e  mov     [rax], rcx
0x180030651  mov     [rcx+8], rax
0x180030655  lea     rcx, [rdi+8]
0x180030659  call    ?Recycle@?$ObjectPool@UTABLE_ENTRY@?$TGenericMap@_KK$0A@$04$0BD@@@$04@@QEAAXPEAUTABLE_ENTRY@?$TGenericMap@_KK$0A@$04$0BD@@@@Z; ObjectPool<TGenericMap<unsigned __int64,ulong,0,5,19>::TABLE_ENTRY,5>::Recycle(TGenericMap<unsigned __int64,ulong,0,5,19>::TABLE_ENTRY *)
0x18003065e  xor     ebx, ebx
0x180030660  jmp     short loc_180030616
```

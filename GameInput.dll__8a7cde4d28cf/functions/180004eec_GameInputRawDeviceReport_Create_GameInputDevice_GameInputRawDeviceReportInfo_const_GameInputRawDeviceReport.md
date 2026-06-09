# GameInputRawDeviceReport::Create(GameInputDevice *,GameInputRawDeviceReportInfo const *,GameInputRawDeviceReport * *)

- ea: `0x180004eec`
- end: `0x1800050b7`
- name: `?Create@GameInputRawDeviceReport@@SAJPEAVGameInputDevice@@PEBUGameInputRawDeviceReportInfo@@PEAPEAV1@@Z`
- size: `459`
- prototype: `__int64 __fastcall(struct GameInputDevice *, const struct GameInputRawDeviceReportInfo *, struct GameInputRawDeviceReport **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180005740`

## callees

- `0x180001304`
- `0x180004eec`
- `0x1800065d8`
- `0x180007e80`
- `0x18000c11c`
- `0x18004c8a5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004f24`
- `ntdll!RtlAllocateHeap` at `0x180004fc4`
- `ntdll!RtlAllocateHeap` at `0x180004f24`
- `ntdll!RtlAllocateHeap` at `0x180004fc4`

## pseudocode

```c
__int64 __fastcall GameInputRawDeviceReport::Create(
        struct GameInputDevice *a1,
        const struct GameInputRawDeviceReportInfo *a2,
        struct GameInputRawDeviceReport **a3)
{
  size_t v3; // r14
  struct _PEB *v5; // rcx
  PVOID Heap; // rdi
  __int64 v9; // r8
  __int64 v10; // r9
  _DWORD *v11; // rax
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  _DWORD *v15; // rbx
  __int64 result; // rax
  unsigned int v17; // eax
  int v18; // [rsp+88h] [rbp+48h] BYREF
  int v19; // [rsp+90h] [rbp+50h] BYREF
  const char *v20; // [rsp+98h] [rbp+58h] BYREF

  v3 = *((unsigned int *)a2 + 2);
  v5 = NtCurrentPeb();
  *a3 = 0;
  Heap = RtlAllocateHeap(v5->ProcessHeap, 0, (unsigned int)v3);
  if ( Heap )
  {
    v11 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
    v15 = v11;
    if ( v11 )
    {
      v11[2] = 0;
      v11[4] = v3;
      *(_QWORD *)v11 = &GameInputRawDeviceReport::`vftable';
      *((_QWORD *)v11 + 3) = Heap;
      *((_QWORD *)v11 + 4) = a1;
      *((_QWORD *)v11 + 5) = a2;
      memset_0(Heap, 0, v3);
      *((_QWORD *)v15 + 6) = 0;
      _InterlockedIncrement(v15 + 2);
      GameInputClient::IncrementGlobalObjectCount();
      ++dword_1800696A0;
      GameInputClientDebugRefCountCheck();
      result = 0;
      *a3 = (struct GameInputRawDeviceReport *)v15;
      return result;
    }
    v17 = dword_180069000;
    *a3 = 0;
    if ( v17 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v18 = -2147024882;
      v19 = 37;
      v20 = "onecore\\xbox\\gameinput\\client\\GameInputRawDeviceReport.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&v20,
        (unsigned __int8 *)&unk_1800594F8,
        v13,
        v14,
        (__int64 **)&v20,
        (__int64)&v19,
        (__int64)&v18);
    }
    operator delete(Heap, v12);
  }
  else if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
  {
    v18 = -2147024882;
    v20 = "onecore\\xbox\\gameinput\\client\\GameInputRawDeviceReport.cpp";
    v19 = 34;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)byte_1800596AD,
      v9,
      v10,
      (__int64 **)&v20,
      (__int64)&v19,
      (__int64)&v18);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004eec  push    rbp
0x180004eee  push    rbx
0x180004eef  push    rsi
0x180004ef0  push    rdi
0x180004ef1  push    r12
0x180004ef3  push    r14
0x180004ef5  push    r15
0x180004ef7  mov     rbp, rsp
0x180004efa  sub     rsp, 40h
0x180004efe  mov     r14d, [rdx+8]
0x180004f02  mov     r12, rcx
0x180004f05  mov     rcx, gs:60h
0x180004f0e  mov     rsi, r8
0x180004f11  mov     r15, rdx
0x180004f14  mov     qword ptr [r8], 0
0x180004f1b  mov     r8d, r14d; Size
0x180004f1e  xor     edx, edx; Flags
0x180004f20  mov     rcx, [rcx+30h]; HeapHandle
0x180004f24  call    cs:__imp_RtlAllocateHeap
0x180004f2b  nop     dword ptr [rax+rax+00h]
0x180004f30  mov     rdi, rax
0x180004f33  test    rax, rax
0x180004f36  jnz     short loc_180004FB1
0x180004f38  mov     eax, cs:dword_180069000
0x180004f3e  cmp     eax, 2
0x180004f41  jbe     loc_1800050A2
0x180004f47  mov     rcx, cs:qword_180069018
0x180004f4e  mov     rax, cs:qword_180069010
0x180004f55  test    al, 1
0x180004f57  jz      loc_1800050A2
0x180004f5d  mov     rax, rcx
0x180004f60  and     eax, 1
0x180004f63  cmp     rax, rcx
0x180004f66  jnz     loc_1800050A2
0x180004f6c  lea     rax, aOnecoreXboxGam_12; "onecore\\xbox\\gameinput\\client\\GameI"...
0x180004f73  mov     [rbp+arg_8], 8007000Eh
0x180004f7a  mov     [rbp+arg_18], rax
0x180004f7e  lea     rdx, byte_1800596AD
0x180004f85  lea     rax, [rbp+arg_8]
0x180004f89  mov     [rbp+arg_10], 22h ; '"'
0x180004f90  mov     [rsp+40h+var_10], rax
0x180004f95  lea     rax, [rbp+arg_10]
0x180004f99  mov     [rsp+40h+var_18], rax
0x180004f9e  lea     rax, [rbp+arg_18]
0x180004fa2  mov     [rsp+40h+var_20], rax
0x180004fa7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180004fac  jmp     loc_1800050A2
0x180004fb1  mov     rcx, gs:60h
0x180004fba  xor     edx, edx; Flags
0x180004fbc  mov     rcx, [rcx+30h]; HeapHandle
0x180004fc0  lea     r8d, [rdx+38h]; Size
0x180004fc4  call    cs:__imp_RtlAllocateHeap
0x180004fcb  nop     dword ptr [rax+rax+00h]
0x180004fd0  mov     rbx, rax
0x180004fd3  test    rax, rax
0x180004fd6  jz      short loc_18000502B
0x180004fd8  mov     dword ptr [rax+8], 0
0x180004fdf  mov     r8, r14; Size
0x180004fe2  lea     rax, ??_7GameInputRawDeviceReport@@6B@; const GameInputRawDeviceReport::`vftable'
0x180004fe9  mov     [rbx+10h], r14d
0x180004fed  xor     edx, edx; Val
0x180004fef  mov     [rbx], rax
0x180004ff2  mov     rcx, rdi; void *
0x180004ff5  mov     [rbx+18h], rdi
0x180004ff9  mov     [rbx+20h], r12
0x180004ffd  mov     [rbx+28h], r15
0x180005001  call    memset_0
0x180005006  mov     qword ptr [rbx+30h], 0
0x18000500e  nop
0x18000500f  lock inc dword ptr [rbx+8]
0x180005013  nop
0x180005014  call    ?IncrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::IncrementGlobalObjectCount(void)
0x180005019  inc     cs:dword_1800696A0
0x18000501f  call    GameInputClientDebugRefCountCheck
0x180005024  xor     eax, eax
0x180005026  mov     [rsi], rbx
0x180005029  jmp     short loc_1800050A7
0x18000502b  mov     eax, cs:dword_180069000
0x180005031  mov     qword ptr [rsi], 0
0x180005038  cmp     eax, 2
0x18000503b  jbe     short loc_18000509A
0x18000503d  mov     rcx, cs:qword_180069018
0x180005044  mov     rax, cs:qword_180069010
0x18000504b  test    al, 1
0x18000504d  jz      short loc_18000509A
0x18000504f  mov     rax, rcx
0x180005052  and     eax, 1
0x180005055  cmp     rax, rcx
0x180005058  jnz     short loc_18000509A
0x18000505a  lea     rcx, [rbp+arg_8]
0x18000505e  mov     [rbp+arg_8], 8007000Eh
0x180005065  mov     [rsp+40h+var_10], rcx
0x18000506a  lea     rax, aOnecoreXboxGam_12; "onecore\\xbox\\gameinput\\client\\GameI"...
0x180005071  lea     rcx, [rbp+arg_10]
0x180005075  mov     [rbp+arg_10], 25h ; '%'
0x18000507c  mov     [rsp+40h+var_18], rcx
0x180005081  lea     rdx, unk_1800594F8
0x180005088  lea     rcx, [rbp+arg_18]
0x18000508c  mov     [rbp+arg_18], rax
0x180005090  mov     [rsp+40h+var_20], rcx
0x180005095  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000509a  mov     rcx, rdi; P
0x18000509d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800050a2  mov     eax, 8007000Eh
0x1800050a7  add     rsp, 40h
0x1800050ab  pop     r15
0x1800050ad  pop     r14
0x1800050af  pop     r12
0x1800050b1  pop     rdi
0x1800050b2  pop     rsi
0x1800050b3  pop     rbx
0x1800050b4  pop     rbp
0x1800050b5  retn
```

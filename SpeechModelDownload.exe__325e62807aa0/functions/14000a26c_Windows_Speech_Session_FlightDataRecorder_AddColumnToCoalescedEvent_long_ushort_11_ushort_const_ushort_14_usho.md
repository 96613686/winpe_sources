# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,ushort [11],ushort const *,ushort [14],ushort const *,ushort [11],ushort const *,ushort [9],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long,ushort const (&)[11],ushort const * const &,ushort const (&)[14],ushort const * const &,ushort const (&)[11],ushort const * const &,ushort const (&)[9],ushort const * const &)

- ea: `0x14000a26c`
- end: `0x14000a3aa`
- name: `??$AddColumnToCoalescedEvent@J$$BY0L@GPEBG$$BY0O@GPEBG$$BY0L@GPEBG$$BY08GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJAEAY0L@$$CBGAEBQEBGAEAY0O@$$CBG323AEAY08$$CBG3@Z`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, unsigned int, __int64, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fdf4`

## callees

- `0x14000365c`
- `0x140003954`
- `0x14000a26c`
- `0x14000a4ac`
- `0x14001d010`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,unsigned short [11],unsigned short const *,unsigned short [14],unsigned short const *,unsigned short [11],unsigned short const *,unsigned short [9],unsigned short const *>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8)
{
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+70h] [rbp+30h] BYREF

  v20 = a3;
  v11 = *a2;
  v20 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(a1, &v20, a3, a4);
  if ( v12 >= 0 )
  {
    v13 = *a6;
    v14 = *a2;
    v20 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v14 = v20;
    }
    a7 = &v20;
    a5 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
            a1,
            &a5,
            L"EngineName",
            v13);
    if ( v12 >= 0 )
    {
      v16 = *a8;
      a5 = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *,unsigned short [11],unsigned short const *,unsigned short [9],unsigned short const *>(
              a1,
              (unsigned int)&a5,
              v15,
              v16);
    }
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  v18 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000a26c  mov     [rsp-18h+arg_0], rbx
0x14000a271  mov     [rsp-18h+arg_10], r8
0x14000a276  mov     [rsp-18h+arg_8], rdx
0x14000a27b  push    rbp
0x14000a27c  push    rsi
0x14000a27d  push    rdi
0x14000a27e  mov     rbp, rsp
0x14000a281  sub     rsp, 40h
0x14000a285  mov     ebx, r9d
0x14000a288  mov     rdi, rdx
0x14000a28b  mov     rsi, rcx
0x14000a28e  mov     rcx, [rdx]
0x14000a291  mov     [rbp+arg_10], rcx
0x14000a295  test    rcx, rcx
0x14000a298  jz      short loc_14000A2A7
0x14000a29a  mov     rax, [rcx]
0x14000a29d  mov     rax, [rax+8]
0x14000a2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2a6  nop
0x14000a2a7  mov     r9d, ebx
0x14000a2aa  lea     rdx, [rbp+arg_10]
0x14000a2ae  mov     rcx, rsi
0x14000a2b1  call    ??$AddColumnToCoalescedEvent@J@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJ@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long)
0x14000a2b6  mov     ebx, eax
0x14000a2b8  test    eax, eax
0x14000a2ba  js      loc_14000A37F
0x14000a2c0  mov     rax, [rbp+arg_28]
0x14000a2c4  mov     rbx, [rax]
0x14000a2c7  mov     rcx, [rdi]
0x14000a2ca  mov     [rbp+arg_10], rcx
0x14000a2ce  test    rcx, rcx
0x14000a2d1  jz      short loc_14000A2E3
0x14000a2d3  mov     rax, [rcx]
0x14000a2d6  mov     rax, [rax+8]
0x14000a2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2df  mov     rcx, [rbp+arg_10]
0x14000a2e3  lea     rax, [rbp+arg_10]
0x14000a2e7  mov     [rbp+arg_30], rax
0x14000a2eb  mov     [rbp+arg_20], rcx
0x14000a2ef  test    rcx, rcx
0x14000a2f2  jz      short loc_14000A301
0x14000a2f4  mov     rax, [rcx]
0x14000a2f7  mov     rax, [rax+8]
0x14000a2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a300  nop
0x14000a301  mov     r9, rbx
0x14000a304  lea     r8, aEnginename; "EngineName"
0x14000a30b  lea     rdx, [rbp+arg_20]
0x14000a30f  mov     rcx, rsi
0x14000a312  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x14000a317  mov     ebx, eax
0x14000a319  test    eax, eax
0x14000a31b  js      short loc_14000A361
0x14000a31d  mov     rax, [rbp+arg_38]
0x14000a321  mov     rbx, [rax]
0x14000a324  mov     rcx, [rbp+arg_10]
0x14000a328  mov     [rbp+arg_20], rcx
0x14000a32c  test    rcx, rcx
0x14000a32f  jz      short loc_14000A33E
0x14000a331  mov     rax, [rcx]
0x14000a334  mov     rax, [rax+8]
0x14000a338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a33d  nop
0x14000a33e  mov     rax, [rbp+arg_58]
0x14000a342  mov     [rsp+40h+var_8], rax
0x14000a347  mov     rax, [rbp+arg_48]
0x14000a34b  mov     [rsp+40h+var_18], rax
0x14000a350  mov     r9, rbx
0x14000a353  lea     rdx, [rbp+arg_20]
0x14000a357  mov     rcx, rsi
0x14000a35a  call    ??$AddColumnToCoalescedEvent@PEBG$$BY0L@GPEBG$$BY08GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGQEBGAEAY0L@$$CBGAEBQEBGAEAY08$$CBG4@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *,ushort [11],ushort const *,ushort [9],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const * const,ushort const (&)[11],ushort const * const &,ushort const (&)[9],ushort const * const &)
0x14000a35f  mov     ebx, eax
0x14000a361  mov     rcx, [rbp+arg_10]
0x14000a365  test    rcx, rcx
0x14000a368  jz      short loc_14000A37F
0x14000a36a  mov     [rbp+arg_10], 0
0x14000a372  mov     rax, [rcx]
0x14000a375  mov     rax, [rax+10h]
0x14000a379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a37e  nop
0x14000a37f  mov     rcx, [rdi]
0x14000a382  test    rcx, rcx
0x14000a385  jz      short loc_14000A39B
0x14000a387  mov     qword ptr [rdi], 0
0x14000a38e  mov     rax, [rcx]
0x14000a391  mov     rax, [rax+10h]
0x14000a395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a39a  nop
0x14000a39b  mov     eax, ebx
0x14000a39d  mov     rbx, [rsp+40h+arg_0]
0x14000a3a2  add     rsp, 40h
0x14000a3a6  pop     rdi
0x14000a3a7  pop     rsi
0x14000a3a8  pop     rbp
0x14000a3a9  retn
```

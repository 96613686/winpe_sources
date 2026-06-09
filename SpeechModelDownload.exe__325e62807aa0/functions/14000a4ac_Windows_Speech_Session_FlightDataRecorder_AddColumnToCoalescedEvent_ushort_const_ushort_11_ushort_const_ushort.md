# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *,ushort [11],ushort const *,ushort [9],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const * const,ushort const (&)[11],ushort const * const &,ushort const (&)[9],ushort const * const &)

- ea: `0x14000a4ac`
- end: `0x14000a5e6`
- name: `??$AddColumnToCoalescedEvent@PEBG$$BY0L@GPEBG$$BY08GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGQEBGAEAY0L@$$CBGAEBQEBGAEAY08$$CBG4@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, __int64, __int64, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a26c`

## callees

- `0x140003954`
- `0x14000a4ac`
- `0x14001d010`

## string_xrefs

- `0x14000a54b`: `LocalePath`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *,unsigned short [11],unsigned short const *,unsigned short [9],unsigned short const *>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8)
{
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // [rsp+50h] [rbp+30h] BYREF

  v19 = a3;
  v11 = *a2;
  v19 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
          a1,
          &v19,
          L"EngineVersion",
          a4);
  if ( v12 >= 0 )
  {
    v13 = *a6;
    v14 = *a2;
    v19 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v14 = v19;
    }
    a7 = &v19;
    a5 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
            a1,
            &a5,
            L"LocalePath",
            v13);
    if ( v12 >= 0 )
    {
      v15 = *a8;
      a5 = v19;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      v12 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *>(
              a1,
              &a5,
              L"ModelUrl",
              v15);
    }
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  v17 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000a4ac  mov     [rsp-18h+arg_0], rbx
0x14000a4b1  mov     [rsp-18h+arg_10], r8
0x14000a4b6  mov     [rsp-18h+arg_8], rdx
0x14000a4bb  push    rbp
0x14000a4bc  push    rsi
0x14000a4bd  push    rdi
0x14000a4be  mov     rbp, rsp
0x14000a4c1  sub     rsp, 20h
0x14000a4c5  mov     rbx, r9
0x14000a4c8  mov     rdi, rdx
0x14000a4cb  mov     rsi, rcx
0x14000a4ce  mov     rcx, [rdx]
0x14000a4d1  mov     [rbp+arg_10], rcx
0x14000a4d5  test    rcx, rcx
0x14000a4d8  jz      short loc_14000A4E7
0x14000a4da  mov     rax, [rcx]
0x14000a4dd  mov     rax, [rax+8]
0x14000a4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4e6  nop
0x14000a4e7  mov     r9, rbx
0x14000a4ea  lea     r8, aEngineversion; "EngineVersion"
0x14000a4f1  lea     rdx, [rbp+arg_10]
0x14000a4f5  mov     rcx, rsi
0x14000a4f8  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x14000a4fd  mov     ebx, eax
0x14000a4ff  test    eax, eax
0x14000a501  js      loc_14000A5BB
0x14000a507  mov     rax, [rbp+arg_28]
0x14000a50b  mov     rbx, [rax]
0x14000a50e  mov     rcx, [rdi]
0x14000a511  mov     [rbp+arg_10], rcx
0x14000a515  test    rcx, rcx
0x14000a518  jz      short loc_14000A52A
0x14000a51a  mov     rax, [rcx]
0x14000a51d  mov     rax, [rax+8]
0x14000a521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a526  mov     rcx, [rbp+arg_10]
0x14000a52a  lea     rax, [rbp+arg_10]
0x14000a52e  mov     [rbp+arg_30], rax
0x14000a532  mov     [rbp+arg_20], rcx
0x14000a536  test    rcx, rcx
0x14000a539  jz      short loc_14000A548
0x14000a53b  mov     rax, [rcx]
0x14000a53e  mov     rax, [rax+8]
0x14000a542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a547  nop
0x14000a548  mov     r9, rbx
0x14000a54b  lea     r8, aLocalepath; "LocalePath"
0x14000a552  lea     rdx, [rbp+arg_20]
0x14000a556  mov     rcx, rsi
0x14000a559  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x14000a55e  mov     ebx, eax
0x14000a560  test    eax, eax
0x14000a562  js      short loc_14000A59D
0x14000a564  mov     rax, [rbp+arg_38]
0x14000a568  mov     rbx, [rax]
0x14000a56b  mov     rcx, [rbp+arg_10]
0x14000a56f  mov     [rbp+arg_20], rcx
0x14000a573  test    rcx, rcx
0x14000a576  jz      short loc_14000A585
0x14000a578  mov     rax, [rcx]
0x14000a57b  mov     rax, [rax+8]
0x14000a57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a584  nop
0x14000a585  mov     r9, rbx
0x14000a588  lea     r8, aModelurl; "ModelUrl"
0x14000a58f  lea     rdx, [rbp+arg_20]
0x14000a593  mov     rcx, rsi
0x14000a596  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x14000a59b  mov     ebx, eax
0x14000a59d  mov     rcx, [rbp+arg_10]
0x14000a5a1  test    rcx, rcx
0x14000a5a4  jz      short loc_14000A5BB
0x14000a5a6  mov     [rbp+arg_10], 0
0x14000a5ae  mov     rax, [rcx]
0x14000a5b1  mov     rax, [rax+10h]
0x14000a5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5ba  nop
0x14000a5bb  mov     rcx, [rdi]
0x14000a5be  test    rcx, rcx
0x14000a5c1  jz      short loc_14000A5D7
0x14000a5c3  mov     qword ptr [rdi], 0
0x14000a5ca  mov     rax, [rcx]
0x14000a5cd  mov     rax, [rax+10h]
0x14000a5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5d6  nop
0x14000a5d7  mov     eax, ebx
0x14000a5d9  mov     rbx, [rsp+20h+arg_0]
0x14000a5de  add     rsp, 20h
0x14000a5e2  pop     rdi
0x14000a5e3  pop     rsi
0x14000a5e4  pop     rbp
0x14000a5e5  retn
```

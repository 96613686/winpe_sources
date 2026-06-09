# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *,ushort [8],ushort const *,ushort [6],ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const * const,ushort const (&)[8],ushort const * const &,ushort const (&)[6],ushort const * const &)

- ea: `0x140013e8c`
- end: `0x140013fc6`
- name: `??$AddColumnToCoalescedEvent@PEBG$$BY07GPEBG$$BY05GPEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGQEBGAEAY07$$CBGAEBQEBGAEAY05$$CBG4@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, __int64, __int64, __int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400180f0`

## callees

- `0x140003954`
- `0x140013e8c`
- `0x14001d010`

## string_xrefs

- `0x140013f68`: `agent`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<unsigned short const *,unsigned short [8],unsigned short const *,unsigned short [6],unsigned short const *>(
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
          L"partner",
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
            L"feature",
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
              L"agent",
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
0x140013e8c  mov     [rsp-18h+arg_0], rbx
0x140013e91  mov     [rsp-18h+arg_10], r8
0x140013e96  mov     [rsp-18h+arg_8], rdx
0x140013e9b  push    rbp
0x140013e9c  push    rsi
0x140013e9d  push    rdi
0x140013e9e  mov     rbp, rsp
0x140013ea1  sub     rsp, 20h
0x140013ea5  mov     rbx, r9
0x140013ea8  mov     rdi, rdx
0x140013eab  mov     rsi, rcx
0x140013eae  mov     rcx, [rdx]
0x140013eb1  mov     [rbp+arg_10], rcx
0x140013eb5  test    rcx, rcx
0x140013eb8  jz      short loc_140013EC7
0x140013eba  mov     rax, [rcx]
0x140013ebd  mov     rax, [rax+8]
0x140013ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ec6  nop
0x140013ec7  mov     r9, rbx
0x140013eca  lea     r8, aPartner; "partner"
0x140013ed1  lea     rdx, [rbp+arg_10]
0x140013ed5  mov     rcx, rsi
0x140013ed8  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x140013edd  mov     ebx, eax
0x140013edf  test    eax, eax
0x140013ee1  js      loc_140013F9B
0x140013ee7  mov     rax, [rbp+arg_28]
0x140013eeb  mov     rbx, [rax]
0x140013eee  mov     rcx, [rdi]
0x140013ef1  mov     [rbp+arg_10], rcx
0x140013ef5  test    rcx, rcx
0x140013ef8  jz      short loc_140013F0A
0x140013efa  mov     rax, [rcx]
0x140013efd  mov     rax, [rax+8]
0x140013f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f06  mov     rcx, [rbp+arg_10]
0x140013f0a  lea     rax, [rbp+arg_10]
0x140013f0e  mov     [rbp+arg_30], rax
0x140013f12  mov     [rbp+arg_20], rcx
0x140013f16  test    rcx, rcx
0x140013f19  jz      short loc_140013F28
0x140013f1b  mov     rax, [rcx]
0x140013f1e  mov     rax, [rax+8]
0x140013f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f27  nop
0x140013f28  mov     r9, rbx
0x140013f2b  lea     r8, aFeature; "feature"
0x140013f32  lea     rdx, [rbp+arg_20]
0x140013f36  mov     rcx, rsi
0x140013f39  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x140013f3e  mov     ebx, eax
0x140013f40  test    eax, eax
0x140013f42  js      short loc_140013F7D
0x140013f44  mov     rax, [rbp+arg_38]
0x140013f48  mov     rbx, [rax]
0x140013f4b  mov     rcx, [rbp+arg_10]
0x140013f4f  mov     [rbp+arg_20], rcx
0x140013f53  test    rcx, rcx
0x140013f56  jz      short loc_140013F65
0x140013f58  mov     rax, [rcx]
0x140013f5b  mov     rax, [rax+8]
0x140013f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f64  nop
0x140013f65  mov     r9, rbx
0x140013f68  lea     r8, aAgent; "agent"
0x140013f6f  lea     rdx, [rbp+arg_20]
0x140013f73  mov     rcx, rsi
0x140013f76  call    ??$AddColumnToCoalescedEvent@PEBG@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG1@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<ushort const *>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,ushort const *)
0x140013f7b  mov     ebx, eax
0x140013f7d  mov     rcx, [rbp+arg_10]
0x140013f81  test    rcx, rcx
0x140013f84  jz      short loc_140013F9B
0x140013f86  mov     [rbp+arg_10], 0
0x140013f8e  mov     rax, [rcx]
0x140013f91  mov     rax, [rax+10h]
0x140013f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f9a  nop
0x140013f9b  mov     rcx, [rdi]
0x140013f9e  test    rcx, rcx
0x140013fa1  jz      short loc_140013FB7
0x140013fa3  mov     qword ptr [rdi], 0
0x140013faa  mov     rax, [rcx]
0x140013fad  mov     rax, [rax+10h]
0x140013fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013fb6  nop
0x140013fb7  mov     eax, ebx
0x140013fb9  mov     rbx, [rsp+20h+arg_0]
0x140013fbe  add     rsp, 20h
0x140013fc2  pop     rdi
0x140013fc3  pop     rsi
0x140013fc4  pop     rbp
0x140013fc5  retn
```

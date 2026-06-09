# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long)

- ea: `0x14000365c`
- end: `0x1400036e2`
- name: `??$AddColumnToCoalescedEvent@J@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJ@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c64`
- `0x14000a26c`
- `0x14000a3b0`

## callees

- `0x14000365c`
- `0x1400036e8`
- `0x14001d010`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  v8 = *a2;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v5 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(a1, &v8, L"hr");
  v6 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x14000365c  mov     rax, rsp
0x14000365f  mov     [rax+8], rbx
0x140003663  mov     [rax+20h], rsi
0x140003667  mov     [rax+18h], r8
0x14000366b  mov     [rax+10h], rdx
0x14000366f  push    rdi
0x140003670  sub     rsp, 20h
0x140003674  mov     edi, r9d
0x140003677  mov     rbx, rdx
0x14000367a  mov     rsi, rcx
0x14000367d  mov     rcx, [rdx]
0x140003680  mov     [rax+18h], rcx
0x140003684  test    rcx, rcx
0x140003687  jz      short loc_140003696
0x140003689  mov     rax, [rcx]
0x14000368c  mov     rax, [rax+8]
0x140003690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003695  nop
0x140003696  movd    xmm3, edi
0x14000369a  cvtdq2pd xmm3, xmm3
0x14000369e  lea     r8, aHr; "hr"
0x1400036a5  lea     rdx, [rsp+28h+arg_10]
0x1400036aa  mov     rcx, rsi
0x1400036ad  call    ??$AddColumnToCoalescedEvent@N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGN@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,double)
0x1400036b2  mov     edi, eax
0x1400036b4  mov     rcx, [rbx]
0x1400036b7  test    rcx, rcx
0x1400036ba  jz      short loc_1400036D0
0x1400036bc  mov     qword ptr [rbx], 0
0x1400036c3  mov     rdx, [rcx]
0x1400036c6  mov     rax, [rdx+10h]
0x1400036ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036cf  nop
0x1400036d0  mov     eax, edi
0x1400036d2  mov     rbx, [rsp+28h+arg_0]
0x1400036d7  mov     rsi, [rsp+28h+arg_18]
0x1400036dc  add     rsp, 20h
0x1400036e0  pop     rdi
0x1400036e1  retn
```

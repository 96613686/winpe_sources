# Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,ushort [14],ulong>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long,ushort const (&)[14],ulong const &)

- ea: `0x14000a3b0`
- end: `0x14000a4a6`
- name: `??$AddColumnToCoalescedEvent@J$$BY0O@GK@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJAEAY0O@$$CBGAEBK@Z`
- size: `246`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d1f4`

## callees

- `0x14000365c`
- `0x1400036e8`
- `0x14000a3b0`
- `0x14001d010`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long,unsigned short [14],unsigned long>(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v8; // rcx
  int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // [rsp+60h] [rbp+30h] BYREF

  v14 = a3;
  v8 = *a2;
  v14 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v9 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(a1, &v14, a3, a4);
  if ( v9 >= 0 )
  {
    v10 = *a2;
    v14 = v10;
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      v10 = v14;
    }
    a5 = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v9 = Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(a1, &a5, L"NumberOfFiles");
    v11 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  v12 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000a3b0  mov     [rsp-18h+arg_0], rbx
0x14000a3b5  mov     [rsp-18h+arg_10], r8
0x14000a3ba  mov     [rsp-18h+arg_8], rdx
0x14000a3bf  push    rbp
0x14000a3c0  push    rsi
0x14000a3c1  push    rdi
0x14000a3c2  mov     rbp, rsp
0x14000a3c5  sub     rsp, 30h
0x14000a3c9  mov     edi, r9d
0x14000a3cc  mov     rbx, rdx
0x14000a3cf  mov     rsi, rcx
0x14000a3d2  mov     rcx, [rdx]
0x14000a3d5  mov     [rbp+arg_10], rcx
0x14000a3d9  test    rcx, rcx
0x14000a3dc  jz      short loc_14000A3EB
0x14000a3de  mov     rax, [rcx]
0x14000a3e1  mov     rax, [rax+8]
0x14000a3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3ea  nop
0x14000a3eb  mov     r9d, edi
0x14000a3ee  lea     rdx, [rbp+arg_10]
0x14000a3f2  mov     rcx, rsi
0x14000a3f5  call    ??$AddColumnToCoalescedEvent@J@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGJ@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<long>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,long)
0x14000a3fa  mov     edi, eax
0x14000a3fc  test    eax, eax
0x14000a3fe  js      short loc_14000A47B
0x14000a400  mov     rax, [rbp+arg_28]
0x14000a404  mov     edi, [rax]
0x14000a406  mov     rcx, [rbx]
0x14000a409  mov     [rbp+arg_10], rcx
0x14000a40d  test    rcx, rcx
0x14000a410  jz      short loc_14000A422
0x14000a412  mov     rax, [rcx]
0x14000a415  mov     rax, [rax+8]
0x14000a419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a41e  mov     rcx, [rbp+arg_10]
0x14000a422  lea     rax, [rbp+arg_10]
0x14000a426  mov     [rbp+var_10], rax
0x14000a42a  mov     [rbp+arg_20], rcx
0x14000a42e  test    rcx, rcx
0x14000a431  jz      short loc_14000A440
0x14000a433  mov     rax, [rcx]
0x14000a436  mov     rax, [rax+8]
0x14000a43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a43f  nop
0x14000a440  xorps   xmm3, xmm3
0x14000a443  cvtsi2sd xmm3, rdi
0x14000a448  lea     r8, aNumberoffiles; "NumberOfFiles"
0x14000a44f  lea     rdx, [rbp+arg_20]
0x14000a453  mov     rcx, rsi
0x14000a456  call    ??$AddColumnToCoalescedEvent@N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGN@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<double>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,double)
0x14000a45b  mov     edi, eax
0x14000a45d  mov     rcx, [rbp+arg_10]
0x14000a461  test    rcx, rcx
0x14000a464  jz      short loc_14000A47B
0x14000a466  mov     [rbp+arg_10], 0
0x14000a46e  mov     rax, [rcx]
0x14000a471  mov     rax, [rax+10h]
0x14000a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47a  nop
0x14000a47b  mov     rcx, [rbx]
0x14000a47e  test    rcx, rcx
0x14000a481  jz      short loc_14000A497
0x14000a483  mov     qword ptr [rbx], 0
0x14000a48a  mov     rax, [rcx]
0x14000a48d  mov     rax, [rax+10h]
0x14000a491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a496  nop
0x14000a497  mov     eax, edi
0x14000a499  mov     rbx, [rsp+30h+arg_0]
0x14000a49e  add     rsp, 30h
0x14000a4a2  pop     rdi
0x14000a4a3  pop     rsi
0x14000a4a4  pop     rbp
0x14000a4a5  retn
```

# Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)

- ea: `0x140005520`
- end: `0x140005660`
- name: `?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c64`
- `0x140004f38`
- `0x1400088c4`
- `0x14000c3d8`
- `0x14000d1f4`
- `0x14000fdf4`
- `0x1400180f0`

## callees

- `0x140005520`
- `0x140005ea0`
- `0x14001d010`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(
        Windows::Speech::Session::FlightDataRecorder *a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *))
{
  __int64 result; // rax
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v7; // rcx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v14; // [rsp+50h] [rbp+30h] BYREF
  __int64 v15; // [rsp+58h] [rbp+38h] BYREF

  v15 = 0;
  v14 = 0;
  result = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(a1);
  if ( (int)result >= 0 && *a2 )
  {
    v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a1 + 9);
    v6 = **v5;
    v7 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    result = v6(v5, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v15);
    if ( (int)result >= 0 )
    {
      v8 = *a2;
      v9 = ***a2;
      v10 = v14;
      if ( v14 )
      {
        v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      result = v9(v8, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v14);
      if ( (int)result >= 0 )
        result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 104LL))(v15, v14);
    }
  }
  v11 = v14;
  if ( v14 )
  {
    v14 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    return ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v13)[2])(v13);
  }
  return result;
}

```

## disassembly

```asm
0x140005520  mov     [rsp-18h+arg_0], rbx
0x140005525  mov     [rsp-18h+arg_8], rdx
0x14000552a  push    rbp
0x14000552b  push    rsi
0x14000552c  push    rdi
0x14000552d  mov     rbp, rsp
0x140005530  sub     rsp, 20h
0x140005534  mov     rbx, rdx
0x140005537  mov     rdi, rcx
0x14000553a  mov     [rbp+arg_18], 0
0x140005542  mov     [rbp+arg_10], 0
0x14000554a  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x14000554f  test    eax, eax
0x140005551  js      loc_1400055FB
0x140005557  cmp     qword ptr [rbx], 0
0x14000555b  jz      loc_1400055FB
0x140005561  mov     rdi, [rdi+48h]
0x140005565  mov     rax, [rdi]
0x140005568  mov     rsi, [rax]
0x14000556b  mov     rcx, [rbp+arg_18]
0x14000556f  test    rcx, rcx
0x140005572  jz      short loc_140005589
0x140005574  mov     [rbp+arg_18], 0
0x14000557c  mov     rdx, [rcx]
0x14000557f  mov     rax, [rdx+10h]
0x140005583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005588  nop
0x140005589  lea     r8, [rbp+arg_18]
0x14000558d  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x140005594  mov     rcx, rdi
0x140005597  mov     rax, rsi
0x14000559a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000559f  nop
0x1400055a0  test    eax, eax
0x1400055a2  js      short loc_1400055FB
0x1400055a4  mov     rdi, [rbx]
0x1400055a7  mov     rax, [rdi]
0x1400055aa  mov     rsi, [rax]
0x1400055ad  mov     rcx, [rbp+arg_10]
0x1400055b1  test    rcx, rcx
0x1400055b4  jz      short loc_1400055CB
0x1400055b6  mov     [rbp+arg_10], 0
0x1400055be  mov     rdx, [rcx]
0x1400055c1  mov     rax, [rdx+10h]
0x1400055c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055ca  nop
0x1400055cb  lea     r8, [rbp+arg_10]
0x1400055cf  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x1400055d6  mov     rcx, rdi
0x1400055d9  mov     rax, rsi
0x1400055dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055e1  nop
0x1400055e2  test    eax, eax
0x1400055e4  js      short loc_1400055FB
0x1400055e6  mov     rcx, [rbp+arg_18]
0x1400055ea  mov     rax, [rcx]
0x1400055ed  mov     rdx, [rbp+arg_10]
0x1400055f1  mov     rax, [rax+68h]
0x1400055f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055fa  nop
0x1400055fb  mov     rcx, [rbp+arg_10]
0x1400055ff  test    rcx, rcx
0x140005602  jz      short loc_140005619
0x140005604  mov     [rbp+arg_10], 0
0x14000560c  mov     rax, [rcx]
0x14000560f  mov     rax, [rax+10h]
0x140005613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005618  nop
0x140005619  mov     rcx, [rbp+arg_18]
0x14000561d  test    rcx, rcx
0x140005620  jz      short loc_140005637
0x140005622  mov     [rbp+arg_18], 0
0x14000562a  mov     rax, [rcx]
0x14000562d  mov     rax, [rax+10h]
0x140005631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005636  nop
0x140005637  mov     rcx, [rbx]
0x14000563a  test    rcx, rcx
0x14000563d  jz      short loc_140005653
0x14000563f  mov     qword ptr [rbx], 0
0x140005646  mov     rax, [rcx]
0x140005649  mov     rax, [rax+10h]
0x14000564d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005652  nop
0x140005653  mov     rbx, [rsp+20h+arg_0]
0x140005658  add     rsp, 20h
0x14000565c  pop     rdi
0x14000565d  pop     rsi
0x14000565e  pop     rbp
0x14000565f  retn
```

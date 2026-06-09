# Windows::Speech::Session::FlightDataRecorder::GetJsonString(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>,Microsoft::WRL::Wrappers::HString *)

- ea: `0x140006720`
- end: `0x140006827`
- name: `?GetJsonString@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@67@@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, _QWORD *, HSTRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005740`
- `0x140015f50`

## callees

- `0x140006720`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400067a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400067a2`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::GetJsonString(__int64 a1, _QWORD *a2, HSTRING *a3)
{
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // [rsp+60h] [rbp+30h]
  __int64 v12; // [rsp+78h] [rbp+48h] BYREF

  v12 = 0;
  v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a2)(
         *a2,
         &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e,
         &v12);
  if ( v5 >= 0 )
  {
    v6 = v12;
    v11 = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v6 = v11;
    }
    if ( a3 )
    {
      v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 56LL);
      WindowsDeleteString(*a3);
      *a3 = 0;
      v5 = v7(v6, a3);
      v6 = v11;
    }
    else
    {
      v5 = -2147024809;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v8 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006720  mov     [rsp-28h+arg_8], rdx
0x140006725  mov     [rsp-28h+arg_0], rcx
0x14000672a  push    rbp
0x14000672b  push    rbx
0x14000672c  push    rsi
0x14000672d  push    rdi
0x14000672e  push    r14
0x140006730  mov     rbp, rsp
0x140006733  sub     rsp, 30h
0x140006737  mov     rsi, r8
0x14000673a  mov     r14, rdx
0x14000673d  mov     [rbp+arg_18], 0
0x140006745  mov     rcx, [rdx]
0x140006748  mov     rax, [rcx]
0x14000674b  lea     r8, [rbp+arg_18]
0x14000674f  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x140006756  mov     rax, [rax]
0x140006759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000675e  mov     ebx, eax
0x140006760  test    eax, eax
0x140006762  js      short loc_1400067E0
0x140006764  mov     rdi, [rbp+arg_18]
0x140006768  mov     [rbp+arg_0], rdi
0x14000676c  test    rdi, rdi
0x14000676f  jz      short loc_140006784
0x140006771  mov     rax, [rdi]
0x140006774  mov     rcx, rdi
0x140006777  mov     rax, [rax+8]
0x14000677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006780  mov     rdi, [rbp+arg_0]
0x140006784  lea     rax, [rbp+arg_0]
0x140006788  mov     [rbp+var_10], rax
0x14000678c  test    rsi, rsi
0x14000678f  jnz     short loc_140006798
0x140006791  mov     ebx, 80070057h
0x140006796  jmp     short loc_1400067C3
0x140006798  mov     rax, [rdi]
0x14000679b  mov     rbx, [rax+38h]
0x14000679f  mov     rcx, [rsi]; string
0x1400067a2  call    cs:__imp_WindowsDeleteString
0x1400067a8  mov     qword ptr [rsi], 0
0x1400067af  mov     rdx, rsi
0x1400067b2  mov     rcx, rdi
0x1400067b5  mov     rax, rbx
0x1400067b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067bd  mov     ebx, eax
0x1400067bf  mov     rdi, [rbp+arg_0]
0x1400067c3  test    rdi, rdi
0x1400067c6  jz      short loc_1400067E0
0x1400067c8  mov     [rbp+arg_0], 0
0x1400067d0  mov     rax, [rdi]
0x1400067d3  mov     rcx, rdi
0x1400067d6  mov     rax, [rax+10h]
0x1400067da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067df  nop
0x1400067e0  mov     rcx, [rbp+arg_18]
0x1400067e4  test    rcx, rcx
0x1400067e7  jz      short loc_1400067FE
0x1400067e9  mov     [rbp+arg_18], 0
0x1400067f1  mov     rax, [rcx]
0x1400067f4  mov     rax, [rax+10h]
0x1400067f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067fd  nop
0x1400067fe  mov     rcx, [r14]
0x140006801  test    rcx, rcx
0x140006804  jz      short loc_14000681A
0x140006806  mov     qword ptr [r14], 0
0x14000680d  mov     rdx, [rcx]
0x140006810  mov     rax, [rdx+10h]
0x140006814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006819  nop
0x14000681a  mov     eax, ebx
0x14000681c  add     rsp, 30h
0x140006820  pop     r14
0x140006822  pop     rdi
0x140006823  pop     rsi
0x140006824  pop     rbx
0x140006825  pop     rbp
0x140006826  retn
```

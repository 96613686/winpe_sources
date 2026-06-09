# Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)

- ea: `0x140005ea0`
- end: `0x140006118`
- name: `?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this)`
- caller_count: `14`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400036e8`
- `0x140003954`
- `0x140003b10`
- `0x140003c64`
- `0x140004f38`
- `0x140005520`
- `0x140005740`
- `0x14000732c`
- `0x1400088c4`
- `0x14000c3d8`
- `0x14000d1f4`
- `0x14000fdf4`
- `0x140015f50`
- `0x1400180f0`

## callees

- `0x140002600`
- `0x140005ea0`
- `0x140007870`
- `0x14001bb90`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140005fc8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006002`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006002`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005f49`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140005f49`

## string_xrefs

- `0x140005fc1`: `Windows.Data.Json.JsonValue`
- `0x140005f07`: `Windows.Data.Json.JsonArray`

## pseudocode

```c
__int64 __fastcall Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(
        Windows::Speech::Session::FlightDataRecorder *this)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ebx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  HSTRING v10; // rbx
  __int64 v11; // rcx
  int ActivationFactory; // eax
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+28h] [rbp-40h] BYREF
  __int64 v22; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h] BYREF

  if ( !*((_BYTE *)this + 10) && !*((_BYTE *)this + 9) )
    return 2147549183LL;
  if ( *((int *)this + 22) >= 0 && (!*((_QWORD *)this + 9) || !*((_QWORD *)this + 10)) )
  {
    v20 = 0;
    v21 = 0;
    string = 0;
    v3 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
    if ( v3 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
      JUMPOUT(0x140006117LL);
    }
    v20 = 0;
    v22 = 0;
    v6 = RoActivateInstance(string, &v22);
    if ( v6 >= 0 )
    {
      if ( !memcmp_0(&GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v20 = v22;
      }
      else
      {
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
               v22,
               &GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81,
               &v20);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    *((_DWORD *)this + 22) = v6;
    if ( v6 >= 0 )
    {
      string = 0;
      v7 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v7 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
        __debugbreak();
      }
      v10 = string;
      v11 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      ActivationFactory = RoGetActivationFactory(v10, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v21);
      *((_DWORD *)this + 22) = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v13 = v20;
        if ( v20 && v21 )
        {
          if ( *((_QWORD *)this + 9) != v20 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
            v14 = *((_QWORD *)this + 9);
            *((_QWORD *)this + 9) = v13;
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          v15 = v21;
          if ( *((_QWORD *)this + 10) == v21 )
            goto LABEL_33;
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
          v16 = *((_QWORD *)this + 10);
          *((_QWORD *)this + 10) = v15;
          if ( !v16 )
            goto LABEL_33;
          goto LABEL_32;
        }
        *((_DWORD *)this + 22) = -2147467259;
      }
    }
    v17 = *((_QWORD *)this + 9);
    if ( v17 )
    {
      *((_QWORD *)this + 9) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v16 = *((_QWORD *)this + 10);
    if ( !v16 )
      goto LABEL_33;
    *((_QWORD *)this + 10) = 0;
LABEL_32:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_33:
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  return *((unsigned int *)this + 22);
}

```

## disassembly

```asm
0x140005ea0  push    rbp
0x140005ea2  push    rbx
0x140005ea3  push    rsi
0x140005ea4  push    rdi
0x140005ea5  mov     rbp, rsp
0x140005ea8  sub     rsp, 68h
0x140005eac  mov     rax, cs:__security_cookie
0x140005eb3  xor     rax, rsp
0x140005eb6  mov     [rbp+var_10], rax
0x140005eba  mov     rdi, rcx
0x140005ebd  xor     esi, esi
0x140005ebf  cmp     [rcx+0Ah], sil
0x140005ec3  jnz     short loc_140005ED5
0x140005ec5  cmp     [rcx+9], sil
0x140005ec9  jnz     short loc_140005ED5
0x140005ecb  mov     eax, 8000FFFFh
0x140005ed0  jmp     loc_1400060F3
0x140005ed5  cmp     [rcx+58h], esi
0x140005ed8  jl      loc_1400060F0
0x140005ede  cmp     [rcx+48h], rsi
0x140005ee2  jz      short loc_140005EEE
0x140005ee4  cmp     [rcx+50h], rsi
0x140005ee8  jnz     loc_1400060F0
0x140005eee  mov     [rbp+var_48], rsi
0x140005ef2  mov     [rbp+var_40], rsi
0x140005ef6  mov     [rbp+string], rsi
0x140005efa  lea     r9, [rbp+string]; string
0x140005efe  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140005f02  mov     edx, 1Bh; length
0x140005f07  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x140005f0e  call    cs:__imp_WindowsCreateStringReference
0x140005f14  test    eax, eax
0x140005f16  js      loc_140006110
0x140005f1c  mov     rbx, [rbp+string]
0x140005f20  mov     rcx, [rbp+var_48]
0x140005f24  test    rcx, rcx
0x140005f27  jz      short loc_140005F3A
0x140005f29  mov     [rbp+var_48], rsi
0x140005f2d  mov     rax, [rcx]
0x140005f30  mov     rax, [rax+10h]
0x140005f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f39  nop
0x140005f3a  mov     [rbp+var_48], rsi
0x140005f3e  mov     [rbp+var_38], rsi
0x140005f42  lea     rdx, [rbp+var_38]
0x140005f46  mov     rcx, rbx
0x140005f49  call    cs:__imp_RoActivateInstance
0x140005f4f  mov     ebx, eax
0x140005f51  test    eax, eax
0x140005f53  js      short loc_140005FA5
0x140005f55  mov     r8d, 10h; Size
0x140005f5b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x140005f62  lea     rcx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81; Buf1
0x140005f69  call    memcmp_0
0x140005f6e  mov     rcx, [rbp+var_38]
0x140005f72  test    eax, eax
0x140005f74  jnz     short loc_140005F7C
0x140005f76  mov     [rbp+var_48], rcx
0x140005f7a  jmp     short loc_140005FA5
0x140005f7c  mov     rax, [rcx]
0x140005f7f  lea     r8, [rbp+var_48]
0x140005f83  lea     rdx, _GUID_08c1ddb6_0cbd_4a9a_b5d3_2f852dc37e81
0x140005f8a  mov     rax, [rax]
0x140005f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f92  mov     ebx, eax
0x140005f94  mov     rcx, [rbp+var_38]
0x140005f98  mov     rax, [rcx]
0x140005f9b  mov     rax, [rax+10h]
0x140005f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fa4  nop
0x140005fa5  mov     [rdi+58h], ebx
0x140005fa8  test    ebx, ebx
0x140005faa  js      loc_140006088
0x140005fb0  mov     [rbp+string], rsi
0x140005fb4  lea     r9, [rbp+string]; string
0x140005fb8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140005fbc  mov     edx, 1Bh; length
0x140005fc1  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x140005fc8  call    cs:__imp_WindowsCreateStringReference
0x140005fce  test    eax, eax
0x140005fd0  js      loc_140006108
0x140005fd6  mov     rbx, [rbp+string]
0x140005fda  mov     rcx, [rbp+var_40]
0x140005fde  test    rcx, rcx
0x140005fe1  jz      short loc_140005FF4
0x140005fe3  mov     [rbp+var_40], rsi
0x140005fe7  mov     rax, [rcx]
0x140005fea  mov     rax, [rax+10h]
0x140005fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ff3  nop
0x140005ff4  lea     r8, [rbp+var_40]
0x140005ff8  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x140005fff  mov     rcx, rbx
0x140006002  call    cs:__imp_RoGetActivationFactory
0x140006008  mov     [rdi+58h], eax
0x14000600b  test    eax, eax
0x14000600d  js      short loc_140006088
0x14000600f  mov     rbx, [rbp+var_48]
0x140006013  test    rbx, rbx
0x140006016  jz      short loc_140006081
0x140006018  cmp     [rbp+var_40], rsi
0x14000601c  jz      short loc_140006081
0x14000601e  cmp     [rdi+48h], rbx
0x140006022  jz      short loc_140006053
0x140006024  test    rbx, rbx
0x140006027  jz      short loc_140006039
0x140006029  mov     rax, [rbx]
0x14000602c  mov     rcx, rbx
0x14000602f  mov     rax, [rax+8]
0x140006033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006038  nop
0x140006039  mov     rcx, [rdi+48h]
0x14000603d  mov     [rdi+48h], rbx
0x140006041  test    rcx, rcx
0x140006044  jz      short loc_140006053
0x140006046  mov     rax, [rcx]
0x140006049  mov     rax, [rax+10h]
0x14000604d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006052  nop
0x140006053  mov     rbx, [rbp+var_40]
0x140006057  cmp     [rdi+50h], rbx
0x14000605b  jz      short loc_1400060BC
0x14000605d  test    rbx, rbx
0x140006060  jz      short loc_140006072
0x140006062  mov     rax, [rbx]
0x140006065  mov     rcx, rbx
0x140006068  mov     rax, [rax+8]
0x14000606c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006071  nop
0x140006072  mov     rcx, [rdi+50h]
0x140006076  mov     [rdi+50h], rbx
0x14000607a  test    rcx, rcx
0x14000607d  jz      short loc_1400060BC
0x14000607f  jmp     short loc_1400060AF
0x140006081  mov     dword ptr [rdi+58h], 80004005h
0x140006088  mov     rcx, [rdi+48h]
0x14000608c  test    rcx, rcx
0x14000608f  jz      short loc_1400060A2
0x140006091  mov     [rdi+48h], rsi
0x140006095  mov     rax, [rcx]
0x140006098  mov     rax, [rax+10h]
0x14000609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060a1  nop
0x1400060a2  mov     rcx, [rdi+50h]
0x1400060a6  test    rcx, rcx
0x1400060a9  jz      short loc_1400060BC
0x1400060ab  mov     [rdi+50h], rsi
0x1400060af  mov     rax, [rcx]
0x1400060b2  mov     rax, [rax+10h]
0x1400060b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060bb  nop
0x1400060bc  mov     rcx, [rbp+var_40]
0x1400060c0  test    rcx, rcx
0x1400060c3  jz      short loc_1400060D6
0x1400060c5  mov     [rbp+var_40], rsi
0x1400060c9  mov     rax, [rcx]
0x1400060cc  mov     rax, [rax+10h]
0x1400060d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060d5  nop
0x1400060d6  mov     rcx, [rbp+var_48]
0x1400060da  test    rcx, rcx
0x1400060dd  jz      short loc_1400060F0
0x1400060df  mov     [rbp+var_48], rsi
0x1400060e3  mov     rax, [rcx]
0x1400060e6  mov     rax, [rax+10h]
0x1400060ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060ef  nop
0x1400060f0  mov     eax, [rdi+58h]
0x1400060f3  mov     rcx, [rbp+var_10]
0x1400060f7  xor     rcx, rsp; StackCookie
0x1400060fa  call    __security_check_cookie
0x1400060ff  add     rsp, 68h
0x140006103  pop     rdi
0x140006104  pop     rsi
0x140006105  pop     rbx
0x140006106  pop     rbp
0x140006107  retn
0x140006108  mov     ecx, eax; this
0x14000610a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000610f  int     3; Trap to Debugger
0x140006110  mov     ecx, eax; this
0x140006112  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

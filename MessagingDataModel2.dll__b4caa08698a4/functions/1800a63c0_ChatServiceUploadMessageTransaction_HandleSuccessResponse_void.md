# ChatServiceUploadMessageTransaction::_HandleSuccessResponse(void)

- ea: `0x1800a63c0`
- end: `0x1800a6727`
- name: `?_HandleSuccessResponse@ChatServiceUploadMessageTransaction@@EEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(ChatServiceUploadMessageTransaction *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x180030bd0`
- `0x18008f260`
- `0x180092840`
- `0x180096400`
- `0x1800a2920`
- `0x1800a622c`
- `0x1800a63c0`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a64f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a64f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a649c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a64d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a652c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a658f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a66d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a649c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a64d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a652c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a658f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a6652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a66d5`

## pseudocode

```c
__int64 __fastcall ChatServiceUploadMessageTransaction::_HandleSuccessResponse(
        ChatServiceUploadMessageTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  __int64 v20; // [rsp+40h] [rbp-9h] BYREF
  _OWORD v21[2]; // [rsp+48h] [rbp-1h] BYREF
  _OWORD v22[2]; // [rsp+68h] [rbp+1Fh] BYREF

  v2 = *((_QWORD *)this + 2);
  v18 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 64LL))(v2, &v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    Log_HREvent_81(v3);
    goto LABEL_3;
  }
  v20 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 104LL))(v18, &v20);
  v4 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent_81(v7);
    goto LABEL_8;
  }
  v9 = v20;
  string = 0;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = v10(v9, &string);
  v4 = v11;
  if ( v11 < 0 )
  {
    Log_HREvent_81(v11);
LABEL_12:
    WindowsDeleteString(string);
    string = 0;
LABEL_8:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v8 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v4;
  }
  memset(v21, 0, sizeof(v21));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v21);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v21,
                           StringRawBuffer) )
  {
    Log_HREvent_81(-2147024882);
    goto LABEL_15;
  }
  if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::find_last_of(v21) == -1 )
  {
    v4 = -2147024809;
    Log_HREvent_81(-2147024809);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
LABEL_3:
    v5 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v4;
  }
  memset(v22, 0, sizeof(v22));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v22);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v22,
                           v21,
                           v14 + 1,
                           ((__int64)(*((_QWORD *)&v21[0] + 1) - *(_QWORD *)&v21[0]) >> 1) - v14 - 1) )
  {
    Log_HREvent_81(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
LABEL_15:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v13 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           *((_QWORD *)this + 12) + 56LL,
                           *(_QWORD *)&v22[0]) )
  {
    Log_HREvent_68(-2147024882);
    Log_HREvent_81(-2147024882);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v15 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return 2147942414LL;
  }
  v16 = ChatServiceTransaction::_HandleSuccessResponse(this);
  v4 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent_81(v16);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
    goto LABEL_12;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v17 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a63c0  mov     [rsp-8+arg_8], rbx
0x1800a63c5  mov     [rsp-8+arg_10], rsi
0x1800a63ca  push    rbp
0x1800a63cb  push    rdi
0x1800a63cc  push    r14
0x1800a63ce  lea     rbp, [rsp-47h]
0x1800a63d3  sub     rsp, 90h
0x1800a63da  mov     rax, cs:__security_cookie
0x1800a63e1  xor     rax, rsp
0x1800a63e4  mov     [rbp+57h+var_18], rax
0x1800a63e8  mov     rsi, rcx
0x1800a63eb  lea     rdx, [rbp+57h+var_70]
0x1800a63ef  mov     rcx, [rcx+10h]
0x1800a63f3  xor     r14d, r14d
0x1800a63f6  mov     [rbp+57h+var_70], r14
0x1800a63fa  mov     rax, [rcx]
0x1800a63fd  mov     rax, [rax+40h]
0x1800a6401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6406  mov     ebx, eax
0x1800a6408  test    eax, eax
0x1800a640a  jns     short loc_1800A643E
0x1800a640c  lea     edx, [r14+1]
0x1800a6410  mov     ecx, eax; int
0x1800a6412  lea     r9d, [r14+7Bh]
0x1800a6416  call    Log_HREvent_81
0x1800a641b  mov     rdx, [rbp+57h+var_70]
0x1800a641f  test    rdx, rdx
0x1800a6422  jz      short loc_1800A6437
0x1800a6424  mov     [rbp+57h+var_70], r14
0x1800a6428  mov     rcx, [rdx]
0x1800a642b  mov     rax, [rcx+10h]
0x1800a642f  mov     rcx, rdx
0x1800a6432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6437  mov     eax, ebx
0x1800a6439  jmp     loc_1800A6703
0x1800a643e  mov     rcx, [rbp+57h+var_70]
0x1800a6442  lea     rdx, [rbp+57h+var_60]
0x1800a6446  mov     [rbp+57h+var_60], r14
0x1800a644a  mov     rax, [rcx]
0x1800a644d  mov     rax, [rax+68h]
0x1800a6451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6456  mov     ebx, eax
0x1800a6458  test    eax, eax
0x1800a645a  jns     short loc_1800A648B
0x1800a645c  mov     edx, 1
0x1800a6461  mov     ecx, eax; int
0x1800a6463  lea     r9d, [rdx+7Dh]
0x1800a6467  call    Log_HREvent_81
0x1800a646c  lea     rcx, [rbp+57h+var_60]
0x1800a6470  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a6475  mov     rcx, [rbp+57h+var_70]
0x1800a6479  test    rcx, rcx
0x1800a647c  jz      short loc_1800A6437
0x1800a647e  mov     [rbp+57h+var_70], r14
0x1800a6482  mov     rax, [rcx]
0x1800a6485  mov     rax, [rax+10h]
0x1800a6489  jmp     short loc_1800A6432
0x1800a648b  mov     rdi, [rbp+57h+var_60]
0x1800a648f  xor     ecx, ecx; string
0x1800a6491  mov     [rbp+57h+string], r14
0x1800a6495  mov     rax, [rdi]
0x1800a6498  mov     rbx, [rax+68h]
0x1800a649c  call    cs:__imp_WindowsDeleteString
0x1800a64a2  lea     rdx, [rbp+57h+string]
0x1800a64a6  mov     [rbp+57h+string], r14
0x1800a64aa  mov     rcx, rdi
0x1800a64ad  mov     rax, rbx
0x1800a64b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a64b5  mov     ebx, eax
0x1800a64b7  test    eax, eax
0x1800a64b9  jns     short loc_1800A64DD
0x1800a64bb  mov     edx, 1
0x1800a64c0  mov     r9d, 81h
0x1800a64c6  mov     ecx, eax; int
0x1800a64c8  call    Log_HREvent_81
0x1800a64cd  mov     rcx, [rbp+57h+string]; string
0x1800a64d1  call    cs:__imp_WindowsDeleteString
0x1800a64d7  mov     [rbp+57h+string], r14
0x1800a64db  jmp     short loc_1800A646C
0x1800a64dd  xorps   xmm0, xmm0
0x1800a64e0  lea     rcx, [rbp+57h+var_58]
0x1800a64e4  movups  [rbp+57h+var_58], xmm0
0x1800a64e8  movups  [rbp+57h+var_48], xmm0
0x1800a64ec  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a64f1  mov     rcx, [rbp+57h+string]; string
0x1800a64f5  xor     edx, edx; length
0x1800a64f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a64fd  mov     rdx, rax
0x1800a6500  lea     rcx, [rbp+57h+var_58]
0x1800a6504  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a6509  test    al, al
0x1800a650b  jnz     short loc_1800A655C
0x1800a650d  xor     edx, edx
0x1800a650f  mov     ecx, 8007000Eh; int
0x1800a6514  mov     r9d, 84h
0x1800a651a  call    Log_HREvent_81
0x1800a651f  lea     rcx, [rbp+57h+var_58]
0x1800a6523  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a6528  mov     rcx, [rbp+57h+string]; string
0x1800a652c  call    cs:__imp_WindowsDeleteString
0x1800a6532  lea     rcx, [rbp+57h+var_60]
0x1800a6536  mov     [rbp+57h+string], r14
0x1800a653a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a653f  mov     rcx, [rbp+57h+var_70]
0x1800a6543  test    rcx, rcx
0x1800a6546  jz      loc_1800A6681
0x1800a654c  mov     [rbp+57h+var_70], r14
0x1800a6550  mov     rax, [rcx]
0x1800a6553  mov     rax, [rax+10h]
0x1800a6557  jmp     loc_1800A667C
0x1800a655c  lea     rcx, [rbp+57h+var_58]
0x1800a6560  call    ?find_last_of@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::find_last_of(ushort const *,unsigned __int64)
0x1800a6565  mov     r8, rax
0x1800a6568  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a656c  jnz     short loc_1800A65A7
0x1800a656e  mov     ebx, 80070057h
0x1800a6573  xor     edx, edx
0x1800a6575  mov     ecx, ebx; int
0x1800a6577  mov     r9d, 87h
0x1800a657d  call    Log_HREvent_81
0x1800a6582  lea     rcx, [rbp+57h+var_58]
0x1800a6586  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a658b  mov     rcx, [rbp+57h+string]; string
0x1800a658f  call    cs:__imp_WindowsDeleteString
0x1800a6595  lea     rcx, [rbp+57h+var_60]
0x1800a6599  mov     [rbp+57h+string], r14
0x1800a659d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a65a2  jmp     loc_1800A641B
0x1800a65a7  xorps   xmm0, xmm0
0x1800a65aa  lea     rcx, [rbp+57h+var_38]
0x1800a65ae  movups  [rbp+57h+var_38], xmm0
0x1800a65b2  movups  [rbp+57h+var_28], xmm0
0x1800a65b6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a65bb  mov     r9, qword ptr [rbp+57h+var_58+8]
0x1800a65bf  lea     rdx, [rbp+57h+var_58]
0x1800a65c3  sub     r9, qword ptr [rbp+57h+var_58]
0x1800a65c7  lea     rcx, [rbp+57h+var_38]
0x1800a65cb  sar     r9, 1
0x1800a65ce  sub     r9, r8
0x1800a65d1  dec     r9
0x1800a65d4  inc     r8
0x1800a65d7  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NAEBV12@_K1@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,unsigned __int64,unsigned __int64)
0x1800a65dc  test    al, al
0x1800a65de  jnz     short loc_1800A6600
0x1800a65e0  xor     edx, edx
0x1800a65e2  mov     ecx, 8007000Eh; int
0x1800a65e7  mov     r9d, 8Ch
0x1800a65ed  call    Log_HREvent_81
0x1800a65f2  lea     rcx, [rbp+57h+var_38]
0x1800a65f6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a65fb  jmp     loc_1800A651F
0x1800a6600  mov     rcx, [rsi+60h]
0x1800a6604  mov     rdx, qword ptr [rbp+57h+var_38]
0x1800a6608  add     rcx, 38h ; '8'
0x1800a660c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a6611  test    al, al
0x1800a6613  jnz     short loc_1800A6688
0x1800a6615  xor     edx, edx
0x1800a6617  mov     ecx, 8007000Eh; int
0x1800a661c  mov     r9d, 0BBh
0x1800a6622  call    Log_HREvent_68
0x1800a6627  mov     edx, 1
0x1800a662c  mov     ecx, 8007000Eh; int
0x1800a6631  mov     r9d, 8Eh
0x1800a6637  call    Log_HREvent_81
0x1800a663c  lea     rcx, [rbp+57h+var_38]
0x1800a6640  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a6645  lea     rcx, [rbp+57h+var_58]
0x1800a6649  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a664e  mov     rcx, [rbp+57h+string]; string
0x1800a6652  call    cs:__imp_WindowsDeleteString
0x1800a6658  lea     rcx, [rbp+57h+var_60]
0x1800a665c  mov     [rbp+57h+string], r14
0x1800a6660  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a6665  mov     rdx, [rbp+57h+var_70]
0x1800a6669  test    rdx, rdx
0x1800a666c  jz      short loc_1800A6681
0x1800a666e  mov     [rbp+57h+var_70], r14
0x1800a6672  mov     rcx, [rdx]
0x1800a6675  mov     rax, [rcx+10h]
0x1800a6679  mov     rcx, rdx
0x1800a667c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6681  mov     eax, 8007000Eh
0x1800a6686  jmp     short loc_1800A6703
0x1800a6688  mov     rcx, rsi; this
0x1800a668b  call    ?_HandleSuccessResponse@ChatServiceTransaction@@MEAAJXZ; ChatServiceTransaction::_HandleSuccessResponse(void)
0x1800a6690  mov     ebx, eax
0x1800a6692  test    eax, eax
0x1800a6694  jns     short loc_1800A66BF
0x1800a6696  mov     edx, 1
0x1800a669b  mov     r9d, 91h
0x1800a66a1  mov     ecx, eax; int
0x1800a66a3  call    Log_HREvent_81
0x1800a66a8  lea     rcx, [rbp+57h+var_38]
0x1800a66ac  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a66b1  lea     rcx, [rbp+57h+var_58]
0x1800a66b5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a66ba  jmp     loc_1800A64CD
0x1800a66bf  lea     rcx, [rbp+57h+var_38]
0x1800a66c3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a66c8  lea     rcx, [rbp+57h+var_58]
0x1800a66cc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a66d1  mov     rcx, [rbp+57h+string]; string
0x1800a66d5  call    cs:__imp_WindowsDeleteString
0x1800a66db  lea     rcx, [rbp+57h+var_60]
0x1800a66df  mov     [rbp+57h+string], r14
0x1800a66e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a66e8  mov     rcx, [rbp+57h+var_70]
0x1800a66ec  test    rcx, rcx
0x1800a66ef  jz      short loc_1800A6701
0x1800a66f1  mov     [rbp+57h+var_70], r14
0x1800a66f5  mov     rax, [rcx]
0x1800a66f8  mov     rax, [rax+10h]
0x1800a66fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6701  xor     eax, eax
0x1800a6703  mov     rcx, [rbp+57h+var_18]
0x1800a6707  xor     rcx, rsp; StackCookie
0x1800a670a  call    __security_check_cookie
0x1800a670f  lea     r11, [rsp+0A0h+var_10]
0x1800a6717  mov     rbx, [r11+28h]
0x1800a671b  mov     rsi, [r11+30h]
0x1800a671f  mov     rsp, r11
0x1800a6722  pop     r14
0x1800a6724  pop     rdi
0x1800a6725  pop     rbp
0x1800a6726  retn
```

# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToastActionsXml(PH_CALL_INFO const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180012eb0`
- end: `0x1800130ba`
- name: `?_BuildIncomingCallToastActionsXml@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJAEBUPH_CALL_INFO@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180011e68`
- `0x180012eb0`
- `0x180015748`
- `0x180019010`

## import_xrefs

- `PhoneOm!PhoneGetAvailableActions` at `0x180012f52`
- `PhoneOm!PhoneGetAvailableActions` at `0x180012f52`
- `PhoneOm!PhoneGetCallCounts` at `0x180012f07`
- `PhoneOm!PhoneGetCallCounts` at `0x180012f07`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToastActionsXml(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _WORD *v3; // r9
  int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // ebx
  unsigned int v11; // edi
  int AvailableActions; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // esi
  __int64 v18; // r8
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+4Ah] [rbp-B6h]
  int v23; // [rsp+52h] [rbp-AEh]
  __int16 v24; // [rsp+56h] [rbp-AAh]
  _OWORD v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h]
  _BYTE v27[68]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v28; // [rsp+D4h] [rbp-2Ch]

  v3 = *(_WORD **)a3;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  *v3 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v7 = PhoneGetCallCounts(v25);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v11 = DWORD2(v26) - DWORD1(v26) - DWORD2(v25[0]);
    v19 = 39;
    AvailableActions = PhoneGetAvailableActions(a2 + 3044, v27, &v19);
    if ( AvailableActions < 0 )
      Log_HREvent_1((unsigned int)AvailableActions, 0, v13, 463);
    v14 = 0;
    while ( 1 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int))(*(_QWORD *)a1 + 136LL))(
             a1,
             a2,
             v11,
             v28,
             v14) )
      {
        v22 = 0;
        v24 = 0;
        v23 = 0;
        Block[0] = &v21;
        Block[1] = &v21;
        v21 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, void **))(*(_QWORD *)a1 + 144LL))(
                a1,
                v14,
                a2 + 3044,
                Block);
        v17 = v15;
        if ( v15 < 0 )
        {
          Log_HREvent_1((unsigned int)v15, 1, v16, 472);
          if ( Block[0] != &v21 )
            operator delete(Block[0]);
          return v17;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 a3,
                                 Block) )
        {
          v9 = -2147024882;
          Log_HREvent_1(2147942414LL, 0, v18, 473);
          if ( Block[0] != &v21 )
            operator delete(Block[0]);
          return v9;
        }
        if ( Block[0] != &v21 )
          operator delete(Block[0]);
      }
      if ( (int)++v14 >= 7 )
        return 0;
    }
  }
  Log_HREvent_1((unsigned int)v7, 1, v8, 455);
  return v9;
}

```

## disassembly

```asm
0x180012eb0  mov     [rsp-8+arg_18], rbx
0x180012eb5  push    rbp
0x180012eb6  push    rsi
0x180012eb7  push    rdi
0x180012eb8  push    r12
0x180012eba  push    r13
0x180012ebc  push    r14
0x180012ebe  push    r15
0x180012ec0  lea     rbp, [rsp-40h]
0x180012ec5  sub     rsp, 140h
0x180012ecc  mov     rax, cs:__security_cookie
0x180012ed3  xor     rax, rsp
0x180012ed6  mov     [rbp+70h+var_40], rax
0x180012eda  mov     r9, [r8]
0x180012edd  xorps   xmm0, xmm0
0x180012ee0  xor     eax, eax
0x180012ee2  mov     [r8+8], r9
0x180012ee6  mov     r15, rcx
0x180012ee9  mov     r14, r8
0x180012eec  lea     rcx, [rsp+170h+var_118]
0x180012ef1  mov     r13, rdx
0x180012ef4  mov     [r9], ax
0x180012ef8  movups  [rsp+170h+var_118], xmm0
0x180012efd  movups  [rsp+170h+var_108], xmm0
0x180012f02  movups  [rsp+170h+var_F8], xmm0
0x180012f07  call    cs:__imp_PhoneGetCallCounts
0x180012f0d  mov     ebx, eax
0x180012f0f  test    eax, eax
0x180012f11  jns     short loc_180012F2C
0x180012f13  mov     edx, 1
0x180012f18  mov     r9d, 1C7h
0x180012f1e  mov     ecx, eax
0x180012f20  call    Log_HREvent_1
0x180012f25  mov     eax, ebx
0x180012f27  jmp     loc_180013027
0x180012f2c  mov     edi, dword ptr [rbp+70h+var_F8+8]
0x180012f2f  lea     r12, [r13+0BE4h]
0x180012f36  sub     edi, dword ptr [rsp+170h+var_F8+4]
0x180012f3a  lea     r8, [rsp+170h+var_140]
0x180012f3f  sub     edi, dword ptr [rsp+170h+var_118+8]
0x180012f43  lea     rdx, [rbp+70h+var_E0]
0x180012f47  mov     rcx, r12
0x180012f4a  mov     [rsp+170h+var_140], 27h ; '''
0x180012f52  call    cs:__imp_PhoneGetAvailableActions
0x180012f58  test    eax, eax
0x180012f5a  jns     short loc_180012F6B
0x180012f5c  xor     edx, edx
0x180012f5e  mov     r9d, 1CFh
0x180012f64  mov     ecx, eax
0x180012f66  call    Log_HREvent_1
0x180012f6b  xor     ebx, ebx
0x180012f6d  mov     rax, [r15]
0x180012f70  mov     r8d, edi
0x180012f73  mov     r9d, [rbp+70h+var_9C]
0x180012f77  mov     rdx, r13
0x180012f7a  mov     rcx, r15
0x180012f7d  mov     [rsp+170h+var_150], ebx
0x180012f81  mov     rax, [rax+88h]
0x180012f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f8d  test    al, al
0x180012f8f  jz      loc_18001301A
0x180012f95  xor     eax, eax
0x180012f97  mov     [rsp+170h+var_126], 0
0x180012fa0  mov     [rsp+170h+var_11A], ax
0x180012fa5  lea     r9, [rsp+170h+Block]
0x180012faa  lea     rax, [rsp+170h+var_128]
0x180012faf  mov     [rsp+170h+var_11E], 0
0x180012fb7  mov     [rsp+170h+Block], rax
0x180012fbc  mov     r8, r12
0x180012fbf  lea     rax, [rsp+170h+var_128]
0x180012fc4  mov     edx, ebx
0x180012fc6  mov     [rsp+170h+var_130], rax
0x180012fcb  mov     rcx, r15
0x180012fce  xor     eax, eax
0x180012fd0  mov     [rsp+170h+var_128], ax
0x180012fd5  mov     rax, [r15]
0x180012fd8  mov     rax, [rax+90h]
0x180012fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fe4  mov     esi, eax
0x180012fe6  test    eax, eax
0x180012fe8  js      loc_180013086
0x180012fee  lea     rdx, [rsp+170h+Block]
0x180012ff3  mov     rcx, r14
0x180012ff6  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NAEBV12@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180012ffb  test    al, al
0x180012ffd  jz      short loc_18001304E
0x180012fff  mov     rcx, [rsp+170h+Block]; Block
0x180013004  lea     rax, [rsp+170h+var_128]
0x180013009  cmp     rcx, rax
0x18001300c  jz      short loc_18001301A
0x18001300e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013015  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001301a  inc     ebx
0x18001301c  cmp     ebx, 7
0x18001301f  jl      loc_180012F6D
0x180013025  xor     eax, eax
0x180013027  mov     rcx, [rbp+70h+var_40]
0x18001302b  xor     rcx, rsp; StackCookie
0x18001302e  call    __security_check_cookie
0x180013033  mov     rbx, [rsp+170h+arg_18]
0x18001303b  add     rsp, 140h
0x180013042  pop     r15
0x180013044  pop     r14
0x180013046  pop     r13
0x180013048  pop     r12
0x18001304a  pop     rdi
0x18001304b  pop     rsi
0x18001304c  pop     rbp
0x18001304d  retn
0x18001304e  mov     ebx, 8007000Eh
0x180013053  xor     edx, edx
0x180013055  mov     ecx, ebx
0x180013057  mov     r9d, 1D9h
0x18001305d  call    Log_HREvent_1
0x180013062  mov     rcx, [rsp+170h+Block]; Block
0x180013067  lea     r8, [rsp+170h+var_128]
0x18001306c  cmp     rcx, r8
0x18001306f  jz      loc_180012F25
0x180013075  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001307c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013081  jmp     loc_180012F25
0x180013086  mov     edx, 1
0x18001308b  mov     r9d, 1D8h
0x180013091  mov     ecx, esi
0x180013093  call    Log_HREvent_1
0x180013098  mov     rcx, [rsp+170h+Block]; Block
0x18001309d  lea     rax, [rsp+170h+var_128]
0x1800130a2  cmp     rcx, rax
0x1800130a5  jz      short loc_1800130B3
0x1800130a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800130ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800130b3  mov     eax, esi
0x1800130b5  jmp     loc_180013027
```

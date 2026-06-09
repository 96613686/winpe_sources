# Streaming::StreamFaultManager::CreateWriteFault(_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,bool)

- ea: `0x14000de2c`
- end: `0x14000e082`
- name: `?CreateWriteFault@StreamFaultManager@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@_N@Z`
- size: `598`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140014ff0`

## callees

- `0x14000da20`
- `0x14000db20`
- `0x14000de2c`
- `0x14000e46c`
- `0x140014dcc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000defe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000defe`
- `ntoskrnl!ExAllocatePool2` at `0x14000de5e`
- `ntoskrnl!ExAllocatePool2` at `0x14000dea3`
- `ntoskrnl!ExAllocatePool2` at `0x14000de5e`
- `ntoskrnl!ExAllocatePool2` at `0x14000dea3`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFaultManager::CreateWriteFault(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  int v4; // r15d
  __int64 Pool2; // rax
  __int64 v10; // rax
  Streaming::WriteFault *v11; // rbx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rdi
  __int64 v14; // r14
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rax
  volatile signed __int32 *v17; // rcx
  unsigned int v18; // edi
  int v20; // eax
  int v21; // [rsp+20h] [rbp-68h] BYREF
  Streaming::WriteFault *v22; // [rsp+28h] [rbp-60h] BYREF
  __int64 v23; // [rsp+30h] [rbp-58h]

  v4 = 0;
  v21 = 0;
  Pool2 = ExAllocatePool2(64, 72, 1718838899);
  if ( Pool2 )
  {
    v10 = Streaming::WriteFault::WriteFault(Pool2, a2, a3, &v21);
    v4 = v21;
    v11 = (Streaming::WriteFault *)v10;
  }
  else
  {
    v11 = 0;
  }
  v22 = v11;
  v12 = ExAllocatePool2(256, 24, 1715758931);
  v13 = (volatile signed __int32 *)v12;
  if ( v12 )
  {
    *(_QWORD *)(v12 + 16) = v11;
    *(_DWORD *)(v12 + 8) = 1;
    v14 = v12 + 8;
    *(_DWORD *)(v12 + 12) = 1;
    v15 = (volatile signed __int32 *)v12;
    v23 = v12;
    *(_QWORD *)v12 = &kernel_std::detail::sp_counted_impl_p<Streaming::WriteFault>::`vftable';
    if ( *(_DWORD *)(v12 + 8) )
      goto LABEL_11;
  }
  else
  {
    v13 = 0;
    v23 = 0;
    if ( v11 )
    {
      Streaming::WriteFault::~WriteFault(v11);
      ExFreePoolWithTag(v11, 0);
    }
    v15 = 0;
    v14 = 8;
  }
  v11 = 0;
  v22 = 0;
LABEL_11:
  if ( !v11 )
  {
    *(_DWORD *)(a2 + 24) = -1073741670;
    goto LABEL_13;
  }
  if ( v4 < 0 )
  {
    *(_DWORD *)(a2 + 24) = v4;
LABEL_13:
    *(_QWORD *)(a2 + 32) = 0;
    if ( !v15 )
      return 4;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) != 1 )
      return 4;
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) != 1 )
      return 4;
    v16 = *(_QWORD *)v15;
    v17 = v15;
LABEL_30:
    (*(void (__fastcall **)(volatile signed __int32 *))(v16 + 16))(v17);
    return 4;
  }
  if ( a4 )
  {
    v20 = appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::QueueWorkItem(
            a1 + 216,
            &v22);
    if ( v20 < 0 )
    {
      *(_DWORD *)(a2 + 24) = v20;
      *(_QWORD *)(a2 + 32) = 0;
      if ( !v13 )
        return 4;
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) != 1 )
        return 4;
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) != 1 )
        return 4;
      v16 = *(_QWORD *)v13;
      v17 = v13;
      goto LABEL_30;
    }
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    return 2;
  }
  else
  {
    v18 = Streaming::WriteFault::ProcessFault(v11);
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    return v18;
  }
}

```

## disassembly

```asm
0x14000de2c  push    rbx
0x14000de2e  push    rbp
0x14000de2f  push    rsi
0x14000de30  push    rdi
0x14000de31  push    r12
0x14000de33  push    r13
0x14000de35  push    r14
0x14000de37  push    r15
0x14000de39  sub     rsp, 48h
0x14000de3d  xor     r15d, r15d
0x14000de40  mov     rbp, rdx
0x14000de43  mov     rbx, r8
0x14000de46  mov     [rsp+88h+var_68], r15d
0x14000de4b  mov     r13, rcx
0x14000de4e  mov     r8d, 66736673h
0x14000de54  mov     r12b, r9b
0x14000de57  lea     edx, [r15+48h]
0x14000de5b  lea     ecx, [rdx-8]
0x14000de5e  call    cs:__imp_ExAllocatePool2
0x14000de65  nop     dword ptr [rax+rax+00h]
0x14000de6a  test    rax, rax
0x14000de6d  jz      short loc_14000DE8C
0x14000de6f  lea     r9, [rsp+88h+var_68]
0x14000de74  mov     r8, rbx
0x14000de77  mov     rdx, rbp
0x14000de7a  mov     rcx, rax
0x14000de7d  call    ??0WriteFault@Streaming@@QEAA@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@AEAJ@Z; Streaming::WriteFault::WriteFault(_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,long &)
0x14000de82  mov     r15d, [rsp+88h+var_68]
0x14000de87  mov     rbx, rax
0x14000de8a  jmp     short loc_14000DE8E
0x14000de8c  xor     ebx, ebx
0x14000de8e  mov     edx, 18h
0x14000de93  mov     [rsp+88h+var_60], rbx
0x14000de98  mov     ecx, 100h
0x14000de9d  mov     r8d, 66446753h
0x14000dea3  call    cs:__imp_ExAllocatePool2
0x14000deaa  nop     dword ptr [rax+rax+00h]
0x14000deaf  mov     rdi, rax
0x14000deb2  test    rax, rax
0x14000deb5  jz      short loc_14000DEE5
0x14000deb7  mov     eax, 1
0x14000debc  mov     [rdi+10h], rbx
0x14000dec0  mov     [rdi+8], eax
0x14000dec3  lea     r14, [rdi+8]
0x14000dec7  mov     [rdi+0Ch], eax
0x14000deca  mov     rsi, rdi
0x14000decd  lea     rax, ??_7?$sp_counted_impl_p@VWriteFault@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::WriteFault>::`vftable'
0x14000ded4  mov     [rsp+88h+var_58], rdi
0x14000ded9  mov     [rdi], rax
0x14000dedc  mov     ecx, [r14]
0x14000dedf  test    ecx, ecx
0x14000dee1  jnz     short loc_14000DF17
0x14000dee3  jmp     short loc_14000DF10
0x14000dee5  xor     edi, edi
0x14000dee7  mov     [rsp+88h+var_58], rdi
0x14000deec  test    rbx, rbx
0x14000deef  jz      short loc_14000DF0A
0x14000def1  mov     rcx, rbx; this
0x14000def4  call    ??1WriteFault@Streaming@@QEAA@XZ; Streaming::WriteFault::~WriteFault(void)
0x14000def9  xor     edx, edx; Tag
0x14000defb  mov     rcx, rbx; P
0x14000defe  call    cs:__imp_ExFreePoolWithTag
0x14000df05  nop     dword ptr [rax+rax+00h]
0x14000df0a  xor     esi, esi
0x14000df0c  lea     r14d, [rsi+8]
0x14000df10  xor     ebx, ebx
0x14000df12  mov     [rsp+88h+var_60], rbx
0x14000df17  test    rbx, rbx
0x14000df1a  jnz     short loc_14000DF6F
0x14000df1c  mov     dword ptr [rbp+18h], 0C000009Ah
0x14000df23  mov     qword ptr [rbp+20h], 0
0x14000df2b  test    rsi, rsi
0x14000df2e  jz      loc_14000E028
0x14000df34  or      ebx, 0FFFFFFFFh
0x14000df37  mov     eax, ebx
0x14000df39  lock xadd [r14], eax
0x14000df3e  add     eax, ebx
0x14000df40  jnz     loc_14000E028
0x14000df46  mov     rax, [rsi]
0x14000df49  mov     rcx, rsi
0x14000df4c  mov     rax, [rax+8]
0x14000df50  call    _guard_dispatch_icall
0x14000df55  mov     eax, ebx
0x14000df57  lock xadd [rsi+0Ch], eax
0x14000df5c  add     eax, ebx
0x14000df5e  jnz     loc_14000E028
0x14000df64  mov     rax, [rsi]
0x14000df67  mov     rcx, rsi
0x14000df6a  jmp     loc_14000E01F
0x14000df6f  test    r15d, r15d
0x14000df72  jns     short loc_14000DF7A
0x14000df74  mov     [rbp+18h], r15d
0x14000df78  jmp     short loc_14000DF23
0x14000df7a  test    r12b, r12b
0x14000df7d  jnz     short loc_14000DFCC
0x14000df7f  mov     rcx, rbx; this
0x14000df82  call    ?ProcessFault@WriteFault@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@XZ; Streaming::WriteFault::ProcessFault(void)
0x14000df87  mov     edi, eax
0x14000df89  test    rsi, rsi
0x14000df8c  jz      short loc_14000DFC5
0x14000df8e  or      ebx, 0FFFFFFFFh
0x14000df91  mov     ecx, ebx
0x14000df93  lock xadd [r14], ecx
0x14000df98  add     ecx, ebx
0x14000df9a  jnz     short loc_14000DFC5
0x14000df9c  mov     rcx, [rsi]
0x14000df9f  mov     rax, [rcx+8]
0x14000dfa3  mov     rcx, rsi
0x14000dfa6  call    _guard_dispatch_icall
0x14000dfab  mov     eax, ebx
0x14000dfad  lock xadd [rsi+0Ch], eax
0x14000dfb2  add     eax, ebx
0x14000dfb4  jnz     short loc_14000DFC5
0x14000dfb6  mov     rax, [rsi]
0x14000dfb9  mov     rcx, rsi
0x14000dfbc  mov     rax, [rax+10h]
0x14000dfc0  call    _guard_dispatch_icall
0x14000dfc5  mov     eax, edi
0x14000dfc7  jmp     loc_14000E070
0x14000dfcc  lea     rcx, [r13+0D8h]
0x14000dfd3  lea     rdx, [rsp+88h+var_60]
0x14000dfd8  call    ?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::WriteFault> &)
0x14000dfdd  test    eax, eax
0x14000dfdf  jns     short loc_14000E02F
0x14000dfe1  mov     [rbp+18h], eax
0x14000dfe4  mov     qword ptr [rbp+20h], 0
0x14000dfec  test    rdi, rdi
0x14000dfef  jz      short loc_14000E028
0x14000dff1  or      ebx, 0FFFFFFFFh
0x14000dff4  mov     eax, ebx
0x14000dff6  lock xadd [rdi+8], eax
0x14000dffb  add     eax, ebx
0x14000dffd  jnz     short loc_14000E028
0x14000dfff  mov     rax, [rdi]
0x14000e002  mov     rcx, rdi
0x14000e005  mov     rax, [rax+8]
0x14000e009  call    _guard_dispatch_icall
0x14000e00e  mov     eax, ebx
0x14000e010  lock xadd [rdi+0Ch], eax
0x14000e015  add     eax, ebx
0x14000e017  jnz     short loc_14000E028
0x14000e019  mov     rax, [rdi]
0x14000e01c  mov     rcx, rdi
0x14000e01f  mov     rax, [rax+10h]
0x14000e023  call    _guard_dispatch_icall
0x14000e028  mov     eax, 4
0x14000e02d  jmp     short loc_14000E070
0x14000e02f  test    rdi, rdi
0x14000e032  jz      short loc_14000E06B
0x14000e034  or      ebx, 0FFFFFFFFh
0x14000e037  mov     eax, ebx
0x14000e039  lock xadd [rdi+8], eax
0x14000e03e  add     eax, ebx
0x14000e040  jnz     short loc_14000E06B
0x14000e042  mov     rax, [rdi]
0x14000e045  mov     rcx, rdi
0x14000e048  mov     rax, [rax+8]
0x14000e04c  call    _guard_dispatch_icall
0x14000e051  mov     eax, ebx
0x14000e053  lock xadd [rdi+0Ch], eax
0x14000e058  add     eax, ebx
0x14000e05a  jnz     short loc_14000E06B
0x14000e05c  mov     rax, [rdi]
0x14000e05f  mov     rcx, rdi
0x14000e062  mov     rax, [rax+10h]
0x14000e066  call    _guard_dispatch_icall
0x14000e06b  mov     eax, 2
0x14000e070  add     rsp, 48h
0x14000e074  pop     r15
0x14000e076  pop     r14
0x14000e078  pop     r13
0x14000e07a  pop     r12
0x14000e07c  pop     rdi
0x14000e07d  pop     rsi
0x14000e07e  pop     rbp
0x14000e07f  pop     rbx
0x14000e080  retn
```

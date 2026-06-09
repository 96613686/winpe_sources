# Streaming::StreamFaultManager::CreateStreamFault(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x14000db88`
- end: `0x14000de23`
- name: `?CreateStreamFault@StreamFaultManager@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009d98`

## callees

- `0x14000be10`
- `0x14000c1d4`
- `0x14000d718`
- `0x14000db88`
- `0x14000e330`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14000dbb8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000dbb8`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dbe4`
- `ntoskrnl!SeQueryInformationToken` at `0x14000dbe4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000dc0e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000dc0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dd79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de03`
- `ntoskrnl!ExAllocatePool2` at `0x14000dc59`
- `ntoskrnl!ExAllocatePool2` at `0x14000dcb2`
- `ntoskrnl!ExAllocatePool2` at `0x14000dc59`
- `ntoskrnl!ExAllocatePool2` at `0x14000dcb2`

## pseudocode

```c
NTSTATUS __fastcall Streaming::StreamFaultManager::CreateStreamFault(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS result; // eax
  NTSTATUS v11; // r14d
  __int64 Pool2; // rax
  __int64 v13; // rax
  Streaming::StreamFault *v14; // rdi
  __int64 v15; // rax
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rsi
  int v18; // eax
  NTSTATUS v19; // [rsp+40h] [rbp-41h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp-39h] BYREF
  Streaming::StreamFault *v21; // [rsp+50h] [rbp-31h] BYREF
  volatile signed __int32 *v22; // [rsp+58h] [rbp-29h]
  __int64 v23; // [rsp+60h] [rbp-21h] BYREF
  PVOID P; // [rsp+68h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-11h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+80h] [rbp-1h] BYREF

  memset(&SubjectContext, 0, sizeof(SubjectContext));
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  TokenInformation = 0;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  result = SeQueryInformationToken(PrimaryToken, TokenUser, &TokenInformation);
  if ( result >= 0 )
  {
    v23 = 0;
    P = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v11 = appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(
            *(PSID *)TokenInformation,
            (__int64)&v23);
    v19 = v11;
    ExFreePoolWithTag(TokenInformation, 0);
    if ( v11 < 0 )
      goto LABEL_32;
    Pool2 = ExAllocatePool2(64, 104, 1718838899);
    if ( Pool2 )
    {
      v13 = Streaming::StreamFault::StreamFault(Pool2, a4, a2, a5, a3, &v23, &v19);
      v11 = v19;
      v14 = (Streaming::StreamFault *)v13;
    }
    else
    {
      v14 = 0;
    }
    v21 = v14;
    v15 = ExAllocatePool2(256, 24, 1715758931);
    v16 = (volatile signed __int32 *)v15;
    if ( v15 )
    {
      *(_DWORD *)(v15 + 8) = 1;
      v17 = v15 + 8;
      *(_DWORD *)(v15 + 12) = 1;
      *(_QWORD *)v15 = &kernel_std::detail::sp_counted_impl_p<Streaming::StreamFault>::`vftable';
      *(_QWORD *)(v15 + 16) = v14;
      v18 = *(_DWORD *)(v15 + 8);
      v22 = v16;
      if ( v18 )
      {
LABEL_15:
        if ( v11 < 0 )
          goto LABEL_29;
        if ( !v14 )
        {
          if ( v16 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
              if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
            }
          }
          if ( P )
            ExFreePoolWithTag(P, 0);
          return -1073741670;
        }
        v11 = appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::QueueWorkItem(
                a1,
                &v21);
        if ( v11 >= 0 )
        {
LABEL_29:
          if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
          {
LABEL_30:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
        else if ( v16 && _InterlockedExchangeAdd((volatile signed __int32 *)v17, 0xFFFFFFFF) == 1 )
        {
          goto LABEL_30;
        }
LABEL_32:
        if ( P )
          ExFreePoolWithTag(P, 0);
        return v11;
      }
    }
    else
    {
      v22 = 0;
      if ( v14 )
      {
        Streaming::StreamFault::~StreamFault(v14);
        ExFreePoolWithTag(v14, 0);
      }
      v17 = 8;
      v16 = 0;
    }
    v14 = 0;
    v21 = 0;
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x14000db88  push    rbp
0x14000db8a  push    rbx
0x14000db8b  push    rsi
0x14000db8c  push    rdi
0x14000db8d  push    r14
0x14000db8f  push    r15
0x14000db91  lea     rbp, [rsp-27h]
0x14000db96  sub     rsp, 0A8h
0x14000db9d  xorps   xmm0, xmm0
0x14000dba0  mov     r15, rcx
0x14000dba3  lea     rcx, [rbp+4Fh+SubjectContext]; SubjectContext
0x14000dba7  mov     rbx, r9
0x14000dbaa  movups  xmmword ptr [rbp+4Fh+SubjectContext.ClientToken], xmm0
0x14000dbae  mov     rdi, r8
0x14000dbb1  mov     rsi, rdx
0x14000dbb4  movups  xmmword ptr [rbp+4Fh+SubjectContext.PrimaryToken], xmm0
0x14000dbb8  call    cs:__imp_SeCaptureSubjectContext
0x14000dbbf  nop     dword ptr [rax+rax+00h]
0x14000dbc4  mov     rax, [rbp+4Fh+SubjectContext.ClientToken]
0x14000dbc8  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x14000dbcc  mov     rcx, [rbp+4Fh+SubjectContext.PrimaryToken]
0x14000dbd0  test    rax, rax
0x14000dbd3  mov     edx, 1; TokenInformationClass
0x14000dbd8  mov     [rbp+4Fh+TokenInformation], 0
0x14000dbe0  cmovnz  rcx, rax; Token
0x14000dbe4  call    cs:__imp_SeQueryInformationToken
0x14000dbeb  nop     dword ptr [rax+rax+00h]
0x14000dbf0  test    eax, eax
0x14000dbf2  js      loc_14000DE12
0x14000dbf8  xor     edx, edx; SourceString
0x14000dbfa  mov     [rbp+4Fh+var_70], 0
0x14000dc02  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14000dc06  mov     [rbp+4Fh+P], 0
0x14000dc0e  call    cs:__imp_RtlInitUnicodeString
0x14000dc15  nop     dword ptr [rax+rax+00h]
0x14000dc1a  mov     rcx, [rbp+4Fh+TokenInformation]
0x14000dc1e  lea     rdx, [rbp+4Fh+var_70]
0x14000dc22  mov     rcx, [rcx]; Sid
0x14000dc25  call    ??$ConvertSid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@@Z; appv::shared::kernel::ConvertSid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)
0x14000dc2a  mov     rcx, [rbp+4Fh+TokenInformation]; P
0x14000dc2e  xor     edx, edx; Tag
0x14000dc30  mov     r14d, eax
0x14000dc33  mov     [rbp+4Fh+var_90], eax
0x14000dc36  call    cs:__imp_ExFreePoolWithTag
0x14000dc3d  nop     dword ptr [rax+rax+00h]
0x14000dc42  test    r14d, r14d
0x14000dc45  js      loc_14000DDF8
0x14000dc4b  mov     edx, 68h ; 'h'
0x14000dc50  mov     r8d, 66736673h
0x14000dc56  lea     ecx, [rdx-28h]
0x14000dc59  call    cs:__imp_ExAllocatePool2
0x14000dc60  nop     dword ptr [rax+rax+00h]
0x14000dc65  test    rax, rax
0x14000dc68  jz      short loc_14000DC9C
0x14000dc6a  mov     r9, [rbp+4Fh+arg_20]
0x14000dc6e  lea     rcx, [rbp+4Fh+var_90]
0x14000dc72  mov     [rsp+0D0h+var_A0], rcx
0x14000dc77  mov     r8, rsi
0x14000dc7a  lea     rcx, [rbp+4Fh+var_70]
0x14000dc7e  mov     rdx, rbx
0x14000dc81  mov     [rsp+0D0h+var_A8], rcx
0x14000dc86  mov     rcx, rax
0x14000dc89  mov     [rsp+0D0h+var_B0], rdi
0x14000dc8e  call    ??0StreamFault@Streaming@@QEAA@AEAU_FLT_CALLBACK_DATA@@PEAU_FLT_INSTANCE@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@AEAU_FILE_OBJECT@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@567@AEAJ@Z; Streaming::StreamFault::StreamFault(_FLT_CALLBACK_DATA &,_FLT_INSTANCE *,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,_FILE_OBJECT &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,long &)
0x14000dc93  mov     r14d, [rbp+4Fh+var_90]
0x14000dc97  mov     rdi, rax
0x14000dc9a  jmp     short loc_14000DC9E
0x14000dc9c  xor     edi, edi
0x14000dc9e  mov     edx, 18h
0x14000dca3  mov     [rbp+4Fh+var_80], rdi
0x14000dca7  mov     ecx, 100h
0x14000dcac  mov     r8d, 66446753h
0x14000dcb2  call    cs:__imp_ExAllocatePool2
0x14000dcb9  nop     dword ptr [rax+rax+00h]
0x14000dcbe  mov     rbx, rax
0x14000dcc1  test    rax, rax
0x14000dcc4  jz      short loc_14000DCF2
0x14000dcc6  mov     dword ptr [rax+8], 1
0x14000dccd  lea     rsi, [rbx+8]
0x14000dcd1  mov     dword ptr [rax+0Ch], 1
0x14000dcd8  lea     rax, ??_7?$sp_counted_impl_p@VStreamFault@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::StreamFault>::`vftable'
0x14000dcdf  mov     [rbx], rax
0x14000dce2  mov     [rbx+10h], rdi
0x14000dce6  mov     eax, [rsi]
0x14000dce8  mov     [rbp+4Fh+var_78], rbx
0x14000dcec  test    eax, eax
0x14000dcee  jnz     short loc_14000DD25
0x14000dcf0  jmp     short loc_14000DD1F
0x14000dcf2  mov     [rbp+4Fh+var_78], 0
0x14000dcfa  test    rdi, rdi
0x14000dcfd  jz      short loc_14000DD18
0x14000dcff  mov     rcx, rdi; this
0x14000dd02  call    ??1StreamFault@Streaming@@QEAA@XZ; Streaming::StreamFault::~StreamFault(void)
0x14000dd07  xor     edx, edx; Tag
0x14000dd09  mov     rcx, rdi; P
0x14000dd0c  call    cs:__imp_ExFreePoolWithTag
0x14000dd13  nop     dword ptr [rax+rax+00h]
0x14000dd18  mov     esi, 8
0x14000dd1d  xor     ebx, ebx
0x14000dd1f  xor     edi, edi
0x14000dd21  mov     [rbp+4Fh+var_80], rdi
0x14000dd25  test    r14d, r14d
0x14000dd28  js      loc_14000DDBD
0x14000dd2e  test    rdi, rdi
0x14000dd31  jnz     short loc_14000DD8F
0x14000dd33  test    rbx, rbx
0x14000dd36  jz      short loc_14000DD6E
0x14000dd38  or      edi, 0FFFFFFFFh
0x14000dd3b  mov     eax, edi
0x14000dd3d  lock xadd [rsi], eax
0x14000dd41  add     eax, edi
0x14000dd43  jnz     short loc_14000DD6E
0x14000dd45  mov     rax, [rbx]
0x14000dd48  mov     rcx, rbx
0x14000dd4b  mov     rax, [rax+8]
0x14000dd4f  call    _guard_dispatch_icall
0x14000dd54  mov     eax, edi
0x14000dd56  lock xadd [rbx+0Ch], eax
0x14000dd5b  add     eax, edi
0x14000dd5d  jnz     short loc_14000DD6E
0x14000dd5f  mov     rax, [rbx]
0x14000dd62  mov     rcx, rbx
0x14000dd65  mov     rax, [rax+10h]
0x14000dd69  call    _guard_dispatch_icall
0x14000dd6e  mov     rcx, [rbp+4Fh+P]; P
0x14000dd72  test    rcx, rcx
0x14000dd75  jz      short loc_14000DD85
0x14000dd77  xor     edx, edx; Tag
0x14000dd79  call    cs:__imp_ExFreePoolWithTag
0x14000dd80  nop     dword ptr [rax+rax+00h]
0x14000dd85  mov     eax, 0C000009Ah
0x14000dd8a  jmp     loc_14000DE12
0x14000dd8f  lea     rdx, [rbp+4Fh+var_80]
0x14000dd93  mov     rcx, r15
0x14000dd96  call    ?QueueWorkItem@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAJAEAV?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@@Z; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::QueueWorkItem(kernel_std::shared_ptr<Streaming::StreamFault> &)
0x14000dd9b  mov     r14d, eax
0x14000dd9e  test    eax, eax
0x14000dda0  jns     short loc_14000DDBD
0x14000dda2  test    rbx, rbx
0x14000dda5  jz      short loc_14000DDF8
0x14000dda7  or      edi, 0FFFFFFFFh
0x14000ddaa  mov     ecx, edi
0x14000ddac  lock xadd [rsi], ecx
0x14000ddb0  add     ecx, edi
0x14000ddb2  jnz     short loc_14000DDF8
0x14000ddb4  mov     rcx, [rbx]
0x14000ddb7  mov     rax, [rcx+8]
0x14000ddbb  jmp     short loc_14000DDD6
0x14000ddbd  test    rbx, rbx
0x14000ddc0  jz      short loc_14000DDF8
0x14000ddc2  or      edi, 0FFFFFFFFh
0x14000ddc5  mov     eax, edi
0x14000ddc7  lock xadd [rsi], eax
0x14000ddcb  add     eax, edi
0x14000ddcd  jnz     short loc_14000DDF8
0x14000ddcf  mov     rax, [rbx]
0x14000ddd2  mov     rax, [rax+8]
0x14000ddd6  mov     rcx, rbx
0x14000ddd9  call    _guard_dispatch_icall
0x14000ddde  mov     eax, edi
0x14000dde0  lock xadd [rbx+0Ch], eax
0x14000dde5  add     eax, edi
0x14000dde7  jnz     short loc_14000DDF8
0x14000dde9  mov     rax, [rbx]
0x14000ddec  mov     rcx, rbx
0x14000ddef  mov     rax, [rax+10h]
0x14000ddf3  call    _guard_dispatch_icall
0x14000ddf8  mov     rcx, [rbp+4Fh+P]; P
0x14000ddfc  test    rcx, rcx
0x14000ddff  jz      short loc_14000DE0F
0x14000de01  xor     edx, edx; Tag
0x14000de03  call    cs:__imp_ExFreePoolWithTag
0x14000de0a  nop     dword ptr [rax+rax+00h]
0x14000de0f  mov     eax, r14d
0x14000de12  add     rsp, 0A8h
0x14000de19  pop     r15
0x14000de1b  pop     r14
0x14000de1d  pop     rdi
0x14000de1e  pop     rsi
0x14000de1f  pop     rbx
0x14000de20  pop     rbp
0x14000de21  retn
```

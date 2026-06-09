# BdeSvcApplyRecoveryPolicy(void)

- ea: `0x18001bdb0`
- end: `0x18001c00c`
- name: `?BdeSvcApplyRecoveryPolicy@@YAJXZ`
- size: `604`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c780`

## callees

- `0x18001b890`
- `0x18001bdb0`
- `0x18001c014`
- `0x180034070`
- `0x180034440`
- `0x18003447c`
- `0x180034610`
- `0x18006851c`
- `0x180068578`
- `0x1800686d0`
- `0x18006bec4`
- `0x18007b3e0`
- `0x18007e010`

## import_xrefs

- `bcd!BcdOpenSystemStore` at `0x18001bed0`
- `bcd!BcdOpenSystemStore` at `0x18001bed0`
- `bcd!BcdOpenObject` at `0x18001befc`
- `bcd!BcdOpenObject` at `0x18001befc`
- `bcd!BcdCloseStore` at `0x18001bfaa`
- `bcd!BcdCloseStore` at `0x18001bfaa`
- `bcd!BcdCloseObject` at `0x18001bf95`
- `bcd!BcdCloseObject` at `0x18001bf95`

## pseudocode

```c
__int64 BdeSvcApplyRecoveryPolicy(void)
{
  CFvePolicyImpl *v0; // rbx
  CFvePolicyImpl *v1; // rax
  const struct std::nothrow_t *v2; // rdx
  CFvePolicyImpl *v3; // rsi
  int RecoveryMessage; // edi
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  void **v10; // [rsp+30h] [rbp-50h] BYREF
  CFvePolicyImpl *v11; // [rsp+38h] [rbp-48h]
  void *v12; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-28h] BYREF
  int v16; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 v17; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp-10h] BYREF

  v15 = 0;
  v12 = 0;
  v16 = 0;
  v13 = 0;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v0 = 0;
  v11 = 0;
  v10 = &CFveServicePolicy::`vftable';
  v1 = (CFvePolicyImpl *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v1;
  if ( !v1 )
  {
    RecoveryMessage = -2147024882;
    goto LABEL_23;
  }
  CFvePolicyImpl::CFvePolicyImpl(v1);
  *(_QWORD *)v3 = &CFveServicePolicyImpl::`vftable';
  RecoveryMessage = ((__int64 (__fastcall *)(CFvePolicyImpl *, _QWORD))CFveServicePolicyImpl::`vftable')(v3, 0);
  if ( RecoveryMessage < 0 )
  {
    CFvePolicyImpl::~CFvePolicyImpl(v3);
    operator delete(v3);
  }
  else
  {
    v0 = v3;
    v11 = v3;
  }
  if ( RecoveryMessage >= 0 )
  {
    v5 = _RTDynamicCast_0(
           v0,
           0,
           &CFvePolicyImpl `RTTI Type Descriptor',
           &CFveServicePolicyImpl `RTTI Type Descriptor',
           0);
    if ( !v5 )
    {
      RecoveryMessage = -2147467261;
      goto LABEL_23;
    }
    RecoveryMessage = (***(__int64 (__fastcall ****)(_QWORD, __int64, int *))(v5 + 32))(*(_QWORD *)(v5 + 32), 160, &v16);
    if ( RecoveryMessage == -2147024894 )
    {
      v6 = 0;
      v16 = 0;
      RecoveryMessage = 0;
    }
    else
    {
      v6 = v16;
    }
    if ( RecoveryMessage >= 0 )
    {
      if ( v6 )
      {
        v7 = BcdOpenSystemStore(&v15);
        RecoveryMessage = FromNtStatus(v7);
        if ( RecoveryMessage >= 0 )
        {
          v8 = BcdOpenObject(v15, &GUID_WINDOWS_BOOTMGR, &v12);
          RecoveryMessage = FromNtStatus(v8);
          if ( RecoveryMessage >= 0 )
          {
            if ( v16 == 2 )
            {
              RecoveryMessage = CFveServicePolicy::GetRecoveryMessage((CFveServicePolicy *)&v10, &v13, &v17);
              if ( RecoveryMessage < 0 )
                goto LABEL_23;
            }
            else if ( v16 == 3 )
            {
              RecoveryMessage = CFveServicePolicy::GetRecoveryUrl((CFveServicePolicy *)&v10, &v14, &v18);
              if ( RecoveryMessage < 0 )
                goto LABEL_23;
            }
            RecoveryMessage = FveBcdUtil::UpdateBcdRecoveryStringData(v12, 0x22000041u, v13);
            if ( RecoveryMessage >= 0 )
              RecoveryMessage = FveBcdUtil::UpdateBcdRecoveryStringData(v12, 0x22000040u, v14);
          }
        }
      }
    }
  }
LABEL_23:
  if ( v12 )
    BcdCloseObject();
  if ( v15 )
    BcdCloseStore();
  if ( v13 )
  {
    operator delete(v13, v2);
    v13 = 0;
  }
  if ( v14 )
  {
    operator delete(v14, v2);
    v14 = 0;
  }
  if ( v0 )
  {
    CFvePolicyImpl::~CFvePolicyImpl(v0);
    operator delete(v0);
  }
  return (unsigned int)RecoveryMessage;
}

```

## disassembly

```asm
0x18001bdb0  push    rbp
0x18001bdb2  push    rbx
0x18001bdb3  push    rsi
0x18001bdb4  push    rdi
0x18001bdb5  push    r14
0x18001bdb7  mov     rbp, rsp
0x18001bdba  sub     rsp, 80h
0x18001bdc1  mov     rax, cs:__security_cookie
0x18001bdc8  xor     rax, rsp
0x18001bdcb  mov     [rbp+var_8], rax
0x18001bdcf  xor     r14d, r14d
0x18001bdd2  mov     [rbp+var_28], r14
0x18001bdd6  mov     [rbp+var_40], r14
0x18001bdda  mov     [rbp+var_20], r14d
0x18001bdde  mov     [rbp+var_38], r14
0x18001bde2  mov     [rbp+var_30], r14
0x18001bde6  mov     [rbp+var_18], r14
0x18001bdea  mov     [rbp+var_10], r14
0x18001bdee  mov     ebx, r14d
0x18001bdf1  mov     [rbp+var_48], rbx
0x18001bdf5  lea     rax, ??_7CFveServicePolicy@@6B@; const CFveServicePolicy::`vftable'
0x18001bdfc  mov     [rbp+var_50], rax
0x18001be00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001be07  mov     ecx, 0B8h; unsigned __int64
0x18001be0c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001be11  mov     rsi, rax
0x18001be14  test    rax, rax
0x18001be17  jz      loc_18001BF87
0x18001be1d  mov     rcx, rax; this
0x18001be20  call    ??0CFvePolicyImpl@@QEAA@XZ; CFvePolicyImpl::CFvePolicyImpl(void)
0x18001be25  lea     rcx, ??_7CFveServicePolicyImpl@@6B@; const CFveServicePolicyImpl::`vftable'
0x18001be2c  mov     [rsi], rcx
0x18001be2f  xor     edx, edx
0x18001be31  mov     rcx, rsi
0x18001be34  mov     rax, cs:??_7CFveServicePolicyImpl@@6B@; const CFveServicePolicyImpl::`vftable'
0x18001be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be40  mov     edi, eax
0x18001be42  test    eax, eax
0x18001be44  js      short loc_18001BE4F
0x18001be46  mov     rbx, rsi
0x18001be49  mov     [rbp+var_48], rbx
0x18001be4d  jmp     short loc_18001BE5F
0x18001be4f  mov     rcx, rsi; this
0x18001be52  call    ??1CFvePolicyImpl@@QEAA@XZ; CFvePolicyImpl::~CFvePolicyImpl(void)
0x18001be57  mov     rcx, rsi; Block
0x18001be5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001be5f  test    edi, edi
0x18001be61  js      loc_18001BF8C
0x18001be67  mov     [rsp+80h+var_60], r14d
0x18001be6c  lea     r9, ??_R0?AVCFveServicePolicyImpl@@@8; CFveServicePolicyImpl `RTTI Type Descriptor'
0x18001be73  lea     r8, ??_R0?AVCFvePolicyImpl@@@8; CFvePolicyImpl `RTTI Type Descriptor'
0x18001be7a  xor     edx, edx
0x18001be7c  mov     rcx, rbx
0x18001be7f  call    __RTDynamicCast_0
0x18001be84  test    rax, rax
0x18001be87  jz      loc_18001BF80
0x18001be8d  mov     rcx, [rax+20h]
0x18001be91  mov     rax, [rcx]
0x18001be94  lea     r8, [rbp+var_20]
0x18001be98  mov     edx, 0A0h
0x18001be9d  mov     rax, [rax]
0x18001bea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bea5  mov     edi, eax
0x18001bea7  cmp     eax, 80070002h
0x18001beac  jnz     short loc_18001BEB9
0x18001beae  mov     eax, r14d
0x18001beb1  mov     [rbp+var_20], eax
0x18001beb4  mov     edi, r14d
0x18001beb7  jmp     short loc_18001BEBC
0x18001beb9  mov     eax, [rbp+var_20]
0x18001bebc  test    edi, edi
0x18001bebe  js      loc_18001BF8C
0x18001bec4  test    eax, eax
0x18001bec6  jz      loc_18001BF8C
0x18001becc  lea     rcx, [rbp+var_28]
0x18001bed0  call    cs:__imp_BcdOpenSystemStore
0x18001bed7  nop     dword ptr [rax+rax+00h]
0x18001bedc  mov     ecx, eax; int
0x18001bede  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001bee3  mov     edi, eax
0x18001bee5  test    eax, eax
0x18001bee7  js      loc_18001BF8C
0x18001beed  lea     r8, [rbp+var_40]
0x18001bef1  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18001bef8  mov     rcx, [rbp+var_28]
0x18001befc  call    cs:__imp_BcdOpenObject
0x18001bf03  nop     dword ptr [rax+rax+00h]
0x18001bf08  mov     ecx, eax; int
0x18001bf0a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001bf0f  mov     edi, eax
0x18001bf11  test    eax, eax
0x18001bf13  js      short loc_18001BF8C
0x18001bf15  mov     eax, [rbp+var_20]
0x18001bf18  cmp     eax, 2
0x18001bf1b  jnz     short loc_18001BF36
0x18001bf1d  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18001bf21  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x18001bf25  lea     rcx, [rbp+var_50]; this
0x18001bf29  call    ?GetRecoveryMessage@CFveServicePolicy@@QEBAJPEAPEAGPEA_K@Z; CFveServicePolicy::GetRecoveryMessage(ushort * *,unsigned __int64 *)
0x18001bf2e  mov     edi, eax
0x18001bf30  test    eax, eax
0x18001bf32  jns     short loc_18001BF52
0x18001bf34  jmp     short loc_18001BF8C
0x18001bf36  cmp     eax, 3
0x18001bf39  jnz     short loc_18001BF52
0x18001bf3b  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18001bf3f  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18001bf43  lea     rcx, [rbp+var_50]; this
0x18001bf47  call    ?GetRecoveryUrl@CFveServicePolicy@@QEBAJPEAPEAGPEA_K@Z; CFveServicePolicy::GetRecoveryUrl(ushort * *,unsigned __int64 *)
0x18001bf4c  mov     edi, eax
0x18001bf4e  test    eax, eax
0x18001bf50  js      short loc_18001BF8C
0x18001bf52  mov     r8, [rbp+var_38]; unsigned __int16 *
0x18001bf56  mov     edx, 22000041h; unsigned int
0x18001bf5b  mov     rcx, [rbp+var_40]; void *
0x18001bf5f  call    ?UpdateBcdRecoveryStringData@FveBcdUtil@@SAJPEAXKPEBG@Z; FveBcdUtil::UpdateBcdRecoveryStringData(void *,ulong,ushort const *)
0x18001bf64  mov     edi, eax
0x18001bf66  test    eax, eax
0x18001bf68  js      short loc_18001BF8C
0x18001bf6a  mov     r8, [rbp+var_30]; unsigned __int16 *
0x18001bf6e  mov     edx, 22000040h; unsigned int
0x18001bf73  mov     rcx, [rbp+var_40]; void *
0x18001bf77  call    ?UpdateBcdRecoveryStringData@FveBcdUtil@@SAJPEAXKPEBG@Z; FveBcdUtil::UpdateBcdRecoveryStringData(void *,ulong,ushort const *)
0x18001bf7c  mov     edi, eax
0x18001bf7e  jmp     short loc_18001BF8C
0x18001bf80  mov     edi, 80004003h
0x18001bf85  jmp     short loc_18001BF8C
0x18001bf87  mov     edi, 8007000Eh
0x18001bf8c  mov     rcx, [rbp+var_40]
0x18001bf90  test    rcx, rcx
0x18001bf93  jz      short loc_18001BFA1
0x18001bf95  call    cs:__imp_BcdCloseObject
0x18001bf9c  nop     dword ptr [rax+rax+00h]
0x18001bfa1  mov     rcx, [rbp+var_28]
0x18001bfa5  test    rcx, rcx
0x18001bfa8  jz      short loc_18001BFB6
0x18001bfaa  call    cs:__imp_BcdCloseStore
0x18001bfb1  nop     dword ptr [rax+rax+00h]
0x18001bfb6  mov     rcx, [rbp+var_38]; void *
0x18001bfba  test    rcx, rcx
0x18001bfbd  jz      short loc_18001BFC8
0x18001bfbf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bfc4  mov     [rbp+var_38], r14
0x18001bfc8  mov     rcx, [rbp+var_30]; void *
0x18001bfcc  test    rcx, rcx
0x18001bfcf  jz      short loc_18001BFDA
0x18001bfd1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bfd6  mov     [rbp+var_30], r14
0x18001bfda  test    rbx, rbx
0x18001bfdd  jz      short loc_18001BFEF
0x18001bfdf  mov     rcx, rbx; this
0x18001bfe2  call    ??1CFvePolicyImpl@@QEAA@XZ; CFvePolicyImpl::~CFvePolicyImpl(void)
0x18001bfe7  mov     rcx, rbx; Block
0x18001bfea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bfef  mov     eax, edi
0x18001bff1  mov     rcx, [rbp+var_8]
0x18001bff5  xor     rcx, rsp; StackCookie
0x18001bff8  call    __security_check_cookie
0x18001bffd  add     rsp, 80h
0x18001c004  pop     r14
0x18001c006  pop     rdi
0x18001c007  pop     rsi
0x18001c008  pop     rbx
0x18001c009  pop     rbp
0x18001c00a  retn
```

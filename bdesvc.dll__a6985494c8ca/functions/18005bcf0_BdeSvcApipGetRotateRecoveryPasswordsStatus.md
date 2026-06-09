# BdeSvcApipGetRotateRecoveryPasswordsStatus

- ea: `0x18005bcf0`
- end: `0x18005bff3`
- name: `BdeSvcApipGetRotateRecoveryPasswordsStatus`
- size: `771`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002d6f0`
- `0x180034070`
- `0x18004f270`
- `0x18005a4b4`
- `0x18005a60c`
- `0x18005a918`
- `0x18005bcf0`
- `0x18005f660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005be18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005be18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bf52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bf52`
- `RPCRT4!RpcImpersonateClient` at `0x18005bd7a`
- `RPCRT4!RpcImpersonateClient` at `0x18005bd7a`
- `RPCRT4!RpcRevertToSelf` at `0x18005bf70`
- `RPCRT4!RpcRevertToSelf` at `0x18005bf70`

## pseudocode

```c
__int64 __fastcall BdeSvcApipGetRotateRecoveryPasswordsStatus(__int64 a1, unsigned int *a2, unsigned __int16 **a3)
{
  char v3; // bp
  unsigned __int16 *v4; // rdi
  PVOID *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int RecoveryPasswordRotationRequestID; // eax
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned __int16 *v15; // rax
  int v16; // eax
  unsigned int v17; // eax
  PVOID *v18; // rcx
  unsigned int v20; // [rsp+20h] [rbp-38h] BYREF
  unsigned int pvData; // [rsp+24h] [rbp-34h] BYREF

  v3 = 0;
  v20 = 2;
  v4 = 0;
  pvData = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    v8 = RpcImpersonateClient(0);
    v9 = v8;
    if ( v8 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v8);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = v9 | 0x80010000;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
      {
        v11 = 69;
LABEL_44:
        v13 = v10;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    v3 = 1;
    RecoveryPasswordRotationRequestID = CheckDeviceForServerKeyRotation();
    v10 = RecoveryPasswordRotationRequestID;
    if ( RecoveryPasswordRotationRequestID < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_46;
      v11 = 70;
      goto LABEL_17;
    }
    EnterCriticalSection(&gBdesvcServerRotationStatusCS);
    RecoveryPasswordRotationRequestID = FveReadRecoveryPasswordRotationStatus(&v20);
    v10 = RecoveryPasswordRotationRequestID;
    if ( RecoveryPasswordRotationRequestID < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_46;
      v11 = 71;
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v20);
    v14 = v20;
    if ( v20 != 2 )
    {
      v15 = (unsigned __int16 *)MIDL_user_allocate(0x102u);
      v4 = v15;
      if ( !v15 )
      {
        v10 = -2147024882;
        goto LABEL_46;
      }
      RecoveryPasswordRotationRequestID = FveReadRecoveryPasswordRotationRequestID(v15);
      v10 = RecoveryPasswordRotationRequestID;
      if ( RecoveryPasswordRotationRequestID < 0 )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_46;
        v11 = 73;
LABEL_17:
        v13 = (unsigned int)RecoveryPasswordRotationRequestID;
LABEL_45:
        WPP_SF_d(v7[2], v11, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v13);
        goto LABEL_46;
      }
      v14 = v20;
      *a3 = v4;
    }
    if ( v14 == -1 )
    {
      v16 = FveReadRecoveryPasswordRotationHResult(&pvData);
      v10 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
            (unsigned int)v16);
        goto LABEL_40;
      }
      v14 = pvData;
      v20 = pvData;
    }
    *a2 = v14;
LABEL_40:
    v4 = 0;
    goto LABEL_46;
  }
  v10 = -2147467261;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
  {
    v11 = 67;
    goto LABEL_44;
  }
LABEL_46:
  LeaveCriticalSection(&gBdesvcServerRotationStatusCS);
  if ( v4 )
    MemoryFree(v4);
  if ( !v3 )
    goto LABEL_53;
  v17 = RpcRevertToSelf();
  if ( !v17 )
    goto LABEL_53;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v17);
LABEL_53:
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x20) != 0 )
    WPP_SF_d(v18[2], 76, WPP_8a3f59d54824346350fe913136af4d55_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18005bcf0  mov     [rsp+arg_0], rbx
0x18005bcf5  mov     [rsp+arg_18], rbp
0x18005bcfa  push    rsi
0x18005bcfb  push    rdi
0x18005bcfc  push    r12
0x18005bcfe  push    r14
0x18005bd00  push    r15
0x18005bd02  sub     rsp, 30h
0x18005bd06  mov     rax, cs:__security_cookie
0x18005bd0d  xor     rax, rsp
0x18005bd10  mov     [rsp+58h+var_30], rax
0x18005bd15  xor     bpl, bpl
0x18005bd18  mov     [rsp+58h+var_38], 2
0x18005bd20  xor     edi, edi
0x18005bd22  mov     [rsp+58h+pvData], 0
0x18005bd2a  mov     rsi, r8
0x18005bd2d  mov     r14, rdx
0x18005bd30  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd37  lea     r15, WPP_GLOBAL_Control
0x18005bd3e  lea     r12, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18005bd45  cmp     rcx, r15
0x18005bd48  jz      short loc_18005BD66
0x18005bd4a  test    byte ptr [rcx+1Ch], 20h
0x18005bd4e  jz      short loc_18005BD66
0x18005bd50  mov     rcx, [rcx+10h]
0x18005bd54  lea     edx, [rdi+42h]
0x18005bd57  mov     r8, r12
0x18005bd5a  call    WPP_SF_
0x18005bd5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd66  test    r14, r14
0x18005bd69  jz      loc_18005BF27
0x18005bd6f  test    rsi, rsi
0x18005bd72  jz      loc_18005BF27
0x18005bd78  xor     ecx, ecx; BindingHandle
0x18005bd7a  call    cs:__imp_RpcImpersonateClient
0x18005bd81  nop     dword ptr [rax+rax+00h]
0x18005bd86  mov     ebx, eax
0x18005bd88  test    eax, eax
0x18005bd8a  jz      short loc_18005BDDC
0x18005bd8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd93  cmp     rcx, r15
0x18005bd96  jz      short loc_18005BDB9
0x18005bd98  test    byte ptr [rcx+1Ch], 2
0x18005bd9c  jz      short loc_18005BDB9
0x18005bd9e  mov     rcx, [rcx+10h]
0x18005bda2  mov     edx, 44h ; 'D'
0x18005bda7  mov     r9d, eax
0x18005bdaa  mov     r8, r12
0x18005bdad  call    WPP_SF_d
0x18005bdb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bdb9  or      ebx, 80010000h
0x18005bdbf  cmp     rcx, r15
0x18005bdc2  jz      loc_18005BF4B
0x18005bdc8  test    byte ptr [rcx+1Ch], 40h
0x18005bdcc  jz      loc_18005BF4B
0x18005bdd2  mov     edx, 45h ; 'E'
0x18005bdd7  jmp     loc_18005BF3C
0x18005bddc  mov     bpl, 1
0x18005bddf  call    ?CheckDeviceForServerKeyRotation@@YAJXZ; CheckDeviceForServerKeyRotation(void)
0x18005bde4  mov     ebx, eax
0x18005bde6  test    eax, eax
0x18005bde8  jns     short loc_18005BE11
0x18005bdea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bdf1  cmp     rcx, r15
0x18005bdf4  jz      loc_18005BF4B
0x18005bdfa  test    byte ptr [rcx+1Ch], 2
0x18005bdfe  jz      loc_18005BF4B
0x18005be04  mov     edx, 46h ; 'F'
0x18005be09  mov     r9d, eax
0x18005be0c  jmp     loc_18005BF3F
0x18005be11  lea     rcx, ?gBdesvcServerRotationStatusCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005be18  call    cs:__imp_EnterCriticalSection
0x18005be1f  nop     dword ptr [rax+rax+00h]
0x18005be24  lea     rcx, [rsp+58h+var_38]; pvData
0x18005be29  call    ?FveReadRecoveryPasswordRotationStatus@@YAJPEAK@Z; FveReadRecoveryPasswordRotationStatus(ulong *)
0x18005be2e  mov     ebx, eax
0x18005be30  test    eax, eax
0x18005be32  jns     short loc_18005BE55
0x18005be34  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be3b  cmp     rcx, r15
0x18005be3e  jz      loc_18005BF4B
0x18005be44  test    byte ptr [rcx+1Ch], 2
0x18005be48  jz      loc_18005BF4B
0x18005be4e  mov     edx, 47h ; 'G'
0x18005be53  jmp     short loc_18005BE09
0x18005be55  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be5c  cmp     rcx, r15
0x18005be5f  jz      short loc_18005BE7D
0x18005be61  test    byte ptr [rcx+1Ch], 8
0x18005be65  jz      short loc_18005BE7D
0x18005be67  mov     r9d, [rsp+58h+var_38]
0x18005be6c  mov     edx, 48h ; 'H'
0x18005be71  mov     rcx, [rcx+10h]
0x18005be75  mov     r8, r12
0x18005be78  call    WPP_SF_d
0x18005be7d  mov     eax, [rsp+58h+var_38]
0x18005be81  cmp     eax, 2
0x18005be84  jz      short loc_18005BEDB
0x18005be86  mov     ecx, 102h; size
0x18005be8b  call    MIDL_user_allocate
0x18005be90  mov     rdi, rax
0x18005be93  test    rax, rax
0x18005be96  jnz     short loc_18005BEA2
0x18005be98  mov     ebx, 8007000Eh
0x18005be9d  jmp     loc_18005BF4B
0x18005bea2  mov     rcx, rdi; unsigned __int16 *
0x18005bea5  call    ?FveReadRecoveryPasswordRotationRequestID@@YAJPEAG@Z; FveReadRecoveryPasswordRotationRequestID(ushort *)
0x18005beaa  mov     ebx, eax
0x18005beac  test    eax, eax
0x18005beae  jns     short loc_18005BED4
0x18005beb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005beb7  cmp     rcx, r15
0x18005beba  jz      loc_18005BF4B
0x18005bec0  test    byte ptr [rcx+1Ch], 2
0x18005bec4  jz      loc_18005BF4B
0x18005beca  mov     edx, 49h ; 'I'
0x18005becf  jmp     loc_18005BE09
0x18005bed4  mov     eax, [rsp+58h+var_38]
0x18005bed8  mov     [rsi], rdi
0x18005bedb  cmp     eax, 0FFFFFFFFh
0x18005bede  jnz     short loc_18005BF20
0x18005bee0  lea     rcx, [rsp+58h+pvData]; pvData
0x18005bee5  call    ?FveReadRecoveryPasswordRotationHResult@@YAJPEAJ@Z; FveReadRecoveryPasswordRotationHResult(long *)
0x18005beea  mov     ebx, eax
0x18005beec  test    eax, eax
0x18005beee  jns     short loc_18005BF18
0x18005bef0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bef7  cmp     rcx, r15
0x18005befa  jz      short loc_18005BF23
0x18005befc  test    byte ptr [rcx+1Ch], 2
0x18005bf00  jz      short loc_18005BF23
0x18005bf02  mov     rcx, [rcx+10h]
0x18005bf06  mov     edx, 4Ah ; 'J'
0x18005bf0b  mov     r9d, eax
0x18005bf0e  mov     r8, r12
0x18005bf11  call    WPP_SF_d
0x18005bf16  jmp     short loc_18005BF23
0x18005bf18  mov     eax, [rsp+58h+pvData]
0x18005bf1c  mov     [rsp+58h+var_38], eax
0x18005bf20  mov     [r14], eax
0x18005bf23  xor     edi, edi
0x18005bf25  jmp     short loc_18005BF4B
0x18005bf27  mov     ebx, 80004003h
0x18005bf2c  cmp     rcx, r15
0x18005bf2f  jz      short loc_18005BF4B
0x18005bf31  test    byte ptr [rcx+1Ch], 40h
0x18005bf35  jz      short loc_18005BF4B
0x18005bf37  mov     edx, 43h ; 'C'
0x18005bf3c  mov     r9d, ebx
0x18005bf3f  mov     rcx, [rcx+10h]
0x18005bf43  mov     r8, r12
0x18005bf46  call    WPP_SF_d
0x18005bf4b  lea     rcx, ?gBdesvcServerRotationStatusCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005bf52  call    cs:__imp_LeaveCriticalSection
0x18005bf59  nop     dword ptr [rax+rax+00h]
0x18005bf5e  test    rdi, rdi
0x18005bf61  jz      short loc_18005BF6B
0x18005bf63  mov     rcx, rdi; void *
0x18005bf66  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18005bf6b  test    bpl, bpl
0x18005bf6e  jz      short loc_18005BFA6
0x18005bf70  call    cs:__imp_RpcRevertToSelf
0x18005bf77  nop     dword ptr [rax+rax+00h]
0x18005bf7c  test    eax, eax
0x18005bf7e  jz      short loc_18005BFA6
0x18005bf80  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf87  cmp     rcx, r15
0x18005bf8a  jz      short loc_18005BFCC
0x18005bf8c  test    byte ptr [rcx+1Ch], 2
0x18005bf90  jz      short loc_18005BFAD
0x18005bf92  mov     rcx, [rcx+10h]
0x18005bf96  mov     edx, 4Bh ; 'K'
0x18005bf9b  mov     r9d, eax
0x18005bf9e  mov     r8, r12
0x18005bfa1  call    WPP_SF_d
0x18005bfa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bfad  cmp     rcx, r15
0x18005bfb0  jz      short loc_18005BFCC
0x18005bfb2  test    byte ptr [rcx+1Ch], 20h
0x18005bfb6  jz      short loc_18005BFCC
0x18005bfb8  mov     rcx, [rcx+10h]
0x18005bfbc  mov     edx, 4Ch ; 'L'
0x18005bfc1  mov     r9d, ebx
0x18005bfc4  mov     r8, r12
0x18005bfc7  call    WPP_SF_d
0x18005bfcc  mov     eax, ebx
0x18005bfce  mov     rcx, [rsp+58h+var_30]
0x18005bfd3  xor     rcx, rsp; StackCookie
0x18005bfd6  call    __security_check_cookie
0x18005bfdb  mov     rbx, [rsp+58h+arg_0]
0x18005bfe0  mov     rbp, [rsp+58h+arg_18]
0x18005bfe5  add     rsp, 30h
0x18005bfe9  pop     r15
0x18005bfeb  pop     r14
0x18005bfed  pop     r12
0x18005bfef  pop     rdi
0x18005bff0  pop     rsi
0x18005bff1  retn
```

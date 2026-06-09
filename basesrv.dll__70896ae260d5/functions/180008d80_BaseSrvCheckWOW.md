# BaseSrvCheckWOW

- ea: `0x180008d80`
- end: `0x18000910b`
- name: `BaseSrvCheckWOW`
- size: `907`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b80`

## callees

- `0x1800083b4`
- `0x180008514`
- `0x1800085bc`
- `0x180008d80`
- `0x1800091dc`
- `0x180009698`
- `0x18000a3b0`
- `0x18000a674`
- `0x18000a894`
- `0x18000c7c4`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x180008e7f`
- `ntdll!NtClose` at `0x180008fce`
- `ntdll!NtClose` at `0x180008e7f`
- `ntdll!NtClose` at `0x180008fce`
- `ntdll!RtlEnterCriticalSection` at `0x180008dce`
- `ntdll!RtlEnterCriticalSection` at `0x180008dce`
- `ntdll!RtlLeaveCriticalSection` at `0x180008fe1`
- `ntdll!RtlLeaveCriticalSection` at `0x180008fe1`
- `ntdll!NtSetEvent` at `0x180008f6b`
- `ntdll!NtSetEvent` at `0x180008f6b`
- `ntdll!RtlCompareUnicodeString` at `0x1800090ce`
- `ntdll!RtlCompareUnicodeString` at `0x1800090ce`
- `ntdll!NtCompareTokens` at `0x180008e63`
- `ntdll!NtCompareTokens` at `0x180008e63`
- `CSRSRV!CsrUnlockProcess` at `0x180009052`
- `CSRSRV!CsrUnlockProcess` at `0x180009052`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009032`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009032`

## pseudocode

```c
__int64 __fastcall BaseSrvCheckWOW(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r12
  __int64 v5; // rdx
  int SharedWow; // ebx
  __int64 v7; // rdi
  _QWORD *v8; // rcx
  __int64 WOWRecord; // rax
  _QWORD *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rsi
  HANDLE FirstTokenHandle; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+40h] [rbp-40h] BYREF
  __int64 v19; // [rsp+48h] [rbp-38h] BYREF
  __int64 v20; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v21[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h]
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 Equal; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  v20 = -1;
  v17 = -1;
  v21[1] = 0;
  v25 = 0;
  v18 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  v19 = 0;
  FirstTokenHandle = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SourceString.Buffer = 0;
  SharedWow = BaseSrvFindSharedWow(a1, v5, &SourceString, &v18);
  if ( SharedWow < 0 )
  {
    *(_DWORD *)(a1 + 128) = 0;
    goto LABEL_31;
  }
  v7 = v18;
  if ( v18 )
  {
    Equal = 0;
    if ( (*(_BYTE *)(v18 + 48) & 8) != 0 )
    {
      SharedWow = OkToRunInSharedWOW(a2, &v25, &FirstTokenHandle);
      if ( SharedWow >= 0 )
      {
        if ( v25 == *(_QWORD *)(v7 + 64) && ((v8 = *(_QWORD **)(a1 + 176)) == 0 || v25 == *v8) )
          NtCompareTokens(FirstTokenHandle, *(HANDLE *)(v7 + 72), &Equal);
        else
          SharedWow = -1073741790;
      }
      if ( FirstTokenHandle )
        NtClose(FirstTokenHandle);
      if ( SharedWow >= 0 )
      {
        WOWRecord = BaseSrvAllocateWOWRecord();
        v10 = (_QWORD *)WOWRecord;
        if ( !WOWRecord )
        {
LABEL_33:
          SharedWow = -1073741801;
          goto LABEL_31;
        }
        v21[0] = 32;
        v22 = WOWRecord;
        if ( !(unsigned int)BaseSrvCopyCommand(a1, v21) )
        {
          BaseSrvFreeWOWRecord(v10);
          goto LABEL_33;
        }
        SharedWow = BaseSrvCreatePairWaitHandles(&v20, &v17);
        if ( SharedWow >= 0 )
        {
          v10[1] = v20;
          v10[2] = v17;
          *(_QWORD *)(a1 + 24) = v17;
          *(_WORD *)(a1 + 174) = 4;
          *(_DWORD *)a1 = *(_DWORD *)v10;
          BaseSrvAddWOWRecord(v7, v10);
          if ( UserNotifyProcessCreate )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))UserNotifyProcessCreate)(
              *(unsigned int *)v10,
              *((unsigned int *)NtCurrentTeb()->CsrClientThread + 12),
              (unsigned int)v17);
            v7 = v18;
          }
          if ( *(_QWORD *)(v7 + 16) )
          {
            *(_BYTE *)(BaseSrvpStaticServerData + 2037) = 1;
            NtSetEvent(*(HANDLE *)(v7 + 16), 0);
          }
        }
        else
        {
          BaseSrvFreeWOWRecord(v10);
        }
      }
    }
  }
  else
  {
    if ( *(_WORD *)(a1 + 164) > 0x80u )
    {
      SharedWow = -1073741811;
      goto LABEL_31;
    }
    SharedWow = OkToRunInSharedWOW(a2, &v25, &FirstTokenHandle);
    if ( SharedWow >= 0 )
    {
      v11 = *(_QWORD **)(a1 + 176);
      if ( !v11 || v25 == *v11 )
      {
        v13 = BaseSrvAllocateSharedWowRecord(&SourceString);
        if ( !v13 )
          goto LABEL_33;
        *(_QWORD *)(v13 + 72) = FirstTokenHandle;
        SharedWow = CsrLockProcessByClientId(a2, &v19);
        if ( SharedWow >= 0 )
        {
          *(_DWORD *)(v13 + 84) = *(_DWORD *)(v19 + 88);
          CsrUnlockProcess(v19);
          v14 = BaseSrvAllocateWOWRecord();
          *(_QWORD *)(v13 + 56) = v14;
          if ( v14 )
          {
            v21[0] = 32;
            v22 = v14;
            if ( (unsigned int)BaseSrvCopyCommand(a1, v21) )
            {
              *(_QWORD *)(v13 + 64) = v25;
              *(_DWORD *)(v13 + 48) = 8;
              *(_DWORD *)a1 = **(_DWORD **)(v13 + 56);
              v15 = gWowHead;
              if ( !gWowHead )
                goto LABEL_43;
              do
              {
                if ( RtlCompareUnicodeString((PCUNICODE_STRING)(v15 + 32), (PCUNICODE_STRING)(v13 + 32), 1u) > 0 )
                  break;
                v2 = (_QWORD *)v15;
                v15 = *(_QWORD *)v15;
              }
              while ( v15 );
              *(_QWORD *)v13 = v15;
              if ( v2 )
                *v2 = v13;
              else
LABEL_43:
                gWowHead = v13;
              *(_WORD *)(a1 + 174) = 1;
              goto LABEL_31;
            }
          }
          SharedWow = -1073741801;
        }
        BaseSrvFreeSharedWowRecord(v13);
        goto LABEL_31;
      }
      SharedWow = -1073741790;
    }
    if ( FirstTokenHandle )
      NtClose(FirstTokenHandle);
  }
LABEL_31:
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWow;
}

```

## disassembly

```asm
0x180008d80  mov     [rsp-38h+arg_0], rbx
0x180008d85  push    rbp
0x180008d86  push    rsi
0x180008d87  push    rdi
0x180008d88  push    r12
0x180008d8a  push    r13
0x180008d8c  push    r14
0x180008d8e  push    r15
0x180008d90  mov     rbp, rsp
0x180008d93  sub     rsp, 80h
0x180008d9a  xor     r12d, r12d
0x180008d9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008da1  mov     r14, rcx
0x180008da4  mov     [rbp+var_30], rax
0x180008da8  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008daf  mov     [rbp+var_48], rax
0x180008db3  mov     [rbp+var_24], r12d
0x180008db7  mov     rsi, rdx
0x180008dba  mov     [rbp+arg_18], r12
0x180008dbe  mov     [rbp+var_40], r12
0x180008dc2  mov     qword ptr [rbp+SourceString.Length], r12
0x180008dc6  mov     [rbp+var_38], r12
0x180008dca  mov     [rbp+FirstTokenHandle], r12
0x180008dce  call    cs:__imp_RtlEnterCriticalSection
0x180008dd5  nop     dword ptr [rax+rax+00h]
0x180008dda  lea     r9, [rbp+var_40]
0x180008dde  mov     [rbp+SourceString.Buffer], r12
0x180008de2  lea     r8, [rbp+SourceString]
0x180008de6  mov     rcx, r14
0x180008de9  call    BaseSrvFindSharedWow
0x180008dee  mov     ebx, eax
0x180008df0  test    eax, eax
0x180008df2  jns     short loc_180008E00
0x180008df4  mov     [r14+80h], r12d
0x180008dfb  jmp     loc_180008FDA
0x180008e00  mov     rdi, [rbp+var_40]
0x180008e04  test    rdi, rdi
0x180008e07  jz      loc_180008F79
0x180008e0d  mov     [rbp+Equal], r12b
0x180008e11  test    byte ptr [rdi+30h], 8
0x180008e15  jz      loc_180008FDA
0x180008e1b  lea     r8, [rbp+FirstTokenHandle]
0x180008e1f  mov     rcx, rsi
0x180008e22  lea     rdx, [rbp+arg_18]
0x180008e26  call    OkToRunInSharedWOW
0x180008e2b  mov     ebx, eax
0x180008e2d  test    eax, eax
0x180008e2f  js      short loc_180008E76
0x180008e31  mov     rax, [rbp+arg_18]
0x180008e35  cmp     eax, [rdi+40h]
0x180008e38  jnz     short loc_180008E71
0x180008e3a  mov     edx, dword ptr [rbp+arg_18+4]
0x180008e3d  cmp     edx, [rdi+44h]
0x180008e40  jnz     short loc_180008E71
0x180008e42  mov     rcx, [r14+0B0h]
0x180008e49  test    rcx, rcx
0x180008e4c  jz      short loc_180008E57
0x180008e4e  cmp     eax, [rcx]
0x180008e50  jnz     short loc_180008E71
0x180008e52  cmp     edx, [rcx+4]
0x180008e55  jnz     short loc_180008E71
0x180008e57  mov     rdx, [rdi+48h]; SecondTokenHandle
0x180008e5b  lea     r8, [rbp+Equal]; Equal
0x180008e5f  mov     rcx, [rbp+FirstTokenHandle]; FirstTokenHandle
0x180008e63  call    cs:__imp_NtCompareTokens
0x180008e6a  nop     dword ptr [rax+rax+00h]
0x180008e6f  jmp     short loc_180008E76
0x180008e71  mov     ebx, 0C0000022h
0x180008e76  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x180008e7a  test    rcx, rcx
0x180008e7d  jz      short loc_180008E8B
0x180008e7f  call    cs:__imp_NtClose
0x180008e86  nop     dword ptr [rax+rax+00h]
0x180008e8b  test    ebx, ebx
0x180008e8d  js      loc_180008FDA
0x180008e93  call    BaseSrvAllocateWOWRecord
0x180008e98  mov     rsi, rax
0x180008e9b  test    rax, rax
0x180008e9e  jz      loc_18000901C
0x180008ea4  lea     rdx, [rbp+var_28]
0x180008ea8  mov     [rbp+var_28], 20h ; ' '
0x180008eaf  mov     rcx, r14
0x180008eb2  mov     [rbp+var_20], rax
0x180008eb6  call    BaseSrvCopyCommand
0x180008ebb  test    eax, eax
0x180008ebd  jnz     short loc_180008ECC
0x180008ebf  mov     rcx, rsi; P
0x180008ec2  call    BaseSrvFreeWOWRecord
0x180008ec7  jmp     loc_18000901C
0x180008ecc  lea     rdx, [rbp+var_48]
0x180008ed0  lea     rcx, [rbp+var_30]
0x180008ed4  call    BaseSrvCreatePairWaitHandles
0x180008ed9  mov     ebx, eax
0x180008edb  test    eax, eax
0x180008edd  jns     short loc_180008EEC
0x180008edf  mov     rcx, rsi; P
0x180008ee2  call    BaseSrvFreeWOWRecord
0x180008ee7  jmp     loc_180008FDA
0x180008eec  mov     rax, [rbp+var_30]
0x180008ef0  mov     r9d, 4
0x180008ef6  mov     [rsi+8], rax
0x180008efa  mov     rdx, rsi
0x180008efd  mov     rax, [rbp+var_48]
0x180008f01  mov     rcx, rdi
0x180008f04  mov     [rsi+10h], rax
0x180008f08  mov     rax, [rbp+var_48]
0x180008f0c  mov     [r14+18h], rax
0x180008f10  mov     [r14+0AEh], r9w
0x180008f18  mov     eax, [rsi]
0x180008f1a  mov     [r14], eax
0x180008f1d  call    BaseSrvAddWOWRecord
0x180008f22  cmp     cs:UserNotifyProcessCreate, r12
0x180008f29  jz      short loc_180008F4D
0x180008f2b  mov     rdx, gs:70h
0x180008f34  mov     r8d, dword ptr [rbp+var_48]
0x180008f38  mov     ecx, [rsi]
0x180008f3a  mov     rax, cs:UserNotifyProcessCreate
0x180008f41  mov     edx, [rdx+30h]
0x180008f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f49  mov     rdi, [rbp+var_40]
0x180008f4d  cmp     [rdi+10h], r12
0x180008f51  jz      loc_180008FDA
0x180008f57  mov     rax, cs:BaseSrvpStaticServerData
0x180008f5e  xor     edx, edx; PreviousState
0x180008f60  mov     byte ptr [rax+7F5h], 1
0x180008f67  mov     rcx, [rdi+10h]; EventHandle
0x180008f6b  call    cs:__imp_NtSetEvent
0x180008f72  nop     dword ptr [rax+rax+00h]
0x180008f77  jmp     short loc_180008FDA
0x180008f79  mov     eax, 80h
0x180008f7e  cmp     [r14+0A4h], ax
0x180008f86  jbe     short loc_180008F8F
0x180008f88  mov     ebx, 0C000000Dh
0x180008f8d  jmp     short loc_180008FDA
0x180008f8f  lea     r8, [rbp+FirstTokenHandle]
0x180008f93  mov     rcx, rsi
0x180008f96  lea     rdx, [rbp+arg_18]
0x180008f9a  call    OkToRunInSharedWOW
0x180008f9f  mov     ebx, eax
0x180008fa1  test    eax, eax
0x180008fa3  js      short loc_180008FC5
0x180008fa5  mov     rcx, [r14+0B0h]
0x180008fac  test    rcx, rcx
0x180008faf  jz      short loc_18000900B
0x180008fb1  mov     eax, [rcx]
0x180008fb3  cmp     dword ptr [rbp+arg_18], eax
0x180008fb6  jnz     short loc_180008FC0
0x180008fb8  mov     eax, [rcx+4]
0x180008fbb  cmp     dword ptr [rbp+arg_18+4], eax
0x180008fbe  jz      short loc_18000900B
0x180008fc0  mov     ebx, 0C0000022h
0x180008fc5  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x180008fc9  test    rcx, rcx
0x180008fcc  jz      short loc_180008FDA
0x180008fce  call    cs:__imp_NtClose
0x180008fd5  nop     dword ptr [rax+rax+00h]
0x180008fda  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180008fe1  call    cs:__imp_RtlLeaveCriticalSection
0x180008fe8  nop     dword ptr [rax+rax+00h]
0x180008fed  mov     eax, ebx
0x180008fef  mov     rbx, [rsp+80h+arg_0]
0x180008ff7  add     rsp, 80h
0x180008ffe  pop     r15
0x180009000  pop     r14
0x180009002  pop     r13
0x180009004  pop     r12
0x180009006  pop     rdi
0x180009007  pop     rsi
0x180009008  pop     rbp
0x180009009  retn
0x18000900b  lea     rcx, [rbp+SourceString]; SourceString
0x18000900f  call    BaseSrvAllocateSharedWowRecord
0x180009014  mov     rdi, rax
0x180009017  test    rax, rax
0x18000901a  jnz     short loc_180009023
0x18000901c  mov     ebx, 0C0000017h
0x180009021  jmp     short loc_180008FDA
0x180009023  mov     rax, [rbp+FirstTokenHandle]
0x180009027  lea     rdx, [rbp+var_38]
0x18000902b  mov     rcx, rsi
0x18000902e  mov     [rdi+48h], rax
0x180009032  call    cs:__imp_CsrLockProcessByClientId
0x180009039  nop     dword ptr [rax+rax+00h]
0x18000903e  mov     ebx, eax
0x180009040  test    eax, eax
0x180009042  js      short loc_18000908C
0x180009044  mov     rax, [rbp+var_38]
0x180009048  mov     ecx, [rax+58h]
0x18000904b  mov     [rdi+54h], ecx
0x18000904e  mov     rcx, [rbp+var_38]
0x180009052  call    cs:__imp_CsrUnlockProcess
0x180009059  nop     dword ptr [rax+rax+00h]
0x18000905e  call    BaseSrvAllocateWOWRecord
0x180009063  mov     [rdi+38h], rax
0x180009067  test    rax, rax
0x18000906a  jz      short loc_180009087
0x18000906c  lea     rdx, [rbp+var_28]
0x180009070  mov     [rbp+var_28], 20h ; ' '
0x180009077  mov     rcx, r14
0x18000907a  mov     [rbp+var_20], rax
0x18000907e  call    BaseSrvCopyCommand
0x180009083  test    eax, eax
0x180009085  jnz     short loc_180009099
0x180009087  mov     ebx, 0C0000017h
0x18000908c  mov     rcx, rdi
0x18000908f  call    BaseSrvFreeSharedWowRecord
0x180009094  jmp     loc_180008FDA
0x180009099  mov     rax, [rbp+arg_18]
0x18000909d  mov     r15d, 1
0x1800090a3  mov     [rdi+40h], rax
0x1800090a7  mov     dword ptr [rdi+30h], 8
0x1800090ae  mov     rax, [rdi+38h]
0x1800090b2  mov     ecx, [rax]
0x1800090b4  mov     [r14], ecx
0x1800090b7  mov     rsi, cs:gWowHead
0x1800090be  test    rsi, rsi
0x1800090c1  jz      short loc_1800090F1
0x1800090c3  lea     rcx, [rsi+20h]; String1
0x1800090c7  mov     r8b, r15b; CaseInsensitive
0x1800090ca  lea     rdx, [rdi+20h]; String2
0x1800090ce  call    cs:__imp_RtlCompareUnicodeString
0x1800090d5  nop     dword ptr [rax+rax+00h]
0x1800090da  test    eax, eax
0x1800090dc  jg      short loc_1800090E9
0x1800090de  mov     r12, rsi
0x1800090e1  mov     rsi, [rsi]
0x1800090e4  test    rsi, rsi
0x1800090e7  jnz     short loc_1800090C3
0x1800090e9  mov     [rdi], rsi
0x1800090ec  test    r12, r12
0x1800090ef  jnz     short loc_1800090FA
0x1800090f1  mov     cs:gWowHead, rdi
0x1800090f8  jmp     short loc_1800090FE
0x1800090fa  mov     [r12], rdi
0x1800090fe  mov     [r14+0AEh], r15w
0x180009106  jmp     loc_180008FDA
```

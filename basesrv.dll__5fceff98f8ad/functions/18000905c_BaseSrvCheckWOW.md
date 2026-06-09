# BaseSrvCheckWOW

- ea: `0x18000905c`
- end: `0x1800093e0`
- name: `BaseSrvCheckWOW`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008e70`

## callees

- `0x1800086a4`
- `0x180008808`
- `0x1800088b0`
- `0x18000905c`
- `0x1800094cc`
- `0x18000996c`
- `0x18000a640`
- `0x18000a8f8`
- `0x18000ab1c`
- `0x18000cb9c`
- `0x18000e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000915b`
- `ntdll!NtClose` at `0x1800092a6`
- `ntdll!NtClose` at `0x18000915b`
- `ntdll!NtClose` at `0x1800092a6`
- `ntdll!RtlEnterCriticalSection` at `0x1800090aa`
- `ntdll!RtlEnterCriticalSection` at `0x1800090aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800092b9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800092b9`
- `ntdll!NtSetEvent` at `0x180009243`
- `ntdll!NtSetEvent` at `0x180009243`
- `ntdll!RtlCompareUnicodeString` at `0x1800093a3`
- `ntdll!RtlCompareUnicodeString` at `0x1800093a3`
- `ntdll!NtCompareTokens` at `0x18000913f`
- `ntdll!NtCompareTokens` at `0x18000913f`
- `CSRSRV!CsrUnlockProcess` at `0x180009327`
- `CSRSRV!CsrUnlockProcess` at `0x180009327`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009307`
- `CSRSRV!CsrLockProcessByClientId` at `0x180009307`

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
  HANDLE FirstTokenHandle; // [rsp+30h] [rbp-40h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v20[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h]
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-10h] BYREF
  __int64 Equal; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  v19 = -1;
  v17 = -1;
  v20[1] = 0;
  v24 = 0;
  Equal = 0;
  *(_QWORD *)&SourceString.Length = 0;
  v18 = 0;
  FirstTokenHandle = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SourceString.Buffer = 0;
  SharedWow = BaseSrvFindSharedWow(a1, v5, &SourceString, &Equal);
  if ( SharedWow < 0 )
  {
    *(_DWORD *)(a1 + 128) = 0;
    goto LABEL_31;
  }
  v7 = Equal;
  if ( Equal )
  {
    LOBYTE(Equal) = 0;
    if ( (*(_BYTE *)(v7 + 48) & 8) != 0 )
    {
      SharedWow = OkToRunInSharedWOW(a2, &v24, &FirstTokenHandle);
      if ( SharedWow >= 0 )
      {
        if ( v24 == *(_QWORD *)(v7 + 64) && ((v8 = *(_QWORD **)(a1 + 176)) == 0 || v24 == *v8) )
          NtCompareTokens(FirstTokenHandle, *(HANDLE *)(v7 + 72), (PBOOLEAN)&Equal);
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
        v20[0] = 32;
        v21 = WOWRecord;
        if ( !(unsigned int)BaseSrvCopyCommand(a1, (__int64)v20) )
        {
          BaseSrvFreeWOWRecord(v10);
          goto LABEL_33;
        }
        SharedWow = BaseSrvCreatePairWaitHandles(&v19, &v17);
        if ( SharedWow >= 0 )
        {
          v10[1] = v19;
          v10[2] = v17;
          *(_QWORD *)(a1 + 24) = v17;
          *(_WORD *)(a1 + 174) = 4;
          *(_DWORD *)a1 = *(_DWORD *)v10;
          BaseSrvAddWOWRecord(v7, v10);
          if ( UserNotifyProcessCreate )
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))UserNotifyProcessCreate)(
              *(unsigned int *)v10,
              *((unsigned int *)NtCurrentTeb()->CsrClientThread + 12),
              (unsigned int)v17);
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
    SharedWow = OkToRunInSharedWOW(a2, &v24, &FirstTokenHandle);
    if ( SharedWow >= 0 )
    {
      v11 = *(_QWORD **)(a1 + 176);
      if ( !v11 || v24 == *v11 )
      {
        v13 = BaseSrvAllocateSharedWowRecord(&SourceString);
        if ( !v13 )
          goto LABEL_33;
        *(_QWORD *)(v13 + 72) = FirstTokenHandle;
        SharedWow = CsrLockProcessByClientId(a2, &v18);
        if ( SharedWow >= 0 )
        {
          *(_DWORD *)(v13 + 84) = *(_DWORD *)(v18 + 88);
          CsrUnlockProcess(v18);
          v14 = BaseSrvAllocateWOWRecord();
          *(_QWORD *)(v13 + 56) = v14;
          if ( v14 )
          {
            v20[0] = 32;
            v21 = v14;
            if ( (unsigned int)BaseSrvCopyCommand(a1, (__int64)v20) )
            {
              *(_QWORD *)(v13 + 64) = v24;
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
0x18000905c  mov     [rsp-38h+arg_0], rbx
0x180009061  push    rbp
0x180009062  push    rsi
0x180009063  push    rdi
0x180009064  push    r12
0x180009066  push    r13
0x180009068  push    r14
0x18000906a  push    r15
0x18000906c  mov     rbp, rsp
0x18000906f  sub     rsp, 70h
0x180009073  xor     r12d, r12d
0x180009076  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000907a  mov     r14, rcx
0x18000907d  mov     [rbp+var_28], rax
0x180009081  xorps   xmm0, xmm0
0x180009084  mov     [rbp+var_38], rax
0x180009088  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000908f  mov     [rbp+var_1C], r12d
0x180009093  mov     [rbp+arg_18], r12
0x180009097  mov     rsi, rdx
0x18000909a  mov     [rbp+Equal], r12
0x18000909e  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x1800090a2  mov     [rbp+var_30], r12
0x1800090a6  mov     [rbp+FirstTokenHandle], r12
0x1800090aa  call    cs:__imp_RtlEnterCriticalSection
0x1800090b1  nop     dword ptr [rax+rax+00h]
0x1800090b6  lea     r9, [rbp+Equal]
0x1800090ba  mov     [rbp+SourceString.Buffer], r12
0x1800090be  lea     r8, [rbp+SourceString]
0x1800090c2  mov     rcx, r14
0x1800090c5  call    BaseSrvFindSharedWow
0x1800090ca  mov     ebx, eax
0x1800090cc  test    eax, eax
0x1800090ce  jns     short loc_1800090DC
0x1800090d0  mov     [r14+80h], r12d
0x1800090d7  jmp     loc_1800092B2
0x1800090dc  mov     rdi, [rbp+Equal]
0x1800090e0  test    rdi, rdi
0x1800090e3  jz      loc_180009251
0x1800090e9  mov     byte ptr [rbp+Equal], r12b
0x1800090ed  test    byte ptr [rdi+30h], 8
0x1800090f1  jz      loc_1800092B2
0x1800090f7  lea     r8, [rbp+FirstTokenHandle]
0x1800090fb  mov     rcx, rsi
0x1800090fe  lea     rdx, [rbp+arg_18]
0x180009102  call    OkToRunInSharedWOW
0x180009107  mov     ebx, eax
0x180009109  test    eax, eax
0x18000910b  js      short loc_180009152
0x18000910d  mov     rax, [rbp+arg_18]
0x180009111  cmp     eax, [rdi+40h]
0x180009114  jnz     short loc_18000914D
0x180009116  mov     edx, dword ptr [rbp+arg_18+4]
0x180009119  cmp     edx, [rdi+44h]
0x18000911c  jnz     short loc_18000914D
0x18000911e  mov     rcx, [r14+0B0h]
0x180009125  test    rcx, rcx
0x180009128  jz      short loc_180009133
0x18000912a  cmp     eax, [rcx]
0x18000912c  jnz     short loc_18000914D
0x18000912e  cmp     edx, [rcx+4]
0x180009131  jnz     short loc_18000914D
0x180009133  mov     rdx, [rdi+48h]; SecondTokenHandle
0x180009137  lea     r8, [rbp+Equal]; Equal
0x18000913b  mov     rcx, [rbp+FirstTokenHandle]; FirstTokenHandle
0x18000913f  call    cs:__imp_NtCompareTokens
0x180009146  nop     dword ptr [rax+rax+00h]
0x18000914b  jmp     short loc_180009152
0x18000914d  mov     ebx, 0C0000022h
0x180009152  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x180009156  test    rcx, rcx
0x180009159  jz      short loc_180009167
0x18000915b  call    cs:__imp_NtClose
0x180009162  nop     dword ptr [rax+rax+00h]
0x180009167  test    ebx, ebx
0x180009169  js      loc_1800092B2
0x18000916f  call    BaseSrvAllocateWOWRecord
0x180009174  mov     rsi, rax
0x180009177  test    rax, rax
0x18000917a  jz      loc_1800092F1
0x180009180  lea     rdx, [rbp+var_20]
0x180009184  mov     [rbp+var_20], 20h ; ' '
0x18000918b  mov     rcx, r14
0x18000918e  mov     [rbp+var_18], rax
0x180009192  call    BaseSrvCopyCommand
0x180009197  test    eax, eax
0x180009199  jnz     short loc_1800091A8
0x18000919b  mov     rcx, rsi; P
0x18000919e  call    BaseSrvFreeWOWRecord
0x1800091a3  jmp     loc_1800092F1
0x1800091a8  lea     rdx, [rbp+var_38]
0x1800091ac  lea     rcx, [rbp+var_28]
0x1800091b0  call    BaseSrvCreatePairWaitHandles
0x1800091b5  mov     ebx, eax
0x1800091b7  test    eax, eax
0x1800091b9  jns     short loc_1800091C8
0x1800091bb  mov     rcx, rsi; P
0x1800091be  call    BaseSrvFreeWOWRecord
0x1800091c3  jmp     loc_1800092B2
0x1800091c8  mov     rax, [rbp+var_28]
0x1800091cc  mov     r9d, 4
0x1800091d2  mov     [rsi+8], rax
0x1800091d6  mov     rdx, rsi
0x1800091d9  mov     rax, [rbp+var_38]
0x1800091dd  mov     rcx, rdi
0x1800091e0  mov     [rsi+10h], rax
0x1800091e4  mov     rax, [rbp+var_38]
0x1800091e8  mov     [r14+18h], rax
0x1800091ec  mov     [r14+0AEh], r9w
0x1800091f4  mov     eax, [rsi]
0x1800091f6  mov     [r14], eax
0x1800091f9  call    BaseSrvAddWOWRecord
0x1800091fe  cmp     cs:UserNotifyProcessCreate, r12
0x180009205  jz      short loc_180009225
0x180009207  mov     rdx, gs:70h
0x180009210  mov     r8d, dword ptr [rbp+var_38]
0x180009214  mov     ecx, [rsi]
0x180009216  mov     rax, cs:UserNotifyProcessCreate
0x18000921d  mov     edx, [rdx+30h]
0x180009220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009225  cmp     [rdi+10h], r12
0x180009229  jz      loc_1800092B2
0x18000922f  mov     rax, cs:BaseSrvpStaticServerData
0x180009236  xor     edx, edx; PreviousState
0x180009238  mov     byte ptr [rax+7F5h], 1
0x18000923f  mov     rcx, [rdi+10h]; EventHandle
0x180009243  call    cs:__imp_NtSetEvent
0x18000924a  nop     dword ptr [rax+rax+00h]
0x18000924f  jmp     short loc_1800092B2
0x180009251  mov     eax, 80h
0x180009256  cmp     [r14+0A4h], ax
0x18000925e  jbe     short loc_180009267
0x180009260  mov     ebx, 0C000000Dh
0x180009265  jmp     short loc_1800092B2
0x180009267  lea     r8, [rbp+FirstTokenHandle]
0x18000926b  mov     rcx, rsi
0x18000926e  lea     rdx, [rbp+arg_18]
0x180009272  call    OkToRunInSharedWOW
0x180009277  mov     ebx, eax
0x180009279  test    eax, eax
0x18000927b  js      short loc_18000929D
0x18000927d  mov     rcx, [r14+0B0h]
0x180009284  test    rcx, rcx
0x180009287  jz      short loc_1800092E0
0x180009289  mov     eax, [rcx]
0x18000928b  cmp     dword ptr [rbp+arg_18], eax
0x18000928e  jnz     short loc_180009298
0x180009290  mov     eax, [rcx+4]
0x180009293  cmp     dword ptr [rbp+arg_18+4], eax
0x180009296  jz      short loc_1800092E0
0x180009298  mov     ebx, 0C0000022h
0x18000929d  mov     rcx, [rbp+FirstTokenHandle]; Handle
0x1800092a1  test    rcx, rcx
0x1800092a4  jz      short loc_1800092B2
0x1800092a6  call    cs:__imp_NtClose
0x1800092ad  nop     dword ptr [rax+rax+00h]
0x1800092b2  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x1800092b9  call    cs:__imp_RtlLeaveCriticalSection
0x1800092c0  nop     dword ptr [rax+rax+00h]
0x1800092c5  mov     eax, ebx
0x1800092c7  mov     rbx, [rsp+70h+arg_0]
0x1800092cf  add     rsp, 70h
0x1800092d3  pop     r15
0x1800092d5  pop     r14
0x1800092d7  pop     r13
0x1800092d9  pop     r12
0x1800092db  pop     rdi
0x1800092dc  pop     rsi
0x1800092dd  pop     rbp
0x1800092de  retn
0x1800092e0  lea     rcx, [rbp+SourceString]; SourceString
0x1800092e4  call    BaseSrvAllocateSharedWowRecord
0x1800092e9  mov     rdi, rax
0x1800092ec  test    rax, rax
0x1800092ef  jnz     short loc_1800092F8
0x1800092f1  mov     ebx, 0C0000017h
0x1800092f6  jmp     short loc_1800092B2
0x1800092f8  mov     rax, [rbp+FirstTokenHandle]
0x1800092fc  lea     rdx, [rbp+var_30]
0x180009300  mov     rcx, rsi
0x180009303  mov     [rdi+48h], rax
0x180009307  call    cs:__imp_CsrLockProcessByClientId
0x18000930e  nop     dword ptr [rax+rax+00h]
0x180009313  mov     ebx, eax
0x180009315  test    eax, eax
0x180009317  js      short loc_180009361
0x180009319  mov     rax, [rbp+var_30]
0x18000931d  mov     ecx, [rax+58h]
0x180009320  mov     [rdi+54h], ecx
0x180009323  mov     rcx, [rbp+var_30]
0x180009327  call    cs:__imp_CsrUnlockProcess
0x18000932e  nop     dword ptr [rax+rax+00h]
0x180009333  call    BaseSrvAllocateWOWRecord
0x180009338  mov     [rdi+38h], rax
0x18000933c  test    rax, rax
0x18000933f  jz      short loc_18000935C
0x180009341  lea     rdx, [rbp+var_20]
0x180009345  mov     [rbp+var_20], 20h ; ' '
0x18000934c  mov     rcx, r14
0x18000934f  mov     [rbp+var_18], rax
0x180009353  call    BaseSrvCopyCommand
0x180009358  test    eax, eax
0x18000935a  jnz     short loc_18000936E
0x18000935c  mov     ebx, 0C0000017h
0x180009361  mov     rcx, rdi
0x180009364  call    BaseSrvFreeSharedWowRecord
0x180009369  jmp     loc_1800092B2
0x18000936e  mov     rax, [rbp+arg_18]
0x180009372  mov     r15d, 1
0x180009378  mov     [rdi+40h], rax
0x18000937c  mov     dword ptr [rdi+30h], 8
0x180009383  mov     rax, [rdi+38h]
0x180009387  mov     ecx, [rax]
0x180009389  mov     [r14], ecx
0x18000938c  mov     rsi, cs:gWowHead
0x180009393  test    rsi, rsi
0x180009396  jz      short loc_1800093C6
0x180009398  lea     rcx, [rsi+20h]; String1
0x18000939c  mov     r8b, r15b; CaseInsensitive
0x18000939f  lea     rdx, [rdi+20h]; String2
0x1800093a3  call    cs:__imp_RtlCompareUnicodeString
0x1800093aa  nop     dword ptr [rax+rax+00h]
0x1800093af  test    eax, eax
0x1800093b1  jg      short loc_1800093BE
0x1800093b3  mov     r12, rsi
0x1800093b6  mov     rsi, [rsi]
0x1800093b9  test    rsi, rsi
0x1800093bc  jnz     short loc_180009398
0x1800093be  mov     [rdi], rsi
0x1800093c1  test    r12, r12
0x1800093c4  jnz     short loc_1800093CF
0x1800093c6  mov     cs:gWowHead, rdi
0x1800093cd  jmp     short loc_1800093D3
0x1800093cf  mov     [r12], rdi
0x1800093d3  mov     [r14+0AEh], r15w
0x1800093db  jmp     loc_1800092B2
```

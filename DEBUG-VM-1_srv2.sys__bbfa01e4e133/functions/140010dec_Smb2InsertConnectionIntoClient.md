# Smb2InsertConnectionIntoClient

- ea: `0x140010dec`
- end: `0x14001120e`
- name: `Smb2InsertConnectionIntoClient`
- size: `1058`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400921f0`

## callees

- `0x14000b130`
- `0x14000bb80`
- `0x14000bbb8`
- `0x140010dec`
- `0x140011580`
- `0x1400139d0`
- `0x1400222ec`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140010f87`
- `ntoskrnl!KeDelayExecutionThread` at `0x140010f87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e1f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010e1f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010ef1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010f04`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010ef1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140010f04`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010f33`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010f42`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110d8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011141`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010f33`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140010f42`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400110d8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140011141`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010f54`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001103a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400110ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001116f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010eae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010f54`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010fd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001103a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400110ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001116f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111e4`

## pseudocode

```c
__int64 __fastcall Smb2InsertConnectionIntoClient(__int64 a1)
{
  __int64 v1; // rbx
  KSPIN_LOCK *v2; // rdi
  int v3; // r15d
  unsigned int v4; // r14d
  KIRQL v6; // al
  KIRQL v7; // bp
  _QWORD *v8; // r13
  int v9; // r12d
  __int64 v10; // rbx
  __int64 Client; // rax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // [rsp+70h] [rbp+8h]
  union _LARGE_INTEGER Interval; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 496);
  v2 = (KSPIN_LOCK *)(a1 + 184);
  v3 = 0;
  v19 = v1;
  v4 = 0;
  while ( 1 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc(v2);
    v7 = v6;
    if ( *(_DWORD *)(a1 + 12) != 220 )
      break;
    v8 = (_QWORD *)(a1 + 464);
    if ( (_QWORD *)*v8 != v8 )
    {
      KeReleaseSpinLock(v2, v6);
      return 0;
    }
    v9 = v1 + 88;
    v10 = RfsHashTableLookup(Smb2ClientHashTable, v1 + 88, 16);
    if ( !v10 )
    {
      Client = Smb2AllocateClient(a1);
      v10 = Client;
      if ( !Client )
      {
        KeReleaseSpinLock(v2, v7);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v13 = 13;
          goto LABEL_43;
        }
        return 3221225626LL;
      }
      v3 = RfsHashTableInsertEx(Smb2ClientHashTable, Client, v9, 16, 1);
      if ( v3 == -1073741270 )
      {
        KeReleaseSpinLock(v2, v7);
        Smb2CloseClient(v10);
        Smb2DereferenceClient(v10);
        if ( v4 >= 3 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v13 = 14;
            goto LABEL_43;
          }
          return 3221225626LL;
        }
        ++v4;
        goto LABEL_9;
      }
      if ( v3 < 0 )
      {
        KeReleaseSpinLock(v2, v7);
        Smb2CloseClient(v10);
        Smb2DereferenceClient(v10);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_a06c1082441b36f4a8793a7860ad7c22_Traceguids, a1);
        }
        return (unsigned int)v3;
      }
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v10 + 80));
    KeAcquireSpinLockAtDpcLevel(&Smb2ClientPendingListLock);
    if ( *(_DWORD *)(v10 + 12) == 220 && !*(_BYTE *)(v10 + 104) )
    {
      v15 = (_QWORD *)(v10 + 64);
      v16 = *(_QWORD *)(v10 + 64);
      if ( v16 == v10 + 64 )
        goto LABEL_32;
      if ( *(_QWORD **)(v16 + 8) != v15 )
        goto LABEL_38;
      v17 = *(_QWORD **)(v10 + 72);
      if ( (_QWORD *)*v17 != v15 )
        goto LABEL_38;
      *v17 = v16;
      *(_QWORD *)(v16 + 8) = v17;
      *(_QWORD *)(v10 + 72) = v10 + 64;
      *v15 = v15;
LABEL_32:
      KeReleaseSpinLockFromDpcLevel(&Smb2ClientPendingListLock);
      if ( *(_WORD *)(v19 + 44) != *(_WORD *)(v10 + 152) )
      {
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v10 + 80));
        KeReleaseSpinLock(v2, v7);
        Smb2DereferenceClient(v10);
        return 3221225561LL;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 24));
      v18 = *(_QWORD **)(v10 + 40);
      if ( *v18 != v10 + 32 )
LABEL_38:
        __fastfail(3u);
      *v8 = v10 + 32;
      *(_QWORD *)(a1 + 472) = v18;
      *v18 = v8;
      *(_QWORD *)(v10 + 40) = v8;
      *(_QWORD *)(v19 + 64) = *(_QWORD *)(v10 + 136);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v10 + 136) + 12LL));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v10 + 80));
      if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)a1, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        __int2c();
      *(_QWORD *)(v19 + 24) = v10;
      KeReleaseSpinLock(v2, v7);
      return (unsigned int)v3;
    }
    Interval.QuadPart = 0;
    KeReleaseSpinLockFromDpcLevel(&Smb2ClientPendingListLock);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v10 + 80));
    KeReleaseSpinLock(v2, v7);
    Smb2DereferenceClient(v10);
    if ( v4 >= 3 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v13 = 16;
LABEL_43:
        WPP_SF_q(v12->AttachedDevice, v13, &WPP_a06c1082441b36f4a8793a7860ad7c22_Traceguids, a1);
      }
      return 3221225626LL;
    }
    ++v4;
    Interval.QuadPart = -5000;
    KeDelayExecutionThread(0, 0, &Interval);
LABEL_9:
    v1 = v19;
  }
  KeReleaseSpinLock(v2, v6);
  return 3221225987LL;
}

```

## disassembly

```asm
0x140010dec  mov     [rsp+arg_10], rbx
0x140010df1  push    rbp
0x140010df2  push    rsi
0x140010df3  push    rdi
0x140010df4  push    r12
0x140010df6  push    r13
0x140010df8  push    r14
0x140010dfa  push    r15
0x140010dfc  sub     rsp, 30h
0x140010e00  mov     rbx, [rcx+1F0h]
0x140010e07  lea     rdi, [rcx+0B8h]
0x140010e0e  xor     r15d, r15d
0x140010e11  mov     [rsp+68h+arg_0], rbx
0x140010e16  xor     r14d, r14d
0x140010e19  mov     rsi, rcx
0x140010e1c  mov     rcx, rdi; SpinLock
0x140010e1f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010e26  nop     dword ptr [rax+rax+00h]
0x140010e2b  cmp     dword ptr [rsi+0Ch], 0DCh
0x140010e32  mov     bpl, al
0x140010e35  jnz     loc_1400111DE
0x140010e3b  lea     r13, [rsi+1D0h]
0x140010e42  cmp     [r13+0], r13
0x140010e46  jnz     loc_1400111C8
0x140010e4c  mov     rcx, cs:Smb2ClientHashTable
0x140010e53  lea     r12, [rbx+58h]
0x140010e57  mov     rdx, r12
0x140010e5a  mov     r8d, 10h
0x140010e60  call    RfsHashTableLookup
0x140010e65  mov     rbx, rax
0x140010e68  test    rax, rax
0x140010e6b  jnz     short loc_140010EEA
0x140010e6d  mov     rcx, rsi
0x140010e70  call    Smb2AllocateClient
0x140010e75  mov     rbx, rax
0x140010e78  test    rax, rax
0x140010e7b  jz      loc_140011034
0x140010e81  mov     rcx, cs:Smb2ClientHashTable
0x140010e88  mov     r9d, 10h
0x140010e8e  mov     r8, r12
0x140010e91  mov     [rsp+68h+var_48], 1
0x140010e96  mov     rdx, rax
0x140010e99  call    RfsHashTableInsertEx
0x140010e9e  mov     r15d, eax
0x140010ea1  cmp     eax, 0C000022Ah
0x140010ea6  jnz     short loc_140010EE1
0x140010ea8  mov     dl, bpl; NewIrql
0x140010eab  mov     rcx, rdi; SpinLock
0x140010eae  call    cs:__imp_KeReleaseSpinLock
0x140010eb5  nop     dword ptr [rax+rax+00h]
0x140010eba  mov     rcx, rbx
0x140010ebd  call    Smb2CloseClient
0x140010ec2  mov     rcx, rbx
0x140010ec5  call    Smb2DereferenceClient
0x140010eca  cmp     r14d, 3
0x140010ece  jnb     loc_140010F98
0x140010ed4  inc     r14d
0x140010ed7  mov     rbx, [rsp+68h+arg_0]
0x140010edc  jmp     loc_140010E1C
0x140010ee1  test    r15d, r15d
0x140010ee4  js      loc_140010FD0
0x140010eea  lea     r12, [rbx+50h]
0x140010eee  mov     rcx, r12; SpinLock
0x140010ef1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140010ef8  nop     dword ptr [rax+rax+00h]
0x140010efd  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x140010f04  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140010f0b  nop     dword ptr [rax+rax+00h]
0x140010f10  cmp     dword ptr [rbx+0Ch], 0DCh
0x140010f17  jnz     short loc_140010F23
0x140010f19  cmp     byte ptr [rbx+68h], 0
0x140010f1d  jz      loc_14001107E
0x140010f23  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x140010f2a  mov     qword ptr [rsp+68h+Interval], 0
0x140010f33  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140010f3a  nop     dword ptr [rax+rax+00h]
0x140010f3f  mov     rcx, r12; SpinLock
0x140010f42  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140010f49  nop     dword ptr [rax+rax+00h]
0x140010f4e  mov     dl, bpl; NewIrql
0x140010f51  mov     rcx, rdi; SpinLock
0x140010f54  call    cs:__imp_KeReleaseSpinLock
0x140010f5b  nop     dword ptr [rax+rax+00h]
0x140010f60  mov     rcx, rbx
0x140010f63  call    Smb2DereferenceClient
0x140010f68  cmp     r14d, 3
0x140010f6c  jnb     loc_140011187
0x140010f72  inc     r14d
0x140010f75  mov     qword ptr [rsp+68h+Interval], 0FFFFFFFFFFFFEC78h
0x140010f7e  lea     r8, [rsp+68h+Interval]; Interval
0x140010f83  xor     edx, edx; Alertable
0x140010f85  xor     ecx, ecx; WaitMode
0x140010f87  call    cs:__imp_KeDelayExecutionThread
0x140010f8e  nop     dword ptr [rax+rax+00h]
0x140010f93  jmp     loc_140010ED7
0x140010f98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010f9f  lea     rax, WPP_GLOBAL_Control
0x140010fa6  cmp     rcx, rax
0x140010fa9  jz      loc_1400111C1
0x140010faf  test    dword ptr [rcx+2Ch], 20000h
0x140010fb6  jz      loc_1400111C1
0x140010fbc  cmp     byte ptr [rcx+29h], 1
0x140010fc0  jb      loc_1400111C1
0x140010fc6  mov     edx, 0Eh
0x140010fcb  jmp     loc_1400111AE
0x140010fd0  mov     dl, bpl; NewIrql
0x140010fd3  mov     rcx, rdi; SpinLock
0x140010fd6  call    cs:__imp_KeReleaseSpinLock
0x140010fdd  nop     dword ptr [rax+rax+00h]
0x140010fe2  mov     rcx, rbx
0x140010fe5  call    Smb2CloseClient
0x140010fea  mov     rcx, rbx
0x140010fed  call    Smb2DereferenceClient
0x140010ff2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010ff9  lea     rax, WPP_GLOBAL_Control
0x140011000  cmp     rcx, rax
0x140011003  jz      short loc_14001102C
0x140011005  test    dword ptr [rcx+2Ch], 20000h
0x14001100c  jz      short loc_14001102C
0x14001100e  cmp     byte ptr [rcx+29h], 1
0x140011012  jb      short loc_14001102C
0x140011014  mov     rcx, [rcx+18h]
0x140011018  lea     r8, WPP_a06c1082441b36f4a8793a7860ad7c22_Traceguids
0x14001101f  mov     edx, 0Fh
0x140011024  mov     r9, rsi
0x140011027  call    WPP_SF_q
0x14001102c  mov     eax, r15d
0x14001102f  jmp     loc_1400111F5
0x140011034  mov     dl, bpl; NewIrql
0x140011037  mov     rcx, rdi; SpinLock
0x14001103a  call    cs:__imp_KeReleaseSpinLock
0x140011041  nop     dword ptr [rax+rax+00h]
0x140011046  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001104d  lea     rax, WPP_GLOBAL_Control
0x140011054  cmp     rcx, rax
0x140011057  jz      loc_1400111C1
0x14001105d  test    dword ptr [rcx+2Ch], 20000h
0x140011064  jz      loc_1400111C1
0x14001106a  cmp     byte ptr [rcx+29h], 1
0x14001106e  jb      loc_1400111C1
0x140011074  mov     edx, 0Dh
0x140011079  jmp     loc_1400111AE
0x14001107e  lea     rax, [rbx+40h]
0x140011082  mov     rdx, [rax]
0x140011085  cmp     rdx, rax
0x140011088  jz      short loc_1400110AF
0x14001108a  cmp     [rdx+8], rax
0x14001108e  jnz     loc_140011180
0x140011094  mov     r8, [rax+8]
0x140011098  cmp     [r8], rax
0x14001109b  jnz     loc_140011180
0x1400110a1  mov     [r8], rdx
0x1400110a4  mov     [rdx+8], r8
0x1400110a8  mov     [rax+8], rax
0x1400110ac  mov     [rax], rax
0x1400110af  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x1400110b6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400110bd  nop     dword ptr [rax+rax+00h]
0x1400110c2  mov     r14, [rsp+68h+arg_0]
0x1400110c7  movzx   eax, word ptr [rbx+98h]
0x1400110ce  cmp     [r14+2Ch], ax
0x1400110d3  jz      short loc_140011108
0x1400110d5  mov     rcx, r12; SpinLock
0x1400110d8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400110df  nop     dword ptr [rax+rax+00h]
0x1400110e4  mov     dl, bpl; NewIrql
0x1400110e7  mov     rcx, rdi; SpinLock
0x1400110ea  call    cs:__imp_KeReleaseSpinLock
0x1400110f1  nop     dword ptr [rax+rax+00h]
0x1400110f6  mov     rcx, rbx
0x1400110f9  call    Smb2DereferenceClient
0x1400110fe  mov     eax, 0C0000059h
0x140011103  jmp     loc_1400111F5
0x140011108  lock inc dword ptr [rbx+18h]
0x14001110c  lea     rax, [rbx+20h]
0x140011110  mov     rcx, [rax+8]
0x140011114  cmp     [rcx], rax
0x140011117  jnz     short loc_140011180
0x140011119  mov     [r13+0], rax
0x14001111d  mov     [r13+8], rcx
0x140011121  mov     [rcx], r13
0x140011124  mov     [rax+8], r13
0x140011128  mov     rax, [rbx+88h]
0x14001112f  mov     [r14+40h], rax
0x140011133  mov     rax, [rbx+88h]
0x14001113a  lock inc dword ptr [rax+0Ch]
0x14001113e  mov     rcx, r12; SpinLock
0x140011141  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140011148  nop     dword ptr [rax+rax+00h]
0x14001114d  mov     eax, 1
0x140011152  lock xadd [rsi], rax
0x140011157  add     rax, 2
0x14001115b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140011161  jnz     short loc_140011165
0x140011163  int     2Ch; Windows NT - assertion failure
0x140011165  mov     dl, bpl; NewIrql
0x140011168  mov     [r14+18h], rbx
0x14001116c  mov     rcx, rdi; SpinLock
0x14001116f  call    cs:__imp_KeReleaseSpinLock
0x140011176  nop     dword ptr [rax+rax+00h]
0x14001117b  jmp     loc_14001102C
0x140011180  mov     ecx, 3
0x140011185  int     29h; Win8: RtlFailFast(ecx)
0x140011187  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001118e  lea     rax, WPP_GLOBAL_Control
0x140011195  cmp     rcx, rax
0x140011198  jz      short loc_1400111C1
0x14001119a  test    dword ptr [rcx+2Ch], 20000h
0x1400111a1  jz      short loc_1400111C1
0x1400111a3  cmp     byte ptr [rcx+29h], 1
0x1400111a7  jb      short loc_1400111C1
0x1400111a9  mov     edx, 10h
0x1400111ae  mov     rcx, [rcx+18h]
0x1400111b2  lea     r8, WPP_a06c1082441b36f4a8793a7860ad7c22_Traceguids
0x1400111b9  mov     r9, rsi
0x1400111bc  call    WPP_SF_q
0x1400111c1  mov     eax, 0C000009Ah
0x1400111c6  jmp     short loc_1400111F5
0x1400111c8  mov     dl, bpl; NewIrql
0x1400111cb  mov     rcx, rdi; SpinLock
0x1400111ce  call    cs:__imp_KeReleaseSpinLock
0x1400111d5  nop     dword ptr [rax+rax+00h]
0x1400111da  xor     eax, eax
0x1400111dc  jmp     short loc_1400111F5
0x1400111de  mov     dl, bpl; NewIrql
0x1400111e1  mov     rcx, rdi; SpinLock
0x1400111e4  call    cs:__imp_KeReleaseSpinLock
0x1400111eb  nop     dword ptr [rax+rax+00h]
0x1400111f0  mov     eax, 0C0000203h
0x1400111f5  mov     rbx, [rsp+68h+arg_10]
0x1400111fd  add     rsp, 30h
0x140011201  pop     r15
0x140011203  pop     r14
0x140011205  pop     r13
0x140011207  pop     r12
0x140011209  pop     rdi
0x14001120a  pop     rsi
0x14001120b  pop     rbp
0x14001120c  retn
```

# BCryptSecretAgreement

- ea: `0x180009570`
- end: `0x180009735`
- name: `BCryptSecretAgreement`
- size: `453`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hPrivKey, BCRYPT_KEY_HANDLE hPubKey, BCRYPT_SECRET_HANDLE *phAgreedSecret, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x180009570`
- `0x180009740`
- `0x180015968`
- `0x18001c010`

## string_xrefs

- `0x180009662`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800096a8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800096eb`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180009713`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptSecretAgreement(
        BCRYPT_KEY_HANDLE hPrivKey,
        BCRYPT_KEY_HANDLE hPubKey,
        BCRYPT_SECRET_HANDLE *phAgreedSecret,
        ULONG dwFlags)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r10
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(_QWORD, _QWORD, __int64, _QWORD); // r12
  __int64 v16; // rax
  _DWORD *v17; // rdi
  int v18; // eax
  NTSTATUS v19; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qqqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      hPubKey,
      phAgreedSecret,
      hPrivKey,
      hPubKey,
      phAgreedSecret,
      dwFlags);
  v8 = ValidateBaseKeyHandle(hPrivKey);
  v9 = ValidateBaseKeyHandle(hPubKey);
  v13 = v9;
  if ( v8 && v9 )
  {
    if ( phAgreedSecret )
    {
      v14 = *(_QWORD *)(v8 + 8);
      if ( *(_DWORD *)(v14 + 36) == 4 )
      {
        v15 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(v14 + 88);
        v16 = SafeAllocaAllocateFromHeap(24);
        v17 = (_DWORD *)v16;
        if ( v16 )
        {
          v18 = v15(*(_QWORD *)(v8 + 16), *(_QWORD *)(v13 + 16), v16 + 16, dwFlags);
          v19 = v18;
          if ( v18 < 0 )
          {
            DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
            MSCryptFree(v17);
          }
          else
          {
            *v17 = 24;
            v17[1] = 1431655764;
            *((_QWORD *)v17 + 1) = v14;
            _InterlockedIncrement((volatile signed __int32 *)(v14 + 16));
            *phAgreedSecret = v17;
          }
        }
        else
        {
          return -1073741801;
        }
      }
      else
      {
        v19 = -1073741637;
        if ( (_UNKNOWN **)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(v12 + 16),
            v10,
            v11,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            171);
      }
    }
    else
    {
      v19 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    }
  }
  else
  {
    v19 = -1073741816;
    if ( (_UNKNOWN **)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v12 + 16),
        v10,
        v11,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        150);
  }
  return v19;
}

```

## disassembly

```asm
0x180009570  push    rbx
0x180009572  push    rbp
0x180009573  push    rsi
0x180009574  push    rdi
0x180009575  push    r12
0x180009577  push    r14
0x180009579  push    r15
0x18000957b  sub     rsp, 40h
0x18000957f  mov     r15d, r9d
0x180009582  mov     r14, r8
0x180009585  mov     rdi, rdx
0x180009588  mov     rbx, rcx
0x18000958b  mov     r10, cs:WPP_GLOBAL_Control
0x180009592  lea     r12, WPP_GLOBAL_Control
0x180009599  cmp     r10, r12
0x18000959c  jz      short loc_1800095A9
0x18000959e  test    byte ptr [r10+1Ch], 4
0x1800095a3  jnz     loc_1800096BE
0x1800095a9  mov     rcx, rbx
0x1800095ac  call    ValidateBaseKeyHandle
0x1800095b1  mov     rcx, rdi
0x1800095b4  mov     rbx, rax
0x1800095b7  call    ValidateBaseKeyHandle
0x1800095bc  mov     rbp, rax
0x1800095bf  test    rbx, rbx
0x1800095c2  jz      loc_18000968F
0x1800095c8  test    rax, rax
0x1800095cb  jz      loc_18000968F
0x1800095d1  test    r14, r14
0x1800095d4  jz      loc_1800096E5
0x1800095da  mov     rsi, [rbx+8]
0x1800095de  cmp     dword ptr [rsi+24h], 4
0x1800095e2  jnz     short loc_180009649
0x1800095e4  mov     r12, [rsi+58h]
0x1800095e8  mov     ecx, 18h
0x1800095ed  call    SafeAllocaAllocateFromHeap
0x1800095f2  mov     rdi, rax
0x1800095f5  test    rax, rax
0x1800095f8  jz      loc_180009688
0x1800095fe  mov     rdx, [rbp+10h]
0x180009602  lea     r8, [rax+10h]
0x180009606  mov     rcx, [rbx+10h]
0x18000960a  mov     rax, r12
0x18000960d  mov     r9d, r15d
0x180009610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009615  mov     ebx, eax
0x180009617  test    eax, eax
0x180009619  js      loc_18000970D
0x18000961f  mov     dword ptr [rdi], 18h
0x180009625  mov     dword ptr [rdi+4], 55555554h
0x18000962c  mov     [rdi+8], rsi
0x180009630  lock inc dword ptr [rsi+10h]
0x180009634  mov     [r14], rdi
0x180009637  mov     eax, ebx
0x180009639  add     rsp, 40h
0x18000963d  pop     r15
0x18000963f  pop     r14
0x180009641  pop     r12
0x180009643  pop     rdi
0x180009644  pop     rsi
0x180009645  pop     rbp
0x180009646  pop     rbx
0x180009647  retn
0x180009649  mov     ebx, 0C00000BBh
0x18000964e  cmp     r10, r12
0x180009651  jz      short loc_180009637
0x180009653  test    byte ptr [r10+1Ch], 1
0x180009658  jz      short loc_180009637
0x18000965a  mov     [rsp+78h+var_48], 14ABh
0x180009662  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009669  mov     [rsp+78h+var_50], rax
0x18000966e  mov     dword ptr [rsp+78h+var_58], 0C00000BBh
0x180009676  mov     rcx, [r10+10h]
0x18000967a  lea     r9, aStatus; "Status"
0x180009681  call    WPP_SF_sDsd
0x180009686  jmp     short loc_180009637
0x180009688  mov     ebx, 0C0000017h
0x18000968d  jmp     short loc_180009637
0x18000968f  mov     ebx, 0C0000008h
0x180009694  cmp     r10, r12
0x180009697  jz      short loc_180009637
0x180009699  test    byte ptr [r10+1Ch], 1
0x18000969e  jz      short loc_180009637
0x1800096a0  mov     [rsp+78h+var_48], 1496h
0x1800096a8  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800096af  mov     [rsp+78h+var_50], rax
0x1800096b4  mov     dword ptr [rsp+78h+var_58], 0C0000008h
0x1800096bc  jmp     short loc_180009676
0x1800096be  mov     rcx, [r10+10h]
0x1800096c2  mov     r9, rbx
0x1800096c5  mov     [rsp+78h+var_48], r15d
0x1800096ca  mov     [rsp+78h+var_50], r14
0x1800096cf  mov     [rsp+78h+var_58], rdi
0x1800096d4  call    WPP_SF_qqqD
0x1800096d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800096e0  jmp     loc_1800095A9
0x1800096e5  mov     r9d, 149Dh
0x1800096eb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800096f2  lea     rdx, aStatus; "Status"
0x1800096f9  mov     ecx, 0C000000Dh
0x1800096fe  mov     ebx, 0C000000Dh
0x180009703  call    DebugTraceError
0x180009708  jmp     loc_180009637
0x18000970d  mov     r9d, 14BDh
0x180009713  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000971a  lea     rdx, aStatus; "Status"
0x180009721  mov     ecx, eax
0x180009723  call    DebugTraceError
0x180009728  mov     rcx, rdi
0x18000972b  call    MSCryptFree
0x180009730  jmp     loc_180009637
```

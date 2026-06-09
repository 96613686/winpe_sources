# BfsTryCommitFveChanges

- ea: `0x14001062c`
- end: `0x140010721`
- name: `BfsTryCommitFveChanges`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010bac`

## callees

- `0x14000e628`
- `0x14001062c`
- `0x140027010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400106e5`
- `KERNEL32!Sleep` at `0x1400106e5`

## string_xrefs

- `0x140010702`: `BfsTryCommitFveChanges failed.retry = %dHRESULT = [%x]`
- `0x1400106cc`: `FveCommitChanges failed (FveCommitChangesEx Unavailable).retry = %dHRESULT = [%x]`
- `0x1400106a0`: `FveCommitChanges failed.retry = %dHRESULT = [%x]`
- `0x14001066f`: `FveCommitChangesEx failed.retry = %dHRESULT = [%x]`

## pseudocode

```c
__int64 __fastcall BfsTryCommitFveChanges(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 (__fastcall *v5)(__int64, __int64); // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax

  if ( a2 && a1 != -1 )
  {
    v4 = 0;
    while ( 1 )
    {
      v5 = *(__int64 (__fastcall **)(__int64, __int64))(a2 + 32);
      if ( v5 )
      {
        v6 = v5(a1, 2);
        v7 = v6;
        if ( v6 < 0 )
          BfspLogMessage(3, L"FveCommitChangesEx failed.retry = %dHRESULT = [%x]", v4, (unsigned int)v6);
        if ( v7 == -2147024809 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64))(a2 + 24))(a1);
          v7 = v8;
          if ( v8 >= 0 )
            return v7;
          BfspLogMessage(3, L"FveCommitChanges failed.retry = %dHRESULT = [%x]", v4, (unsigned int)v8);
        }
        if ( (v7 & 0x80000000) == 0 )
          return v7;
      }
      else
      {
        v9 = (*(__int64 (__fastcall **)(__int64))(a2 + 24))(a1);
        v7 = v9;
        if ( v9 >= 0 )
          return v7;
        BfspLogMessage(
          3,
          L"FveCommitChanges failed (FveCommitChangesEx Unavailable).retry = %dHRESULT = [%x]",
          v4,
          (unsigned int)v9);
      }
      Sleep(0x1F4u);
      if ( ++v4 >= 3 )
        goto LABEL_17;
    }
  }
  v4 = 0;
  v7 = -2147024809;
LABEL_17:
  BfspLogMessage(4, L"BfsTryCommitFveChanges failed.retry = %dHRESULT = [%x]", v4, v7);
  return v7;
}

```

## disassembly

```asm
0x14001062c  push    rbx
0x14001062e  push    rbp
0x14001062f  push    rsi
0x140010630  push    rdi
0x140010631  sub     rsp, 28h
0x140010635  mov     rsi, rdx
0x140010638  mov     rbp, rcx
0x14001063b  test    rdx, rdx
0x14001063e  jz      loc_1400106F8
0x140010644  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140010648  jz      loc_1400106F8
0x14001064e  xor     edi, edi
0x140010650  mov     rax, [rsi+20h]
0x140010654  mov     rcx, rbp
0x140010657  test    rax, rax
0x14001065a  jz      short loc_1400106BA
0x14001065c  mov     edx, 2
0x140010661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010666  mov     ebx, eax
0x140010668  test    eax, eax
0x14001066a  jns     short loc_140010683
0x14001066c  mov     r9d, eax
0x14001066f  lea     rdx, aFvecommitchang_1; "FveCommitChangesEx failed.retry = %dHRE"...
0x140010676  mov     r8d, edi
0x140010679  mov     ecx, 3
0x14001067e  call    BfspLogMessage
0x140010683  cmp     ebx, 80070057h
0x140010689  jnz     short loc_1400106B4
0x14001068b  mov     rax, [rsi+18h]
0x14001068f  mov     rcx, rbp
0x140010692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010697  mov     ebx, eax
0x140010699  test    eax, eax
0x14001069b  jns     short loc_140010716
0x14001069d  mov     r9d, eax
0x1400106a0  lea     rdx, aFvecommitchang; "FveCommitChanges failed.retry = %dHRESU"...
0x1400106a7  mov     r8d, edi
0x1400106aa  mov     ecx, 3
0x1400106af  call    BfspLogMessage
0x1400106b4  test    ebx, ebx
0x1400106b6  jns     short loc_140010716
0x1400106b8  jmp     short loc_1400106E0
0x1400106ba  mov     rax, [rsi+18h]
0x1400106be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106c3  mov     ebx, eax
0x1400106c5  test    eax, eax
0x1400106c7  jns     short loc_140010716
0x1400106c9  mov     r9d, eax
0x1400106cc  lea     rdx, aFvecommitchang_0; "FveCommitChanges failed (FveCommitChang"...
0x1400106d3  mov     r8d, edi
0x1400106d6  mov     ecx, 3
0x1400106db  call    BfspLogMessage
0x1400106e0  mov     ecx, 1F4h; dwMilliseconds
0x1400106e5  call    cs:__imp_Sleep
0x1400106eb  inc     edi
0x1400106ed  cmp     edi, 3
0x1400106f0  jb      loc_140010650
0x1400106f6  jmp     short loc_1400106FF
0x1400106f8  xor     edi, edi
0x1400106fa  mov     ebx, 80070057h
0x1400106ff  mov     r9d, ebx
0x140010702  lea     rdx, aBfstrycommitfv_0; "BfsTryCommitFveChanges failed.retry = %"...
0x140010709  mov     r8d, edi
0x14001070c  mov     ecx, 4
0x140010711  call    BfspLogMessage
0x140010716  mov     eax, ebx
0x140010718  add     rsp, 28h
0x14001071c  pop     rdi
0x14001071d  pop     rsi
0x14001071e  pop     rbp
0x14001071f  pop     rbx
0x140010720  retn
```

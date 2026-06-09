# BfsTryCommitFveChanges

- ea: `0x180048420`
- end: `0x180048515`
- name: `BfsTryCommitFveChanges`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180048078`
- `0x1800489c4`

## callees

- `0x180048420`
- `0x18004cdd4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800484d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800484d9`

## string_xrefs

- `0x180048463`: `FveCommitChangesEx failed.retry = %dHRESULT = [%x]`
- `0x1800484c0`: `FveCommitChanges failed (FveCommitChangesEx Unavailable).retry = %dHRESULT = [%x]`
- `0x180048494`: `FveCommitChanges failed.retry = %dHRESULT = [%x]`
- `0x1800484f6`: `BfsTryCommitFveChanges failed.retry = %dHRESULT = [%x]`

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
0x180048420  push    rbx
0x180048422  push    rbp
0x180048423  push    rsi
0x180048424  push    rdi
0x180048425  sub     rsp, 28h
0x180048429  mov     rsi, rdx
0x18004842c  mov     rbp, rcx
0x18004842f  test    rdx, rdx
0x180048432  jz      loc_1800484EC
0x180048438  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004843c  jz      loc_1800484EC
0x180048442  xor     edi, edi
0x180048444  mov     rax, [rsi+20h]
0x180048448  mov     rcx, rbp
0x18004844b  test    rax, rax
0x18004844e  jz      short loc_1800484AE
0x180048450  mov     edx, 2
0x180048455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004845a  mov     ebx, eax
0x18004845c  test    eax, eax
0x18004845e  jns     short loc_180048477
0x180048460  mov     r9d, eax
0x180048463  lea     rdx, aFvecommitchang_1; "FveCommitChangesEx failed.retry = %dHRE"...
0x18004846a  mov     r8d, edi
0x18004846d  mov     ecx, 3
0x180048472  call    BfspLogMessage
0x180048477  cmp     ebx, 80070057h
0x18004847d  jnz     short loc_1800484A8
0x18004847f  mov     rax, [rsi+18h]
0x180048483  mov     rcx, rbp
0x180048486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004848b  mov     ebx, eax
0x18004848d  test    eax, eax
0x18004848f  jns     short loc_18004850A
0x180048491  mov     r9d, eax
0x180048494  lea     rdx, aFvecommitchang; "FveCommitChanges failed.retry = %dHRESU"...
0x18004849b  mov     r8d, edi
0x18004849e  mov     ecx, 3
0x1800484a3  call    BfspLogMessage
0x1800484a8  test    ebx, ebx
0x1800484aa  jns     short loc_18004850A
0x1800484ac  jmp     short loc_1800484D4
0x1800484ae  mov     rax, [rsi+18h]
0x1800484b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484b7  mov     ebx, eax
0x1800484b9  test    eax, eax
0x1800484bb  jns     short loc_18004850A
0x1800484bd  mov     r9d, eax
0x1800484c0  lea     rdx, aFvecommitchang_0; "FveCommitChanges failed (FveCommitChang"...
0x1800484c7  mov     r8d, edi
0x1800484ca  mov     ecx, 3
0x1800484cf  call    BfspLogMessage
0x1800484d4  mov     ecx, 1F4h; dwMilliseconds
0x1800484d9  call    cs:__imp_Sleep
0x1800484df  inc     edi
0x1800484e1  cmp     edi, 3
0x1800484e4  jb      loc_180048444
0x1800484ea  jmp     short loc_1800484F3
0x1800484ec  xor     edi, edi
0x1800484ee  mov     ebx, 80070057h
0x1800484f3  mov     r9d, ebx
0x1800484f6  lea     rdx, aBfstrycommitfv_2; "BfsTryCommitFveChanges failed.retry = %"...
0x1800484fd  mov     r8d, edi
0x180048500  mov     ecx, 4
0x180048505  call    BfspLogMessage
0x18004850a  mov     eax, ebx
0x18004850c  add     rsp, 28h
0x180048510  pop     rdi
0x180048511  pop     rsi
0x180048512  pop     rbp
0x180048513  pop     rbx
0x180048514  retn
```

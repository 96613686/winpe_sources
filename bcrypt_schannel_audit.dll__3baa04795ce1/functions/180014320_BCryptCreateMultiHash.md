# BCryptCreateMultiHash

- ea: `0x180014320`
- end: `0x180014509`
- name: `BCryptCreateMultiHash`
- size: `489`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180006bd0`
- `0x180009430`
- `0x180013fd4`
- `0x180014320`
- `0x18001c010`

## string_xrefs

- `0x180014368`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800144d8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptCreateMultiHash(__int64 a1, _QWORD *a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rdi
  __int64 v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  unsigned int v13; // r8d
  int v14; // eax
  __int64 v15; // rcx
  _DWORD *v16; // r14
  __int64 (__fastcall *v17)(_QWORD, _DWORD *, _QWORD); // rax
  int v18; // eax
  unsigned int v20; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+58h] [rbp-40h] BYREF

  v5 = 0;
  v21[0] = 0;
  v20 = 0;
  v10 = ValidateBaseAlgHandle(a1);
  if ( !v10 )
  {
    v11 = -1073741816;
    v12 = 3221225480LL;
LABEL_3:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return v11;
  }
  if ( !a3 )
  {
    v11 = -1073741811;
    v12 = 3221225485LL;
    goto LABEL_3;
  }
  v13 = a5;
  if ( !a4 )
  {
    if ( !a5 )
    {
      v14 = AllocateMultiObjectBuffer(a1, a3, v21, &v20);
      v5 = v21[0];
      v11 = v14;
      if ( v14 < 0 )
      {
        v15 = (unsigned int)v14;
        goto LABEL_22;
      }
      v13 = v20;
      a4 = v21[0];
    }
    if ( !a4 )
      goto LABEL_21;
  }
  if ( a2 )
  {
    if ( v13 >= 0x46 )
    {
      v16 = (_DWORD *)((a4 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
      if ( *(_DWORD *)(v10 + 36) == 2 && *(_WORD *)(v10 + 48) >= 2u )
      {
        v17 = *(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD))(v10 + 128);
        *v16 = 40;
        *(_DWORD *)(((a4 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 4) = 1431655763;
        *(_QWORD *)(((a4 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 8) = v10;
        *(_QWORD *)(((a4 + 15) & 0xFFFFFFFFFFFFFFF0uLL) + 0x20) = v5;
        v18 = v17(*(_QWORD *)(v10 + 24), v16 + 4, a3);
        v11 = v18;
        if ( v18 >= 0 )
        {
          *a2 = v16;
          v11 = 0;
LABEL_25:
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
          return v11;
        }
        v15 = (unsigned int)v18;
      }
      else
      {
        v11 = -1073741637;
        v15 = 3221225659LL;
      }
    }
    else
    {
      v11 = -1073741789;
      v15 = 3221225507LL;
    }
  }
  else
  {
LABEL_21:
    v11 = -1073741811;
    v15 = 3221225485LL;
  }
LABEL_22:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
  if ( v5 )
    MSCryptFree(v5);
  if ( (v11 & 0x80000000) == 0 )
    goto LABEL_25;
  return v11;
}

```

## disassembly

```asm
0x180014320  push    rbx
0x180014322  push    rbp
0x180014323  push    rsi
0x180014324  push    rdi
0x180014325  push    r14
0x180014327  push    r15
0x180014329  sub     rsp, 68h
0x18001432d  xor     edi, edi
0x18001432f  mov     rbx, r9
0x180014332  mov     [rsp+98h+var_40], rdi
0x180014337  mov     ebp, r8d
0x18001433a  mov     [rsp+98h+var_48], edi
0x18001433e  mov     r15, rdx
0x180014341  mov     r14, rcx
0x180014344  call    ValidateBaseAlgHandle
0x180014349  mov     rsi, rax
0x18001434c  test    rax, rax
0x18001434f  jnz     short loc_180014379
0x180014351  mov     ebx, 0C0000008h
0x180014356  mov     r9d, 1847h
0x18001435c  mov     ecx, 0C0000008h
0x180014361  lea     rdx, aStatus; "Status"
0x180014368  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001436f  call    DebugTraceError
0x180014374  jmp     loc_1800144F9
0x180014379  cmp     ebp, 1
0x18001437c  jnb     short loc_180014390
0x18001437e  mov     ebx, 0C000000Dh
0x180014383  mov     r9d, 184Eh
0x180014389  mov     ecx, 0C000000Dh
0x18001438e  jmp     short loc_180014361
0x180014390  mov     r8d, [rsp+98h+arg_20]
0x180014398  test    rbx, rbx
0x18001439b  jnz     short loc_1800143DF
0x18001439d  test    r8d, r8d
0x1800143a0  jnz     short loc_1800143D6
0x1800143a2  lea     r9, [rsp+98h+var_48]
0x1800143a7  mov     edx, ebp
0x1800143a9  lea     r8, [rsp+98h+var_40]
0x1800143ae  mov     rcx, r14
0x1800143b1  call    AllocateMultiObjectBuffer
0x1800143b6  mov     rdi, [rsp+98h+var_40]
0x1800143bb  mov     ebx, eax
0x1800143bd  test    eax, eax
0x1800143bf  jns     short loc_1800143CE
0x1800143c1  mov     ecx, eax
0x1800143c3  mov     r9d, 185Ah
0x1800143c9  jmp     loc_1800144D1
0x1800143ce  mov     r8d, [rsp+98h+var_48]
0x1800143d3  mov     rbx, rdi
0x1800143d6  test    rbx, rbx
0x1800143d9  jz      loc_1800144C1
0x1800143df  test    r15, r15
0x1800143e2  jz      loc_1800144C1
0x1800143e8  cmp     r8d, 46h ; 'F'
0x1800143ec  jnb     short loc_180014403
0x1800143ee  mov     ebx, 0C0000023h
0x1800143f3  mov     ecx, 0C0000023h
0x1800143f8  mov     r9d, 1871h
0x1800143fe  jmp     loc_1800144D1
0x180014403  lea     r14, [rbx+0Fh]
0x180014407  mov     eax, 2
0x18001440c  and     r14, 0FFFFFFFFFFFFFFF0h
0x180014410  cmp     [rsi+24h], eax
0x180014413  jnz     loc_1800144AF
0x180014419  cmp     [rsi+30h], ax
0x18001441d  jb      loc_1800144AF
0x180014423  mov     rax, [rsi+80h]
0x18001442a  mov     edx, r14d
0x18001442d  sub     edx, ebx
0x18001442f  mov     dword ptr [r14], 28h ; '('
0x180014436  mov     dword ptr [r14+4], 55555553h
0x18001443e  mov     [r14+8], rsi
0x180014442  mov     [r14+20h], rdi
0x180014446  lea     rcx, [rdx+28h]
0x18001444a  add     rcx, rbx
0x18001444d  lea     r9, [rcx+0Fh]
0x180014451  and     r9, 0FFFFFFFFFFFFFFF0h
0x180014455  sub     ecx, r9d
0x180014458  sub     ecx, edx
0x18001445a  lea     rdx, [r14+10h]
0x18001445e  add     ecx, 0FFFFFFD8h
0x180014461  add     r8d, ecx
0x180014464  mov     ecx, [rsp+98h+arg_38]
0x18001446b  mov     [rsp+98h+var_60], ecx
0x18001446f  mov     ecx, [rsp+98h+arg_30]
0x180014476  mov     [rsp+98h+var_68], ecx
0x18001447a  mov     rcx, [rsp+98h+arg_28]
0x180014482  mov     [rsp+98h+var_70], rcx
0x180014487  mov     rcx, [rsi+18h]
0x18001448b  mov     [rsp+98h+var_78], r8d
0x180014490  mov     r8d, ebp
0x180014493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014498  mov     ebx, eax
0x18001449a  test    eax, eax
0x18001449c  jns     short loc_1800144A8
0x18001449e  mov     ecx, eax
0x1800144a0  mov     r9d, 189Ch
0x1800144a6  jmp     short loc_1800144D1
0x1800144a8  mov     [r15], r14
0x1800144ab  xor     ebx, ebx
0x1800144ad  jmp     short loc_1800144F5
0x1800144af  mov     ebx, 0C00000BBh
0x1800144b4  mov     ecx, 0C00000BBh
0x1800144b9  mov     r9d, 187Fh
0x1800144bf  jmp     short loc_1800144D1
0x1800144c1  mov     ebx, 0C000000Dh
0x1800144c6  mov     ecx, 0C000000Dh
0x1800144cb  mov     r9d, 186Ah
0x1800144d1  lea     rdx, aStatus; "Status"
0x1800144d8  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800144df  call    DebugTraceError
0x1800144e4  test    rdi, rdi
0x1800144e7  jz      short loc_1800144F1
0x1800144e9  mov     rcx, rdi
0x1800144ec  call    MSCryptFree
0x1800144f1  test    ebx, ebx
0x1800144f3  js      short loc_1800144F9
0x1800144f5  lock inc dword ptr [rsi+10h]
0x1800144f9  mov     eax, ebx
0x1800144fb  add     rsp, 68h
0x1800144ff  pop     r15
0x180014501  pop     r14
0x180014503  pop     rdi
0x180014504  pop     rsi
0x180014505  pop     rbp
0x180014506  pop     rbx
0x180014507  retn
```

# CRuleWriter::RemovePathAndHandleChecksum(RULE_PATH_INFO const *)

- ea: `0x18000f2d0`
- end: `0x18000f3e5`
- name: `?RemovePathAndHandleChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000f280`
- `0x18001cf60`
- `0x18001d120`

## callees

- `0x18000f2d0`
- `0x180011704`
- `0x180011838`
- `0x18001cee4`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall CRuleWriter::RemovePathAndHandleChecksum(CRuleWriter *this, const struct RULE_PATH_INFO *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  int v6; // ebx
  BOOL v7; // eax
  unsigned int v8; // ebx
  int v10; // r14d
  int v11; // eax
  int v12; // edi
  int v13; // eax

  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         *((_QWORD *)a2 + 3),
         0);
  v5 = *((_QWORD *)a2 + 4);
  v6 = v4;
  v7 = v5
    && (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         v5,
         0) != -2003292352;
  if ( v6 != -2003292352 || (v8 = 0, v7) )
  {
    v10 = CRuleWriter::NeedToProcessChecksumForPath(this, a2);
    if ( !v10 || (v8 = CRuleWriter::WriteOtherKeysAffectedByChecksum(this, a2), (v8 & 0x80000000) == 0) )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 64LL))(
              *((_QWORD *)this + 5),
              *((_QWORD *)a2 + 3));
      v8 = v11;
      if ( v11 == -2003292352 )
      {
        v12 = 0;
        v8 = 0;
      }
      else
      {
        if ( v11 < 0 )
          return v8;
        v12 = 1;
      }
      if ( *((_QWORD *)a2 + 4) )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 64LL))(*((_QWORD *)this + 5));
        v8 = v13;
        if ( v13 == -2003292352 )
        {
          v8 = 0;
        }
        else
        {
          if ( v13 < 0 )
            return v8;
          v12 = 1;
        }
      }
      if ( v10 && v12 )
        CRuleWriter::UpdateChecksum(this, a2);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000f2d0  push    rbx
0x18000f2d2  push    rbp
0x18000f2d3  push    rsi
0x18000f2d4  push    rdi
0x18000f2d5  push    r12
0x18000f2d7  push    r14
0x18000f2d9  sub     rsp, 28h
0x18000f2dd  mov     rbp, rcx
0x18000f2e0  mov     rsi, rdx
0x18000f2e3  mov     rcx, [rcx+28h]
0x18000f2e7  xor     r8d, r8d
0x18000f2ea  mov     rdx, [rdx+18h]
0x18000f2ee  mov     rax, [rcx]
0x18000f2f1  mov     rax, [rax+28h]
0x18000f2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2fa  mov     rdx, [rsi+20h]
0x18000f2fe  mov     ebx, eax
0x18000f300  mov     r12d, 88982F40h
0x18000f306  test    rdx, rdx
0x18000f309  jnz     short loc_18000F327
0x18000f30b  xor     eax, eax
0x18000f30d  cmp     ebx, r12d
0x18000f310  jnz     short loc_18000F346
0x18000f312  xor     ebx, ebx
0x18000f314  test    eax, eax
0x18000f316  jnz     short loc_18000F346
0x18000f318  mov     eax, ebx
0x18000f31a  add     rsp, 28h
0x18000f31e  pop     r14
0x18000f320  pop     r12
0x18000f322  pop     rdi
0x18000f323  pop     rsi
0x18000f324  pop     rbp
0x18000f325  pop     rbx
0x18000f326  retn
0x18000f327  mov     rcx, [rbp+28h]
0x18000f32b  mov     r8, [rcx]
0x18000f32e  mov     rax, [r8+28h]
0x18000f332  xor     r8d, r8d
0x18000f335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f33a  cmp     eax, r12d
0x18000f33d  jz      short loc_18000F30B
0x18000f33f  mov     eax, 1
0x18000f344  jmp     short loc_18000F30D
0x18000f346  mov     rdx, rsi; struct RULE_PATH_INFO *
0x18000f349  mov     rcx, rbp; this
0x18000f34c  call    ?NeedToProcessChecksumForPath@CRuleWriter@@IEAAHPEBURULE_PATH_INFO@@@Z; CRuleWriter::NeedToProcessChecksumForPath(RULE_PATH_INFO const *)
0x18000f351  mov     r14d, eax
0x18000f354  test    eax, eax
0x18000f356  jz      short loc_18000F369
0x18000f358  mov     rdx, rsi; struct RULE_PATH_INFO *
0x18000f35b  mov     rcx, rbp; this
0x18000f35e  call    ?WriteOtherKeysAffectedByChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::WriteOtherKeysAffectedByChecksum(RULE_PATH_INFO const *)
0x18000f363  mov     ebx, eax
0x18000f365  test    eax, eax
0x18000f367  js      short loc_18000F318
0x18000f369  mov     rcx, [rbp+28h]
0x18000f36d  mov     rdx, [rcx]
0x18000f370  mov     rax, [rdx+40h]
0x18000f374  mov     rdx, [rsi+18h]
0x18000f378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f37d  mov     ebx, eax
0x18000f37f  cmp     eax, r12d
0x18000f382  jnz     short loc_18000F38A
0x18000f384  xor     edi, edi
0x18000f386  xor     ebx, ebx
0x18000f388  jmp     short loc_18000F393
0x18000f38a  test    eax, eax
0x18000f38c  js      short loc_18000F318
0x18000f38e  mov     edi, 1
0x18000f393  mov     rdx, [rsi+20h]
0x18000f397  test    rdx, rdx
0x18000f39a  jz      short loc_18000F3C4
0x18000f39c  mov     rcx, [rbp+28h]
0x18000f3a0  mov     rax, [rcx]
0x18000f3a3  mov     rax, [rax+40h]
0x18000f3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3ac  mov     ebx, eax
0x18000f3ae  cmp     eax, r12d
0x18000f3b1  jnz     short loc_18000F3B7
0x18000f3b3  xor     ebx, ebx
0x18000f3b5  jmp     short loc_18000F3C4
0x18000f3b7  test    eax, eax
0x18000f3b9  js      loc_18000F318
0x18000f3bf  mov     edi, 1
0x18000f3c4  test    r14d, r14d
0x18000f3c7  jz      loc_18000F318
0x18000f3cd  test    edi, edi
0x18000f3cf  jz      loc_18000F318
0x18000f3d5  mov     rdx, rsi; struct RULE_PATH_INFO *
0x18000f3d8  mov     rcx, rbp; this
0x18000f3db  call    ?UpdateChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::UpdateChecksum(RULE_PATH_INFO const *)
0x18000f3e0  jmp     loc_18000F318
```

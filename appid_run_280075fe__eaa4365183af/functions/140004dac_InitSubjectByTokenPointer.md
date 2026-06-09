# InitSubjectByTokenPointer

- ea: `0x140004dac`
- end: `0x140004e1f`
- name: `InitSubjectByTokenPointer`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005750`
- `0x1400057ec`
- `0x140005848`

## callees

- `0x1400048b8`
- `0x140004dac`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140004ddb`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004ddb`

## pseudocode

```c
__int64 __fastcall InitSubjectByTokenPointer(struct _SECURITY_SUBJECT_CONTEXT *a1, _QWORD *a2)
{
  struct _SECURITY_SUBJECT_CONTEXT *v3; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v4; // rax
  __int64 result; // rax
  struct _SECURITY_SUBJECT_CONTEXT *v6; // rax
  PACCESS_TOKEN ClientToken; // rax

  v3 = a1;
  if ( a1 )
  {
    v6 = 0;
  }
  else
  {
    v4 = (struct _SECURITY_SUBJECT_CONTEXT *)EnterpriseContextLibMemAlloc(32);
    v3 = v4;
    if ( !v4 )
      return 3221225495LL;
    SeCaptureSubjectContext(v4);
    v6 = v3;
  }
  a2[1] = v6;
  ClientToken = v3->ClientToken;
  if ( !v3->ClientToken )
    ClientToken = v3->PrimaryToken;
  *a2 = ClientToken;
  result = 0;
  a2[3] = 0;
  a2[2] = 0;
  return result;
}

```

## disassembly

```asm
0x140004dac  mov     [rsp+arg_0], rbx
0x140004db1  push    rdi
0x140004db2  sub     rsp, 20h
0x140004db6  mov     rdi, rdx
0x140004db9  mov     rbx, rcx
0x140004dbc  test    rcx, rcx
0x140004dbf  jnz     short loc_140004DEC
0x140004dc1  lea     ecx, [rbx+20h]
0x140004dc4  call    EnterpriseContextLibMemAlloc
0x140004dc9  mov     rbx, rax
0x140004dcc  test    rax, rax
0x140004dcf  jnz     short loc_140004DD8
0x140004dd1  mov     eax, 0C0000017h
0x140004dd6  jmp     short loc_140004E13
0x140004dd8  mov     rcx, rbx; SubjectContext
0x140004ddb  call    cs:__imp_SeCaptureSubjectContext
0x140004de2  nop     dword ptr [rax+rax+00h]
0x140004de7  mov     rax, rbx
0x140004dea  jmp     short loc_140004DEE
0x140004dec  xor     eax, eax
0x140004dee  mov     [rdi+8], rax
0x140004df2  mov     rax, [rbx]
0x140004df5  test    rax, rax
0x140004df8  jnz     short loc_140004DFE
0x140004dfa  mov     rax, [rbx+10h]
0x140004dfe  mov     [rdi], rax
0x140004e01  xor     eax, eax
0x140004e03  mov     qword ptr [rdi+18h], 0
0x140004e0b  mov     qword ptr [rdi+10h], 0
0x140004e13  mov     rbx, [rsp+28h+arg_0]
0x140004e18  add     rsp, 20h
0x140004e1c  pop     rdi
0x140004e1d  retn
```

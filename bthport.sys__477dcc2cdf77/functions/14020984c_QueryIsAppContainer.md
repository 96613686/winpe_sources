# QueryIsAppContainer

- ea: `0x14020984c`
- end: `0x1402098ca`
- name: `QueryIsAppContainer`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1401bd640`

## callees

- `0x14020984c`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14020989d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14020989d`
- `ntoskrnl!SeQueryInformationToken` at `0x14020988c`
- `ntoskrnl!SeQueryInformationToken` at `0x14020988c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140209870`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140209870`

## pseudocode

```c
__int64 __fastcall QueryIsAppContainer(struct _KPROCESS *a1, bool *a2)
{
  NTSTATUS v3; // edi
  PACCESS_TOKEN v4; // rbx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(TokenInformation) = 0;
  v3 = -1073741823;
  if ( a1 )
  {
    v4 = PsReferencePrimaryToken(a1);
    v3 = SeQueryInformationToken(v4, TokenIsAppContainer, &TokenInformation);
    PsDereferencePrimaryToken(v4);
    if ( v3 >= 0 )
      *a2 = (_DWORD)TokenInformation != 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14020984c  mov     [rsp+arg_8], rbx
0x140209851  mov     [rsp+arg_10], rsi
0x140209856  push    rdi
0x140209857  sub     rsp, 20h
0x14020985b  mov     dword ptr [rsp+28h+TokenInformation], 0
0x140209863  mov     rsi, rdx
0x140209866  mov     edi, 0C0000001h
0x14020986b  test    rcx, rcx
0x14020986e  jz      short loc_1402098B7
0x140209870  call    cs:__imp_PsReferencePrimaryToken
0x140209877  nop     dword ptr [rax+rax+00h]
0x14020987c  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x140209881  mov     edx, 1Dh; TokenInformationClass
0x140209886  mov     rcx, rax; Token
0x140209889  mov     rbx, rax
0x14020988c  call    cs:__imp_SeQueryInformationToken
0x140209893  nop     dword ptr [rax+rax+00h]
0x140209898  mov     rcx, rbx; PrimaryToken
0x14020989b  mov     edi, eax
0x14020989d  call    cs:__imp_PsDereferencePrimaryToken
0x1402098a4  nop     dword ptr [rax+rax+00h]
0x1402098a9  test    edi, edi
0x1402098ab  js      short loc_1402098B7
0x1402098ad  cmp     dword ptr [rsp+28h+TokenInformation], 0
0x1402098b2  setnz   cl
0x1402098b5  mov     [rsi], cl
0x1402098b7  mov     rbx, [rsp+28h+arg_8]
0x1402098bc  mov     eax, edi
0x1402098be  mov     rsi, [rsp+28h+arg_10]
0x1402098c3  add     rsp, 20h
0x1402098c7  pop     rdi
0x1402098c8  retn
```

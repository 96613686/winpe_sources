# AipQueryValue

- ea: `0x14002aefc`
- end: `0x14002b07c`
- name: `AipQueryValue`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002ab78`

## callees

- `0x14002aafc`
- `0x14002aefc`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002afed`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002afed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002afbe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002afbe`

## pseudocode

```c
__int64 __fastcall AipQueryValue(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int16 v9; // cx
  unsigned __int16 *v10; // rsi
  WCHAR *v11; // r15
  int v12; // ebp
  __int64 v13; // rax
  unsigned __int16 v14; // cx
  __int64 v15; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  v8 = -2;
  String1 = 0;
  DestinationString = 0;
  if ( !a1[2] )
  {
    v9 = *a1;
    if ( (unsigned __int16)(v9 - 8) <= 0x7FF8u && (v9 & 1) == 0 )
    {
LABEL_6:
      while ( *a2 == 92 )
        ++a2;
      v10 = (unsigned __int16 *)AipCheckBlock(v7, *v7);
      if ( v10 )
      {
        if ( *a2 )
        {
          v11 = a2;
          do
          {
            if ( *a2 == 92 )
              break;
            ++a2;
          }
          while ( *a2 );
          v12 = (_DWORD)v7 + *v7;
          while ( AipCheckBlock(v10, (unsigned int)(v12 - (_DWORD)v10)) )
          {
            RtlInitUnicodeString(&DestinationString, v10 + 3);
            String1.Buffer = v11;
            String1.Length = (_WORD)a2 - (_WORD)v11;
            String1.MaximumLength = (_WORD)a2 - (_WORD)v11;
            if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
            {
              v7 = v10;
              goto LABEL_6;
            }
            v10 = (unsigned __int16 *)((char *)v10 + ((*v10 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
          }
        }
        else
        {
          *a4 = v7[1];
          v13 = -1;
          do
            ++v13;
          while ( v7[v13 + 3] );
          v14 = v7[1];
          if ( v14 && (v7[2] || v14 >= 2u) )
            v15 = (2 * (_DWORD)v13 + 11) & 0xFFFFFFFC;
          else
            v15 = 2LL * (unsigned int)v13 + 6;
          v8 = 0;
          *a3 = (char *)v7 + v15;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14002aefc  push    rbx
0x14002aefe  push    rbp
0x14002aeff  push    rsi
0x14002af00  push    rdi
0x14002af01  push    r12
0x14002af03  push    r13
0x14002af05  push    r14
0x14002af07  push    r15
0x14002af09  sub     rsp, 48h
0x14002af0d  xor     ebp, ebp
0x14002af0f  xorps   xmm0, xmm0
0x14002af12  xorps   xmm1, xmm1
0x14002af15  mov     r12, r9
0x14002af18  mov     r13, r8
0x14002af1b  mov     rdi, rdx
0x14002af1e  mov     rbx, rcx
0x14002af21  mov     r14d, 0FFFFFFFEh
0x14002af27  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x14002af2c  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x14002af31  cmp     [rcx+4], bp
0x14002af35  jnz     loc_14002B067
0x14002af3b  movzx   ecx, word ptr [rcx]
0x14002af3e  mov     edx, 7FF8h
0x14002af43  lea     eax, [rcx-8]
0x14002af46  cmp     ax, dx
0x14002af49  ja      loc_14002B067
0x14002af4f  test    cl, 1
0x14002af52  jnz     loc_14002B067
0x14002af58  mov     r15d, 2
0x14002af5e  jmp     short loc_14002AF63
0x14002af60  add     rdi, r15
0x14002af63  cmp     word ptr [rdi], 5Ch ; '\'
0x14002af67  jz      short loc_14002AF60
0x14002af69  movzx   edx, word ptr [rbx]
0x14002af6c  mov     rcx, rbx
0x14002af6f  call    AipCheckBlock
0x14002af74  mov     rsi, rax
0x14002af77  test    rax, rax
0x14002af7a  jz      loc_14002B067
0x14002af80  cmp     [rdi], bp
0x14002af83  jz      loc_14002B017
0x14002af89  mov     r15, rdi
0x14002af8c  cmp     word ptr [rdi], 5Ch ; '\'
0x14002af90  jz      short loc_14002AF9B
0x14002af92  add     rdi, 2
0x14002af96  cmp     [rdi], bp
0x14002af99  jnz     short loc_14002AF8C
0x14002af9b  movzx   ebp, word ptr [rbx]
0x14002af9e  add     ebp, ebx
0x14002afa0  mov     edx, ebp
0x14002afa2  mov     rcx, rsi
0x14002afa5  sub     edx, esi
0x14002afa7  call    AipCheckBlock
0x14002afac  test    rax, rax
0x14002afaf  jz      loc_14002B067
0x14002afb5  lea     rdx, [rsi+6]; SourceString
0x14002afb9  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14002afbe  call    cs:__imp_RtlInitUnicodeString
0x14002afc5  nop     dword ptr [rax+rax+00h]
0x14002afca  movzx   eax, di
0x14002afcd  mov     [rsp+88h+String1.Buffer], r15
0x14002afd2  sub     ax, r15w
0x14002afd6  lea     rdx, [rsp+88h+DestinationString]; String2
0x14002afdb  mov     r8b, 1; CaseInSensitive
0x14002afde  mov     [rsp+88h+String1.Length], ax
0x14002afe3  lea     rcx, [rsp+88h+String1]; String1
0x14002afe8  mov     [rsp+88h+String1.MaximumLength], ax
0x14002afed  call    cs:__imp_RtlCompareUnicodeString
0x14002aff4  nop     dword ptr [rax+rax+00h]
0x14002aff9  test    eax, eax
0x14002affb  jz      short loc_14002B00D
0x14002affd  movzx   eax, word ptr [rsi]
0x14002b000  add     rax, 3
0x14002b004  and     rax, 0FFFFFFFFFFFFFFFCh
0x14002b008  add     rsi, rax
0x14002b00b  jmp     short loc_14002AFA0
0x14002b00d  mov     rbx, rsi
0x14002b010  xor     ebp, ebp
0x14002b012  jmp     loc_14002AF58
0x14002b017  movzx   eax, word ptr [rbx+2]
0x14002b01b  mov     [r12], rax
0x14002b01f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b023  inc     rax
0x14002b026  cmp     [rbx+rax*2+6], bp
0x14002b02b  jnz     short loc_14002B023
0x14002b02d  movzx   ecx, word ptr [rbx+2]
0x14002b031  test    cx, cx
0x14002b034  jz      short loc_14002B053
0x14002b036  cmp     [rbx+4], bp
0x14002b03a  jnz     short loc_14002B042
0x14002b03c  cmp     cx, r15w
0x14002b040  jb      short loc_14002B053
0x14002b042  lea     eax, ds:0Bh[rax*2]
0x14002b049  mov     ecx, 0FFFFFFFCh
0x14002b04e  and     rax, rcx
0x14002b051  jmp     short loc_14002B05D
0x14002b053  mov     eax, eax
0x14002b055  lea     rax, ds:6[rax*2]
0x14002b05d  add     rax, rbx
0x14002b060  mov     r14d, ebp
0x14002b063  mov     [r13+0], rax
0x14002b067  mov     eax, r14d
0x14002b06a  add     rsp, 48h
0x14002b06e  pop     r15
0x14002b070  pop     r14
0x14002b072  pop     r13
0x14002b074  pop     r12
0x14002b076  pop     rdi
0x14002b077  pop     rsi
0x14002b078  pop     rbp
0x14002b079  pop     rbx
0x14002b07a  retn
```

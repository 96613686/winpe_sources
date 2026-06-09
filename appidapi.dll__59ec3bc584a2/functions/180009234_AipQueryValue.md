# AipQueryValue

- ea: `0x180009234`
- end: `0x1800093a6`
- name: `AipQueryValue`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008be4`

## callees

- `0x180008b48`
- `0x180009234`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180009320`
- `ntdll!RtlCompareUnicodeString` at `0x180009320`
- `ntdll!RtlInitUnicodeString` at `0x1800092f7`
- `ntdll!RtlInitUnicodeString` at `0x1800092f7`

## pseudocode

```c
__int64 __fastcall AipQueryValue(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rsi
  WCHAR *v10; // r15
  int v11; // ebp
  __int64 v12; // rax
  __int64 v13; // rax
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  v8 = -2;
  String1 = 0;
  DestinationString = 0;
  if ( !a1[2] && (unsigned __int16)(*a1 - 8) <= 0x7FF8u && (*(_BYTE *)a1 & 1) == 0 )
  {
LABEL_6:
    while ( *a2 == 92 )
      ++a2;
    v9 = (unsigned __int16 *)AipCheckBlock(v7, *v7);
    if ( v9 )
    {
      if ( *a2 )
      {
        v10 = a2;
        do
        {
          if ( *a2 == 92 )
            break;
          ++a2;
        }
        while ( *a2 );
        v11 = (_DWORD)v7 + *v7;
        while ( AipCheckBlock(v9, (unsigned int)(v11 - (_DWORD)v9)) )
        {
          RtlInitUnicodeString(&DestinationString, v9 + 3);
          String1.Buffer = v10;
          String1.Length = (_WORD)a2 - (_WORD)v10;
          String1.MaximumLength = (_WORD)a2 - (_WORD)v10;
          if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
          {
            v7 = v9;
            goto LABEL_6;
          }
          v9 = (unsigned __int16 *)((char *)v9 + ((*v9 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
        }
      }
      else
      {
        *a4 = v7[1];
        v12 = -1;
        do
          ++v12;
        while ( v7[v12 + 3] );
        if ( v7[1] && *(_DWORD *)(v7 + 1) >= 2u )
          v13 = (2 * (_DWORD)v12 + 11) & 0xFFFFFFFC;
        else
          v13 = 2LL * (unsigned int)v12 + 6;
        v8 = 0;
        *a3 = (char *)v7 + v13;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180009234  push    rbx
0x180009236  push    rbp
0x180009237  push    rsi
0x180009238  push    rdi
0x180009239  push    r12
0x18000923b  push    r13
0x18000923d  push    r14
0x18000923f  push    r15
0x180009241  sub     rsp, 48h
0x180009245  xor     ebp, ebp
0x180009247  xorps   xmm0, xmm0
0x18000924a  xorps   xmm1, xmm1
0x18000924d  mov     r12, r9
0x180009250  mov     r13, r8
0x180009253  mov     rdi, rdx
0x180009256  mov     rbx, rcx
0x180009259  mov     r14d, 0FFFFFFFEh
0x18000925f  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x180009264  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x180009269  cmp     [rcx+4], bp
0x18000926d  jnz     loc_180009392
0x180009273  movzx   eax, word ptr [rcx]
0x180009276  mov     ecx, 7FF8h
0x18000927b  sub     ax, 8
0x18000927f  cmp     ax, cx
0x180009282  ja      loc_180009392
0x180009288  test    byte ptr [rbx], 1
0x18000928b  jnz     loc_180009392
0x180009291  mov     r15d, 2
0x180009297  jmp     short loc_18000929C
0x180009299  add     rdi, r15
0x18000929c  cmp     word ptr [rdi], 5Ch ; '\'
0x1800092a0  jz      short loc_180009299
0x1800092a2  movzx   edx, word ptr [rbx]
0x1800092a5  mov     rcx, rbx
0x1800092a8  call    AipCheckBlock
0x1800092ad  mov     rsi, rax
0x1800092b0  test    rax, rax
0x1800092b3  jz      loc_180009392
0x1800092b9  cmp     [rdi], bp
0x1800092bc  jz      loc_180009344
0x1800092c2  mov     r15, rdi
0x1800092c5  cmp     word ptr [rdi], 5Ch ; '\'
0x1800092c9  jz      short loc_1800092D4
0x1800092cb  add     rdi, 2
0x1800092cf  cmp     [rdi], bp
0x1800092d2  jnz     short loc_1800092C5
0x1800092d4  movzx   ebp, word ptr [rbx]
0x1800092d7  add     ebp, ebx
0x1800092d9  mov     edx, ebp
0x1800092db  mov     rcx, rsi
0x1800092de  sub     edx, esi
0x1800092e0  call    AipCheckBlock
0x1800092e5  test    rax, rax
0x1800092e8  jz      loc_180009392
0x1800092ee  lea     rdx, [rsi+6]; SourceString
0x1800092f2  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800092f7  call    cs:__imp_RtlInitUnicodeString
0x1800092fd  movzx   eax, di
0x180009300  mov     [rsp+88h+String1.Buffer], r15
0x180009305  sub     ax, r15w
0x180009309  lea     rdx, [rsp+88h+DestinationString]; String2
0x18000930e  mov     r8b, 1; CaseInsensitive
0x180009311  mov     [rsp+88h+String1.Length], ax
0x180009316  lea     rcx, [rsp+88h+String1]; String1
0x18000931b  mov     [rsp+88h+String1.MaximumLength], ax
0x180009320  call    cs:__imp_RtlCompareUnicodeString
0x180009326  test    eax, eax
0x180009328  jz      short loc_18000933A
0x18000932a  movzx   eax, word ptr [rsi]
0x18000932d  add     rax, 3
0x180009331  and     rax, 0FFFFFFFFFFFFFFFCh
0x180009335  add     rsi, rax
0x180009338  jmp     short loc_1800092D9
0x18000933a  mov     rbx, rsi
0x18000933d  xor     ebp, ebp
0x18000933f  jmp     loc_180009291
0x180009344  movzx   eax, word ptr [rbx+2]
0x180009348  mov     [r12], rax
0x18000934c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009350  inc     rax
0x180009353  cmp     [rbx+rax*2+6], bp
0x180009358  jnz     short loc_180009350
0x18000935a  cmp     [rbx+2], bp
0x18000935e  jz      short loc_18000937E
0x180009360  cmp     [rbx+4], bp
0x180009364  jnz     short loc_18000936D
0x180009366  cmp     [rbx+2], r15w
0x18000936b  jb      short loc_18000937E
0x18000936d  lea     eax, ds:0Bh[rax*2]
0x180009374  mov     ecx, 0FFFFFFFCh
0x180009379  and     rax, rcx
0x18000937c  jmp     short loc_180009388
0x18000937e  mov     eax, eax
0x180009380  lea     rax, ds:6[rax*2]
0x180009388  add     rax, rbx
0x18000938b  mov     r14d, ebp
0x18000938e  mov     [r13+0], rax
0x180009392  mov     eax, r14d
0x180009395  add     rsp, 48h
0x180009399  pop     r15
0x18000939b  pop     r14
0x18000939d  pop     r13
0x18000939f  pop     r12
0x1800093a1  pop     rdi
0x1800093a2  pop     rsi
0x1800093a3  pop     rbp
0x1800093a4  pop     rbx
0x1800093a5  retn
```

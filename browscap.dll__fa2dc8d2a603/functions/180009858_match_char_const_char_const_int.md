# match(char const *,char const *,int *)

- ea: `0x180009858`
- end: `0x180009936`
- name: `?match@@YA_NPEBD0PEAH@Z`
- size: `222`
- prototype: `bool __fastcall(char *, char *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008e40`
- `0x180009858`

## callees

- `0x180009858`

## import_xrefs

- `msvcrt!strchr` at `0x180009880`
- `msvcrt!strchr` at `0x180009880`
- `msvcrt!tolower` at `0x1800098c3`
- `msvcrt!tolower` at `0x1800098ce`
- `msvcrt!tolower` at `0x1800098c3`
- `msvcrt!tolower` at `0x1800098ce`

## pseudocode

```c
bool __fastcall match(char *a1, char *a2, int *a3)
{
  char v3; // al
  const char *v6; // rdi
  char *v7; // rax
  char v8; // cl
  char v9; // dl
  int v10; // ebx
  bool result; // al
  bool v12; // al
  int v13; // edx
  int v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v6 = a1;
  while ( v3 != 42 )
  {
    if ( !*a2 )
      return v3 == 0;
    if ( v3 == 91 )
    {
      v7 = strchr(v6, 93);
      if ( v7 )
      {
        while ( 1 )
        {
          v8 = *++v6;
          if ( *v6 == 93 )
            return 0;
          v9 = *a2;
          if ( v8 != *a2 )
          {
            if ( v6[1] != 45 )
              continue;
            v6 += 2;
            if ( *v6 < v9 || v8 > v9 )
              continue;
          }
          ++*a3;
          goto LABEL_15;
        }
      }
    }
    if ( *v6 == 63 )
    {
      ++*a3;
    }
    else
    {
      v10 = tolower(*v6);
      if ( v10 != tolower(*a2) )
        return 0;
    }
    v7 = (char *)v6;
LABEL_15:
    v6 = v7 + 1;
    ++a2;
    v3 = v7[1];
  }
  while ( 1 )
  {
    v14 = 0;
    v12 = match(v6 + 1, a2, &v14);
    v13 = *a3;
    if ( v12 )
      break;
    *a3 = v13 + 1;
    if ( !*a2 )
      return 0;
    ++a2;
  }
  result = 1;
  *a3 = v14 + v13;
  return result;
}

```

## disassembly

```asm
0x180009858  push    rbx
0x18000985a  push    rsi
0x18000985b  push    rdi
0x18000985c  push    r14
0x18000985e  sub     rsp, 28h
0x180009862  mov     al, [rcx]
0x180009864  mov     r14, r8
0x180009867  mov     rsi, rdx
0x18000986a  mov     rdi, rcx
0x18000986d  jmp     short loc_1800098E4
0x18000986f  cmp     byte ptr [rsi], 0
0x180009872  jz      short loc_1800098EA
0x180009874  cmp     al, 5Bh ; '['
0x180009876  jnz     short loc_1800098B6
0x180009878  mov     edx, 5Dh ; ']'; Val
0x18000987d  mov     rcx, rdi; Str
0x180009880  call    cs:__imp_strchr
0x180009886  test    rax, rax
0x180009889  jz      short loc_1800098B6
0x18000988b  inc     rdi
0x18000988e  mov     cl, [rdi]
0x180009890  cmp     cl, 5Dh ; ']'
0x180009893  jz      loc_180009932
0x180009899  mov     dl, [rsi]
0x18000989b  cmp     cl, dl
0x18000989d  jz      short loc_1800098B1
0x18000989f  cmp     byte ptr [rdi+1], 2Dh ; '-'
0x1800098a3  jnz     short loc_18000988B
0x1800098a5  add     rdi, 2
0x1800098a9  cmp     [rdi], dl
0x1800098ab  jl      short loc_18000988B
0x1800098ad  cmp     cl, dl
0x1800098af  jg      short loc_18000988B
0x1800098b1  inc     dword ptr [r14]
0x1800098b4  jmp     short loc_1800098DB
0x1800098b6  cmp     byte ptr [rdi], 3Fh ; '?'
0x1800098b9  jnz     short loc_1800098C0
0x1800098bb  inc     dword ptr [r14]
0x1800098be  jmp     short loc_1800098D8
0x1800098c0  movsx   ecx, byte ptr [rdi]; C
0x1800098c3  call    cs:__imp_tolower
0x1800098c9  movsx   ecx, byte ptr [rsi]; C
0x1800098cc  mov     ebx, eax
0x1800098ce  call    cs:__imp_tolower
0x1800098d4  cmp     ebx, eax
0x1800098d6  jnz     short loc_180009932
0x1800098d8  mov     rax, rdi
0x1800098db  lea     rdi, [rax+1]
0x1800098df  inc     rsi
0x1800098e2  mov     al, [rdi]
0x1800098e4  cmp     al, 2Ah ; '*'
0x1800098e6  jnz     short loc_18000986F
0x1800098e8  jmp     short loc_1800098FF
0x1800098ea  test    al, al
0x1800098ec  setz    al
0x1800098ef  jmp     short loc_180009928
0x1800098f1  lea     eax, [rdx+1]
0x1800098f4  mov     [r14], eax
0x1800098f7  cmp     byte ptr [rsi], 0
0x1800098fa  jz      short loc_180009932
0x1800098fc  inc     rsi
0x1800098ff  lea     r8, [rsp+48h+arg_0]; int *
0x180009904  mov     [rsp+48h+arg_0], 0
0x18000990c  mov     rdx, rsi; char *
0x18000990f  lea     rcx, [rdi+1]; char *
0x180009913  call    ?match@@YA_NPEBD0PEAH@Z; match(char const *,char const *,int *)
0x180009918  mov     edx, [r14]
0x18000991b  cmp     al, 1
0x18000991d  jnz     short loc_1800098F1
0x18000991f  add     edx, [rsp+48h+arg_0]
0x180009923  mov     al, 1
0x180009925  mov     [r14], edx
0x180009928  add     rsp, 28h
0x18000992c  pop     r14
0x18000992e  pop     rdi
0x18000992f  pop     rsi
0x180009930  pop     rbx
0x180009931  retn
0x180009932  xor     al, al
0x180009934  jmp     short loc_180009928
```

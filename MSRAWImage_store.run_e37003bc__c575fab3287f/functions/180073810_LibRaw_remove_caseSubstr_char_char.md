# LibRaw::remove_caseSubstr(char *,char *)

- ea: `0x180073810`
- end: `0x1800738f0`
- name: `?remove_caseSubstr@LibRaw@@KAXPEAD0@Z`
- size: `224`
- prototype: `void __fastcall(char *String1, char *String2)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180073a10`

## callees

- `0x180005d0f`
- `0x18002c2f0`
- `0x180073810`
- `0x180094fb1`
- `0x1800b0460`
- `0x1800b0b00`

## pseudocode

```c
void __fastcall LibRaw::remove_caseSubstr(char *String1, char *String2)
{
  char *v4; // rax
  int v5; // ebx
  int v6; // eax
  int v7; // edx
  int v8; // ebx
  char *v9; // rax
  char *v10; // rsi
  int v11; // eax
  int v12; // ebx
  char *i; // rdi
  char j; // al

  v4 = LibRaw::strcasestr(String1, String2);
  v5 = (int)v4;
  if ( v4 )
  {
    do
    {
      v6 = strlen_0(String2);
      v8 = v5 - (_DWORD)String1;
      if ( v8 < v8 + v6 )
      {
        LOBYTE(v7) = 32;
        memset(&String1[v8], v7, v6);
      }
      v9 = LibRaw::strcasestr(String1, String2);
      v5 = (int)v9;
    }
    while ( v9 );
  }
  v10 = String1;
  v11 = strlen_0(String1);
  v12 = v11;
  if ( v11 )
  {
    for ( i = &String1[v11]; isspace_0(*(i - 1)); *i = 0 )
    {
      --i;
      --v12;
    }
    for ( j = *String1; j; --v12 )
    {
      if ( !isspace_0(j) )
        break;
      j = *++v10;
    }
    memmove(String1, v10, v12 + 1);
  }
}

```

## disassembly

```asm
0x180073810  mov     [rsp+arg_0], rbx
0x180073815  mov     [rsp+arg_8], rsi
0x18007381a  mov     [rsp+arg_10], rdi
0x18007381f  push    r14
0x180073821  sub     rsp, 20h
0x180073825  mov     rdi, rdx
0x180073828  mov     r14, rcx
0x18007382b  call    ?strcasestr@LibRaw@@KAPEADPEADPEBD@Z; LibRaw::strcasestr(char *,char const *)
0x180073830  mov     rbx, rax
0x180073833  test    rax, rax
0x180073836  jz      short loc_18007386D
0x180073838  mov     rcx, rdi; Str
0x18007383b  call    strlen_0
0x180073840  sub     ebx, r14d
0x180073843  lea     ecx, [rbx+rax]
0x180073846  cmp     ebx, ecx
0x180073848  jge     short loc_18007385A
0x18007384a  movsxd  rcx, ebx
0x18007384d  mov     dl, 20h ; ' '; Val
0x18007384f  add     rcx, r14; void *
0x180073852  movsxd  r8, eax; Size
0x180073855  call    memset
0x18007385a  mov     rdx, rdi; String2
0x18007385d  mov     rcx, r14; String1
0x180073860  call    ?strcasestr@LibRaw@@KAPEADPEADPEBD@Z; LibRaw::strcasestr(char *,char const *)
0x180073865  mov     rbx, rax
0x180073868  test    rax, rax
0x18007386b  jnz     short loc_180073838
0x18007386d  mov     rcx, r14; Str
0x180073870  mov     rsi, r14
0x180073873  call    strlen_0
0x180073878  mov     rbx, rax
0x18007387b  test    eax, eax
0x18007387d  jz      short loc_1800738DA
0x18007387f  movsxd  rdi, eax
0x180073882  add     rdi, r14
0x180073885  movsx   ecx, byte ptr [rdi-1]; C
0x180073889  call    isspace_0
0x18007388e  test    eax, eax
0x180073890  jz      short loc_1800738A8
0x180073892  lea     rdi, [rdi-1]
0x180073896  dec     ebx
0x180073898  mov     byte ptr [rdi], 0
0x18007389b  movsx   ecx, byte ptr [rdi-1]; C
0x18007389f  call    isspace_0
0x1800738a4  test    eax, eax
0x1800738a6  jnz     short loc_180073892
0x1800738a8  movzx   eax, byte ptr [r14]
0x1800738ac  test    al, al
0x1800738ae  jz      short loc_1800738C9
0x1800738b0  movsx   ecx, al; C
0x1800738b3  call    isspace_0
0x1800738b8  test    eax, eax
0x1800738ba  jz      short loc_1800738C9
0x1800738bc  movzx   eax, byte ptr [rsi+1]
0x1800738c0  inc     rsi
0x1800738c3  dec     ebx
0x1800738c5  test    al, al
0x1800738c7  jnz     short loc_1800738B0
0x1800738c9  lea     eax, [rbx+1]
0x1800738cc  mov     rdx, rsi; Src
0x1800738cf  movsxd  r8, eax; Size
0x1800738d2  mov     rcx, r14; void *
0x1800738d5  call    memmove
0x1800738da  mov     rbx, [rsp+28h+arg_0]
0x1800738df  mov     rsi, [rsp+28h+arg_8]
0x1800738e4  mov     rdi, [rsp+28h+arg_10]
0x1800738e9  add     rsp, 20h
0x1800738ed  pop     r14
0x1800738ef  retn
```

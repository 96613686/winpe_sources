# IPStrToDWord(ushort const *,ulong *)

- ea: `0x180026f60`
- end: `0x18002709e`
- name: `?IPStrToDWord@@YAJPEBGPEAK@Z`
- size: `318`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800200e0`

## callees

- `0x180003460`
- `0x180026f60`

## import_xrefs

- `msvcrt!wcschr` at `0x180026fd9`
- `msvcrt!wcschr` at `0x180027005`
- `msvcrt!wcschr` at `0x18002702d`
- `msvcrt!wcschr` at `0x180026fd9`
- `msvcrt!wcschr` at `0x180027005`
- `msvcrt!wcschr` at `0x18002702d`
- `msvcrt!_wtoi` at `0x180026ff3`
- `msvcrt!_wtoi` at `0x18002701c`
- `msvcrt!_wtoi` at `0x180027044`
- `msvcrt!_wtoi` at `0x18002705b`
- `msvcrt!_wtoi` at `0x180026ff3`
- `msvcrt!_wtoi` at `0x18002701c`
- `msvcrt!_wtoi` at `0x180027044`
- `msvcrt!_wtoi` at `0x18002705b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026faa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026faa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027075`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027075`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026fbf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180026fbf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026f8a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180026f8a`

## pseudocode

```c
__int64 __fastcall IPStrToDWord(const unsigned __int16 *a1, unsigned int *a2)
{
  int v4; // edi
  const wchar_t *Str; // rax
  const wchar_t *v6; // rbx
  wchar_t *v7; // rsi
  int v8; // r15d
  wchar_t *v9; // rbx
  int v10; // ebp
  wchar_t *v11; // rsi
  int v12; // ebx
  _BYTE v14[56]; // [rsp+20h] [rbp-68h] BYREF

  STRU::STRU((STRU *)v14);
  if ( !a2 || !a1 )
    goto LABEL_9;
  v4 = STRU::Copy((STRU *)v14, a1);
  if ( v4 >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v14);
    v6 = Str;
    if ( Str )
    {
      v7 = wcschr(Str, 0x2Eu);
      if ( v7 )
      {
        *v7 = 0;
        v8 = _wtoi(v6);
        v9 = wcschr(v7 + 1, 0x2Eu);
        if ( v9 )
        {
          *v9 = 0;
          v10 = _wtoi(v7 + 1);
          v11 = wcschr(v9 + 1, 0x2Eu);
          if ( v11 )
          {
            *v11 = 0;
            v12 = v8 | ((v10 | (_wtoi(v9 + 1) << 8)) << 8);
            *a2 = v12 | (_wtoi(v11 + 1) << 24);
            goto LABEL_10;
          }
        }
      }
    }
LABEL_9:
    v4 = -2147024809;
  }
LABEL_10:
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026f60  mov     [rsp+arg_10], rbx
0x180026f65  push    rbp
0x180026f66  push    rsi
0x180026f67  push    rdi
0x180026f68  push    r14
0x180026f6a  push    r15
0x180026f6c  sub     rsp, 60h
0x180026f70  mov     rax, cs:__security_cookie
0x180026f77  xor     rax, rsp
0x180026f7a  mov     [rsp+88h+var_30], rax
0x180026f7f  mov     rbx, rcx
0x180026f82  mov     r14, rdx
0x180026f85  lea     rcx, [rsp+88h+var_68]
0x180026f8a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180026f90  test    r14, r14
0x180026f93  jz      loc_18002706B
0x180026f99  test    rbx, rbx
0x180026f9c  jz      loc_18002706B
0x180026fa2  mov     rdx, rbx
0x180026fa5  lea     rcx, [rsp+88h+var_68]
0x180026faa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026fb0  mov     edi, eax
0x180026fb2  test    eax, eax
0x180026fb4  js      loc_180027070
0x180026fba  lea     rcx, [rsp+88h+var_68]
0x180026fbf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180026fc5  mov     rbx, rax
0x180026fc8  test    rax, rax
0x180026fcb  jz      loc_18002706B
0x180026fd1  mov     edx, 2Eh ; '.'; Ch
0x180026fd6  mov     rcx, rax; Str
0x180026fd9  call    cs:__imp_wcschr
0x180026fdf  mov     rsi, rax
0x180026fe2  test    rax, rax
0x180026fe5  jz      loc_18002706B
0x180026feb  xor     eax, eax
0x180026fed  mov     rcx, rbx; String
0x180026ff0  mov     [rsi], ax
0x180026ff3  call    cs:__imp__wtoi
0x180026ff9  mov     edx, 2Eh ; '.'; Ch
0x180026ffe  lea     rcx, [rsi+2]; Str
0x180027002  mov     r15d, eax
0x180027005  call    cs:__imp_wcschr
0x18002700b  mov     rbx, rax
0x18002700e  test    rax, rax
0x180027011  jz      short loc_18002706B
0x180027013  xor     eax, eax
0x180027015  lea     rcx, [rsi+2]; String
0x180027019  mov     [rbx], ax
0x18002701c  call    cs:__imp__wtoi
0x180027022  mov     edx, 2Eh ; '.'; Ch
0x180027027  lea     rcx, [rbx+2]; Str
0x18002702b  mov     ebp, eax
0x18002702d  call    cs:__imp_wcschr
0x180027033  mov     rsi, rax
0x180027036  test    rax, rax
0x180027039  jz      short loc_18002706B
0x18002703b  xor     eax, eax
0x18002703d  lea     rcx, [rbx+2]; String
0x180027041  mov     [rsi], ax
0x180027044  call    cs:__imp__wtoi
0x18002704a  mov     ebx, eax
0x18002704c  lea     rcx, [rsi+2]; String
0x180027050  shl     ebx, 8
0x180027053  or      ebx, ebp
0x180027055  shl     ebx, 8
0x180027058  or      ebx, r15d
0x18002705b  call    cs:__imp__wtoi
0x180027061  shl     eax, 18h
0x180027064  or      eax, ebx
0x180027066  mov     [r14], eax
0x180027069  jmp     short loc_180027070
0x18002706b  mov     edi, 80070057h
0x180027070  lea     rcx, [rsp+88h+var_68]
0x180027075  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002707b  mov     eax, edi
0x18002707d  mov     rcx, [rsp+88h+var_30]
0x180027082  xor     rcx, rsp; StackCookie
0x180027085  call    __security_check_cookie
0x18002708a  mov     rbx, [rsp+88h+arg_10]
0x180027092  add     rsp, 60h
0x180027096  pop     r15
0x180027098  pop     r14
0x18002709a  pop     rdi
0x18002709b  pop     rsi
0x18002709c  pop     rbp
0x18002709d  retn
```

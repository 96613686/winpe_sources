# CDfsShell::~CDfsShell(void)

- ea: `0x180002b10`
- end: `0x180002bd2`
- name: `??1CDfsShell@@QEAA@XZ`
- size: `194`
- prototype: `void __fastcall(CDfsShell *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002c90`
- `0x180002d50`

## callees

- `0x180002b10`
- `0x1800082c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002b62`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002b62`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002b7b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002b95`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002bac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002b7b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002b95`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002bac`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b46`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b59`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b46`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180002b59`

## pseudocode

```c
void __fastcall CDfsShell::~CDfsShell(CDfsShell *this)
{
  _QWORD *v2; // rcx
  int v3; // edi
  BSTR *v4; // rsi
  void *v5; // rcx
  void *v6; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 39);
  if ( v2 )
  {
    if ( *v2 )
    {
      v3 = 0;
      do
      {
        v4 = (BSTR *)v2[v3];
        if ( v4 )
        {
          SysFreeString(v4[2]);
          SysFreeString(v4[1]);
          SysFreeString(*v4);
          operator delete(v4);
        }
        v2 = (_QWORD *)*((_QWORD *)this + 39);
        ++v3;
      }
      while ( v2[v3] );
    }
    operator delete[](v2);
    *((_QWORD *)this + 39) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    operator delete[](v5);
    *((_QWORD *)this + 4) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    operator delete[](v6);
    *((_QWORD *)this + 3) = 0;
  }
  CDfsShellExtProp::~CDfsShellExtProp((CDfsShell *)((char *)this + 40));
}

```

## disassembly

```asm
0x180002b10  mov     [rsp+arg_0], rbx
0x180002b15  mov     [rsp+arg_8], rsi
0x180002b1a  push    rdi
0x180002b1b  sub     rsp, 20h
0x180002b1f  mov     rbx, rcx
0x180002b22  mov     rcx, [rcx+138h]
0x180002b29  test    rcx, rcx
0x180002b2c  jz      short loc_180002B8C
0x180002b2e  cmp     qword ptr [rcx], 0
0x180002b32  jz      short loc_180002B7B
0x180002b34  xor     edi, edi
0x180002b36  movsxd  rax, edi
0x180002b39  mov     rsi, [rcx+rax*8]
0x180002b3d  test    rsi, rsi
0x180002b40  jz      short loc_180002B68
0x180002b42  mov     rcx, [rsi+10h]; bstrString
0x180002b46  call    cs:__imp_SysFreeString
0x180002b4c  mov     rcx, [rsi+8]; bstrString
0x180002b50  call    cs:__imp_SysFreeString
0x180002b56  mov     rcx, [rsi]; bstrString
0x180002b59  call    cs:__imp_SysFreeString
0x180002b5f  mov     rcx, rsi
0x180002b62  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002b68  mov     rcx, [rbx+138h]
0x180002b6f  inc     edi
0x180002b71  movsxd  rax, edi
0x180002b74  cmp     qword ptr [rcx+rax*8], 0
0x180002b79  jnz     short loc_180002B36
0x180002b7b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002b81  mov     qword ptr [rbx+138h], 0
0x180002b8c  mov     rcx, [rbx+20h]
0x180002b90  test    rcx, rcx
0x180002b93  jz      short loc_180002BA3
0x180002b95  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002b9b  mov     qword ptr [rbx+20h], 0
0x180002ba3  mov     rcx, [rbx+18h]
0x180002ba7  test    rcx, rcx
0x180002baa  jz      short loc_180002BBA
0x180002bac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002bb2  mov     qword ptr [rbx+18h], 0
0x180002bba  lea     rcx, [rbx+28h]; this
0x180002bbe  mov     rbx, [rsp+28h+arg_0]
0x180002bc3  mov     rsi, [rsp+28h+arg_8]
0x180002bc8  add     rsp, 20h
0x180002bcc  pop     rdi
0x180002bcd  jmp     ??1CDfsShellExtProp@@UEAA@XZ; CDfsShellExtProp::~CDfsShellExtProp(void)
```

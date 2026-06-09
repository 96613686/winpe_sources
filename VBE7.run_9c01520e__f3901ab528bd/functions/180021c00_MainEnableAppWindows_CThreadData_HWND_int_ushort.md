# MainEnableAppWindows(CThreadData *,HWND__ *,int,ushort)

- ea: `0x180021c00`
- end: `0x180021e32`
- name: `?MainEnableAppWindows@@YAXPEAVCThreadData@@PEAUHWND__@@HG@Z`
- size: `562`
- prototype: `void __fastcall(struct CThreadData *, HWND, int, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180058200`

## callees

- `0x180021c00`
- `0x180022c48`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x180021ded`
- `MSVCR100!free` at `0x180021ded`
- `MSVCR100!malloc` at `0x180021d35`
- `MSVCR100!malloc` at `0x180021d35`
- `MSVCR100!realloc` at `0x180021d94`
- `MSVCR100!realloc` at `0x180021d94`
- `MSVCR100!_msize` at `0x180021d69`
- `MSVCR100!_msize` at `0x180021d69`
- `KERNEL32!lstrcmpA` at `0x180021cd7`
- `KERNEL32!lstrcmpA` at `0x180021cd7`
- `KERNEL32!RaiseException` at `0x180021d88`
- `KERNEL32!RaiseException` at `0x180021d88`
- `KERNEL32!GetCurrentThreadId` at `0x180021c39`
- `KERNEL32!GetCurrentThreadId` at `0x180021c39`
- `USER32!GetClassNameA` at `0x180021cc5`
- `USER32!GetClassNameA` at `0x180021cc5`
- `USER32!GetDesktopWindow` at `0x180021c97`
- `USER32!GetDesktopWindow` at `0x180021c97`
- `USER32!GetParent` at `0x180021c7d`
- `USER32!GetParent` at `0x180021c7d`
- `USER32!GetWindow` at `0x180021ca5`
- `USER32!GetWindow` at `0x180021ca5`
- `USER32!GetWindowLongA` at `0x180021c8b`
- `USER32!GetWindowLongA` at `0x180021d0a`
- `USER32!GetWindowLongA` at `0x180021c8b`
- `USER32!GetWindowLongA` at `0x180021d0a`
- `USER32!GetWindowThreadProcessId` at `0x180021cf3`
- `USER32!GetWindowThreadProcessId` at `0x180021cf3`

## pseudocode

```c
void __fastcall MainEnableAppWindows(struct CThreadData *a1, HWND Parent, int a3, __int16 a4)
{
  unsigned __int16 v7; // si
  DWORD CurrentThreadId; // r14d
  __int16 v9; // bp
  int v10; // r13d
  HWND i; // rcx
  HWND DesktopWindow; // rax
  UINT v13; // edx
  HWND j; // rcx
  HWND Window; // rdi
  void *v16; // rax
  void *v17; // r14
  const ULONG_PTR *v18; // rax
  void *v19; // rax
  DWORD v20; // [rsp+24h] [rbp-94h]
  CHAR ClassName[64]; // [rsp+30h] [rbp-88h] BYREF

  v7 = a4 | 4;
  CurrentThreadId = GetCurrentThreadId();
  v20 = CurrentThreadId;
  v9 = v7 & 8;
  v10 = 10;
  *((_DWORD *)a1 + 438) = 1;
  if ( (v7 & 8) != 0 )
    *((_DWORD *)a1 + 439) = 0;
  for ( i = Parent; (GetWindowLongA(i, -16) & 0x40000000) != 0; i = Parent )
    Parent = GetParent(Parent);
  DesktopWindow = GetDesktopWindow();
  v13 = 5;
  for ( j = DesktopWindow; ; j = Window )
  {
    Window = GetWindow(j, v13);
    if ( !Window )
      break;
    GetClassNameA(Window, ClassName, 64);
    if ( lstrcmpA(ClassName, "ThunderRT6Main")
      && Window != Parent
      && GetWindowThreadProcessId(Window, 0) == CurrentThreadId
      && (GetWindowLongA(Window, -16) & 0x40000000) == 0 )
    {
      if ( v9 )
      {
        if ( !*((_QWORD *)a1 + 218) )
        {
          v16 = malloc(8LL * v10);
          *((_QWORD *)a1 + 218) = v16;
          if ( !v16 )
            goto LABEL_24;
        }
        if ( *((_DWORD *)a1 + 439) >= v10 )
        {
          v17 = (void *)*((_QWORD *)a1 + 218);
          v10 += 10;
          v18 = (const ULONG_PTR *)_msize(v17);
          if ( (const ULONG_PTR *)(unsigned int)v18 != v18 )
            RaiseException(0xC0000095, 1u, 1u, v18);
          v19 = realloc(v17, 8LL * v10);
          if ( !v19 )
          {
            free(*((void **)a1 + 218));
LABEL_24:
            MainEnableOneWindow(Window, a3, v7);
            break;
          }
          v9 = v7 & 8;
          CurrentThreadId = v20;
          *((_QWORD *)a1 + 218) = v19;
        }
        *(_QWORD *)(*((_QWORD *)a1 + 218) + 8LL * (int)(*((_DWORD *)a1 + 439))++) = Window;
      }
      else
      {
        MainEnableOneWindow(Window, a3, v7);
      }
    }
    v13 = 2;
  }
  *((_DWORD *)a1 + 438) = 0;
}

```

## disassembly

```asm
0x180021c00  mov     [rsp+arg_18], rbx
0x180021c05  push    rbp
0x180021c06  push    rsi
0x180021c07  push    rdi
0x180021c08  push    r12
0x180021c0a  push    r13
0x180021c0c  push    r14
0x180021c0e  push    r15
0x180021c10  mov     eax, 80h
0x180021c15  call    _alloca_probe
0x180021c1a  sub     rsp, rax
0x180021c1d  mov     rax, cs:__security_cookie
0x180021c24  xor     rax, rsp
0x180021c27  mov     [rsp+0B8h+var_48], rax
0x180021c2c  movzx   esi, r9w
0x180021c30  mov     r15d, r8d
0x180021c33  mov     r12, rdx
0x180021c36  mov     rbx, rcx
0x180021c39  call    cs:__imp_GetCurrentThreadId
0x180021c3f  or      si, 4
0x180021c43  movzx   ebp, si
0x180021c46  mov     r14d, eax
0x180021c49  mov     [rsp+0B8h+var_94], eax
0x180021c4d  xor     eax, eax
0x180021c4f  and     bp, 8
0x180021c53  mov     r13d, 0Ah
0x180021c59  mov     [rsp+0B8h+var_98], bp
0x180021c5e  mov     dword ptr [rbx+6D8h], 1
0x180021c68  jz      short loc_180021C70
0x180021c6a  mov     [rbx+6DCh], eax
0x180021c70  mov     edi, 0FFFFFFF0h
0x180021c75  mov     rcx, r12
0x180021c78  jmp     short loc_180021C89
0x180021c7a  mov     rcx, r12; hWnd
0x180021c7d  call    cs:__imp_GetParent
0x180021c83  mov     r12, rax
0x180021c86  mov     rcx, rax; hWnd
0x180021c89  mov     edx, edi; nIndex
0x180021c8b  call    cs:__imp_GetWindowLongA
0x180021c91  bt      eax, 1Eh
0x180021c95  jb      short loc_180021C7A
0x180021c97  call    cs:__imp_GetDesktopWindow
0x180021c9d  mov     edx, 5; uCmd
0x180021ca2  mov     rcx, rax; hWnd
0x180021ca5  call    cs:__imp_GetWindow
0x180021cab  mov     rdi, rax
0x180021cae  xor     eax, eax
0x180021cb0  test    rdi, rdi
0x180021cb3  jz      loc_180021E04
0x180021cb9  lea     r8d, [rax+40h]; nMaxCount
0x180021cbd  lea     rdx, [rsp+0B8h+ClassName]; lpClassName
0x180021cc2  mov     rcx, rdi; hWnd
0x180021cc5  call    cs:__imp_GetClassNameA
0x180021ccb  lea     rdx, aThunderrt6main; "ThunderRT6Main"
0x180021cd2  lea     rcx, [rsp+0B8h+ClassName]; lpString1
0x180021cd7  call    cs:__imp_lstrcmpA
0x180021cdd  test    eax, eax
0x180021cdf  jz      loc_180021DD9
0x180021ce5  cmp     rdi, r12
0x180021ce8  jz      loc_180021DD9
0x180021cee  xor     edx, edx; lpdwProcessId
0x180021cf0  mov     rcx, rdi; hWnd
0x180021cf3  call    cs:__imp_GetWindowThreadProcessId
0x180021cf9  cmp     eax, r14d
0x180021cfc  jnz     loc_180021DD9
0x180021d02  mov     edx, 0FFFFFFF0h; nIndex
0x180021d07  mov     rcx, rdi; hWnd
0x180021d0a  call    cs:__imp_GetWindowLongA
0x180021d10  bt      eax, 1Eh
0x180021d14  jb      loc_180021DD9
0x180021d1a  xor     eax, eax
0x180021d1c  test    bp, bp
0x180021d1f  jz      loc_180021DCA
0x180021d25  cmp     [rbx+6D0h], rax
0x180021d2c  jnz     short loc_180021D4B
0x180021d2e  movsxd  rcx, r13d
0x180021d31  shl     rcx, 3; Size
0x180021d35  call    cs:__imp_malloc
0x180021d3b  mov     [rbx+6D0h], rax
0x180021d42  test    rax, rax
0x180021d45  jz      loc_180021DF3
0x180021d4b  cmp     [rbx+6DCh], r13d
0x180021d52  jl      short loc_180021DB0
0x180021d54  mov     r14, [rbx+6D0h]
0x180021d5b  add     r13d, 0Ah
0x180021d5f  movsxd  rbp, r13d
0x180021d62  mov     rcx, r14; Block
0x180021d65  shl     rbp, 3
0x180021d69  call    cs:__imp__msize
0x180021d6f  mov     edx, eax
0x180021d71  cmp     rdx, rax
0x180021d74  jz      short loc_180021D8E
0x180021d76  mov     r9, rax; lpArguments
0x180021d79  mov     eax, 1
0x180021d7e  mov     ecx, 0C0000095h; dwExceptionCode
0x180021d83  mov     r8d, eax; nNumberOfArguments
0x180021d86  mov     edx, eax; dwExceptionFlags
0x180021d88  call    cs:__imp_RaiseException
0x180021d8e  mov     rdx, rbp; Size
0x180021d91  mov     rcx, r14; Block
0x180021d94  call    cs:__imp_realloc
0x180021d9a  test    rax, rax
0x180021d9d  jz      short loc_180021DE6
0x180021d9f  movzx   ebp, [rsp+0B8h+var_98]
0x180021da4  mov     r14d, [rsp+0B8h+var_94]
0x180021da9  mov     [rbx+6D0h], rax
0x180021db0  movsxd  rcx, dword ptr [rbx+6DCh]
0x180021db7  mov     rax, [rbx+6D0h]
0x180021dbe  mov     [rax+rcx*8], rdi
0x180021dc2  inc     dword ptr [rbx+6DCh]
0x180021dc8  jmp     short loc_180021DD9
0x180021dca  movzx   r8d, si; unsigned __int16
0x180021dce  mov     edx, r15d; int
0x180021dd1  mov     rcx, rdi; HWND
0x180021dd4  call    ?MainEnableOneWindow@@YAXPEAUHWND__@@HG@Z; MainEnableOneWindow(HWND__ *,int,ushort)
0x180021dd9  mov     edx, 2
0x180021dde  mov     rcx, rdi
0x180021de1  jmp     loc_180021CA5
0x180021de6  mov     rcx, [rbx+6D0h]; Block
0x180021ded  call    cs:__imp_free
0x180021df3  movzx   r8d, si; unsigned __int16
0x180021df7  mov     edx, r15d; int
0x180021dfa  mov     rcx, rdi; HWND
0x180021dfd  call    ?MainEnableOneWindow@@YAXPEAUHWND__@@HG@Z; MainEnableOneWindow(HWND__ *,int,ushort)
0x180021e02  xor     eax, eax
0x180021e04  mov     [rbx+6D8h], eax
0x180021e0a  mov     rcx, [rsp+0B8h+var_48]
0x180021e0f  xor     rcx, rsp; StackCookie
0x180021e12  call    __security_check_cookie
0x180021e17  mov     rbx, [rsp+0B8h+arg_18]
0x180021e1f  add     rsp, 80h
0x180021e26  pop     r15
0x180021e28  pop     r14
0x180021e2a  pop     r13
0x180021e2c  pop     r12
0x180021e2e  pop     rdi
0x180021e2f  pop     rsi
0x180021e30  pop     rbp
0x180021e31  retn
```

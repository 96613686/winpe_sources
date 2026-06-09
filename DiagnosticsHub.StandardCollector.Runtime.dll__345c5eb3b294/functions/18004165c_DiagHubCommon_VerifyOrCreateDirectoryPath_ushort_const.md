# DiagHubCommon::VerifyOrCreateDirectoryPath(ushort const *)

- ea: `0x18004165c`
- end: `0x180041832`
- name: `?VerifyOrCreateDirectoryPath@DiagHubCommon@@YAJPEBG@Z`
- size: `470`
- prototype: `__int64 __fastcall(DiagHubCommon *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003ba48`
- `0x18003c40c`

## callees

- `0x180002604`
- `0x180041618`
- `0x18004165c`
- `0x180049b50`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180041799`
- `KERNEL32!CreateDirectoryW` at `0x180041799`
- `KERNEL32!GetDriveTypeW` at `0x180041718`
- `KERNEL32!GetDriveTypeW` at `0x180041718`
- `KERNEL32!GetFileAttributesW` at `0x18004169c`
- `KERNEL32!GetFileAttributesW` at `0x18004169c`
- `KERNEL32!GetLastError` at `0x1800417a3`
- `KERNEL32!GetLastError` at `0x1800417a3`
- `USER32!IsCharAlphaW` at `0x1800416ec`
- `USER32!IsCharAlphaW` at `0x1800416ec`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004172f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004172f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800417e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800417e1`

## pseudocode

```c
__int64 __fastcall DiagHubCommon::VerifyOrCreateDirectoryPath(DiagHubCommon *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdx
  __int64 v5; // r14
  __int64 v6; // rdi
  WCHAR v7; // ax
  WCHAR *v8; // rbx
  __int64 v9; // r12
  WCHAR v10; // r15
  signed int LastError; // eax
  signed int Directory; // r14d
  WCHAR RootPathName; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+22h] [rbp-36h]

  if ( !this )
    return 2147942487LL;
  if ( GetFileAttributesW((LPCWSTR)this) != -1 )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)this + v5) );
  if ( (int)v5 > 6 )
  {
    v6 = 1;
    if ( *(_WORD *)this == 92
      && *((_WORD *)this + 1) == 92
      && *((_WORD *)this + 2) == 63
      && *((_WORD *)this + 3) == 92
      && IsCharAlphaW(*((_WORD *)this + 4))
      && *((_WORD *)this + 5) == 58
      && *((_WORD *)this + 6) == 92 )
    {
      v7 = *((_WORD *)this + 4);
      v14 = 58;
      RootPathName = v7;
      if ( GetDriveTypeW(&RootPathName) < 2 )
        return 2147942403LL;
      v6 = 7;
    }
    goto LABEL_17;
  }
  if ( (int)v5 < 0 )
    ATL::AtlThrowImpl(-2147024809);
  v6 = 1;
  if ( (_DWORD)v5 )
  {
LABEL_17:
    _mm_lfence();
    v8 = SysAllocStringLen((const OLECHAR *)this, v5);
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    goto LABEL_23;
  }
  v8 = 0;
LABEL_23:
  _mm_lfence();
  v9 = (int)v5;
  if ( v6 >= (int)v5 )
  {
LABEL_35:
    Directory = DiagHubCommon::VerifyOrCreateDirectory(this, v4);
    goto LABEL_36;
  }
  _mm_lfence();
  while ( 1 )
  {
    v10 = v8[v6];
    if ( v10 != 92 && v10 != 47 )
      goto LABEL_34;
    v8[v6] = 0;
    if ( !v8 )
      break;
    if ( !CreateDirectoryW(v8, 0) )
    {
      LastError = GetLastError();
      if ( LastError != 183 )
      {
        Directory = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          Directory = LastError;
        if ( Directory < 0 )
          goto LABEL_36;
      }
    }
    v8[v6] = v10;
LABEL_34:
    if ( ++v6 >= v9 )
      goto LABEL_35;
  }
  Directory = -2147024809;
LABEL_36:
  SysFreeString(v8);
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x18004165c  mov     [rsp+arg_8], rbx
0x180041661  mov     [rsp+arg_10], rbp
0x180041666  mov     [rsp+arg_18], rsi
0x18004166b  push    rdi
0x18004166c  push    r12
0x18004166e  push    r13
0x180041670  push    r14
0x180041672  push    r15
0x180041674  sub     rsp, 30h
0x180041678  mov     rax, cs:__security_cookie
0x18004167f  xor     rax, rsp
0x180041682  mov     [rsp+58h+var_30], rax
0x180041687  xor     r13d, r13d
0x18004168a  mov     rsi, rcx
0x18004168d  test    rcx, rcx
0x180041690  jnz     short loc_18004169C
0x180041692  mov     eax, 80070057h
0x180041697  jmp     loc_1800417EA
0x18004169c  call    cs:__imp_GetFileAttributesW
0x1800416a2  cmp     eax, 0FFFFFFFFh
0x1800416a5  jz      short loc_1800416AE
0x1800416a7  xor     eax, eax
0x1800416a9  jmp     loc_1800417EA
0x1800416ae  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800416b2  inc     r14
0x1800416b5  cmp     [rsi+r14*2], r13w
0x1800416ba  jnz     short loc_1800416B2
0x1800416bc  cmp     r14d, 6
0x1800416c0  jle     loc_18004174D
0x1800416c6  cmp     word ptr [rsi], 5Ch ; '\'
0x1800416ca  mov     ebp, 1
0x1800416cf  mov     edi, ebp
0x1800416d1  jnz     short loc_180041726
0x1800416d3  cmp     word ptr [rsi+2], 5Ch ; '\'
0x1800416d8  jnz     short loc_180041726
0x1800416da  cmp     word ptr [rsi+4], 3Fh ; '?'
0x1800416df  jnz     short loc_180041726
0x1800416e1  cmp     word ptr [rsi+6], 5Ch ; '\'
0x1800416e6  jnz     short loc_180041726
0x1800416e8  movzx   ecx, word ptr [rsi+8]; ch
0x1800416ec  call    cs:__imp_IsCharAlphaW
0x1800416f2  test    eax, eax
0x1800416f4  jz      short loc_180041726
0x1800416f6  lea     ecx, [rbp+39h]
0x1800416f9  cmp     [rsi+0Ah], cx
0x1800416fd  jnz     short loc_180041726
0x1800416ff  cmp     word ptr [rsi+0Ch], 5Ch ; '\'
0x180041704  jnz     short loc_180041726
0x180041706  movzx   eax, word ptr [rsi+8]
0x18004170a  mov     [rsp+58h+var_36], ecx
0x18004170e  lea     rcx, [rsp+58h+RootPathName]; lpRootPathName
0x180041713  mov     [rsp+58h+RootPathName], ax
0x180041718  call    cs:__imp_GetDriveTypeW
0x18004171e  cmp     eax, 2
0x180041721  jb      short loc_180041743
0x180041723  lea     edi, [rbp+6]
0x180041726  lfence
0x180041729  mov     edx, r14d; ui
0x18004172c  mov     rcx, rsi; strIn
0x18004172f  call    cs:__imp_SysAllocStringLen
0x180041735  mov     rbx, rax
0x180041738  test    rax, rax
0x18004173b  jz      loc_180041827
0x180041741  jmp     short loc_180041765
0x180041743  mov     eax, 80070003h
0x180041748  jmp     loc_1800417EA
0x18004174d  test    r14d, r14d
0x180041750  js      loc_18004181C
0x180041756  mov     ebp, 1
0x18004175b  mov     edi, ebp
0x18004175d  test    r14d, r14d
0x180041760  jnz     short loc_180041726
0x180041762  mov     rbx, r13
0x180041765  lfence
0x180041768  movsxd  r12, r14d
0x18004176b  cmp     rdi, r12
0x18004176e  jge     short loc_1800417D3
0x180041770  lfence
0x180041773  movzx   r15d, word ptr [rbx+rdi*2]
0x180041778  cmp     r15w, 5Ch ; '\'
0x18004177d  jz      short loc_180041786
0x18004177f  cmp     r15w, 2Fh ; '/'
0x180041784  jnz     short loc_1800417CB
0x180041786  mov     [rbx+rdi*2], r13w
0x18004178b  test    rbx, rbx
0x18004178e  jz      loc_180041814
0x180041794  xor     edx, edx; lpSecurityAttributes
0x180041796  mov     rcx, rbx; lpPathName
0x180041799  call    cs:__imp_CreateDirectoryW
0x18004179f  test    eax, eax
0x1800417a1  jnz     short loc_1800417C6
0x1800417a3  call    cs:__imp_GetLastError
0x1800417a9  cmp     eax, 0B7h
0x1800417ae  jz      short loc_1800417C6
0x1800417b0  movzx   r14d, ax
0x1800417b4  or      r14d, 80070000h
0x1800417bb  test    eax, eax
0x1800417bd  cmovle  r14d, eax
0x1800417c1  test    r14d, r14d
0x1800417c4  js      short loc_1800417DE
0x1800417c6  mov     [rbx+rdi*2], r15w
0x1800417cb  add     rdi, rbp
0x1800417ce  cmp     rdi, r12
0x1800417d1  jl      short loc_180041773
0x1800417d3  mov     rcx, rsi; this
0x1800417d6  call    ?VerifyOrCreateDirectory@DiagHubCommon@@YAJPEBG@Z; DiagHubCommon::VerifyOrCreateDirectory(ushort const *)
0x1800417db  mov     r14d, eax
0x1800417de  mov     rcx, rbx; bstrString
0x1800417e1  call    cs:__imp_SysFreeString
0x1800417e7  mov     eax, r14d
0x1800417ea  mov     rcx, [rsp+58h+var_30]
0x1800417ef  xor     rcx, rsp; StackCookie
0x1800417f2  call    __security_check_cookie
0x1800417f7  mov     rbx, [rsp+58h+arg_8]
0x1800417fc  mov     rbp, [rsp+58h+arg_10]
0x180041801  mov     rsi, [rsp+58h+arg_18]
0x180041806  add     rsp, 30h
0x18004180a  pop     r15
0x18004180c  pop     r14
0x18004180e  pop     r13
0x180041810  pop     r12
0x180041812  pop     rdi
0x180041813  retn
0x180041814  mov     r14d, 80070057h
0x18004181a  jmp     short loc_1800417DE
0x18004181c  mov     ecx, 80070057h; int
0x180041821  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180041827  mov     ecx, 8007000Eh; int
0x18004182c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

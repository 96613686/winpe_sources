# wil::init_once_nothrow__lambda_d61325500fdac13b057b26824d96c668___

- ea: `0x1800556d4`
- end: `0x18005577c`
- name: `wil::init_once_nothrow__lambda_d61325500fdac13b057b26824d96c668___`
- size: `168`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800604f0`

## callees

- `0x180011e84`
- `0x180011ea4`
- `0x1800556d4`
- `0x18005f838`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180055757`
- `KERNEL32!InitOnceComplete` at `0x180055769`
- `KERNEL32!InitOnceComplete` at `0x180055757`
- `KERNEL32!InitOnceComplete` at `0x180055769`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800556fb`
- `KERNEL32!InitOnceBeginInitialize` at `0x1800556fb`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_d61325500fdac13b057b26824d96c668___(
        LPINIT_ONCE lpInitOnce,
        __int64 a2,
        __int64 a3)
{
  const char *v4; // r9
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF
  WINBOOL v11; // [rsp+40h] [rbp+18h] BYREF
  int v12; // [rsp+44h] [rbp+1Ch]

  v12 = HIDWORD(a3);
  v10 = a2;
  v11 = 0;
  if ( !InitOnceBeginInitialize(lpInitOnce, 0, &v11, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v4);
  if ( v11 )
  {
    v6 = lambda_d61325500fdac13b057b26824d96c668_::operator()(&v10);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v6, v8);
      InitOnceComplete(lpInitOnce, 4u, 0);
      return v7;
    }
    InitOnceComplete(lpInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800556d4  mov     rax, rsp
0x1800556d7  mov     [rax+8], rbx
0x1800556db  mov     [rax+18h], r8
0x1800556df  mov     [rax+10h], rdx
0x1800556e3  push    rdi; int
0x1800556e4  sub     rsp, 20h
0x1800556e8  mov     rdi, rcx
0x1800556eb  mov     dword ptr [rax+18h], 0
0x1800556f2  xor     r9d, r9d; lpContext
0x1800556f5  lea     r8, [rax+18h]; fPending
0x1800556f9  xor     edx, edx; dwFlags
0x1800556fb  call    cs:__imp_InitOnceBeginInitialize
0x180055701  test    eax, eax
0x180055703  jnz     short loc_18005571D
0x180055705  mov     rcx, [rsp+28h]; this
0x18005570a  lea     r8, aWil; "wil"
0x180055711  mov     edx, 37Ah; void *
0x180055716  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005571b  jmp     short loc_180055771
0x18005571d  cmp     [rsp+28h+arg_10], 0
0x180055722  jz      short loc_18005576F
0x180055724  lea     rcx, [rsp+28h+arg_8]
0x180055729  call    _lambda_d61325500fdac13b057b26824d96c668___operator__
0x18005572e  mov     ebx, eax
0x180055730  test    eax, eax
0x180055732  jns     short loc_180055761
0x180055734  mov     rcx, [rsp+28h]; this
0x180055739  mov     r9d, eax; char *
0x18005573c  lea     r8, aWil; "wil"
0x180055743  mov     edx, 37Fh; void *
0x180055748  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005574d  xor     r8d, r8d; lpContext
0x180055750  lea     edx, [r8+4]; dwFlags
0x180055754  mov     rcx, rdi; lpInitOnce
0x180055757  call    cs:__imp_InitOnceComplete
0x18005575d  mov     eax, ebx
0x18005575f  jmp     short loc_180055771
0x180055761  xor     r8d, r8d; lpContext
0x180055764  xor     edx, edx; dwFlags
0x180055766  mov     rcx, rdi; lpInitOnce
0x180055769  call    cs:__imp_InitOnceComplete
0x18005576f  xor     eax, eax
0x180055771  mov     rbx, [rsp+28h+arg_0]
0x180055776  add     rsp, 20h
0x18005577a  pop     rdi
0x18005577b  retn
```

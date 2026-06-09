# wil::init_once_nothrow__lambda_c7edcbd80f6eeb1c9246526a5db02147___

- ea: `0x180055624`
- end: `0x1800556cc`
- name: `wil::init_once_nothrow__lambda_c7edcbd80f6eeb1c9246526a5db02147___`
- size: `168`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180060020`

## callees

- `0x180011e84`
- `0x180011ea4`
- `0x180055624`
- `0x18005f23c`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1800556a7`
- `KERNEL32!InitOnceComplete` at `0x1800556b9`
- `KERNEL32!InitOnceComplete` at `0x1800556a7`
- `KERNEL32!InitOnceComplete` at `0x1800556b9`
- `KERNEL32!InitOnceBeginInitialize` at `0x18005564b`
- `KERNEL32!InitOnceBeginInitialize` at `0x18005564b`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow__lambda_c7edcbd80f6eeb1c9246526a5db02147___(
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
    v6 = lambda_c7edcbd80f6eeb1c9246526a5db02147_::operator()(&v10);
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
0x180055624  mov     rax, rsp
0x180055627  mov     [rax+8], rbx
0x18005562b  mov     [rax+18h], r8
0x18005562f  mov     [rax+10h], rdx
0x180055633  push    rdi; int
0x180055634  sub     rsp, 20h
0x180055638  mov     rdi, rcx
0x18005563b  mov     dword ptr [rax+18h], 0
0x180055642  xor     r9d, r9d; lpContext
0x180055645  lea     r8, [rax+18h]; fPending
0x180055649  xor     edx, edx; dwFlags
0x18005564b  call    cs:__imp_InitOnceBeginInitialize
0x180055651  test    eax, eax
0x180055653  jnz     short loc_18005566D
0x180055655  mov     rcx, [rsp+28h]; this
0x18005565a  lea     r8, aWil; "wil"
0x180055661  mov     edx, 37Ah; void *
0x180055666  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005566b  jmp     short loc_1800556C1
0x18005566d  cmp     [rsp+28h+arg_10], 0
0x180055672  jz      short loc_1800556BF
0x180055674  lea     rcx, [rsp+28h+arg_8]
0x180055679  call    _lambda_c7edcbd80f6eeb1c9246526a5db02147___operator__
0x18005567e  mov     ebx, eax
0x180055680  test    eax, eax
0x180055682  jns     short loc_1800556B1
0x180055684  mov     rcx, [rsp+28h]; this
0x180055689  mov     r9d, eax; char *
0x18005568c  lea     r8, aWil; "wil"
0x180055693  mov     edx, 37Fh; void *
0x180055698  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005569d  xor     r8d, r8d; lpContext
0x1800556a0  lea     edx, [r8+4]; dwFlags
0x1800556a4  mov     rcx, rdi; lpInitOnce
0x1800556a7  call    cs:__imp_InitOnceComplete
0x1800556ad  mov     eax, ebx
0x1800556af  jmp     short loc_1800556C1
0x1800556b1  xor     r8d, r8d; lpContext
0x1800556b4  xor     edx, edx; dwFlags
0x1800556b6  mov     rcx, rdi; lpInitOnce
0x1800556b9  call    cs:__imp_InitOnceComplete
0x1800556bf  xor     eax, eax
0x1800556c1  mov     rbx, [rsp+28h+arg_0]
0x1800556c6  add     rsp, 20h
0x1800556ca  pop     rdi
0x1800556cb  retn
```

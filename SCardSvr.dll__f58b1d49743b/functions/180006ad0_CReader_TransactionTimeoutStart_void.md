# CReader::TransactionTimeoutStart(void)

- ea: `0x180006ad0`
- end: `0x180006bff`
- name: `?TransactionTimeoutStart@CReader@@IEAAXXZ`
- size: `303`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180004730`
- `0x1800066c4`
- `0x180006700`
- `0x18000f770`
- `0x18000fc90`
- `0x18000fcf0`
- `0x18002fb6c`

## callees

- `0x180006ad0`
- `0x1800075d0`
- `0x18000d9c0`
- `0x180028b78`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006b85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReader::TransactionTimeoutStart(CReader *this)
{
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( !g_fDisableTransactionTimeoutDelay )
  {
    CReader::TransactionTimeoutStop(this);
    (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 30))((char *)this + 240, 0, 0);
    v2 = *((_QWORD *)this + 37);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 30) + 8LL))((char *)this + 240);
    WppTraceIndent(v3, 2);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
          WPP_pszIndent);
      }
      SetThreadpoolTimer(*((PTP_TIMER *)this + 89), (PFILETIME)this + 91, 0, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
  }
}

```

## disassembly

```asm
0x180006ad0  mov     [rsp+arg_0], rbx
0x180006ad5  mov     [rsp+arg_8], rsi
0x180006ada  push    rdi
0x180006adb  sub     rsp, 20h
0x180006adf  mov     rbx, rcx
0x180006ae2  cmp     cs:?g_fDisableTransactionTimeoutDelay@@3_NA, 0; bool g_fDisableTransactionTimeoutDelay
0x180006ae9  jz      short loc_180006AFB
0x180006aeb  mov     rbx, [rsp+28h+arg_0]
0x180006af0  mov     rsi, [rsp+28h+arg_8]
0x180006af5  add     rsp, 20h
0x180006af9  pop     rdi
0x180006afa  retn
0x180006afb  call    ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
0x180006b00  mov     rax, [rbx+0F0h]
0x180006b07  xor     r8d, r8d
0x180006b0a  xor     edx, edx
0x180006b0c  lea     rcx, [rbx+0F0h]
0x180006b13  mov     rax, [rax]
0x180006b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1b  mov     rdi, [rbx+128h]
0x180006b22  mov     rax, [rbx+0F0h]
0x180006b29  lea     rcx, [rbx+0F0h]
0x180006b30  mov     rax, [rax+8]
0x180006b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b39  nop
0x180006b3a  mov     edx, 2
0x180006b3f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006b44  test    rdi, rdi
0x180006b47  jz      short loc_180006B8C
0x180006b49  lea     rax, WPP_GLOBAL_Control
0x180006b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b57  cmp     rcx, rax
0x180006b5a  jz      short loc_180006B62
0x180006b5c  test    byte ptr [rcx+1Ch], 10h
0x180006b60  jnz     short loc_180006BD8
0x180006b62  lea     rdx, [rbx+2D8h]
0x180006b69  xor     r9d, r9d
0x180006b6c  xor     r8d, r8d
0x180006b6f  mov     rcx, [rbx+2C8h]
0x180006b76  mov     rbx, [rsp+28h+arg_0]
0x180006b7b  mov     rsi, [rsp+28h+arg_8]
0x180006b80  add     rsp, 20h
0x180006b84  pop     rdi
0x180006b85  jmp     cs:__imp_SetThreadpoolTimer
0x180006b8c  lea     rax, WPP_GLOBAL_Control
0x180006b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b9a  cmp     rcx, rax
0x180006b9d  jz      loc_180006AEB
0x180006ba3  test    byte ptr [rcx+1Ch], 10h
0x180006ba7  jz      loc_180006AEB
0x180006bad  cmp     byte ptr [rcx+19h], 4
0x180006bb1  jb      loc_180006AEB
0x180006bb7  mov     edx, 16h
0x180006bbc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006bc3  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180006bca  mov     rcx, [rcx+10h]
0x180006bce  call    WPP_SF_s
0x180006bd3  jmp     loc_180006AEB
0x180006bd8  cmp     byte ptr [rcx+19h], 4
0x180006bdc  jb      short loc_180006B62
0x180006bde  mov     edx, 15h
0x180006be3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006bea  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180006bf1  mov     rcx, [rcx+10h]
0x180006bf5  call    WPP_SF_s
0x180006bfa  jmp     loc_180006B62
```

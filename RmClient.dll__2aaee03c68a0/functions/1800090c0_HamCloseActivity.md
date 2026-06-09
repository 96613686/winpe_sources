# HamCloseActivity

- ea: `0x1800090c0`
- end: `0x1800092ca`
- name: `HamCloseActivity`
- size: `522`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800090c0`
- `0x1800095a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000926c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000927a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000926c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000927a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800091a8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009247`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800091a8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009247`
- `ntdll!RtlRbRemoveNode` at `0x180009216`
- `ntdll!RtlRbRemoveNode` at `0x180009216`
- `ntdll!TpPostWork` at `0x180009262`
- `ntdll!TpPostWork` at `0x180009262`
- `RPCRT4!NdrClientCall3` at `0x18000911d`
- `RPCRT4!NdrClientCall3` at `0x18000911d`
- `RPCRT4!RpcExceptionFilter` at `0x18001b20e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b20e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009133`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009133`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCloseActivity` at `0x18000916b`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCloseActivity` at `0x18000916b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamCloseActivity(__int64 a1, unsigned __int64 a2)
{
  CLIENT_CALL_RETURN result; // rax
  int v5; // edi
  unsigned __int64 v6; // rbx
  int v7; // eax
  unsigned __int64 v8; // rax
  _QWORD *v9; // rdx
  _QWORD *v10; // rbx
  __int64 v11; // rbx
  int v12; // eax
  _OWORD v13[6]; // [rsp+40h] [rbp-68h] BYREF

  memset(v13, 0, 64);
  if ( *(_QWORD *)(a1 + 8) )
    result.Simple = HampInProcCloseActivity();
  else
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, *(_QWORD *)a1, a2).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
  {
    memset((char *)&v13[1] + 4, 0, 44);
    v13[0] = a2;
    LODWORD(v13[1]) = 3;
    RtlAcquireSRWLockExclusive(a1 + 32);
    *(_DWORD *)(a1 + 40) = GetCurrentThreadId();
    v5 = *(_BYTE *)(a1 + 56) & 1;
    v6 = *(_QWORD *)(a1 + 48);
    if ( (*(_BYTE *)(a1 + 56) & 1) != 0 )
    {
      if ( v6 )
        v6 ^= a1 + 48;
      else
        v6 = 0;
    }
    if ( !v6 )
    {
LABEL_18:
      *(_DWORD *)(a1 + 40) = 0;
      RtlReleaseSRWLockExclusive(a1 + 32);
      return 0;
    }
    while ( 1 )
    {
      v7 = HampIpcChannelObjectComparePayloadForTree(v13, v6);
      if ( v7 < 0 )
      {
        v8 = *(_QWORD *)v6;
        if ( v5 && v8 )
          goto LABEL_26;
      }
      else
      {
        if ( v7 <= 0 )
          goto LABEL_13;
        v8 = *(_QWORD *)(v6 + 8);
        if ( v5 && v8 )
        {
LABEL_26:
          v6 ^= v8;
          goto LABEL_12;
        }
      }
      v6 = v8;
LABEL_12:
      if ( !v6 )
      {
LABEL_13:
        if ( v6 )
        {
          RtlRbRemoveNode(a1 + 48, v6);
          v9 = *(_QWORD **)(a1 + 72);
          if ( *v9 != a1 + 64 )
            __fastfail(3u);
          v10 = (_QWORD *)(v6 + 24);
          *v10 = a1 + 64;
          v10[1] = v9;
          *v9 = v10;
          *(_QWORD *)(a1 + 72) = v10;
          v11 = *(_QWORD *)(a1 + 24);
          RtlAcquireSRWLockExclusive(v11 + 32);
          *(_DWORD *)(v11 + 64) |= 2u;
          v12 = *(_DWORD *)(v11 + 64);
          if ( (v12 & 1) == 0 )
          {
            *(_DWORD *)(v11 + 64) = v12 | 1;
            TpPostWork(*(_QWORD *)(v11 + 56));
          }
          RtlReleaseSRWLockExclusive(v11 + 32);
        }
        goto LABEL_18;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800090c0  mov     rax, rsp
0x1800090c3  mov     [rax+20h], rbx
0x1800090c7  mov     [rax+10h], rdx
0x1800090cb  mov     [rax+8], rcx
0x1800090cf  push    rsi
0x1800090d0  push    rdi
0x1800090d1  push    r12
0x1800090d3  push    r14
0x1800090d5  push    r15
0x1800090d7  sub     rsp, 80h
0x1800090de  mov     rbx, rdx
0x1800090e1  mov     r14, rcx
0x1800090e4  xorps   xmm0, xmm0
0x1800090e7  movups  xmmword ptr [rax-68h], xmm0
0x1800090eb  movups  xmmword ptr [rax-58h], xmm0
0x1800090ef  movups  xmmword ptr [rax-48h], xmm0
0x1800090f3  movups  xmmword ptr [rax-38h], xmm0
0x1800090f7  mov     rcx, [rcx+8]
0x1800090fb  test    rcx, rcx
0x1800090fe  jnz     short loc_18000916B
0x180009100  xor     esi, esi
0x180009102  mov     [rax+18h], rsi
0x180009106  mov     [rsp+0A8h+var_88], rdx
0x18000910b  mov     r9, [r14]
0x18000910e  xor     r8d, r8d; pReturnValue
0x180009111  mov     edx, 0Fh; nProcNum
0x180009116  lea     rcx, pProxyInfo; pProxyInfo
0x18000911d  call    cs:__imp_NdrClientCall3
0x180009123  mov     [rsp+0A8h+arg_10], rax
0x18000912b  mov     [rsp+0A8h+var_78], eax
0x18000912f  jmp     short loc_18000914F
0x180009131  mov     ecx, eax; Status
0x180009133  call    cs:__imp_I_RpcMapWin32Status
0x180009139  mov     [rsp+0A8h+var_78], eax
0x18000913d  xor     esi, esi
0x18000913f  mov     rbx, [rsp+0A8h+arg_8]
0x180009147  mov     r14, [rsp+0A8h+arg_0]
0x18000914f  test    eax, eax
0x180009151  jns     short loc_180009175
0x180009153  mov     rbx, [rsp+0A8h+arg_18]
0x18000915b  add     rsp, 80h
0x180009162  pop     r15
0x180009164  pop     r14
0x180009166  pop     r12
0x180009168  pop     rdi
0x180009169  pop     rsi
0x18000916a  retn
0x18000916b  call    cs:__imp_HampInProcCloseActivity
0x180009171  xor     esi, esi
0x180009173  jmp     short loc_18000914F
0x180009175  mov     [rsp+0A8h+var_54], rsi
0x18000917a  mov     [rsp+0A8h+var_4C], rsi
0x18000917f  mov     [rsp+0A8h+var_44], rsi
0x180009184  mov     [rsp+0A8h+var_3C], rsi
0x180009189  mov     [rsp+0A8h+var_34], rsi
0x18000918e  mov     [rsp+0A8h+var_2C], esi
0x180009192  mov     [rsp+0A8h+var_68], rbx
0x180009197  mov     [rsp+0A8h+var_60], rsi
0x18000919c  mov     [rsp+0A8h+var_58], 3
0x1800091a4  lea     rcx, [r14+20h]
0x1800091a8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800091ae  call    cs:__imp_GetCurrentThreadId
0x1800091b4  mov     [r14+28h], eax
0x1800091b8  lea     r15, [r14+30h]
0x1800091bc  movzx   edi, byte ptr [r15+8]
0x1800091c1  and     edi, 1
0x1800091c4  mov     rbx, [r15]
0x1800091c7  test    byte ptr [r15+8], 1
0x1800091cc  jnz     loc_18000929D
0x1800091d2  test    rbx, rbx
0x1800091d5  jz      loc_180009272
0x1800091db  nop     dword ptr [rax+rax+00h]
0x1800091e0  mov     rdx, rbx
0x1800091e3  lea     rcx, [rsp+0A8h+var_68]
0x1800091e8  call    HampIpcChannelObjectComparePayloadForTree
0x1800091ed  test    eax, eax
0x1800091ef  js      loc_180009287
0x1800091f5  jle     short loc_18000920B
0x1800091f7  mov     rax, [rbx+8]
0x1800091fb  test    edi, edi
0x1800091fd  jnz     loc_1800092B2
0x180009203  mov     rbx, rax
0x180009206  test    rbx, rbx
0x180009209  jnz     short loc_1800091E0
0x18000920b  test    rbx, rbx
0x18000920e  jz      short loc_180009272
0x180009210  mov     rdx, rbx
0x180009213  mov     rcx, r15
0x180009216  call    cs:__imp_RtlRbRemoveNode
0x18000921c  lea     rax, [r14+40h]
0x180009220  mov     rdx, [rax+8]
0x180009224  cmp     [rdx], rax
0x180009227  jnz     loc_1800092C3
0x18000922d  add     rbx, 18h
0x180009231  mov     [rbx], rax
0x180009234  mov     [rbx+8], rdx
0x180009238  mov     [rdx], rbx
0x18000923b  mov     [rax+8], rbx
0x18000923f  mov     rbx, [r14+18h]
0x180009243  lea     rcx, [rbx+20h]
0x180009247  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000924d  or      dword ptr [rbx+40h], 2
0x180009251  mov     eax, [rbx+40h]
0x180009254  test    al, 1
0x180009256  jnz     short loc_180009268
0x180009258  or      eax, 1
0x18000925b  mov     [rbx+40h], eax
0x18000925e  mov     rcx, [rbx+38h]
0x180009262  call    cs:__imp_TpPostWork
0x180009268  lea     rcx, [rbx+20h]
0x18000926c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009272  mov     [r14+28h], esi
0x180009276  lea     rcx, [r14+20h]
0x18000927a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009280  mov     eax, esi
0x180009282  jmp     loc_180009153
0x180009287  mov     rax, [rbx]
0x18000928a  test    edi, edi
0x18000928c  jz      loc_180009203
0x180009292  test    rax, rax
0x180009295  jz      loc_180009203
0x18000929b  jmp     short loc_1800092BB
0x18000929d  test    rbx, rbx
0x1800092a0  jz      short loc_1800092AA
0x1800092a2  xor     rbx, r15
0x1800092a5  jmp     loc_1800091D2
0x1800092aa  mov     rbx, rsi
0x1800092ad  jmp     loc_1800091D2
0x1800092b2  test    rax, rax
0x1800092b5  jz      loc_180009203
0x1800092bb  xor     rbx, rax
0x1800092be  jmp     loc_180009206
0x1800092c3  mov     ecx, 3
0x1800092c8  int     29h; Win8: RtlFailFast(ecx)
0x18001b200  push    rbp
0x18001b202  sub     rsp, 30h
0x18001b206  mov     rbp, rdx
0x18001b209  mov     rcx, [rcx]
0x18001b20c  mov     ecx, [rcx]; ExceptionCode
0x18001b20e  call    cs:__imp_RpcExceptionFilter
0x18001b214  nop
0x18001b215  add     rsp, 30h
0x18001b219  pop     rbp
0x18001b21a  retn
```

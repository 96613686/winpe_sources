# MetaAdd(_INDEX_STRUCT *,NDX_OBJECT_TYPE,ushort const *,ushort const *,ushort const *,ushort const *,NDX_OBJREF *)

- ea: `0x180007ff0`
- end: `0x180008233`
- name: `?MetaAdd@@YAKPEAU_INDEX_STRUCT@@W4NDX_OBJECT_TYPE@@PEBG222PEAUNDX_OBJREF@@@Z`
- size: `579`
- prototype: `DWORD __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000913c`

## callees

- `0x180007ff0`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008095`
- `KERNEL32!GetLastError` at `0x1800080df`
- `KERNEL32!GetLastError` at `0x180008095`
- `KERNEL32!GetLastError` at `0x1800080df`
- `DEVRTL!NdxTableSetPropertyValue` at `0x1800080d3`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180008137`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180008158`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000819a`
- `DEVRTL!NdxTableSetPropertyValue` at `0x1800081d4`
- `DEVRTL!NdxTableSetPropertyValue` at `0x1800080d3`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180008137`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180008158`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000819a`
- `DEVRTL!NdxTableSetPropertyValue` at `0x1800081d4`
- `DEVRTL!NdxTableRemoveObject` at `0x1800080eb`
- `DEVRTL!NdxTableRemoveObject` at `0x1800080eb`
- `DEVRTL!NdxTableAddObject` at `0x180008089`
- `DEVRTL!NdxTableAddObject` at `0x180008089`

## pseudocode

```c
DWORD __fastcall MetaAdd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  unsigned int v9; // edi
  __int64 v11; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  DWORD LastError; // ebx
  __int64 v19; // rax
  unsigned __int64 v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned __int64 v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int128 v30; // xmm1
  __int64 v31; // xmm0_8
  int v32; // [rsp+20h] [rbp-48h] BYREF
  __int128 v33; // [rsp+28h] [rbp-40h] BYREF
  __int128 v34; // [rsp+38h] [rbp-30h]
  __int64 v35; // [rsp+48h] [rbp-20h]

  v35 = 0;
  v32 = 0;
  v9 = a2;
  v33 = 0;
  v34 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !(unsigned int)NdxTableAddObject(*(_QWORD *)(a1 + 40), v9, a3, &v33) )
    return GetLastError();
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a4 + 2 * v14) );
  v15 = 2 * v14 + 2;
  if ( v15 > 0xFFFFFFFF )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v11);
  if ( !(unsigned int)NdxTableSetPropertyValue(&v33, 0, a4, (unsigned int)v15) )
    goto LABEL_20;
  if ( a6 )
  {
    v32 = 1;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(a6 + 2 * v19) );
    v20 = 2 * v19 + 2;
    if ( v20 > 0xFFFFFFFF )
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16);
    if ( !(unsigned int)NdxTableSetPropertyValue(&v33, 2, a6, (unsigned int)v20) )
      goto LABEL_20;
  }
  else
  {
    v32 = 0;
  }
  if ( !(unsigned int)NdxTableSetPropertyValue(&v33, 1, &v32, 4) )
    goto LABEL_20;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(a3 + 2 * v23) );
  v24 = 2 * v23 + 2;
  if ( v24 > 0xFFFFFFFF )
    MicrosoftTelemetryAssertTriggeredNoArgs(v22, v21);
  if ( !(unsigned int)NdxTableSetPropertyValue(&v33, 6, a3, (unsigned int)v24) )
    goto LABEL_20;
  do
    ++v13;
  while ( *(_WORD *)(a5 + 2 * v13) );
  v27 = 2 * v13 + 2;
  if ( v27 > 0xFFFFFFFF )
    MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25);
  if ( !(unsigned int)NdxTableSetPropertyValue(&v33, 3, a5, (unsigned int)v27) )
  {
LABEL_20:
    LastError = GetLastError();
    NdxTableRemoveObject(&v33);
    return LastError;
  }
  v30 = v34;
  *(_OWORD *)a7 = v33;
  v31 = v35;
  *(_OWORD *)(a7 + 16) = v30;
  *(_QWORD *)(a7 + 32) = v31;
  if ( g_nPackages < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v29, v28);
  _InterlockedIncrement(&g_nPackages);
  return 0;
}

```

## disassembly

```asm
0x180007ff0  push    rbp
0x180007ff2  push    rbx
0x180007ff3  push    rsi
0x180007ff4  push    rdi
0x180007ff5  push    r12
0x180007ff7  push    r13
0x180007ff9  push    r14
0x180007ffb  push    r15
0x180007ffd  mov     rbp, rsp
0x180008000  sub     rsp, 68h
0x180008004  mov     rax, cs:__security_cookie
0x18000800b  xor     rax, rsp
0x18000800e  mov     [rbp+var_18], rax
0x180008012  mov     r13, [rbp+arg_20]
0x180008016  xor     eax, eax
0x180008018  mov     r12, [rbp+arg_28]
0x18000801c  xorps   xmm0, xmm0
0x18000801f  mov     r14, [rbp+arg_30]
0x180008023  mov     rsi, r9
0x180008026  mov     [rbp+var_20], rax
0x18000802a  mov     r15, r8
0x18000802d  mov     [rbp+var_48], eax
0x180008030  mov     edi, edx
0x180008032  mov     rbx, rcx
0x180008035  movups  [rbp+var_40], xmm0
0x180008039  movups  [rbp+var_30], xmm0
0x18000803d  test    rcx, rcx
0x180008040  jnz     short loc_180008047
0x180008042  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008047  cmp     dword ptr [rbx], 494E4445h
0x18000804d  jz      short loc_180008054
0x18000804f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008054  test    r15, r15
0x180008057  jnz     short loc_18000805E
0x180008059  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000805e  test    rsi, rsi
0x180008061  jnz     short loc_180008068
0x180008063  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008068  test    r14, r14
0x18000806b  jnz     short loc_180008072
0x18000806d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008072  test    r13, r13
0x180008075  jnz     short loc_18000807C
0x180008077  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000807c  mov     rcx, [rbx+28h]
0x180008080  lea     r9, [rbp+var_40]
0x180008084  mov     r8, r15
0x180008087  mov     edx, edi
0x180008089  call    cs:__imp_NdxTableAddObject
0x18000808f  xor     ecx, ecx
0x180008091  test    eax, eax
0x180008093  jnz     short loc_1800080A0
0x180008095  call    cs:__imp_GetLastError
0x18000809b  jmp     loc_180008216
0x1800080a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800080a4  mov     rax, rbx
0x1800080a7  inc     rax
0x1800080aa  cmp     [rsi+rax*2], cx
0x1800080ae  jnz     short loc_1800080A7
0x1800080b0  lea     rdi, ds:2[rax*2]
0x1800080b8  mov     eax, 0FFFFFFFFh
0x1800080bd  cmp     rdi, rax
0x1800080c0  jbe     short loc_1800080C7
0x1800080c2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800080c7  mov     r9d, edi
0x1800080ca  lea     rcx, [rbp+var_40]
0x1800080ce  mov     r8, rsi
0x1800080d1  xor     edx, edx
0x1800080d3  call    cs:__imp_NdxTableSetPropertyValue
0x1800080d9  xor     esi, esi
0x1800080db  test    eax, eax
0x1800080dd  jnz     short loc_1800080F8
0x1800080df  call    cs:__imp_GetLastError
0x1800080e5  lea     rcx, [rbp+var_40]
0x1800080e9  mov     ebx, eax
0x1800080eb  call    cs:__imp_NdxTableRemoveObject
0x1800080f1  mov     eax, ebx
0x1800080f3  jmp     loc_180008216
0x1800080f8  test    r12, r12
0x1800080fb  jz      short loc_180008143
0x1800080fd  mov     [rbp+var_48], 1
0x180008104  mov     rax, rbx
0x180008107  inc     rax
0x18000810a  cmp     [r12+rax*2], si
0x18000810f  jnz     short loc_180008107
0x180008111  lea     rdi, ds:2[rax*2]
0x180008119  mov     eax, 0FFFFFFFFh
0x18000811e  cmp     rdi, rax
0x180008121  jbe     short loc_180008128
0x180008123  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008128  mov     r9d, edi
0x18000812b  lea     rcx, [rbp+var_40]
0x18000812f  mov     r8, r12
0x180008132  mov     edx, 2
0x180008137  call    cs:__imp_NdxTableSetPropertyValue
0x18000813d  test    eax, eax
0x18000813f  jnz     short loc_180008146
0x180008141  jmp     short loc_1800080DF
0x180008143  mov     [rbp+var_48], esi
0x180008146  mov     r9d, 4
0x18000814c  lea     r8, [rbp+var_48]
0x180008150  lea     rcx, [rbp+var_40]
0x180008154  lea     edx, [r9-3]
0x180008158  call    cs:__imp_NdxTableSetPropertyValue
0x18000815e  test    eax, eax
0x180008160  jz      loc_1800080DF
0x180008166  mov     rax, rbx
0x180008169  inc     rax
0x18000816c  cmp     [r15+rax*2], si
0x180008171  jnz     short loc_180008169
0x180008173  lea     rdi, ds:2[rax*2]
0x18000817b  mov     r12d, 0FFFFFFFFh
0x180008181  cmp     rdi, r12
0x180008184  jbe     short loc_18000818B
0x180008186  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000818b  mov     r9d, edi
0x18000818e  lea     rcx, [rbp+var_40]
0x180008192  mov     r8, r15
0x180008195  mov     edx, 6
0x18000819a  call    cs:__imp_NdxTableSetPropertyValue
0x1800081a0  test    eax, eax
0x1800081a2  jz      loc_1800080DF
0x1800081a8  inc     rbx
0x1800081ab  cmp     [r13+rbx*2+0], si
0x1800081b1  jnz     short loc_1800081A8
0x1800081b3  lea     rbx, ds:2[rbx*2]
0x1800081bb  cmp     rbx, r12
0x1800081be  jbe     short loc_1800081C5
0x1800081c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800081c5  mov     r9d, ebx
0x1800081c8  lea     rcx, [rbp+var_40]
0x1800081cc  mov     r8, r13
0x1800081cf  mov     edx, 3
0x1800081d4  call    cs:__imp_NdxTableSetPropertyValue
0x1800081da  test    eax, eax
0x1800081dc  jz      loc_1800080DF
0x1800081e2  movups  xmm0, [rbp+var_40]
0x1800081e6  movups  xmm1, [rbp+var_30]
0x1800081ea  movups  xmmword ptr [r14], xmm0
0x1800081ee  movsd   xmm0, [rbp+var_20]
0x1800081f3  movups  xmmword ptr [r14+10h], xmm1
0x1800081f8  movsd   qword ptr [r14+20h], xmm0
0x1800081fe  mov     eax, cs:?g_nPackages@@3JC; long volatile g_nPackages
0x180008204  test    eax, eax
0x180008206  jns     short loc_18000820D
0x180008208  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000820d  lock inc cs:?g_nPackages@@3JC; long volatile g_nPackages
0x180008214  xor     eax, eax
0x180008216  mov     rcx, [rbp+var_18]
0x18000821a  xor     rcx, rsp; StackCookie
0x18000821d  call    __security_check_cookie
0x180008222  add     rsp, 68h
0x180008226  pop     r15
0x180008228  pop     r14
0x18000822a  pop     r13
0x18000822c  pop     r12
0x18000822e  pop     rdi
0x18000822f  pop     rsi
0x180008230  pop     rbx
0x180008231  pop     rbp
0x180008232  retn
```

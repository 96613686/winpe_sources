# FaxGetExtensionDataW

- ea: `0x180023070`
- end: `0x1800231f0`
- name: `FaxGetExtensionDataW`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022fb0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180023070`
- `0x18002c31c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023154`
- `RPCRT4!NdrClientCall3` at `0x180023154`
- `KERNEL32!SetLastError` at `0x1800231cd`
- `KERNEL32!SetLastError` at `0x1800231cd`

## pseudocode

```c
__int64 __fastcall FaxGetExtensionDataW(__int64 a1, int a2, const OLECHAR *a3, _QWORD *a4, __int64 a5)
{
  DWORD valid; // eax
  DWORD v10; // ecx
  unsigned int Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids);
  }
  if ( a3 && a4 && a5 )
  {
    if ( a1 && *(_DWORD *)a1 && !*(_DWORD *)(a1 + 16) )
    {
      valid = IsValidGUID(a3);
      if ( valid )
      {
        v10 = valid;
      }
      else
      {
        *a4 = 0;
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                  0x31u,
                                  0,
                                  **(_QWORD **)(a1 + 32),
                                  a2,
                                  a3,
                                  a4,
                                  a5).Pointer;
        if ( !Pointer )
          return 1;
        v10 = Pointer;
      }
    }
    else
    {
      v10 = 6;
    }
  }
  else
  {
    v10 = 87;
  }
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x180023070  mov     [rsp+arg_0], rbx
0x180023075  mov     [rsp+arg_8], rsi
0x18002307a  push    rdi
0x18002307b  push    r14
0x18002307d  push    r15
0x18002307f  sub     rsp, 50h
0x180023083  mov     rdi, r9
0x180023086  mov     rsi, r8
0x180023089  mov     r15d, edx
0x18002308c  mov     rbx, rcx
0x18002308f  lea     rax, WPP_GLOBAL_Control
0x180023096  mov     rcx, cs:WPP_GLOBAL_Control
0x18002309d  cmp     rcx, rax
0x1800230a0  jz      short loc_1800230C6
0x1800230a2  test    dword ptr [rcx+1Ch], 1000h
0x1800230a9  jz      short loc_1800230C6
0x1800230ab  cmp     byte ptr [rcx+19h], 5
0x1800230af  jb      short loc_1800230C6
0x1800230b1  mov     edx, 5Dh ; ']'
0x1800230b6  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x1800230bd  mov     rcx, [rcx+10h]
0x1800230c1  call    WPP_SF_
0x1800230c6  test    rsi, rsi
0x1800230c9  jz      loc_1800231C8
0x1800230cf  test    rdi, rdi
0x1800230d2  jz      loc_1800231C8
0x1800230d8  mov     r14, [rsp+68h+arg_20]
0x1800230e0  test    r14, r14
0x1800230e3  jz      loc_1800231C8
0x1800230e9  test    rbx, rbx
0x1800230ec  jz      loc_1800231C1
0x1800230f2  cmp     dword ptr [rbx], 0
0x1800230f5  jz      loc_1800231C1
0x1800230fb  cmp     dword ptr [rbx+10h], 0
0x1800230ff  jnz     loc_1800231C1
0x180023105  mov     rcx, rsi; lpsz
0x180023108  call    IsValidGUID
0x18002310d  test    eax, eax
0x18002310f  jz      short loc_180023118
0x180023111  mov     ecx, eax
0x180023113  jmp     loc_1800231CD
0x180023118  mov     qword ptr [rdi], 0
0x18002311f  mov     rax, [rbx+20h]
0x180023123  mov     [rsp+68h+arg_10], 0
0x18002312f  mov     [rsp+68h+var_30], r14
0x180023134  mov     [rsp+68h+var_38], rdi
0x180023139  mov     [rsp+68h+var_40], rsi
0x18002313e  mov     [rsp+68h+var_48], r15d
0x180023143  mov     r9, [rax]
0x180023146  xor     r8d, r8d; pReturnValue
0x180023149  lea     edx, [r8+31h]; nProcNum
0x18002314d  lea     rcx, pProxyInfo; pProxyInfo
0x180023154  call    cs:__imp_NdrClientCall3
0x18002315b  nop     dword ptr [rax+rax+00h]
0x180023160  mov     rbx, rax
0x180023163  mov     [rsp+68h+arg_10], rax
0x18002316b  mov     [rsp+68h+var_28], eax
0x18002316f  jmp     short loc_1800231B2
0x180023171  mov     ebx, eax
0x180023173  mov     [rsp+68h+var_28], eax
0x180023177  lea     rdx, WPP_GLOBAL_Control
0x18002317e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023185  cmp     rcx, rdx
0x180023188  jz      short loc_1800231B2
0x18002318a  test    dword ptr [rcx+1Ch], 1000h
0x180023191  jz      short loc_1800231B2
0x180023193  cmp     byte ptr [rcx+19h], 2
0x180023197  jb      short loc_1800231B2
0x180023199  mov     edx, 5Eh ; '^'
0x18002319e  mov     r9d, eax
0x1800231a1  lea     r8, WPP_04c6cf12b900389b5c43665f04f60bbb_Traceguids
0x1800231a8  mov     rcx, [rcx+10h]
0x1800231ac  call    WPP_SF_d
0x1800231b1  nop
0x1800231b2  test    ebx, ebx
0x1800231b4  jz      short loc_1800231BA
0x1800231b6  mov     ecx, ebx
0x1800231b8  jmp     short loc_1800231CD
0x1800231ba  mov     eax, 1
0x1800231bf  jmp     short loc_1800231DB
0x1800231c1  mov     ecx, 6
0x1800231c6  jmp     short loc_1800231CD
0x1800231c8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800231cd  call    cs:__imp_SetLastError
0x1800231d4  nop     dword ptr [rax+rax+00h]
0x1800231d9  xor     eax, eax
0x1800231db  mov     rbx, [rsp+68h+arg_0]
0x1800231e0  mov     rsi, [rsp+68h+arg_8]
0x1800231e5  add     rsp, 50h
0x1800231e9  pop     r15
0x1800231eb  pop     r14
0x1800231ed  pop     rdi
0x1800231ee  retn
```

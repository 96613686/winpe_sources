# I_ReaderMonitorThreadProc

- ea: `0x18001b8c0`
- end: `0x18001ba46`
- name: `I_ReaderMonitorThreadProc`
- size: `390`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001b8c0`
- `0x18001ba4c`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b965`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b96e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b965`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b96e`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorThreadProc(PVOID Parameter)
{
  unsigned int v1; // esi
  ULONGLONG TickCount64; // rdi
  int v3; // r14d
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  ULONGLONG v7; // rax

  v1 = 0;
  TickCount64 = 0;
  v3 = (int)Parameter;
  WppTraceIndent(Parameter, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  do
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          v4 = I_ReaderMonitorWorker(v3);
          v6 = v4;
          if ( v4 )
            break;
          WppTraceIndent(v5, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              235,
              &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent);
          }
        }
      }
      while ( v4 == -2146435054 || v4 == -2146435043 || v4 == -2146435042 );
      if ( !TickCount64 )
        TickCount64 = GetTickCount64();
      v7 = GetTickCount64();
      if ( v7 - TickCount64 <= 0x36EE80 )
        break;
      TickCount64 = v7;
      v1 = 1;
    }
    ++v1;
  }
  while ( v1 < 3 );
  WppTraceIndent(v7 - TickCount64, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      236,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18001b8c0  mov     rax, rsp
0x18001b8c3  mov     [rax+18h], rbx
0x18001b8c7  mov     [rax+20h], rsi
0x18001b8cb  push    rdi
0x18001b8cc  push    r12
0x18001b8ce  push    r14
0x18001b8d0  sub     rsp, 30h
0x18001b8d4  xor     esi, esi
0x18001b8d6  mov     dword ptr [rax+8], 1
0x18001b8dd  xor     edi, edi
0x18001b8df  mov     [rax+10h], esi
0x18001b8e2  xor     edx, edx
0x18001b8e4  mov     r14, rcx
0x18001b8e7  call    WppTraceIndent
0x18001b8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8f3  lea     r12, WPP_GLOBAL_Control
0x18001b8fa  cmp     rcx, r12
0x18001b8fd  jz      short loc_18001B927
0x18001b8ff  test    byte ptr [rcx+1Ch], 2
0x18001b903  jz      short loc_18001B927
0x18001b905  cmp     byte ptr [rcx+19h], 5
0x18001b909  jb      short loc_18001B927
0x18001b90b  mov     r9, cs:WPP_pszIndent
0x18001b912  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b919  mov     rcx, [rcx+10h]
0x18001b91d  mov     edx, 0EAh
0x18001b922  call    WPP_SF_s
0x18001b927  lea     r8, [rsp+48h+arg_8]
0x18001b92c  mov     rcx, r14; int
0x18001b92f  lea     rdx, [rsp+48h+arg_0]
0x18001b934  call    I_ReaderMonitorWorker
0x18001b939  mov     ebx, eax
0x18001b93b  test    eax, eax
0x18001b93d  jz      short loc_18001B996
0x18001b93f  cmp     eax, 80100012h
0x18001b944  jz      loc_18001B9E3
0x18001b94a  cmp     eax, 8010001Dh
0x18001b94f  jz      loc_18001B9E3
0x18001b955  cmp     eax, 8010001Eh
0x18001b95a  jz      loc_18001B9E3
0x18001b960  test    rdi, rdi
0x18001b963  jnz     short loc_18001B96E
0x18001b965  call    cs:__imp_GetTickCount64
0x18001b96b  mov     rdi, rax
0x18001b96e  call    cs:__imp_GetTickCount64
0x18001b974  mov     rcx, rax
0x18001b977  sub     rcx, rdi
0x18001b97a  cmp     rcx, 36EE80h
0x18001b981  jbe     short loc_18001B98D
0x18001b983  mov     rdi, rax
0x18001b986  mov     esi, 1
0x18001b98b  jmp     short loc_18001B9E3
0x18001b98d  inc     esi
0x18001b98f  cmp     esi, 3
0x18001b992  jnb     short loc_18001B9EE
0x18001b994  jmp     short loc_18001B9E3
0x18001b996  mov     edx, 2
0x18001b99b  call    WppTraceIndent
0x18001b9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9a7  cmp     rcx, r12
0x18001b9aa  jz      short loc_18001B9D4
0x18001b9ac  test    byte ptr [rcx+1Ch], 1
0x18001b9b0  jz      short loc_18001B9D4
0x18001b9b2  cmp     byte ptr [rcx+19h], 4
0x18001b9b6  jb      short loc_18001B9D4
0x18001b9b8  mov     r9, cs:WPP_pszIndent
0x18001b9bf  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b9c6  mov     rcx, [rcx+10h]
0x18001b9ca  mov     edx, 0EBh
0x18001b9cf  call    WPP_SF_s
0x18001b9d4  cmp     [rsp+48h+arg_0], 0
0x18001b9d9  jnz     loc_18001B927
0x18001b9df  mov     ebx, [rsp+48h+arg_8]
0x18001b9e3  cmp     [rsp+48h+arg_0], 0
0x18001b9e8  jnz     loc_18001B927
0x18001b9ee  mov     edx, 1
0x18001b9f3  call    WppTraceIndent
0x18001b9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9ff  cmp     rcx, r12
0x18001ba02  jz      short loc_18001BA30
0x18001ba04  test    byte ptr [rcx+1Ch], 2
0x18001ba08  jz      short loc_18001BA30
0x18001ba0a  cmp     byte ptr [rcx+19h], 5
0x18001ba0e  jb      short loc_18001BA30
0x18001ba10  mov     r9, cs:WPP_pszIndent
0x18001ba17  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ba1e  mov     rcx, [rcx+10h]
0x18001ba22  mov     edx, 0ECh
0x18001ba27  mov     [rsp+48h+var_28], ebx
0x18001ba2b  call    WPP_SF_sd
0x18001ba30  mov     rsi, [rsp+48h+arg_18]
0x18001ba35  mov     eax, ebx
0x18001ba37  mov     rbx, [rsp+48h+arg_10]
0x18001ba3c  add     rsp, 30h
0x18001ba40  pop     r14
0x18001ba42  pop     r12
0x18001ba44  pop     rdi
0x18001ba45  retn
```

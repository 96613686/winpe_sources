# I_ReaderListReadCertsFromCard

- ea: `0x180017da8`
- end: `0x180017f94`
- name: `I_ReaderListReadCertsFromCard`
- size: `492`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180016d74`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001317c`
- `0x1800135d0`
- `0x180017da8`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017f00`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017f00`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadCertsFromCard(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  unsigned __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v9; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v9 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v5 = (unsigned int)(*(_DWORD *)(a1 + 24) - 1);
  if ( *(_DWORD *)(a1 + 24) != 1 )
  {
    if ( *(_DWORD *)(a1 + 24) != 2 )
      goto LABEL_27;
    goto LABEL_7;
  }
  if ( *(_DWORD *)(a2 + 12) == 1024 )
  {
LABEL_7:
    if ( *(_QWORD *)(a2 + 88) )
    {
      v7 = I_CollectCertsUsingCng(a1, a2, &v9);
      goto LABEL_22;
    }
    if ( !*(_QWORD *)(a2 + 80) )
    {
      WppTraceIndent(v5, 2);
      v5 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v6 = 172;
LABEL_19:
        WPP_SF_s(*(_QWORD *)(v5 + 16), v6, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
LABEL_20:
    v7 = I_CollectCertsUsingCapi(a1, a2, &v9);
LABEL_22:
    *(_DWORD *)(a2 + 144) = 1;
    *(_DWORD *)(a2 + 152) = 0;
    v3 = v7;
    EventActivityIdControl(1u, (LPGUID)(a2 + 184));
    if ( v3 )
    {
      WppTraceIndent(v5, 2);
      v5 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          173,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v3);
      }
    }
    goto LABEL_27;
  }
  if ( *(_QWORD *)(a2 + 80) )
    goto LABEL_20;
  WppTraceIndent(v5, 2);
  v5 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v6 = 171;
    goto LABEL_19;
  }
LABEL_27:
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      174,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x180017da8  push    rbx
0x180017daa  push    rsi
0x180017dab  push    rdi
0x180017dac  push    r12
0x180017dae  push    r13
0x180017db0  push    r14
0x180017db2  sub     rsp, 38h
0x180017db6  mov     rbx, rdx
0x180017db9  xor     edi, edi
0x180017dbb  xor     edx, edx
0x180017dbd  mov     [rsp+68h+arg_0], edi
0x180017dc1  mov     rsi, rcx
0x180017dc4  call    WppTraceIndent
0x180017dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dd0  lea     r12, WPP_GLOBAL_Control
0x180017dd7  lea     r13, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017dde  cmp     rcx, r12
0x180017de1  jz      short loc_180017E07
0x180017de3  test    byte ptr [rcx+1Ch], 2
0x180017de7  jz      short loc_180017E07
0x180017de9  cmp     byte ptr [rcx+19h], 5
0x180017ded  jb      short loc_180017E07
0x180017def  mov     r9, cs:WPP_pszIndent
0x180017df6  mov     edx, 0AAh
0x180017dfb  mov     rcx, [rcx+10h]
0x180017dff  mov     r8, r13
0x180017e02  call    WPP_SF_s
0x180017e07  mov     ecx, [rsi+18h]
0x180017e0a  mov     r14d, 1
0x180017e10  sub     ecx, r14d
0x180017e13  jz      short loc_180017E67
0x180017e15  cmp     ecx, r14d
0x180017e18  jnz     loc_180017F48
0x180017e1e  cmp     [rbx+58h], rdi
0x180017e22  jnz     loc_180017ED3
0x180017e28  cmp     [rbx+50h], rdi
0x180017e2c  jnz     loc_180017EC1
0x180017e32  mov     edx, 2
0x180017e37  call    WppTraceIndent
0x180017e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e43  cmp     rcx, r12
0x180017e46  jz      loc_180017F48
0x180017e4c  test    [rcx+1Ch], r14b
0x180017e50  jz      loc_180017F48
0x180017e56  cmp     byte ptr [rcx+19h], 3
0x180017e5a  jb      loc_180017F48
0x180017e60  mov     edx, 0ACh
0x180017e65  jmp     short loc_180017EA9
0x180017e67  cmp     dword ptr [rbx+0Ch], 400h
0x180017e6e  jz      short loc_180017E1E
0x180017e70  cmp     [rbx+50h], rdi
0x180017e74  jnz     short loc_180017EC1
0x180017e76  mov     edx, 2
0x180017e7b  call    WppTraceIndent
0x180017e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e87  cmp     rcx, r12
0x180017e8a  jz      loc_180017F48
0x180017e90  test    [rcx+1Ch], r14b
0x180017e94  jz      loc_180017F48
0x180017e9a  cmp     byte ptr [rcx+19h], 3
0x180017e9e  jb      loc_180017F48
0x180017ea4  mov     edx, 0ABh
0x180017ea9  mov     r9, cs:WPP_pszIndent
0x180017eb0  mov     r8, r13
0x180017eb3  mov     rcx, [rcx+10h]
0x180017eb7  call    WPP_SF_s
0x180017ebc  jmp     loc_180017F48
0x180017ec1  lea     r8, [rsp+68h+arg_0]
0x180017ec6  mov     rdx, rbx
0x180017ec9  mov     rcx, rsi
0x180017ecc  call    I_CollectCertsUsingCapi
0x180017ed1  jmp     short loc_180017EE3
0x180017ed3  lea     r8, [rsp+68h+arg_0]
0x180017ed8  mov     rdx, rbx
0x180017edb  mov     rcx, rsi
0x180017ede  call    I_CollectCertsUsingCng
0x180017ee3  lea     rdx, [rbx+0B8h]; ActivityId
0x180017eea  mov     [rbx+90h], r14d
0x180017ef1  mov     ecx, r14d; ControlCode
0x180017ef4  mov     dword ptr [rbx+98h], 0
0x180017efe  mov     edi, eax
0x180017f00  call    cs:__imp_EventActivityIdControl
0x180017f06  test    edi, edi
0x180017f08  jz      short loc_180017F48
0x180017f0a  mov     edx, 2
0x180017f0f  call    WppTraceIndent
0x180017f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f1b  cmp     rcx, r12
0x180017f1e  jz      short loc_180017F48
0x180017f20  test    [rcx+1Ch], r14b
0x180017f24  jz      short loc_180017F48
0x180017f26  cmp     byte ptr [rcx+19h], 3
0x180017f2a  jb      short loc_180017F48
0x180017f2c  mov     r9, cs:WPP_pszIndent
0x180017f33  mov     edx, 0ADh
0x180017f38  mov     rcx, [rcx+10h]
0x180017f3c  mov     r8, r13
0x180017f3f  mov     [rsp+68h+var_48], edi
0x180017f43  call    WPP_SF_sd
0x180017f48  mov     edx, r14d
0x180017f4b  call    WppTraceIndent
0x180017f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f57  cmp     rcx, r12
0x180017f5a  jz      short loc_180017F84
0x180017f5c  test    byte ptr [rcx+1Ch], 2
0x180017f60  jz      short loc_180017F84
0x180017f62  cmp     byte ptr [rcx+19h], 5
0x180017f66  jb      short loc_180017F84
0x180017f68  mov     r9, cs:WPP_pszIndent
0x180017f6f  mov     edx, 0AEh
0x180017f74  mov     rcx, [rcx+10h]
0x180017f78  mov     r8, r13
0x180017f7b  mov     [rsp+68h+var_48], edi
0x180017f7f  call    WPP_SF_sd
0x180017f84  mov     eax, edi
0x180017f86  add     rsp, 38h
0x180017f8a  pop     r14
0x180017f8c  pop     r13
0x180017f8e  pop     r12
0x180017f90  pop     rdi
0x180017f91  pop     rsi
0x180017f92  pop     rbx
0x180017f93  retn
```

# FaxGetSecurityExInternal(void *,ulong,void * *,ulong)

- ea: `0x1800145a0`
- end: `0x180014901`
- name: `?FaxGetSecurityExInternal@@YAHPEAXKPEAPEAXK@Z`
- size: `865`
- prototype: `__int64 __fastcall(void *, unsigned int, void **, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015ef0`
- `0x180015f10`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800145a0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014773`
- `RPCRT4!NdrClientCall3` at `0x1800147f9`
- `RPCRT4!NdrClientCall3` at `0x18001483d`
- `RPCRT4!NdrClientCall3` at `0x180014773`
- `RPCRT4!NdrClientCall3` at `0x1800147f9`
- `RPCRT4!NdrClientCall3` at `0x18001483d`
- `KERNEL32!SetLastError` at `0x180014623`
- `KERNEL32!SetLastError` at `0x18001466a`
- `KERNEL32!SetLastError` at `0x1800146ac`
- `KERNEL32!SetLastError` at `0x18001489d`
- `KERNEL32!SetLastError` at `0x1800148b7`
- `KERNEL32!SetLastError` at `0x180014623`
- `KERNEL32!SetLastError` at `0x18001466a`
- `KERNEL32!SetLastError` at `0x1800146ac`
- `KERNEL32!SetLastError` at `0x18001489d`
- `KERNEL32!SetLastError` at `0x1800148b7`

## pseudocode

```c
__int64 __fastcall FaxGetSecurityExInternal(_DWORD *a1, int a2, void **a3, unsigned int a4)
{
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // ebx
  __int64 v11; // rax
  __int64 v12; // r9
  unsigned int Pointer; // eax
  int v15; // [rsp+A0h] [rbp+8h] BYREF

  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
  }
  if ( !a1 || !*a1 || a1[4] )
  {
    SetLastError(6u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 40;
LABEL_46:
    WPP_SF_(v8[2], v9, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids);
    return 0;
  }
  if ( (a2 & 0xF) == 0 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 41;
    goto LABEL_46;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 42;
    goto LABEL_46;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v9 = 43;
    goto LABEL_46;
  }
  *a3 = 0;
  if ( a4 == 0x20000 )
  {
    v11 = *((_QWORD *)a1 + 4);
    v12 = *(unsigned int *)(v11 + 80);
    if ( (unsigned int)v12 >= 0x10000 )
    {
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x51u,
                                0,
                                *(_QWORD *)v11,
                                a2,
                                a3,
                                &v15).Pointer;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids, v12);
      }
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x17u,
                                0,
                                **((_QWORD **)a1 + 4),
                                a3,
                                &v15).Pointer;
    }
    v10 = Pointer;
  }
  else if ( a4 == 196608 )
  {
    v10 = (unsigned int)NdrClientCall3(
                          (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                          0x63u,
                          0,
                          **((_QWORD **)a1 + 4),
                          a2,
                          a3,
                          &v15).Pointer;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids, a4);
    }
    v10 = 668;
  }
  if ( !v10 )
    return 1;
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x1800145a0  mov     rax, rsp
0x1800145a3  push    rbx
0x1800145a4  push    rsi
0x1800145a5  push    r12
0x1800145a7  push    r13
0x1800145a9  push    r14
0x1800145ab  push    r15
0x1800145ad  sub     rsp, 68h
0x1800145b1  mov     r14d, r9d
0x1800145b4  mov     r15, r8
0x1800145b7  mov     r12d, edx
0x1800145ba  mov     rsi, rcx
0x1800145bd  mov     dword ptr [rax+8], 0
0x1800145c4  lea     r13, WPP_GLOBAL_Control
0x1800145cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145d2  mov     ebx, 1000h
0x1800145d7  cmp     rcx, r13
0x1800145da  jz      short loc_1800145FC
0x1800145dc  test    [rcx+1Ch], ebx
0x1800145df  jz      short loc_1800145FC
0x1800145e1  cmp     byte ptr [rcx+19h], 5
0x1800145e5  jb      short loc_1800145FC
0x1800145e7  mov     edx, 27h ; '''
0x1800145ec  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x1800145f3  mov     rcx, [rcx+10h]
0x1800145f7  call    WPP_SF_
0x1800145fc  test    rsi, rsi
0x1800145ff  jz      loc_1800148B2
0x180014605  cmp     dword ptr [rsi], 0
0x180014608  jz      loc_1800148B2
0x18001460e  cmp     dword ptr [rsi+10h], 0
0x180014612  jnz     loc_1800148B2
0x180014618  test    r12b, 0Fh
0x18001461c  jnz     short loc_18001465C
0x18001461e  mov     ecx, 57h ; 'W'; dwErrCode
0x180014623  call    cs:__imp_SetLastError
0x18001462a  nop     dword ptr [rax+rax+00h]
0x18001462f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014636  cmp     rcx, r13
0x180014639  jz      loc_1800148EF
0x18001463f  test    [rcx+1Ch], ebx
0x180014642  jz      loc_1800148EF
0x180014648  cmp     byte ptr [rcx+19h], 2
0x18001464c  jb      loc_1800148EF
0x180014652  mov     edx, 29h ; ')'
0x180014657  jmp     loc_1800148DF
0x18001465c  test    r12d, 0FFFFFFF0h
0x180014663  jz      short loc_1800146A3
0x180014665  mov     ecx, 57h ; 'W'; dwErrCode
0x18001466a  call    cs:__imp_SetLastError
0x180014671  nop     dword ptr [rax+rax+00h]
0x180014676  mov     rcx, cs:WPP_GLOBAL_Control
0x18001467d  cmp     rcx, r13
0x180014680  jz      loc_1800148EF
0x180014686  test    [rcx+1Ch], ebx
0x180014689  jz      loc_1800148EF
0x18001468f  cmp     byte ptr [rcx+19h], 2
0x180014693  jb      loc_1800148EF
0x180014699  mov     edx, 2Ah ; '*'
0x18001469e  jmp     loc_1800148DF
0x1800146a3  test    r15, r15
0x1800146a6  jnz     short loc_1800146E4
0x1800146a8  lea     ecx, [r15+57h]; dwErrCode
0x1800146ac  call    cs:__imp_SetLastError
0x1800146b3  nop     dword ptr [rax+rax+00h]
0x1800146b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146bf  cmp     rcx, r13
0x1800146c2  jz      loc_1800148EF
0x1800146c8  test    [rcx+1Ch], ebx
0x1800146cb  jz      loc_1800148EF
0x1800146d1  cmp     byte ptr [rcx+19h], 2
0x1800146d5  jb      loc_1800148EF
0x1800146db  lea     edx, [r15+2Bh]
0x1800146df  jmp     loc_1800148DF
0x1800146e4  mov     qword ptr [r15], 0
0x1800146eb  cmp     r14d, 20000h
0x1800146f2  jz      loc_18001478C
0x1800146f8  cmp     r14d, 30000h
0x1800146ff  jz      short loc_18001473E
0x180014701  mov     rcx, cs:WPP_GLOBAL_Control
0x180014708  cmp     rcx, r13
0x18001470b  jz      short loc_180014730
0x18001470d  test    [rcx+1Ch], ebx
0x180014710  jz      short loc_180014730
0x180014712  cmp     byte ptr [rcx+19h], 2
0x180014716  jb      short loc_180014730
0x180014718  mov     edx, 2Dh ; '-'
0x18001471d  mov     r9d, r14d
0x180014720  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x180014727  mov     rcx, [rcx+10h]
0x18001472b  call    WPP_SF_d
0x180014730  mov     ebx, 29Ch
0x180014735  mov     [rsp+98h+var_58], ebx
0x180014739  jmp     loc_180014854
0x18001473e  mov     rax, [rsi+20h]
0x180014742  mov     [rsp+98h+var_50], 0
0x18001474b  lea     rcx, [rsp+98h+arg_0]
0x180014753  mov     [rsp+98h+var_68], rcx
0x180014758  mov     [rsp+98h+var_70], r15
0x18001475d  mov     dword ptr [rsp+98h+var_78], r12d
0x180014762  mov     r9, [rax]
0x180014765  xor     r8d, r8d; pReturnValue
0x180014768  lea     edx, [r8+63h]; nProcNum
0x18001476c  lea     rcx, pProxyInfo; pProxyInfo
0x180014773  call    cs:__imp_NdrClientCall3
0x18001477a  nop     dword ptr [rax+rax+00h]
0x18001477f  mov     rbx, rax
0x180014782  mov     [rsp+98h+var_50], rax
0x180014787  jmp     loc_180014850
0x18001478c  mov     rax, [rsi+20h]
0x180014790  mov     r9d, [rax+50h]
0x180014794  cmp     r9d, 10000h
0x18001479b  jnb     short loc_18001480C
0x18001479d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a4  cmp     rcx, r13
0x1800147a7  jz      short loc_1800147C9
0x1800147a9  test    [rcx+1Ch], ebx
0x1800147ac  jz      short loc_1800147C9
0x1800147ae  cmp     byte ptr [rcx+19h], 5
0x1800147b2  jb      short loc_1800147C9
0x1800147b4  mov     edx, 2Ch ; ','
0x1800147b9  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x1800147c0  mov     rcx, [rcx+10h]
0x1800147c4  call    WPP_SF_d
0x1800147c9  mov     rax, [rsi+20h]
0x1800147cd  mov     [rsp+98h+var_48], 0
0x1800147d6  lea     rcx, [rsp+98h+arg_0]
0x1800147de  mov     [rsp+98h+var_70], rcx
0x1800147e3  mov     [rsp+98h+var_78], r15
0x1800147e8  mov     r9, [rax]
0x1800147eb  xor     r8d, r8d; pReturnValue
0x1800147ee  lea     edx, [r8+17h]; nProcNum
0x1800147f2  lea     rcx, pProxyInfo; pProxyInfo
0x1800147f9  call    cs:__imp_NdrClientCall3
0x180014800  nop     dword ptr [rax+rax+00h]
0x180014805  mov     [rsp+98h+var_48], rax
0x18001480a  jmp     short loc_18001484E
0x18001480c  mov     [rsp+98h+var_40], 0
0x180014815  lea     rcx, [rsp+98h+arg_0]
0x18001481d  mov     [rsp+98h+var_68], rcx
0x180014822  mov     [rsp+98h+var_70], r15
0x180014827  mov     dword ptr [rsp+98h+var_78], r12d
0x18001482c  mov     r9, [rax]
0x18001482f  xor     r8d, r8d; pReturnValue
0x180014832  lea     edx, [r8+51h]; nProcNum
0x180014836  lea     rcx, pProxyInfo; pProxyInfo
0x18001483d  call    cs:__imp_NdrClientCall3
0x180014844  nop     dword ptr [rax+rax+00h]
0x180014849  mov     [rsp+98h+var_40], rax
0x18001484e  mov     ebx, eax
0x180014850  mov     [rsp+98h+var_58], eax
0x180014854  jmp     short loc_180014897
0x180014856  mov     ebx, eax
0x180014858  mov     [rsp+98h+var_58], eax
0x18001485c  lea     rdx, WPP_GLOBAL_Control
0x180014863  mov     rcx, cs:WPP_GLOBAL_Control
0x18001486a  cmp     rcx, rdx
0x18001486d  jz      short loc_180014897
0x18001486f  test    dword ptr [rcx+1Ch], 1000h
0x180014876  jz      short loc_180014897
0x180014878  cmp     byte ptr [rcx+19h], 2
0x18001487c  jb      short loc_180014897
0x18001487e  mov     edx, 2Eh ; '.'
0x180014883  mov     r9d, eax
0x180014886  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x18001488d  mov     rcx, [rcx+10h]
0x180014891  call    WPP_SF_d
0x180014896  nop
0x180014897  test    ebx, ebx
0x180014899  jz      short loc_1800148AB
0x18001489b  mov     ecx, ebx; dwErrCode
0x18001489d  call    cs:__imp_SetLastError
0x1800148a4  nop     dword ptr [rax+rax+00h]
0x1800148a9  jmp     short loc_1800148EF
0x1800148ab  mov     eax, 1
0x1800148b0  jmp     short loc_1800148F1
0x1800148b2  mov     ecx, 6; dwErrCode
0x1800148b7  call    cs:__imp_SetLastError
0x1800148be  nop     dword ptr [rax+rax+00h]
0x1800148c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148ca  cmp     rcx, r13
0x1800148cd  jz      short loc_1800148EF
0x1800148cf  test    [rcx+1Ch], ebx
0x1800148d2  jz      short loc_1800148EF
0x1800148d4  cmp     byte ptr [rcx+19h], 2
0x1800148d8  jb      short loc_1800148EF
0x1800148da  mov     edx, 28h ; '('
0x1800148df  lea     r8, WPP_652374daa97d31cbf23d290be6b800e6_Traceguids
0x1800148e6  mov     rcx, [rcx+10h]
0x1800148ea  call    WPP_SF_
0x1800148ef  xor     eax, eax
0x1800148f1  add     rsp, 68h
0x1800148f5  pop     r15
0x1800148f7  pop     r14
0x1800148f9  pop     r13
0x1800148fb  pop     r12
0x1800148fd  pop     rsi
0x1800148fe  pop     rbx
0x1800148ff  retn
```

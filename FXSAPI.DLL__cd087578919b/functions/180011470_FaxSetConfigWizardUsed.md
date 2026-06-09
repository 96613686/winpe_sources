# FaxSetConfigWizardUsed

- ea: `0x180011470`
- end: `0x18001163a`
- name: `FaxSetConfigWizardUsed`
- size: `458`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180011470`
- `0x180027b70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180011583`
- `RPCRT4!NdrClientCall3` at `0x180011583`
- `KERNEL32!SetLastError` at `0x180011510`
- `KERNEL32!SetLastError` at `0x1800115f5`
- `KERNEL32!SetLastError` at `0x180011510`
- `KERNEL32!SetLastError` at `0x1800115f5`

## pseudocode

```c
__int64 __fastcall FaxSetConfigWizardUsed(_QWORD *a1, int a2)
{
  DWORD v4; // ecx
  __int64 v5; // rax
  __int64 v6; // r9
  unsigned int Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( a1 && *(_DWORD *)a1 && !*((_DWORD *)a1 + 4) )
  {
    if ( (unsigned int)IsLocalFaxConnection(a1) )
    {
      v5 = a1[4];
      v6 = *(unsigned int *)(v5 + 80);
      if ( (unsigned int)v6 >= 0x10000 )
      {
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x4Du, 0, *(_QWORD *)v5, a2).Pointer;
        if ( !Pointer )
          return 1;
        v4 = Pointer;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, v6);
        }
        v4 = 7012;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 305, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      v4 = 6;
    }
    SetLastError(v4);
  }
  else
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011470  push    rbx
0x180011472  push    rsi
0x180011473  push    rdi
0x180011474  push    r14
0x180011476  sub     rsp, 48h
0x18001147a  mov     esi, edx
0x18001147c  mov     rdi, rcx
0x18001147f  lea     r14, WPP_GLOBAL_Control
0x180011486  mov     rcx, cs:WPP_GLOBAL_Control
0x18001148d  mov     ebx, 1000h
0x180011492  cmp     rcx, r14
0x180011495  jz      short loc_1800114B7
0x180011497  test    [rcx+1Ch], ebx
0x18001149a  jz      short loc_1800114B7
0x18001149c  cmp     byte ptr [rcx+19h], 5
0x1800114a0  jb      short loc_1800114B7
0x1800114a2  mov     edx, 12Fh
0x1800114a7  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800114ae  mov     rcx, [rcx+10h]
0x1800114b2  call    WPP_SF_
0x1800114b7  test    rdi, rdi
0x1800114ba  jz      loc_1800115F0
0x1800114c0  cmp     dword ptr [rdi], 0
0x1800114c3  jz      loc_1800115F0
0x1800114c9  cmp     dword ptr [rdi+10h], 0
0x1800114cd  jnz     loc_1800115F0
0x1800114d3  mov     rcx, rdi; void *
0x1800114d6  call    ?IsLocalFaxConnection@@YAHPEAX@Z; IsLocalFaxConnection(void *)
0x1800114db  test    eax, eax
0x1800114dd  jnz     short loc_180011521
0x1800114df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114e6  cmp     rcx, r14
0x1800114e9  jz      short loc_18001150B
0x1800114eb  test    [rcx+1Ch], ebx
0x1800114ee  jz      short loc_18001150B
0x1800114f0  cmp     byte ptr [rcx+19h], 2
0x1800114f4  jb      short loc_18001150B
0x1800114f6  mov     edx, 131h
0x1800114fb  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011502  mov     rcx, [rcx+10h]
0x180011506  call    WPP_SF_
0x18001150b  mov     ecx, 6; dwErrCode
0x180011510  call    cs:__imp_SetLastError
0x180011517  nop     dword ptr [rax+rax+00h]
0x18001151c  jmp     loc_18001162D
0x180011521  mov     rax, [rdi+20h]
0x180011525  mov     r9d, [rax+50h]
0x180011529  cmp     r9d, 10000h
0x180011530  jnb     short loc_180011565
0x180011532  mov     rcx, cs:WPP_GLOBAL_Control
0x180011539  cmp     rcx, r14
0x18001153c  jz      short loc_18001155E
0x18001153e  test    [rcx+1Ch], ebx
0x180011541  jz      short loc_18001155E
0x180011543  cmp     byte ptr [rcx+19h], 2
0x180011547  jb      short loc_18001155E
0x180011549  mov     edx, 132h
0x18001154e  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011555  mov     rcx, [rcx+10h]
0x180011559  call    WPP_SF_d
0x18001155e  mov     ecx, 1B64h
0x180011563  jmp     short loc_180011510
0x180011565  mov     [rsp+68h+arg_0], 0
0x18001156e  mov     [rsp+68h+var_48], esi
0x180011572  mov     r9, [rax]
0x180011575  xor     r8d, r8d; pReturnValue
0x180011578  lea     edx, [r8+4Dh]; nProcNum
0x18001157c  lea     rcx, pProxyInfo; pProxyInfo
0x180011583  call    cs:__imp_NdrClientCall3
0x18001158a  nop     dword ptr [rax+rax+00h]
0x18001158f  mov     rbx, rax
0x180011592  mov     [rsp+68h+arg_0], rax
0x180011597  mov     [rsp+68h+var_38], eax
0x18001159b  jmp     short loc_1800115DE
0x18001159d  mov     ebx, eax
0x18001159f  mov     [rsp+68h+var_38], eax
0x1800115a3  lea     rdx, WPP_GLOBAL_Control
0x1800115aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115b1  cmp     rcx, rdx
0x1800115b4  jz      short loc_1800115DE
0x1800115b6  test    dword ptr [rcx+1Ch], 1000h
0x1800115bd  jz      short loc_1800115DE
0x1800115bf  cmp     byte ptr [rcx+19h], 2
0x1800115c3  jb      short loc_1800115DE
0x1800115c5  mov     edx, 133h
0x1800115ca  mov     r9d, eax
0x1800115cd  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800115d4  mov     rcx, [rcx+10h]
0x1800115d8  call    WPP_SF_d
0x1800115dd  nop
0x1800115de  test    ebx, ebx
0x1800115e0  jz      short loc_1800115E9
0x1800115e2  mov     ecx, ebx
0x1800115e4  jmp     loc_180011510
0x1800115e9  mov     eax, 1
0x1800115ee  jmp     short loc_18001162F
0x1800115f0  mov     ecx, 6; dwErrCode
0x1800115f5  call    cs:__imp_SetLastError
0x1800115fc  nop     dword ptr [rax+rax+00h]
0x180011601  mov     rcx, cs:WPP_GLOBAL_Control
0x180011608  cmp     rcx, r14
0x18001160b  jz      short loc_18001162D
0x18001160d  test    [rcx+1Ch], ebx
0x180011610  jz      short loc_18001162D
0x180011612  cmp     byte ptr [rcx+19h], 2
0x180011616  jb      short loc_18001162D
0x180011618  mov     edx, 130h
0x18001161d  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180011624  mov     rcx, [rcx+10h]
0x180011628  call    WPP_SF_
0x18001162d  xor     eax, eax
0x18001162f  add     rsp, 48h
0x180011633  pop     r14
0x180011635  pop     rdi
0x180011636  pop     rsi
0x180011637  pop     rbx
0x180011638  retn
```

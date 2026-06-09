# FaxRemoveOutboundGroupW

- ea: `0x180010720`
- end: `0x180010963`
- name: `FaxRemoveOutboundGroupW`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010650`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180010720`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800107d8`
- `msvcrt!_wcsicmp` at `0x1800107d8`
- `RPCRT4!NdrClientCall3` at `0x180010899`
- `RPCRT4!NdrClientCall3` at `0x180010899`
- `KERNEL32!SetLastError` at `0x180010795`
- `KERNEL32!SetLastError` at `0x1800107ed`
- `KERNEL32!SetLastError` at `0x180010841`
- `KERNEL32!SetLastError` at `0x1800108fa`
- `KERNEL32!SetLastError` at `0x180010914`
- `KERNEL32!SetLastError` at `0x180010795`
- `KERNEL32!SetLastError` at `0x1800107ed`
- `KERNEL32!SetLastError` at `0x180010841`
- `KERNEL32!SetLastError` at `0x1800108fa`
- `KERNEL32!SetLastError` at `0x180010914`

## pseudocode

```c
__int64 __fastcall FaxRemoveOutboundGroupW(__int64 a1, const wchar_t *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 233;
LABEL_32:
    WPP_SF_(v4[2], v5, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 234;
    goto LABEL_32;
  }
  if ( !_wcsicmp(a2, L"<All devices>") )
  {
    SetLastError(0x10DDu);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 235;
    goto LABEL_32;
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 >= 0x80 )
  {
    SetLastError(0x6Fu);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 236;
    goto LABEL_32;
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x35u, 0, **(_QWORD **)(a1 + 32), a2).Pointer;
  if ( !Pointer )
    return 1;
  SetLastError(Pointer);
  return 0;
}

```

## disassembly

```asm
0x180010720  mov     [rsp+arg_8], rbx
0x180010725  mov     [rsp+arg_10], rsi
0x18001072a  push    rdi
0x18001072b  push    r14
0x18001072d  push    r15
0x18001072f  sub     rsp, 40h
0x180010733  mov     r14, rdx
0x180010736  mov     rsi, rcx
0x180010739  lea     r15, WPP_GLOBAL_Control
0x180010740  mov     rcx, cs:WPP_GLOBAL_Control
0x180010747  mov     ebx, 1000h
0x18001074c  cmp     rcx, r15
0x18001074f  jz      short loc_180010771
0x180010751  test    [rcx+1Ch], ebx
0x180010754  jz      short loc_180010771
0x180010756  cmp     byte ptr [rcx+19h], 5
0x18001075a  jb      short loc_180010771
0x18001075c  mov     edx, 0E8h
0x180010761  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010768  mov     rcx, [rcx+10h]
0x18001076c  call    WPP_SF_
0x180010771  xor     edi, edi
0x180010773  test    rsi, rsi
0x180010776  jz      loc_18001090F
0x18001077c  cmp     [rsi], edi
0x18001077e  jz      loc_18001090F
0x180010784  cmp     [rsi+10h], edi
0x180010787  jnz     loc_18001090F
0x18001078d  test    r14, r14
0x180010790  jnz     short loc_1800107CE
0x180010792  lea     ecx, [rdi+57h]; dwErrCode
0x180010795  call    cs:__imp_SetLastError
0x18001079c  nop     dword ptr [rax+rax+00h]
0x1800107a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107a8  cmp     rcx, r15
0x1800107ab  jz      loc_18001094C
0x1800107b1  test    [rcx+1Ch], ebx
0x1800107b4  jz      loc_18001094C
0x1800107ba  cmp     byte ptr [rcx+19h], 2
0x1800107be  jb      loc_18001094C
0x1800107c4  mov     edx, 0EAh
0x1800107c9  jmp     loc_18001093C
0x1800107ce  lea     rdx, aAllDevices; "<All devices>"
0x1800107d5  mov     rcx, r14; String1
0x1800107d8  call    cs:__imp__wcsicmp
0x1800107df  nop     dword ptr [rax+rax+00h]
0x1800107e4  test    eax, eax
0x1800107e6  jnz     short loc_180010826
0x1800107e8  mov     ecx, 10DDh; dwErrCode
0x1800107ed  call    cs:__imp_SetLastError
0x1800107f4  nop     dword ptr [rax+rax+00h]
0x1800107f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010800  cmp     rcx, r15
0x180010803  jz      loc_18001094C
0x180010809  test    [rcx+1Ch], ebx
0x18001080c  jz      loc_18001094C
0x180010812  cmp     byte ptr [rcx+19h], 2
0x180010816  jb      loc_18001094C
0x18001081c  mov     edx, 0EBh
0x180010821  jmp     loc_18001093C
0x180010826  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001082a  inc     rax
0x18001082d  cmp     [r14+rax*2], di
0x180010832  jnz     short loc_18001082A
0x180010834  cmp     rax, 80h
0x18001083a  jb      short loc_18001087A
0x18001083c  mov     ecx, 6Fh ; 'o'; dwErrCode
0x180010841  call    cs:__imp_SetLastError
0x180010848  nop     dword ptr [rax+rax+00h]
0x18001084d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010854  cmp     rcx, r15
0x180010857  jz      loc_18001094C
0x18001085d  test    [rcx+1Ch], ebx
0x180010860  jz      loc_18001094C
0x180010866  cmp     byte ptr [rcx+19h], 2
0x18001086a  jb      loc_18001094C
0x180010870  mov     edx, 0ECh
0x180010875  jmp     loc_18001093C
0x18001087a  mov     rax, [rsi+20h]
0x18001087e  mov     [rsp+58h+arg_0], rdi
0x180010883  mov     [rsp+58h+var_38], r14
0x180010888  mov     r9, [rax]
0x18001088b  xor     r8d, r8d; pReturnValue
0x18001088e  lea     edx, [r8+35h]; nProcNum
0x180010892  lea     rcx, pProxyInfo; pProxyInfo
0x180010899  call    cs:__imp_NdrClientCall3
0x1800108a0  nop     dword ptr [rax+rax+00h]
0x1800108a5  mov     rbx, rax
0x1800108a8  mov     [rsp+58h+arg_0], rax
0x1800108ad  mov     [rsp+58h+var_28], eax
0x1800108b1  jmp     short loc_1800108F4
0x1800108b3  mov     ebx, eax
0x1800108b5  mov     [rsp+58h+var_28], eax
0x1800108b9  lea     rdx, WPP_GLOBAL_Control
0x1800108c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108c7  cmp     rcx, rdx
0x1800108ca  jz      short loc_1800108F4
0x1800108cc  test    dword ptr [rcx+1Ch], 1000h
0x1800108d3  jz      short loc_1800108F4
0x1800108d5  cmp     byte ptr [rcx+19h], 2
0x1800108d9  jb      short loc_1800108F4
0x1800108db  mov     edx, 0EDh
0x1800108e0  mov     r9d, eax
0x1800108e3  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800108ea  mov     rcx, [rcx+10h]
0x1800108ee  call    WPP_SF_d
0x1800108f3  nop
0x1800108f4  test    ebx, ebx
0x1800108f6  jz      short loc_180010908
0x1800108f8  mov     ecx, ebx; dwErrCode
0x1800108fa  call    cs:__imp_SetLastError
0x180010901  nop     dword ptr [rax+rax+00h]
0x180010906  jmp     short loc_18001094C
0x180010908  mov     eax, 1
0x18001090d  jmp     short loc_18001094E
0x18001090f  mov     ecx, 6; dwErrCode
0x180010914  call    cs:__imp_SetLastError
0x18001091b  nop     dword ptr [rax+rax+00h]
0x180010920  mov     rcx, cs:WPP_GLOBAL_Control
0x180010927  cmp     rcx, r15
0x18001092a  jz      short loc_18001094C
0x18001092c  test    [rcx+1Ch], ebx
0x18001092f  jz      short loc_18001094C
0x180010931  cmp     byte ptr [rcx+19h], 2
0x180010935  jb      short loc_18001094C
0x180010937  mov     edx, 0E9h
0x18001093c  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010943  mov     rcx, [rcx+10h]
0x180010947  call    WPP_SF_
0x18001094c  xor     eax, eax
0x18001094e  mov     rbx, [rsp+58h+arg_8]
0x180010953  mov     rsi, [rsp+58h+arg_10]
0x180010958  add     rsp, 40h
0x18001095c  pop     r15
0x18001095e  pop     r14
0x180010960  pop     rdi
0x180010961  retn
```

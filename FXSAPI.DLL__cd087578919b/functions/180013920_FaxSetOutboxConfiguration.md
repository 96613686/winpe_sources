# FaxSetOutboxConfiguration

- ea: `0x180013920`
- end: `0x180013b7c`
- name: `FaxSetOutboxConfiguration`
- size: `604`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180013920`
- `0x180014368`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180013a5a`
- `RPCRT4!NdrClientCall3` at `0x180013a5a`
- `KERNEL32!SetLastError` at `0x18001398c`
- `KERNEL32!SetLastError` at `0x1800139cf`
- `KERNEL32!SetLastError` at `0x180013abe`
- `KERNEL32!SetLastError` at `0x180013ade`
- `KERNEL32!SetLastError` at `0x180013b37`
- `KERNEL32!SetLastError` at `0x18001398c`
- `KERNEL32!SetLastError` at `0x1800139cf`
- `KERNEL32!SetLastError` at `0x180013abe`
- `KERNEL32!SetLastError` at `0x180013ade`
- `KERNEL32!SetLastError` at `0x180013b37`

## pseudocode

```c
__int64 __fastcall FaxSetOutboxConfiguration(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD Pointer; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v5 = 145;
LABEL_33:
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
    v5 = 146;
    goto LABEL_33;
  }
  if ( *(_DWORD *)a2 != 36 )
  {
    SetLastError(0x57u);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 147;
    goto LABEL_33;
  }
  if ( *(_WORD *)(a2 + 20) >= 0x18u
    || *(_WORD *)(a2 + 22) >= 0x3Cu
    || *(_WORD *)(a2 + 24) >= 0x18u
    || *(_WORD *)(a2 + 26) >= 0x3Cu )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        *(unsigned __int16 *)(a2 + 24),
        *(unsigned __int16 *)(a2 + 20),
        *(unsigned __int16 *)(a2 + 22),
        *(unsigned __int16 *)(a2 + 24),
        *(unsigned __int16 *)(a2 + 26));
    }
  }
  else
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x27u,
                              0,
                              **(_QWORD **)(a1 + 32),
                              a2).Pointer;
    if ( !Pointer )
      return 1;
    SetLastError(Pointer);
  }
  return 0;
}

```

## disassembly

```asm
0x180013920  push    rbx
0x180013922  push    rsi
0x180013923  push    rdi
0x180013924  push    r14
0x180013926  sub     rsp, 58h
0x18001392a  mov     rbx, rdx
0x18001392d  mov     rsi, rcx
0x180013930  lea     r14, WPP_GLOBAL_Control
0x180013937  mov     rcx, cs:WPP_GLOBAL_Control
0x18001393e  mov     edi, 1000h
0x180013943  cmp     rcx, r14
0x180013946  jz      short loc_180013968
0x180013948  test    [rcx+1Ch], edi
0x18001394b  jz      short loc_180013968
0x18001394d  cmp     byte ptr [rcx+19h], 5
0x180013951  jb      short loc_180013968
0x180013953  mov     edx, 90h
0x180013958  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001395f  mov     rcx, [rcx+10h]
0x180013963  call    WPP_SF_
0x180013968  test    rsi, rsi
0x18001396b  jz      loc_180013B32
0x180013971  cmp     dword ptr [rsi], 0
0x180013974  jz      loc_180013B32
0x18001397a  cmp     dword ptr [rsi+10h], 0
0x18001397e  jnz     loc_180013B32
0x180013984  test    rbx, rbx
0x180013987  jnz     short loc_1800139C5
0x180013989  lea     ecx, [rbx+57h]; dwErrCode
0x18001398c  call    cs:__imp_SetLastError
0x180013993  nop     dword ptr [rax+rax+00h]
0x180013998  mov     rcx, cs:WPP_GLOBAL_Control
0x18001399f  cmp     rcx, r14
0x1800139a2  jz      loc_180013B6F
0x1800139a8  test    [rcx+1Ch], edi
0x1800139ab  jz      loc_180013B6F
0x1800139b1  cmp     byte ptr [rcx+19h], 2
0x1800139b5  jb      loc_180013B6F
0x1800139bb  mov     edx, 92h
0x1800139c0  jmp     loc_180013B5F
0x1800139c5  cmp     dword ptr [rbx], 24h ; '$'
0x1800139c8  jz      short loc_180013A08
0x1800139ca  mov     ecx, 57h ; 'W'; dwErrCode
0x1800139cf  call    cs:__imp_SetLastError
0x1800139d6  nop     dword ptr [rax+rax+00h]
0x1800139db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139e2  cmp     rcx, r14
0x1800139e5  jz      loc_180013B6F
0x1800139eb  test    [rcx+1Ch], edi
0x1800139ee  jz      loc_180013B6F
0x1800139f4  cmp     byte ptr [rcx+19h], 2
0x1800139f8  jb      loc_180013B6F
0x1800139fe  mov     edx, 93h
0x180013a03  jmp     loc_180013B5F
0x180013a08  cmp     word ptr [rbx+14h], 18h
0x180013a0d  jnb     loc_180013AD9
0x180013a13  cmp     word ptr [rbx+16h], 3Ch ; '<'
0x180013a18  jnb     loc_180013AD9
0x180013a1e  cmp     word ptr [rbx+18h], 18h
0x180013a23  jnb     loc_180013AD9
0x180013a29  cmp     word ptr [rbx+1Ah], 3Ch ; '<'
0x180013a2e  jnb     loc_180013AD9
0x180013a34  mov     rax, [rsi+20h]
0x180013a38  mov     [rsp+78h+arg_0], 0
0x180013a44  mov     [rsp+78h+var_58], rbx
0x180013a49  mov     r9, [rax]
0x180013a4c  xor     r8d, r8d; pReturnValue
0x180013a4f  lea     edx, [r8+27h]; nProcNum
0x180013a53  lea     rcx, pProxyInfo; pProxyInfo
0x180013a5a  call    cs:__imp_NdrClientCall3
0x180013a61  nop     dword ptr [rax+rax+00h]
0x180013a66  mov     rbx, rax
0x180013a69  mov     [rsp+78h+arg_0], rax
0x180013a71  mov     [rsp+78h+var_38], eax
0x180013a75  jmp     short loc_180013AB8
0x180013a77  mov     ebx, eax
0x180013a79  mov     [rsp+78h+var_38], eax
0x180013a7d  lea     rdx, WPP_GLOBAL_Control
0x180013a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a8b  cmp     rcx, rdx
0x180013a8e  jz      short loc_180013AB8
0x180013a90  test    dword ptr [rcx+1Ch], 1000h
0x180013a97  jz      short loc_180013AB8
0x180013a99  cmp     byte ptr [rcx+19h], 2
0x180013a9d  jb      short loc_180013AB8
0x180013a9f  mov     edx, 95h
0x180013aa4  mov     r9d, eax
0x180013aa7  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180013aae  mov     rcx, [rcx+10h]
0x180013ab2  call    WPP_SF_d
0x180013ab7  nop
0x180013ab8  test    ebx, ebx
0x180013aba  jz      short loc_180013ACF
0x180013abc  mov     ecx, ebx; dwErrCode
0x180013abe  call    cs:__imp_SetLastError
0x180013ac5  nop     dword ptr [rax+rax+00h]
0x180013aca  jmp     loc_180013B6F
0x180013acf  mov     eax, 1
0x180013ad4  jmp     loc_180013B71
0x180013ad9  mov     ecx, 57h ; 'W'; dwErrCode
0x180013ade  call    cs:__imp_SetLastError
0x180013ae5  nop     dword ptr [rax+rax+00h]
0x180013aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180013af1  cmp     rcx, r14
0x180013af4  jz      short loc_180013B6F
0x180013af6  test    [rcx+1Ch], edi
0x180013af9  jz      short loc_180013B6F
0x180013afb  cmp     byte ptr [rcx+19h], 2
0x180013aff  jb      short loc_180013B6F
0x180013b01  movzx   eax, word ptr [rbx+1Ah]
0x180013b05  movzx   r8d, word ptr [rbx+18h]
0x180013b0a  movzx   r10d, word ptr [rbx+16h]
0x180013b0f  movzx   r9d, word ptr [rbx+14h]
0x180013b14  mov     edx, 94h
0x180013b19  mov     [rsp+78h+var_48], eax
0x180013b1d  mov     [rsp+78h+var_50], r8d
0x180013b22  mov     dword ptr [rsp+78h+var_58], r10d
0x180013b27  mov     rcx, [rcx+10h]
0x180013b2b  call    WPP_SF_dddd
0x180013b30  jmp     short loc_180013B6F
0x180013b32  mov     ecx, 6; dwErrCode
0x180013b37  call    cs:__imp_SetLastError
0x180013b3e  nop     dword ptr [rax+rax+00h]
0x180013b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b4a  cmp     rcx, r14
0x180013b4d  jz      short loc_180013B6F
0x180013b4f  test    [rcx+1Ch], edi
0x180013b52  jz      short loc_180013B6F
0x180013b54  cmp     byte ptr [rcx+19h], 2
0x180013b58  jb      short loc_180013B6F
0x180013b5a  mov     edx, 91h
0x180013b5f  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180013b66  mov     rcx, [rcx+10h]
0x180013b6a  call    WPP_SF_
0x180013b6f  xor     eax, eax
0x180013b71  add     rsp, 58h
0x180013b75  pop     r14
0x180013b77  pop     rdi
0x180013b78  pop     rsi
0x180013b79  pop     rbx
0x180013b7a  retn
```

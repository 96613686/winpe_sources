# DeinitSecUtils

- ea: `0x180004fa0`
- end: `0x180005108`
- name: `DeinitSecUtils`
- size: `360`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008b00`

## callees

- `0x180004b80`
- `0x180004f00`
- `0x180004fa0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050b4`

## pseudocode

```c
__int64 DeinitSecUtils()
{
  PVOID *v0; // rcx
  __int64 result; // rax
  unsigned int v2; // edi
  __int64 i; // rbx
  __int64 j; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = *(_QWORD *)&g_pSecurity;
  if ( *(_QWORD *)&g_pSecurity )
  {
    v2 = 0;
    for ( i = 0; i != 20; ++i )
    {
      if ( *(_QWORD *)(result + 8 * (i + 15)) )
      {
        FreeMemory(result + 8 * (i + 15), "DeinitSecUtils", 784);
        result = *(_QWORD *)&g_pSecurity;
      }
    }
    for ( j = 0; j != 10; ++j )
    {
      v5 = *(_QWORD *)(result + 8 * j);
      if ( v5 )
      {
        FreeWellKnownSid(v5);
        result = *(_QWORD *)&g_pSecurity;
        *(_QWORD *)(*(_QWORD *)&g_pSecurity + 8 * j) = 0;
      }
    }
    result = FreeWellKnownSid(*(_QWORD *)(result + 416));
    v6 = *(_QWORD *)&g_pSecurity;
    *(_QWORD *)(*(_QWORD *)&g_pSecurity + 416LL) = 0;
    if ( *(_DWORD *)(v6 + 408) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 368));
      result = *(_QWORD *)&g_pSecurity;
      *(_DWORD *)(*(_QWORD *)&g_pSecurity + 408LL) = 0;
    }
    *(_QWORD *)&g_pSecurity = 0;
    goto LABEL_19;
  }
  if ( v0 == &WPP_GLOBAL_Control )
    return result;
  v2 = 5023;
  if ( (*((_BYTE *)v0 + 28) & 4) != 0 )
  {
    result = WPP_SF_L(v0[2], 83, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 5023);
LABEL_19:
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
    return WPP_SF_L(v0[2], 84, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v2);
  return result;
}

```

## disassembly

```asm
0x180004fa0  push    rbp
0x180004fa2  sub     rsp, 20h
0x180004fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fad  lea     rbp, WPP_GLOBAL_Control
0x180004fb4  cmp     rcx, rbp
0x180004fb7  jz      short loc_180004FDB
0x180004fb9  test    byte ptr [rcx+1Ch], 8
0x180004fbd  jz      short loc_180004FDB
0x180004fbf  mov     rcx, [rcx+10h]
0x180004fc3  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004fca  mov     edx, 52h ; 'R'
0x180004fcf  call    WPP_SF_
0x180004fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fdb  mov     rax, cs:g_pSecurity
0x180004fe2  mov     [rsp+28h+arg_10], rdi
0x180004fe7  test    rax, rax
0x180004fea  jnz     short loc_180005021
0x180004fec  cmp     rcx, rbp
0x180004fef  jz      loc_1800050FD
0x180004ff5  test    byte ptr [rcx+1Ch], 4
0x180004ff9  mov     edi, 139Fh
0x180004ffe  jz      loc_1800050DA
0x180005004  mov     rcx, [rcx+10h]
0x180005008  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000500f  mov     edx, 53h ; 'S'
0x180005014  mov     r9d, edi
0x180005017  call    WPP_SF_L
0x18000501c  jmp     loc_1800050D3
0x180005021  mov     [rsp+28h+arg_0], rbx
0x180005026  mov     [rsp+28h+arg_8], rsi
0x18000502b  xor     esi, esi
0x18000502d  mov     edi, esi
0x18000502f  mov     ebx, esi
0x180005031  lea     rcx, [rbx+0Fh]
0x180005035  cmp     [rax+rcx*8], rsi
0x180005039  lea     rcx, [rax+rcx*8]
0x18000503d  jz      short loc_180005058
0x18000503f  mov     r8d, 310h
0x180005045  lea     rdx, aDeinitsecutils_0; "DeinitSecUtils"
0x18000504c  call    FreeMemory
0x180005051  mov     rax, cs:g_pSecurity
0x180005058  inc     rbx
0x18000505b  cmp     rbx, 14h
0x18000505f  jnz     short loc_180005031
0x180005061  mov     rbx, rsi
0x180005064  mov     rcx, [rax+rbx*8]
0x180005068  test    rcx, rcx
0x18000506b  jz      short loc_18000507D
0x18000506d  call    FreeWellKnownSid
0x180005072  mov     rax, cs:g_pSecurity
0x180005079  mov     [rax+rbx*8], rsi
0x18000507d  inc     rbx
0x180005080  cmp     rbx, 0Ah
0x180005084  jnz     short loc_180005064
0x180005086  mov     rcx, [rax+1A0h]
0x18000508d  mov     rbx, [rsp+28h+arg_0]
0x180005092  call    FreeWellKnownSid
0x180005097  mov     rcx, cs:g_pSecurity
0x18000509e  mov     [rcx+1A0h], rsi
0x1800050a5  cmp     [rcx+198h], esi
0x1800050ab  jz      short loc_1800050C7
0x1800050ad  add     rcx, 170h; lpCriticalSection
0x1800050b4  call    cs:__imp_DeleteCriticalSection
0x1800050ba  mov     rax, cs:g_pSecurity
0x1800050c1  mov     [rax+198h], esi
0x1800050c7  mov     cs:g_pSecurity, rsi
0x1800050ce  mov     rsi, [rsp+28h+arg_8]
0x1800050d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050da  cmp     rcx, rbp
0x1800050dd  jz      short loc_1800050FD
0x1800050df  test    byte ptr [rcx+1Ch], 8
0x1800050e3  jz      short loc_1800050FD
0x1800050e5  mov     rcx, [rcx+10h]
0x1800050e9  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800050f0  mov     edx, 54h ; 'T'
0x1800050f5  mov     r9d, edi
0x1800050f8  call    WPP_SF_L
0x1800050fd  mov     rdi, [rsp+28h+arg_10]
0x180005102  add     rsp, 20h
0x180005106  pop     rbp
0x180005107  retn
```

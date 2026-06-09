# VerifyRpcClientAccess

- ea: `0x180001130`
- end: `0x1800013c2`
- name: `VerifyRpcClientAccess`
- size: `658`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001130`
- `0x1800013d0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001199`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000121f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000121f`

## pseudocode

```c
__int64 __fastcall VerifyRpcClientAccess(unsigned int a1)
{
  __int64 v1; // rsi
  PVOID *v2; // rcx
  int v3; // edi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v7; // rdx
  __int64 v8; // r9

  v1 = a1;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_(v2[2], 72, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v3 = 0;
  if ( *(_QWORD *)&g_pSecurity )
  {
    v4 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v3 = 1;
LABEL_9:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v4 = 5023;
  if ( v2 == &WPP_GLOBAL_Control )
    goto LABEL_20;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    WPP_SF_L(v2[2], 73, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 5023);
    goto LABEL_9;
  }
LABEL_10:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_L(v2[2], 74, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      goto LABEL_20;
    if ( (*((_BYTE *)v2 + 28) & 4) == 0 )
      goto LABEL_17;
    v7 = 111;
    goto LABEL_39;
  }
  if ( (unsigned int)v1 < 0x14 )
  {
    v5 = VerifyRpcClientAccessToSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(*(_QWORD *)&g_pSecurity + 8 * v1 + 120));
    v4 = v5;
    if ( !v5 )
    {
LABEL_16:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_20;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_17;
    v7 = 113;
    v8 = v5;
LABEL_32:
    WPP_SF_L(v2[2], v7, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v8);
    goto LABEL_16;
  }
  v4 = 87;
  if ( v2 == &WPP_GLOBAL_Control )
    goto LABEL_20;
  if ( (*((_BYTE *)v2 + 28) & 4) != 0 )
  {
    v7 = 112;
LABEL_39:
    v8 = v4;
    goto LABEL_32;
  }
LABEL_17:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    WPP_SF_(v2[2], 75, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v3 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&g_pSecurity + 368LL));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_L(v2[2], 76, WPP_fd6184a389643c6486807174a58ed414_Traceguids, 0);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_L(v2[2], 114, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180001130  push    r14
0x180001132  sub     rsp, 20h
0x180001136  mov     [rsp+28h+arg_8], rbp
0x18000113b  mov     ebp, edx
0x18000113d  mov     [rsp+28h+arg_10], rsi
0x180001142  mov     [rsp+28h+arg_18], rdi
0x180001147  mov     esi, ecx
0x180001149  mov     rcx, cs:WPP_GLOBAL_Control
0x180001150  lea     r14, WPP_GLOBAL_Control
0x180001157  cmp     rcx, r14
0x18000115a  jz      short loc_180001175
0x18000115c  test    byte ptr [rcx+1Ch], 8
0x180001160  jnz     loc_1800012C5
0x180001166  cmp     rcx, r14
0x180001169  jz      short loc_180001175
0x18000116b  test    byte ptr [rcx+1Ch], 8
0x18000116f  jnz     loc_1800012E6
0x180001175  xor     edi, edi
0x180001177  mov     [rsp+28h+arg_0], rbx
0x18000117c  cmp     cs:g_pSecurity, rdi
0x180001183  jz      loc_180001307
0x180001189  mov     rcx, cs:g_pSecurity
0x180001190  mov     ebx, edi
0x180001192  add     rcx, 170h; lpCriticalSection
0x180001199  call    cs:__imp_EnterCriticalSection
0x18000119f  mov     edi, 1
0x1800011a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011ab  cmp     rcx, r14
0x1800011ae  jz      short loc_1800011BA
0x1800011b0  test    byte ptr [rcx+1Ch], 8
0x1800011b4  jnz     loc_1800012A1
0x1800011ba  test    ebx, ebx
0x1800011bc  jnz     loc_18000133C
0x1800011c2  cmp     esi, 14h
0x1800011c5  jnb     loc_180001363
0x1800011cb  mov     rcx, cs:g_pSecurity
0x1800011d2  mov     edx, ebp
0x1800011d4  mov     rcx, [rcx+rsi*8+78h]; pSecurityDescriptor
0x1800011d9  call    VerifyRpcClientAccessToSecurityDescriptor
0x1800011de  mov     ebx, eax
0x1800011e0  test    eax, eax
0x1800011e2  jnz     loc_18000126E
0x1800011e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011ef  cmp     rcx, r14
0x1800011f2  jz      short loc_1800011FE
0x1800011f4  test    byte ptr [rcx+1Ch], 8
0x1800011f8  jnz     loc_18000137D
0x1800011fe  mov     rsi, [rsp+28h+arg_10]
0x180001203  test    edi, edi
0x180001205  mov     rdi, [rsp+28h+arg_18]
0x18000120a  mov     rbp, [rsp+28h+arg_8]
0x18000120f  jz      short loc_18000122C
0x180001211  mov     rcx, cs:g_pSecurity
0x180001218  add     rcx, 170h; lpCriticalSection
0x18000121f  call    cs:__imp_LeaveCriticalSection
0x180001225  mov     rcx, cs:WPP_GLOBAL_Control
0x18000122c  cmp     rcx, r14
0x18000122f  jz      short loc_180001240
0x180001231  test    byte ptr [rcx+1Ch], 8
0x180001235  jnz     loc_18000139E
0x18000123b  cmp     rcx, r14
0x18000123e  jnz     short loc_18000124E
0x180001240  mov     eax, ebx
0x180001242  mov     rbx, [rsp+28h+arg_0]
0x180001247  add     rsp, 20h
0x18000124b  pop     r14
0x18000124d  retn
0x18000124e  test    byte ptr [rcx+1Ch], 8
0x180001252  jz      short loc_180001240
0x180001254  mov     rcx, [rcx+10h]
0x180001258  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000125f  mov     edx, 72h ; 'r'
0x180001264  mov     r9d, ebx
0x180001267  call    WPP_SF_L
0x18000126c  jmp     short loc_180001240
0x18000126e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001275  cmp     rcx, r14
0x180001278  jz      short loc_1800011FE
0x18000127a  test    byte ptr [rcx+1Ch], 4
0x18000127e  jz      loc_1800011EF
0x180001284  mov     edx, 71h ; 'q'
0x180001289  mov     r9d, eax
0x18000128c  mov     rcx, [rcx+10h]
0x180001290  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001297  call    WPP_SF_L
0x18000129c  jmp     loc_1800011E8
0x1800012a1  mov     rcx, [rcx+10h]
0x1800012a5  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800012ac  mov     edx, 4Ah ; 'J'
0x1800012b1  mov     r9d, ebx
0x1800012b4  call    WPP_SF_L
0x1800012b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012c0  jmp     loc_1800011BA
0x1800012c5  mov     rcx, [rcx+10h]
0x1800012c9  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800012d0  mov     edx, 6Eh ; 'n'
0x1800012d5  call    WPP_SF_
0x1800012da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012e1  jmp     loc_180001166
0x1800012e6  mov     rcx, [rcx+10h]
0x1800012ea  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800012f1  mov     edx, 48h ; 'H'
0x1800012f6  call    WPP_SF_
0x1800012fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180001302  jmp     loc_180001175
0x180001307  mov     ebx, 139Fh
0x18000130c  cmp     rcx, r14
0x18000130f  jz      loc_1800011FE
0x180001315  test    byte ptr [rcx+1Ch], 4
0x180001319  jz      loc_1800011AB
0x18000131f  mov     rcx, [rcx+10h]
0x180001323  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000132a  mov     edx, 49h ; 'I'
0x18000132f  mov     r9d, ebx
0x180001332  call    WPP_SF_L
0x180001337  jmp     loc_1800011A4
0x18000133c  cmp     rcx, r14
0x18000133f  jz      loc_1800011FE
0x180001345  test    byte ptr [rcx+1Ch], 4
0x180001349  jz      loc_1800011EF
0x18000134f  mov     edx, 6Fh ; 'o'
0x180001354  jmp     short loc_18000135B
0x180001356  mov     edx, 70h ; 'p'
0x18000135b  mov     r9d, ebx
0x18000135e  jmp     loc_18000128C
0x180001363  mov     ebx, 57h ; 'W'
0x180001368  cmp     rcx, r14
0x18000136b  jz      loc_1800011FE
0x180001371  test    byte ptr [rcx+1Ch], 4
0x180001375  jz      loc_1800011EF
0x18000137b  jmp     short loc_180001356
0x18000137d  mov     rcx, [rcx+10h]
0x180001381  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180001388  mov     edx, 4Bh ; 'K'
0x18000138d  call    WPP_SF_
0x180001392  mov     rcx, cs:WPP_GLOBAL_Control
0x180001399  jmp     loc_1800011FE
0x18000139e  mov     rcx, [rcx+10h]
0x1800013a2  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800013a9  mov     edx, 4Ch ; 'L'
0x1800013ae  xor     r9d, r9d
0x1800013b1  call    WPP_SF_L
0x1800013b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013bd  jmp     loc_18000123B
```

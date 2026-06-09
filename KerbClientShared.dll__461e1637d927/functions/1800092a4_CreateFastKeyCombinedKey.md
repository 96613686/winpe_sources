# CreateFastKeyCombinedKey

- ea: `0x1800092a4`
- end: `0x1800093bb`
- name: `CreateFastKeyCombinedKey`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015ce0`
- `0x180015dd0`

## callees

- `0x1800092a4`
- `0x1800095d0`
- `0x180016090`
- `0x180029010`

## import_xrefs

- `cryptdll!KRBFXCF2` at `0x18000932f`
- `cryptdll!KRBFXCF2` at `0x18000932f`

## pseudocode

```c
__int64 __fastcall CreateFastKeyCombinedKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  void *v9; // rsi
  int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  int v17; // ecx
  __int64 v19; // [rsp+20h] [rbp-68h]
  __int64 v20; // [rsp+28h] [rbp-60h]
  __int64 v21; // [rsp+30h] [rbp-58h]

  v9 = (void *)((__int64 (__fastcall *)(_QWORD))qword_1800334A0)(*(unsigned int *)(a1 + 16));
  if ( v9 )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(a4 + v12) );
    do
      ++v11;
    while ( *(_BYTE *)(a3 + v11) );
    v10 = KRBFXCF2(
            *(unsigned int *)(a1 + 12),
            *(_QWORD *)(a1 + 24),
            *(unsigned int *)(a1 + 16),
            a3,
            v11,
            *(_DWORD *)(a2 + 12),
            *(_QWORD *)(a2 + 24),
            *(_DWORD *)(a2 + 16),
            a4,
            v12,
            v9);
    if ( v10 >= 0 )
    {
      v16 = *(_DWORD *)(a1 + 12);
      v17 = *(_DWORD *)(a1 + 16);
      *(_QWORD *)a5 = 0;
      *(_DWORD *)(a5 + 20) = 0;
      *(_QWORD *)(a5 + 32) = 0;
      *(_DWORD *)(a5 + 12) = v16;
      *(_DWORD *)(a5 + 16) = v17;
      *(_QWORD *)(a5 + 24) = v9;
      *(_DWORD *)(a5 + 8) = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(v21) = *(_DWORD *)(a2 + 12);
        LODWORD(v20) = *(_DWORD *)(a1 + 12);
        LODWORD(v19) = v10;
        WPP_SF_sDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v15, v19, v20, v21);
      }
      KerbClientFree(v9);
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800092a4  push    rbx
0x1800092a6  push    rbp
0x1800092a7  push    rsi
0x1800092a8  push    rdi
0x1800092a9  push    r14
0x1800092ab  sub     rsp, 60h
0x1800092af  mov     rax, cs:qword_1800334A0
0x1800092b6  mov     rdi, rcx
0x1800092b9  mov     ecx, [rcx+10h]
0x1800092bc  mov     rbx, r9
0x1800092bf  mov     r14, r8
0x1800092c2  mov     rbp, rdx
0x1800092c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ca  mov     rsi, rax
0x1800092cd  test    rax, rax
0x1800092d0  jnz     short loc_1800092DC
0x1800092d2  mov     ebx, 0C0000017h
0x1800092d7  jmp     loc_1800093AE
0x1800092dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800092e0  mov     rcx, rax
0x1800092e3  inc     rcx
0x1800092e6  cmp     byte ptr [rbx+rcx], 0
0x1800092ea  jnz     short loc_1800092E3
0x1800092ec  mov     edx, [rbp+10h]
0x1800092ef  mov     r8, [rbp+18h]
0x1800092f3  mov     r9d, [rbp+0Ch]
0x1800092f7  inc     rax
0x1800092fa  cmp     byte ptr [r14+rax], 0
0x1800092ff  jnz     short loc_1800092F7
0x180009301  mov     [rsp+88h+var_38], rsi
0x180009306  mov     [rsp+88h+var_40], ecx
0x18000930a  mov     ecx, [rdi+0Ch]
0x18000930d  mov     [rsp+88h+var_48], rbx
0x180009312  mov     [rsp+88h+var_50], edx
0x180009316  mov     rdx, [rdi+18h]
0x18000931a  mov     [rsp+88h+var_58], r8
0x18000931f  mov     r8d, [rdi+10h]
0x180009323  mov     dword ptr [rsp+88h+var_60], r9d
0x180009328  mov     r9, r14
0x18000932b  mov     dword ptr [rsp+88h+var_68], eax
0x18000932f  call    cs:__imp_KRBFXCF2
0x180009335  mov     ebx, eax
0x180009337  test    eax, eax
0x180009339  jns     short loc_180009379
0x18000933b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009342  lea     rax, WPP_GLOBAL_Control
0x180009349  cmp     rcx, rax
0x18000934c  jz      short loc_18000936F
0x18000934e  test    byte ptr [rcx+1Ch], 1
0x180009352  jz      short loc_18000936F
0x180009354  mov     eax, [rbp+0Ch]
0x180009357  mov     rcx, [rcx+10h]
0x18000935b  mov     dword ptr [rsp+88h+var_58], eax
0x18000935f  mov     eax, [rdi+0Ch]
0x180009362  mov     dword ptr [rsp+88h+var_60], eax
0x180009366  mov     dword ptr [rsp+88h+var_68], ebx
0x18000936a  call    WPP_SF_sDdd
0x18000936f  mov     rcx, rsi; void *
0x180009372  call    ?KerbClientFree@@YAXPEAX@Z; KerbClientFree(void *)
0x180009377  jmp     short loc_1800093AE
0x180009379  mov     rdx, [rsp+88h+arg_20]
0x180009381  mov     eax, [rdi+0Ch]
0x180009384  mov     ecx, [rdi+10h]
0x180009387  mov     qword ptr [rdx], 0
0x18000938e  mov     dword ptr [rdx+14h], 0
0x180009395  mov     qword ptr [rdx+20h], 0
0x18000939d  mov     [rdx+0Ch], eax
0x1800093a0  mov     [rdx+10h], ecx
0x1800093a3  mov     [rdx+18h], rsi
0x1800093a7  mov     dword ptr [rdx+8], 1
0x1800093ae  mov     eax, ebx
0x1800093b0  add     rsp, 60h
0x1800093b4  pop     r14
0x1800093b6  pop     rdi
0x1800093b7  pop     rsi
0x1800093b8  pop     rbp
0x1800093b9  pop     rbx
0x1800093ba  retn
```

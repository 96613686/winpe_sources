# UbpmpMaintenanceTaskIsCritical

- ea: `0x180015c7c`
- end: `0x180015e16`
- name: `UbpmpMaintenanceTaskIsCritical`
- size: `410`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016b50`
- `0x18002ee00`
- `0x180030914`

## callees

- `0x180015c7c`
- `0x1800166b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015d49`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015dd7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015d49`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180015dd7`

## pseudocode

```c
char __fastcall UbpmpMaintenanceTaskIsCritical(__int64 a1)
{
  unsigned __int16 i; // bx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx
  const WCHAR *v6; // rdi
  const WCHAR *lpString2; // rbp
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 cchCount2; // r9
  int v11; // eax
  PCNZWCH v13; // rdi
  const WCHAR *v14; // rbp
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // r9
  int v18; // eax

  for ( i = 0; ; ++i )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (unsigned int)i >= *(_DWORD *)(v3 + 32) )
      break;
    v4 = *(_QWORD *)(v3 + 40);
    if ( *(_DWORD *)(v4 + 40LL * i + 16) == 1 )
    {
      v5 = *(_QWORD *)(v4 + 40LL * i + 24);
      if ( *(_DWORD *)v5 == 2 )
      {
        if ( (unsigned int)UbpmpIsCriticalAction(*(UUID **)(v5 + 8)) )
          return 1;
      }
    }
  }
  v6 = g_CriticalMaintenanceTasks;
  if ( g_CriticalMaintenanceTasks )
  {
    lpString2 = *(const WCHAR **)(v3 + 8);
    if ( lpString2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( lpString2[v8] );
      while ( *v6 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        if ( (unsigned int)v8 >= (unsigned int)v9 )
        {
          cchCount2 = (unsigned int)(v9 - 1);
          if ( v6[cchCount2] == 42 )
          {
            v11 = CompareStringW(0x7Fu, 1u, v6, cchCount2, lpString2, cchCount2);
          }
          else
          {
            if ( (_DWORD)v8 != (_DWORD)v9 )
              goto LABEL_15;
            v11 = CompareStringW(0x7Fu, 1u, v6, v9, lpString2, v8);
          }
          if ( v11 == 2 )
            return 1;
        }
LABEL_15:
        v6 += (unsigned int)(v9 + 1);
      }
    }
  }
  v13 = g_CriticalTasks;
  if ( g_CriticalTasks )
  {
    v14 = *(const WCHAR **)(*(_QWORD *)(a1 + 24) + 8LL);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      while ( 1 )
      {
        if ( !*v13 )
          return 0;
        v16 = -1;
        do
          ++v16;
        while ( v13[v16] );
        if ( (unsigned int)v15 >= (unsigned int)v16 )
        {
          v17 = (unsigned int)(v16 - 1);
          if ( v13[v17] == 42 )
          {
            v18 = CompareStringW(0x7Fu, 1u, v13, v17, v14, v17);
          }
          else
          {
            if ( (_DWORD)v15 != (_DWORD)v16 )
              goto LABEL_28;
            v18 = CompareStringW(0x7Fu, 1u, v13, v16, v14, v15);
          }
          if ( v18 == 2 )
            return 1;
        }
LABEL_28:
        v13 += (unsigned int)(v16 + 1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015c7c  push    rbx
0x180015c7e  push    rbp
0x180015c7f  push    rsi
0x180015c80  push    rdi
0x180015c81  push    r12
0x180015c83  push    r13
0x180015c85  push    r14
0x180015c87  push    r15
0x180015c89  sub     rsp, 38h
0x180015c8d  xor     r15d, r15d
0x180015c90  mov     r14, rcx
0x180015c93  mov     ebx, r15d
0x180015c96  lea     r12d, [r15+1]
0x180015c9a  mov     rdx, [r14+18h]
0x180015c9e  movzx   eax, bx
0x180015ca1  cmp     eax, [rdx+20h]
0x180015ca4  jnb     short loc_180015CD9
0x180015ca6  movzx   eax, bx
0x180015ca9  lea     rcx, [rax+rax*4]
0x180015cad  mov     rax, [rdx+28h]
0x180015cb1  cmp     [rax+rcx*8+10h], r12d
0x180015cb6  jnz     short loc_180015CD3
0x180015cb8  mov     rcx, [rax+rcx*8+18h]
0x180015cbd  cmp     dword ptr [rcx], 2
0x180015cc0  jnz     short loc_180015CD3
0x180015cc2  mov     rcx, [rcx+8]; Uuid2
0x180015cc6  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x180015ccb  test    eax, eax
0x180015ccd  jnz     loc_180015D5A
0x180015cd3  add     bx, r12w
0x180015cd7  jmp     short loc_180015C9A
0x180015cd9  mov     rdi, cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x180015ce0  or      r13, 0FFFFFFFFFFFFFFFFh
0x180015ce4  test    rdi, rdi
0x180015ce7  jz      loc_180015D6F
0x180015ced  mov     rbp, [rdx+8]
0x180015cf1  test    rbp, rbp
0x180015cf4  jz      short loc_180015D6F
0x180015cf6  mov     rsi, r13
0x180015cf9  inc     rsi
0x180015cfc  cmp     [rbp+rsi*2+0], r15w
0x180015d02  jnz     short loc_180015CF9
0x180015d04  cmp     [rdi], r15w
0x180015d08  jz      short loc_180015D6F
0x180015d0a  mov     rbx, r13
0x180015d0d  inc     rbx
0x180015d10  cmp     [rdi+rbx*2], r15w
0x180015d15  jnz     short loc_180015D0D
0x180015d17  cmp     esi, ebx
0x180015d19  jnb     short loc_180015D24
0x180015d1b  lea     eax, [rbx+1]
0x180015d1e  lea     rdi, [rdi+rax*2]
0x180015d22  jmp     short loc_180015D04
0x180015d24  lea     r9d, [rbx-1]; cchCount1
0x180015d28  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180015d2e  jnz     loc_180015DF5
0x180015d34  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180015d39  mov     r8, rdi; lpString1
0x180015d3c  mov     [rsp+78h+lpString2], rbp; lpString2
0x180015d41  mov     edx, r12d; dwCmpFlags
0x180015d44  mov     ecx, 7Fh; Locale
0x180015d49  call    cs:__imp_CompareStringW
0x180015d50  nop     dword ptr [rax+rax+00h]
0x180015d55  cmp     eax, 2
0x180015d58  jnz     short loc_180015D1B
0x180015d5a  mov     al, r12b
0x180015d5d  add     rsp, 38h
0x180015d61  pop     r15
0x180015d63  pop     r14
0x180015d65  pop     r13
0x180015d67  pop     r12
0x180015d69  pop     rdi
0x180015d6a  pop     rsi
0x180015d6b  pop     rbp
0x180015d6c  pop     rbx
0x180015d6d  retn
0x180015d6f  mov     rdi, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180015d76  test    rdi, rdi
0x180015d79  jz      short loc_180015DEE
0x180015d7b  mov     rax, [r14+18h]
0x180015d7f  mov     rbp, [rax+8]
0x180015d83  test    rbp, rbp
0x180015d86  jz      short loc_180015DEE
0x180015d88  mov     rsi, r13
0x180015d8b  inc     rsi
0x180015d8e  cmp     [rbp+rsi*2+0], r15w
0x180015d94  jnz     short loc_180015D8B
0x180015d96  cmp     [rdi], r15w
0x180015d9a  jz      short loc_180015DEE
0x180015d9c  mov     rbx, r13
0x180015d9f  inc     rbx
0x180015da2  cmp     [rdi+rbx*2], r15w
0x180015da7  jnz     short loc_180015D9F
0x180015da9  cmp     esi, ebx
0x180015dab  jnb     short loc_180015DB6
0x180015dad  lea     eax, [rbx+1]
0x180015db0  lea     rdi, [rdi+rax*2]
0x180015db4  jmp     short loc_180015D96
0x180015db6  lea     r9d, [rbx-1]; cchCount1
0x180015dba  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180015dc0  jnz     short loc_180015E09
0x180015dc2  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180015dc7  mov     r8, rdi; lpString1
0x180015dca  mov     [rsp+78h+lpString2], rbp; lpString2
0x180015dcf  mov     edx, r12d; dwCmpFlags
0x180015dd2  mov     ecx, 7Fh; Locale
0x180015dd7  call    cs:__imp_CompareStringW
0x180015dde  nop     dword ptr [rax+rax+00h]
0x180015de3  cmp     eax, 2
0x180015de6  jz      loc_180015D5A
0x180015dec  jmp     short loc_180015DAD
0x180015dee  xor     al, al
0x180015df0  jmp     loc_180015D5D
0x180015df5  cmp     esi, ebx
0x180015df7  jnz     loc_180015D1B
0x180015dfd  mov     [rsp+78h+cchCount2], esi
0x180015e01  mov     r9d, ebx
0x180015e04  jmp     loc_180015D39
0x180015e09  cmp     esi, ebx
0x180015e0b  jnz     short loc_180015DAD
0x180015e0d  mov     [rsp+78h+cchCount2], esi
0x180015e11  mov     r9d, ebx
0x180015e14  jmp     short loc_180015DC7
```

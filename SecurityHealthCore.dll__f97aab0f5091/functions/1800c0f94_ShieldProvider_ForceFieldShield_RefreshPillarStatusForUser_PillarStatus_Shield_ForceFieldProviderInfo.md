# ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(PillarStatus *,Shield_ForceFieldProviderInfo * *)

- ea: `0x1800c0f94`
- end: `0x1800c1219`
- name: `?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAUPillarStatus@@PEAPEAUShield_ForceFieldProviderInfo@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this, struct PillarStatus *, struct Shield_ForceFieldProviderInfo **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800c0e30`

## callees

- `0x1800be7ac`
- `0x1800bebd8`
- `0x1800bf3c0`
- `0x1800c0f94`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800c1062`
- `ole32!CoTaskMemFree` at `0x1800c106c`
- `ole32!CoTaskMemFree` at `0x1800c1076`
- `ole32!CoTaskMemFree` at `0x1800c107f`
- `ole32!CoTaskMemFree` at `0x1800c10e4`
- `ole32!CoTaskMemFree` at `0x1800c10ee`
- `ole32!CoTaskMemFree` at `0x1800c10f8`
- `ole32!CoTaskMemFree` at `0x1800c1101`
- `ole32!CoTaskMemFree` at `0x1800c1177`
- `ole32!CoTaskMemFree` at `0x1800c1186`
- `ole32!CoTaskMemFree` at `0x1800c1195`
- `ole32!CoTaskMemFree` at `0x1800c11a8`
- `ole32!CoTaskMemFree` at `0x1800c11dc`
- `ole32!CoTaskMemFree` at `0x1800c11e6`
- `ole32!CoTaskMemFree` at `0x1800c11f0`
- `ole32!CoTaskMemFree` at `0x1800c11f9`
- `ole32!CoTaskMemFree` at `0x1800c1062`
- `ole32!CoTaskMemFree` at `0x1800c106c`
- `ole32!CoTaskMemFree` at `0x1800c1076`
- `ole32!CoTaskMemFree` at `0x1800c107f`
- `ole32!CoTaskMemFree` at `0x1800c10e4`
- `ole32!CoTaskMemFree` at `0x1800c10ee`
- `ole32!CoTaskMemFree` at `0x1800c10f8`
- `ole32!CoTaskMemFree` at `0x1800c1101`
- `ole32!CoTaskMemFree` at `0x1800c1177`
- `ole32!CoTaskMemFree` at `0x1800c1186`
- `ole32!CoTaskMemFree` at `0x1800c1195`
- `ole32!CoTaskMemFree` at `0x1800c11a8`
- `ole32!CoTaskMemFree` at `0x1800c11dc`
- `ole32!CoTaskMemFree` at `0x1800c11e6`
- `ole32!CoTaskMemFree` at `0x1800c11f0`
- `ole32!CoTaskMemFree` at `0x1800c11f9`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(
        ShieldProvider::ForceFieldShield *this,
        struct PillarStatus *a2,
        struct Shield_ForceFieldProviderInfo **a3)
{
  struct Shield_ForceFieldProviderInfo **v3; // r14
  LPVOID *v4; // rdi
  unsigned int v7; // ebx
  int v8; // esi
  int v9; // r15d
  unsigned int v10; // r14d
  char *v11; // rbx
  unsigned int i; // r14d
  unsigned __int64 v13; // rbx
  int v15; // [rsp+20h] [rbp-20h]
  LPVOID pv; // [rsp+28h] [rbp-18h] BYREF
  struct Shield_ForceFieldProviderInfo *v17[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+40h] BYREF
  struct Shield_ForceFieldProviderInfo **v19; // [rsp+90h] [rbp+50h]
  int v20; // [rsp+98h] [rbp+58h] BYREF

  v19 = a3;
  v3 = a3;
  *(_QWORD *)a2 = 0;
  v4 = 0;
  *a3 = 0;
  v17[0] = 0;
  v18 = 0;
  pv = 0;
  v15 = (*(__int64 (__fastcall **)(ShieldProvider::ForceFieldShield *, unsigned int *, LPVOID *))(*(_QWORD *)this + 72LL))(
          this,
          &v18,
          &pv);
  v7 = v15;
  if ( v15 < 0 )
    return v7;
  v8 = 1;
  v9 = 138;
  if ( !v18 )
    goto LABEL_27;
  v10 = 0;
  do
  {
    v11 = (char *)pv + 64 * (unsigned __int64)v10;
    if ( !*((_DWORD *)v11 + 12) )
      goto LABEL_23;
    v20 = 0;
    ShieldProvider::ForceFieldShield::GetIsWarningStateDismissedForUser(
      this,
      (char *)pv + 64 * (unsigned __int64)v10,
      140,
      &v20);
    if ( *((_DWORD *)v11 + 13) == 3 )
    {
      if ( v8 < 8 )
      {
        v8 = 8;
        v9 = 141;
        if ( v4 )
        {
          CoTaskMemFree(v4[2]);
          CoTaskMemFree(v4[3]);
          CoTaskMemFree(v4[4]);
          CoTaskMemFree(v4);
          v17[0] = 0;
        }
        ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(
          (struct Shield_ForceFieldProviderInfo *)v11,
          v17);
        v4 = (LPVOID *)v17[0];
      }
LABEL_21:
      if ( v20 )
        ShieldProvider::ForceFieldShield::ChangeWarningStateDismissalForUser(this, v11, 140, 0);
      goto LABEL_23;
    }
    if ( *((_DWORD *)v11 + 13) != 2 )
    {
      if ( *((_DWORD *)v11 + 13) != 1 )
        goto LABEL_23;
      if ( v8 < 2 )
      {
        v8 = 2;
        v9 = 139;
      }
      goto LABEL_21;
    }
    if ( v20 )
    {
      if ( v8 < 2 )
      {
        v8 = 2;
        v9 = 139;
      }
    }
    else if ( v8 < 4 )
    {
      v8 = 4;
      v9 = 140;
      if ( v4 )
      {
        CoTaskMemFree(v4[2]);
        CoTaskMemFree(v4[3]);
        CoTaskMemFree(v4[4]);
        CoTaskMemFree(v4);
        v17[0] = 0;
      }
      ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(
        (struct Shield_ForceFieldProviderInfo *)v11,
        v17);
      v4 = (LPVOID *)v17[0];
    }
LABEL_23:
    ++v10;
  }
  while ( v10 < v18 );
  for ( i = 0; i < v18; ++i )
  {
    v13 = (unsigned __int64)i << 6;
    CoTaskMemFree(*(LPVOID *)((char *)pv + v13 + 16));
    CoTaskMemFree(*(LPVOID *)((char *)pv + v13 + 24));
    CoTaskMemFree(*(LPVOID *)((char *)pv + v13 + 32));
  }
  CoTaskMemFree(pv);
  v7 = v15;
  v3 = v19;
  pv = 0;
LABEL_27:
  *(_DWORD *)a2 = v9;
  *((_DWORD *)a2 + 1) = v8;
  if ( v4 )
    *v3 = (struct Shield_ForceFieldProviderInfo *)v4;
  return v7;
}

```

## disassembly

```asm
0x1800c0f94  mov     [rsp-38h+arg_8], rbx
0x1800c0f99  mov     [rsp-38h+arg_10], r8
0x1800c0f9e  push    rbp
0x1800c0f9f  push    rsi
0x1800c0fa0  push    rdi
0x1800c0fa1  push    r12
0x1800c0fa3  push    r13
0x1800c0fa5  push    r14
0x1800c0fa7  push    r15
0x1800c0fa9  mov     rbp, rsp
0x1800c0fac  sub     rsp, 40h
0x1800c0fb0  xor     eax, eax
0x1800c0fb2  mov     r14, r8
0x1800c0fb5  mov     [rdx], rax
0x1800c0fb8  mov     edi, eax
0x1800c0fba  mov     [r8], rax
0x1800c0fbd  mov     r12, rdx
0x1800c0fc0  mov     [rbp+var_10], rax
0x1800c0fc4  lea     r8, [rbp+pv]
0x1800c0fc8  mov     [rbp+arg_0], eax
0x1800c0fcb  lea     rdx, [rbp+arg_0]
0x1800c0fcf  mov     [rbp+pv], rax
0x1800c0fd3  mov     r13, rcx
0x1800c0fd6  mov     rax, [rcx]
0x1800c0fd9  mov     rax, [rax+48h]
0x1800c0fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0fe2  mov     [rbp+var_20], eax
0x1800c0fe5  mov     ebx, eax
0x1800c0fe7  test    eax, eax
0x1800c0fe9  js      loc_1800C11D3
0x1800c0fef  mov     ecx, [rbp+arg_0]
0x1800c0ff2  lea     esi, [rdi+1]
0x1800c0ff5  mov     r15d, 8Ah
0x1800c0ffb  test    ecx, ecx
0x1800c0ffd  jz      loc_1800C11BD
0x1800c1003  xor     r14d, r14d
0x1800c1006  test    ecx, ecx
0x1800c1008  jz      loc_1800C115E
0x1800c100e  mov     ebx, r14d
0x1800c1011  shl     rbx, 6
0x1800c1015  add     rbx, [rbp+pv]
0x1800c1019  cmp     dword ptr [rbx+30h], 0
0x1800c101d  jz      loc_1800C1151
0x1800c1023  lea     r9, [rbp+arg_18]
0x1800c1027  mov     [rbp+arg_18], 0
0x1800c102e  mov     r8d, 8Ch
0x1800c1034  mov     rdx, rbx
0x1800c1037  mov     rcx, r13
0x1800c103a  call    ?GetIsWarningStateDismissedForUser@ForceFieldShield@ShieldProvider@@AEAAJAEBU_GUID@@W4PillarStatusFlag@@PEAH@Z; ShieldProvider::ForceFieldShield::GetIsWarningStateDismissedForUser(_GUID const &,PillarStatusFlag,int *)
0x1800c103f  cmp     dword ptr [rbx+34h], 3
0x1800c1043  jnz     short loc_1800C10A2
0x1800c1045  cmp     esi, 8
0x1800c1048  jge     loc_1800C1137
0x1800c104e  mov     esi, 8
0x1800c1053  mov     r15d, 8Dh
0x1800c1059  test    rdi, rdi
0x1800c105c  jz      short loc_1800C108D
0x1800c105e  mov     rcx, [rdi+10h]; pv
0x1800c1062  call    cs:__imp_CoTaskMemFree
0x1800c1068  mov     rcx, [rdi+18h]; pv
0x1800c106c  call    cs:__imp_CoTaskMemFree
0x1800c1072  mov     rcx, [rdi+20h]; pv
0x1800c1076  call    cs:__imp_CoTaskMemFree
0x1800c107c  mov     rcx, rdi; pv
0x1800c107f  call    cs:__imp_CoTaskMemFree
0x1800c1085  mov     [rbp+var_10], 0
0x1800c108d  lea     rdx, [rbp+var_10]; struct Shield_ForceFieldProviderInfo **
0x1800c1091  mov     rcx, rbx; struct Shield_ForceFieldProviderInfo *
0x1800c1094  call    ?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)
0x1800c1099  mov     rdi, [rbp+var_10]
0x1800c109d  jmp     loc_1800C1137
0x1800c10a2  cmp     dword ptr [rbx+34h], 2
0x1800c10a6  jnz     short loc_1800C1121
0x1800c10a8  cmp     [rbp+arg_18], 0
0x1800c10ac  jz      short loc_1800C10C7
0x1800c10ae  cmp     esi, 2
0x1800c10b1  jge     loc_1800C1151
0x1800c10b7  mov     esi, 2
0x1800c10bc  mov     r15d, 8Bh
0x1800c10c2  jmp     loc_1800C1151
0x1800c10c7  cmp     esi, 4
0x1800c10ca  jge     loc_1800C1151
0x1800c10d0  mov     esi, 4
0x1800c10d5  mov     r15d, 8Ch
0x1800c10db  test    rdi, rdi
0x1800c10de  jz      short loc_1800C110F
0x1800c10e0  mov     rcx, [rdi+10h]; pv
0x1800c10e4  call    cs:__imp_CoTaskMemFree
0x1800c10ea  mov     rcx, [rdi+18h]; pv
0x1800c10ee  call    cs:__imp_CoTaskMemFree
0x1800c10f4  mov     rcx, [rdi+20h]; pv
0x1800c10f8  call    cs:__imp_CoTaskMemFree
0x1800c10fe  mov     rcx, rdi; pv
0x1800c1101  call    cs:__imp_CoTaskMemFree
0x1800c1107  mov     [rbp+var_10], 0
0x1800c110f  lea     rdx, [rbp+var_10]; struct Shield_ForceFieldProviderInfo **
0x1800c1113  mov     rcx, rbx; struct Shield_ForceFieldProviderInfo *
0x1800c1116  call    ?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)
0x1800c111b  mov     rdi, [rbp+var_10]
0x1800c111f  jmp     short loc_1800C1151
0x1800c1121  cmp     dword ptr [rbx+34h], 1
0x1800c1125  jnz     short loc_1800C1151
0x1800c1127  cmp     esi, 2
0x1800c112a  jge     short loc_1800C1137
0x1800c112c  mov     esi, 2
0x1800c1131  mov     r15d, 8Bh
0x1800c1137  cmp     [rbp+arg_18], 0
0x1800c113b  jz      short loc_1800C1151
0x1800c113d  xor     r9d, r9d
0x1800c1140  mov     r8d, 8Ch
0x1800c1146  mov     rdx, rbx
0x1800c1149  mov     rcx, r13
0x1800c114c  call    ?ChangeWarningStateDismissalForUser@ForceFieldShield@ShieldProvider@@AEAAJAEBU_GUID@@W4PillarStatusFlag@@_N@Z; ShieldProvider::ForceFieldShield::ChangeWarningStateDismissalForUser(_GUID const &,PillarStatusFlag,bool)
0x1800c1151  inc     r14d
0x1800c1154  cmp     r14d, [rbp+arg_0]
0x1800c1158  jb      loc_1800C100E
0x1800c115e  xor     r14d, r14d
0x1800c1161  cmp     [rbp+arg_0], r14d
0x1800c1165  jbe     short loc_1800C11A4
0x1800c1167  mov     rcx, [rbp+pv]
0x1800c116b  mov     ebx, r14d
0x1800c116e  shl     rbx, 6
0x1800c1172  mov     rcx, [rbx+rcx+10h]; pv
0x1800c1177  call    cs:__imp_CoTaskMemFree
0x1800c117d  mov     rcx, [rbp+pv]
0x1800c1181  mov     rcx, [rbx+rcx+18h]; pv
0x1800c1186  call    cs:__imp_CoTaskMemFree
0x1800c118c  mov     rcx, [rbp+pv]
0x1800c1190  mov     rcx, [rbx+rcx+20h]; pv
0x1800c1195  call    cs:__imp_CoTaskMemFree
0x1800c119b  inc     r14d
0x1800c119e  cmp     r14d, [rbp+arg_0]
0x1800c11a2  jb      short loc_1800C1167
0x1800c11a4  mov     rcx, [rbp+pv]; pv
0x1800c11a8  call    cs:__imp_CoTaskMemFree
0x1800c11ae  mov     ebx, [rbp+var_20]
0x1800c11b1  mov     r14, [rbp+arg_10]
0x1800c11b5  mov     [rbp+pv], 0
0x1800c11bd  mov     [r12], r15d
0x1800c11c1  mov     [r12+4], esi
0x1800c11c6  test    rdi, rdi
0x1800c11c9  jz      short loc_1800C11FF
0x1800c11cb  mov     rax, rdi
0x1800c11ce  xor     edi, edi
0x1800c11d0  mov     [r14], rax
0x1800c11d3  test    rdi, rdi
0x1800c11d6  jz      short loc_1800C11FF
0x1800c11d8  mov     rcx, [rdi+10h]; pv
0x1800c11dc  call    cs:__imp_CoTaskMemFree
0x1800c11e2  mov     rcx, [rdi+18h]; pv
0x1800c11e6  call    cs:__imp_CoTaskMemFree
0x1800c11ec  mov     rcx, [rdi+20h]; pv
0x1800c11f0  call    cs:__imp_CoTaskMemFree
0x1800c11f6  mov     rcx, rdi; pv
0x1800c11f9  call    cs:__imp_CoTaskMemFree
0x1800c11ff  mov     eax, ebx
0x1800c1201  mov     rbx, [rsp+40h+arg_8]
0x1800c1209  add     rsp, 40h
0x1800c120d  pop     r15
0x1800c120f  pop     r14
0x1800c1211  pop     r13
0x1800c1213  pop     r12
0x1800c1215  pop     rdi
0x1800c1216  pop     rsi
0x1800c1217  pop     rbp
0x1800c1218  retn
```

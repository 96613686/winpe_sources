# SiFixupResiliency(_SU_POOL_OBJECT *,_SI_CREATE_CONTEXT *)

- ea: `0x140011a74`
- end: `0x140011bb2`
- name: `?SiFixupResiliency@@YAHPEAU_SU_POOL_OBJECT@@PEAU_SI_CREATE_CONTEXT@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, struct _SI_CREATE_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140010f8c`

## callees

- `0x14000e298`
- `0x140011a74`
- `0x140013c64`
- `0x140014324`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140011b16`
- `KERNEL32!SetLastError` at `0x140011b16`

## pseudocode

```c
__int64 __fastcall SiFixupResiliency(struct _SU_POOL_OBJECT *a1, struct _SI_CREATE_CONTEXT *a2)
{
  int *v2; // rbx
  unsigned int v5; // ebp
  int *v6; // r9
  int v7; // eax
  unsigned int v8; // eax
  unsigned int NumberOfFaultDomains; // r8d
  int *v10; // r9
  bool v11; // zf
  unsigned int v12; // esi
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // r14d
  int v17; // eax
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v20; // [rsp+60h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)a2 + 2);
  v20 = 0;
  v5 = 1;
  v6 = v2 + 3;
  if ( *v2 == 3 )
  {
    v7 = *v6;
    if ( *v6 == -1 )
      v7 = 1;
    v5 = 3 * v7 + v2[1] - 1;
  }
  v8 = SP_RESILIENCY_INFO::DefaultNumberOfColumns((SP_RESILIENCY_INFO *)v2);
  v11 = *v2 == 3;
  v12 = v8;
  v19 = v8;
  if ( v11 && *v10 == -1 )
  {
    v13 = *((_QWORD *)a2 + 1);
    if ( *(_DWORD *)(v13 + 20) == *(_DWORD *)(v13 + 28) )
    {
      *(_DWORD *)a2 |= 2u;
      NumberOfFaultDomains = SiGetNumberOfFaultDomains((char *)a1 + 64, *(unsigned int *)(v13 + 28), &v19);
      if ( !NumberOfFaultDomains )
        return NumberOfFaultDomains;
      v12 = v19;
      if ( v19 < v5 )
      {
LABEL_10:
        SetLastError(0x13Au);
        return 0;
      }
      if ( v19 > v5 )
        v12 = v19 - 1;
    }
    else
    {
      v14 = v2[1];
      v15 = v14;
      *v10 = v14;
      if ( v14 == -1 )
        v15 = NumberOfFaultDomains;
      v5 = v15 - 1 + v14 + 2 * v15;
      v12 = SP_RESILIENCY_INFO::DefaultNumberOfColumns((SP_RESILIENCY_INFO *)v2);
    }
  }
  if ( *v2 != 2 || v2[2] != 2 )
  {
    v16 = 2 * v2[1] + 1;
    if ( v5 < v16 )
    {
      NumberOfFaultDomains = SuGetNumberOfDrives((struct _GUID *)((char *)a1 + 40), &v20);
      if ( !NumberOfFaultDomains )
        return NumberOfFaultDomains;
      if ( v20 < v16 )
        goto LABEL_10;
    }
  }
  v17 = v2[4];
  if ( v17 == -1 )
  {
    *((_DWORD *)a2 + 12) = v12;
    *((_DWORD *)a2 + 13) = v5;
  }
  else
  {
    *((_DWORD *)a2 + 12) = v17;
    *((_DWORD *)a2 + 13) = v2[4];
  }
  return NumberOfFaultDomains;
}

```

## disassembly

```asm
0x140011a74  mov     [rsp+arg_0], rbx
0x140011a79  mov     [rsp+arg_18], rbp
0x140011a7e  push    rsi
0x140011a7f  push    rdi
0x140011a80  push    r12
0x140011a82  push    r14
0x140011a84  push    r15
0x140011a86  sub     rsp, 20h
0x140011a8a  mov     rbx, [rdx+10h]
0x140011a8e  or      r12d, 0FFFFFFFFh
0x140011a92  mov     r8d, 1
0x140011a98  mov     [rsp+48h+arg_10], 0
0x140011aa0  mov     rdi, rdx
0x140011aa3  mov     r15, rcx
0x140011aa6  mov     ebp, r8d
0x140011aa9  cmp     dword ptr [rbx], 3
0x140011aac  lea     r9, [rbx+0Ch]
0x140011ab0  jnz     short loc_140011AC6
0x140011ab2  mov     eax, [r9]
0x140011ab5  cmp     eax, r12d
0x140011ab8  mov     ebp, [rbx+4]
0x140011abb  cmovz   eax, r8d
0x140011abf  dec     ebp
0x140011ac1  lea     ecx, [rax+rax*2]
0x140011ac4  add     ebp, ecx
0x140011ac6  mov     rcx, rbx; this
0x140011ac9  call    ?DefaultNumberOfColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::DefaultNumberOfColumns(void)
0x140011ace  cmp     dword ptr [rbx], 3
0x140011ad1  mov     esi, eax
0x140011ad3  mov     [rsp+48h+arg_8], eax
0x140011ad7  jnz     short loc_140011B48
0x140011ad9  cmp     [r9], r12d
0x140011adc  jnz     short loc_140011B48
0x140011ade  mov     rdx, [rdi+8]
0x140011ae2  mov     eax, [rdx+1Ch]
0x140011ae5  cmp     [rdx+14h], eax
0x140011ae8  jnz     short loc_140011B28
0x140011aea  or      dword ptr [rdi], 2
0x140011aed  lea     rcx, [r15+40h]
0x140011af1  mov     edx, [rdx+1Ch]
0x140011af4  lea     r8, [rsp+48h+arg_8]
0x140011af9  call    ?SiGetNumberOfFaultDomains@@YAHPEAU_GUID@@W4_SC_FD_TYPE@@PEAK@Z; SiGetNumberOfFaultDomains(_GUID *,_SC_FD_TYPE,ulong *)
0x140011afe  mov     r8d, eax
0x140011b01  test    eax, eax
0x140011b03  jz      loc_140011B98
0x140011b09  mov     esi, [rsp+48h+arg_8]
0x140011b0d  cmp     esi, ebp
0x140011b0f  jnb     short loc_140011B21
0x140011b11  mov     ecx, 13Ah; dwErrCode
0x140011b16  call    cs:__imp_SetLastError
0x140011b1c  xor     r8d, r8d
0x140011b1f  jmp     short loc_140011B98
0x140011b21  jbe     short loc_140011B48
0x140011b23  add     esi, r12d
0x140011b26  jmp     short loc_140011B48
0x140011b28  mov     eax, [rbx+4]
0x140011b2b  mov     ecx, eax
0x140011b2d  cmp     eax, r12d
0x140011b30  mov     [r9], eax
0x140011b33  cmovz   ecx, r8d
0x140011b37  lea     ebp, [rax+rcx*2]
0x140011b3a  dec     ecx
0x140011b3c  add     ebp, ecx
0x140011b3e  mov     rcx, rbx; this
0x140011b41  call    ?DefaultNumberOfColumns@SP_RESILIENCY_INFO@@QEAAKXZ; SP_RESILIENCY_INFO::DefaultNumberOfColumns(void)
0x140011b46  mov     esi, eax
0x140011b48  cmp     dword ptr [rbx], 2
0x140011b4b  jnz     short loc_140011B53
0x140011b4d  cmp     dword ptr [rbx+8], 2
0x140011b51  jz      short loc_140011B7F
0x140011b53  mov     eax, [rbx+4]
0x140011b56  lea     r14d, ds:1[rax*2]
0x140011b5e  cmp     ebp, r14d
0x140011b61  jnb     short loc_140011B7F
0x140011b63  lea     rcx, [r15+28h]; struct _GUID *
0x140011b67  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x140011b6c  call    ?SuGetNumberOfDrives@@YAHPEAU_GUID@@PEAK@Z; SuGetNumberOfDrives(_GUID *,ulong *)
0x140011b71  mov     r8d, eax
0x140011b74  test    eax, eax
0x140011b76  jz      short loc_140011B98
0x140011b78  cmp     [rsp+48h+arg_10], r14d
0x140011b7d  jb      short loc_140011B11
0x140011b7f  mov     eax, [rbx+10h]
0x140011b82  cmp     eax, r12d
0x140011b85  jnz     short loc_140011B8F
0x140011b87  mov     [rdi+30h], esi
0x140011b8a  mov     [rdi+34h], ebp
0x140011b8d  jmp     short loc_140011B98
0x140011b8f  mov     [rdi+30h], eax
0x140011b92  mov     eax, [rbx+10h]
0x140011b95  mov     [rdi+34h], eax
0x140011b98  mov     rbx, [rsp+48h+arg_0]
0x140011b9d  mov     eax, r8d
0x140011ba0  mov     rbp, [rsp+48h+arg_18]
0x140011ba5  add     rsp, 20h
0x140011ba9  pop     r15
0x140011bab  pop     r14
0x140011bad  pop     r12
0x140011baf  pop     rdi
0x140011bb0  pop     rsi
0x140011bb1  retn
```
